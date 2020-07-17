---
title: 監控並改善 Microsoft 團隊的通話品質
author: lolajacobsen
ms.author: lolaj
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: 使用 [服務品質（QoS）] 設定，然後在 Microsoft 團隊中呼叫分析和通話品質儀表板。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d5db11bbd9608aebb1eb2b73ebacc9793629e44
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085932"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a><span data-ttu-id="826fd-103">監控並改善 Microsoft 團隊的通話品質</span><span class="sxs-lookup"><span data-stu-id="826fd-103">Monitor and improve call quality for Microsoft Teams</span></span>

<span data-ttu-id="826fd-104">本文將介紹三個主要工具，您可以用來在 Microsoft 團隊中監控、排除、管理及改善通話品質。</span><span class="sxs-lookup"><span data-stu-id="826fd-104">This article introduces three key tools you can use to monitor, troubleshoot, manage, and improve call quality in Microsoft Teams.</span></span> 

- <span data-ttu-id="826fd-105">**通話品質儀表板（CQD）**：若要分析整個組織的趨勢或問題，請推動效能的改善</span><span class="sxs-lookup"><span data-stu-id="826fd-105">**Call Quality Dashboard (CQD)**: To analyze org-wide trends or problems, drive improvements to performance</span></span>

- <span data-ttu-id="826fd-106">**通話分析**：分析個別使用者的通話與會議品質</span><span class="sxs-lookup"><span data-stu-id="826fd-106">**Call analytics**: To analyze call and meeting quality for individual users</span></span>

- <span data-ttu-id="826fd-107">**服務品質（QoS）**：用於排定重要網路流量的優先順序</span><span class="sxs-lookup"><span data-stu-id="826fd-107">**Quality of Service (QoS)**: To prioritize important network traffic</span></span>



## <a name="monitor-and-troubleshoot-call-quality"></a><span data-ttu-id="826fd-108">監控通話品質並進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="826fd-108">Monitor and troubleshoot call quality</span></span>
<span data-ttu-id="826fd-109">您將會使用每個使用者的**通話分析**和**通話品質儀表板**，找出並疑難排解在進行中的作業時所產生的通話品質問題。</span><span class="sxs-lookup"><span data-stu-id="826fd-109">You'll use per-user **Call analytics** and **Call Quality Dashboard** to find and troubleshoot call-quality problems that come up during ongoing operation.</span></span> <span data-ttu-id="826fd-110">這可讓您提高整個網路的效能。</span><span class="sxs-lookup"><span data-stu-id="826fd-110">This lets you drive performance improvements across your network.</span></span> <span data-ttu-id="826fd-111">這兩種工具都是在團隊系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="826fd-111">Both of these tools are in the Teams admin center.</span></span>

 - <span data-ttu-id="826fd-112">[**通話分析**] 會顯示與團隊中每位使用者的***特定通話與會議***相關的裝置、網路及連線性的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="826fd-112">**Call analytics** shows detailed information about the devices, networks, and connectivity related to  ***specific calls and meetings*** for each user in Teams.</span></span> <span data-ttu-id="826fd-113">團隊管理員和支援人員的代理程式會使用此資訊來針對特定通話中的通話品質和連線問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="826fd-113">Teams admin and helpdesk agents will use this information to troubleshoot call quality and connection problems in a specific call.</span></span> <span data-ttu-id="826fd-114">若要深入瞭解，請參閱[設定通話分析](set-up-call-analytics.md)和[使用呼叫分析，以解決不佳通話品質的問題](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="826fd-114">To learn more, read [Set up call analytics](set-up-call-analytics.md) and [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
 
 - <span data-ttu-id="826fd-115">**通話品質儀表板（CQD）** 可在整個組織中提供通話品質的整個***網路視圖***。</span><span class="sxs-lookup"><span data-stu-id="826fd-115">**Call Quality Dashboard (CQD)** gives you a ***network-wide view*** of call quality across your organization.</span></span> <span data-ttu-id="826fd-116">使用 CQD 資訊來協助您找出並修正問題。</span><span class="sxs-lookup"><span data-stu-id="826fd-116">Use CQD information to help you identify and fix problems.</span></span> <span data-ttu-id="826fd-117">首先，[設定 CQD](turning-on-and-using-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="826fd-117">First, [Set up CQD](turning-on-and-using-call-quality-dashboard.md).</span></span> <span data-ttu-id="826fd-118">然後閱讀[團隊中的 [管理通話與會議品質](quality-of-experience-review-guide.md)]。</span><span class="sxs-lookup"><span data-stu-id="826fd-118">Then read [Manage call and meeting quality in Teams](quality-of-experience-review-guide.md).</span></span>

 <span data-ttu-id="826fd-119">呼叫分析與 CQD 會並存執行，而且可以獨立地或一起使用。</span><span class="sxs-lookup"><span data-stu-id="826fd-119">Call analytics and CQD run in parallel and can be used independently or together.</span></span> <span data-ttu-id="826fd-120">例如，如果通訊支援專家認為他們需要進一步協助解決使用者的呼叫問題，他們會將通話升級至通訊支援工程師，他們可以存取有關通話的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="826fd-120">For example, if a communications support specialist determines that they need more help troubleshooting a user's call problem, they escalate the call to a communications support engineer, who has access to additional information about the call.</span></span> <span data-ttu-id="826fd-121">接著，通訊支援工程師會通知網路工程師，看看在通話分析中可能會注意到的與網站相關的問題。</span><span class="sxs-lookup"><span data-stu-id="826fd-121">In turn, the communications support engineer alerts a network engineer to a possible site-related issue they noticed in the call analytics.</span></span> <span data-ttu-id="826fd-122">網路工程師會檢查 CQD，以查看總體網站相關問題是否可能是造成使用者通話問題的原因。</span><span class="sxs-lookup"><span data-stu-id="826fd-122">The network engineer checks CQD to see if an overall site-related issue could be a contributing cause of the user's call problem.</span></span>


## <a name="prioritize-important-network-traffic-using-qos"></a><span data-ttu-id="826fd-123">使用 QoS 來設定重要網路流量的優先順序</span><span class="sxs-lookup"><span data-stu-id="826fd-123">Prioritize important network traffic using QoS</span></span>
<span data-ttu-id="826fd-124">當您的使用者開始使用團隊撥打電話與會議時，可能會遇到來電者的語音或撥打電話或會議。</span><span class="sxs-lookup"><span data-stu-id="826fd-124">As your users start using Teams for calls and meetings, they may experience a caller's voice breaking up or cutting in and out of a call or meeting.</span></span> <span data-ttu-id="826fd-125">共用影片可能會凍結或像素化，或完全失敗。</span><span class="sxs-lookup"><span data-stu-id="826fd-125">Shared video may freeze or pixelate, or fail altogether.</span></span> <span data-ttu-id="826fd-126">這是因為 IP 資料包所代表的語音和影片通信量遇到網路擁塞，而不是順序讀出或根本無法進行。</span><span class="sxs-lookup"><span data-stu-id="826fd-126">This is due to the IP packets that represent voice and video traffic encountering network congestion and arriving out of sequence or not at all.</span></span> <span data-ttu-id="826fd-127">如果發生這種情況（或是要防止它在第一個位置發生），請使用**服務品質（QoS）**。</span><span class="sxs-lookup"><span data-stu-id="826fd-127">If this happens (or to prevent it from happening in the first place), use **Quality of Service (QoS)**.</span></span> 

<span data-ttu-id="826fd-128">透過 QoS，您可以將延遲敏感的網路流量（例如語音或視頻串流）劃分優先順序，讓它在不太敏感的流量（例如下載新的應用程式，需要額外的時間來下載，而不是大筆的情況下）中進行「在行中切削」。</span><span class="sxs-lookup"><span data-stu-id="826fd-128">With QoS, you prioritize delay-sensitive network traffic (for example, voice or video streams), allowing it to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal).</span></span> <span data-ttu-id="826fd-129">QoS 會使用 Windows 群組原則物件和路由功能（稱為埠的存取控制清單）來識別及標記即時資料流中的所有資料包，這會指示您的網路為自己的私人網路絡頻寬提供語音、影片和螢幕共用。</span><span class="sxs-lookup"><span data-stu-id="826fd-129">QoS identifies and marks all packets in real-time streams using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, which instructs your network to give voice, video, and screen sharing their own dedicated network bandwidth.</span></span>

<span data-ttu-id="826fd-130">在理想的情況下，您會在內部網路上實施 QoS，以準備好要推出小組，但您可以隨時進行。</span><span class="sxs-lookup"><span data-stu-id="826fd-130">Ideally, you'll implement QoS on your internal network while getting ready to roll out Teams, but you can do it anytime.</span></span> <span data-ttu-id="826fd-131">如果您的小一點足夠小，您可能不需要 QoS。</span><span class="sxs-lookup"><span data-stu-id="826fd-131">If you're small enough, you might not need QoS.</span></span>

<span data-ttu-id="826fd-132">當您準備好時，請參閱[在 Microsoft 團隊中實施服務品質（QoS）](QoS-in-Teams.md)。</span><span class="sxs-lookup"><span data-stu-id="826fd-132">When you're ready, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span>

<span data-ttu-id="826fd-133">若要使用 QoS 管理會議流量，請閱讀[設定您想要處理團隊會議即時媒體流量的方式](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。</span><span class="sxs-lookup"><span data-stu-id="826fd-133">To use QoS to manage meeting traffic, read [Set how you want to handle real-time media traffic for Teams meetings](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).</span></span>


## <a name="related-topics"></a><span data-ttu-id="826fd-134">相關主題</span><span class="sxs-lookup"><span data-stu-id="826fd-134">Related Topics</span></span>

[<span data-ttu-id="826fd-135">設定通話分析</span><span class="sxs-lookup"><span data-stu-id="826fd-135">Set up call analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="826fd-136">使用通話分析來疑難排解不良通話品質</span><span class="sxs-lookup"><span data-stu-id="826fd-136">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="826fd-137">設定 CQD</span><span class="sxs-lookup"><span data-stu-id="826fd-137">Set up CQD</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="826fd-138">在團隊中管理通話與會議品質</span><span class="sxs-lookup"><span data-stu-id="826fd-138">Manage call and meeting quality in Teams</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="826fd-139">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="826fd-139">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

