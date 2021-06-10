---
title: 監控並改善通話品質Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: 在 QoS (中) 服務品質，然後在 Microsoft Teams。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 62e687de154fadffd6ac95bd628fec6f9454cc51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162693"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a><span data-ttu-id="9ff33-103">監控並改善通話品質Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9ff33-103">Monitor and improve call quality for Microsoft Teams</span></span>

<span data-ttu-id="9ff33-104">本文介紹三種可用於監控、疑難排解、管理和改善通話品質的重要Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="9ff33-104">This article introduces three key tools you can use to monitor, troubleshoot, manage, and improve call quality in Microsoft Teams.</span></span> 

- <span data-ttu-id="9ff33-105">**通話品質儀表板 (CQD) ：** 若要分析全組織的趨勢或問題，推動改善績效</span><span class="sxs-lookup"><span data-stu-id="9ff33-105">**Call Quality Dashboard (CQD)**: To analyze org-wide trends or problems, drive improvements to performance</span></span>

- <span data-ttu-id="9ff33-106">**通話分析**：分析個別使用者的通話和會議品質</span><span class="sxs-lookup"><span data-stu-id="9ff33-106">**Call analytics**: To analyze call and meeting quality for individual users</span></span>

- <span data-ttu-id="9ff33-107">**服務品質與 QoS (：)** 重要網路流量的優先順序</span><span class="sxs-lookup"><span data-stu-id="9ff33-107">**Quality of Service (QoS)**: To prioritize important network traffic</span></span>



## <a name="monitor-and-troubleshoot-call-quality"></a><span data-ttu-id="9ff33-108">監控和疑難排解通話品質</span><span class="sxs-lookup"><span data-stu-id="9ff33-108">Monitor and troubleshoot call quality</span></span>
<span data-ttu-id="9ff33-109">您將使用每個使用者的通話分析與通話品質 **儀表板**，尋找及疑難排解在進行中作業期間所出現之通話品質問題。</span><span class="sxs-lookup"><span data-stu-id="9ff33-109">You'll use per-user **Call analytics** and **Call Quality Dashboard** to find and troubleshoot call-quality problems that come up during ongoing operation.</span></span> <span data-ttu-id="9ff33-110">這可讓您在整個網路中推動提升績效。</span><span class="sxs-lookup"><span data-stu-id="9ff33-110">This lets you drive performance improvements across your network.</span></span> <span data-ttu-id="9ff33-111">這兩個工具都位於Teams中心。</span><span class="sxs-lookup"><span data-stu-id="9ff33-111">Both of these tools are in the Teams admin center.</span></span>

 - <span data-ttu-id="9ff33-112">**通話分析** 會顯示與特定通話和會議相關的裝置、網路和連接的詳細資訊，Teams。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9ff33-112">**Call analytics** shows detailed information about the devices, networks, and connectivity related to  **_specific calls and meetings_** for each user in Teams.</span></span> <span data-ttu-id="9ff33-113">Teams系統管理員和技術支援人員會使用這項資訊來疑難排解特定通話中的通話品質與連接問題。</span><span class="sxs-lookup"><span data-stu-id="9ff33-113">Teams admin and helpdesk agents will use this information to troubleshoot call quality and connection problems in a specific call.</span></span> <span data-ttu-id="9ff33-114">若要深入瞭解，請參閱 [設定通話分析](set-up-call-analytics.md) 及使用通話分析來疑難排解 [通話品質不佳的問題](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="9ff33-114">To learn more, read [Set up call analytics](set-up-call-analytics.md) and [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
 
 - <span data-ttu-id="9ff33-115">**通話品質儀表板 (CQD)** 提供您整個組織的通話品質 \*\*\*\* 全網路視圖。</span><span class="sxs-lookup"><span data-stu-id="9ff33-115">**Call Quality Dashboard (CQD)** gives you a **_network-wide view_** of call quality across your organization.</span></span> <span data-ttu-id="9ff33-116">使用 CQD 資訊來説明您找出並修正問題。</span><span class="sxs-lookup"><span data-stu-id="9ff33-116">Use CQD information to help you identify and fix problems.</span></span> <span data-ttu-id="9ff33-117">首先， [設定 CQD](turning-on-and-using-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="9ff33-117">First, [Set up CQD](turning-on-and-using-call-quality-dashboard.md).</span></span> <span data-ttu-id="9ff33-118">然後在 中[閱讀管理通話和會議Teams。](quality-of-experience-review-guide.md)</span><span class="sxs-lookup"><span data-stu-id="9ff33-118">Then read [Manage call and meeting quality in Teams](quality-of-experience-review-guide.md).</span></span>

 <span data-ttu-id="9ff33-119">通話分析與 CQD 同時執行，可以獨立或一起使用。</span><span class="sxs-lookup"><span data-stu-id="9ff33-119">Call analytics and CQD run in parallel and can be used independently or together.</span></span> <span data-ttu-id="9ff33-120">例如，如果通訊支援專家決定他們需要更多協助來疑難排解使用者的通話問題，他們會將通話升級至通訊支援工程師，而該工程師可以存取通話的其他相關資訊。</span><span class="sxs-lookup"><span data-stu-id="9ff33-120">For example, if a communications support specialist determines that they need more help troubleshooting a user's call problem, they escalate the call to a communications support engineer, who has access to additional information about the call.</span></span> <span data-ttu-id="9ff33-121">因此，通訊支援工程師會通知網路工程師在通話分析中發現可能的網站相關問題。</span><span class="sxs-lookup"><span data-stu-id="9ff33-121">In turn, the communications support engineer alerts a network engineer to a possible site-related issue they noticed in the call analytics.</span></span> <span data-ttu-id="9ff33-122">網路工程師會檢查 CQD，查看整體網站相關問題是否可能是造成使用者通話問題的原因。</span><span class="sxs-lookup"><span data-stu-id="9ff33-122">The network engineer checks CQD to see if an overall site-related issue could be a contributing cause of the user's call problem.</span></span>


## <a name="prioritize-important-network-traffic-using-qos"></a><span data-ttu-id="9ff33-123">使用 QoS 排定重要網路流量的優先順序</span><span class="sxs-lookup"><span data-stu-id="9ff33-123">Prioritize important network traffic using QoS</span></span>
<span data-ttu-id="9ff33-124">當使用者開始使用 Teams電話和會議時，他們可能會遇到來電者的語音中斷或中斷通話或會議。</span><span class="sxs-lookup"><span data-stu-id="9ff33-124">As your users start using Teams for calls and meetings, they may experience a caller's voice breaking up or cutting in and out of a call or meeting.</span></span> <span data-ttu-id="9ff33-125">共用影片可能會凍結或像素化，或完全失敗。</span><span class="sxs-lookup"><span data-stu-id="9ff33-125">Shared video may freeze or pixelate, or fail altogether.</span></span> <span data-ttu-id="9ff33-126">這是因為代表語音和視音訊流量的 IP 封包遇到網路擠塞，且到達順序不一或完全中斷。</span><span class="sxs-lookup"><span data-stu-id="9ff33-126">This is due to the IP packets that represent voice and video traffic encountering network congestion and arriving out of sequence or not at all.</span></span> <span data-ttu-id="9ff33-127">如果發生此 (或防止其發生于第一) ，請使用服務品質 (**QoS) 。**</span><span class="sxs-lookup"><span data-stu-id="9ff33-127">If this happens (or to prevent it from happening in the first place), use **Quality of Service (QoS)**.</span></span> 

<span data-ttu-id="9ff33-128">使用 QoS，您可以排定延遲敏感性網路流量的優先順序 (例如語音或視音訊流) ，讓流量在較不敏感的流量前面「一路剪下」 (例如下載新的應用程式，其中額外的第二秒下載並不是一件) 。</span><span class="sxs-lookup"><span data-stu-id="9ff33-128">With QoS, you prioritize delay-sensitive network traffic (for example, voice or video streams), allowing it to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal).</span></span> <span data-ttu-id="9ff33-129">QoS 會使用 Windows 群組原則物件和稱為埠式存取控制清單的路由功能，來識別並標記即時資料流中的所有封包，這項功能會指示您的網路提供語音、視像和螢幕共用自己的私人網路絡頻寬。</span><span class="sxs-lookup"><span data-stu-id="9ff33-129">QoS identifies and marks all packets in real-time streams using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, which instructs your network to give voice, video, and screen sharing their own dedicated network bandwidth.</span></span>

<span data-ttu-id="9ff33-130">在理想情況下，您將在內部網路上實現 QoS，同時準備推出Teams，但您隨時可以執行。</span><span class="sxs-lookup"><span data-stu-id="9ff33-130">Ideally, you'll implement QoS on your internal network while getting ready to roll out Teams, but you can do it anytime.</span></span> <span data-ttu-id="9ff33-131">如果您夠小，您可能不需要 QoS。</span><span class="sxs-lookup"><span data-stu-id="9ff33-131">If you're small enough, you might not need QoS.</span></span>

<span data-ttu-id="9ff33-132">準備好時，請參閱在 (中) [QoS Microsoft Teams。](QoS-in-Teams.md)</span><span class="sxs-lookup"><span data-stu-id="9ff33-132">When you're ready, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span>

<span data-ttu-id="9ff33-133">若要使用 QoS 管理會議流量，請參閱設定要如何處理會議即時Teams[流量](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。</span><span class="sxs-lookup"><span data-stu-id="9ff33-133">To use QoS to manage meeting traffic, read [Set how you want to handle real-time media traffic for Teams meetings](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).</span></span>


## <a name="related-topics"></a><span data-ttu-id="9ff33-134">相關主題</span><span class="sxs-lookup"><span data-stu-id="9ff33-134">Related Topics</span></span>

[<span data-ttu-id="9ff33-135">設定通話分析</span><span class="sxs-lookup"><span data-stu-id="9ff33-135">Set up call analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="9ff33-136">使用通話分析來疑難排解不良通話品質</span><span class="sxs-lookup"><span data-stu-id="9ff33-136">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="9ff33-137">設定 CQD</span><span class="sxs-lookup"><span data-stu-id="9ff33-137">Set up CQD</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="9ff33-138">管理通話和會議品質Teams</span><span class="sxs-lookup"><span data-stu-id="9ff33-138">Manage call and meeting quality in Teams</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="9ff33-139">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="9ff33-139">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)