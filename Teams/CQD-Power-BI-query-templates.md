---
title: 使用 Power BI 來分析 Microsoft 團隊的 CQD 資料
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- remotework
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 使用 Power BI 來分析 Microsoft 團隊的 CQD 資料。
ms.openlocfilehash: 256b2264cef4b84dc4f9d9881c960d357cee28e5
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908642"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>使用 Power BI 來分析 Microsoft 團隊的 CQD 資料

2020年1月 [的新功能：下載 POWER BI 查詢範本以進行 CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 可自訂的 Power BI 範本，您可以用來分析及報告您的 CQD 資料。

如果您想要使用 Power BI 查詢及報告資料，請在 [通話品質儀表板] (CQD [團隊中) 報表]，然後下載我們的 CQD Power BI 範本。 當您在 Power BI 中開啟範本時，系統會提示您使用 CQD 管理員認證登入。 您可以自訂這些查詢範本，並將它們發佈給貴組織中擁有 Power BI 授權及 CQD 系統管理員許可權的任何人。

在您可以使用這些 PBIT 檔案之前，您必須使用 [下載](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)中包含的 *MicrosoftCallQuality Pqx* 檔案， [安裝 Microsoft CQD 的 Power BI 連接器](CQD-Power-BI-connector.md)。 

請確定您擁有正確的 [CQD 存取角色](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd) ，才能存取 Power BI 報表。 

|  |  |
|---------|---------|
|<strong> (New！ ) </strong> CQD 小組自動語音應答 & 通話佇列歷史報告。 pbit     |  此範本提供下列三筆報告：</p><li>自動語音應答-顯示進入自動語音應答之通話的分析。</li><li>通話佇列–顯示撥入通話佇列之通話的分析。</li><li>[替代時程表] –顯示通話佇列通話中正在使用中的代理程式的 [時程表] 視圖。</li><br>若要深入瞭解，請參閱 [使用 CQD POWER BI 報表查看自動語音應答，& 通話佇列中記錄報告](CQD-teams-aa-cq-historical-report.md)。        |
|CQD 支援人員報告。 pbit     |整合建立與 EUII 資料時，此報告的設計目的是讓您從單一使用者向上切入，以找出該使用者的通話品質差的上游根本原因，例如，使用者在遇到網路問題) 中的 (。         |
|CQD 位置增強的報表。 pbit     | 重新 imagining CQD 的 SPD 位置報告。 包括9個報告、提供通話品質、建立 WiFi、可靠性，以及使用其他 thrus （透過建立或由使用者）來評價我的通話 () RMC 資訊。  請確定您上傳的是組建資料，以最大化您的報表體驗。        |
|CQD 行動裝置報告。 pbit     | 提供專門針對行動裝置使用者進行調整的深入資訊，包括通話品質、可靠性及評級我的通話。 在 Android、iOS)  (查看行動網路、WiFi 網路及行動作業系統報告。        |
|CQD PSTN 直向路由報告。 pbit     |提供穿過直接路由的 PSTN 呼叫的深入見解。 若要深入瞭解，請 [使用 CQD PSTN Direct 路由報告](CQD-PSTN-report.md)進行閱讀。         |
|CQD 摘要報表。 pbit     |更好的視覺效果、改良的簡報、增加的資訊密度，以及滾動日期。 這些報告可讓識別碼的離群更容易。 使用便於使用的互動式地圖，透過位置深化通話品質。 9個新的報表：</p>整體品質<br>-整體可靠性<br>-RMC () 整體撥打通話費用<br>-會議品質<br>-P2P 品質<br>-會議可靠性<br>-P2P 可靠性<br>-會議 RMC<br>-P2P RMC         |
|<strong> (New！ ) </strong> CQD [團隊利用率] 報表。 pbit     | 顯示貴組織中的使用者如何使用團隊以及多少。 請確定您上傳的是組建資料，以最大化您的報表體驗。 若要深入瞭解，請參閱 [使用 CQD POWER BI 報表來查看 Microsoft 團隊的利用率](CQD-teams-utilization-report.md)。        |
|CQD [使用者意見反應] (將我的通話) 報告。 pbit     | 顯示使用您可以輕鬆地協助支援您組織通話的方式，為我的通話資料打分。 與 verbatims 進行交叉參照，以找出使用者的教育機會。        |

> [!TIP]
> 在您設定 Power BI 報表以取得 CQD 資料後，請將其新增為頻道的索引標籤。 選取頻道之後 **+** ，請選取 [ **Power BI** ]，然後尋找您的報表。 若要深入瞭解，請參閱 [使用 [POWER BI] 索引標籤針對團隊的內嵌報表](https://docs.microsoft.com/power-bi/service-embed-report-microsoft-teams)。 請記住，只有具備 Power BI 授權及 CQD 管理員認證的人員才能存取這些報告。


## <a name="related-topics"></a>相關主題

[通話品質儀表板中提供的維度和量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通話品質儀表板中的資料流分類](stream-classification-in-call-quality-dashboard.md)

[設定商務用 Skype 通話分析](set-up-call-analytics.md)

[使用通話分析來疑難排解不良通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通話分析和通話品質儀表板](difference-between-call-analytics-and-call-quality-dashboard.md)
 
