---
title: 使用 Microsoft Teams 的活動報告
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 04/17/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: chenle
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何使用活動報告來查看貴組織中使用者如何使用 Microsoft Teams。
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9c975bf4a3f2253dbc99230f85b48a9ae9cd0d65
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107189"
---
<a name="use-activity-reports-for-microsoft-teams"></a>使用 Microsoft Teams 的活動報告 
========================================

您可以在 Microsoft 365 系統管理中心使用活動報告，查看貴組織的使用者如何使用 Microsoft Teams。 例如，如果有些人尚未使用 Microsoft Teams，他們可能無法瞭解如何開始使用，或瞭解如何使用 Teams 來提高工作效率和共同合作。 組織可以使用活動報告來決定要優先進行訓練和溝通的方面。

## <a name="how-to-view-the-teams-reports-in-the-reports-dashboard"></a>如何在報表儀表板中查看 Teams 報表

1. 在 [Microsoft 365 系統管理中心中](https://portal.office.com/adminportal/home)，選取報告  >  **使用方式**。
 
2. 在使用 **狀況** 頁面上，選擇選取 **報表，然後在****報表清單中的 Microsoft Teams** 下，選擇您想要查看的報告。

## <a name="teams-activity-reports-that-are-available"></a>可用的 Teams 活動報告

目前您可以查看兩個活動報告：

- [Microsoft Teams 使用者活動報告](#microsoft-teams-user-activity-report) 
- [Microsoft Teams 裝置使用方式報告](#microsoft-teams-device-usage-report) 

### <a name="microsoft-teams-user-activity-report"></a>Microsoft Teams 使用者活動報告

Teams 使用者活動報告提供您使用者在 Teams 中執行之最常見活動的視圖。 這包括有多少人在頻道中參與聊天、有多少人透過私人聊天訊息通訊，以及有多少人參與通話或會議。 您可以看見整個組織以及每個使用者的這項資訊。

![系統管理中心中使用者活動報表的螢幕擷取畫面。](media/teams-user-activity-report.png)

#### <a name="interpret-the-microsoft-teams-user-activity-report"></a>解譯 Microsoft Teams 使用者活動報告

您可以查看活動和使用者圖表，以取得 Teams **使用者活動的** 視圖。 

![使用編號圖說說法的使用者活動報表螢幕擷取畫面。](media/teams-user-activity-report-with-callouts.png)

|標注 |說明  |
|--------|-------------|
|**1**   |您可以針對過去 7 天、30 天、90 天或 180 天的趨勢來查看 Teams 使用者活動報告。 不過，如果您按一下報告中的特定時間範圍，表格 (7) 會顯示 30 天內的資料，最多為產生報表的日期 (2) 。 |
|**2**   |每個報表都有產生此報表的日期。 報告通常會反映啟用時間起 24 到 48 小時的延遲。 |
|**3**   |活動 **視圖** 會以活動類型顯示 Microsoft Teams 活動的數量。 活動類型為小組聊天訊息、私人聊天訊息、通話和會議數目。 |
|**4**   |使用者 **視圖** 會以活動類型顯示使用者數目。 活動類型為小組聊天訊息、私人聊天訊息、通話和會議數目。 |
|**5**   |圖表上的 X 軸是特定報表的選取日期範圍。 <ul><li>在 **活動圖表** 上，Y 軸是指定活動的計數。</ul></li> <ul><li>在使用者 **圖表** 上，Y 軸是參與團隊聊天、私人聊天、通話或會議的使用者數目。</ul></li> |
|**6**   |您可以按一下圖例中的專案，來篩選圖表上看到的數列。 例如，在 [**活動** 圖上，按一下或點一下頻道訊息、**聊天** 訊息、通話或 **會議**，以查看每個訊息的相關資訊。 變更此選取範圍不會變更格線表格中的資訊。 |
|**7**   |報告時間範圍為 180 天 (最) 團隊的清單。  活動計數會根據日期選取範圍而有所差異。 <br><br> 若要查看下表的下列資訊，請確定您將欄新增到資料表。 <ul><li>**使用者** 名稱是使用者的電子郵件地址。 您可以顯示實際的電子郵件地址，或將此欄位匿名。</ul></li> <ul><li>**[上次活動日期 (UTC**) 是指使用者最後一次參與 Microsoft Teams 活動的日期。</ul></li> <ul><li>**頻道訊息** 是使用者在指定的時段內，在小組聊天中張貼的唯一訊息數目。</ul></li> <ul><li>**聊天訊息** 是使用者在指定的時段內，在私人聊天中張貼的唯一訊息數目。</ul></li> <ul><li>**通話** 是使用者在指定的時段內參與的通話數。</ul></li> <ul><li>**會議** 是使用者在指定的時段內參與的線上會議數目。</ul></li> <ul><li>其他活動 **是使用者** 進行的其他小組活動數量，其中一些活動包括但不限於：喜歡郵件、應用程式、處理檔案、搜尋、遵循團隊和頻道，以及喜歡它們。</ul></li> <ul><li>**刪除** 代表團隊是否已刪除。 如果小組已被刪除，但報告期間有活動，它會顯示在格線中，已刪除的設定為 true。</ul></li> <ul><li>**刪除日期** 是使用者被刪除的日期。</ul></li> <ul><li>**已指派的產品** 是指派給使用者的產品清單。</ul></li>如果貴組織的政策禁止您檢視可識別使用者資訊的報告，您可以變更所有這些報表的隱私權設定。 Check out the **How do I hide user level details?** section in the [Activity Reports in the Microsoft 365 Admin Center Preview](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**8**   |按一下或點 **一下 [欄** 來新增或移除表格中的欄。 |
|**9**   |按一下或點 **一下 [匯出** 以將報表資料匯出至 Excel .csv 檔案。 這會匯出所有使用者的資料，並可讓您執行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2，000 人，您可以在報表本身的表格內排序和篩選。 如果您有超過 2，000 個使用者，您必須匯出資料，以篩選及排序報表。 

### <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams 裝置使用方式報告

Teams 裝置使用方式報告會提供使用者如何連接到 Teams 的資訊，包括行動裝置 App。 報告可協助瞭解貴組織中哪些裝置很受歡迎，以及有多少使用者正在外工作。

![Teams 裝置使用方式報表的螢幕擷取畫面。](media/teams-device-usage-report.png)

### <a name="interpret-the-microsoft-teams-device-usage-report"></a>解譯 Microsoft Teams 裝置使用方式報告

您可以查看使用者和通訊組圖表，以取得 Teams 裝置 **使用方式** 的視圖。

![Teams 裝置使用方式報表的螢幕擷取畫面，其中有編號的圖說說。](media/teams-device-usage-report-with-callouts.png)

|標注 |說明  |
|--------|-------------|
|**1**   |您可以針對過去 7 天、30 天、90 天或 180 天的趨勢來查看 Teams 裝置報告。 不過，如果您按一下報告中的特定時間範圍，表格 (7) 會顯示 30 天內的資料，最多為產生報表的日期 (2) 。 |
|**2**   |每個報表都有產生此報表的日期。 報告通常會反映啟用時間起 24 到 48 小時的延遲。 |
|**3**   |使用者 **視圖** 會以裝置類型顯示每日使用者數。 |
|**4**   |通訊 **組** 視圖會顯示所選時段內按裝置顯示的使用者數目。  |
|**5**   | <ul><li>在使用者 **圖表** 上，X 軸是報表的選取日期範圍，而 Y 軸是按裝置類型顯示的使用者數目。</ul></li> <ul><li>在 **通訊圖** 上，X 軸會顯示用來連接到 Teams 的不同裝置，而 Y 軸是使用裝置的使用者數目。</ul></li> |
|**6**   |您可以按一下圖例中的專案，來篩選圖表上看到的數列。 例如，在 [通訊組 **圖** 上，按一下或點一下 Windows、Mac、Linux、Web、iOS 或 **Android** ，只查看與每個圖表相關的資訊。      變更此選取範圍不會變更格線表格中的資訊。 |
|**7**   |報告時間範圍為 180 天 (最) 團隊的清單。  活動計數會根據日期選取範圍而有所差異。 <br><br> 若要在表格中查看下列資訊，請確定您將欄新增到資料表。 <ul><li>**使用者** 名稱是使用者的電子郵件地址。 您可以顯示實際的電子郵件地址，或將此欄位匿名。</ul></li> <ul><li>**[上次活動 (UTC)** 是指使用者上次參與 Teams 活動的日期。</ul></li> <ul><li>**刪除** 代表團隊是否已刪除。 如果小組已被刪除，但報告期間有活動，它會顯示在格線中，已刪除的設定為 true。</ul></li><ul><li>**刪除日期** 是使用者被刪除的日期。</ul></li> <ul><li>**如果使用者**  在 Windows 型電腦的 Teams 桌面用戶端中活動，會選取 Windows。</ul></li> <ul><li>**如果使用者在 MacOS** 電腦的 Teams 桌面用戶端中活動，會選取 Mac。</ul></li>  <ul><li>**如果使用者** 在 Linux 電腦的 Teams 桌面用戶端中活動，會選取 Linux。</ul></li>   <ul><li>**如果使用者** 在 Teams Web 用戶端上使用中，則已選取 Web。</ul></li> <ul><li>**如果使用者在 iOS** 版 Teams 行動用戶端上使用中，會選取 iOS。</ul></li> <ul><li>**如果使用者使用**  Android 版 Teams 行動用戶端，系統即會選取 Android 手機。</ul></li></li> <ui>If your organization's policies prevents you from viewing reports where user information is identifiable, you can change the privacy setting for all these reports. Check out the **How do I hide user level details?** section in the [Activity Reports in the Microsoft 365 Admin Center Preview](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263).</ui> |
|**8**   |按一下或點 **一下 [欄** 來新增或移除表格中的欄。 |
|**9**   |按一下或點 **一下 [匯出** 以將報表資料匯出至 Excel .csv 檔案。 這會匯出所有使用者的資料，並可讓您執行簡單的排序和篩選，以便進一步分析。 如果您的使用者少於 2，000 人，您可以在報表本身的表格內排序和篩選。 如果您有超過 2，000 個使用者，您必須匯出資料，以篩選及排序報表。 

## <a name="who-can-access-the-teams-activity-reports"></a>誰可以存取 Teams 活動報告

指派的使用者可以存取活動報告：

- 全域系統管理員角色
- Exchange、商務用 Skype 或 SharePoint (產品特定的系統管理員角色) 
- 報表讀取者角色

### <a name="reports-reader-role"></a>報表讀取者角色

您可以將報表讀者角色指派給沒有系統管理員許可權，但負責推動 Teams 採用或追蹤授權使用方式的人。 若要瞭解如何指派角色，請參閱指派系統管理員和非系統管理員角色給使用者 [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。

## <a name="other-information-on-the-reports-dashboard"></a>報表儀表板上的其他資訊

### <a name="at-a-glance-activity-widget"></a>快速流覽活動小工具

報告儀表板包含 Teams 在快速流覽活動小工具中的使用方式資料，讓您瞭解使用者在 Microsoft 365 或 Office 365 中使用其他各種服務通訊和共同作業的方式。

![Teams 快速流覽活動小工具的螢幕擷取畫面。](media/at-a-glance-activity-widget.png)

### <a name="teams-activity-card"></a>Teams 活動卡片

報表儀表板上的 Teams 活動卡片可概觀 Teams 中的活動，包括使用中使用者的數量，以便快速瞭解有多少使用者使用服務。 按一下儀表板上的活動卡片，即可將您帶至 Teams 使用者活動報告。 

![Teams 活動卡片的螢幕擷取畫面。](media/teams-activity-card.png)