---
title: Microsoft 團隊裝置使用量報告
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 瞭解如何使用 Microsoft 團隊系統管理中心中的 [團隊裝置使用量] 報告, 以瞭解貴組織中的使用者如何連線至團隊。
appliesto:
- Microsoft Teams
ms.openlocfilehash: cfe8b11d633a8848d73e87c8fe0b4ecc8854062f
ms.sourcegitcommit: a5cde2df1aceed9d919ef53281dd0d75f1f5e183
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2019
ms.locfileid: "36667099"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft 團隊裝置使用量報告

Microsoft 團隊系統管理中心的 [小組裝置使用量] 報告可提供使用者連線至團隊之方式的相關資訊。 您可以使用報告來查看貴組織所使用的裝置, 包括在行動裝置上使用的小組數。  

## <a name="view-the-report"></a>查看報表

1. 在 Microsoft [團隊管理中心] 的左導覽中, 按一下 [**分析] & 報表**], 然後在 [**報表**] 底下, 選取 [**團隊裝置使用方式**]。
2. 在 [**日期範圍**] 底下, 選取一個範圍, 然後按一下 [**執行報表**]。

    小組系統![管理中心的 [小組裝置使用方式] 報告螢幕擷取畫面 (含標注])小組系統(../media/teams-reports-device-usage-with-callouts.png "管理中心的 [小組裝置使用方式] 報告螢幕擷取畫面 (含標注"))

## <a name="interpret-the-report"></a>解讀報表

|圖說文字 |說明  |
|--------|-------------|
|**sr-1**   |您可以在過去7天或28天的趨勢中查看小組裝置使用方式報告。  |
|**pplx-2**   |每個報告都有產生報告的日期。 報告通常會反映來自啟用時間的24到48小時延遲時間。 |
|**3**   |<ul><li>圖表上的 X 軸代表用來連接至團隊的不同裝置 (**Windows**、 **Mac**、 **iOS**、 **Android 手機**)。 </li><li>Y 軸是在所選時間範圍內使用裝置的使用者數目。</li> </ul>將游標暫留在代表裝置的列上, 即可查看使用裝置連接至團隊的使用者數目。|
|**4**   |此表格可讓您細分使用者的裝置使用量。 <ul><li>[**顯示名稱**] 是使用者的顯示名稱。 您可以按一下顯示名稱, 移至 Microsoft 團隊系統管理中心的 [使用者設定] 頁面。 </li><li>如果使用者是在 Windows 電腦上的小組桌面用戶端中使用中, 則會選取 [ **Windows** ]。</li><li>如果使用者在 macOS 電腦上的小組桌面用戶端中處於作用中, 則會選取**Mac** 。 </li> <li>如果使用者在 iOS 的 [小組行動用戶端] 上是作用中的, 就會選取**ios** 。</li><li>如果使用者在 Android 版團隊行動用戶端上是作用中的, 則會選取 [ **android 手機**]。 <li>[**上一個活動**] 是使用者參與團隊活動的最後一個日期 (UTC)。</li> </ul> 請注意, 如果使用者帳戶已不存在於 Azure AD 中, 則使用者名稱會在資料表中顯示為 "--"。 <br><br>若要在表格中查看您想要的資訊, 請務必將資料行新增至資料表。 |
|**500**   |選取 [**編輯欄**] 以新增或移除表格中的欄。 |
|**6**   |您可以將報表匯出為 CSV 檔案, 以便進行離線分析。 按一下 [**匯出至 Excel**], 然後在 [**下載**] 索引標籤上, 按一下 [**下載**] 以在準備好時下載報告。<br><br>![[下載] 索引標籤上顯示匯出報表的螢幕擷取畫面](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>相關主題

- [團隊分析和報告](teams-reporting-reference.md)