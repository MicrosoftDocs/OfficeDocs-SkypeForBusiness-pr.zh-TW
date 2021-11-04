---
title: 設定 Edge Server 的埠範圍和服務品質
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 本文說明如何設定 Edge Server 的埠範圍，以及如何為您的 A/V Edge Server 設定服務品質原則。
ms.openlocfilehash: 1f455ab417ed111a34134e3581806b4ce2a4bd57
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778303"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a>在商務用 Skype Server 中設定 Edge server 的埠範圍和服務品質原則

本文說明如何設定 Edge Server 的埠範圍，以及如何為您的 A/V Edge Server 設定服務品質原則。

## <a name="configure-port-ranges"></a>設定埠範圍

透過 Edge server，您不需要為音訊、影片和應用程式共用設定個別的埠範圍;同樣地，Edge server 所用的埠範圍不必比對您的會議、應用程式及轉送伺服器所使用的埠範圍。 在繼續進行範例之前，請務必強調此選項存在時，建議您不要變更埠範圍，因為當您移出50000埠範圍時，可能會對某些案例產生負面影響。

例如，假設您已設定會議、應用程式以及中繼伺服器以使用這些連接埠範圍：


<table>
<colgroup>
</colgroup>
<thead>
<tr class="header">
<th>封包類型</th>
<th>起始連接埠</th>
<th>已保留連接埠數目</th>
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
<td><p>影片</p></td>
<td><p>57500</p></td>
<td><p>8034</p></td>
</tr>
<tr class="even">
<td><p><strong>總數</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


如您所見，音訊、影片和應用程式共用的埠範圍會從埠40803開始，並包含24732埠的總數。 如果您願意，您可以從商務用 Skype Server 管理命令介面中執行類似如下的命令，將指定的 Edge Server 設定為使用這些整體埠值：

  **Set-CsEdgeServer-Identity EdgeServer:atl-edge-001.litwareinc.com-MediaCommunicationPortStart 40803-MediaCommunicationPortCount 24730**

或者，使用下列命令以在組織中同時設定所有 Edge 伺服器：

  **Get-CsService-Edgeserver atl-edge |ForEach-Object {Set-CsEdgeServer-Identity $ _。Identity-MediaCommunicationPortStart 40803-MediaCommunicationPortCount 24730}**

您可以使用下列商務用 Skype Server 管理命令介面命令來驗證 Edge server 的目前埠設定：

  **Get-CsService-Edgeserver atl-edge |Select-Object 身分識別、MediaCommunicationPortStart、MediaCommunicationPortCount**

同樣地，我們確實提供這些選項，我們強烈建議您保留其為埠設定的內容。

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a>設定 A/V Edge Server 的 QoS 原則

除了為會議伺服器、應用程式伺服器及中繼伺服器建立 QoS 原則，您也必須為 A/V Edge Server 的內部端建立音訊及視訊原則。 不過，在 Edge Server 上使用的原則，不同於在會議伺服器、應用程式伺服器及中繼伺服器上使用的原則。 針對會議、應用程式及轉送伺服器，您指定了來源埠範圍;透過 Edge server，您必須指定目的地埠範圍。 因此，您無法只將會議、應用程式及轉送伺服器 QoS 原則套用至 Edge server：這些原則根本無法運作。 反之，您必須建立新的原則，並將這些原則只套用到 Edge Server。

下列程序說明如何在 Edge Server 上，建立可以用來管理服務品質的 Active Directory 群組原則物件。 當然，您的 Edge Server 有可能是沒有 Active Directory 帳戶的獨立伺服器。 若是如此，您可以使用本機群組原則來代替 Active Directory 群組原則：唯一不同的是，您必須使用本機群組原則編輯器來建立這些本機原則，而且必須在每部 Edge Server 上個別建立相同的原則集。 若要在 Edge server 上啟動本機組策略編輯器，請執行下列操作：

1.  按一下 **[開始]**，再按一下 **[執行]**。

2.  在 [ **執行** ] 對話方塊中，輸入 **gpedit.msc**，然後按 enter。

如果您要建立 Active Directory 型原則，應登入已安裝群組原則管理的電腦。 在此情況下，請開啟 [群組原則管理] (按一下 [ **開始**]，指向 [系統 **管理工具**]，然後按一下 [ **群組原則管理**) ]，然後完成下列步驟：

1.  在群組原則管理中，找出要用來建立新原則的容器。 例如，如果您的所有商務用 Skype Server 電腦都位於名為商務用 Skype Server 的 OU 中，則應該在商務用 Skype Server OU 中建立新的原則。

2.  以滑鼠右鍵按一下適當的容器，然後按一下 [ **在這個網域中建立 GPO]，並在這裡連結**。

3.  在 [**新增 GPO** ] 對話方塊的 [**名稱**] 方塊中，輸入新群組原則物件的名稱 (例如，**商務用 Skype Server 音訊**) ]，然後按一下 **[確定]**。

4.  以滑鼠右鍵按一下新建立的原則，然後按一下 [ **編輯**]。

從這裡開始，無論您是要建立 Active Directory 原則或本機原則，程序都一樣：

1.  在群組原則管理編輯器或本機群組原則編輯器中，依序展開 [電腦設定]、[原則]、[Windows 設定]，以滑鼠右鍵按一下 [以原則為依據的 QoS]，然後按一下 [建立新原則]。

2.  在 [**原則型 QoS** ] 對話方塊的 [開始] 頁面上，于 [**名稱**] 方塊中輸入新原則的名稱 (例如，**商務用 Skype Server Audio**) 。 選取 [指定 DSCP 數值]，並將該值設為 **46**。 將 [指定輸出節流閥速率] 保留未選取狀態，然後按 [下一步]。

3.  在下一個頁面上，確定已選取 [ **所有應用程式** ]，然後按 **[下一步]**。 此設定會指示網路尋找 DSCP 標示為 46 的所有封包，而不只是特定應用程式建立的封包。

4.  在第三頁上，確定已選取 [ **所有來源 ip 位址** ] 和 [ **任何目的地 ip 位址** ]，然後按 **[下一步]**。 這兩個設定可確保無論是哪部電腦 (IP 位址) 傳送封包，以及哪部電腦 (IP 位址) 接收封包，那些封包都會受到管理。

5.  在第四頁上，從 [選取此 QoS 原則套用的通訊協定] 下拉式清單中選取 [TCP 及 UDP]。 TCP (傳輸控制通訊協定) 和 UDP (使用者資料包通訊協定) 是商務用 Skype Server 及其用戶端應用程式最常使用的兩種網路通訊協定。

6.  在 [指定目的地連接埠號碼] 標題底下，選取 [從此目的地連接埠或範圍]。 在隨附的文字方塊中，輸入為音訊傳輸保留的連接埠範圍。 例如，如果您將埠49152設定為音訊流量的埠57500，請輸入使用此格式的埠範圍： **49152:57500**。 按一下 **[完成]**。

在建立音訊流量的 QoS 原則之後，您應該先建立影片流量的第二個原則。 若要為視訊建立原則，請遵循您建立音訊原則時所使用的相同基本程序，並替換下列項目：

  - 使用不同的 (和唯一的) 原則名稱 (例如 **商務用 Skype Server 影片**) 。

  - 將 DSCP 值設為 **34** 而不是 46。(請注意，DSCP 值不一定要使用 34。唯一的要求是用於視訊和音訊的 DSCP 值必須不同。)

  - 使用先前設定的影片流量的埠範圍。 例如，如果您有保留的埠57501到65535以取得影片，請將埠範圍設定為： **57501:65535**。 再強調一次，這應該設為目的地連接埠範圍。

如果您決定建立用來管理應用程式共用流量的原則，則必須建立第三個原則，以進行下列替代：

  - 使用不同的 (和唯一的) 原則名稱 (例如，**商務用 Skype Server 應用程式共用**) 。

  - 將 DSCP 值設為 **24** 而不是 46。(再強調一次，DSCP 值不一定要使用 24。唯一的要求是用於應用程式共用的 DSCP 值必須與視訊或音訊不同。)

  - 使用先前設定的影片流量的埠範圍。 例如，如果您有保留埠40803到49151以進行應用程式共用，請將埠範圍設定為： **40803:49151**。

必須在 Edge Server 上重新整理群組原則之後，您建立的新原則才會生效。雖然群組原則本身會定期重新整理，但您可以在需要重新整理群組原則的每部電腦上執行下列命令，以強制立即重新整理：

 **Gpudate.exe/force**

這個命令可以從商務用 Skype Server 中執行，或從任何以系統管理員認證執行的命令視窗執行。 若要以系統管理員憑證執行命令視窗，請按一下 [開始]，以滑鼠右鍵按一下 [命令提示字元]，然後按一下 [以系統管理員身分執行]。 請注意，即使在執行 Gpudate.exe 之後，可能還是需要重新啟動 Edge Server。

為幫助確保網路封包標示適當的 DSCP 值，您也應該要在每部電腦上建立新的登錄項目，請完成下列程序：

1.  按一下 **[開始]**，再按一下 **[執行]**。

2.  在 [ **執行** ] 對話方塊中，輸入 **regedit**，然後按 enter。

3.  在 [登錄編輯程式] 中，展開 [ **HKEY \_ 本機 \_ 電腦**]，展開 [ **系統**]，展開 [ **CurrentControlSet**]，展開 [ **服務**]，然後展開 [ **Tcpip**]。

4.  以滑鼠右鍵按一下 [Tcpip]，指向 [新增]，然後按一下 [索引鍵]。 在建立新的登錄機碼之後，輸入 **QoS**，然後按 enter 重新命名機碼。

5.  以滑鼠右鍵按一下 [QoS]，指向 [新增]，然後按一下 [字串值]。 在建立新的登錄值之後，請輸入 [ **不要使用 NLA**]，然後按 enter 鍵來重新命名值。

6.  按兩下 [Do not use NLA]。 在 [**編輯字串**] 對話方塊的 [**數值資料**] 方塊中，輸入 **1** ，然後按一下 **[確定]**。

7.  關閉 [登錄編輯程式]，然後重新開機電腦。
