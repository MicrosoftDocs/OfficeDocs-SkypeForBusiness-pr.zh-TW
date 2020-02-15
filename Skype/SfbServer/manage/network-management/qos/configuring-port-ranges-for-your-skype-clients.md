---
title: 設定您的用戶端連接埠範圍和服務品質原則
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
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本文說明如何為您的用戶端和 Skype 中的設定服務品質原則設定的連接埠範圍商務伺服器執行 Windows 10 上的用戶端。
ms.openlocfilehash: 95fe768333a01aff165e74eec334f14bf23d69dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045886"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>設定連接埠範圍與 skype for Business Server 用戶端的服務品質原則

本文說明如何為您的用戶端和 Skype 中的設定服務品質原則設定的連接埠範圍商務伺服器執行 Windows 10 上的用戶端。

## <a name="configure-port-ranges"></a>設定連接埠範圍

根據預設，Skype 商務用戶端應用程式可以使用任何之間的連接埠連接埠 1024年與 65535 時參與通訊工作階段;這是因為特定的連接埠範圍不會自動啟用用戶端。 然而為了使用服務品質，您必須將各種流量類型重新分派 (音訊、視訊、媒體、應用程式共用及檔案傳輸) 至一系列的唯一連接埠範圍。 使用 Set-CsConferencingConfiguration Cmdlet 可達成此目的。

> [!NOTE]  
> 使用者無法進行這些變更本身。 連接埠變更只能由系統管理員使用 Set-csconferencingconfiguration 指令程式。


您可以決定哪一個連接埠範圍目前所使用的通訊工作階段執行下列命令，從內 Skype for Business Server 管理命令介面：

    Get-CsConferencingConfiguration

假設安裝 Skype for Business Server 後，已不到您的會議設定進行任何變更，您應該會得到資訊，包含這些屬性值：

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

這是很重要的因為當此屬性設為 False，Skype 商務用戶端會使用任何可用的連接埠之間的通訊埠 1024年與 65535 時參與通訊工作階段;這是不論任何其他連接埠設定 （例如，ClientMediaPort 或 ClientVideoPort），則為 true。 如果您想要限制使用量至指定的連接埠 （且這是您想要執行如果您計劃實作的服務品質的某個項目），您必須先啟用用戶端的媒體連接埠範圍。 可以完成，使用下列 Windows PowerShell 命令：

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
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>影片</p></td>
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


在上述表格中，用戶端連接埠範圍代表針對您的伺服器設定的連接埠範圍的子集。 例如，在伺服器，應用程式共用已設定為使用連接埠 40803 到 49151;在用戶端電腦，應用程式共用設定為使用透過 42019 42000 的連接埠。 太，這是主要是以方便管理工作的 QoS： 不需要用戶端連接埠呈現的部分的伺服器上使用的連接埠。 （例如，用戶端電腦上您可以設定應用程式共用才能使用，請說，連接埠 10000 透過 10019。）不過，建議您讓您的用戶端連接埠範圍伺服器連接埠範圍的子集。

此外，您可能還有注意到，在伺服器上針對應用程式共用獨立設定了 8348 個連接埠，但用戶端上的應用程式共用僅獨立設定了 20 個連接埠。 這，太，建議使用，但不是 hard-and-fast 規則。 一般而言，您可以考慮每個可用的連接埠來代表單一的通訊工作階段： 如果您有 100 連接埠的連接埠範圍，表示問題的電腦可能參與，提供最，100 的通訊工作階段在任何指定時間。 因為伺服器可能會比用戶端參與更多的交談，所以在伺服器上開啟比用戶端更多的連接埠也很合理。 為應用程式共用在用戶端上獨立設定 20 個連接埠，表示使用者可在特定裝置上同時參與 20 個應用程式共用工作階段。 這對於您絕大多數的使用者而言應該已足夠使用。

若要將先前的連接埠範圍指派給您的會議組態設定的全域集合，您可以使用下列 Skype for Business Server 管理命令介面命令：

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

或是使用此命令將這些相同的連接埠範圍指派給所有會議組態設定：

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

個別使用者必須登出商務用 Skype，然後再重新登入才會實際這些變更生效。

> [!NOTE]  
> 您可以也可以讓用戶端的媒體連接埠範圍，並接著指派這些連接埠範圍，使用單一命令。 例如：<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>執行 Windows 10 上的用戶端設定服務品質原則

除了指定供您 Skype 商務用戶端的連接埠範圍，您也必須建立個別的服務品質原則會套用至用戶端電腦。 （建立會議、 應用程式及中繼伺服器的服務品質原則應該不會套用至用戶端電腦。）這項資訊只適用於執行 Skype 商務用戶端和 Windows 10 電腦。

下列範例會使用此組連接埠範圍建立音訊與視訊原則：


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
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>影片</p></td>
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

若要建立 Windows 10 電腦的服務品質音訊原則，請先登入已安裝群組原則管理的電腦。 開啟群組原則管理] （按一下 [**開始]**、 指向 [**系統管理工具**]，然後按一下 [**群組原則管理**），然後完成下列程序：

1.  在群組原則管理中，找出要用來建立新原則的容器。 例如，如果您所有的用戶端電腦位於名為用戶端 OU 中，應該建立新原則在用戶端的 OU 中。

2.  以滑鼠右鍵按一下適當的容器，然後按一下 [**建立此網域中的 GPO 並連結到**。

3.  在 [**新增 GPO** ] 對話方塊中，在 [**名稱**] 方塊中，輸入新的群組原則物件的名稱，然後按一下 **[確定]**。

4.  新建立的原則，以滑鼠右鍵按一下，然後按一下 [**編輯**。

5.  在群組原則管理編輯器 」 中，展開 [**電腦組態**]，依序展開 [ **Windows 設定**，以滑鼠右鍵按一下 [**原則式 QoS**]，，然後按一下 [**建立新原則**。

6.  在 [**原則式 QoS** ] 對話方塊中，在 [開啟] 頁面中，輸入 [**名稱**] 方塊中的新原則的名稱。 選取 [指定 DSCP 數值]****，並將該值設為 **46**。 將 [指定輸出節流閥速率]**** 保留未選取狀態，然後按 [下一步]****。

7.  在 [下一步] 頁面上，選取 [**僅限應用程式具有此可執行檔名稱**、 輸入**Lync.exe**作為名稱，然後再按 [**下一步**。 此設定會指示來只設定優先順序相符從 Skype 商務用戶端流量的原則。

8.  在第三個頁面上，請確定**任何來源 IP 位址**和**任何目的地 IP 位址**已選取，然後按一下 [**下一步**。 這兩個設定可確保無論是哪部電腦 (IP 位址) 傳送封包，以及哪部電腦 (IP 位址) 接收封包，那些封包都會受到管理。

9.  在第四頁上，從 [選取此 QoS 原則套用的通訊協定]**** 下拉式清單中選取 [TCP 及 UDP]****。 （傳輸控制通訊協定） TCP 及 UDP （使用者資料包通訊協定） 是最常使用 Skype 商務伺服器和其用戶端應用程式的兩個網路通訊協定。

10. 在**指定的來源連接埠號碼**標題下，選取 [**從這個來源的連接埠或範圍**。 在隨附的文字方塊中，輸入為音訊傳輸保留的連接埠範圍。 例如，如果您已保留連接埠 50020 透過連接埠 50039 的音訊流量進入使用這種格式的連接埠範圍： **50020:50039**。 按一下 [完成]****。

當您建立音訊 QoS 原則之後您再應該建立影片的第二個原則。 若要為視訊建立原則，請遵循您建立音訊原則時所使用的相同基本程序，並替換下列項目：

  - 使用不同 （且唯一） 的原則名稱。

  - DSCP 值設為**34**而不是 46。 （如先前所述，您不需要使用 DSCP 數值 34; 您只是必須指派不同的 DSCP 值所使用的音訊）。

  - 使用先前所設定的連接埠範圍的視訊流量。 例如，如果您已保留連接埠 58000 透過 58019 視訊，設定連接埠範圍如下： **58000:58019**。

如果您決定建立原則來管理應用程式共用流量，請更改以下設定：

  - 使用不同 （且唯一） 的原則名稱 (例如，**商務用 Skype 商務伺服器應用程式共用**)。

  - 設定的 DSCP 值為**24**而不是 46。 （同樣地，此值沒有設為 24; 它只是必須不同於使用的音訊和視訊的 DSCP 值）。

  - 使用先前所設定的連接埠範圍的視訊流量。 例如，如果您已保留連接埠 42000 透過 42019 應用程式共用，再將連接埠範圍設定為這： **42000:42019**。

檔案傳輸原則：

  - 使用不同 （且唯一） 的原則名稱 (例如， **Skype for Business 伺服器檔案傳輸**)。

  - 設定的 DSCP 值為**14**。 （同樣地，此值沒有設為 14; 它只是必須是唯一的 DSCP 程式碼）。

  - 應用程式中使用先前所設定的連接埠範圍。 例如，如果您已保留連接埠 42020 透過 42039 應用程式共用，再將連接埠範圍設定為這： **42020:42039**。

您已建立的新原則不會生效之前已重新整理您的用戶端電腦上的群組原則。 雖然群組原則本身會定期重新整理，但您可以在需要重新整理群組原則的每部電腦上執行下列命令，以強制立即重新整理：

    Gpupdate.exe /force

可以從系統管理員認證執行任何命令視窗執行此命令。 若要以系統管理員憑證執行命令視窗，請按一下 [開始]****，以滑鼠右鍵按一下 [命令提示字元]****，然後按一下 [以系統管理員身分執行]****。

請記住，這些原則應已設定目標向用戶端電腦。 它們不應該套用到執行 Skype for Business Server 的伺服器。

為幫助確保網路封包標示適當的 DSCP 值，您也應該要在每部電腦上建立新的登錄項目，請完成下列程序：

1.  按一下 [開始]****，然後按一下 [執行]****。

2.  在 [**執行**] 對話方塊中，輸入**regedit**，，然後按 ENTER。

3.  在登錄編輯程式中，依序展開 [ **HKEY\_本機\_機器**、 展開 [**系統**、 [ **CurrentControlSet**、 展開 [**服務**] 及 [ **tcpip]**。

4.  以滑鼠右鍵按一下 [Tcpip]****，指向 [新增]****，然後按一下 [索引鍵]****。 建立新的登錄機碼後，輸入的**QoS**]，並按 ENTER，以重新命名機碼。

5.  以滑鼠右鍵按一下 [QoS]****，指向 [新增]****，然後按一下 [字串值]****。 建立新的登錄值後，輸入**不使用 NLA**，，然後按 ENTER 以數值重新命名。

6.  連按兩下 [**不使用 NLA**。 在 [**編輯字串**] 對話方塊中，在 [**數值資料**] 方塊中，輸入**1** ，然後按一下 [**確定]**。

7.  關閉登錄編輯程式，並 eboot 您的電腦。

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>在具有多個網路介面卡的電腦上設定服務品質

如果您有多個網路介面卡的電腦，您可能會偶爾會在執行其中 DSCP 值顯示為 0x00 的問題，而不是設定的值。 這通常會發生在一或多個網路介面卡不能夠存取您的 Active Directory 網域 （例如，如果這些介面卡用於私人網路） 的電腦上。 在這類的情況下，DSCP 值將會標記為可以存取該網域，但不會標記為無法存取之網域的介面卡的介面卡。

如果您想要在電腦上，包括您的網域，不需要存取的介面卡的所有網路介面卡的標記 DSCP 值必須新增及設定的登錄值。 可以藉由完成下列程序：

1.  按一下 [開始]****，然後按一下 [執行]****。

2.  在 [**執行**] 對話方塊中，輸入**regedit**，，然後按 ENTER。

3.  在登錄編輯程式中，依序展開 [ **HKEY\_本機\_機器**、 展開 [**系統**、 [ **CurrentControlSet**、 展開 [**服務**] 及 [ **tcpip]**。

4.  如果看不到登錄機碼，然後標示**QoS** **Tcpip**上按一下滑鼠右鍵，指向 [**新增**]，然後按一下 [**機碼**。 建立新的金鑰後，輸入的**QoS**]，並按 ENTER，以重新命名機碼。

5.  以滑鼠右鍵按一下 [QoS]****，指向 [新增]****，然後按一下 [字串值]****。 建立新的登錄值後，輸入**不使用 NLA**，，然後按 ENTER 以數值重新命名。

6.  連按兩下 [**不使用 NLA**。 在 [**編輯字串**] 對話方塊中，在 [**數值資料**] 方塊中，輸入**1** ，然後按一下 [**確定]**。

建立及設定新的登錄值之後, 您必須重新啟動電腦，變更才會生效。

## <a name="see-also"></a>另請參閱

[在 Windows 10 中建立群組原則物件](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
