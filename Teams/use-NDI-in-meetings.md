---
title: 在 Microsoft 團隊中使用 NDI
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中使用 NDI。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: d971a7c9e44e2fbf7c3d2500f237e3755c5f89d0
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522900"
---
# <a name="use-ndi-in-microsoft-teams"></a><span data-ttu-id="25e66-103">在 Microsoft 團隊中使用 NDI</span><span class="sxs-lookup"><span data-stu-id="25e66-103">Use NDI in Microsoft Teams</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="25e66-104">網路裝置介面（NDI）是一種連線媒體裝置（例如畫室式相機和混音器）的新式方案。</span><span class="sxs-lookup"><span data-stu-id="25e66-104">Network Device Interface (NDI) is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="25e66-105">NDI 會透過本機內部網路（包括本機電腦）來啟用連線，而不是使用物理連線。</span><span class="sxs-lookup"><span data-stu-id="25e66-105">Instead of using physical connections, NDI enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="25e66-106">NewTek NDI®已成為一個標準的工業方案，可為數據流製作即時內容，並在專業的廣播世界中取得重要的認識與採納。</span><span class="sxs-lookup"><span data-stu-id="25e66-106">NewTek NDI® has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="25e66-107">Skype 先前已在晚2018中新增 NDI Out 功能至 Skype。</span><span class="sxs-lookup"><span data-stu-id="25e66-107">Skype previously added NDI-Out functionality to Skype in late 2018.</span></span> <span data-ttu-id="25e66-108">Microsoft 團隊利用此功能來改善會議體驗。</span><span class="sxs-lookup"><span data-stu-id="25e66-108">Microsoft Teams leverages this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="25e66-109">NDI 受限於局域網，且只能看作是生產工作流程的一部分，而不是廣播方案。</span><span class="sxs-lookup"><span data-stu-id="25e66-109">NDI is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi"></a><span data-ttu-id="25e66-110">開啟 NDI</span><span class="sxs-lookup"><span data-stu-id="25e66-110">Turn on NDI</span></span>

<span data-ttu-id="25e66-111">NDI 需要為使用者開啟兩個步驟。</span><span class="sxs-lookup"><span data-stu-id="25e66-111">NDI requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="25e66-112">租使用者管理員必須啟用功能標誌 enableStreamingCallsOverNdi。</span><span class="sxs-lookup"><span data-stu-id="25e66-112">The tenant admin must enable the feature flag enableStreamingCallsOverNdi.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="25e66-113">在此變更已填入之後，使用者必須從 [**設定**] 許可權開啟其特定用戶端的 NDI  >  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="25e66-113">After this change has populated, the end user must turn on NDI for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="25e66-114">當使用者加入會議時，他們會看到一則訊息，通知他們正在廣播會議。</span><span class="sxs-lookup"><span data-stu-id="25e66-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="25e66-115">如果使用者不想納入廣播，他們將需要從會議中除去。</span><span class="sxs-lookup"><span data-stu-id="25e66-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="25e66-116">下圖顯示使用者在團隊會議中看到的橫幅訊息。</span><span class="sxs-lookup"><span data-stu-id="25e66-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![顯示在團隊會議中的 NDI 橫幅影像。](media/NDI-disclosure.png)

<span data-ttu-id="25e66-118">橫幅有[Microsoft 隱私權原則](https://support.skype.com/faq/FA34853/what-is-skype-for-content-creators?q=ndi)的連結。</span><span class="sxs-lookup"><span data-stu-id="25e66-118">The banner has a link to the [Microsoft privacy policy](https://support.skype.com/faq/FA34853/what-is-skype-for-content-creators?q=ndi).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="25e66-119">支援的區域設定和使用者類型</span><span class="sxs-lookup"><span data-stu-id="25e66-119">Supported locales and user types</span></span>

<span data-ttu-id="25e66-120">NDI 在所有地區設定中都受支援。</span><span class="sxs-lookup"><span data-stu-id="25e66-120">NDI is supported in all locales.</span></span> <span data-ttu-id="25e66-121">NDI 會議支援下列使用者：</span><span class="sxs-lookup"><span data-stu-id="25e66-121">The following users are supported in an NDI meeting:</span></span>

- <span data-ttu-id="25e66-122">租使用者-完全支援，根據響鈴/tenantId/userId （由會議原則 + 功能標誌控制）提供。</span><span class="sxs-lookup"><span data-stu-id="25e66-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy + Feature Flag)</span></span>
- <span data-ttu-id="25e66-123">同盟–否（即使已開啟 NDI）<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="25e66-123">Federated – no (even when they have NDI on)<sup>1</sup></span></span>
- <span data-ttu-id="25e66-124">Freemium-否（預設值）</span><span class="sxs-lookup"><span data-stu-id="25e66-124">Freemium - no (default value)</span></span>
- <span data-ttu-id="25e66-125">匿名–否（預設值）</span><span class="sxs-lookup"><span data-stu-id="25e66-125">Anonymous – no (default value)</span></span>
- <span data-ttu-id="25e66-126">來賓–否（預設值）</span><span class="sxs-lookup"><span data-stu-id="25e66-126">Guest – no  (default value)</span></span>

<span data-ttu-id="25e66-127"><sup>1</sup>個裝置預設為開啟的 NDI 設定。</span><span class="sxs-lookup"><span data-stu-id="25e66-127"><sup>1</sup> Devices have an NDI setting that is on by default.</span></span> <span data-ttu-id="25e66-128">如果會議參與者使用的裝置有 NDI [關閉]，就必須開啟 NDI。</span><span class="sxs-lookup"><span data-stu-id="25e66-128">If a meeting participant is using a device with NDI off, they'll need to turn on NDI.</span></span>
