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
ms.openlocfilehash: a1b756cfdb56de533d4dd170f301dc38e4b3b529
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308166"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="0ca90-103">在 Microsoft 團隊中使用 NDI®技術</span><span class="sxs-lookup"><span data-stu-id="0ca90-103">Use NDI® technology in Microsoft Teams</span></span>

 <span data-ttu-id="0ca90-104">NewTek NDI® (網路裝置介面) 技術是一種連線媒體裝置的新式方案， (例如畫室式相機和混音器) 。</span><span class="sxs-lookup"><span data-stu-id="0ca90-104">NewTek NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="0ca90-105">NDI®技術不是使用物理連線，而是透過本機內部網路（包括本機電腦）來實現連線。</span><span class="sxs-lookup"><span data-stu-id="0ca90-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="0ca90-106">NDI®技術已成為一個標準的工業方案，可為數據流製作即時內容，並在專業的廣播世界中取得重要的認識與採納。</span><span class="sxs-lookup"><span data-stu-id="0ca90-106">NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="0ca90-107">Skype 先前已在2018中新增 NDI® out 功能至 Skype。</span><span class="sxs-lookup"><span data-stu-id="0ca90-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="0ca90-108">Microsoft 團隊使用這個功能來改善會議體驗。</span><span class="sxs-lookup"><span data-stu-id="0ca90-108">Microsoft Teams uses this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="0ca90-109">NDI®技術受限於局域網，且只能看作是生產工作流程的一部分，而不是廣播方案。</span><span class="sxs-lookup"><span data-stu-id="0ca90-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="0ca90-110">開啟 NDI®技術</span><span class="sxs-lookup"><span data-stu-id="0ca90-110">Turn on NDI® technology</span></span>

<span data-ttu-id="0ca90-111">NDI®技術需要為使用者開啟兩個步驟。</span><span class="sxs-lookup"><span data-stu-id="0ca90-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="0ca90-112">租使用者管理員必須在 CsTeamsMeetingPolicy 中啟用 ' AllowNDIStreaming」屬性。</span><span class="sxs-lookup"><span data-stu-id="0ca90-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="0ca90-113">此變更已填入之後，使用者必須從 [**設定**] 許可權開啟其特定用戶端的 NDI®技術  >  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="0ca90-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="0ca90-114">當使用者加入會議時，他們會看到一則訊息，通知他們正在廣播會議。</span><span class="sxs-lookup"><span data-stu-id="0ca90-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="0ca90-115">如果使用者不想納入廣播，他們將需要從會議中除去。</span><span class="sxs-lookup"><span data-stu-id="0ca90-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="0ca90-116">下圖顯示使用者在團隊會議中看到的橫幅訊息。</span><span class="sxs-lookup"><span data-stu-id="0ca90-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![在團隊會議中顯示的 NDI®技術橫幅的影像。](media/NDI-disclosure.png)

<span data-ttu-id="0ca90-118">橫幅有 [Microsoft 隱私權原則](https://aka.ms/teamsprivacy)的連結。</span><span class="sxs-lookup"><span data-stu-id="0ca90-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="0ca90-119">支援的區域設定和使用者類型</span><span class="sxs-lookup"><span data-stu-id="0ca90-119">Supported locales and user types</span></span>

<span data-ttu-id="0ca90-120">NDI®技術在所有地區設定中都受到支援。</span><span class="sxs-lookup"><span data-stu-id="0ca90-120">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="0ca90-121">下列使用者包含在 NDI®技術資料流程中，但不是所有使用者都可以存取 NDI®技術資料流程：</span><span class="sxs-lookup"><span data-stu-id="0ca90-121">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="0ca90-122">受租使用者-完整支援，根據會議原則所控制的響鈴/tenantId/userId (傳送) </span><span class="sxs-lookup"><span data-stu-id="0ca90-122">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="0ca90-123">同盟-即使在) <sup>1</sup>上有 NDI®技術，也沒有資料流程存取 (</span><span class="sxs-lookup"><span data-stu-id="0ca90-123">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="0ca90-124">Freemium-沒有資料流程存取權</span><span class="sxs-lookup"><span data-stu-id="0ca90-124">Freemium - no stream access</span></span>
- <span data-ttu-id="0ca90-125">匿名–無資料流程存取</span><span class="sxs-lookup"><span data-stu-id="0ca90-125">Anonymous – no stream access</span></span>
- <span data-ttu-id="0ca90-126">來賓–無資料流程存取</span><span class="sxs-lookup"><span data-stu-id="0ca90-126">Guest – no stream access</span></span>  

<span data-ttu-id="0ca90-127"><sup>1</sup> 台裝置的 NDI®技術設定預設為開啟。</span><span class="sxs-lookup"><span data-stu-id="0ca90-127"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="0ca90-128">如果會議參與者使用的裝置的 NDI®技術關閉，他們必須開啟 NDI®技術。</span><span class="sxs-lookup"><span data-stu-id="0ca90-128">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>
