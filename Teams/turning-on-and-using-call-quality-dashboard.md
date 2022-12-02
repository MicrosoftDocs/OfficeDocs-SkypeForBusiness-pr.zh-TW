---
title: '設定 CQD (呼叫品質儀表板) '
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 瞭解如何開啟和使用通話品質儀表板，以及取得通話品質的摘要報告。
ms.openlocfilehash: 5f3b9fbb42199892136569ac179907b18da4e460
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2022
ms.locfileid: "69245656"
---
# <a name="set-up-the-call-quality-dashboard"></a>設定通話品質儀表板

在 (使用您的系統管理員認證) 登入時，開啟 Microsoft 通話品質儀表板 (CQD [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)) 。 或移至 Teams 系統管理中心，然後選 **取 [分析&報告**  >  **通話品質儀表板]**。

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Teams 系統管理中心中 [通話品質儀表板] 按鈕的螢幕擷取畫面。":::

在開啟的頁面上，按一下 [**登入**]，然後輸入您的全域系統管理員帳戶或Microsoft Teams 系統管理員帳戶資訊。 第一次登入之後，CQD 將會開始收集和處理資料。 請記住，處理足夠的資料可能需要一或多個小時，才能在報告中顯示有意義的結果。

CQD 會以全組織層級顯示 Microsoft Teams、商務用 Skype Online 和 商務用 Skype Server 2019 的通話和會議品質。 

> [!IMPORTANT]
> 若要搭配 商務用 Skype Server 2019 使用 CQD，您必須設定[通話資料連線器](/skypeforbusiness/hybrid/configure-call-data-connector)。 請參閱 [開始之前規劃通話資料連線器](/skypeforbusiness/hybrid/plan-call-data-connector) 。


## <a name="assign-admin-roles-for-access-to-cqd"></a>指派系統管理員角色以存取 CQD

將存取 CQD [的角色](/microsoft-365/admin/add-users/about-admin-roles) 指派給需要使用 CQD 的人員。

如果您希望非系統管理員使用者 (例如支援工程師和技術服務專員，) 使用通話品質儀表板，您可以指派下列其中一個角色給這些使用者，以便存取 CQD。 


|&nbsp;  |檢視報表  |檢視 EUII 欄位  |建立報表  |上傳建築物資料  |
|---------|:-------:|:-------:|:-------:|:-------:|
|全域系統管理員     |是         |是         |是         |是         |
|Teams 系統管理員     |是         |是         |是         |是         |
|Teams 通訊系統管理員     |是         |是         |是         |是         |
|Teams 通訊支援工程師     |是         |是         |是         |否         |
|Teams 通訊支援專家     |是         |否         |是         |否         |
|商務用 Skype系統管理員]     |是         |是         |是         |是         |
|全域閱讀程式 |是         |是         |是         |否         |
|報表閱讀程式<sup>1</sup>     |是         |否         |是         |否         |

<sup>1</sup>除了閱讀 CQD 報告，報表閱讀程式還可以檢視系統管理中心的所有[活動報告](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)，以及來自[Microsoft 365 採用內容套件](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)的任何報告。

> [!NOTE]
> 如果您沒有在 [) 看到 EUII (使用者標識資訊 ](CQD-data-and-reports.md#euii-data) ，而且您擁有其中一個允許查看此資訊的角色，請記住，CQD 只會保留 EUII 28 天。 超過 28 天的任何內容都會刪除。

如需這些角色的詳細資訊，請參[閱關於Office 365系統管理員角色](/office365/admin/add-users/about-admin-roles)。


第一次登入之後，CQD 將會開始收集和處理資料。

## <a name="use-power-bi-to-analyze-cqd-data"></a>使用 Power BI 分析 CQD 資料

2020 年 1 月的新功能： [下載適用于 CQD 的 Power BI 查詢範本](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 您可以使用可自訂的 Power BI 範本來分析及報告 CQD 資料。

若要深入瞭解，請參閱 [使用 Power BI 來分析 CQD 資料](CQD-Power-BI-query-templates.md) 。

## <a name="related-topics"></a>相關主題

[改善及監控 Teams 的通話品質](monitor-call-quality-qos.md)

[什麼是 CQD？](CQD-what-is-call-quality-dashboard.md)

[上傳租使用者和建築物資料](CQD-upload-tenant-building-data.md)

[CQD 資料和報表](CQD-data-and-reports.md)

[使用 CQD 管理通話和會議品質](quality-of-experience-review-guide.md)

[CQD 中提供的維度和量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的串流分類](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI 分析 CQD 資料](CQD-Power-BI-query-templates.md)
