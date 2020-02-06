---
title: 為邊緣伺服器設定埠範圍和服務品質
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本文說明如何設定邊緣伺服器的埠範圍，以及如何設定您的 A/V 邊緣伺服器的服務品質原則。
ms.openlocfilehash: 5762cb6861552696f160dfe69459c357f6b63452
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817432"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a>在商務用 Skype Server 中針對 Edge 伺服器設定埠範圍和服務品質原則

本文說明如何設定邊緣伺服器的埠範圍，以及如何設定您的 A/V 邊緣伺服器的服務品質原則。

## <a name="configure-port-ranges"></a>設定埠範圍

有了 Edge 伺服器，您就不需要針對音訊、影片和應用程式共用設定個別的埠範圍;同樣地，邊緣伺服器所用的埠範圍不一定要與您的會議、應用程式及中繼伺服器所使用的埠範圍相符。 在開始使用我們的範例之前，請務必先將這個選項提供給您，但我們建議您不要變更埠範圍，因為如果您移出50000埠範圍，就可能會對某些案例造成負面影響。

例如，假設您已將會議、應用程式和中繼伺服器設定為使用這些埠範圍：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>資料包類型</th>
<th>起始埠</th>
<th>保留的埠數</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>應用程式共用</p></td>
<td><p>40803</p></td>
<td><p>8348</p></td>
</tr>
<tr class="even">
<td><p>音訊</p></td>
<td><p>49152</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>顯示器</p></td>
<td><p>57500</p></td>
<td><p>8034</p></td>
</tr>
<tr class="even">
<td><p><strong>本壘</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


如您所見，音訊、影片和應用程式共用的埠範圍是從埠40803開始，並包含總共24732個埠。 如果您想要的話，您可以將指定的邊緣伺服器設定為使用這些整體埠值，方法是從商務用 Skype Server 管理命令介面中執行如下的命令：

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

或者，使用下列命令同時設定貴組織中的所有邊緣伺服器：

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

您可以使用此商務用 Skype Server Management Shell 命令來驗證邊緣伺服器的目前埠設定：

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

同樣地，雖然我們確實提供這些選項，但我們強烈建議您將它們留給埠配置。

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a>為您的 A/V 邊緣伺服器設定 QoS 原則

除了為您的會議、應用程式和中繼伺服器建立 QoS 原則之外，您還必須為 A/V 邊緣伺服器的內部端建立音訊與影片原則。 不過，在 Edge 伺服器上使用的原則與在您的會議、應用程式和中繼伺服器上使用的原則不同。 針對會議、應用程式及中繼伺服器，您指定了來源埠範圍;有了 Edge 伺服器，您必須指定目的地埠範圍。 因此，您無法直接將會議、應用程式和中繼伺服器 QoS 原則套用到您的邊緣伺服器：這些原則根本無法運作。 相反地，您必須建立新的原則，並將這些原則只套用到 Edge 伺服器。

下列程式說明建立 Active Directory 群組原則物件的程式，這些物件可用於管理 Edge 伺服器上的服務品質。 當然，您的邊緣伺服器可能是不具備 Active Directory 帳戶的獨立伺服器。 如果是這種情況，您可以使用本機組策略，而不是 Active Directory 群組原則：唯一的差別是，您必須使用本機組策略編輯器來建立這些本機原則，而且必須在每個 Edge 伺服器上分別建立相同的原則組。 若要在 Edge 伺服器上啟動本機組策略編輯器，請執行下列動作：

1.  按一下 [**開始**]，然後按一下 [**執行**]。

2.  在 [**執行**] 對話方塊中，輸入 [ **gpedit.msc**]，然後按 enter。

如果您要建立 Active Directory 的原則，您應該登入已安裝群組原則管理的電腦。 在這種情況下，請開啟 [群組原則管理] （按一下 [**開始**]，指向 [系統**管理工具**]，然後按一下 [**群組原則管理**]），然後完成下列步驟：

1.  在 [群組原則管理] 中，找出要建立新原則的容器。 例如，如果您所有的商務用 Skype Server 電腦都位於名為商務用 Skype Server 的 OU 中，則應該在商務用 Skype Server OU 中建立新原則。

2.  以滑鼠右鍵按一下適當的容器，然後按一下 [**在這個網域建立 GPO]，然後在這裡連結**。

3.  在 [**新增 GPO** ] 對話方塊的 [**名稱**] 方塊中，輸入新群組原則物件的名稱（例如商務用**Skype Server 音訊**），然後按一下 **[確定]**。

4.  以滑鼠右鍵按一下新建立的原則，然後按一下 [**編輯**]。

無論您是建立 Active Directory 原則或本機原則，此程式都是相同的：

1.  在 [群組原則管理編輯器] 或 [本機組策略編輯器] 中，展開 [**電腦**設定]，展開 [**原則**]，展開 [ **Windows 設定**]，以滑鼠右鍵按一下 [**原則式 QoS**]，然後按一下 [**建立新策略**]。

2.  在 [**原則式 QoS** ] 對話方塊的 [開始] 頁面上，于 [**名稱**] 方塊中輸入新原則的名稱（例如**商務用 Skype Server 音訊**）。 選取 [**指定 DSCP 值**]，然後將值設定為**46**。 [離開]**指定輸出限制率**未選取，然後按 **[下一步]**。

3.  在下一頁上，確認已選取 [**所有應用程式**]，然後按一下 **[下一步]**。 此設定會指示網路尋找 DSCP 標記為46的所有資料包，而不只是特定應用程式所建立的資料包。

4.  在第三個頁面上，確認已選取 [**所有來源 ip 位址**] 和 [**任何目的地 ip 位址**]，然後按一下 **[下一步]**。 這兩項設定可確保無論哪些電腦（IP 位址）傳送這些資料包，以及哪些電腦（IP 位址）會接收那些資料包，都會管理資料包。

5.  在第4頁，從 [**選取此 QoS 原則適用**于] 下拉式清單中選取 [ **TCP 和 UDP** ]。 TCP （傳輸控制通訊協定）和 UDP （使用者資料包通訊協定）是商務用 Skype Server 及其用戶端應用程式最常用的兩種網路通訊協定。

6.  在 [標題] 底下**指定目的地埠號**，選取 [**從此目的地埠或範圍**]。 在隨附的文字方塊中，輸入為音訊廣播保留的埠範圍。 例如，如果您是透過埠57500將埠49152保留音訊流量，請輸入使用此格式的埠範圍： **49152:57500**。 按一下 **[完成]**。

在您建立音訊流量的 QoS 原則之後，您應該為影片流量建立第二個原則。 若要建立影片的原則，請遵循您在建立音訊原則時所遵循的基本程式，進行這些替換：

  - 使用不同（且唯一的）原則名稱（例如商務用**Skype Server 影片**）。

  - 將 DSCP 值設為**34** ，而不是46。 （請注意，您不需要使用34的 DSCP 值。 唯一的需求是，您針對影片使用的 DSCP 值與音訊所用的不同。

  - 使用先前設定的影片流量埠範圍。 例如，如果您已將埠57501到65535的備用，請將埠範圍設定為： **57501:65535**。 同樣地，應該將它設定為目的地埠範圍。

如果您決定建立用來管理應用程式共用流量的原則，您必須建立第三個原則，以進行下列替換：

  - 使用不同（且唯一的）原則名稱（例如，**商務用 Skype Server 應用程式共用**）。

  - 將 DSCP 值設為**24** ，而不是46。 （同樣地，您不需要使用 DSCP 值24。 唯一的需求是，您針對與音訊或影片搭配使用的應用程式共用，使用不同的 DSCP 值。

  - 使用先前設定的影片流量埠範圍。 例如，如果您已在應用程式共用中保留埠40803到49151，請將埠範圍設定為： **40803:49151**。

您所建立的新原則必須在您的 Edge 伺服器上刷新群組原則之後，才會生效。 雖然群組原則會定期自行進行重新整理，但是您可以在需要重新整理群組原則的每一台電腦上執行下列命令，以強制立即重新整理：

    Gpudate.exe /force

此命令可以從商務用 Skype 伺服器內執行，或是從任何在 [管理員認證] 下執行的命令視窗中執行。 若要在 [管理員認證] 下執行命令視窗，請按一下 [**開始**]，以滑鼠右鍵按一下**命令提示**字元，然後按一下 [**以系統管理員身分執行**] 請注意，即使執行 Gpudate 之後，您可能還需要重新開機 Edge 伺服器。

若要協助確保網路資料包是以適當的 DSCP 值標示，您也應該透過完成下列程式，在每個電腦上建立新的登錄專案：

1.  按一下 [**開始**]，然後按一下 [**執行**]。

2.  在 [**執行**] 對話方塊中，輸入**regedit**，然後按 enter。

3.  在 [登錄編輯程式] 中，展開 [ **HKEY\_本機\_電腦**]，展開 [**系統**]、[ **CurrentControlSet**]、[**服務**]，然後再展開 [ **Tcpip**]。

4.  以滑鼠右鍵按一下 [ **Tcpip**]，指向 [**新增**]，然後按一下 [**金鑰**]。 建立新的登錄金鑰之後，請輸入**QoS**，然後按 enter 來重新命名金鑰。

5.  以滑鼠右鍵按一下 [ **QoS**]，指向 [**新增**]，然後按一下 [**字串值**]。 建立新的登錄值之後，請輸入 [**不使用 NLA**]，然後按 enter 鍵來重新命名值。

6.  按兩下 [**不使用 NLA**]。 在 [**編輯字串**] 對話方塊中，于 [**值資料**] 方塊中輸入**1** ，然後按一下 **[確定]**。

7.  關閉 [登錄編輯程式]，然後重新開機您的電腦。
