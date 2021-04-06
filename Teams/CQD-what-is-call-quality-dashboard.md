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
description: 瞭解通話品質儀表板 (CQD) ，以及如何使用它來查看 Microsoft Teams 中的會議與通話品質報告。
ms.openlocfilehash: d262449394d9ad880d13897988e40e26dd98578c
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593831"
---
# <a name="what-is-call-quality-dashboard-cqd"></a><span data-ttu-id="3ec4c-103">什麼是通話品質儀表板 (CQD) ？</span><span class="sxs-lookup"><span data-stu-id="3ec4c-103">What is Call Quality Dashboard (CQD)?</span></span>

<span data-ttu-id="3ec4c-104">Microsoft 通話品質儀表板 (CQD) [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - - 顯示 Microsoft Teams、商務用Skype Online 和商務用 Skype Server 2019 全組織層級的通話和會議品質。</span><span class="sxs-lookup"><span data-stu-id="3ec4c-104">The Microsoft Call Quality Dashboard (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - shows call and meeting quality, at an **org-wide level**, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

  
<span data-ttu-id="3ec4c-105">最新版本的 CQD 具有接近即時 [的 (NRT) ](CQD-data-and-reports.md)資料摘要，這表示通話記錄可在通話結束的 30 分鐘內在 CQD 中提供。</span><span class="sxs-lookup"><span data-stu-id="3ec4c-105">The latest version of CQD features a [near-real-time (NRT) data feed](CQD-data-and-reports.md), which means that call records are available in CQD within 30 minutes of the end of a call.</span></span>

<span data-ttu-id="3ec4c-106">無論 CQD 包含使用者標識資訊 ([EUII) 資料，](CQD-data-and-reports.md#euii-data)其管理方式與 [整個 Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)的 EUII 相同。</span><span class="sxs-lookup"><span data-stu-id="3ec4c-106">Wherever CQD includes [end-user identifiable information (EUII) data](CQD-data-and-reports.md#euii-data), it's managed in the same way as [EUII throughout Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="3ec4c-107">CQD 是專為協助 Teams 系統管理員、商務用 Skype 系統管理員和網路工程師監控全組織層級的通話和會議品質所設計。</span><span class="sxs-lookup"><span data-stu-id="3ec4c-107">CQD is designed to help Teams admins, Skype for Business admins, and network engineers monitor call and meeting quality at an org-wide level.</span></span> <span data-ttu-id="3ec4c-108">您將使用 CQD 來協助 **優化您的網路** ，以提升績效品質。</span><span class="sxs-lookup"><span data-stu-id="3ec4c-108">You'll use CQD to help you **optimize your network** to drive performance quality.</span></span> <span data-ttu-id="3ec4c-109">當您需要查看特定使用者的通話和會議資訊時，請使用CQD 資料與每個使用者的通話[分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="3ec4c-109">When you need to look into call and meeting information for a **specific user**, use CQD data in conjunction with per-user [call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>

<span data-ttu-id="3ec4c-110">例如，使用 CQD，您可以判斷使用者使用每個使用者通話分析 (所觀察到的通話品質不佳) 是因為網路問題也會影響到許多其他使用者。</span><span class="sxs-lookup"><span data-stu-id="3ec4c-110">For example, using CQD, you can determine that a user's poor call quality (which you observed using per-user call analytics) is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="3ec4c-111">CQD 會同時取得使用 Teams 或商務用 Skype 進行之通話的個人通話體驗和整體品質。</span><span class="sxs-lookup"><span data-stu-id="3ec4c-111">CQD captures both the individual call experience and the overall quality of calls made using Teams or Skype for Business.</span></span> <span data-ttu-id="3ec4c-112">有了 CQD，整體模式可能會變得明顯，因此網路工程師可以做出明智的通話品質評定。</span><span class="sxs-lookup"><span data-stu-id="3ec4c-112">With CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="3ec4c-113">CQD 提供通話品質度量報告，可深入瞭解整體通話品質、伺服器-用戶端資料流程、用戶端-用戶端資料流程和語音品質[SLA。](https://go.microsoft.com/fwlink/p/?linkid=846252)</span><span class="sxs-lookup"><span data-stu-id="3ec4c-113">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![通話品質儀表板的螢幕擷取畫面。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="3ec4c-115">在 CQD 中，我們鼓勵您上傳建築物和端點資訊，讓您使用 Location-Enhanced 報表來分析使用者建築物內的通話品質和可靠性。</span><span class="sxs-lookup"><span data-stu-id="3ec4c-115">In CQD, we encourage you to upload building and endpoint information, which lets you use Location-Enhanced Reports to analyze call quality and reliability within a user's building.</span></span> <span data-ttu-id="3ec4c-116">您可以評估資料，以判斷問題是否與單一使用者隔離，或影響較大的使用者區段。</span><span class="sxs-lookup"><span data-stu-id="3ec4c-116">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span> <span data-ttu-id="3ec4c-117">若要在 CQD 中開啟建築物或端點特定視圖，系統管理員必須在 [](CQD-upload-tenant-building-data.md)CQD **租** 使用者資料上傳頁面上上傳建築物或端點資訊。</span><span class="sxs-lookup"><span data-stu-id="3ec4c-117">To turn on building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](CQD-upload-tenant-building-data.md) on the CQD **Tenant Data Upload** page.</span></span>

![通話品質儀表板的螢幕擷取畫面Location-Enhanced報表。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

<span data-ttu-id="3ec4c-119">請勿錯過我們的管理通話和會議 [品質](quality-of-experience-review-guide.md) 文章，本文為負責在 Teams 中管理服務品質的 Teams 系統管理員或支援工程師提供深入指引。</span><span class="sxs-lookup"><span data-stu-id="3ec4c-119">Don't miss our [Manage call and meeting quality](quality-of-experience-review-guide.md) article, which offers in-depth guidance for the Teams admin or support engineer responsible for managing service quality in Teams.</span></span>

## <a name="legacy-version-of-cqd-cqdlynccom"></a><span data-ttu-id="3ec4c-120">舊版 CQD (CQD.lync.com) </span><span class="sxs-lookup"><span data-stu-id="3ec4c-120">Legacy version of CQD (CQD.lync.com)</span></span>

<span data-ttu-id="3ec4c-121">目前版本的 CQD (https://CQD.Teams.microsoft.com) 已取代舊版 CQD https://CQD.lync.com) (。</span><span class="sxs-lookup"><span data-stu-id="3ec4c-121">The current version of CQD (https://CQD.Teams.microsoft.com) has replaced the legacy version of CQD (https://CQD.lync.com).</span></span> <span data-ttu-id="3ec4c-122">您仍可使用 CQD.lync.com (商務用 Skype 系統管理中心) 提供的資料，但自 2020 年 7 月 1 日起，它使用的是 CQD 的資料。Teams.microsoft.com，您無法再從舊的 CQD 資料表來查看或修改建築物或查詢 (CQD.lync.com) 。</span><span class="sxs-lookup"><span data-stu-id="3ec4c-122">You can still use CQD.lync.com (available from the Skype for Business admin center), but as of July 1, 2020, it's using the data from CQD.Teams.microsoft.com and you can no longer view or modify your building or query data from the old CQD (CQD.lync.com).</span></span> <span data-ttu-id="3ec4c-123">如果您尚未從資料庫移 CQD.lync.com，請記錄支援票證。</span><span class="sxs-lookup"><span data-stu-id="3ec4c-123">If you haven't already migrated this data from CQD.lync.com and still need it, log a support ticket.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3ec4c-124">自 2021 年 7 月 31 日起，我們將淘汰舊版 CQD (CQD.lync.com) 。</span><span class="sxs-lookup"><span data-stu-id="3ec4c-124">As of July 31, 2021, we are retiring the legacy version of CQD (CQD.lync.com).</span></span> <span data-ttu-id="3ec4c-125">之後，系統會自動將您重新導向至 CQD。Teams.microsoft.com 存取 CQD.lync.com，任何未匯出建築物或查詢資料都會遺失。</span><span class="sxs-lookup"><span data-stu-id="3ec4c-125">After that date, you will be automatically redirected to CQD.Teams.microsoft.com when attempting to access CQD.lync.com, and any unmigrated building or query data will be lost.</span></span>

## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="3ec4c-126">使用 Power BI 分析 CQD 資料</span><span class="sxs-lookup"><span data-stu-id="3ec4c-126">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="3ec4c-127">2020 年 1 月新增： [下載 CQD 的 Power BI](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)查詢範本。</span><span class="sxs-lookup"><span data-stu-id="3ec4c-127">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="3ec4c-128">您可以使用可自訂的 Power BI 範本來分析及報告您的 CQD 資料。</span><span class="sxs-lookup"><span data-stu-id="3ec4c-128">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="3ec4c-129">請閱讀 [使用 Power BI 分析 CQD 資料](CQD-Power-BI-query-templates.md) 以深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="3ec4c-129">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>



## <a name="related-topics"></a><span data-ttu-id="3ec4c-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="3ec4c-130">Related topics</span></span>

[<span data-ttu-id="3ec4c-131">改善及監控 Teams 的通話品質</span><span class="sxs-lookup"><span data-stu-id="3ec4c-131">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="3ec4c-132">設定通話品質儀表板 (CQD) </span><span class="sxs-lookup"><span data-stu-id="3ec4c-132">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="3ec4c-133">上傳租使用者和建築物資料</span><span class="sxs-lookup"><span data-stu-id="3ec4c-133">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="3ec4c-134">CQD 資料和報表</span><span class="sxs-lookup"><span data-stu-id="3ec4c-134">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="3ec4c-135">使用 CQD 管理通話和會議品質</span><span class="sxs-lookup"><span data-stu-id="3ec4c-135">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="3ec4c-136">CQD 中可用的維度和度量</span><span class="sxs-lookup"><span data-stu-id="3ec4c-136">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="3ec4c-137">CQD 中的資料流程分類</span><span class="sxs-lookup"><span data-stu-id="3ec4c-137">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="3ec4c-138">使用 Power BI 分析 CQD 資料</span><span class="sxs-lookup"><span data-stu-id="3ec4c-138">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)


[<span data-ttu-id="3ec4c-139">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="3ec4c-139">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
