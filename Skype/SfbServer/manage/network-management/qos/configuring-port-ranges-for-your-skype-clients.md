---
title: 為用戶端設定埠範圍和服務品質原則
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本文說明如何為您的用戶端設定埠範圍, 以及如何在執行 Windows 10 之用戶端的商務用 Skype Server 中設定品質原則。
ms.openlocfilehash: 4d7999634864e222dd627ea3b46a3a3da5c67fe5
ms.sourcegitcommit: 67282b5f2f1aac3e675c4a485f4846deba15deb4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/24/2019
ms.locfileid: "36194120"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>在商務用 Skype Server 中針對用戶端設定埠範圍和服務品質原則

本文說明如何為您的用戶端設定埠範圍, 以及如何在執行 Windows 10 之用戶端的商務用 Skype Server 中設定品質原則。

## <a name="configure-port-ranges"></a>設定埠範圍

根據預設, 商務用 Skype 用戶端應用程式在通訊會話中參與時, 可以使用埠1024和65535之間的任何埠;這是因為不會針對用戶端自動啟用特定的埠範圍。 不過, 若要使用服務品質, 您需要將各種類型的流量 (音訊、影片、媒體、應用程式共用及檔案傳輸) 重新指派到一系列的唯一端口範圍。 您可以使用 CsConferencingConfiguration Cmdlet 來完成這項工作。

> [!NOTE]  
> 最終使用者無法自行進行這些變更。 只有系統管理員才能使用 CsConferencingConfiguration Cmdlet 進行埠變更。


您可以從商務用 Skype Server Management 命令介面中執行下列命令, 以判斷通訊會話目前使用的是哪個埠範圍:

    Get-CsConferencingConfiguration

假設您在安裝商務用 Skype Server 之後, 您還沒有對會議設定進行任何變更, 您應該會返回包含這些屬性值的資訊:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

如果您仔細查看上述輸出, 您會看到兩個重要事項。 首先, ClientMediaPortRangeEnabled 屬性會設定為 False:

    ClientMediaPortRangeEnabled : False

這很重要, 因為當這個屬性設定為 False 時, 商務用 Skype 用戶端會在通訊會話中涉及埠1024和65535之間的任何可用埠;無論任何其他的埠設定 (例如, ClientMediaPort 或 ClientVideoPort), 都是如此。 如果您想要將使用量限制在指定的一組埠 (如果您打算執行服務品質, 這是您想要執行的動作), 則必須先啟用用戶端媒體埠範圍。 可以使用下列 Windows PowerShell 命令完成:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

上述命令可讓用戶端媒體埠範圍用於全域集合會議設定。不過, 這些設定也可以套用至網站範圍和/或服務範圍 (僅適用于會議服務器服務)。 若要啟用特定網站或伺服器的用戶端媒體埠範圍, 請在呼叫 Set-CsConferencingConfiguration 時指定該網站或伺服器的身分識別:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

或者, 您也可以使用此命令同時啟用所有會議設定的埠範圍:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

您會注意到的第二個重要事項是, 樣本輸出顯示針對每種類型的網路流量所設定的媒體埠範圍是完全相同的:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

為了實現 QoS, 這些埠範圍中的每一個都必須是唯一的。 例如, 您可以設定埠範圍, 如下所示:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>用戶端流量類型</th>
<th>埠開始</th>
<th>埠範圍</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音訊</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>顯示器</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>應用程式共用</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>檔案傳輸</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>


在前一個表格中, 用戶端埠範圍代表伺服器設定的埠範圍的子集。 例如, 在伺服器上, 應用程式共用已設定為使用埠40803到 49151;在用戶端電腦上, 應用程式共用設定為使用埠42000到42019。 如此一來, 主要是為了更輕鬆地管理 QoS: 用戶端埠不需要代表在伺服器上使用的埠子集。 (例如, 您可以在用戶端電腦上設定要使用的應用程式共用, 比如說埠10000到10019。)不過, 建議您將用戶端埠範圍設為伺服器埠範圍的子集。

此外, 您可能已經注意到8348埠已針對伺服器上的應用程式共用而設定, 但用戶端上的應用程式共用只留有20個埠。 我們也建議您這麼做, 但不是很難且快速的規則。 一般來說, 您可以考慮每個可用的埠代表單一通訊會話: 如果您的埠範圍中有100埠, 這表示有問題的電腦在任何特定時間都可以參與到100通訊會話。 因為伺服器可能會參與許多用戶端的交談, 所以在伺服器上開啟的埠數會比用戶端多。 為用戶端上的應用程式共用設定20個埠, 意味著使用者可以同時在指定的裝置上參與20個應用程式共用會話。 這對於絕大多數使用者而言, 都應該有足夠的證明。

若要將先前的埠範圍指派給您的全域會議設定設定, 您可以使用下列商務用 Skype Server Management Shell 命令:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

或者, 您可以使用這個命令, 為所有的會議設定指派相同的埠範圍:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

個別使用者必須從商務用 Skype 登出, 然後重新登入, 這些變更才會生效。

> [!NOTE]  
> 您也可以使用單一命令來啟用用戶端媒體埠範圍, 然後指派這些埠範圍。 例如：<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>設定在 Windows 10 上執行之用戶端的服務品質原則

除了指定要供商務用 Skype 用戶端使用的埠範圍之外, 您還必須建立會套用至用戶端電腦的個別服務品質。 (針對會議、應用程式和中繼伺服器所建立的服務品質原則, 不應該套用到用戶端電腦。)此資訊僅適用于執行商務用 Skype 用戶端和 Windows 10 的電腦。

下列範例使用這組埠範圍來建立音訊原則和影片原則:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>用戶端流量類型</th>
<th>埠開始</th>
<th>埠範圍</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音訊</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>顯示器</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>應用程式共用</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>檔案傳輸</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>

若要建立適用于 Windows 10 電腦的服務品質音訊原則, 請先登入已安裝群組原則管理的電腦。 開啟 [群組原則管理] (按一下 [**開始**], 指向 [系統**管理工具**], 然後按一下 [**群組原則管理**]), 然後完成下列程式:

1.  在 [群組原則管理] 中, 找出要建立新原則的容器。 例如, 如果所有用戶端電腦都位於一個名為「用戶端」的 OU 中, 則應該在用戶端 OU 中建立新的原則。

2.  以滑鼠右鍵按一下適當的容器, 然後按一下 [**在這個網域建立 GPO], 然後在這裡連結**。

3.  在 [**新增 GPO** ] 對話方塊的 [**名稱**] 方塊中, 輸入新群組原則物件的名稱, 然後按一下 **[確定]**。

4.  以滑鼠右鍵按一下新建立的原則, 然後按一下 [**編輯**]。

5.  在 [群組原則管理編輯器] 中, 展開 [**電腦**設定], 展開 [ **Windows 設定**], 以滑鼠右鍵按一下 [**原則式 QoS**], 然後按一下 [**建立新策略**]。

6.  在 [**原則式 QoS** ] 對話方塊的 [開始] 頁面上, 于 [**名稱**] 方塊中輸入新原則的名稱。 選取 [**指定 DSCP 值**], 然後將值設定為**46**。 [離開]**指定輸出限制率**未選取, 然後按 **[下一步]**。

7.  在下一頁上, 選取 [**僅限具有此可執行檔名稱的應用程式**], 輸入**Lync**作為名稱, 然後按 **[下一步]**。 這個設定會指示原則只會將商務用 Skype 用戶端的通訊順序設成優先順序。

8.  在第三個頁面上, 確認已選取 [**所有來源 ip 位址**] 和 [**任何目的地 ip 位址**], 然後按一下 **[下一步]**。 這兩項設定可確保無論哪些電腦 (IP 位址) 傳送這些資料包, 以及哪些電腦 (IP 位址) 會接收那些資料包, 都會管理資料包。

9.  在第4頁, 從 [**選取此 QoS 原則適用**于] 下拉式清單中選取 [ **TCP 和 UDP** ]。 TCP (傳輸控制通訊協定) 和 UDP (使用者資料包通訊協定) 是商務用 Skype Server 及其用戶端應用程式最常用的兩種網路通訊協定。

10. 在 [標題] 底下,**指定來源埠號**, 選取 [**從此來源埠或範圍**]。 在隨附的文字方塊中, 輸入為音訊廣播保留的埠範圍。 例如, 如果您是透過埠50039將埠50020預留給音訊流量, 請輸入使用此格式的埠範圍: **50020:50039**。 按一下 **[完成]**。

在您建立音訊的 QoS 原則之後, 您應該先建立影片的第二個原則。 若要建立影片的原則, 請遵循您在建立音訊原則時所遵循的基本程式, 進行這些替換:

  - 使用不同 (且唯一的) 原則名稱。

  - 將 DSCP 值設為**34** , 而不是46。 (如前所述, 您不需要使用 DSCP 值 34; 您只需指派不同于音訊所用的 DSCP 值即可)。

  - 使用先前設定的影片流量埠範圍。 例如, 如果您已將埠58000到58019的備用, 請將埠範圍設定為: **58000:58019**。

如果您決定建立用來管理應用程式共用流量的原則, 請進行下列替換:

  - 使用不同 (且唯一的) 原則名稱 (例如,**商務用 Skype Server 應用程式共用**)。

  - 將 DSCP 值設為**24** , 而不是46。 (同樣地, 此值不一定必須是 24; 它必須與用於音訊和影片的 DSCP 值不同)。

  - 使用先前設定的影片流量埠範圍。 例如, 如果您已在應用程式共用中保留埠42000到 42019, 請將埠範圍設定為: **42000:42019**。

針對檔案傳輸原則:

  - 使用不同 (且唯一的) 原則名稱 (例如,**商務用 Skype Server 檔案傳輸**)。

  - 將 DSCP 值設為**14**。 (同樣地, 這個值不一定是 14; 它必須是唯一的 DSCP 代碼。)

  - 使用先前設定的應用程式埠範圍。 例如, 如果您已在應用程式共用中保留埠42020到 42039, 請將埠範圍設定為: **42020:42039**。

您所建立的新原則必須在用戶端電腦上重新整理群組原則後才會生效。 雖然群組原則會定期自行進行重新整理, 但是您可以在需要重新整理群組原則的每一台電腦上執行下列命令, 以強制立即重新整理:

    Gpupdate.exe /force

這個命令可以從任何執行在「管理員認證」的命令視窗中執行。 若要在 [管理員認證] 下執行命令視窗, 請按一下 [**開始**], 以滑鼠右鍵按一下**命令提示**字元, 然後按一下 [**以系統管理員身分執行**]

請記住, 這些原則應該針對用戶端電腦進行設定。 它們不應該套用到執行商務用 Skype Server 的伺服器。

若要協助確保網路資料包是以適當的 DSCP 值標示, 您也應該透過完成下列程式, 在每個電腦上建立新的登錄專案:

1.  按一下 [**開始**], 然後按一下 [**執行**]。

2.  在 [**執行**] 對話方塊中, 輸入**regedit**, 然後按 enter。

3.  在 [登錄編輯程式] 中, 展開 [ **HKEY\_本機\_電腦**], 展開 [**系統**]、[ **CurrentControlSet**]、[**服務**], 然後再展開 [ **Tcpip**]。

4.  以滑鼠右鍵按一下 [ **Tcpip**], 指向 [**新增**], 然後按一下 [**金鑰**]。 建立新的登錄金鑰之後, 請輸入**QoS**, 然後按 enter 來重新命名金鑰。

5.  以滑鼠右鍵按一下 [ **QoS**], 指向 [**新增**], 然後按一下 [**字串值**]。 建立新的登錄值之後, 請輸入 [**不使用 NLA**], 然後按 enter 鍵來重新命名值。

6.  按兩下 [**不使用 NLA**]。 在 [**編輯字串**] 對話方塊中, 于 [**值資料**] 方塊中輸入**1** , 然後按一下 **[確定]**。

7.  關閉 [登錄編輯程式], 然後 eboot 您的電腦。

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>在有多個網路介面卡的電腦上設定服務品質

如果您的電腦有多個網路介面卡, 您可能偶爾會遇到 DSCP 值顯示為 0x00 (而不是設定的值) 的問題。 這通常會發生在電腦上一或多個網路介面卡無法存取您的 Active Directory 網域 (例如, 如果是針對私人網路使用這些配接器)。 在這種情況下, 會將 DSCP 值標記為可存取網域的配接器, 但不會針對無法存取網域的配接器標記。

如果您想要為電腦中的所有網路介面卡標示 DSCP 值, 包括沒有您網域存取權的配接器, 您必須在註冊表中新增並設定值。 完成下列程式, 即可完成作業:

1.  按一下 [**開始**], 然後按一下 [**執行**]。

2.  在 [**執行**] 對話方塊中, 輸入**regedit**, 然後按 enter。

3.  在 [登錄編輯程式] 中, 展開 [ **HKEY\_本機\_電腦**], 展開 [**系統**]、[ **CurrentControlSet**]、[**服務**], 然後再展開 [ **Tcpip**]。

4.  如果您沒有看到標示為 [ **QoS** ] 的登錄機碼, 請以滑鼠右鍵按一下 [ **Tcpip**], 指向 [**新增**], 然後按一下 [**金鑰**]。 建立新的金鑰之後, 請輸入**QoS**, 然後按 enter 來重新命名金鑰。

5.  以滑鼠右鍵按一下 [ **QoS**], 指向 [**新增**], 然後按一下 [**字串值**]。 建立新的登錄值之後, 請輸入 [**不使用 NLA**], 然後按 enter 鍵來重新命名值。

6.  按兩下 [**不使用 NLA**]。 在 [**編輯字串**] 對話方塊中, 于 [**值資料**] 方塊中輸入**1** , 然後按一下 **[確定]**。

建立並設定新的登錄值之後, 您必須重新開機電腦, 變更才會生效。

## <a name="see-also"></a>另請參閱

[在 Windows 10 中建立群組原則物件](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
