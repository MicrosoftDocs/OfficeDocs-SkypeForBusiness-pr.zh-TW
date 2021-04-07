---
title: 在 Microsoft Teams 中使用 NDI
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 中使用 NDI。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e26c6a7ad92353e083c67d0dad777e980a83fdfe
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598462"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a><span data-ttu-id="8a3ce-103">在 Microsoft Teams ®使用 NDI®技術</span><span class="sxs-lookup"><span data-stu-id="8a3ce-103">Use NDI® technology in Microsoft Teams</span></span>

 <span data-ttu-id="8a3ce-104">NewTek NDI® (網路裝置介面) 技術是連接媒體裝置的新解決方案， (例如工作室相機和混頻) 。</span><span class="sxs-lookup"><span data-stu-id="8a3ce-104">NewTek NDI® (Network Device Interface) technology is a modern solution for connecting media devices (such as a studio camera and mixer).</span></span> <span data-ttu-id="8a3ce-105">NDI 技術可®內部網路 ，包括本機電腦上，而非使用實體連接。</span><span class="sxs-lookup"><span data-stu-id="8a3ce-105">Instead of using physical connections, NDI® technology enables connectivity over a local intranet, including on a local machine.</span></span>

<span data-ttu-id="8a3ce-106">NDI®技術已成為為數據流製作即時內容的標準產業解決方案，並獲得了專業廣播業界的顯著認知和採用。</span><span class="sxs-lookup"><span data-stu-id="8a3ce-106">NDI® technology has become a standard industry solution for producing live content for streams and has gained significant awareness and adoption in the professional broadcast world.</span></span>

<span data-ttu-id="8a3ce-107">Skype 先前于 2018 ®新增 NDI 和 out 功能至 Skype。</span><span class="sxs-lookup"><span data-stu-id="8a3ce-107">Skype previously added NDI®-out functionality to Skype in late 2018.</span></span> <span data-ttu-id="8a3ce-108">Microsoft Teams 會使用這項功能來改善會議體驗。</span><span class="sxs-lookup"><span data-stu-id="8a3ce-108">Microsoft Teams uses this functionality to improve the meeting experience.</span></span>

<span data-ttu-id="8a3ce-109">NDI®僅限本地網路，只應視為生產工作流程的一部分，而非廣播解決方案。</span><span class="sxs-lookup"><span data-stu-id="8a3ce-109">NDI® technology is limited to a local network and should only be considered a part of the production workflow, not a broadcast solution.</span></span>

## <a name="turn-on-ndi-technology"></a><span data-ttu-id="8a3ce-110">開啟 NDI®技術</span><span class="sxs-lookup"><span data-stu-id="8a3ce-110">Turn on NDI® technology</span></span>

<span data-ttu-id="8a3ce-111">NDI®使用者需要開啟兩個步驟。</span><span class="sxs-lookup"><span data-stu-id="8a3ce-111">NDI® technology requires two steps to be turned on for a user.</span></span>

1. <span data-ttu-id="8a3ce-112">租使用者系統管理員必須在 CsTeamsMeetingPolicy 中啟用 'AllowNDIStreaming' 屬性。</span><span class="sxs-lookup"><span data-stu-id="8a3ce-112">The tenant admin must enable the 'AllowNDIStreaming' property in CsTeamsMeetingPolicy.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. <span data-ttu-id="8a3ce-113">完成此變更之後，使用者必須從設定許可權開啟其®用戶端的 NDI®\*\*\*\*  >  **技術**。</span><span class="sxs-lookup"><span data-stu-id="8a3ce-113">After this change has populated, the end user must turn on NDI® technology for their specific client from **Settings** > **Permissions**.</span></span>

<span data-ttu-id="8a3ce-114">當使用者加入會議時，會看到一則訊息，通知他們會議正在廣播中。</span><span class="sxs-lookup"><span data-stu-id="8a3ce-114">When a user joins a meeting, they'll see a message that notifies them that the meeting is being broadcast.</span></span> <span data-ttu-id="8a3ce-115">如果使用者不想包含在廣播中，則需要從會議刪除。</span><span class="sxs-lookup"><span data-stu-id="8a3ce-115">If users don’t want to be included in the broadcast, they’ll need to drop from the meeting.</span></span>

<span data-ttu-id="8a3ce-116">下圖顯示使用者在 Teams 會議看到的橫幅訊息。</span><span class="sxs-lookup"><span data-stu-id="8a3ce-116">The following image shows the banner message that a user sees in a Teams meeting.</span></span>

![he NDI® Teams 會議顯示的技術橫幅。](media/NDI-disclosure.png)

<span data-ttu-id="8a3ce-118">橫幅有 Microsoft [隱私權政策的連結](https://aka.ms/teamsprivacy)。</span><span class="sxs-lookup"><span data-stu-id="8a3ce-118">The banner has a link to the [Microsoft privacy policy](https://aka.ms/teamsprivacy).</span></span>

> [!NOTE]
> <span data-ttu-id="8a3ce-119">NDI®只會啟用每個會話。</span><span class="sxs-lookup"><span data-stu-id="8a3ce-119">NDI® is activated per session only.</span></span> <span data-ttu-id="8a3ce-120">下次登入時，使用者必須先啟用，才能使用 NDI®。</span><span class="sxs-lookup"><span data-stu-id="8a3ce-120">On the next login, the user must activate it before using NDI®.</span></span>

## <a name="supported-locales-and-user-types"></a><span data-ttu-id="8a3ce-121">支援的地區設置和使用者類型</span><span class="sxs-lookup"><span data-stu-id="8a3ce-121">Supported locales and user types</span></span>

<span data-ttu-id="8a3ce-122">NDI®支援所有地區。</span><span class="sxs-lookup"><span data-stu-id="8a3ce-122">NDI® technology is supported in all locales.</span></span> <span data-ttu-id="8a3ce-123">下列使用者包含在 NDI®技術流中，但並非所有使用者都可以存取 NDI®技術流：</span><span class="sxs-lookup"><span data-stu-id="8a3ce-123">The following users are included in an NDI® technology stream, but not all users can access the NDI® technology stream:</span></span>

- <span data-ttu-id="8a3ce-124">租使用者內 – 完全支援，根據 Ring/tenantId/userId (由會議策略) </span><span class="sxs-lookup"><span data-stu-id="8a3ce-124">In-tenant – full support, delivered based on ring/tenantId/userId (controlled by Meetings Policy)</span></span>
- <span data-ttu-id="8a3ce-125">聯合 – 即使<sup>1</sup> (有 NDI®，也) 存取</span><span class="sxs-lookup"><span data-stu-id="8a3ce-125">Federated – no stream access (even when they have NDI® technology on)<sup>1</sup></span></span>
- <span data-ttu-id="8a3ce-126">進位版 - 沒有串流存取</span><span class="sxs-lookup"><span data-stu-id="8a3ce-126">Premium - no stream access</span></span>
- <span data-ttu-id="8a3ce-127">匿名 – 沒有串流存取</span><span class="sxs-lookup"><span data-stu-id="8a3ce-127">Anonymous – no stream access</span></span>
- <span data-ttu-id="8a3ce-128">來賓 – 沒有串流存取</span><span class="sxs-lookup"><span data-stu-id="8a3ce-128">Guest – no stream access</span></span>  

<span data-ttu-id="8a3ce-129"><sup>1</sup> 裝置預設為® NDI®技術設定。</span><span class="sxs-lookup"><span data-stu-id="8a3ce-129"><sup>1</sup> Devices have an NDI® technology setting that is on by default.</span></span> <span data-ttu-id="8a3ce-130">如果會議參與者使用具有 NDI ®關閉的裝置，他們必須開啟 NDI®技術。</span><span class="sxs-lookup"><span data-stu-id="8a3ce-130">If a meeting participant is using a device with NDI® technology off, they'll need to turn on NDI® technology.</span></span>
