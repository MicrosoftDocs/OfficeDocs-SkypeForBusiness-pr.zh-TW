---
title: 使用 Power BI 分析 CQD 資料Microsoft Teams
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
description: 使用 Power BI 來分析 CQD 資料Microsoft Teams。
ms.openlocfilehash: 5ef98f75854cb4a255bf3f01aeb32de66c059b76
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096519"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>使用 Power BI 分析 CQD 資料Microsoft Teams

2020 年 1[月新增：下載 Power BI CQD 的查詢範本](https://www.microsoft.com/download/details.aspx?id=102291)。 您可以Power BI自訂範本，以分析及報告您的 CQD 資料。

針對 (中 (CQD) 報表，如果您想要使用 Teams Power BI 查詢及報告資料，請下載我們的 CQD Power BI範本。 當您在 Power BI 中開啟範本時，系統會提示您以 CQD 系統管理員認證進行登錄。 您可以自訂這些查詢範本，並將這些範本發佈給組織中擁有授權和 CQD Power BI許可權的任何人。

使用這些 PBIT 檔案之前，您必須使用下載中包含的 *MicrosoftCallQuality.pqx* 檔案安裝 [Microsoft CQD](CQD-Power-BI-connector.md)的 Power BI [Connector。](https://www.microsoft.com/download/details.aspx?id=102291) 

請確定您擁有正確的[CQD 存取角色](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)，以存取Power BI報表。 

|  |  |
|---------|---------|
|<strong> (新增！) </strong>CQD Teams自動&通話佇列歷史報告.pbit     |  此範本提供下列三個報告：</p><li>自動助理 – 顯示自動電話機來電的分析。</li><li>通話佇列 – 顯示來電佇列來電的分析。</li><li>代理人時程表 – 顯示在通話佇列通話中作用中的代理人時程表視圖。</li><br>若要深入瞭解，請參閱 [自動&通話佇列歷史報告](aa-cq-cqd-historical-reports.md)。        |
|CQD Helpdesk Report.pbit     |整合建築物和 EUII 資料，此報表的設計目的是讓您從單一使用者向上切取，找出造成該使用者通話品質不佳的上行原因 (例如，使用者位於發生網路問題的建築物中) 。         |
|CQD 位置增強型 Report.pbit     | 重新想像 CQD SPD 位置報告。 包含 9 個報告，提供通話品質、建建 WiFi、可靠性，以及將我的通話 (RMC) 進一步根據建築物或使用者提供的資訊。  請確定您上傳建築物資料，以最大化您的報告體驗。        |
|CQD Mobile Device Report.pbit     | 提供專為行動裝置使用者提供的深入資訊，包括通話品質、可靠性，以及我的通話評分。 在 Android、iOS (中查看行動網路、WiFi 網路和) 。        |
|CQD PSTN 直接路由報表.pbit     |提供透過直接路由進行 PSTN 通話的特定深入資訊。 若要深入瞭解，請參閱 [使用 CQD PSTN 直接路由報告](CQD-PSTN-report.md)。         |
|CQD 摘要報表.pbit     |更好的視覺效果、改良的簡報、增加的資訊密度和滾動日期。 這些報告可更輕鬆地識別識別碼異常值。 使用便於使用的互動式地圖，根據位置深入瞭解通話品質。 9 個新報表：</p>- 整體品質<br>- 整體可靠性<br>- RMC (將我的通話) 整體<br>- 會議品質<br>- P2P 品質<br>- 會議可靠性<br>- P2P 可靠性<br>- 會議 RMC<br>- P2P RMC         |
|<strong> (新增！) </strong>CQD Teams使用方式報表.pbit     | 顯示貴組織中使用者如何使用Teams以及使用數量。 請確定您上傳建築物資料，以最大化您的報告體驗。 若要深入瞭解，請參閱[使用 CQD Power BI報表來Microsoft Teams使用方式](CQD-teams-utilization-report.md)。        |
|CQD 使用者意見 (將我的通話) Report.pbit     | 顯示評分我的通話資料，方便您輕鬆協助支援貴組織的通話。 使用逐字交互參照，找出使用者教育機會。        |

> [!TIP]
> 設定好 CQD 資料Power BI報表之後，將它們新增為頻道的一個定位停駐點。 在頻道 **+** 中選取後，選取Power BI，然後尋找報表。 若要深入瞭解，請參閱[內嵌報表，並Power BI的 Teams。](/power-bi/service-embed-report-microsoft-teams) 請記住，只有擁有授權Power BI CQD 系統管理員認證的人才能存取這些報告。


## <a name="related-topics"></a>相關主題

[通話品質儀表板中提供的維度和量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通話品質儀表板中的資料流分類](stream-classification-in-call-quality-dashboard.md)

[設定商務用 Skype 通話分析](set-up-call-analytics.md)

[使用通話分析來疑難排解不良通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通話分析和通話品質儀表板](./monitor-call-quality-qos.md)
