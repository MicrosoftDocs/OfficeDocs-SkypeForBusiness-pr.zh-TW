---
title: 使用 Shifts 連接器精靈將 Shifts 連接到 Blue Yonder Workforce Management
author: lanachin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何使用 Shifts 連接器精靈，將 Teams 中的班次與 Blue Yonder Workforce Management整合。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: de511df118e1c5e6d62e0bed8cd076a7481b3407
ms.sourcegitcommit: 90f03a841f8ca33092dce65c543357c7c2f7b82a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/06/2022
ms.locfileid: "66647804"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-blue-yonder-workforce-management"></a>使用 Shifts 連接器精靈將 Shifts 連接到 Blue Yonder Workforce Management

## <a name="overview"></a>概觀

Microsoft 365 系統管理中心中的 Shifts 連接器精靈可讓您將 Microsoft Teams 中的 Shifts 應用程式與您的員工管理 (WFM) 系統整合。 設定連線之後，第一線工作人員就可以從班次中順暢地在您的WFM系統中檢視和管理他們的排程。

精靈會設定 Shifts 連接器、建立WFM系統的連線，並套用您選擇的同步設定和小組對應。 同步設定會決定WFM系統和 Shifts 之間同步的排程資訊。 團隊對應定義您在 Teams 中WFM實例和團隊之間的同步處理關聯。 您可以對應至現有的團隊和新的團隊。

您可以設定多個連線，每個連線都有不同的同步設定。 例如，如果貴組織有多個位置的排程需求不同，請建立每個位置的唯一同步處理設定連線。 請記住，WFM實例在任何指定時間只能對應至一個小組。 如果WFM實例已對應至團隊，則無法對應至其他團隊。

使用WFM系統做為記錄系統，第一線工作人員就可以在他們的裝置上查看及調班、管理其顯示狀態，以及要求休假。 前線主管可以繼續使用您的WFM系統來設定排程。

## <a name="integrate-shifts-with-blue-yonder-workforce-management"></a>將 Shifts 與 Blue Yonder Workforce Management整合

目前精靈支援 [適用于 Blue Yonder 的 Microsoft Teams Shifts 連接器](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder)。 此連接器可讓您將 Shifts 與 Blue Yonder Workforce Management (Blue Yonder 整合WFM) 來管理您的排程並保持在最新狀態。 在本文中，我們會逐步引導您執行精靈，以透過連接器設定與 Blue Yonder WFM的連線。

> [!NOTE]
> 您也可以使用 PowerShell 將 Shifts 與 Blue Yonder WFM整合。 若要深入瞭解，請參閱[使用 PowerShell 將 Shifts 連線至 Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)。

## <a name="before-you-begin"></a>開始之前

您必須是 Microsoft 365 全域系統管理員，才能執行精靈。

### <a name="prerequisites"></a>必要條件
<a name="prerequisites"> </a>
[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

- 您要對應的團隊沒有任何排程。 如果團隊有現有的排程，請在將 Blue Yonder WFM實例對應到[該團隊之前，先將排程從團隊中移除](#remove-schedules-from-teams-you-want-to-map)。 否則，您會看到重複的班次。

## <a name="remove-schedules-from-teams-you-want-to-map"></a>從您要對應的團隊中移除排程
<a name="remove_schedules"> </a>

> [!NOTE]
> 如果您要將 Blue Yonder WFM實例對應到具有排程的現有團隊，請完成此步驟。 如果您要對應到沒有任何排程的團隊，或是要建立要對應的新團隊，您可以略過此步驟。

使用 PowerShell 移除團隊中的排程。

1. 首先，您需要安裝 PowerShell 模組並進行設定。 依照步驟 [來設定您的環境](shifts-connector-powershell-manage.md#set-up-your-environment)。
1. 執行下列命令：

    ```powershell
    Remove-CsTeamsShiftsScheduleRecord -TeamId <Teams team ID> -DateRangeStartDate <start time> -DateRangeEndDate <end time> -ClearSchedulingGroup:$false -EntityType <the scenario entities that you want to remove, the format is @(scenario1, scenario2, ...)> -DesignatedActorId <Teams team owner ID>
    ```

    若要取得參數的 `EntityType` 案例清單，請執行 [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector)。 將會移除您指定的日期和時間範圍的排程資料。

若要深入瞭解，請參閱 [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord)。

## <a name="run-the-wizard"></a>執行精靈

### <a name="get-started"></a>開始使用

1. 在Microsoft 365 系統管理中心的左側導 [覽](https://admin.microsoft.com/)中，選擇 **[設定]**，然後移至 [**應用程式與電子郵件**] 區段。
1. 選取 **[連線您的員工管理系統]**。 在這裡，您可以進一步瞭解將 Shifts 連接器與第一線員工和主管在將 Shifts 連線到WFM系統時的體驗。
    :::image type="content" source="../../media/shifts-connector-wizard-get-started.png" alt-text="Microsoft 365 系統管理中心中 Shifts 連接器精靈詳細資料頁面的螢幕擷取畫面。" lightbox="../../media/shifts-connector-wizard-get-started.png":::
1. 當您準備好時，選取 **[開始使用]**。
1. 選取 **[下一步**] 以建立 Blue Yonder WFM連線。

### <a name="enter-connection-details"></a>輸入連線詳細資料
<a name="connection_details"> </a>

1. 在 [連線詳細資料] 頁面上，為您的連線命名唯一名稱。 長度不能超過 128 個字元或具有任何特殊字元。
    :::image type="content" source="../../media/shifts-connector-wizard-connection-details.png" alt-text="顯示連線設定的精靈 [連線詳細資料] 頁面的螢幕擷取畫面。" lightbox="../../media/shifts-connector-wizard-connection-details.png":::
1. 輸入您的 Blue Yonder WFM服務帳戶名稱、密碼和服務 URL。
1. 完成後，選取 [ **下一步** ] 以測試與您所輸入設定的連線。

### <a name="choose-sync-settings"></a>選擇同步設定
<a name="sync"> </a>

在 [同步設定] 頁面上，選擇要從 Blue Yonder WFM同步處理至 Shifts 的資訊、同步處理頻率，以及 Shifts 使用者是否可以變更資料。

1. 輸入您的 Microsoft 365 系統帳戶。
    :::image type="content" source="../../media/shifts-connector-wizard-sync-settings.png" alt-text="精靈 [同步設定] 頁面的螢幕擷取畫面，顯示同步處理設定。" lightbox="../../media/shifts-connector-wizard-sync-settings.png":::
<a name="email"> </a>
1. 在 **[電子郵件通知收件者**] 底下，選擇接收此連線之電子郵件通知的人員。 您可以新增個別使用者和群組。 電子郵件通知包含連線設定狀態的相關資訊，以及連線設定後可能發生的任何問題或錯誤。
1. 選擇您的同步設定：
    1. 在 [**排程和班次**] 底下，選擇 [Blue Yonder] WFM Shifts 使用者可以看到或變更的資料，然後設定同步頻率。
    2. 在 [ **要求**] 底下，選擇 Shifts 使用者可以看到並建立的要求類型。

    > [!IMPORTANT]
    > 如果您選擇下列任一選項來停用開啟班、開啟班次要求、調班要求或休假要求，則需要執行另一個步驟來隱藏 Shifts 中的功能。
    >
    > - 開啟班次：**班次使用者不會看到 Blue Yonder WFM資料**
    > - 交換要求： **所有使用者的功能已停用**
    > - 休假要求： **已停用所有使用者的功能**
    >
    > After you run the wizard, make sure you follow the steps in the [Disable open shifts, open shifts requests, swap requests, and time off requests](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) section later in this article.
 
1. 當您完成選擇設定時，請選取 [ **建立連線]**。

### <a name="map-blue-yonder-workforce-management-instances-to-teams"></a>將 Blue Yonder Workforce Management實例對應至團隊
<a name="sites"> </a>

選擇您要連線到 Shifts 的 Blue Yonder WFM實例，然後將每個實例對應到 Teams 中的團隊。 您最多可以對應 100 個實例。 有兩種方法可以執行此動作：

- [手動將實例對應到團隊](#manually-map-instances-to-teams)
- [準備及上傳定義對應的 CSV 檔案](#use-a-csv-file-to-map-instances-to-teams)

#### <a name="manually-map-instances-to-teams"></a>手動將實例對應到團隊

選取您要對應的實例。

:::image type="content" source="../../media/shifts-connector-wizard-sites.png" alt-text="精靈的螢幕擷取畫面，顯示 Blue Yonder WFM實例清單。" lightbox="../../media/shifts-connector-wizard-sites.png":::
<a name="mapping"></a> 
 <a name="search_teams"></a>然後，將每個實例對應到 Teams 中的團隊。 您可以將實例對應到現有的團隊，也可以建立新的團隊。
:::image type="content" source="../../media/shifts-connector-wizard-search-team.png" alt-text="顯示搜尋小組選項並建立新團隊選項之窗格的螢幕擷取畫面。" lightbox="../../media/shifts-connector-wizard-search-team.png":::

##### <a name="to-map-an-instance-to-an-existing-team"></a>將實例對應至現有團隊

1. 選取實例名稱。
2. 在窗格中搜尋團隊，然後選取該團隊。 請記住，已對應到此連線實例的團隊不會顯示在搜尋中。
3. 選擇時區和最近的城市。
4. 選 **取 [儲存**]，然後選取 [ **下一步]**。

##### <a name="to-map-an-instance-to-a-new-team"></a>將實例對應至新團隊

1. 選取實例名稱。
2. 在窗格中，選擇 **[建立新團隊]**。 您將會移至瀏覽器中的新索引標籤，您可以在其中建立新的小組Microsoft 365 系統管理中心。
    1. 輸入團隊的名稱和選擇性描述。
    1. 新增一或多個團隊擁有者。 請務必將 Microsoft 365 系統帳戶新增為擁有者。
    1. 新增小組成員。
    1. 新增小組電子郵件地址並選擇隱私權設定。
    1. 檢閱您的設定，然後選擇 [ **新增團隊]**。 建立小組時，選擇 **[關閉]**。
3. 返回到精靈，搜尋，然後選取您建立的新團隊。
4. 選擇時區和最近的城市。
5. 選 **取 [儲存**]，然後選取 [ **下一步]**。

#### <a name="use-a-csv-file-to-map-instances-to-teams"></a>使用 CSV 檔案將實例對應至團隊

1. 選 **取切換為大量模式**。
1. 選 **取下載範本檔案** 以下載您可用來定義對應的對應範本。

    :::image type="content" source="../../media/shifts-connector-wizard-mapping-file.png" alt-text="精靈 [上傳對應檔案] 頁面的螢幕擷取畫面。" lightbox="../../media/shifts-connector-wizard-mapping-file.png":::

1. 使用範本建立對應檔案。 從第一欄開始，它會依下列順序包含這些欄。 星號 (*) 表示必要資料行。

    |欄名稱  |描述  |
    |---------|---------|
    |**Blue Yonder 實例識別碼*** |Blue Yonder WFM實例識別碼。|
    |**Blue Yonder 實例名稱**|Blue Yonder WFM實例名稱。|
    |**小組識別碼*** |團隊識別碼。|
    |**團隊名稱**|團隊名稱。|
    |**時區*** |以 tz 資料庫格式顯示的時區。 例如，歐洲/倫敦。|

    > [!NOTE]
    > 您只需要填寫所需的欄， (Blue Yonder 實例識別碼、小組識別碼、時區) 以將實例對應至團隊。

    以下是對應檔案外觀的範例。

    |Blue Yonder 實例識別碼|Blue Yonder 實例名稱|小組識別碼|團隊名稱|時區|
    |---------|---------|---------|---------|---------|
    |2111|Contoso US 小組|3a4d78a-2261|美國團隊|美國/Los_Angeles|
    |3212|Contoso 英國團隊|2d1f6c2e-5272|英國隊|歐洲/倫敦|
    |4865||bfa6o89e-1328||美國/多倫多|

1. 當您建立對應檔案時，請選取 **[流覽** ] 上傳檔案。 精靈會驗證您的檔案。 如果發現錯誤，您會看到錯誤清單，以及要求您修正錯誤的訊息。 否則，您會看到繼續下一個步驟的訊息。  
1. 選取 **[下一步]**。

### <a name="review-and-finish"></a>檢閱並完成

檢閱您的設定。 如果您需要變更任何團隊對應，請選擇 **[編輯** ] 進行變更。 當您準備好時，選取 [ **完成]**。

:::image type="content" source="../../media/shifts-connector-wizard-review.png" alt-text="精靈 [校閱] 頁面顯示對應的螢幕擷取畫面。" lightbox="../../media/shifts-connector-wizard-review.png":::

您會看到一則訊息，確認我們已收到您的要求以及作業識別碼。 記下作業識別碼。 您需要它來檢查連線的設定狀態。

:::image type="content" source="../../media/shifts-connector-wizard-operation-id.png" alt-text="顯示確認訊息和作業識別碼的精靈頁面螢幕擷取畫面。" lightbox="../../media/shifts-connector-wizard-operation-id.png":::

精靈會啟動設定連線的程式，並將實例對應到您選取的團隊。 此程式可能需要一些時間來完成。 您選擇的收件者將會收到有關設定狀態的電子郵件通知。

選 **取 [完成]** 以結束精靈。

您已在途中，但尚未完成！ 請務必檢查您的電子郵件。 您會收到確認訊息，表示我們已收到您的要求，以及如何檢查設定狀態的 [連結](shifts-connector-powershell-manage.md#check-connection-setup-status) 。

> [!NOTE]
> 如果連線設定完成後發生問題或錯誤，您會收到電子郵件通知。 請依照電子郵件中的指示進行問題的疑難排解。

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>停用開啟班、開啟班次要求、調班要求和休假要求

> [!IMPORTANT]
> 只有當您在精靈中選擇下列任一選項來停用開啟班、開啟班次要求、調班要求或休假要求時，請遵循下列步驟。 完成此步驟會隱藏 Shifts 中的功能。
>
> - 開啟班次：**班次使用者不會看到 Blue Yonder WFM資料**
> - 交換要求： **所有使用者的功能已停用**
> - 休假要求： **已停用所有使用者的功能**
>
> 如果沒有此第二個步驟，使用者仍會在 Shifts 中看到此功能，如果他們嘗試使用該功能，則會收到「不支援的作業」錯誤訊息。

若要在 Shifts 中隱藏開啟的班次、調班要求和休假要求，請使用圖形 API[排程資源類型](/graph/api/resources/schedule)，為您對應到 ```false``` Blue Yonder WFM實例的每個小組設定下列參數：

- 開啟班次： ```openShiftsEnabled```
- 調換要求：  ```swapShiftsRequestsEnabled```
- 休假要求： ```timeOffRequestsEnabled```

若要在班次中隱藏開啟的班次要求，請移至 [班次中的 **設定** ]，然後關閉 [ **開啟班次** ] 設定。

## <a name="if-you-need-to-make-changes-to-a-connection"></a>如果您需要變更連線
<a name="update_connection"> </a>

連線設定完成後，您可以使用 PowerShell 對它進行變更。 例如，您可以更新同步設定、小組對應，以及停用連線的同步處理。 如需逐步指引，請參閱[使用 PowerShell 管理您的 Blue Yonder Workforce Management班次連線](shifts-connector-powershell-manage.md)。

## <a name="related-articles"></a>相關文章

- [Shifts 連接器](shifts-connectors.md)
- [使用 PowerShell 管理您與 Blue Yonder Workforce Management的 Shifts 連線](shifts-connector-powershell-manage.md)
- [在 Teams 中管理 Shifts 應用程式](manage-the-shifts-app-for-your-organization-in-teams.md)
