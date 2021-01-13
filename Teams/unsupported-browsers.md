---
title: Microsoft 團隊在不支援的瀏覽器上的會議
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
description: 瞭解團隊如何在不受支援的瀏覽器中支援音訊和影片。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4aca1592a89e36e7a26a9a22b111968e4b44a302
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804523"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a><span data-ttu-id="b56b1-103">Microsoft 團隊在不支援的瀏覽器上的會議</span><span class="sxs-lookup"><span data-stu-id="b56b1-103">Microsoft Teams meetings on unsupported browsers</span></span>

<span data-ttu-id="b56b1-104">某些瀏覽器（例如 Internet Explorer 11、Safari 和 Firefox）支援 Microsoft 團隊 web app，但不支援某些小組通話與會議功能。</span><span class="sxs-lookup"><span data-stu-id="b56b1-104">Some browsers, such as Internet Explorer 11, Safari, and Firefox, support the Microsoft Teams web app but don't support some of the Teams calling and meeting features.</span></span> <span data-ttu-id="b56b1-105">若要解決這個限制，小組 web 應用程式可讓使用者透過 PSTN 連線接收音訊，讓他們以較低的顯示速率來查看顯示的內容 (畫面共用) 。</span><span class="sxs-lookup"><span data-stu-id="b56b1-105">To work around this limitation, the Teams web app lets users receive audio through a PSTN connection and lets them view presented content (screen share) at a reduced display rate.</span></span>

> [!Note]
> <span data-ttu-id="b56b1-106">Microsoft 365 應用程式和服務不支援 Internet Explorer 11，從2021年8月17日起，Microsoft 團隊將不會在2020年11月30日之後，從) 中開始， (的 internet explorer 11</span><span class="sxs-lookup"><span data-stu-id="b56b1-106">Microsoft 365 apps and services will not support Internet Explorer 11 starting August 17, 2021 (Microsoft Teams will not support Internet Explorer 11 earlier, starting  November 30, 2020).</span></span> <span data-ttu-id="b56b1-107">[深入了解](https://aka.ms/AA97tsw)。</span><span class="sxs-lookup"><span data-stu-id="b56b1-107">[Learn more](https://aka.ms/AA97tsw).</span></span> <span data-ttu-id="b56b1-108">請注意，Internet Explorer 11 仍然是受支援的瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="b56b1-108">Please note that Internet Explorer 11 will remain a supported browser.</span></span> <span data-ttu-id="b56b1-109">Internet Explorer 11 是 Windows 作業系統的元件，且遵循安裝它之產品的 [生命週期原則](https://docs.microsoft.com/lifecycle/faq/internet-explorer-microsoft-edge) 。</span><span class="sxs-lookup"><span data-stu-id="b56b1-109">Internet Explorer 11 is a component of the Windows operating system and [follows the Lifecycle Policy](https://docs.microsoft.com/lifecycle/faq/internet-explorer-microsoft-edge) for the product on which it is  installed.</span></span>

<span data-ttu-id="b56b1-110">當團隊偵測到不受支援的瀏覽器時，它會自動顯示一則訊息，說明問題及會話限制。</span><span class="sxs-lookup"><span data-stu-id="b56b1-110">When Teams detects an unsupported browser, it automatically displays a message explaining the issue and the session limitations.</span></span> <span data-ttu-id="b56b1-111">此訊息提供更多有關存取會議音訊的指示，例如，建議使用者保留回撥號碼，讓小組可以呼叫使用者，或指示使用者撥打會議邀請中包含的會議號碼。</span><span class="sxs-lookup"><span data-stu-id="b56b1-111">The message provides further instructions for accessing the meeting audio, such as advising the user to leave a call back number so that Teams can call the user, or instructing the user to call the conference number included in the meeting invitation.</span></span> <span data-ttu-id="b56b1-112">此訊息也會鼓勵使用者下載並使用 [小組桌面用戶端](https://teams.microsoft.com/downloads) 來取得完整的團隊體驗。</span><span class="sxs-lookup"><span data-stu-id="b56b1-112">The message also encourages the user to download and use the [Teams desktop client](https://teams.microsoft.com/downloads) for the full Teams experience.</span></span>

<span data-ttu-id="b56b1-113">如果 PSTN 無法使用，使用者就不會看到用來存取會議的指示，而且無法加入會議。</span><span class="sxs-lookup"><span data-stu-id="b56b1-113">If PSTN is unavailable, the user won't see the instructions for accessing the meeting and won't be able to join the meeting.</span></span>

## <a name="browser-limitations"></a><span data-ttu-id="b56b1-114">瀏覽器限制</span><span class="sxs-lookup"><span data-stu-id="b56b1-114">Browser limitations</span></span>

<span data-ttu-id="b56b1-115">在不受支援的瀏覽器上使用小組 web app 的人員將會遇到下列限制：</span><span class="sxs-lookup"><span data-stu-id="b56b1-115">People who use the Teams web app on unsupported browsers will experience the following limitations:</span></span>

- <span data-ttu-id="b56b1-116">只能透過 PSTN 連接使用音訊。</span><span class="sxs-lookup"><span data-stu-id="b56b1-116">Audio is available through a PSTN connection only.</span></span> <span data-ttu-id="b56b1-117">使用者無法使用其麥克風。</span><span class="sxs-lookup"><span data-stu-id="b56b1-117">Users can't use their microphone.</span></span>
- <span data-ttu-id="b56b1-118">使用者無法共用其相機，或查看其他參與者的影片，但可以透過影像螢幕共用來查看所呈現的內容。</span><span class="sxs-lookup"><span data-stu-id="b56b1-118">Users can't share their camera or see other participants' videos but can view presented content through image-based screen sharing.</span></span>
- <span data-ttu-id="b56b1-119">雖然使用者可以看到其他會議參與者共用的畫面，但他們無法共用其螢幕。</span><span class="sxs-lookup"><span data-stu-id="b56b1-119">Users can't share their screen, although they can see a screen that another meeting participant shares.</span></span>
- <span data-ttu-id="b56b1-120">使用者在螢幕共用會話期間無法進行控制。</span><span class="sxs-lookup"><span data-stu-id="b56b1-120">Users can't take control during a screen sharing session.</span></span>
- <span data-ttu-id="b56b1-121">使用者不會收到來電通知。</span><span class="sxs-lookup"><span data-stu-id="b56b1-121">Users won't receive incoming call notifications.</span></span>
- <span data-ttu-id="b56b1-122">如果通話中斷，會議就不會自動重新連線。</span><span class="sxs-lookup"><span data-stu-id="b56b1-122">If the call is interrupted, the meeting won't automatically reconnect.</span></span>
- <span data-ttu-id="b56b1-123">使用者無法啟動會議。</span><span class="sxs-lookup"><span data-stu-id="b56b1-123">Users can't start meetings.</span></span>

<span data-ttu-id="b56b1-124">如需有關團隊中瀏覽器支援的詳細資訊，請參閱 [小組的限制與規格](/microsoftteams/limits-specifications-teams#browsers)。</span><span class="sxs-lookup"><span data-stu-id="b56b1-124">For more information about browser support in Teams, see [Limits and specifications for Teams](/microsoftteams/limits-specifications-teams#browsers).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b56b1-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="b56b1-125">Related topics</span></span>

- [<span data-ttu-id="b56b1-126">在不受支援的瀏覽器上加入團隊會議</span><span class="sxs-lookup"><span data-stu-id="b56b1-126">Join a Teams meeting on an unsupported browser</span></span>](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)
