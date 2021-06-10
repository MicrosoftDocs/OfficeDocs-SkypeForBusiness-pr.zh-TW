---
title: Microsoft Teams瀏覽器上的會議
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
MS.collection:
- M365-collaboration
ms.reviewer: nakulm
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何Teams瀏覽器支援音訊和視音訊。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83617628fe04140c45b005e993d95eac34c6f8bd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121311"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a><span data-ttu-id="72393-103">Microsoft Teams瀏覽器上的會議</span><span class="sxs-lookup"><span data-stu-id="72393-103">Microsoft Teams meetings on unsupported browsers</span></span>

<span data-ttu-id="72393-104">部分瀏覽器 ，例如 Internet Explorer 11、Safari 和 Firefox 支援 Microsoft Teams Web App，但不支援部分 Teams 通話和會議功能。</span><span class="sxs-lookup"><span data-stu-id="72393-104">Some browsers, such as Internet Explorer 11, Safari, and Firefox, support the Microsoft Teams web app but don't support some of the Teams calling and meeting features.</span></span> <span data-ttu-id="72393-105">若要解決這項限制，Teams Web App 可讓使用者透過 PSTN 連接接收音訊，並讓他們以降低的顯示速率 (螢幕) 分享內容。</span><span class="sxs-lookup"><span data-stu-id="72393-105">To work around this limitation, the Teams web app lets users receive audio through a PSTN connection and lets them view presented content (screen share) at a reduced display rate.</span></span>

> [!Note]
> <span data-ttu-id="72393-106">Microsoft 365應用程式和服務不支援 Internet Explorer 11，自 2021 年 8 月 17 日起 (Microsoft Teams自 2020 年 11 月 30 日起 (Microsoft Teams將不支援 Internet Explorer 11。從 2020 年 11 月 30 日) 。</span><span class="sxs-lookup"><span data-stu-id="72393-106">Microsoft 365 apps and services will not support Internet Explorer 11 starting August 17, 2021 (Microsoft Teams will not support Internet Explorer 11 earlier, starting  November 30, 2020).</span></span> <span data-ttu-id="72393-107">[深入了解](https://aka.ms/AA97tsw)。</span><span class="sxs-lookup"><span data-stu-id="72393-107">[Learn more](https://aka.ms/AA97tsw).</span></span> <span data-ttu-id="72393-108">請注意，Internet Explorer 11 仍然是受支援的瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="72393-108">Please note that Internet Explorer 11 will remain a supported browser.</span></span> <span data-ttu-id="72393-109">Internet Explorer 11 是作業系統Windows元件，並遵循安裝[](/lifecycle/faq/internet-explorer-microsoft-edge)該作業系統之產品的生命週期政策。</span><span class="sxs-lookup"><span data-stu-id="72393-109">Internet Explorer 11 is a component of the Windows operating system and [follows the Lifecycle Policy](/lifecycle/faq/internet-explorer-microsoft-edge) for the product on which it is  installed.</span></span>

<span data-ttu-id="72393-110">當您Teams不支援的瀏覽器時，瀏覽器會自動顯示一則訊息，說明問題與會話限制。</span><span class="sxs-lookup"><span data-stu-id="72393-110">When Teams detects an unsupported browser, it automatically displays a message explaining the issue and the session limitations.</span></span> <span data-ttu-id="72393-111">該訊息提供存取會議音訊的進一步指示，例如建議使用者留下回電號碼，Teams可以打電話給使用者，或指示使用者撥打會議邀請中包含的會議號碼。</span><span class="sxs-lookup"><span data-stu-id="72393-111">The message provides further instructions for accessing the meeting audio, such as advising the user to leave a call back number so that Teams can call the user, or instructing the user to call the conference number included in the meeting invitation.</span></span> <span data-ttu-id="72393-112">訊息也會鼓勵使用者下載並使用桌面Teams[用戶端](https://teams.microsoft.com/downloads)，以獲得完整的Teams體驗。</span><span class="sxs-lookup"><span data-stu-id="72393-112">The message also encourages the user to download and use the [Teams desktop client](https://teams.microsoft.com/downloads) for the full Teams experience.</span></span>

<span data-ttu-id="72393-113">如果 PSTN 無法使用，使用者將看不到存取會議的指示，且無法加入會議。</span><span class="sxs-lookup"><span data-stu-id="72393-113">If PSTN is unavailable, the user won't see the instructions for accessing the meeting and won't be able to join the meeting.</span></span>

## <a name="browser-limitations"></a><span data-ttu-id="72393-114">瀏覽器限制</span><span class="sxs-lookup"><span data-stu-id="72393-114">Browser limitations</span></span>

<span data-ttu-id="72393-115">在不支援的瀏覽器Teams Web App 的人將會遇到下列限制：</span><span class="sxs-lookup"><span data-stu-id="72393-115">People who use the Teams web app on unsupported browsers will experience the following limitations:</span></span>

- <span data-ttu-id="72393-116">音訊僅能透過 PSTN 連接使用。</span><span class="sxs-lookup"><span data-stu-id="72393-116">Audio is available through a PSTN connection only.</span></span> <span data-ttu-id="72393-117">使用者無法使用麥克風。</span><span class="sxs-lookup"><span data-stu-id="72393-117">Users can't use their microphone.</span></span>
- <span data-ttu-id="72393-118">使用者無法共用相機或查看其他參與者的影片，但可以透過圖像型螢幕分享來查看呈現的內容。</span><span class="sxs-lookup"><span data-stu-id="72393-118">Users can't share their camera or see other participants' videos but can view presented content through image-based screen sharing.</span></span>
- <span data-ttu-id="72393-119">使用者無法共用其螢幕，雖然他們可以看到另一個會議參與者分享的畫面。</span><span class="sxs-lookup"><span data-stu-id="72393-119">Users can't share their screen, although they can see a screen that another meeting participant shares.</span></span>
- <span data-ttu-id="72393-120">使用者無法控制螢幕共用會話期間。</span><span class="sxs-lookup"><span data-stu-id="72393-120">Users can't take control during a screen sharing session.</span></span>
- <span data-ttu-id="72393-121">使用者不會收到來電通知。</span><span class="sxs-lookup"><span data-stu-id="72393-121">Users won't receive incoming call notifications.</span></span>
- <span data-ttu-id="72393-122">如果通話中斷，會議不會自動重新連接。</span><span class="sxs-lookup"><span data-stu-id="72393-122">If the call is interrupted, the meeting won't automatically reconnect.</span></span>
- <span data-ttu-id="72393-123">使用者無法開始會議。</span><span class="sxs-lookup"><span data-stu-id="72393-123">Users can't start meetings.</span></span>

<span data-ttu-id="72393-124">如要進一Teams瀏覽器支援，請參閱適用于 Teams 的限制[Teams。](./limits-specifications-teams.md#browsers)</span><span class="sxs-lookup"><span data-stu-id="72393-124">For more information about browser support in Teams, see [Limits and specifications for Teams](./limits-specifications-teams.md#browsers).</span></span>

## <a name="related-topics"></a><span data-ttu-id="72393-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="72393-125">Related topics</span></span>

- [<span data-ttu-id="72393-126">在不支援Teams上加入會議</span><span class="sxs-lookup"><span data-stu-id="72393-126">Join a Teams meeting on an unsupported browser</span></span>](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)