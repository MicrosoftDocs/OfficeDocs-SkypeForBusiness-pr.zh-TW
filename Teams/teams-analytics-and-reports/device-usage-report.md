---
title: Microsoft Teams 裝置使用方式報告
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解如何在 Microsoft Teams 系統管理中心使用 Teams 裝置使用方式報告，以查看貴組織中使用者如何連接到 Teams。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1d47888884ce86bfa56546a9df600ce958380e0d
ms.sourcegitcommit: 66e7b28ba1c0433535eb6a3e7d883851c27d9d1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "51478353"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams 裝置使用方式報告

Microsoft Teams 系統管理中心的 Teams 裝置使用方式報告會提供使用者如何連接到 Teams 的資訊。 您可以使用報表查看整個組織使用的裝置，包括在行動裝置上使用 Teams 的裝置數。  

## <a name="view-the-device-usage-report"></a>查看裝置使用方式報告

1. 在 Microsoft Teams 系統管理中心的左側流覽中，按一下 [分析&**報告**  >  **使用方式報告**。 On the **View reports** tab, under **Report**, select **Teams device usage**.
2. 在 **[日期範圍**」 下，選取範圍，然後按一下 [ **執行報表**> 。

    ![Teams 系統管理中心中 Teams 裝置使用方式報告與圖說圖的螢幕擷取畫面](../media/teams-reports-device-usage-with-callouts.png "Teams 系統管理中心中 Teams 裝置使用方式報告與圖說圖的螢幕擷取畫面")

## <a name="interpret-the-report"></a>解譯報表

|標注 |描述  |
|--------|-------------|
|**1**   |您可以針對過去 7 天或 30 天內的趨勢來查看 Teams 裝置使用方式報告。  |
|**2**   |每個報表都有產生報表的日期。 報告通常會反映啟用時間 24 小時的延遲。 |
|**3**   |<ul><li>圖表上的 X 軸代表用來 (**Windows、Mac、Linux、iOS、Android**  **Phone、Web**) 和 Teams 的不同裝置。   </li><li>Y 軸是所選時段內使用裝置的使用者數目。</li> </ul>將游標停留在代表裝置的長條上，以查看使用裝置連接到 Teams 的使用者數目。|
|**4**   |下表提供使用者裝置使用量的明細。 <ul><li>**使用者** 名稱是使用者的顯示名稱。 您可以按一下顯示名稱，以前往 Microsoft Teams 系統管理中心的使用者的設定頁面。 </li><li>**如果使用者** 在 Windows 型電腦的 Teams 桌面用戶端中活動，會選取 Windows。</li><li>**如果使用者在 MacOS** 電腦的 Teams 桌面用戶端中活動，會選取 Mac。 </li> <li>**如果使用者** 在 Linux 電腦的 Teams 桌面用戶端中活動，會選取 Linux。 </li> <li>**如果使用者在 iOS** 版 Teams 行動用戶端上使用中，會選取 iOS。</li><li>**如果使用者使用** Android 版 Teams 行動用戶端，系統即會選取 Android 手機。 <li><li>**如果使用者** 在 Teams Web 用戶端上使用中，則已選取 Web。 <li>**上次活動** 是使用者參與 Teams (UTC) 的最後一個日期。</li> </ul> 請注意，如果 Azure AD 中不再有使用者帳戶，使用者名稱會顯示為 「--」于表格中。 <br><br>若要在表格中查看您想要的資訊，請務必新增欄至資料表。 |
|**5**   |選取 **編輯欄** 以新增或移除表格中的欄。 |
|**6**   |您可以將報表匯出為 CSV 檔案，進行離線分析。 按一下 **[匯出至 Excel，** 然後在[下載> 選項卡上，按一下 **[下載** 以在報表準備就緒時下載報表。<br><br>![顯示匯出報表的下載清單螢幕擷取畫面](../media/teams-reports-export-to-csv.png)|


## <a name="make-the-user-specific-data-anonymous"></a>將使用者特定資料匿名

若要將 Teams 裝置使用方式報告中的資料匿名，您必須是全域系統管理員。 這會隱藏可辨識的資訊，例如報表及其匯出中的顯示名稱、電子郵件和 AAD 識別碼。

1. 在 Microsoft 365 系統管理中心，請前往設定組織設定，然後選擇在服務 \> ******標籤** 下的報表。
    
2. 選取 **報表**，然後選擇顯示 **匿名識別碼**。 這項設定會同時適用于 Microsoft 365 系統管理中心以及 Teams 系統管理中心的使用方式報告。
  
3. 選取 **儲存變更**。

## <a name="related-topics"></a>相關主題

- [Teams 分析和報告](teams-reporting-reference.md)
