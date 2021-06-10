---
title: Microsoft Teams 如何使用記憶體
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: 瞭解Microsoft Teams記憶體使用量，以及為什麼桌面應用程式與 Web 應用程式之間的記憶體使用量相同。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: d218c71a0e3ecdde40559d67e1ad3a408d65a5d9
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878717"
---
# <a name="how-microsoft-teams-uses-memory"></a><span data-ttu-id="e7409-103">Microsoft Teams 如何使用記憶體</span><span class="sxs-lookup"><span data-stu-id="e7409-103">How Microsoft Teams uses memory</span></span>

<span data-ttu-id="e7409-104">有些Microsoft Teams使用者對於如何使用記憶體Teams有疑問。</span><span class="sxs-lookup"><span data-stu-id="e7409-104">Some Microsoft Teams users have questions about how Teams uses memory.</span></span> <span data-ttu-id="e7409-105">本文將說明 Teams 如何使用記憶體，以及 Teams 桌面應用程式 (應用程式) 和 Teams Web App 為何無法防止同一部電腦上其他應用程式和工作負載有足夠的記憶體以最佳方式執行。</span><span class="sxs-lookup"><span data-stu-id="e7409-105">This article describes how memory is used by Teams, and why the Teams desktop application (app) and the Teams web app do not prevent other apps and workloads on the same computer from having enough memory to run optimally.</span></span> <span data-ttu-id="e7409-106">Teams是專為使用新式 Web 技術所設計。</span><span class="sxs-lookup"><span data-stu-id="e7409-106">Teams is designed to use modern web technology.</span></span> <span data-ttu-id="e7409-107">為了達成此目的，Teams桌面用戶端是在電子上開發，它使用 Chromium來呈現。</span><span class="sxs-lookup"><span data-stu-id="e7409-107">To achieve this, the Teams desktop client was developed on Electron, which uses Chromium for rendering.</span></span> <span data-ttu-id="e7409-108">這是許多現今最熱門的瀏覽器背後的相同呈現引擎，包括 Edge 和 Chrome。</span><span class="sxs-lookup"><span data-stu-id="e7409-108">This is the same rendering engine behind many of today's most popular browsers, including Edge and Chrome.</span></span>

## <a name="how-teams-works"></a><span data-ttu-id="e7409-109">如何Teams運作</span><span class="sxs-lookup"><span data-stu-id="e7409-109">How Teams works</span></span>

<span data-ttu-id="e7409-110">Teams在電子上設計，可加快開發速度，而且在不同作業系統 Teams、Mac 和 Linux (Windows 之間維持 Teams 版本之間的) 。</span><span class="sxs-lookup"><span data-stu-id="e7409-110">Teams being designed on Electron allows for faster development, and it also maintains parity between Teams versions across different operating systems (Windows, Mac, and Linux).</span></span> <span data-ttu-id="e7409-111">這個奇偶性是有可能的，因為電子Chromium在所有版本之間維持相似的程式碼基礎。</span><span class="sxs-lookup"><span data-stu-id="e7409-111">This parity is possible because Electron and Chromium maintain a similar code base across all versions.</span></span> <span data-ttu-id="e7409-112">此架構的另一個優點，是 Web 應用程式與桌上出版Teams記憶體使用量設定檔類似。</span><span class="sxs-lookup"><span data-stu-id="e7409-112">Another advantage of this architecture is there's a similar memory usage profile between the Teams web app and the desktop version.</span></span> <span data-ttu-id="e7409-113">Web App 和桌上出版使用記憶體的方式與瀏覽器的使用方式類似。</span><span class="sxs-lookup"><span data-stu-id="e7409-113">Both the web app and the desktop versions use memory in a similar way to how a browser would use it.</span></span> <span data-ttu-id="e7409-114">有關電子的更多相關資訊，請參閱 [他們的網站](https://electronjs.org/)。</span><span class="sxs-lookup"><span data-stu-id="e7409-114">More information about Electron is available at [their Web site](https://electronjs.org/).</span></span>

<span data-ttu-id="e7409-115">請參閱[Chromium Chrome](https://www.chromium.org/developers/memory-usage-backgrounder)記憶體中的儲存體使用量和主要概[念，以](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md)瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="e7409-115">See [Chromium Memory Usage](https://www.chromium.org/developers/memory-usage-backgrounder) and [Key Concepts in Chrome Memory](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) for more information.</span></span>

<span data-ttu-id="e7409-116">下圖顯示 Windows 版 Teams 桌面應用程式與此範例中的 Teams Web 應用程式 (在 Google Chrome) 中同時使用) 。</span><span class="sxs-lookup"><span data-stu-id="e7409-116">The following image shows side-by-side memory usages of the Teams desktop app for Windows and the Teams Web app (in this example, running in Google Chrome).</span></span>

![Teams應用程式與 Web 應用程式的記憶體使用量](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a><span data-ttu-id="e7409-118">中記憶體使用量Teams</span><span class="sxs-lookup"><span data-stu-id="e7409-118">Memory usage in Teams</span></span>

<span data-ttu-id="e7409-119">瞭解系統記憶體Teams預期的行為，並瞭解真正有問題的系統記憶體問題之症狀，這一點非常重要。</span><span class="sxs-lookup"><span data-stu-id="e7409-119">It is important to understand the *expected* behavior of Teams when it comes to system memory, and to know the symptoms of truly problematic system memory issues.</span></span>

### <a name="expected-memory-usage-by-teams"></a><span data-ttu-id="e7409-120">預期記憶體使用量Teams</span><span class="sxs-lookup"><span data-stu-id="e7409-120">Expected memory usage by Teams</span></span>

<span data-ttu-id="e7409-121">無論您是在Teams或 Teams Web App 中，Chromium偵測可用的系統記憶體量，並運用足夠的記憶體來優化呈現體驗。</span><span class="sxs-lookup"><span data-stu-id="e7409-121">Whether you're running the Teams desktop app or the Teams web app, Chromium detects how much system memory is available and utilizes enough of that memory to optimize the rendering experience.</span></span> <span data-ttu-id="e7409-122">當其他應用程式或服務需要系統記憶體時，Chromium記憶體給這些程式。</span><span class="sxs-lookup"><span data-stu-id="e7409-122">When other apps or services require system memory, Chromium gives up memory to those processes.</span></span> <span data-ttu-id="e7409-123">Chromium持續Teams調整記憶體使用量，以優化Teams，而不會影響目前執行中的任何其他專案。</span><span class="sxs-lookup"><span data-stu-id="e7409-123">Chromium tunes Teams memory usage on an ongoing basis in order to optimize Teams performance without impacting anything else currently running.</span></span>

<span data-ttu-id="e7409-124">如此一來，Chromium工作負載會根據可用的系統記憶體量，使用不同的記憶體量。</span><span class="sxs-lookup"><span data-stu-id="e7409-124">In this way, similar Chromium workloads can utilize varying amounts of memory, depending on the amount of system memory that is available.</span></span>

<span data-ttu-id="e7409-125">下圖說明在四個不同的系統上Teams記憶體使用量，每個系統都有不同的可用記憶體量。</span><span class="sxs-lookup"><span data-stu-id="e7409-125">The following graph depicts memory usage by Teams on four separate systems, each with different amounts of memory available.</span></span> <span data-ttu-id="e7409-126">每一個系統正在處理類似的工作負載， (開啟並執行相同的應用程式) 。</span><span class="sxs-lookup"><span data-stu-id="e7409-126">Each of the systems is processing similar workloads (same apps open and running).</span></span>

![Teams不同系統記憶體使用量](media/teams-memory-usage.png)

<span data-ttu-id="e7409-128">當電腦有更多記憶體時，Teams就會使用該記憶體。</span><span class="sxs-lookup"><span data-stu-id="e7409-128">When computers have more memory, Teams will use that memory.</span></span> <span data-ttu-id="e7409-129">在記憶體不足的系統中，Teams使用較少。</span><span class="sxs-lookup"><span data-stu-id="e7409-129">In systems where memory is scarce, Teams will use less.</span></span>

### <a name="symptoms-of-system-memory-issues"></a><span data-ttu-id="e7409-130">系統記憶體問題之症狀</span><span class="sxs-lookup"><span data-stu-id="e7409-130">Symptoms of system memory issues</span></span>

<span data-ttu-id="e7409-131">如果您在電腦上看到下列一或多個症狀，則可能是系統記憶體問題：</span><span class="sxs-lookup"><span data-stu-id="e7409-131">If you see one or more of the following symptoms on your computer, you could have a serious system memory issue:</span></span>

- <span data-ttu-id="e7409-132">當多個大型應用程式同時執行時，會使用高記憶體。</span><span class="sxs-lookup"><span data-stu-id="e7409-132">High memory use when multiple large applications are running simultaneously.</span></span>
- <span data-ttu-id="e7409-133">系統執行速度變慢或應用程式懸空。</span><span class="sxs-lookup"><span data-stu-id="e7409-133">Slow system performance or applications hanging.</span></span>
- <span data-ttu-id="e7409-134">在所有 App 上持續使用 90% 或更高的系統記憶體使用量。</span><span class="sxs-lookup"><span data-stu-id="e7409-134">Sustained overall system memory usage of 90% or higher across all apps.</span></span> <span data-ttu-id="e7409-135">有了這個記憶體使用量，Teams將記憶體回饋給其他應用程式和工作負載。</span><span class="sxs-lookup"><span data-stu-id="e7409-135">With this amount of memory usage, Teams should be giving memory back to other apps and workloads.</span></span> <span data-ttu-id="e7409-136">持續使用 90% Teams表示系統無法提供記憶體，這表示發生問題。</span><span class="sxs-lookup"><span data-stu-id="e7409-136">Sustained memory usage of 90% could mean Teams isn't giving memory back to the system, which indicates a problem.</span></span>

<span data-ttu-id="e7409-137">下列影像顯示當系統記憶體使用量異常高時，Task Manager 中的視圖範例。</span><span class="sxs-lookup"><span data-stu-id="e7409-137">The following images show examples of views in Task Manager when system memory usage is abnormally high.</span></span>

![Teams Manager 中的記憶體使用量視圖](media/teams-memory-high-mem-process-list.png)

![Teams Manager 中的記憶體使用量圖表](media/teams-memory-high-mem-process-list2.png)
