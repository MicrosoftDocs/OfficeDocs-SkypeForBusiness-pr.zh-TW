---
title: 商務用 Skype Server 2015 應力與效能工具的常見問題
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: 商務用 Skype 2015 壓力與效能工具常見問題 (FAQ), 適用于找出支援哪些工具設定、疑難排解工具問題, 以及闡明您在執行壓力和效能工具時可能會看到的 behaviours.
ms.openlocfilehash: 36bb3e05751bd69b747d84fa563347b29362ddd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193135"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="c9fc8-103">商務用 Skype Server 2015 應力與效能工具的常見問題</span><span class="sxs-lookup"><span data-stu-id="c9fc8-103">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="c9fc8-104">商務用 Skype 2015 壓力與效能工具常見問題 (FAQ), 適用于找出支援哪些工具設定、疑難排解工具問題, 以及闡明您在執行壓力和效能工具時可能會看到的 behaviours.</span><span class="sxs-lookup"><span data-stu-id="c9fc8-104">Skype for Business 2015 Stress and Performance Tool frequently asked questions (FAQ), useful for finding out what tool configurations are supported, troubleshooting tool issues, and clarifying behaviours you may see when running the Stress and Performance tools.</span></span>
  
 <span data-ttu-id="c9fc8-105">此常見問題涵蓋有關商務用 Skype Server 2015 的一些常見問題和效能工具, 並且可能會協助您解決問題及工具設定選項。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-105">This FAQ covers some of the most frequently asked questions about the Skype for Business Server 2015 Stress and Performance tool, and may help with troubleshooting and tool configuration choices.</span></span>
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="c9fc8-106">我可以在生產中執行 LyncPerfTool 嗎？</span><span class="sxs-lookup"><span data-stu-id="c9fc8-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="c9fc8-107">建議您**不要**這麼做。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-107">This is **not** recommended.</span></span> <span data-ttu-id="c9fc8-108">此工具會影響您的生產伺服器效能、安全性和最終使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-108">The tool would impact your production server performance, security, and the end user experience.</span></span>
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a><span data-ttu-id="c9fc8-109">我是第一次登入我的使用者。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-109">I'm logging my users on for the first time.</span></span> <span data-ttu-id="c9fc8-110">為什麼我的伺服器執行的是高負載？</span><span class="sxs-lookup"><span data-stu-id="c9fc8-110">Why are my servers running a high load?</span></span>

<span data-ttu-id="c9fc8-111">使用者第一次登入時, 會在背景執行額外的作業。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-111">The first time the users log on, additional operations occur in the background.</span></span> <span data-ttu-id="c9fc8-112">因此, Microsoft SQL Server 後端伺服器的效能可能會下降。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-112">As a result, the performance on the Microsoft SQL Server Back End Server can be degraded.</span></span> <span data-ttu-id="c9fc8-113">建議您執行簡短的測試, 讓您的所有使用者都能登入, 然後重新開機用戶端, 才能開始使用工具來測量結果。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-113">It's recommended that you run a short test that logs on all of your users, and then restart the clients before you begin to measure results with the tool.</span></span> <span data-ttu-id="c9fc8-114">商務用 Skype 伺服器不支援每秒超過12個併發使用者登入會話, 但請注意, 您的伺服器可處理的實際數位取決於您的硬體設定, 且可能低於支援的值。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-114">Skype for Business Server doesn't support more than 12 concurrent user logon sessions per second, but please be aware the actual number that can be handled by your servers depends on your hardware configuration, and may be lower than the supported value.</span></span>
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="c9fc8-115">我的用戶端記憶體不足!</span><span class="sxs-lookup"><span data-stu-id="c9fc8-115">My clients are running out of memory!</span></span> <span data-ttu-id="c9fc8-116">我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="c9fc8-116">What should I do?</span></span>

<span data-ttu-id="c9fc8-117">如果用戶端記憶體不足, 您就應該減少每個商務用 Skype Server 前端池登入的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-117">If clients are running out of memory, you should reduce the number of users logged on per Skype for Business Server Front End pool.</span></span> <span data-ttu-id="c9fc8-118">如果問題持續發生, 您也可以選擇擴大前端池。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-118">You can also choose to scale out Front End pools if the problem is persistent.</span></span>
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a><span data-ttu-id="c9fc8-119">我可以在商務用 Skype 伺服器上執行這個工具嗎？</span><span class="sxs-lookup"><span data-stu-id="c9fc8-119">Can I run this tool on a Skype for Business server, itself?</span></span>

<span data-ttu-id="c9fc8-120">您不應該這麼做。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-120">You shouldn't do that.</span></span> <span data-ttu-id="c9fc8-121">此案例不受支援, 因為可能會因為二進位不相符而失敗, 也可能是因為目標是測量伺服器上的資源佔用情況。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-121">This scenario isn't supported because it may fail due to a binary mismatch, and also because the goal is to measure resource consumption on the server.</span></span> <span data-ttu-id="c9fc8-122">實際執行工具會影響伺服器效能, 並使您的資料與度量無效。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-122">Actually running the tool there would impact server performance and invalidate your data and measurements.</span></span>
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="c9fc8-123">我可以在虛擬伺服器或 Microsoft Hyper-v Server 2008/2012 上執行 LyncPerfTool 嗎？</span><span class="sxs-lookup"><span data-stu-id="c9fc8-123">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="c9fc8-124">是的, 您可以。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-124">Yes you can.</span></span>
  
## <a name="what-does-mpop-mean"></a><span data-ttu-id="c9fc8-125">MPOP 代表什麼意思？</span><span class="sxs-lookup"><span data-stu-id="c9fc8-125">What does MPOP mean?</span></span>

<span data-ttu-id="c9fc8-126">MPOP 是一種簡短的方式, 說出「多個目前狀態點」。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-126">MPOP is a shortened way of saying "multiple points of presence".</span></span> <span data-ttu-id="c9fc8-127">MPOP 是要模擬使用者從多部電腦或裝置登入商務用 Skype 2015 用戶端的情況。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-127">MPOP is meant to simulate scenarios where users are logged on to Skype for Business 2015 client from multiple machines or devices.</span></span> <span data-ttu-id="c9fc8-128">請注意, 在 LyncPerfTool 中, 每個端點都會使用預設設定檔。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-128">Be aware that, in LyncPerfTool.exe, each endpoint uses the default profile.</span></span> <span data-ttu-id="c9fc8-129">換句話說, 設定檔不會在兩個目前狀態點之間分割。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-129">In other words, the profile isn't split between two points of presence.</span></span>
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="c9fc8-130">我已開始 LyncPerfTool, 但卻沒有發生任何事。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-130">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="c9fc8-131">這是怎麼回事？</span><span class="sxs-lookup"><span data-stu-id="c9fc8-131">What's going on?</span></span>

<span data-ttu-id="c9fc8-132">檢查伺服器上的 [總工作端點] 計數器, 查看使用者是否正在連線。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-132">Check the Total Active Endpoints counter on the servers to see if the users are connecting.</span></span> <span data-ttu-id="c9fc8-133">如果使用者沒有連線, 請確認您的商務用 Skype Server 2015 設定。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-133">If the users aren't connecting, verify your Skype for Business Server 2015 configuration.</span></span> <span data-ttu-id="c9fc8-134">您通常會看到的問題是因為其中一個伺服器名稱、使用者首碼或密碼不正確。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-134">The issue you're seeing usually occurs because one of server name, user prefix, or password, is incorrect.</span></span> <span data-ttu-id="c9fc8-135">請注意, 外部用戶端應該指定存取 Proxy 與 TargetServer 值。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-135">Take note that external clients should specify Access Proxy and TargetServer values.</span></span> <span data-ttu-id="c9fc8-136">驗證設定檔中的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-136">Verify the port number in the configuration file.</span></span>
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a><span data-ttu-id="c9fc8-137">我要如何確定已測量某個專案？</span><span class="sxs-lookup"><span data-stu-id="c9fc8-137">How can I be sure that something is being measured?</span></span>

<span data-ttu-id="c9fc8-138">有 LyncPerfTool 的效能計數器可指出使用者是否要連線並執行動作, 但最簡單的方法就是要讓您以商務用 Skype 2015 用戶端登入其中一個帳戶, 並執行這些動作自己的動作。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-138">There are LyncPerfTool performance counters that indicate whether or not users are connecting and performing actions, but the easiest way to make sure actions are being measured is to log on to one of the accounts with a Skype for Business 2015 client and do those actions yourself.</span></span> <span data-ttu-id="c9fc8-139">檢查結果, 確認已採取測量。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-139">Check the results to confirm measurements were taken.</span></span>
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a><span data-ttu-id="c9fc8-140">我已安裝 Lync Server 2010 容量規劃工具和/或 Lync Server 2013 容量規劃工具。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-140">I have Lync Server 2010 Capacity Planning Tools and/or Lync Server 2013 Capacity Planning tools installed.</span></span> <span data-ttu-id="c9fc8-141">那好嗎？</span><span class="sxs-lookup"><span data-stu-id="c9fc8-141">Is that okay?</span></span>

 <span data-ttu-id="c9fc8-142">這些工具有互通性問題!</span><span class="sxs-lookup"><span data-stu-id="c9fc8-142">These tools have interoperability issues!</span></span> <span data-ttu-id="c9fc8-143">您必須卸載這些工具的所有舊版, 才能從商務用 Skype Server 2015 應力和效能工具中取得有效的資料。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-143">You must uninstall all the previous versions of these tools to get valid data from the Skype for Business Server 2015 Stress and Performance tool.</span></span>
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="c9fc8-144">壓力與效能工具會設定 CAA 通話資訊伺服器拓撲嗎？</span><span class="sxs-lookup"><span data-stu-id="c9fc8-144">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="c9fc8-145">不行, 這些工具無法執行此動作。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-145">No, the tools won't do this.</span></span> <span data-ttu-id="c9fc8-146">工具只會建立使用者、連絡人及通訊群組清單, 以模擬使用者負載。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-146">The tools only create users, contacts, and distribution lists, to simulate user load.</span></span>
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="c9fc8-147">工具支援的使用者數目上限為何？</span><span class="sxs-lookup"><span data-stu-id="c9fc8-147">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="c9fc8-148">在測試中, 我們已建立最多80000個使用者, 以及執行的測試, 其中匯總了執行這些工具的30000使用者。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-148">In testing, we've created up to a total of 80,000 users, and executed tests totaling 30,000 users running these tools.</span></span> <span data-ttu-id="c9fc8-149">我們建議您最多120000個使用者, 雖然技術限制允許使用較高的值。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-149">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher values.</span></span> <span data-ttu-id="c9fc8-150">請記住, 這些值是由您環境中的伺服器和硬體所決定。</span><span class="sxs-lookup"><span data-stu-id="c9fc8-150">Remember that these values depend on the server and hardware in your environment.</span></span>
  

