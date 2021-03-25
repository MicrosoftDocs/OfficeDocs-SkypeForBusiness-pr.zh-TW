---
title: 為用戶端設定埠範圍和服務品質原則
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本文說明如何為您的用戶端設定埠範圍，以及如何為在 Windows 10 上執行的用戶端在商務用 Skype Server 中設定服務品質原則。
ms.openlocfilehash: 9cd5fe3fa84c4acd9365e02c0e5801b63d5497d1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122427"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>為商務用 Skype Server 中的用戶端設定埠範圍和服務品質原則

本文說明如何為您的用戶端設定埠範圍，以及如何為在 Windows 10 上執行的用戶端在商務用 Skype Server 中設定服務品質原則。

## <a name="configure-port-ranges"></a>設定埠範圍

根據預設，商務用 Skype 用戶端應用程式可以使用埠1024和65535之間的任何埠，與通訊會話相關;這是因為不會自動為用戶端啟用特定埠範圍。 然而為了使用服務品質，您必須將各種流量類型重新分派 (音訊、視訊、媒體、應用程式共用及檔案傳輸) 至一系列的唯一連接埠範圍。 使用 Set-CsConferencingConfiguration Cmdlet 可達成此目的。

> [!NOTE]  
> 使用者無法自行進行這些變更。 只有管理員使用 Set-CsConferencingConfiguration Cmdlet 才能進行埠變更。


您可以從商務用 Skype Server 管理命令介面中執行下列命令，判斷目前用於通訊會話的埠範圍：

    Get-CsConferencingConfiguration

假設您在安裝商務用 Skype Server 後，尚未對會議設定進行任何變更，您應該會收到包含下列屬性值的資訊：

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

若您仔細看前面的輸出，就會注意到兩項重點。 首先，ClientMediaPortRangeEnabled 屬性是設為 False：

    ClientMediaPortRangeEnabled : False

這一點很重要，因為當此屬性設定為 False 時，商務用 Skype 用戶端會在通訊會話中時使用埠1024和65535之間的任何可用埠;不論任何其他埠設定 (例如，ClientMediaPort 或 ClientVideoPort) ，都是如此。 如果您想要將使用限制在一組指定的埠 (，而這是您在規劃執行服務品質) 時所要執行的動作，則必須先啟用用戶端媒體埠範圍。 可以使用下列 Windows PowerShell 命令來完成：

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

前面的命令會啟用全域會議組態設定集合的用戶端媒體連接埠；不過這些設定也可套用至網站範圍及/或服務範圍 (僅限會議伺服器服務)。若要啟用特定網站或伺服器的用戶端媒體連接埠範圍，請在呼叫 Set-CsConferencingConfiguration 時指定該網站或伺服器的識別：

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

或者，您也可使用此命令，同時啟用所有會議組態設定的連接埠範圍：

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

您注意到的第二項重點是範例輸出顯示，根據預設，針對每個網路流量類型所設定的媒體連接埠範圍皆為相同：

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

為了實作 QoS，其中的每個連接埠範圍皆必須是唯一的連接埠範圍。例如，您可能設定了如下的連接埠範圍：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>用戶端流量類型</th>
<th>連接埠開始</th>
<th>連接埠範圍</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音訊</p></td>
<td><p>50020</p></td>
<td><p>共</p></td>
</tr>
<tr class="even">
<td><p>影片</p></td>
<td><p>58000</p></td>
<td><p>共</p></td>
</tr>
<tr class="odd">
<td><p>應用程式共用</p></td>
<td><p>42000</p></td>
<td><p>共</p></td>
</tr>
<tr class="even">
<td><p>檔案傳輸</p></td>
<td><p>42020</p></td>
<td><p>共</p></td>
</tr>
</tbody>
</table>


在上表中，用戶端埠範圍代表為您的伺服器設定的埠範圍的子集。 例如，在伺服器上，應用程式共用設定為使用埠40803到 49151;在用戶端電腦上，應用程式共用設定為使用埠42000到42019。 這樣做也主要是為了簡化 QoS 的管理：用戶端埠不一定要代表伺服器上使用的埠子集。  (例如，在用戶端電腦上，您可以設定要使用的應用程式共用，比如說，埠10000到10019。 ) 不過，建議您讓用戶端埠範圍成為伺服器埠範圍的子集。

此外，您可能還有注意到，在伺服器上針對應用程式共用獨立設定了 8348 個連接埠，但用戶端上的應用程式共用僅獨立設定了 20 個連接埠。 建議您也這麼做，但不是一種很快的規則。 一般說來，您可以將每個可用的埠視為代表單一通訊會話：如果埠範圍中有100埠可供使用，這表示有問題的電腦在任何指定時間內最多可加入100通訊會話。 因為伺服器可能會比用戶端參與更多的交談，所以在伺服器上開啟比用戶端更多的連接埠也很合理。 為應用程式共用在用戶端上獨立設定 20 個連接埠，表示使用者可在特定裝置上同時參與 20 個應用程式共用工作階段。 這對於您絕大多數的使用者而言應該已足夠使用。

若要將先前的埠範圍指派給全域會議設定的集合，您可以使用下列商務用 Skype Server 管理命令介面命令：

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

或是使用此命令將這些相同的連接埠範圍指派給所有會議組態設定：

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

個別使用者必須從商務用 Skype 登出，然後重新登入，這些變更實際會生效。

> [!NOTE]  
> 您也可以啟用用戶端媒體埠範圍，然後使用單一命令指派這些埠範圍。 例如：<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>設定在 Windows 10 上執行之用戶端的服務品質原則

除了指定商務用 Skype 用戶端所使用的埠範圍之外，還必須建立要套用至用戶端電腦的個別服務原則品質。  (針對會議、應用程式及轉送伺服器建立的服務原則的品質不應該套用至用戶端電腦。 ) 此資訊僅適用于執行商務用 Skype 用戶端和 Windows 10 的電腦。

下列範例會使用這組埠範圍來建立音訊原則和影片原則：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>用戶端流量類型</th>
<th>連接埠開始</th>
<th>連接埠範圍</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音訊</p></td>
<td><p>50020</p></td>
<td><p>共</p></td>
</tr>
<tr class="even">
<td><p>影片</p></td>
<td><p>58000</p></td>
<td><p>共</p></td>
</tr>
<tr class="odd">
<td><p>應用程式共用</p></td>
<td><p>42000</p></td>
<td><p>共</p></td>
</tr>
<tr class="even">
<td><p>檔案傳輸</p></td>
<td><p>42020</p></td>
<td><p>共</p></td>
</tr>
</tbody>
</table>

若要為 Windows 10 電腦建立服務品質音訊原則，請先登入已安裝群組原則管理的電腦。 開啟群組原則管理 (按一下 [ **開始**]，指向 [系統 **管理工具**]，然後按一下 [ **群組原則管理**) ]，然後完成下列程式：

1.  在群組原則管理中，找出要用來建立新原則的容器。 例如，如果所有用戶端電腦都位於名為用戶端的 OU 中，則應該在用戶端 OU 中建立新的原則。

2.  以滑鼠右鍵按一下適當的容器，然後按一下 [ **在這個網域中建立 GPO]，並在這裡連結**。

3.  在 [ **新增 GPO** ] 對話方塊的 [ **名稱** ] 方塊中，輸入新群組原則物件的名稱，然後按一下 **[確定]**。

4.  以滑鼠右鍵按一下新建立的原則，然後按一下 [ **編輯**]。

5.  在 [群組原則管理編輯器] 中，展開 [ **電腦** 設定]，展開 [ **Windows 設定**]，以滑鼠右鍵按一下 [ **原則] QoS**，然後按一下 [ **建立新原則**]。

6.  在 [ **原則型 QoS** ] 對話方塊的 [開始] 頁面上，于 [ **名稱** ] 方塊中輸入新原則的名稱。 選取 [指定 DSCP 數值]，並將該值設為 **46**。 將 [指定輸出節流閥速率] 保留未選取狀態，然後按 [下一步]。

7.  在下一個頁面上，選取 [ **僅限具有此可執行檔名稱的應用程式**]，輸入 **Lync.exe** 作為名稱，然後按 **[下一步]**。 此設定指示原則僅優先于商務用 Skype 用戶端的相符流量。

8.  在第三頁上，確定已選取 [ **所有來源 ip 位址** ] 和 [ **任何目的地 ip 位址** ]，然後按 **[下一步]**。 這兩個設定可確保無論是哪部電腦 (IP 位址) 傳送封包，以及哪部電腦 (IP 位址) 接收封包，那些封包都會受到管理。

9.  在第四頁上，從 [選取此 QoS 原則套用的通訊協定] 下拉式清單中選取 [TCP 及 UDP]。 TCP (傳輸控制通訊協定) 和 UDP (使用者資料包通訊協定) 是商務用 Skype Server 及其用戶端應用程式最常使用的兩種網路通訊協定。

10. 在 [標題] 中 **指定來源埠號碼**，選取 [ **從此來源埠或範圍**]。 在隨附的文字方塊中，輸入為音訊傳輸保留的連接埠範圍。 例如，如果您使用埠50020經由埠50039進行音訊流量，請輸入使用此格式的埠範圍： **50020:50039**。 按一下 **[完成]**。

建立音訊的 QoS 原則之後，您應該先建立影片的第二個原則。 若要為視訊建立原則，請遵循您建立音訊原則時所使用的相同基本程序，並替換下列項目：

  - 使用不同的 (和唯一的) 原則名稱。

  - 將 DSCP 值設定為 **34** ，而不是46。  (如先前所述，您不需要使用 DSCP 值 34;您只須指派不同于音訊使用的 DSCP 值。 ) 

  - 使用先前設定的影片流量的埠範圍。 例如，如果您有保留的埠58000到58019以取得影片，請將埠範圍設定為： **58000:58019**。

如果您決定建立原則以管理應用程式共用流量，請進行下列的替代專案：

  - 使用不同的 (和唯一的) 原則名稱 (例如， **商務用 Skype Server 應用程式共用**) 。

  - 將 DSCP 值設定為 **24** ，而不是46。  (此外，此值不必為 24;它只必須不同于音訊和影片所用的 DSCP 值。 ) 

  - 使用先前設定的影片流量的埠範圍。 例如，如果您有保留埠42000到42019以進行應用程式共用，請將埠範圍設定為： **42000:42019**。

對於檔案傳輸原則：

  - 使用不同的 (和唯一的) 原則名稱 (例如， **商務用 Skype Server** 檔案會) 傳輸。

  - 將 DSCP 值設定為 **14**。  (此外，此值不必為 14;它只必須是唯一的 DSCP 代碼。 ) 

  - 針對應用程式使用先前設定的埠範圍。 例如，如果您有保留埠42020到42039以進行應用程式共用，請將埠範圍設定為： **42020:42039**。

在用戶端電腦上重新整理群組原則後，您建立的新原則將不會生效。 雖然群組原則本身會定期重新整理，但您可以在需要重新整理群組原則的每部電腦上執行下列命令，以強制立即重新整理：

    Gpupdate.exe /force

您可以從任何以系統管理員認證執行的命令視窗中執行此命令。 若要以系統管理員憑證執行命令視窗，請按一下 [開始]，以滑鼠右鍵按一下 [命令提示字元]，然後按一下 [以系統管理員身分執行]。

請記住，這些原則應該針對您的用戶端電腦。 它們不應用於執行商務用 Skype 伺服器的伺服器。

為幫助確保網路封包標示適當的 DSCP 值，您也應該要在每部電腦上建立新的登錄項目，請完成下列程序：

1.  按一下 **[開始]**，再按一下 **[執行]**。

2.  在 [ **執行** ] 對話方塊中，輸入 **regedit**，然後按 enter。

3.  在 [登錄編輯程式] 中，展開 [ **HKEY \_ 本機 \_ 電腦**]，展開 [ **系統**]，展開 [ **CurrentControlSet**]，展開 [ **服務**]，然後展開 [ **Tcpip**]。

4.  以滑鼠右鍵按一下 [Tcpip]，指向 [新增]，然後按一下 [索引鍵]。 在建立新的登錄機碼之後，輸入 **QoS**，然後按 enter 重新命名機碼。

5.  以滑鼠右鍵按一下 [QoS]，指向 [新增]，然後按一下 [字串值]。 在建立新的登錄值之後，請輸入 [ **不要使用 NLA**]，然後按 enter 鍵來重新命名值。

6.  按兩下 [ **不要使用 NLA**]。 在 [**編輯字串**] 對話方塊的 [**數值資料**] 方塊中，輸入 **1** ，然後按一下 **[確定]**。

7.  關閉 [登錄編輯程式] 並 eboot 您的電腦。

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>在具有多個網路介面卡的電腦上設定服務品質

如果您的電腦有多個網路介面卡，您可能會在中執行某些問題： DSCP 值顯示為0x00，而不是設定的值。 這通常會發生在可能有一或多個網路介面卡無法存取您的 Active Directory 網域的電腦上 (例如，如果這些配接器是用於私人網路) 。 在此情況下，會針對可以存取網域的配接器標記 DSCP 值，但不會將其標記為無法存取網域的配接器。

如果您想要針對電腦中的所有網路介面卡標記 DSCP 值，包括沒有網域存取權的配接器，您必須在登錄中新增及設定值。 若要完成，請完成下列程式：

1.  按一下 **[開始]**，再按一下 **[執行]**。

2.  在 [ **執行** ] 對話方塊中，輸入 **regedit**，然後按 enter。

3.  在 [登錄編輯程式] 中，展開 [ **HKEY \_ 本機 \_ 電腦**]，展開 [ **系統**]，展開 [ **CurrentControlSet**]，展開 [ **服務**]，然後展開 [ **Tcpip**]。

4.  如果您看不到標示為 **QoS** 的登錄機碼，請以滑鼠右鍵按一下 [ **Tcpip**]，指向 [ **新增**]，然後按一下 [機 **碼**]。 建立新的金鑰之後，輸入 **QoS**，然後按 enter 重新命名機碼。

5.  以滑鼠右鍵按一下 [QoS]，指向 [新增]，然後按一下 [字串值]。 在建立新的登錄值之後，請輸入 [ **不要使用 NLA**]，然後按 enter 鍵來重新命名值。

6.  按兩下 [ **不要使用 NLA**]。 在 [**編輯字串**] 對話方塊的 [**數值資料**] 方塊中，輸入 **1** ，然後按一下 **[確定]**。

建立並設定新的登錄值後，您必須重新開機電腦，變更才會生效。

## <a name="see-also"></a>另請參閱

[在 Windows 10 中建立群組原則物件](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)