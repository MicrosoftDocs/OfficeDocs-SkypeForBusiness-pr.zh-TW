---
title: Microsoft Teams 應用程式使用方式報告
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
ms.date: 09/27/2022
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何在 Microsoft Teams 系統管理中心使用 Teams 應用程式使用方式報告。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c437676df215ead9b588091f2cb58c19d1e136fd
ms.sourcegitcommit: 8dd36e1e30a47316c15c99e964d0464715bcd742
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532263"
---
# <a name="microsoft-teams-app-usage-report"></a>Microsoft Teams 應用程式使用方式報告

Microsoft Teams 系統管理中心中的 Teams 應用程式使用方式報告可讓您深入瞭解使用者在 Teams 中使用哪些應用程式。 您可以深入瞭解貴組織中的應用程式活動，瞭解不同的 Microsoft (Viva learning、Shifts 等) 、協力廠商 (Polly、Trello 等，) &商務 (LOB) Teams 應用程式。   

您可以使用此報告來瞭解使用不同應用程式的位置，並深入探討每個應用程式的使用狀況資料。

此報告中顯示的資料提供下列問題的解答：

-  您環境中的使用者有多少個已安裝的應用程式？
-  根據 microsoft、協力廠商和 LOB)  (類型，您的環境中至少有一個作用中使用者的應用程式數目？
-  每個平臺 (Windows、Mac、Web 或行動裝置) 使用多少應用程式？
-  有多少作用中的使用者和作用中的團隊正在使用應用程式？

> [!NOTE]
> 此報告不包含 **側載** LOB 應用程式的使用量。

本文說明如何存取報表，以及如何檢視及解讀報表內的各種計量。 

## <a name="view-the-app-usage-report"></a>檢視應用程式使用方式報告

您必須是全域系統管理員、全域助讀程式或 Teams 服務系統管理員，才能在 Microsoft Teams 系統管理中心檢視報告。 請參閱[使用 Teams 系統管理員角色來管理 Teams](../using-admin-roles.md)，以了解取得系統管理員角色和權限。

1. 在 Microsoft Teams 系統管理中心的左側導覽中，選 **取 [分析&報告**  >  **使用方式報告。** 在 [ **檢視報表]** 索引標籤的 [ **報表**] 底下，選取 **[應用程式使用量]**。

2. 在 **[日期範圍]** 底下，選取範圍，然後選取 [ **執行報表]**。

:::image type="content" alt-text="Teams 系統管理中心內含圖說文字的 Teams 應用程式使用方式報告螢幕擷取畫面。" source="media/app-usage2-report10.png" lightbox="media/app-usage2-report10.png":::

## <a name="interpret-the-report"></a>解讀報表

|標注 |描述  |
|--------|-------------|
|**1**   |您可以檢視應用程式使用方式報告，瞭解過去 7、30、90 和 180 天的趨勢。 |
|**2**   |每份報告都有產生此報告的日期。 報告通常反映應用程式使用時間的 24-48 小時延遲。 例如，1 月 10 日的資料應該會在 1 月 12 日左右顯示在報告中。 |
|**3**   |<ul><li>圖表上的 X 軸是報表的選取日期範圍。</li> <li> Y 軸是專案計數。</li> </ul>將游標停留在代表指定日期之專案的點上，以查看該專案在指定日期上的實例數目。|
|**4**   |您可以選取圖例中的專案來篩選圖表上顯示的內容。 例如，選取 [ **作用中的 Microsoft 應用程式**]、[ **已安裝的應用程式總計**] 等，以僅查看每個應用程式的相關資訊。 變更此選取範圍並不會變更表格中的資訊。 <ul><li>**作用中的 Microsoft 應用程式** 是 microsoft 應用程式 (數目，例如貴組織中使用的 Viva learning) 。 </li> <li>**作用中的協力廠商應用程式** 是 (協力廠商應用程式的數目，例如貴組織中使用的「投票) 」。  </li> <li>**作用中的 LOB 應用程式** 是貴組織中所使用的商務營運應用程式數目。 </li><li>**作用中應用程式** 總數是貴組織中使用的應用程式總數。 </li><li>**非作用中應用程式總數** 是貴組織中未使用的應用程式數量。 </li><li>**已安裝的應用程式** 總數是貴組織內安裝的應用程式總數。 所有安裝計量的開始日期是 2021 年 10 月。 只會計算該日期之後安裝的應用程式。</li></ul> 圖表顯示組織在所選期間內每天的匯總計量。 例如，如果您選取 [1 月 28 日] 和 [標準 **作用中的協力廠商應用程式**]，圖表會顯示組織中 1 月 28 日使用的協力廠商應用程式總數。  |
|**5**   |表格提供每個應用程式的使用量明細。 <ul><li>**應用程式識別碼** 是出現在應用程式資訊清單中的外部應用程式識別碼。 <br/>如需應用程式的詳細資訊，請參閱 Teams 系統管理 [中心的 [管理應用程式] 區段，](/microsoftteams/manage-apps) 並使用此外部應用程式識別碼來瞭解。</li> <li>**應用程式名稱** 是應用程式資訊清單中所示的這個應用程式名稱。 </li> <li>**Publisher** 是此應用程式的發行者，如應用程式資訊清單中所示。 這僅適用于發佈到全域市集的應用程式。</li> <li>**使用此應用程式的 Teams** 是至少有一個使用者使用此應用程式的不同 Teams 團隊數目。 </li><li>**使用此應用程式的使用者** 是貴組織中使用此應用程式的不同使用者數目。</li> <li>**Windows 上使用的** 應用程式會指出貴組織中至少一位使用者是否曾在 Windows 上使用過該應用程式。</li><li>**在 Mac 上使用** 此應用程式可指出貴組織中至少一位使用者是否曾在 MAC 上使用過該應用程式。</li><li>**在 Web 上使用** ：表示貴組織中至少有一個使用者已在網路上使用該應用程式。 </li> <li>**上次使用的日期** 是貴組織中任何人上次使用該應用程式的日期。 </li></ul> |
|**6**   |選取 **[編輯欄]** 以新增或移除表格中的欄。|
|**7**   |將報表匯出為 CSV 檔案以進行離線分析。 選取 [ **匯出至 Excel** ] 圖示，報表就會在瀏覽器中下載。|
|**8** |在頂端圖表中表示的時間序列資料會顯示針對整個租使用者匯總的不同使用量計量。|
|**9** |下半部顯示的表格式資料會顯示每個小組匯總的不同使用量計量。|


## <a name="managing-apps-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 系統管理中心管理應用程式

如需如何管理 Teams 應用程式的詳細資訊，請參閱 [關於 Microsoft Teams 中的應用程式](/microsoftteams/deploy-apps-microsoft-teams-landing-page.md)。

若要將此報告中的應用程式連結至 Microsoft Teams 系統管理中心的 [管理應用程式] 體驗，您可以使用下列方法：

- 應用程式名稱
- 外部應用程式識別碼

外部應用程式識別碼相當於 Microsoft Store 應用程式 [管理應用程式] 頁面中的識別碼。 對於 LOB 應用程式，可以在 Teams 系統管理中心欄設定的 [[管理應用程式] 區段中](/microsoftteams/manage-apps)啟用 **[外部應用程式標識** 符] 欄。 您也可以在自訂 LOB 應用程式的應用程式詳細資料頁面上檢視它。

## <a name="related-articles"></a>相關文章

- [Teams 分析與報告](teams-reporting-reference.md)
