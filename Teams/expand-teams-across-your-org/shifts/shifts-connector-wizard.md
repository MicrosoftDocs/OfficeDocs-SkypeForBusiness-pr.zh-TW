---
title: 使用 Shifts 連接器精靈將 Shifts 連接到 Blue Yonder 員工管理
author: lanachin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何使用 Shifts 連接器精靈，將 Shifts Teams與 Blue Yonder 員工管理整合。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4041b0909a3c5e8f1aa256fd2ec662030548343c
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593646"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-blue-yonder-workforce-management"></a>使用 Shifts 連接器精靈將 Shifts 連接到 Blue Yonder 員工管理

## <a name="overview"></a>概觀

此應用程式中的 Shifts 連接器精靈Microsoft 365 系統管理中心將 Shifts 應用程式整合到 Microsoft Teams 中與您的員工管理 (WFM) 系統。 設定連接之後，前線工作人員可以在 Shifts 中順暢地在 WFM 系統中查看及管理排程。

精靈會設定 Shifts 連接器、建立與 WFM 系統的連接，並適用您選擇的同步設定和小組映射。 同步設定會決定在 WFM 系統與 Shifts 之間同步的排程資訊。 團隊地圖會定義您的 WFM 網站與團隊之間的同步處理Teams。 您可以與現有的團隊和新團隊進行地圖。

您可以設定多個連接，每個連接使用不同的同步處理設定。 例如，如果貴組織有多個具有不同排程需求的位置，請為每個位置建立具有唯一同步處理設定的連接。 請記住，WFM 網站在任一時間只能對應到一個小組。 如果 WFM 網站已經對應到團隊，它無法對應到另一個團隊。

以您的 WFM 系統做為記錄系統，前線員工可以在他們的裝置上查看和調班、管理其可用性，以及要求在 Shifts 中休息。 前線管理員可以繼續使用您的 WFM 系統來設定排程。

## <a name="integrate-shifts-with-blue-yonder-workforce-management"></a>將班次與 Blue Yonder 員工管理整合

目前，精靈支援 Blue [Yonder Microsoft Teams Shifts 連接器](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder)。 此連接器可讓您將 Shifts 與 Blue Yonder 員工管理 (Blue Yonder WFM) 整合，以管理您的排程，並保持其最新狀態。 本文將介紹如何執行精靈，以透過連接器設定與 Blue Yonder WFM 的關聯。

> [!NOTE]
> 您也可以使用 PowerShell 將 Shifts 與 Blue Yonder WFM 整合。 若要深入瞭解，請參閱 [使用 PowerShell 將 Shifts 連接到 Blue Yonder 員工管理](shifts-connector-blue-yonder-powershell-setup.md)。

## <a name="before-you-begin"></a>開始之前

您必須是全域Microsoft 365才能執行精靈。

### <a name="prerequisites"></a>必要條件
<a name="prerequisites"> </a>
[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

- 您想要地圖的團隊沒有任何排程。 如果團隊有現有的排程，請[](#remove-schedules-from-teams-you-want-to-map)移除團隊的排程，然後再將藍色 Yonder WFM 網站與它進行連結。 否則，您會看到重複的班次。

## <a name="remove-schedules-from-teams-you-want-to-map"></a>從您想要地圖的團隊移除排程
<a name="remove_schedules"> </a>

> [!NOTE]
> 如果您要將 Blue Yonder WFM 網站與有排程的現有團隊進行比對，請完成此步驟。 如果您要與沒有任何排程的小組進行繪圖，或是要建立要地圖的新團隊，您可以略過此步驟。

使用 PowerShell 從團隊移除排程。

1. 首先，您需要安裝 PowerShell 模組並加以設定。 請遵循 [步驟來設定您的環境](shifts-connector-powershell-manage.md#set-up-your-environment)。
1. 執行下列命令：

    ```powershell
    Remove-CsTeamsShiftsScheduleRecord -TeamId <Teams team ID> -DateRangeStartDate <start time> -DateRangeEndDate <end time> -ClearSchedulingGroup:$false -EntityType <the scenario entities that you want to remove, the format is @(scenario1, scenario2, ...)> -DesignatedActorId <Teams team owner ID>
    ```

    若要取得參數的 `EntityType` 情境清單，請執行 [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps)。 系統將會針對您指定的日期和時間範圍移除排程資料。

若要深入瞭解，請參閱 [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps)。

## <a name="run-the-wizard"></a>執行精靈

### <a name="get-started"></a>開始使用

1. 在左側流覽 [Microsoft 365 系統管理中心，選擇](https://admin.microsoft.com/)**設定，** 然後前往應用程式 **與電子郵件** 區段。
1. 選取 **連線您的員工管理系統**。 在這裡，您可以深入瞭解 Shifts 連接器，以及當您將 Shifts 連接到 WFM 系統時，前線員工和主管的體驗。
    :::image type="content" source="../../media/shifts-connector-wizard-get-started.png" alt-text="畫面中 Shifts 連接器精靈詳細資料頁面的螢幕擷取畫面Microsoft 365 系統管理中心。" lightbox="../../media/shifts-connector-wizard-get-started.png":::
1. 當您準備好時，**請選取 開始**。
1. 選取 **下** 一步以建立藍色 Yonder WFM 連接。

### <a name="enter-connection-details"></a>輸入連接詳細資料
<a name="connection_details"> </a>

1. 在連接詳細資料頁面上，為連接指定唯一的名稱。 不能超過 128 個字元，或具有任何特殊字元。
    :::image type="content" source="../../media/shifts-connector-wizard-connection-details.png" alt-text="精靈中顯示連接設定之連接詳細資料頁面的螢幕擷取畫面。" lightbox="../../media/shifts-connector-wizard-connection-details.png":::
1. 輸入您的 Blue Yonder WFM 服務帳戶名稱、密碼和服務 URL。
1. 完成後，請 **選取下一** 步，以測試您輸入的設定與連接。

### <a name="choose-sync-settings"></a>選擇同步設定
<a name="sync"> </a>

在同步處理設定頁面上，您可以選擇從 Blue Yonder WFM 同步處理至 Shifts 的資訊、同步頻率，以及 Shifts 使用者是否可以變更資料。

1. 輸入您的Microsoft 365帳戶。
    :::image type="content" source="../../media/shifts-connector-wizard-sync-settings.png" alt-text="精靈的同步設定頁面螢幕擷取畫面，顯示同步設定。" lightbox="../../media/shifts-connector-wizard-sync-settings.png":::
<a name="email"> </a>
1. 在 **電子郵件通知收件者下**，選擇接收此連結電子郵件通知的收件者。 您可以新增個別的使用者和群組。 電子郵件通知包含有關連接設定狀態的資訊，以及設定連接後可能會發生的任何問題或錯誤。
1. 選擇您的同步設定：
    1. 在 **排程和班次** 下，選擇 Shifts 使用者可以查看或變更的藍色 Yonder WFM 資料，然後設定同步處理頻率。
    2. 在 **要求下**，選擇 Shifts 使用者可以查看及建立的要求類型。

    > [!IMPORTANT]
    > 如果您選擇下列任一選項來停用開啟的班、開啟班要求、調班要求或請假要求，您需要執行另一個步驟來隱藏 Shifts 中的功能。
    >
    > - 開啟班次： **班次使用者不會看到藍色 Yonder WFM 資料**
    > - 調換要求 **：所有使用者的功能已停用**
    > - 請假要求： **所有使用者都停用此功能**
    >
    > 執行精靈之後，請確定您遵循本文稍後的停用開啟班[](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests)、開啟班要求、調班要求和請假要求一節中的步驟。
 
1. 完成選擇設定後，請選取建立 **連接**。

### <a name="map-blue-yonder-workforce-management-sites-to-teams"></a>將藍色 Yonder 員工管理網站與團隊進行地圖
<a name="sites"> </a>

選擇您想要連結至 Shifts 的藍色 Yonder WFM 網站。 您最多可以選取 100 個網站。

:::image type="content" source="../../media/shifts-connector-wizard-sites.png" alt-text="精靈的螢幕擷取畫面，顯示藍色 Yonder WFM 網站清單。" lightbox="../../media/shifts-connector-wizard-sites.png":::
<a name="mapping"></a> 
 <a name="search_teams"></a>然後，將您選取的每個 Blue Yonder WFM 網站，與 Teams。 您可以將網站與現有的小組進行連結，也可以建立新團隊。
:::image type="content" source="../../media/shifts-connector-wizard-search-team.png" alt-text="顯示搜尋小組選項並建立新團隊選項之窗格的螢幕擷取畫面。" lightbox="../../media/shifts-connector-wizard-search-team.png":::
#### <a name="to-map-a-site-to-an-existing-team"></a>將網站與現有的小組進行連結

1. 選取網站名稱。
2. 在窗格中搜尋團隊，然後選取它。 請記住，已對應到此連結網站的團隊不會顯示在搜尋中。
3. 選擇時區和最近的城市。
4. 選取 **儲存**，然後選取下 **一步**。

#### <a name="to-map-a-site-to-a-new-team"></a>將網站與新小組進行連結

1. 選取網站名稱。
2. 在窗格中，選擇建立 **新團隊**。 系統將會將您帶至瀏覽器中的新選項卡，您可以在其中建立新Microsoft 365 系統管理中心。
    1. 輸入團隊的名稱和選擇性描述。
    1. 新增一或多個團隊擁有者。 請確定您將系統帳戶Microsoft 365為擁有者。
    1. 新增小組成員。
    1. 新增小組電子郵件地址並選擇隱私權設定。
    1. 檢查您的設定，然後選擇新增 **團隊**。 建立團隊時，**選擇關閉。**
3. 返回精靈，搜尋，然後選取您建立的新團隊。
4. 選擇時區和最近的城市。
5. 選取 **儲存**，然後選取下 **一步**。

### <a name="review-and-finish"></a>審查並完成

檢查您的設定。 如果您需要變更任何小組的映射， **請選擇編輯以** 執行此操作。 當您準備好時， **請選取完成**。

:::image type="content" source="../../media/shifts-connector-wizard-review.png" alt-text="精靈的檢查頁面螢幕擷取畫面，顯示地圖。" lightbox="../../media/shifts-connector-wizard-review.png":::

您會看到一則訊息，確認我們已收到您的要求，以及作業識別碼。 記下作業識別碼。 您需要它來檢查您的連接設定狀態。

:::image type="content" source="../../media/shifts-connector-wizard-operation-id.png" alt-text="精靈頁面的螢幕擷取畫面，顯示確認訊息和作業識別碼。" lightbox="../../media/shifts-connector-wizard-operation-id.png":::

精靈會啟動程式來設定連接，並將網站與所選團隊進行連結。 此程式可能需要一些時間才能完成。 您選取的收件者會收到有關設定狀態的電子郵件通知。

選取 **完成** 以離開精靈。

您上路了，但尚未完成！ 請務必檢查您的電子郵件。 您會收到確認，確認我們已收到您的要求，以及如何檢查設定[](shifts-connector-powershell-manage.md#check-connection-setup-status)狀態的連結。

> [!NOTE]
> 如果設定連接後發生問題或錯誤，系統就會以電子郵件通知您。 請遵循電子郵件中的指示來疑難排解問題。

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>停用開啟的班、開啟的班要求、調班要求，以及請假要求

> [!IMPORTANT]
> 只有在您選擇下列任一選項來停用開啟的班、開啟班要求、調班要求或精靈中的請假要求時，才能遵循這些步驟。 完成此步驟會隱藏 Shifts 中的功能。
>
> - 開啟班次： **班次使用者不會看到藍色 Yonder WFM 資料**
> - 調換要求 **：所有使用者的功能已停用**
> - 請假要求： **所有使用者都停用此功能**
>
> 如果沒有這個第二個步驟，使用者仍然會看到 Shifts 中的功能，如果使用者嘗試使用此功能，就會收到「不支援的操作」錯誤訊息。

若要在 Shifts 中隱藏已開啟的班、調班要求和請假要求，請使用 圖形 API [](/graph/api/resources/schedule?view=graph-rest-1.0) ```false``` 排程資源類型，針對對應至 Blue Yonder WFM 網站的每個小組設定下列參數：

- 開啟班次： ```openShiftsEnabled```
- 調換要求：  ```swapShiftsRequestsEnabled```
- 請假要求： ```timeOffRequestsEnabled```

若要在 Shifts 中隱藏開啟的班要求，請 **設定中開啟** 的班數，然後關閉開啟 **班** 設定。

## <a name="if-you-need-to-make-changes-to-a-connection"></a>如果您需要變更連接
<a name="update_connection"> </a>

設定連接之後，您可以使用 PowerShell 進行變更。 例如，您可以更新同步設定、小組映射，以及停用連接的同步。 有關逐步指南，請參閱使用 [PowerShell 管理您與 Blue Yonder 員工管理之間的 Shifts 連接](shifts-connector-powershell-manage.md)。

## <a name="related-articles"></a>相關文章

- [移轉連接器](shifts-connectors.md)
- [使用 PowerShell 管理您與 Blue Yonder 員工管理之間的 Shifts 連接](shifts-connector-powershell-manage.md)
- [在應用程式中管理 Shifts Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
