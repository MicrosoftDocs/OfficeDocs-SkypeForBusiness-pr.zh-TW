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
description: 瞭解如何開啟和使用通話品質儀表板，並取得通話品質的摘要報告。
ms.openlocfilehash: 60363ed86e4e073b7ca5a752261ac806188900b1
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2021
ms.locfileid: "50112839"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>設定通話品質儀表板 (CQD) 

開啟 Microsoft 通話品質儀表板 (CQD) 在 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (使用您的管理員認證登入) 。 或移至 [團隊管理中心]，然後選取 [ **通話品質儀表板**]。 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="[團隊管理中心] 中 [通話品質儀表板] 按鈕的螢幕擷取畫面":::

在開啟的頁面上，按一下 [登 **入** ]，然後輸入您的全域系統管理員帳戶或 Microsoft 團隊服務系統管理員帳戶資訊。 第一次登入時，CQD 會開始收集及處理資料。 請記住，可能需要一或幾個小時的時間來處理足夠的資料，才能在報表中顯示有意義的結果。

CQD 會顯示通話與會議品質，在組織範圍中，針對 Microsoft 團隊、商務用 Skype Online 及商務用 Skype Server 2019。 

> [!IMPORTANT]
> 若要在商務用 Skype Server 2019 中使用 CQD，您必須 [設定 [呼叫資料連線器](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector)]。 請參閱 [規劃通話資料連線器](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) ，然後再開始進行。


## <a name="assign-admin-roles-for-access-to-cqd"></a>指派管理員角色來存取 CQD

指派 [角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) ，以存取 CQD 給需要使用的人員。

如果您想要非系統管理員的使用者 (例如支援工程師和支援者代理) 使用 [通話品質儀表板]，您可以為這些使用者指派下列其中一個角色，提供 CQD 的存取權。 


|  |查看報表  |[查看 EUII] 欄位  |建立報表  |上傳資料  |
|---------|:-------:|:-------:|:-------:|:-------:|
|全域系統管理員     |是         |是         |是         |是         |
|Teams 服務管理員     |是         |是         |是         |是         |
|Teams 通訊系統管理員     |是         |是         |是         |是         |
|Teams 通訊支援工程師     |是         |是         |是         |否         |
|團隊溝通支援專家     |是         |否         |是         |否         |
|商務用 Skype 系統管理員     |是         |是         |是         |是         |
|全域閱讀程式 |是         |是         |是         |否         |
|報告讀取器<sup>1</sup>     |是         |否         |是         |否         |

<sup>1</sup> 除了讀取 CQD 報表之外，報表閱讀者還可以查看系統管理中心的所有 [活動報告](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) ，以及 [Microsoft 365 採用內容套件](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)中的所有報告。

> [!NOTE]
> 如果您沒有看到 [EUII (使用者可辨識的資訊) ](CQD-data-and-reports.md#euii-data) ，且您擁有允許其查看這項資訊的角色，請記住 CQD 只能在28天內保留 EUII。 已刪除超過28天的任何專案。

如需有關這些角色的詳細資訊，請參閱 [關於 Office 365 系統管理員角色](/office365/admin/add-users/about-admin-roles)。


第一次登入時，CQD 會開始收集及處理資料。 從2019年12月之後，您仍然可以存取舊版的 CQD (cqd.lync.com) ，不過舊版入口網站提供了最新 CQD (cqd.teams.microsoft.com) 的連結。 最後，將會解除舊版的 CQD。 從2020年7月1日起，較舊版本的 CQD 會存取最新 CQD 的資料。


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>從舊版 CQD 遷移資料和報表

> [!IMPORTANT]
> 從2020年7月1日起，您將無法再從舊的 CQD (中開始建立資料和報表 https://CQD.lync.com) 。 



## <a name="use-power-bi-to-analyze-cqd-data"></a>使用 Power BI 來分析 CQD 資料

2020年1月 [的新功能：下載 POWER BI 查詢範本以進行 CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 可自訂的 Power BI 範本，您可以用來分析及報告您的 CQD 資料。

已閱讀 [ [使用 POWER BI 分析 CQD 資料](CQD-Power-BI-query-templates.md) ] 以深入瞭解。


## <a name="related-topics"></a>相關主題

[改善及監視團隊的通話品質](monitor-call-quality-qos.md)

[什麼是 CQD？](CQD-what-is-call-quality-dashboard.md)

[上傳租使用者及組建資料](CQD-upload-tenant-building-data.md)

[CQD 資料和報表](CQD-data-and-reports.md)

[使用 CQD 管理通話與會議品質](quality-of-experience-review-guide.md)

[CQD 中可用的維度與量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的資料流程分類](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI 來分析 CQD 資料](CQD-Power-BI-query-templates.md)
