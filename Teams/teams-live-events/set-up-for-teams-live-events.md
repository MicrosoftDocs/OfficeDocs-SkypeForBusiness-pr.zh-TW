---
title: 在 Microsoft 團隊中設定即時事件
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 瞭解在小組中設定即時事件的步驟, 包括準備網路、指派授權、使用原則來啟用即時事件功能及排程使用者, 以及設定協力廠商的發佈提供者。
f1keywords: ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
ms.openlocfilehash: e82506a78f907192a43eaf08d5d7d47841ebc1a4
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2019
ms.locfileid: "36184746"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>在 Microsoft 團隊中設定即時事件

當您設定即時事件時, 必須採取幾個步驟。

## <a name="step-1-set-up-your-network-for-live-events-in-teams"></a>步驟 1: 在團隊中設定即時事件的網路
在團隊中產生的即時事件需要您[準備貴組織的小組網路](https://docs.microsoft.com/microsoftteams/prepare-network)。  

## <a name="step-2-get-and-assign-licenses"></a>步驟 2: 取得並指派授權
請確定您有[誰可以建立和排程即時事件](plan-for-teams-live-events.md#who-can-create-and-schedule-live-events), 以及[誰可以觀看即時事件](plan-for-teams-live-events.md#who-can-watch-live-events)的授權指派正確。

## <a name="step-3-set-up-live-events-policies"></a>步驟 3: 設定即時事件原則
即時事件原則是用來控制貴組織中的哪些人員可以保留即時事件, 以及他們所建立之事件中提供的功能。 您可以使用 [預設原則] 或 [建立一或多個自訂即時事件] 原則。 建立自訂原則之後, 請將它指派給貴組織中的使用者或使用者群組。

> [!NOTE]
> 除非您建立並指派自訂原則, 否則貴組織中的使用者將會取得全域原則。 根據預設, [全域原則] 會針對團隊使用者啟用即時事件排程, 並關閉 [即時標題] 與 [字幕] (會議), 組織中的每個人都可以加入即時事件, 而 [錄製] 設定則設定為 [永遠錄製]。 

### <a name="create-or-edit-a-live-events-policy"></a>建立或編輯即時事件原則
<a name="bkcreatepolicy"> </a>

**![使用 Microsoft [團隊管理中心] 顯示](../media/teams-logo-30x30.png) Microsoft 團隊標誌的圖示**

1. 在左側導覽中, 移至 [**會議** > **即時事件] 原則**。 
2. 請執行下列其中一項操作:
- 如果您想要編輯現有的預設原則, 請選擇 [**全域] ([組織內的預設值])**。 
- 如果您想要建立新的自訂原則, 請選擇 [**新增原則**]。 
- 如果您想要編輯自訂原則, 請選取該原則, 然後選擇 [Edit] (**編輯**)。 

    您可以變更這些設定, 以符合貴組織的需求。

    ![即時事件原則設定的螢幕擷取畫面](../media/teams-live-events-policies.png "Microsoft 團隊系統管理中心中 [即時事件] 原則設定的螢幕擷取畫面") 

|正在  |說明  |
|---------|---------|
|**名稱**     |這是出現在 [即時事件原則] 頁面上的原則名稱。 它不能超過64個字元或包含任何特殊字元。          |
|**說明**    |使用此操作來新增原則的易記描述。         |
|**允許排程**     |開啟此功能可讓貴組織中的使用者在團隊中建立及排程即時事件。 請務必注意, 如果您希望使用者排程由外部 app 或裝置產生的即時事件, 您必須執行其他步驟。 若要深入瞭解, 請參閱[讓使用者排程由外部 app 或裝置產生的事件](#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)。     |
|**允許會議出席者** |此設定僅適用于小組中產生的事件。 開啟此功能可讓即時活動出席者在事件期間查看動態標題和字幕。         |
|**誰可以加入排程的即時事件**    |選擇下列其中一項。<br><br>**所有人**使用者可以建立即時事件, 包括所有人, 包括貴組織外部的人員, 都可以出席。 此設定會在使用者排程即時事件時, 在小組中啟用 [**公用**] 許可權類型。<br> **組織中的所有人**使用者可以建立您組織中的人員 (包括新增至貴組織的[來賓使用者](../add-guests.md)) 可以出席的即時事件。 使用者無法建立匿名使用者所參與的即時事件。 此設定會在使用者排程即時事件時, 在小組中啟用**組織內**的許可權類型。<br> **特定使用者或群組**使用者可以建立只有貴組織中的特定使用者或群組可以出席的即時事件。 使用者無法建立由組織中的所有人或匿名使用者所參與的即時事件。 此設定可讓使用者在排程即時事件時, 在小組中啟用 [**人員與群組**] 許可權類型。       |
|**錄製設定**  <br>     | 此設定僅適用于小組中產生的事件。 選擇下列其中一項。 <br><br> **永遠錄製**使用者建立的即時事件永遠會進行錄製。 事件結束之後, 活動小組成員可以下載錄製, 而出席者可以觀看事件。 <br> **永不錄製**使用者建立的即時事件永遠不會被記錄。 <br>**召集人可以記錄或不錄製**使用者可以決定是否要錄製即時事件。 如果記錄在事件結束之後, 活動小組成員可以下載錄製, 而出席者可以觀看事件。      

您也可以使用 Windows PowerShell 來執行此動作。 如需詳細資訊, 請參閱[使用 PowerShell 在團隊中設定即時事件原則](set-teams-live-events-policies-using-powershell.md)。 

### <a name="assign-a-live-events-policy-to-users"></a>指派即時事件原則給使用者 

如果您已建立自訂即時事件原則, 請將它指派給使用者, 讓原則成為作用中。 

![顯示 Microsoft [小組標誌] 的圖示](../media/teams-logo-30x30.png) 使用 Microsoft 團隊系統管理中心

1. 在左側導覽中, 移至 [**使用者**], 然後選取使用者。
2. 在 [**指派的原則**] 旁, 選擇 [**編輯**]。 
3. 選取您要指派的即時事件原則, 然後選擇 [**儲存**]。 

您也可以將即時事件原則指派給一或多個使用者, 如下所示:

![顯示 Microsoft [小組標誌] 的圖示](../media/teams-logo-30x30.png) 使用 Microsoft 團隊系統管理中心

1. 移至 [**會議** > **即時事件] 原則**。
2. 按一下原則名稱左方, 選取原則。
3. 選取 [**管理使用者**]。
4. 在 [**管理使用者**] 窗格中, 依 [顯示名稱] 或 [使用者名稱] 搜尋使用者, 選取名稱, 然後選取 [**新增**]。 針對您要新增的每個使用者重複此步驟。
5. 完成新增使用者後, 請選取 [**儲存**]。
 

### <a name="enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device"></a>讓使用者能夠排程由外部 app 或裝置產生的事件

若要讓使用者排程由外部 app 或裝置產生的事件, 您也必須執行下列動作:

1. 針對貴組織中的使用者啟用 Microsoft Stream。 資料流程是以合格的 Office 365 訂閱或獨立服務的形式提供。 [商務基本版] 或 [商務版 Premium 方案] 中不包含資料流程。 如需詳細資訊, 請參閱[資料流程授權概覽](https://docs.microsoft.com/stream/license-overview)。

      深入瞭解如何[在 Office 365 中指派授權給使用者](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC), 讓使用者可以存取資料流程。 請確定您在[本文](https://docs.microsoft.com/stream/disable-user-organization)中定義的使用者未封鎖資料流程。

2. 確保使用者在資料流程中擁有即時事件建立許可權。 根據預設, 系統管理員可以使用外部 app 或裝置建立事件。 資料流程管理員可以[讓其他使用者在資料流程中建立即時事件](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating)。  

3. 確保即時事件召集人已同意資料流程管理員設定的公司原則。如果串流管理員已[設定公司指導原則](https://docs.microsoft.com/stream/company-policy-and-consent), 並要求員工在儲存內容之前接受此原則, 則使用者必須先進行, 然後才能在小組中建立即時事件 (在外部 app 或裝置上)。 在您推出組織中的 [即時事件] 功能之前, 請先確認將建立這些即時事件的使用者有權使用該原則。 

## <a name="step-4-set-up-a-video-distribution-solution-for-live-events-in-teams"></a>步驟 4: 在團隊中設定即時事件的視頻發佈方案
即時事件影片的播放使用彈性高位元速率資料流程 (ABR), 但它是單播資料流程, 這表示每個檢視器都會從網際網路取得自己的影片資料流程。 如果您的組織中有大量的即時事件或影片, 可能會有查看者佔用大量的網際網路頻寬。 針對想要減少即時事件之網際網路流量的組織而言, 即時事件解決方案是與 Microsoft 的受信任的影片傳送合作夥伴, 提供軟體定義的網路 (SDNs) 或企業內容傳遞網路 (eCDNs)。 這些 SDN/eCDN 平臺可讓組織在不犧牲最終使用者觀賞體驗的情況下, 優化網路頻寬。 我們的合作夥伴可以協助您在整個商業網路中更具伸縮性且更有效率的視頻發佈。

**在團隊外購買及設定您的解決方案**您可以利用 Microsoft 的信任的影片傳遞合作夥伴, 透過調整視頻傳送來取得專家說明。 您必須先購買並將 SDN/eCDN 方案放在外, 並獨立于團隊, 才能啟用要與團隊搭配使用的影片傳遞提供者。

下列 SDN/eCDN 解決方案是預先整合的, 可設定為搭配資料流程使用。

- **Hive 流式處理**可為即時和點播的企業影片發佈提供簡單且功能強大的方案。 Hive 是一種軟體式解決方案, 不需要額外的硬體或頻寬, 而且提供安全的方式來啟用成千上萬同時進行的視頻檢視器, 而不會影響您的網路。 針對想要在購買 SDN/eCDN 方案之前, 想要瞭解其網路上的影響影片的客戶, Hive 資料流程也會為 Microsoft 客戶提供以瀏覽器為基礎的分析方案。 [深入瞭解](https://www.hivestreaming.com/partners/integration-partners/microsoft/)。
 
- **Kollective**是一個以雲端為基礎的智慧對等發佈平臺, 可利用您現有的網路基礎結構, 以多種形式 (即時資料流影片、點播影片、軟體更新、安全性修補程式等等) 來傳送內容。更快速地以較低的頻寬可靠地進行。 我們的安全平臺受世界上最大的金融機構信任, 而且沒有額外的硬體、設定和維護很簡單。 [深入瞭解](http://www.kollective.com)。
 
- **斜坡 OmniCache**提供新一代網路發佈, 並確保跨全球 wan 順暢地傳送影片內容, 協助事件發生器優化網路頻寬, 並支援成功的即時事件廣播和隨選傳遞. 我們即將推出在小組中產生的即時事件支援的快速衝刺 OmniCache。 [深入瞭解](http://www.ramp.com)。 
 
> [!NOTE] 
> 您所選擇的 SDN 或 eCDN 方案受限於所選的**協力廠商提供者服務條款與隱私權原則**, 這將會控制提供者的解決方案的使用。 您使用的是提供者的解決方案, 不會受到 Microsoft 大量授權條款或線上服務條款的制約。 如果您不同意**協力廠商提供者的條款**, 請不要在小組中啟用此方案。 

在您設定 SDN 或 eCDN 方案之後, 您就可以為團隊中的即時事件設定提供者。 

## <a name="next-steps"></a>後續步驟
移至 [[設定團隊中的即時事件] 設定](configure-teams-live-events.md)。

### <a name="related-topics"></a>相關主題
- [什麼是團隊即時活動？](what-are-teams-live-events.md)
- [規劃團隊即時事件](plan-for-teams-live-events.md)
- [在團隊中設定即時事件設定](configure-teams-live-events.md)

