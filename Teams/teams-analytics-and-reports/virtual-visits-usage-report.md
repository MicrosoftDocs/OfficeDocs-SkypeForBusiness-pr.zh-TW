---
title: Microsoft Teams虛擬造訪使用方式報告
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
description: 瞭解如何使用 Microsoft Teams 系統管理中心的虛擬造訪使用方式報告，以取得貴組織中虛擬約會活動的概觀。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 91f1aa8ff25b591305c8d5ca41485f7ceec9faca
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853214"
---
# <a name="microsoft-teams-virtual-visits-usage-report"></a>Microsoft Teams虛擬造訪使用方式報告

Microsoft Teams系統管理中心的虛擬造訪使用方式報告提供您組織中Teams虛擬約會活動的概觀。 您可以檢視透過[Bookings 應用程式](../expand-teams-across-your-org/bookings-virtual-visits.md)和Microsoft Teams[電子健康情況記錄 (EHR) 連接器排](../expand-teams-across-your-org/healthcare/teams-in-hc.md#virtual-appointments-and-electronic-healthcare-record-ehr-integration)程的虛擬約會詳細活動。

若要檢視報告，您必須是全域系統管理員或Teams系統管理員。

報表包含下列索引標籤。 您會在報告中看到的資訊，取決於您是否擁有 Bookings 應用程式、Teams EHR 連接器或兩者的授權。

|選項 卡 |描述  |
|---------|---------|
|**[虛擬造訪](#virtual-visits)**     |顯示虛擬約會的總數，其中包含使用 Bookings 應用程式排定的約會數目明細，以及Teams由 EHR 系統進行的 EHR 整合式會議。         |
|**[時間](#duration)**     |顯示參與者的平均約會持續時間和平均大廳等候時間。         |
|**[Bookings](#bookings)**     |顯示透過 Bookings 應用程式排程的約會數目。         |
|**[EHR](#ehr)**     |顯示從 EHR 系統進行的Teams個 EHR 整合式約會數目。         |  

使用此報告以深入瞭解貴組織中的虛擬約會活動和趨勢。 這些資訊可協助您優化虛擬約會，以提供更好的商務成果。

## <a name="view-the-virtual-visits-usage-report"></a>檢視虛擬造訪使用方式報告

1. 在Microsoft Teams系統管理中心的左側導覽中，選擇 **[分析] &報**  >  表 **使用報表**。 在 [ **檢視報表]** 索引標籤的 [ **報表**] 底下，選 **取 [虛擬造訪使用量]**。
2. 在 **[日期範圍]** 底下，選取 7 天、30 天或 90 天的日期範圍。 然後，選擇 [ **執行報表]**。

> [!NOTE]
> 根據預設，虛擬造訪分析功能已開啟，且報表可供使用。 您可以使用這份報告，授與 Microsoft 許可權來收集貴組織中虛擬約會的相關資料。 如需資料保留原則的相關資訊，請參閱[資料保留、刪除和破壞Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)。
>
>如果您想要關閉組織的報表，可以在頁面右上角 **的設定** 中執行此動作。 此設定可能需要 0 (零) 到 2 小時，才會在您變更後生效。

## <a name="interpret-the-report"></a>解讀報表

### <a name="virtual-visits"></a>虛擬造訪

您會在這裡看到的圖形取決於您是否擁有 Bookings 應用程式的授權、Teams EHR 連接器或兩者都擁有授權。 若要深入瞭解，請參閱[管理Bookings應用程式](../bookings-app-admin.md)，以及[整合至 Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md)或[整合至 EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md)。

:::image type="content" source="../media/virtual-visits-usage-report-virtual-visits.png" alt-text="顯示編號圖說文字的虛擬造訪使用方式報告 [虛擬流覽] 索引標籤的螢幕擷取畫面。" lightbox="../media/virtual-visits-usage-report-virtual-visits.png":::

|標注 |描述  |
|--------|-------------|
|**1**   |每份報告都有該報告產生時間的日期。 報告通常會反映啟用時間的 24 到 48 小時延遲。 |
|**2**   |X 軸是報表選取的日期範圍。 Y 軸是約會的數目。<br>將游標停留在指定日期的點上，即可查看該日期的約會數目。|
|**3**   |您可以選取圖例中的專案來篩選圖表上顯示的內容。 例如，選 **取 [總Bookings虛擬流覽次數**] 或 [**總計 EHR 虛擬流覽量**]，以僅查看與每一次相關的資訊。 變更此選取範圍並不會變更表格中的資訊。 |
|**4**   |表格提供您在所選日期範圍內所進行的每個約會的詳細資訊。 <ul><li>**開始時間 (UTC)** 是教職員成員和參與者同時參與會議的日期和時間，或會議中發生第一個活動的時間。  </li> <li>**會議 ID** 是會議的唯一識別碼。</li> <li>**大廳等候時間** 是指參與者第一次加入大廳到同一位參與者或另一位參與者被教職員成員准准參加會議之間的時間。</li><li>**持續時間** 是指開始時間與最後一個人離開會議的時間差異。 如果教職員成員和參與者都未加入會議，則持續時間會顯示為 0 (零) 。</li> <li>**狀態** 會顯示會議狀態。 <ul><li>**已完成**：如果有一或多個教職員成員和參與者加入會議，則會議已結束。 或者，如果有一或多個參與者加入會議且會議已結束。</li> <li> **沒有顯示**：如果一個教職員成員加入會議，但沒有其他人加入，而且會議已結束。 </li></ul> </li> <li>**會議類型** 會指出虛擬約會是透過 Bookings 應用程式或 Teams EHR 連接器排程。</li> <li>**出席** 者是會議中的教職員成員和參與者總數。</li> <li>**傳送的簡訊** 會指出是否已傳送簡訊通知給出席者。 </li> </li> </ul> |
|**5**   |選 **取 [設定**] 以開啟 **[虛擬造訪分析] 窗** 格。 您可以在此為貴組織關閉或開啟虛擬造訪報告，並新增或移除資料表中的資料行。 若要在資料表中查看您要的資訊，請務必將欄新增至資料表。|
|**6**   |您可以將報表匯出為 CSV 檔案以進行離線分析。 選取 [**匯出至Excel**]，然後在 [**下載**] 索引標籤上選擇 [**下載**] 以在報表準備就緒時下載報表。|

### <a name="duration"></a>時間

:::image type="content" source="../media/virtual-visits-usage-report-duration.png" alt-text="顯示編號圖說文字的虛擬造訪使用方式報告 [持續時間] 索引標籤的螢幕擷取畫面。" lightbox="../media/virtual-visits-usage-report-duration.png":::

|標注 |描述  |
|--------|-------------|
|**1**   |每份報告都有該報告產生時間的日期。 報告通常會反映啟用時間的 24 到 48 小時延遲。 |
|**2**   |X 軸是報表選取的日期範圍。 Y 軸是分鐘數。<br>將游標停留在指定日期的點上，以查看指定日期的平均約會持續時間或平均大廳等候時間。  |
|**3**   |您可以選取圖例中的專案來篩選圖表上顯示的內容。 例如，選取 **[平均虛擬造訪持續時間** ] 或 [ **平均大廳等候時間** ]，只查看與每一個服務相關的資訊。 變更此選取範圍並不會變更表格中的資訊。 |
|**4**   |表格提供您在所選日期範圍內所進行的每個約會的詳細資訊。 <ul><li>**開始時間 (UTC)** 是教職員成員和參與者同時參與會議的日期和時間，或會議中發生第一個活動的時間。  </li> <li>**會議 ID** 是會議的唯一識別碼。</li> <li>**大廳等候時間** 是指參與者第一次加入大廳到同一位參與者或另一位參與者被教職員成員准准參加會議之間的時間。</li><li>**持續時間** 是指開始時間與最後一個人離開會議的時間差異。 如果教職員成員和參與者都未加入會議，則持續時間會顯示為 0 (零) 。</li> <li>**狀態** 會顯示會議狀態。 <ul><li>**已完成**：如果有一或多個教職員成員和參與者加入會議，則會議已結束。 或者，如果有一或多個參與者加入會議且會議已結束。</li> <li> **沒有顯示**：如果一個教職員成員加入會議，但沒有其他人加入，而且會議已結束。 </li></ul> </li> <li>**會議類型** 會指出虛擬約會是透過 Bookings 應用程式或 Teams EHR 連接器排程。</li> <li>**出席** 者是會議中的教職員成員和參與者總數。</li> <li>**傳送的簡訊** 會指出是否已傳送簡訊通知給出席者。 </li> </li> </ul>|
|**5**   |選 **取 [設定**] 以開啟 **[虛擬造訪分析] 窗** 格。 您可以在此為貴組織關閉或開啟虛擬造訪報告，並新增或移除資料表中的資料行。 若要在資料表中查看您要的資訊，請務必將欄新增至資料表。|
|**6**   |您可以將報表匯出為 CSV 檔案以進行離線分析。 選取 [**匯出至Excel**]，然後在 [**下載**] 索引標籤上選擇 [**下載**] 以在報表準備就緒時下載報表。|
### <a name="bookings"></a>Bookings

如果您的授權包含Bookings應用程式，您將會看到這個索引標籤。 若要深入瞭解，請參閱[管理Bookings應用程式](../bookings-app-admin.md)。

:::image type="content" source="../media/virtual-visits-usage-report-bookings.png" alt-text="顯示編號圖說文字的 [虛擬流覽次數] 使用方式報告中 [Bookings] 索引標籤的螢幕擷取畫面。" lightbox="../media/virtual-visits-usage-report-bookings.png":::

|標注 |描述  |
|--------|-------------|
|**1**   |每份報告都有該報告產生時間的日期。 報告通常會反映啟用時間的 24 到 48 小時延遲。 |
|**2**   |X 軸是報表選取的日期範圍。 Y 軸是Bookings約會的數目。<br>將游標停留在指定日期的點上，以查看該日期發生的Bookings約會數目。|
|**3**   |表格提供您在所選日期範圍內所進行的每個約會的詳細資訊。 <ul><li>**開始時間 (UTC)** 是教職員成員和參與者同時參與會議的日期和時間，或會議中發生第一個活動的時間。  </li> <li>**會議 ID** 是會議的唯一識別碼。</li> <li>**大廳等候時間** 是指參與者第一次加入大廳到同一位參與者或另一位參與者被教職員成員准准參加會議之間的時間。</li><li>**持續時間** 是指開始時間與最後一個人離開會議的時間差異。 如果教職員成員和參與者都未加入會議，則持續時間會顯示為 0 (零) 。</li> <li>**狀態** 會顯示會議狀態。 <ul><li>**已完成**：如果有一或多個教職員成員和參與者加入會議，則會議已結束。 或者，如果有一或多個參與者加入會議且會議已結束。</li> <li> **沒有顯示**：如果一個教職員成員加入會議，但沒有其他人加入，而且會議已結束。 </li></ul> </li> <li>**會議類型** 會指出虛擬約會是透過 Bookings 應用程式或 Teams EHR 連接器排程。</li> <li>**出席** 者是會議中的教職員成員和參與者總數。</li> <li>**傳送的簡訊** 會指出是否已傳送簡訊通知給出席者。 </li> </li> </ul>|
|**4**   |選 **取 [設定**] 以開啟 **[虛擬造訪分析] 窗** 格。 您可以在此為貴組織關閉或開啟虛擬造訪報告，並新增或移除資料表中的資料行。 若要在資料表中查看您要的資訊，請務必將欄新增至資料表。|
|**5**   |您可以將報表匯出為 CSV 檔案以進行離線分析。 選取 [**匯出至Excel**]，然後在 [**下載**] 索引標籤上選擇 [**下載**] 以在報表準備就緒時下載報表。|
### <a name="ehr"></a>EHR

如果您的授權包含 Teams EHR 連接器，您將會看到此索引標籤。 若要深入瞭解，請參閱[整合至 Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md)或[整合至 EHR。](../expand-teams-across-your-org/healthcare/ehr-admin.md)

:::image type="content" source="../media/virtual-visits-usage-report-ehr.png" alt-text="顯示編號圖說文字的虛擬造訪使用方式報告之 [EHR] 索引標籤的螢幕擷取畫面。" lightbox="../media/virtual-visits-usage-report-ehr.png":::

|標注 |描述  |
|--------|-------------|
|**1**   |每份報告都有該報告產生時間的日期。 報告通常會反映啟用時間的 24 到 48 小時延遲。 |
|**2**   |X 軸是報表選取的日期範圍。 Y 軸是 EHR 約會的數目。<br>將游標停留在指定日期的點上，以查看該日期的 EHR 約會數目。|
|**3**   |表格提供您在所選日期範圍內所進行的每個約會的詳細資訊。 <ul><li>**開始時間 (UTC)** 是教職員成員和參與者同時參與會議的日期和時間，或會議中發生第一個活動的時間。  </li> <li>**會議 ID** 是會議的唯一識別碼。</li> <li>**大廳等候時間** 是指參與者第一次加入大廳到同一位參與者或另一位參與者被教職員成員准准參加會議之間的時間。</li><li>**持續時間** 是指開始時間與最後一個人離開會議的時間差異。 如果教職員成員和參與者都未加入會議，則持續時間會顯示為 0 (零) 。</li> <li>**狀態** 會顯示會議狀態。 <ul><li>**已完成**：如果有一或多個教職員成員和參與者加入會議，則會議已結束。 或者，如果有一或多個參與者加入會議且會議已結束。</li> <li> **沒有顯示**：如果一個教職員成員加入會議，但沒有其他人加入，而且會議已結束。 </li></ul> </li> <li>**會議類型** 會指出虛擬約會是透過 Bookings 應用程式或 Teams EHR 連接器排程。</li> <li>**出席** 者是會議中的教職員成員和參與者總數。</li> <li>**傳送的簡訊** 會指出是否已傳送簡訊通知給出席者。 </li> </li> </ul>|
|**4**   |選 **取 [設定**] 以開啟 **[虛擬造訪分析] 窗** 格。 您可以在此為貴組織關閉或開啟虛擬造訪報告，並新增或移除資料表中的資料行。 若要在資料表中查看您要的資訊，請務必將欄新增至資料表。|
|**5**   |您可以將報表匯出為 CSV 檔案以進行離線分析。 選取 [**匯出至Excel**]，然後在 [**下載**] 索引標籤上選擇 [**下載**] 以在報表準備就緒時下載報表。|

> [!NOTE]
> 如果您的組織想要參與私人預覽，讓企業決策者等非系統管理員使用者能夠存取和檢視此報告，請與 [我們連](mailto:tapmwtanalytics@microsoft.com)絡。

## <a name="related-articles"></a>相關文章

- [Teams 分析與報告](teams-reporting-reference.md)
- [使用 Teams 和 Bookings 應用程式的虛擬約會](../expand-teams-across-your-org/bookings-virtual-visits.md)
- [虛擬約會與 Teams - 整合至 EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md)
- [虛擬約會與 Teams - 整合至 Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md)
