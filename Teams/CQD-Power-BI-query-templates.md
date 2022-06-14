---
title: 使用 Power BI 分析 Microsoft Teams 的 CQD 資料
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
ms.localizationpriority: medium
description: 使用 Power BI 來分析 Microsoft Teams 的 CQD 資料。
ms.openlocfilehash: 7d951c0e96f98c343a388e536311bf00890e5302
ms.sourcegitcommit: e38776625a3623216b0d5f092fffaff67519b1a6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/13/2022
ms.locfileid: "66056953"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>使用 Power BI 分析 Microsoft Teams 的 CQD 資料

2020 年 1 月的新功能：[下載 Power BI CQD 查詢範本](https://www.microsoft.com/download/details.aspx?id=102291)。 可自訂Power BI範本，可用來分析及報告您的 CQD 資料。

針對 Teams 中的通話品質儀表板 (CQD) 報告，如果您想要使用 Power BI 查詢和報告資料，請下載我們的 CQD Power BI範本。 當您在 Power BI 中開啟範本時，系統會提示您使用 CQD 系統管理員認證登入。 您可以自訂這些查詢範本，並將它們發佈給貴組織中具有Power BI授權和 CQD 系統管理員許可權的任何人。

使用這些 PBIT 檔案之前，您必須使用 [下載](https://www.microsoft.com/download/details.aspx?id=102291)中包含的 *MicrosoftCallQuality.pqx* 檔案 [來安裝適用于 Microsoft CQD 的 Power BI Connector](CQD-Power-BI-connector.md)。 

請確定您擁有正確的[CQD 存取角色](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)來存取Power BI報告。 

|Pbit |描述 |
|:----------|:---------|
|<strong> (新！) </strong> QER.pbit     |  QER) 範本 (體驗品質報告可讓客戶在升級之前，主動找出影響Teams會議和通話體驗的問題。 同時提供報告可讓系統管理員快速回應向上呈報的問題，並協助回答「會議期間發生了什麼事？」問題。  此範本提供下列報告：</p><li>搜尋 – 可透過會議 URL、會議 ID、子網或 UPN 進行搜尋。</li><li>會議健康情況詳細資料 – 單一會議的詳細計量。</li><li>使用者健康情況詳細資料 – 單一使用者的詳細計量。</li><li>媒體健康情況 – 主要健康情況指標 (KHI) 整體租使用者會議和通話健康情況的整體概觀。</li><li>媒體設定 – 分析媒體設定失敗。</li><li>媒體可靠性 – 分析媒體可靠性問題。</li><li>音訊/視訊/共用健康情況 – 檢閱中層 KHI 以瞭解音訊、視訊或共用健康情況。</li><li>音訊/視訊/共用健康情況詳細資料 – 檢閱音訊、視訊或共用健康情況的詳細計量。</li><li>VPN – 檢閱 VPN 對會議健康情況的影響。  (預估或對應 VPN) </li><li>前 10 名報告： 識別租使用者中的問題區域。</li><li>Dailies – 檢閱 KHI 的每日報告。</li><li>使用方式 – 一般會議和通話使用方式。</li><li>使用者意見反應 – 檢閱使用者問卷意見反應，也稱為評分我的通話。</li><li>傳輸 – 識別封鎖 UDP 的網路。</li><li>裝置 – 檢閱裝置的影響。</li><li>用戶端 - 檢閱用戶端焦點指派。</li><li>建築物資料 – 在 CQD 中檢閱建築物資料檔案。</li><li>PSTN 健康情況和使用者詳細資料 – 兩個報告提供高階摘要，以及 PSTN 型通話的個別使用者健康情況。</li><li>網路計量 ： 顯示抖動、封包遺失和延遲之原始網路計量詳細資料的兩個報表。</li>  |
|CQD Teams自動語音應答&通話佇列歷史報告.pbit     |  此範本提供下列三種報告：</p><li>自動語音應答： 顯示自動語音應答中來電的分析資料。</li><li>通話佇列 ： 顯示來電進入通話佇列的分析資料。</li><li>專員時間軸： 顯示代理程式在通話佇列通話中作用中的時程表檢視。</li><br>若要深入瞭解，請參閱[自動語音應答&通話佇列歷史報告。](aa-cq-cqd-historical-reports.md) |
|CQD Helpdesk Report.pbit     |整合建築物和 EUII 資料，此報告的設計目的是要讓您從單一使用者向上切入，以找出該使用者通話品質不佳的起層根 (例如，使用者位於發生網路問題的建築物中，) 。 |
|CQD 位置增強型 Report.pbit     | 重新想像 CQD SPD 位置報告。 包含 9 個報告，提供通話品質、建築物 WiFi、可靠性，以及 [我的通話評分] (RMC) 資訊，以及透過建置或由使用者進行的其他切入。 請務必上傳建築物資料，以最大化您的報告體驗。 |
|CQD 行動裝置報表.pbit     | 提供針對行動裝置使用者特別調整的深入解析，包括通話品質、可靠性和通話評分。 iOS)  (Android檢視行動網路、WiFi 網路和行動裝置作業系統報告。 |
|CQD PSTN 直接路由報表.pbit     |針對透過直接路由的 PSTN 通話提供特定的深入解析。 若要深入瞭解，請閱讀 [使用 CQD PSTN 直接路由報告](CQD-PSTN-report.md)。 |
|CQD 摘要報表.pbit     |更好的視覺效果、改良的簡報、增加的資訊密度，以及滾動日期。 這些報告可讓您更容易識別異常值。 使用簡單易用的互動式地圖，依位置切入通話品質。 九個新報告：</p>- 整體品質<br>- 整體可靠性<br>- RMC ([我的通話評分]) 整體<br>- 會議品質<br>- P2P 品質<br>- 會議可靠性<br>- P2P 可靠性<br>- 會議 RMC<br>- P2P RMC         |
|CQD Teams使用量報表.pbit     | 顯示貴組織中的使用者如何使用Teams和使用量。 請務必上傳建築物資料，以最大化您的報告體驗。 若要深入瞭解，請閱讀[使用 CQD Power BI報表以檢視Microsoft Teams使用率](CQD-teams-utilization-report.md)。 |
|CQD 使用者意見反應 (為我的通話評分) Report.pbit     | 顯示 [我的通話評分] 資料，讓您可以輕鬆地用來協助組織支援通話。 與逐字清單交互參照，以識別使用者的教育機會。 |

> [!TIP]
> 設定 CQD 資料的Power BI報表之後，請將它們新增為頻道的索引標籤。 在頻道中選 **+** 取後，選 **取 [Power BI**]，然後尋找您的報告。 若要深入瞭解，請閱讀內[嵌報表與Teams Power BI索引標籤](/power-bi/service-embed-report-microsoft-teams)。 請記住，只有擁有Power BI授權和 CQD 系統管理員認證的人員才能存取這些報告。

## <a name="related-topics"></a>相關主題

[通話品質儀表板中提供的維度和量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通話品質儀表板中的資料流分類](stream-classification-in-call-quality-dashboard.md)

[設定商務用 Skype 通話分析](set-up-call-analytics.md)

[使用通話分析來疑難排解不良通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通話分析和通話品質儀表板](./monitor-call-quality-qos.md)
