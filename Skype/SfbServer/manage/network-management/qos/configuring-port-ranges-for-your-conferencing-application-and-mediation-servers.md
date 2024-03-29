---
title: 針對會議、應用程式及轉送伺服器設定埠範圍和服務品質原則
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 本文說明如何針對會議、應用程式及轉送伺服器設定埠範圍和服務品質原則。
ms.openlocfilehash: ea7e150824ff3816c99a26bb92c165e9b237b5fe
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62410756"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a>針對會議、應用程式及轉送伺服器設定埠範圍和服務品質原則

本文說明如何針對會議、應用程式及轉送伺服器設定埠範圍和服務品質原則。

## <a name="configure-port-ranges"></a>設定埠範圍

若要執行服務品質，您應該針對會議、應用程式及轉送伺服器上的音訊、影片和應用程式共用，設定相同的埠範圍。此外，這些埠範圍不得以任何方式重疊。 舉個簡單的例子，假設您針對會議伺服器上的視訊使用連接埠 10000 到 10999。 這表示您也必須為應用程式和中繼伺服器上的視訊保留連接埠 10000 到 10999。 如果沒有，服務品質 (QoS) 將無法如預期般運作。

同樣地，假設您為視訊保留連接埠 10000 到 10999，但接著為音訊保留連接埠 10500 到 11999。 這樣會造成服務品質的問題，因為連接埠範圍重疊。 在 QoS 中，每個模態都必須有一組獨特的埠：如果您使用埠10000到10999以進行影片，則必須使用不同的範圍 (（例如11000到11999，針對音訊) ）。

依預設，音訊和視訊連接埠範圍不會在商務用 Skype Server 中重疊; 不過，指派給應用程式共用的埠範圍與音訊和影片埠範圍重疊。  (它會反過來表示這些範圍都不是唯一的。 ) 您可以從商務用 Skype Server 管理命令介面中執行下列三個命令，以驗證會議、應用程式及轉送伺服器的現有埠範圍。

  Get-CsService-ConferencingServer |Select-Object 身分識別、AudioPortStart、AudioPortCount、VideoPortStart、VideoPortCount、AppSharingPortStart AppSharingPortCount
    
  Get-CsService-ApplicationServer |Select-Object 身分識別、AudioPortStart、AudioPortCount
    
  Get-CsService-MediationServer |Select-Object 身分識別、AudioPortStart、AudioPortCount

> [!WARNING]  
> 如同您在上述命令中所見，每一種連接埠類型 (音訊、視訊和應用程式共用) 都會被指派兩個不同的屬性值：連接埠起點和連接埠計數。 連接埠起點指出用於該形式的第一個連接埠；例如，如果音訊連接埠起點等於 50000，表示用於音訊流量的第一個連接埠是連接埠 50000。 如果音訊埠計數為 2 (不是有效值，但在這裡是用來做說明，請) ，這表示只有兩個埠為音訊所指派。 如果第一個連接埠是連接埠 50000，且總共有兩個連接埠，表示第二個連接埠一定是連接埠 50001 (連接埠範圍必須是連續的)。 因此，音訊的連接埠範圍將會是連接埠 50000 到 50001 (含)。<BR><br>另請注意，應用程式伺服器和中繼伺服器只支援音訊的服務品質；您不需要在應用程式伺服器或中繼伺服器中變更視訊或應用程式共用連接埠。

如果您執行上述三個命令，您會看到商務用 Skype Server 的預設埠值設定如下：

<table>
<colgroup>
</colgroup>
<thead>
<tr class="header">
<th>屬性</th>
<th>會議伺服器</th>
<th>應用程式伺服器</th>
<th>中繼伺服器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AudioPortStart</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
</tr>
<tr class="even">
<td><p>AudioPortCount</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>VideoPortStart</p></td>
<td><p>57501</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>VideoPortCount</p></td>
<td><p>8034</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationSharingPortStart</p></td>
<td><p>49152</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>ApplicationSharingPortCount</p></td>
<td><p>16383</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>

如先前所述，設定 QoS 的商務用 Skype Server 埠時，應確定在您的會議、應用程式和轉送伺服器上，： 1) 音訊埠設定都相同; 2) 埠範圍不會重疊。 如果您仔細查看前面的表格，您會看到埠範圍在三個伺服器類型中皆相同。 例如，在每個伺服器類型上，啟動音訊埠設定為埠49152，而在每個伺服器上為音訊保留的埠總數也相同：8348。 不過，埠範圍會重迭：音訊埠會從埠49152開始，但也會為應用程式共用設定埠。 為了讓服務品質獲得最佳的使用，應將應用程式共用重新設定為使用唯一的埠範圍。 例如，您可以將應用程式共用設定為從埠40803開始，並使用8348埠。  (為何8348埠？ 如果您將這些值一起新增--40803 + 8348--這表示應用程式共用將使用埠40803透過埠49150。 因為音訊埠不會開始，直到埠49152，您就不會再有任何重疊的埠範圍。 ) 

選取應用程式共用的新埠範圍後，您可以使用 Set-CsConferencingServer Cmdlet 進行變更。 您不需要在應用程式伺服器或中繼伺服器上進行這項變更，因為這些伺服器不會處理應用程式共用流量。 如果您決定要重新指派用於音效流量的連接埠，只要在這些伺服器上變更連接埠值即可。

若要在單一會議服務器上修改應用程式共用的埠值，請從商務用 Skype Server 管理命令介面中執行類似以下的命令：

  **Set-CsConferenceServer-Identity ConferencingServer： atl-cs-001.litwareinc.com-AppSharingPortStart 40803-AppSharingPortCount 8348**

如果您想要在所有會議服務器上進行這些變更，可以改為執行下列命令：

  **Get-CsService-ConferencingServer |ForEach-Object {Set-CsConferenceServer-Identity $ _。Identity-AppSharingPortStart 40803-AppSharingPortCount 8348}**

變更埠設定之後，您應該停止並重新啟動每個變更所影響的服務。

您的會議伺服器、應用程式伺服器和中繼伺服器並不是一定要共用完全相同的連接埠範圍；唯一必要的需求是您要在所有的伺服器上預留唯一的連接埠範圍。不過，如果您在所有伺服器上使用同一組連接埠，通常會讓管理工作更為輕鬆。

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a>在商務用 Skype Server 中為會議、應用程式及轉送伺服器設定服務品質原則

設定埠範圍可確保指定類型的所有流量 (，以協助使用服務品質。例如，所有音訊流量) 一組相同的埠。 這可讓系統輕鬆識別及標記指定的封包：如果為音訊流量保留埠49152，則透過埠49152的任何封包都會以 DSCP 代碼標示，表示這是音訊封包。 反過來，這可讓路由器將封包識別為音訊封包，並提供比未標記的封包更高的優先順序 (例如，用來將檔案從一部伺服器複製到另一個) 的封包。

不過，只要將一組埠限制在特定類型的流量中，就不會導致透過以適當 DSCP 代碼標示的埠傳送傳輸。 除了定義埠範圍之外，您還必須建立服務原則的品質，指定要與每個埠範圍相關聯的 DSCP 碼。 若為商務用 Skype Server，通常表示建立兩個原則：一個用於音訊，另一個用於影片。

使用群組原則，可很輕鬆地建立及管理服務品質原則。 您也可以使用本機安全性原則建立這些相同原則 (。 不過，您必須在每個電腦和每一部電腦上重複相同的程式。 ) 您的初始 QoS 原則集合 (一個用於音訊，另一個用於影片) 只應該套用至商務用 Skype Server 執行會議服務器、應用程式伺服器及/或轉送伺服器服務的電腦。 如果所有這些電腦都位於相同的 Active Directory OU 中，您可以只指派新的群組原則物件 (GPO) 給該 OU。 或者，您也可以執行其他步驟，將新的原則設定為指定的電腦;例如，您可以將適當的電腦放在安全性群組中，然後使用群組原則安全性篩選，將 GPO 只套用到該安全性群組。

若要建立服務品質原則以管理音訊，請登入已安裝群組原則管理的電腦。 開啟群組原則管理 (按一下 [ **開始**]，指向 [系統 **管理工具**]，然後按一下 [ **群組原則管理** ]) 然後完成下列程式：

1.  在群組原則管理中，找出要用來建立新原則的容器。 例如，如果您的所有商務用 Skype Server 電腦都位於名為商務用 Skype Server 的 OU 中，則應該在商務用 Skype Server OU 中建立新的原則。

2.  以滑鼠右鍵按一下適當的容器，然後按一下 [ **在這個網域中建立 GPO]，並在這裡連結**。

3.  在 [**新增 GPO** ] 對話方塊的 [**名稱**] 方塊中，輸入新群組原則物件的名稱 (例如，**商務用 Skype Server QoS**) ]，然後按一下 **[確定]**。

4.  以滑鼠右鍵按一下新建立的原則，然後按一下 [ **編輯**]。

5.  在 [群組原則管理編輯器] 中，依序展開 [**電腦** 設定] 及 [**原則**]，展開 **Windows 設定**，以滑鼠右鍵按一下 **原則 QoS**]，然後按一下 [**建立新原則**]。

6.  在 [**原則型 QoS** ] 對話方塊的 [開始] 頁面上，于 [**名稱**] 方塊中輸入新原則的名稱 (例如，**商務用 Skype Server QoS**) 。 選取 [指定 DSCP 數值]，並將該值設為 **46**。 將 [指定輸出節流閥速率] 保留未選取狀態，然後按 [下一步]。

7.  在下一個頁面上，確定已選取 [ **所有應用程式** ]，然後按 **[下一步]**。 這只是確保所有應用程式會與指定的 DSCP 碼從指定的埠範圍中的封包相符。

8.  在第三頁上，確定已選取 [ **所有來源 ip 位址] 和 [任何目的地 ip 位址** ]，然後按 **[下一步]**。 這兩個設定可確保無論是哪部電腦 (IP 位址) 傳送封包，以及哪部電腦 (IP 位址) 接收封包，那些封包都會受到管理。

9.  在第四頁上，從 [選取此 QoS 原則套用的通訊協定] 下拉式清單中選取 [TCP 及 UDP]。 TCP (傳輸控制通訊協定) 和 UDP (使用者資料包通訊協定) 是商務用 Skype Server 及其用戶端應用程式最常使用的兩種網路通訊協定。

10. 在 [標題] 中 **指定來源埠號碼**，選取 [ **從此來源埠或範圍**]。 在隨附的文字方塊中，輸入為音訊傳輸保留的連接埠範圍。 例如，如果您將埠49152設定為音訊流量的埠57500，請輸入使用此格式的埠範圍： **49152:57500**。 按一下 **[完成]**。

> [!NOTE]  
> 46的 DSCP 值有點隨意：雖然 DSCP 46 通常是用來標示音訊封包，但您不需要使用 DSCP 46 進行音訊通訊。 如果您已執行 QoS，而且您使用的是不同的 DSCP 碼來進行音訊 (例如，DSCP 40) ，則應該設定您的服務品質原則，以使用相同的程式碼 (例如，40的音訊) 。 如果您現在只是實施服務品質，建議您將 DSCP 46 用於音訊，只是因為此值通常是用來標示音訊封包。

在您建立音訊流量的 QoS 原則之後，您應該先為影片流量建立第二個原則 (並選擇性地，第三個用於管理應用程式共用流量) 的原則。 若要為視訊建立原則，請遵循您建立音訊原則時所使用的相同基本程序，並替換下列項目：

  - 使用不同的 (和唯一的) 原則名稱 (例如 **商務用 Skype Server 影片**) 。

  - 將 DSCP 值設為 **34** 而不是 46。(請注意，DSCP 值不一定要使用 34。唯一的要求是用於視訊和音訊的 DSCP 值必須不同。)

  - 使用先前設定的影片流量的埠範圍。 例如，如果您有保留的埠57501到65535以取得影片，請將埠範圍設定為： **57501:65535**。

如果您決定建立用來管理應用程式共用流量的原則，則必須建立第三個原則，以進行下列替代：

  - 使用不同的 (和唯一的) 原則名稱 (例如，**商務用 Skype Server 應用程式共用**) 。

  - 將 DSCP 值設為 **24** 而不是 46。(再強調一次，DSCP 值不一定要使用 24。唯一的要求是用於應用程式共用的 DSCP 值必須與視訊或音訊不同。)

  - 使用先前設定的影片流量的埠範圍。 例如，如果您有保留埠40803到49151以進行應用程式共用，請將埠範圍設定為： **40803:49151**。

在您的商務用 Skype Server 電腦上重新整理群組原則之前，您建立的新原則將不會生效。 雖然群組原則本身會定期重新整理，但您可以在需要重新整理群組原則的每部電腦上執行下列命令，以強制立即重新整理：

  **Gpupdate.exe/force**

您可以從商務用 Skype Server 管理命令介面或任何執行系統管理員認證的命令視窗中執行此命令。 若要以系統管理員憑證執行命令視窗，請按一下 [開始]，以滑鼠右鍵按一下 [命令提示字元]，然後按一下 [以系統管理員身分執行]。

若要確認已套用新的 QoS 原則，請執行下列操作：

1.  在商務用 Skype Server 電腦上，按一下 [**開始**]，然後按一下 [**執行**]。

2.  在 [ **執行** ] 對話方塊中，輸入 **regedit**，然後按 enter。

3.  在 [登錄編輯程式] 中，依序展開 [**電腦**]、[ **HKEY \_ 本機 \_ 電腦**]、[**軟體**]、[**原則**] 和 [ **Microsoft**]，展開 **Windows**，然後按一下 [ **QoS**]。 在 [ **QoS** 您應該會看到您剛才建立之每個 QoS 原則的登錄機碼。 例如，如果您建立兩個新的原則 (一個名為商務用 Skype Server 音訊 QoS 和另一個名為商務用 Skype Server 的影片 QoS) ，您應該會看到商務用 Skype Server 音訊 QoS 和商務用 Skype Server 視頻 QoS 的登錄專案。

為幫助確保網路封包標示適當的 DSCP 值，您也應該要在每部電腦上建立新的登錄項目，請完成下列程序：

1.  按一下 **[開始]**，再按一下 **[執行]**。

2.  在 [ **執行** ] 對話方塊中，輸入 **regedit**，然後按 enter。

3.  在 [登錄編輯程式] 中，展開 [ **HKEY \_ 本機 \_ 電腦**]，展開 [ **系統**]，展開 [ **CurrentControlSet**]，展開 [ **服務**]，然後展開 [ **Tcpip**]。

4.  以滑鼠右鍵按一下 [Tcpip]，指向 [新增]，然後按一下 [索引鍵]。 在建立新的登錄機碼之後，輸入 **QoS**，然後按 enter 重新命名機碼。

5.  以滑鼠右鍵按一下 [QoS]，指向 [新增]，然後按一下 [字串值]。 在建立新的登錄值之後，請輸入 [ **不要使用 NLA**]，然後按 enter 鍵來重新命名值。

6.  按兩下 [ **不要使用 NLA**]。 在 [**編輯字串**] 對話方塊的 [**數值資料**] 方塊中，輸入 **1** ，然後按一下 **[確定]**。

7.  關閉 [登錄編輯程式]，然後重新開機電腦。
