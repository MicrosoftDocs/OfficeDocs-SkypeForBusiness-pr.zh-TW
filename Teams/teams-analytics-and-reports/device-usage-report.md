---
title: Microsoft Teams 裝置使用方式報告
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何使用 Microsoft Teams 系統管理中心的 Teams 裝置使用方式報告，以查看貴組織中的使用者如何連線至 Teams。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 949ad172425f5e02da2fa67078193b198cb987d1
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825507"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams 裝置使用方式報告

Microsoft Teams 系統管理中心的 Teams 裝置使用方式報告會提供使用者如何連線至 Teams 的相關資訊。 您可以使用報告來查看貴組織中使用的裝置，包括在外出時從行動裝置使用 Teams 的數目。  

## <a name="view-the-device-usage-report"></a>檢視裝置使用方式報告

1. 在 Microsoft Teams 系統管理中心的左側導覽中，按一下 **[分析&報告**  >  **使用方式報告。** 在 [ **檢視報表]** 索引標籤的 [ **報表**] 底下，選 **取 [Teams 裝置使用量]**。
2. 在 **[日期範圍]** 底下，選取範圍，然後按一下 [ **執行報表]**。

    ![Teams 系統管理中心內含圖說文字的 Teams 裝置使用方式報告螢幕擷取畫面。](../media/teams-reports-device-usage-with-callouts.png "Teams 系統管理中心內含圖說文字的 Teams 裝置使用方式報告螢幕擷取畫面")

## <a name="interpret-the-report"></a>解讀報表

|標注 |描述  |
|--------|-------------|
|**1**   |您可以檢視 Teams 裝置使用方式報告，瞭解過去 7 天或 30 天的趨勢。  |
|**2**   |每份報告都有該報告產生時間的日期。 報告通常會反映啟用時間的 24 小時延遲。 |
|**3**   |<ul><li>圖表上的 X 軸代表用來連線至 **Teams (Windows**、 **Mac**、 **Linux**、 **iOS**、 **Android Phone**、 **Web**) 的不同裝置。 </li><li>Y 軸是所選時段內使用裝置的使用者數目。</li> </ul>將游標停留在代表裝置的列上，以查看使用裝置連線至 Teams 的使用者數目。|
|**4**   |表格提供使用者的裝置使用量明細。 <ul><li>**使用者名稱** 是使用者的顯示名稱。 您可以按一下顯示名稱，移至 Microsoft Teams 系統管理中心的使用者設定頁面。 </li><li>如果使用者在 Windows 電腦的 Teams 桌面用戶端中處於使用中狀態，**就會** 選取 Windows。</li><li>如果使用者在 macOS 電腦上使用 Teams 桌面用戶端，**則** 會選取 Mac。 </li> <li>如果使用者在 Linux 電腦上使用 Teams 桌面用戶端，則會選取 **Linux**。 </li> <li>如果使用者在 **iOS** 版 Teams 行動用戶端上處於使用中狀態，就會選取 iOS。</li><li>如果使用者在 Android 版 Teams 行動用戶端上處於使用中狀態，就會選取 Android **手機**。 <li><li>如果使用者在 Teams Web 用戶端上處於使用中狀態，就會選取 [**Web**]。 <li>**上次活動** 是使用者參與 Teams 活動 (UTC) 的最後一個日期。</li> </ul> 請注意，如果 Azure AD 中不再存在使用者帳戶，則使用者名稱會在資料表中顯示為 「--」。 <br><br>若要在資料表中查看您要的資訊，請務必將欄新增至資料表。 |
|**5**   |選取 **[編輯欄]** 以新增或移除表格中的欄。 |
|**6**   |您可以將報表匯出為 CSV 檔案以進行離線分析。 按一下 **[匯出至 Excel**]，然後在 [ **下載] 索引卷** 標上，按一下 [ **下載** ] 以在報表準備就緒時下載報表。<br><br>![顯示匯出報告的 [下載] 索引標籤螢幕擷取畫面。](../media/teams-reports-export-to-csv.png)|


## <a name="make-the-user-specific-data-anonymous"></a>將使用者的特定資料匿名化

若要將 Teams 裝置使用方式報告中的資料匿名化，您必須是全域系統管理員。 這會隱藏報表中的可識別資訊，例如顯示名稱、電子郵件和 AAD ID 及其匯出。

1. 在 Microsoft 365 系統管理中心 中，移至 [**設定** \> **組織設定]**，然後在 [**服務]** 索引標籤下選擇 [**報告]**。
    
2. 選取 **[報告**]，然後選擇 **[顯示匿名識別碼]**。 此設定會同時套用至 Microsoft 365 系統管理中心 中的使用方式報告，以及 Teams 系統管理中心。
  
3. 選 **取 [儲存變更]**。

## <a name="related-topics"></a>相關主題

- [Teams 分析與報告](teams-reporting-reference.md)
