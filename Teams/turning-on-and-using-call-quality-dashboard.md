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
description: 瞭解如何開啟並使用通話品質儀表板，並取得通話品質摘要報告。
ms.openlocfilehash: 2d671de0e2ddc5d4c2a4e321cf90e2e2f0dbe770
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162700"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>設定通話品質儀表板 (CQD) 

使用系統管理員認證 (在 CQD) 開啟 microsoft 通話品質儀表板 (以您的系統管理員認證 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)) 。 或前往 Teams 系統管理中心，然後選取通話 **品質儀表板**。 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Teams 系統管理中心的通話品質儀表板按鈕螢幕擷取畫面":::

在開啟的頁面上，按一下 [ **登錄** 並輸入您的全域系統管理員帳戶或 Microsoft Teams 服務系統管理員帳戶資訊。 在您第一次登錄之後，CQD 會開始收集和處理資料。 請記住，可能需要一或多個小時處理足夠的資料，才能在報告中顯示有意義的結果。

CQD 在全組織層級顯示 Microsoft Teams、商務用 Skype Online 和商務用 Skype Server 2019 的通話和會議品質。 

> [!IMPORTANT]
> 若要在商務用 Skype Server 2019 中使用 CQD，您必須設定 [通話資料連線器](/skypeforbusiness/hybrid/configure-call-data-connector)。 在 [啟動前，請參閱規劃通話](/skypeforbusiness/hybrid/plan-call-data-connector) 資料連線器。


## <a name="assign-admin-roles-for-access-to-cqd"></a>指派系統管理員角色以存取 CQD

將 [存取](/microsoft-365/admin/add-users/about-admin-roles) CQD 的角色指派給需要使用該角色的人。

如果您希望非系統管理員使用者 (例如支援工程師和技術支援人員) 使用通話品質儀表板，您可以指派下列其中一個角色來存取 CQD。 


|  |查看報表  |查看 EUII 欄位  |建立報表  |上傳建築物資料  |
|---------|:-------:|:-------:|:-------:|:-------:|
|全域系統管理員     |是         |是         |是         |是         |
|Teams 服務管理員     |是         |是         |是         |是         |
|Teams 通訊系統管理員     |是         |是         |是         |是         |
|Teams 通訊支援工程師     |是         |是         |是         |否         |
|Teams Communications 支援專員     |是         |否         |是         |否         |
|商務用 Skype 系統管理員     |是         |是         |是         |是         |
|全域閱讀程式 |是         |是         |是         |否         |
|報表閱讀<sup>程式 1</sup>     |是         |否         |是         |否         |

<sup>1</sup>除了閱讀 CQD 報告之外，報表閱讀程式還可以查看[](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)系統管理中心的所有活動報告，以及 Microsoft [365 採用內容](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)套件的任何報告。

> [!NOTE]
> 如果您沒有看到 [EUII (](CQD-data-and-reports.md#euii-data) 使用者識別資訊) 且您擁有允許查看此資訊的其中一個角色，請記住，CQD 只會讓 EUII 保留 28 天。 任何超過 28 天都將會刪除。

有關這些角色的資訊，請參閱關於 [Office 365 系統管理員角色](/office365/admin/add-users/about-admin-roles)。


在您第一次登錄之後，CQD 會開始收集和處理資料。 自 2019 年 12 月起，您仍可存取舊版 CQD (cqd.lync.com) ，雖然舊版入口網站提供您最新 CQD (cqd.teams.microsoft.com) 。 最後，較舊版本的 CQD 將會解除授權。 自 2020 年 7 月 1 日起，舊版 CQD 會存取最新 CQD 的資料。


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>從先前版本的 CQD 遷移建築物資料和報表

> [!IMPORTANT]
> 自 2020 年 7 月 1 日起，您無法再從舊的 CQD 資料庫移轉建築物資料 https://CQD.lync.com) (。 



## <a name="use-power-bi-to-analyze-cqd-data"></a>使用 Power BI 分析 CQD 資料

2020 年 1 月新增： [下載 CQD 的 Power BI](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)查詢範本。 您可以使用可自訂的 Power BI 範本來分析及報告您的 CQD 資料。

請閱讀 [使用 Power BI 分析 CQD 資料](CQD-Power-BI-query-templates.md) 以深入瞭解。


## <a name="related-topics"></a>相關主題

[改善及監控 Teams 的通話品質](monitor-call-quality-qos.md)

[什麼是 CQD？](CQD-what-is-call-quality-dashboard.md)

[上傳租使用者和建築物資料](CQD-upload-tenant-building-data.md)

[CQD 資料和報表](CQD-data-and-reports.md)

[使用 CQD 管理通話和會議品質](quality-of-experience-review-guide.md)

[CQD 中可用的維度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的資料流程分類](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI 分析 CQD 資料](CQD-Power-BI-query-templates.md)