---
title: 什麼是通話品質儀表板 (CQD) ？
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
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
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 瞭解通話品質儀表板 (CQD) ，以及如何使用它來查看 Microsoft Teams 中的會議和通話品質報告。
ms.openlocfilehash: 3bc3c9dcd83e4ff95a07fbffb6f07da39d254cde
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790068"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>什麼是通話品質儀表板 (CQD) ？

Microsoft 通話品質儀表板 (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) 顯示 Microsoft Teams、商務用 Skype Online 和 商務用 Skype Server 2019 的 **全組織通話** 和會議品質。 

  
最新版的 CQD 功能 [為接近即時 (NRT) 資料摘要](CQD-data-and-reports.md)，這表示通話結束後的 30 分鐘內，CQD 會提供通話記錄。

無論 CQD 包含 [使用者標識資訊 (EUII) 資料](CQD-data-and-reports.md#euii-data)，其管理方式都與 [整個 Microsoft 365 中的 EUII](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)相同。

CQD 是專為協助 Teams 系統管理員、商務用 Skype系統管理員和網路工程師監控整個組織層級的通話和會議品質所設計。 您將使用 CQD 來協助您 **優化網路** 以提升效能品質。 當您需要調查 **特定使用者** 的通話和會議資訊時，請將 CQD 資料與每個使用者 [的通話分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)搭配使用。

例如，使用 CQD，您可以判斷使用者的通話品質不佳 (您使用個別使用者通話分析) 觀察到的，是因為網路問題也會影響許多其他使用者。 CQD 同時會擷取使用 Teams 或商務用 Skype的個別通話體驗和通話整體品質。 透過 CQD，整體模式可能會變得明顯，因此網路工程師可以對通話品質做出明智的評估。 CQD 提供通話品質指派的報告，可讓您深入瞭解整體通話品質、伺服器-用戶端串流、用戶端-用戶端串流和語音品質 [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)。 
  
![通話品質儀表板的螢幕擷取畫面。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

在 CQD 中，我們鼓勵您上傳建築物和端點資訊，這可讓您使用Location-Enhanced報告來分析使用者建築物內的通話品質和可靠性。 您可以評估資料，判斷問題是否與單一使用者隔離，或影響較大的使用者區段。 若要在 CQD 中開啟建置或端點特定檢視，系統管理員必須在 CQD **租使用者資料上傳** 頁面上 [傳建築物或端點資訊](CQD-upload-tenant-building-data.md)。

![通話品質儀表板Location-Enhanced報告的螢幕擷取畫面。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

請勿錯過我們的 [「管理通話和會議品質](quality-of-experience-review-guide.md) 」文章，本文提供深入指導方針給負責管理 Teams 中服務品質的 Teams 系統管理員或支援工程師。


## <a name="use-power-bi-to-analyze-cqd-data"></a>使用 Power BI 分析 CQD 資料

2020 年 1 月的新功能： [下載適用于 CQD 的 Power BI 查詢範本](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 您可以使用可自訂的 Power BI 範本來分析及報告 CQD 資料。

若要深入瞭解，請參閱 [使用 Power BI 來分析 CQD 資料](CQD-Power-BI-query-templates.md) 。



## <a name="related-topics"></a>相關主題

[改善及監控 Teams 的通話品質](monitor-call-quality-qos.md)

[設定呼叫品質儀表板 (CQD) ](turning-on-and-using-call-quality-dashboard.md)

[上傳租使用者和建築物資料](CQD-upload-tenant-building-data.md)

[CQD 資料和報表](CQD-data-and-reports.md)

[使用 CQD 管理通話和會議品質](quality-of-experience-review-guide.md)

[CQD 中提供的維度和量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的串流分類](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI 分析 CQD 資料](CQD-Power-BI-query-templates.md)


[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)
