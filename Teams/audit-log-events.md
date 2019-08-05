---
title: 在 [審核記錄] 中搜尋 Microsoft 團隊中的事件
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: 瞭解如何從 Office 365 審核記錄中檢索 Microsoft 團隊資料。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 90645a7c2ffde142bdda80855b613877afc2f19e
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2019
ms.locfileid: "36183636"
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a>在 [審核記錄] 中搜尋 Microsoft 團隊中的事件
==================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

審核記錄可協助您調查跨 Office 365 服務的特定活動。 針對團隊而言, 以下是一些經過審核的活動:

-   小組建立

-   小組刪除

-   已新增頻道

-   已變更設定

若要查看在 Office 365 中審核之活動的完整清單, 請閱讀[在 office 365 安全性 & 合規性中心搜尋審核記錄](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c)。

## <a name="turn-on-auditing-in-teams"></a>在團隊中開啟審核

您必須先在**安全性 & 合規性中心**(https://protection.office.com)) 中開啟審核, 才能查看審核資料。 如需有關開啟審核的協助, 請參閱[開啟或關閉 Office 365 審核記錄搜尋](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。


> [!IMPORTANT]
> 審核資料只能從您開啟 [審計] 的位置使用。



## <a name="retrieve-teams-data-from-the-audit-log"></a>從審核記錄中取得團隊資料

1.  若要取得審核記錄, 請移至[安全性 & 合規性中心](https://go.microsoft.com/fwlink/?linkid=855775)。 在 [**搜尋 & 調查**] 底下, 選取 [**審核記錄搜尋**]。![[審計記錄搜尋] 頁面的螢幕擷取畫面](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  使用 [**搜尋**] 篩選您想要審核的活動、日期和使用者。

3.  將結果匯出至 Excel 以進行進一步分析。


> [!IMPORTANT]
> 審核資料只有在已開啟審核的情況下, 才會顯示在審核記錄中。

## <a name="video-techtip-using-audit-log-search-in-teams"></a>影片: TechTip: 在團隊中使用審核記錄搜尋

加入 Ansuman Acharya (一種小組的程式管理員), 他示範如何在 Office 365 安全 & 規範中心中執行審核記錄搜尋小組。 


> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]






