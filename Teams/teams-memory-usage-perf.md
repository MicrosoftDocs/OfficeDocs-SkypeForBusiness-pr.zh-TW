---
title: Microsoft 團隊如何使用記憶體
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Microsoft 團隊如何使用系統記憶體，以及為什麼桌面應用程式與 web 應用程式之間的記憶體使用量相同。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6dcbe03851b8dbb31cd0bd6f1b580913d4dc683d
ms.sourcegitcommit: f017e38095098d4d28c71241dddac53538be79d7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/24/2020
ms.locfileid: "41506895"
---
# <a name="how-microsoft-teams-uses-memory"></a><span data-ttu-id="d2b2d-103">Microsoft 團隊如何使用記憶體</span><span class="sxs-lookup"><span data-stu-id="d2b2d-103">How Microsoft Teams uses memory</span></span>

<span data-ttu-id="d2b2d-104">有些 Microsoft 團隊使用者有關于團隊如何使用記憶體的問題。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-104">Some Microsoft Teams users have questions about how Teams uses memory.</span></span> <span data-ttu-id="d2b2d-105">本文說明團隊如何使用記憶體，以及為什麼團隊桌面應用程式（應用程式）和團隊 web app 不會防止同一部電腦上的其他應用程式和工作負載能以最佳的方式執行。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-105">This article describes how memory is used by Teams, and why the Teams desktop application (app) and the Teams web app do not prevent other apps and workloads on the same computer from having enough memory to run optimally.</span></span> <span data-ttu-id="d2b2d-106">團隊是設計用來使用新式 web 技術的。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-106">Teams is designed to use modern web technology.</span></span> <span data-ttu-id="d2b2d-107">若要這樣做，小組桌面用戶端是在 Electron 上開發的，使用 Chromium 來轉譯。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-107">To achieve this, the Teams desktop client was developed on Electron, which uses Chromium for rendering.</span></span> <span data-ttu-id="d2b2d-108">此轉譯引擎是在如今許多最流行的瀏覽器（包括邊緣與 Chrome）之後，都是相同的轉譯引擎。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-108">This is the same rendering engine behind many of today’s most popular browsers, including Edge and Chrome.</span></span>

## <a name="how-teams-works"></a><span data-ttu-id="d2b2d-109">團隊的運作方式</span><span class="sxs-lookup"><span data-stu-id="d2b2d-109">How Teams works</span></span>

<span data-ttu-id="d2b2d-110">在 Electron 上設計的團隊可讓您更快速地進行開發，而且也會在不同的作業系統（Windows、Mac 和 Linux）之間維持團隊版本之間的同位。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-110">Teams being designed on Electron allows for faster development, and it also maintains parity between Teams versions across different operating systems (Windows, Mac, and Linux).</span></span> <span data-ttu-id="d2b2d-111">此同位是可能的，因為 Electron 和 Chromium 會在所有版本中維持相似的程式碼基底。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-111">This parity is possible because Electron and Chromium maintain a similar code base across all versions.</span></span> <span data-ttu-id="d2b2d-112">這個體系結構的另一個優點是，小組 web app 與桌上出版本之間有類似的記憶體使用量設定檔。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-112">Another advantage of this architecture is there's a similar memory usage profile between the Teams web app and the desktop version.</span></span> <span data-ttu-id="d2b2d-113">Web app 和桌上出版都使用記憶體，與瀏覽器使用的方式類似。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-113">Both the web app and the desktop versions use memory in a similar way to how a browser would use it.</span></span> <span data-ttu-id="d2b2d-114">有關 Electron 的詳細資訊可在[他們的網站](https://electronjs.org/)上使用。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-114">More information about Electron is available at [their Web site](https://electronjs.org/).</span></span>

<span data-ttu-id="d2b2d-115">如需詳細資訊，請參閱[Chrome 記憶體中](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md)的[Chromium 記憶體使用量](https://www.chromium.org/developers/memory-usage-backgrounder)與重要概念。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-115">See [Chromium Memory Usage](https://www.chromium.org/developers/memory-usage-backgrounder) and [Key Concepts in Chrome Memory](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) for more information.</span></span>

<span data-ttu-id="d2b2d-116">下列影像顯示適用于 Windows 和小組 Web app （在此範例中，在 Google Chrome 中執行）的小組桌面應用程式的並排記憶體使用量。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-116">The following image shows side-by-side memory usages of the Teams desktop app for Windows and the Teams Web app (in this example, running in Google Chrome).</span></span>

![團隊桌面應用程式和 Web app 記憶體使用量](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a><span data-ttu-id="d2b2d-118">團隊中的記憶體使用量</span><span class="sxs-lookup"><span data-stu-id="d2b2d-118">Memory usage in Teams</span></span>

<span data-ttu-id="d2b2d-119">瞭解團隊在系統記憶體中的*預期*行為，並瞭解真正問題的系統記憶體問題的症狀，這一點很重要。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-119">It is important to understand the *expected* behavior of Teams when it comes to system memory, and to know the symptoms of truly problematic system memory issues.</span></span>

### <a name="expected-memory-usage-by-teams"></a><span data-ttu-id="d2b2d-120">小組預期的記憶體使用量</span><span class="sxs-lookup"><span data-stu-id="d2b2d-120">Expected memory usage by Teams</span></span>

<span data-ttu-id="d2b2d-121">不論您執行的是團隊桌面應用程式還是團隊 web app，Chromium 會偵測到有多少可用的系統記憶體，並充分利用該記憶體來優化轉譯體驗。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-121">Whether you're running the Teams desktop app or the Teams web app, Chromium detects how much system memory is available and utilizes enough of that memory to optimize the rendering experience.</span></span> <span data-ttu-id="d2b2d-122">當其他 app 或服務需要系統記憶體時，Chromium 會為那些進程帶來記憶體。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-122">When other apps or services require system memory, Chromium gives up memory to those processes.</span></span> <span data-ttu-id="d2b2d-123">Chromium [調整小組的記憶體使用量]，以優化團隊效能，而不會影響目前執行的任何其他專案。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-123">Chromium tunes Teams memory usage on an ongoing basis in order to optimize Teams performance without impacting anything else currently running.</span></span>

<span data-ttu-id="d2b2d-124">如此一來，類似的 Chromium 工作負載可能會使用不同的記憶體量，視可用的系統記憶體數量而定。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-124">In this way, similar Chromium workloads can utilize varying amounts of memory, depending on the amount of system memory that is available.</span></span>

<span data-ttu-id="d2b2d-125">下圖說明四個不同系統上的小組記憶體使用量，每個都有不同的可用記憶體量。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-125">The following graph depicts memory usage by Teams on four separate systems, each with different amounts of memory available.</span></span> <span data-ttu-id="d2b2d-126">每個系統都會處理相似的工作負荷（相同的 app 開啟並執行）。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-126">Each of the systems is processing similar workloads (same apps open and running).</span></span>

![團隊在不同系統上的記憶體使用量](media/teams-memory-usage.png)

<span data-ttu-id="d2b2d-128">當電腦有更多記憶體時，小組會使用該記憶體。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-128">When computers have more memory, Teams will use that memory.</span></span> <span data-ttu-id="d2b2d-129">在記憶體不足的系統中，小組將會使用較少的時間。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-129">In systems where memory is scarce, Teams will use less.</span></span> 

### <a name="symptoms-of-system-memory-issues"></a><span data-ttu-id="d2b2d-130">系統記憶體問題的症狀</span><span class="sxs-lookup"><span data-stu-id="d2b2d-130">Symptoms of system memory issues</span></span>

<span data-ttu-id="d2b2d-131">如果您在電腦上看到下列一或多個症狀，可能會有嚴重的系統記憶體問題：</span><span class="sxs-lookup"><span data-stu-id="d2b2d-131">If you see one or more of the following symptoms on your computer, you could have a serious system memory issue:</span></span>

- <span data-ttu-id="d2b2d-132">當多個大型應用程式同時執行時，會使用高記憶體。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-132">High memory use when multiple large applications are running simultaneously.</span></span>
- <span data-ttu-id="d2b2d-133">系統效能變慢或應用程式掛起。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-133">Slow system performance or applications hanging.</span></span>
- <span data-ttu-id="d2b2d-134">所有 app 在90% 或更高的整體系統記憶體使用量。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-134">Sustained overall system memory usage of 90% or higher across all apps.</span></span> <span data-ttu-id="d2b2d-135">使用這個記憶體使用量時，小組應該將記憶體傳回其他 app 和工作負載。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-135">With this amount of memory usage, Teams should be giving memory back to other apps and workloads.</span></span> <span data-ttu-id="d2b2d-136">持續記憶體使用量90% 可能意味著團隊沒有將記憶體傳回給系統，這表示發生問題。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-136">Sustained memory usage of 90% could mean Teams isn't giving memory back to the system, which indicates a problem.</span></span>

<span data-ttu-id="d2b2d-137">下列影像顯示在系統記憶體使用量異常高時，工作管理員中的視圖範例。</span><span class="sxs-lookup"><span data-stu-id="d2b2d-137">The following images show examples of views in Task Manager when system memory usage is abnormally high.</span></span>

![[工作管理員] 中的小組記憶體使用量視圖](media/teams-memory-high-mem-process-list.png)

![[團隊記憶體使用量] 圖形在 [工作管理員] 中](media/teams-memory-high-mem-process-list2.png)
