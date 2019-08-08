---
title: 在 Microsoft 團隊中實施 QoS 及監視通話分析
author: jambirk
ms.author: jambirk
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: jambirk
description: 使用 [服務品質 (QoS)] 設定, 然後在 Microsoft 團隊中呼叫分析和通話品質儀表板。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 70e862adf2aad795a9ef1ab34eaa2de21240a388
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239250"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a><span data-ttu-id="05aa1-103">在 Microsoft 團隊中實施 QoS 及監視通話品質</span><span class="sxs-lookup"><span data-stu-id="05aa1-103">Implement QoS and Monitor Call Quality in Microsoft Teams</span></span>

## <a name="get-started"></a><span data-ttu-id="05aa1-104">快速入門</span><span class="sxs-lookup"><span data-stu-id="05aa1-104">Get Started</span></span>

<span data-ttu-id="05aa1-105">當您的使用者開始使用團隊撥打電話和召開會議時, 他們可能會遇到來電或 chopping 通話或會議的問題。</span><span class="sxs-lookup"><span data-stu-id="05aa1-105">As your users start using Teams for making calls and holding meetings, they may experience a caller's voice breaking up or chopping in and out of a call or meeting.</span></span> <span data-ttu-id="05aa1-106">共用影片可能會凍結或像素化, 或完全失敗。</span><span class="sxs-lookup"><span data-stu-id="05aa1-106">Shared video may freeze or pixelate, or fail altogether.</span></span> <span data-ttu-id="05aa1-107">這是因為 IP 資料包所代表的語音和影片通信量遇到網路擁塞, 而不是順序讀出或根本無法進行。</span><span class="sxs-lookup"><span data-stu-id="05aa1-107">This is due to the IP packets that represent voice and video traffic encountering network congestion and arriving out of sequence or not at all.</span></span> <span data-ttu-id="05aa1-108">有幾種方法可以在它們出現表面並防止其傳回 (主要是服務品質 (QoS)) 時, 找出這些問題。</span><span class="sxs-lookup"><span data-stu-id="05aa1-108">There are ways to identify these problems when they surface and prevent their return, primarily Quality of Service (QoS).</span></span>

<span data-ttu-id="05aa1-109">**[服務品質 (QoS)** ] 是一種允許即時網路流量 (例如語音或視頻串流), 可讓您在不太敏感的通信量 (例如下載新的 app, 增加額外的下載沒太大的交易。</span><span class="sxs-lookup"><span data-stu-id="05aa1-109">**Quality of Service (QoS)** is a way to allow real-time network traffic (like voice or video streams) that is sensitive to network delays to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal).</span></span> <span data-ttu-id="05aa1-110">QoS 會使用 Windows 群組原則物件和路由功能 (稱為埠的存取控制清單) 來識別及標記即時資料流中的所有資料包, 這可協助您的網路提供語音、影片和螢幕共用來傳送自己的專用部分網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="05aa1-110">QoS identifies and marks all packets in real-time streams using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, which then helps your network to give voice, video, and screen share streams their own dedicated portions of network bandwidth.</span></span>

 <span data-ttu-id="05aa1-111">現在, 我們只是說它是透過郵件傳送信件的方式: 如果您傳送 it 書籍的速度非常快, 且有足夠的功能, 如果您將它傳送給第一個課程, 就能以更快的速度傳送它, 而且如果您傳送 it 優先順序郵件, 它會在兩天內取得。</span><span class="sxs-lookup"><span data-stu-id="05aa1-111">For now, we'll just say that it's a lot like sending a letter through the mail: If you send it book rate it gets there pretty soon and that's good enough, if you send it first class it gets there a lot faster, and if you send it Priority Mail, it gets there within two days.</span></span> <span data-ttu-id="05aa1-112">當然的網路比郵件執行的速度更快, 但仍會執行 true, 因為速度對於某些應用程式來說非常重要, 而且對其他人而言並不重要。</span><span class="sxs-lookup"><span data-stu-id="05aa1-112">Of course networks run faster than the mail, but it still runs true that speed is critical for some applications and is not so critical for others.</span></span> <span data-ttu-id="05aa1-113">這個主旨本身在本質上是非常複雜且難以理解, 但它會在使用者體驗上帶來巨大的差異, 因此需要提前進行投資與精力。</span><span class="sxs-lookup"><span data-stu-id="05aa1-113">This subject is inherently detailed and tricky to understand at first, but it makes a huge difference in the user experience so it's worth investing time and energy upfront.</span></span> <span data-ttu-id="05aa1-114">已閱讀[[在 Microsoft 團隊中實施服務品質 (QoS)](QoS-in-Teams.md) ], 以取得更詳細的討論。</span><span class="sxs-lookup"><span data-stu-id="05aa1-114">Read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md) for a more detailed discussion.</span></span>

<span data-ttu-id="05aa1-115">理想的做法是, 在您的內部網路上實施 QoS, 而不是設定小組, 但如果足夠小, 就可以選用。</span><span class="sxs-lookup"><span data-stu-id="05aa1-115">Ideally you would implement QoS on your internal network while setting up Teams, but if you're small enough it can be optional.</span></span> <span data-ttu-id="05aa1-116">這可讓延遲式的語音及視頻流量在其他流量前優先。</span><span class="sxs-lookup"><span data-stu-id="05aa1-116">This allows the delay-sensitive voice and video traffic to get prioritized ahead of other traffic.</span></span> <span data-ttu-id="05aa1-117">您可以在[Microsoft 團隊系統管理中心](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)的所有[用戶端裝置](QoS-in-Teams-clients.md), 以及您網路中的交換器與路由器上, 執行這項優先順序。</span><span class="sxs-lookup"><span data-stu-id="05aa1-117">You'd do this prioritization on all the [client devices](QoS-in-Teams-clients.md), in the [Microsoft Teams admin center](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings), as well as on the switches and routers in your network.</span></span>

<span data-ttu-id="05aa1-118">[[**通話分析] 和 [通話品質儀表板**](difference-between-call-analytics-and-call-quality-dashboard.md)] 可用來找出並疑難排解在進行中的作業時所帶來的問題。</span><span class="sxs-lookup"><span data-stu-id="05aa1-118">[**Call Analytics and Call Quality Dashboard**](difference-between-call-analytics-and-call-quality-dashboard.md) are used to find and troubleshoot problems that come up during ongoing operation.</span></span>  

<span data-ttu-id="05aa1-119">[**通話分析**] 會顯示與 Microsoft 團隊或商務用 Skype 帳戶中每位使用者的***特定通話與會議***相關的裝置、網路及連線性的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="05aa1-119">**Call Analytics** shows detailed information about the devices, networks, and connectivity related to  ***specific calls and meetings*** for each user in a Microsoft Teams or Skype for Business account.</span></span> <span data-ttu-id="05aa1-120">如果您是 Office 365 系統管理員, 您可以使用呼叫分析來針對特定通話中遇到的通話品質和連線問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="05aa1-120">If you're an Office 365 admin, you can use Call Analytics to troubleshoot call quality and connection problems experienced in a specific call.</span></span> <span data-ttu-id="05aa1-121">這可協助您找出並消除問題。</span><span class="sxs-lookup"><span data-stu-id="05aa1-121">This can help you to identify and eliminate problems.</span></span>

<span data-ttu-id="05aa1-122">**通話品質儀表板 (CQD)** 的設計目的是協助系統管理員和網路工程師優化其***網路***, 不會分析和疑難排解單一通話。</span><span class="sxs-lookup"><span data-stu-id="05aa1-122">**Call Quality Dashboard (CQD)** is designed to help admins and network engineers optimize their ***network***, not analyze and troubleshoot a single call.</span></span> <span data-ttu-id="05aa1-123">CQD 會將焦點從特定的使用者轉移, 以查看整個組織的匯總資訊。</span><span class="sxs-lookup"><span data-stu-id="05aa1-123">CQD shifts focus from specific users to look at aggregated information for an entire organization.</span></span> <span data-ttu-id="05aa1-124">這也可以協助您找出並消除問題。</span><span class="sxs-lookup"><span data-stu-id="05aa1-124">This can also help you to identify and eliminate problems.</span></span>

## <a name="related-topics"></a><span data-ttu-id="05aa1-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="05aa1-125">Related Topics</span></span>

[<span data-ttu-id="05aa1-126">在 Microsoft 團隊中實現服務品質 (QoS)</span><span class="sxs-lookup"><span data-stu-id="05aa1-126">Implement Quality of Service (QoS) in Microsoft Teams</span></span>](QoS-in-Teams.md)

[<span data-ttu-id="05aa1-127">影片: 通話品質概覽</span><span class="sxs-lookup"><span data-stu-id="05aa1-127">Video: Call Quality Overview</span></span>](https://aka.ms/teams-quality)

[<span data-ttu-id="05aa1-128">設定通話分析</span><span class="sxs-lookup"><span data-stu-id="05aa1-128">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="05aa1-129">使用呼叫分析來排查不佳的通話品質問題</span><span class="sxs-lookup"><span data-stu-id="05aa1-129">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="05aa1-130">開啟並使用通話品質儀表板</span><span class="sxs-lookup"><span data-stu-id="05aa1-130">Turning on and using Call Quality Dashboard</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="05aa1-131">通話品質儀表板中提供的維度與量值</span><span class="sxs-lookup"><span data-stu-id="05aa1-131">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="05aa1-132">通話品質儀表板中的資料流程分類</span><span class="sxs-lookup"><span data-stu-id="05aa1-132">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)