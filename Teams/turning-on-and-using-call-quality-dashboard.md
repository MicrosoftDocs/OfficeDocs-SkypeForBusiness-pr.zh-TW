---
title: '設定通話品質儀表板 (CQD) '
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 瞭解如何開啟和使用 [通話品質] 儀表板，以及取得通話品質的摘要報告。
ms.openlocfilehash: cf4c6d56e4fa646495383b4998e80789d9cdaca67b9cc35d07f613cda4e70b85
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300449"
---
# <a name="how-to-set-up-call-quality-dashboard"></a>如何設定通話品質儀表板

[https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)使用您的系統管理員認證)  (登入，開啟 Microsoft 通話品質儀表板 (CQD) 。 或是移至 Teams 系統管理中心，然後選取 [**通話品質儀表板**]。 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Teams 系統管理中心中通話品質儀表板按鈕的螢幕擷取畫面":::

在開啟的頁面上，按一下 [登 **入**]，然後輸入您的全域系統管理員帳戶或 Microsoft Teams 系統管理員帳戶資訊。 在您第一次登入之後，CQD 將開始收集和處理資料。 請記住，可能需要一或多個小時的時間，才能處理足夠的資料，以在報告中顯示有意義的結果。

CQD 顯示通話和會議品質、組織內層級、Microsoft Teams 商務用 Skype 線上及商務用 Skype Server 2019。 

> [!IMPORTANT]
> 若要使用 CQD 與商務用 Skype Server 2019，您必須[設定來電資料連線器](/skypeforbusiness/hybrid/configure-call-data-connector)。 開始之前，請參閱 [規劃通話資料連線器](/skypeforbusiness/hybrid/plan-call-data-connector) 。


## <a name="assign-admin-roles-for-access-to-cqd"></a>指派系統管理員角色以存取 CQD

指派 [角色](/microsoft-365/admin/add-users/about-admin-roles) ，將 CQD 存取至需要使用該角色的人員。

如果您想要非系統管理員使用者 (例如「支援工程師」和「服務台」的工程師) 使用通話品質儀表板，您可以將下列其中一個角色指派給這些使用者，以便存取 CQD。 


|&nbsp;  |檢視報告  |View EUII 欄位  |建立報表  |建立資料的 Upload  |
|---------|:-------:|:-------:|:-------:|:-------:|
|全域系統管理員     |是         |是         |是         |是         |
|Teams管理員     |是         |是         |是         |是         |
|Teams 通訊系統管理員     |是         |是         |是         |是         |
|Teams 通訊支援工程師     |是         |是         |是         |否         |
|Teams 通訊支援專員     |是         |否         |是         |否         |
|商務用 Skype 系統管理員     |是         |是         |是         |是         |
|全域讀取者 |是         |是         |是         |否         |
|報告讀取器<sup>1</sup>     |是         |否         |是         |否         |

<sup>1</sup>除了讀取 CQD 報告之外，報告讀取器也可以查看系統管理中心內所有的[活動報告](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)，以及[Microsoft 365 採用內容套件](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)中的任何報告。

> [!NOTE]
> 如果您未看到 [EUII (使用者辨識的身分識別資訊) ](CQD-data-and-reports.md#euii-data) ，且您有其中一個允許查看此資訊的角色，請記住 CQD 只會持續 EUII 的28天。 會刪除超過28天的任何專案。

如需這些角色的相關資訊，請參閱[關於 Office 365 系統管理員角色](/office365/admin/add-users/about-admin-roles)。


在您第一次登入之後，CQD 將開始收集和處理資料。 到12月2019，您仍然可以存取舊版的 CQD (cqd.lync.com) ，不過舊版入口網站提供您最新 CQD (cqd.teams.microsoft.com) 的連結。 最後，舊版本的 CQD 將解除委任。 從2020年7月1日起，舊版本的 CQD 會從最新的 CQD 存取資料。


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>從先前版本的 CQD 遷移資料和報表

> [!IMPORTANT]
> 從2020年7月1日起，您就無法再從舊的 CQD (中，遷移資料和報表 https://CQD.lync.com) 。 



## <a name="use-power-bi-to-analyze-cqd-data"></a>使用 Power BI 分析 CQD 資料

2020年1月的新功能：[下載 CQD 的 Power BI 查詢範本](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 可自訂的 Power BI 範本，可供您用來分析和報告您的 CQD 資料。

Read[使用 Power BI 來分析 CQD 資料](CQD-Power-BI-query-templates.md)，以深入瞭解。


## <a name="related-topics"></a>相關主題

[改善及監視 Teams 的通話品質](monitor-call-quality-qos.md)

[什麼是 CQD？](CQD-what-is-call-quality-dashboard.md)

[上傳租用戶和建築物資料](CQD-upload-tenant-building-data.md)

[CQD 資料和報告](CQD-data-and-reports.md)

[使用 CQD 管理通話和會議品質](quality-of-experience-review-guide.md)

[CQD 中可用的維度和量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的串流分類](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI 分析 CQD 資料](CQD-Power-BI-query-templates.md)
