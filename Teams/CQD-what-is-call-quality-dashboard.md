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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 瞭解通話品質儀表板 (CQD) ，以及如何使用它在 Microsoft 團隊中查看會議和通話品質的報告。
ms.openlocfilehash: 9ba1956533887314a9ffa7ad994cbb4c81ffe103
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583482"
---
# <a name="what-is-call-quality-dashboard-cqd"></a><span data-ttu-id="12d56-103">什麼是通話品質儀表板 (CQD) ？</span><span class="sxs-lookup"><span data-stu-id="12d56-103">What is Call Quality Dashboard (CQD)?</span></span>

<span data-ttu-id="12d56-104">Microsoft 通話品質儀表板 (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) -顯示通話與會議品質，在**組織範圍內**、Microsoft 團隊、商務用 Skype Online 及商務用 skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="12d56-104">The Microsoft Call Quality Dashboard (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - shows call and meeting quality, at an **org-wide level**, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

  
<span data-ttu-id="12d56-105">最新版本的 CQD 功能是[近即時 (NRT) 資料](CQD-data-and-reports.md)摘要，這表示在通話結束後的30分鐘內，就能使用 CQD 的通話記錄。</span><span class="sxs-lookup"><span data-stu-id="12d56-105">The latest version of CQD features a [near-real-time (NRT) data feed](CQD-data-and-reports.md), which means that call records are available in CQD within 30 minutes of the end of a call.</span></span>

<span data-ttu-id="12d56-106">無論是 CQD 包含[使用者可識別資訊 (EUII) 資料](CQD-data-and-reports.md#euii-data)，其管理方式都與[Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)中的 EUII 一樣。</span><span class="sxs-lookup"><span data-stu-id="12d56-106">Wherever CQD includes [end-user identifiable information (EUII) data](CQD-data-and-reports.md#euii-data), it's managed in the same way as [EUII throughout Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="12d56-107">CQD 的設計目的是協助小組系統管理員、商務用 Skype 系統管理員，以及網路工程人員在組織範圍內監視通話與會議品質。</span><span class="sxs-lookup"><span data-stu-id="12d56-107">CQD is designed to help Teams admins, Skype for Business admins, and network engineers monitor call and meeting quality at an org-wide level.</span></span> <span data-ttu-id="12d56-108">您將會使用 CQD 來協助您**優化網路**，以提高效能品質。</span><span class="sxs-lookup"><span data-stu-id="12d56-108">You'll use CQD to help you **optimize your network** to drive performance quality.</span></span> <span data-ttu-id="12d56-109">當您需要查看**特定使用者**的通話與會議資訊時，請結合使用 CQD 資料與每個使用者的[呼叫分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="12d56-109">When you need to look into call and meeting information for a **specific user**, use CQD data in conjunction with per-user [call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>

<span data-ttu-id="12d56-110">例如，您可以使用 CQD 來判斷您使用每個使用者的呼叫分析所觀察的使用者不佳通話品質 (，) 是因為網路問題也會影響許多其他使用者。</span><span class="sxs-lookup"><span data-stu-id="12d56-110">For example, using CQD, you can determine that a user's poor call quality (which you observed using per-user call analytics) is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="12d56-111">CQD 會捕獲個人通話體驗，以及使用團隊或商務用 Skype 所做的總體通話品質。</span><span class="sxs-lookup"><span data-stu-id="12d56-111">CQD captures both the individual call experience and the overall quality of calls made using Teams or Skype for Business.</span></span> <span data-ttu-id="12d56-112">使用 CQD 時，整個模式可能會變得很明顯，因此網路工程師可以進行通話品質的及時評估。</span><span class="sxs-lookup"><span data-stu-id="12d56-112">With CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="12d56-113">CQD 提供通話品質度量的報告，可讓您深入瞭解整個通話品質、伺服器用戶端資料流程、用戶端用戶端資料流程，以及語音品質[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)。</span><span class="sxs-lookup"><span data-stu-id="12d56-113">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![通話品質儀表板的螢幕擷取畫面。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="12d56-115">在 CQD 中，我們鼓勵您上傳建築物與端點資訊，讓您使用位置改良式報告來分析使用者組建中的通話品質與可靠性。</span><span class="sxs-lookup"><span data-stu-id="12d56-115">In CQD, we encourage you to upload building and endpoint information, which lets you use Location-Enhanced Reports to analyze call quality and reliability within a user's building.</span></span> <span data-ttu-id="12d56-116">您可以評估資料來判斷問題是獨立于單一使用者，還是會影響較大的使用者區段。</span><span class="sxs-lookup"><span data-stu-id="12d56-116">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span> <span data-ttu-id="12d56-117">若要在 CQD 中開啟組建或端點專用的視圖，系統管理員必須在 CQD**租使用者資料**上傳頁面上的[建築物或端點資訊](CQD-upload-tenant-building-data.md)。</span><span class="sxs-lookup"><span data-stu-id="12d56-117">To turn on building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](CQD-upload-tenant-building-data.md) on the CQD **Tenant Data Upload** page.</span></span>

![[通話品質儀表板] 的位置改良報告的螢幕擷取畫面。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

<span data-ttu-id="12d56-119">不要錯過我們的 [[管理通話與會議品質](quality-of-experience-review-guide.md)] 文章，這會為負責管理團隊中的服務品質的小組系統管理員或支援工程師提供深入指引。</span><span class="sxs-lookup"><span data-stu-id="12d56-119">Don't miss our [Manage call and meeting quality](quality-of-experience-review-guide.md) article, which offers in-depth guidance for the Teams admin or support engineer responsible for managing service quality in Teams.</span></span>

## <a name="older-version-of-cqd-cqdlynccom"></a><span data-ttu-id="12d56-120">較舊版本的 CQD (CQD.lync.com) </span><span class="sxs-lookup"><span data-stu-id="12d56-120">Older version of CQD (CQD.lync.com)</span></span>

<span data-ttu-id="12d56-121">目前版本的 CQD (https://CQD.Teams.microsoft.com) 取代舊版的 CQD (https://CQD.lync.com) 。</span><span class="sxs-lookup"><span data-stu-id="12d56-121">The current version of CQD (https://CQD.Teams.microsoft.com) is replacing the older version of CQD (https://CQD.lync.com).</span></span> <span data-ttu-id="12d56-122">您仍然可以使用 CQD.lync.com (從商務用 Skype 系統管理中心) ，但從2020年7月1日起，就是使用來自 CQD 的資料。Teams.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="12d56-122">You can still use CQD.lync.com (available from the Skype for Business admin center), but as of July 1, 2020, it's using the data from CQD.Teams.microsoft.com.</span></span> <span data-ttu-id="12d56-123">我們將關閉 CQD.lync.com 的 access，因此您應該移至 CQD。如果您尚未這麼做，請 Teams.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="12d56-123">We'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="12d56-124">從2020年7月1日起，您將無法再從舊版 CQD 中查看或修改您的建立或查詢資料)  (CQD.lync.com。</span><span class="sxs-lookup"><span data-stu-id="12d56-124">As of July 1, 2020, you can no longer view or modify your building or query data from the old CQD (CQD.lync.com).</span></span> <span data-ttu-id="12d56-125">如果您還沒有從 CQD.lync.com 遷移這些資料，但仍需要，請記錄支援票證。</span><span class="sxs-lookup"><span data-stu-id="12d56-125">If you haven't already migrated this data from CQD.lync.com and still need it, log a support ticket.</span></span>

## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="12d56-126">使用 Power BI 來分析 CQD 資料</span><span class="sxs-lookup"><span data-stu-id="12d56-126">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="12d56-127">2020年1月[的新功能：下載 POWER BI 查詢範本以進行 CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="12d56-127">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="12d56-128">可自訂的 Power BI 範本，您可以用來分析及報告您的 CQD 資料。</span><span class="sxs-lookup"><span data-stu-id="12d56-128">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="12d56-129">已閱讀 [[使用 POWER BI 分析 CQD 資料](CQD-Power-BI-query-templates.md)] 以深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="12d56-129">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>



## <a name="related-topics"></a><span data-ttu-id="12d56-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="12d56-130">Related topics</span></span>

[<span data-ttu-id="12d56-131">改善及監視團隊的通話品質</span><span class="sxs-lookup"><span data-stu-id="12d56-131">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="12d56-132">設定通話品質儀表板 (CQD) </span><span class="sxs-lookup"><span data-stu-id="12d56-132">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="12d56-133">上傳租使用者及組建資料</span><span class="sxs-lookup"><span data-stu-id="12d56-133">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="12d56-134">CQD 資料和報表</span><span class="sxs-lookup"><span data-stu-id="12d56-134">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="12d56-135">使用 CQD 管理通話與會議品質</span><span class="sxs-lookup"><span data-stu-id="12d56-135">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="12d56-136">CQD 中可用的維度與量值</span><span class="sxs-lookup"><span data-stu-id="12d56-136">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="12d56-137">CQD 中的資料流程分類</span><span class="sxs-lookup"><span data-stu-id="12d56-137">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="12d56-138">使用 Power BI 來分析 CQD 資料</span><span class="sxs-lookup"><span data-stu-id="12d56-138">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)


[<span data-ttu-id="12d56-139">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="12d56-139">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)