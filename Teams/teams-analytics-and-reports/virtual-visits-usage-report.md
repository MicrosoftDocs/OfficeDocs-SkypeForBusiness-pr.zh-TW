---
title: Microsoft Teams虛擬訪問使用方式報告
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何在系統管理中心使用虛擬Microsoft Teams使用方式報告，以取得貴組織的虛擬流覽活動概觀。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2b3432ea92ad89c5304d81b266fce61fb9b95d5b
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435847"
---
# <a name="microsoft-teams-virtual-visits-usage-report"></a>Microsoft Teams虛擬訪問使用方式報告

系統管理中心中的虛擬Microsoft Teams使用方式報告，提供貴Teams虛擬流覽活動概觀。 您可以透過[Bookings](../expand-teams-across-your-org/bookings-virtual-visits.md) App 和[EHR Microsoft Teams電子](../expand-teams-across-your-org/healthcare/teams-in-hc.md#virtual-visits-and-electronic-healthcare-record-ehr-integration)健康記錄 (虛擬約會) 活動。

若要查看報表，您必須是全域系統管理員或Teams管理員。

報表包含下列定位停駐點。 您在報告中看到的資訊取決於您擁有 Bookings App、eHR 連接器或兩者Teams授權。

|選項 卡 |描述  |
|---------|---------|
|**[虛擬訪問](#virtual-visits)**     |顯示虛擬訪問的總數，以及使用 Bookings App 排定的Teams EHR 整合會議。         |
|**[時間](#duration)**     |顯示參與者的平均訪問持續時間和大廳的平均等候時間。         |
|**[Bookings](#bookings)**     |顯示透過 Bookings App 排定的流覽次數。         |
|**[EHR](#ehr)**     |顯示從 EHR 系統Teams EHR 整合的拜訪次數。         |  

使用此報告可深入瞭解貴組織的虛擬訪問活動和趨勢。 這些資訊可協助優化虛擬訪問，以提供更好的商務成果。

## <a name="view-the-virtual-visits-usage-report"></a>查看虛擬訪問使用方式報告

1. 在系統管理中心的左側導Microsoft Teams，選擇分析 **&報表**  >  **。** On the **View reports** tab, under **Report**, select **Virtual Visits usage**.
2. 在 **日期範圍** 下，選取 7 天、30 天或 90 天的日期範圍。 接著，選擇 **執行報表**。

> [!NOTE]
> 根據預設，虛擬訪問分析為啟用狀態，且報告可供使用。 您可以使用此報表，讓 Microsoft 有權收集貴組織中虛擬訪問的資料。 有關資料保留政策的資訊，請參閱資料[保留、刪除和破壞](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)Microsoft 365。
>
>如果您想要關閉貴組織的報表，您可以在頁面設定右上角的其中一個視窗執行此工作。 此設定可能需要 0 (0) 2 小時，才能在您變更後生效。

## <a name="interpret-the-report"></a>解譯報表

### <a name="virtual-visits"></a>虛擬訪問

您在這裡會看到的圖形取決於您是否擁有 Bookings App、Teams EHR 連接器或兩者都有授權。 若要深入瞭解，請參閱 [管理 Bookings App](../bookings-app-admin.md)，以及整合至 [Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) 或 [整合至Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md)。

:::image type="content" source="../media/virtual-visits-usage-report-virtual-visits.png" alt-text="顯示編號圖說說法之虛擬訪問使用方式報表的虛擬訪問清單的螢幕擷取畫面。" lightbox="../media/virtual-visits-usage-report-virtual-visits.png":::

|標注 |描述  |
|--------|-------------|
|**1**   |每個報表都有產生報表的日期。 報告通常會反映啟用時間起 24 到 48 小時的延遲。 |
|**2**   |X 軸是報表的選取日期範圍。 Y 軸是訪問次數。<br>將游標停留在給定日期的點上方，以查看該日期的拜訪次數。|
|**3**   |您可以選取圖例中的專案，以篩選圖表上看到的專案。 例如，選取 **總計預約虛擬訪問** 或 **EHR 總計虛擬訪問** ，只查看每個虛擬訪問的相關資訊。 變更此選取範圍不會變更表格中的資訊。 |
|**4**   |表格提供您所選日期範圍內每一次流覽的詳細資料。 <ul><li>**UTC (開始時間**) 是教職員成員和參與者同時參與會議或會議第一個活動發生的日期和時間。  </li> <li>**會議 ID** 是會議的唯一識別碼。</li> <li>**大廳等候時間** 是參與者第一次加入大廳到該同一位參與者或另一位參與者被教職員成員獲准參加會議之間的時間。</li><li>**持續時間** 是開始時間與最後一個人離開會議的時間差。 如果教職員成員和參與者都未加入會議，持續時間會顯示為 0 (0) 。</li> <li>**狀態** 會顯示會議狀態。 <ul><li>**完成**：如果一或多個教職員成員和參與者加入會議，且會議已經結束。 或者，如果一或多個參與者加入會議，且會議已經結束。</li> <li> **無顯示**：如果有一位教職員成員加入會議，但其他人沒有加入，且會議已經結束。 </li></ul> </li> <li>**會議類型** 會指出虛擬約會是透過 Bookings App 或 EHR 連接器Teams排程。</li> <li>**出席者** 是會議的員工成員和參與者總數。</li> <li>**已送出** 簡訊表示是否已將簡訊通知寄給出席者。 </li> </li> </ul> |
|**5**   |選取 **設定** 以開啟 **虛擬訪問分析** 窗格。 您可以在這裡關閉或開啟貴組織的虛擬訪問報告，以及新增或移除表格中的欄。 若要在表格中查看您想要的資訊，請務必新增欄至資料表。|
|**6**   |您可以將報表匯出為 CSV 檔案，進行離線分析。 選取 **匯出Excel**，然後在下載的選項卡上，選擇下載以在報表準備就緒時下載報表。|

### <a name="duration"></a>時間

:::image type="content" source="../media/virtual-visits-usage-report-duration.png" alt-text="顯示編號圖說說法的虛擬訪問使用方式報表的持續時間選項卡螢幕擷取畫面。" lightbox="../media/virtual-visits-usage-report-duration.png":::

|標注 |描述  |
|--------|-------------|
|**1**   |每個報表都有產生報表的日期。 報告通常會反映啟用時間起 24 到 48 小時的延遲。 |
|**2**   |X 軸是報表的選取日期範圍。 Y 軸是分鐘數。<br>將游標停留在給定日期的點上方，以查看給定日期的平均流覽持續時間或大廳的平均等候時間。  |
|**3**   |您可以選取圖例中的專案，以篩選圖表上看到的專案。 例如，選取 **平均虛擬流覽持續時間** 或 **平均大廳** 等候時間，只查看與每個時間相關的資訊。 變更此選取範圍不會變更表格中的資訊。 |
|**4**   |表格提供您所選日期範圍內每一次流覽的詳細資料。 <ul><li>**UTC (開始時間**) 是教職員成員和參與者同時參與會議或會議第一個活動發生的日期和時間。  </li> <li>**會議 ID** 是會議的唯一識別碼。</li> <li>**大廳等候時間** 是參與者第一次加入大廳到該同一位參與者或另一位參與者被教職員成員獲准參加會議之間的時間。</li><li>**持續時間** 是開始時間與最後一個人離開會議的時間差。 如果教職員成員和參與者都未加入會議，持續時間會顯示為 0 (0) 。</li> <li>**狀態** 會顯示會議狀態。 <ul><li>**完成**：如果一或多個教職員成員和參與者加入會議，且會議已經結束。 或者，如果一或多個參與者加入會議，且會議已經結束。</li> <li> **無顯示**：如果有一位教職員成員加入會議，但其他人沒有加入，且會議已經結束。 </li></ul> </li> <li>**會議類型** 會指出虛擬約會是透過 Bookings App 或 EHR 連接器Teams排程。</li> <li>**出席者** 是會議的員工成員和參與者總數。</li> <li>**已送出** 簡訊表示是否已將簡訊通知寄給出席者。 </li> </li> </ul>|
|**5**   |選取 **設定** 以開啟 **虛擬訪問分析** 窗格。 您可以在這裡關閉或開啟貴組織的虛擬訪問報告，以及新增或移除表格中的欄。 若要在表格中查看您想要的資訊，請務必新增欄至資料表。|
|**6**   |您可以將報表匯出為 CSV 檔案，進行離線分析。 選取 **匯出Excel**，然後在下載的選項卡上，選擇下載以在報表準備就緒時下載報表。|
### <a name="bookings"></a>Bookings

如果您有包含 Bookings 應用程式之授權，就會看到此 Tab。 若要深入瞭解，請參閱 [管理 Bookings 應用程式](../bookings-app-admin.md)。

:::image type="content" source="../media/virtual-visits-usage-report-bookings.png" alt-text="顯示編號圖說說法的虛擬訪問使用方式報表的 Bookings 選項卡螢幕擷取畫面。" lightbox="../media/virtual-visits-usage-report-bookings.png":::

|標注 |描述  |
|--------|-------------|
|**1**   |每個報表都有產生報表的日期。 報告通常會反映啟用時間起 24 到 48 小時的延遲。 |
|**2**   |X 軸是報表的選取日期範圍。 Y 軸是 Bookings 的查訪次數。<br>將游標停留在給定日期的點上方，以查看該日期發生的 Bookings 訪問次數。|
|**3**   |表格提供您所選日期範圍內每一次流覽的詳細資料。 <ul><li>**UTC (開始時間**) 是教職員成員和參與者同時參與會議或會議第一個活動發生的日期和時間。  </li> <li>**會議 ID** 是會議的唯一識別碼。</li> <li>**大廳等候時間** 是參與者第一次加入大廳到該同一位參與者或另一位參與者被教職員成員獲准參加會議之間的時間。</li><li>**持續時間** 是開始時間與最後一個人離開會議的時間差。 如果教職員成員和參與者都未加入會議，持續時間會顯示為 0 (0) 。</li> <li>**狀態** 會顯示會議狀態。 <ul><li>**完成**：如果一或多個教職員成員和參與者加入會議，且會議已經結束。 或者，如果一或多個參與者加入會議，且會議已經結束。</li> <li> **無顯示**：如果有一位教職員成員加入會議，但其他人沒有加入，且會議已經結束。 </li></ul> </li> <li>**會議類型** 會指出虛擬約會是透過 Bookings App 或 EHR 連接器Teams排程。</li> <li>**出席者** 是會議的員工成員和參與者總數。</li> <li>**已送出** 簡訊表示是否已將簡訊通知寄給出席者。 </li> </li> </ul>|
|**4**   |選取 **設定** 以開啟 **虛擬訪問分析** 窗格。 您可以在這裡關閉或開啟貴組織的虛擬訪問報告，以及新增或移除表格中的欄。 若要在表格中查看您想要的資訊，請務必新增欄至資料表。|
|**5**   |您可以將報表匯出為 CSV 檔案，進行離線分析。 選取 **匯出Excel**，然後在下載的選項卡上，選擇下載以在報表準備就緒時下載報表。|
### <a name="ehr"></a>EHR

如果您擁有包含 EHR 連接器之 Teams，就會看到此Teams。 若要深入瞭解，請參閱 [整合至 Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) 或 [整合至Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md)。

:::image type="content" source="../media/virtual-visits-usage-report-ehr.png" alt-text="顯示編號圖說說法的虛擬訪問使用方式報表的 EHR 選項卡螢幕擷取畫面。" lightbox="../media/virtual-visits-usage-report-ehr.png":::

|標注 |描述  |
|--------|-------------|
|**1**   |每個報表都有產生報表的日期。 報告通常會反映啟用時間起 24 到 48 小時的延遲。 |
|**2**   |X 軸是報表的選取日期範圍。 Y 軸是 EHR 訪問次數。<br>將游標停留在給定日期的點上方，以查看該日期的 EHR 訪問次數。|
|**3**   |表格提供您所選日期範圍內每一次流覽的詳細資料。 <ul><li>**UTC (開始時間**) 是教職員成員和參與者同時參與會議或會議第一個活動發生的日期和時間。  </li> <li>**會議 ID** 是會議的唯一識別碼。</li> <li>**大廳等候時間** 是參與者第一次加入大廳到該同一位參與者或另一位參與者被教職員成員獲准參加會議之間的時間。</li><li>**持續時間** 是開始時間與最後一個人離開會議的時間差。 如果教職員成員和參與者都未加入會議，持續時間會顯示為 0 (0) 。</li> <li>**狀態** 會顯示會議狀態。 <ul><li>**完成**：如果一或多個教職員成員和參與者加入會議，且會議已經結束。 或者，如果一或多個參與者加入會議，且會議已經結束。</li> <li> **無顯示**：如果有一位教職員成員加入會議，但其他人沒有加入，且會議已經結束。 </li></ul> </li> <li>**會議類型** 會指出虛擬約會是透過 Bookings App 或 EHR 連接器Teams排程。</li> <li>**出席者** 是會議的員工成員和參與者總數。</li> <li>**已送出** 簡訊表示是否已將簡訊通知寄給出席者。 </li> </li> </ul>|
|**4**   |選取 **設定** 以開啟 **虛擬訪問分析** 窗格。 您可以在這裡關閉或開啟貴組織的虛擬訪問報告，以及新增或移除表格中的欄。 若要在表格中查看您想要的資訊，請務必新增欄至資料表。|
|**5**   |您可以將報表匯出為 CSV 檔案，進行離線分析。 選取 **匯出Excel**，然後在下載的選項卡上，選擇下載以在報表準備就緒時下載報表。|

> [!NOTE]
> 如果貴組織想參與私人預覽，讓非系統管理員使用者 ，例如商務決策者能夠存取及查看此報告，請 [告訴我們](mailto:tapmwtanalytics@microsoft.com)。

## <a name="related-articles"></a>相關文章

- [Teams 分析與報告](teams-reporting-reference.md)
- [使用 Teams 和 Bookings 應用程式進行虛擬訪問](../expand-teams-across-your-org/bookings-virtual-visits.md)
- [使用虛擬Teams - 整合至Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md)
- [使用虛擬Teams - 整合至 Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md)
