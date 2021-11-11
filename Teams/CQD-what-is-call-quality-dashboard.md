---
title: 什麼是通話品質儀表板 (CQD) ？
ms.author: serdars
author: SerdarSoysal
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
description: 瞭解 CQD (儀表板) ，以及如何使用它在 Microsoft Teams 中查看會議與通話品質Microsoft Teams。
ms.openlocfilehash: f87f8184b0417d04206d31780392f21dca387d10
ms.sourcegitcommit: 115e44f33fc7993f6eb1bc781f83eb02a506e29b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/11/2021
ms.locfileid: "60909554"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>什麼是通話品質儀表板 (CQD) ？

Microsoft 通話品質儀表板 (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) 顯示 2019 年Microsoft Teams、商務用 Skype Online 和 商務用 Skype Server 的通話和會議品質。 

  
最新版本的 CQD 具有接近即時 [的 (NRT) ](CQD-data-and-reports.md)資料摘要，這表示通話記錄可在通話結束的 30 分鐘內在 CQD 中提供。

無論 CQD 包含使用者標識資訊 ([EUII) 資料，](CQD-data-and-reports.md#euii-data)其管理方式與[EUII](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)在整個 Microsoft 365。

CQD 是專為協助Teams系統管理員商務用 Skype系統管理員和網路工程師監控全組織層級的通話和會議品質所設計。 您將使用 CQD 來協助 **優化** 您的網路，以提升品質。 當您需要查看特定使用者的通話和會議資訊時，請使用CQD 資料與每個使用者的通話[分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)。

例如，使用 CQD，您可以判斷使用者使用每個使用者通話分析 (所觀察到的通話品質不佳) 是因為網路問題也會影響到許多其他使用者。 CQD 會同時捕獲個別通話體驗，以及使用通話或通話Teams商務用 Skype。 有了 CQD，整體模式可能會變得明顯，因此網路工程師可以做出明智的通話品質評定。 CQD 提供通話品質度量報告，可深入瞭解整體通話品質、伺服器-用戶端資料流程、用戶端-用戶端資料流程和語音品質[SLA。](https://go.microsoft.com/fwlink/p/?linkid=846252) 
  
![通話品質儀表板的螢幕擷取畫面。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

在 CQD 中，我們鼓勵您上傳建築物和端點資訊，Location-Enhanced報表來分析使用者建築物內的通話品質和可靠性。 您可以評估資料，判斷問題是否與單一使用者隔離，或影響較大使用者區段。 若要在 CQD 中開啟建築物或端點特定視圖，系統管理員必須在 [](CQD-upload-tenant-building-data.md)CQD 租使用者資料頁面上傳建築物或 **端點Upload** 資訊。

![通話品質儀表板的 Location-Enhanced螢幕擷取畫面。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

請勿錯過我們的管理通話[](quality-of-experience-review-guide.md)和會議品質文章，本文為負責管理 Teams 服務品質的系統管理員或支援工程師提供深入Teams。


## <a name="use-power-bi-to-analyze-cqd-data"></a>使用 Power BI分析 CQD 資料

2020 年 1[月新增：下載 Power BI CQD 的查詢範本](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 您可以Power BI自訂範本，以分析及報告您的 CQD 資料。

請參閱[使用 Power BI分析 CQD 資料](CQD-Power-BI-query-templates.md)以深入瞭解。



## <a name="related-topics"></a>相關主題

[改善及監控通話品質Teams](monitor-call-quality-qos.md)

[設定通話品質儀表板 (CQD) ](turning-on-and-using-call-quality-dashboard.md)

[Upload租使用者和建築物資料](CQD-upload-tenant-building-data.md)

[CQD 資料和報表](CQD-data-and-reports.md)

[使用 CQD 管理通話和會議品質](quality-of-experience-review-guide.md)

[CQD 中可用的維度和度量](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的資料流程分類](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI分析 CQD 資料](CQD-Power-BI-query-templates.md)


[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)
