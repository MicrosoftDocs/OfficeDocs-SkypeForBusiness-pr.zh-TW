---
title: 商務用 Skype Server 2015 的常見問題解答和效能工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ce18db60-5f6b-423d-bc41-91e7c80fb7e3
description: 商務用 Skype 2015 壓力和效能工具常見問題解答 (常見問題) ，可找出支援哪些工具設定、疑難排解工具問題，並闡明當您執行壓力和效能工具時，您可能會看到的 behaviours。
ms.openlocfilehash: 4c9a8acca21e4e4bb8f6b6e0a5ff1f68484e6b1c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814963"
---
# <a name="faq-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="9df56-103">商務用 Skype Server 2015 的常見問題解答和效能工具</span><span class="sxs-lookup"><span data-stu-id="9df56-103">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="9df56-104">商務用 Skype 2015 壓力和效能工具常見問題解答 (常見問題) ，可找出支援哪些工具設定、疑難排解工具問題，並闡明當您執行壓力和效能工具時，您可能會看到的 behaviours。</span><span class="sxs-lookup"><span data-stu-id="9df56-104">Skype for Business 2015 Stress and Performance Tool frequently asked questions (FAQ), useful for finding out what tool configurations are supported, troubleshooting tool issues, and clarifying behaviours you may see when running the Stress and Performance tools.</span></span>
  
 <span data-ttu-id="9df56-105">此 FAQ 涵蓋有關商務用 Skype Server 2015 壓力和效能工具的常見問題，而且可能會協助疑難排解及工具的設定選項。</span><span class="sxs-lookup"><span data-stu-id="9df56-105">This FAQ covers some of the most frequently asked questions about the Skype for Business Server 2015 Stress and Performance tool, and may help with troubleshooting and tool configuration choices.</span></span>
  
## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="9df56-106">我可以在生產環境中執行 LyncPerfTool.exe 嗎？</span><span class="sxs-lookup"><span data-stu-id="9df56-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="9df56-107">建議您 **不要** 這麼做。</span><span class="sxs-lookup"><span data-stu-id="9df56-107">This is **not** recommended.</span></span> <span data-ttu-id="9df56-108">工具會影響實際執行伺服器的效能、安全性和使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="9df56-108">The tool would impact your production server performance, security, and the end user experience.</span></span>
  
## <a name="im-logging-my-users-on-for-the-first-time-why-are-my-servers-running-a-high-load"></a><span data-ttu-id="9df56-109">我是第一次登入我的使用者。</span><span class="sxs-lookup"><span data-stu-id="9df56-109">I'm logging my users on for the first time.</span></span> <span data-ttu-id="9df56-110">為什麼伺服器的負載很高？</span><span class="sxs-lookup"><span data-stu-id="9df56-110">Why are my servers running a high load?</span></span>

<span data-ttu-id="9df56-111">使用者第一次登入時，會在後臺進行其他作業。</span><span class="sxs-lookup"><span data-stu-id="9df56-111">The first time the users log on, additional operations occur in the background.</span></span> <span data-ttu-id="9df56-112">因此，Microsoft SQL Server 後端伺服器的效能可能會降級。</span><span class="sxs-lookup"><span data-stu-id="9df56-112">As a result, the performance on the Microsoft SQL Server Back End Server can be degraded.</span></span> <span data-ttu-id="9df56-113">建議您執行簡短的測試，讓您在所有的使用者上登入，然後在開始使用工具測量結果之前重新開機用戶端。</span><span class="sxs-lookup"><span data-stu-id="9df56-113">It's recommended that you run a short test that logs on all of your users, and then restart the clients before you begin to measure results with the tool.</span></span> <span data-ttu-id="9df56-114">商務用 Skype 伺服器不支援每秒超過12個同時使用者登入會話，但是請注意，您的伺服器可以處理的實際數目取決於您的硬體設定，而且可能會低於支援的值。</span><span class="sxs-lookup"><span data-stu-id="9df56-114">Skype for Business Server doesn't support more than 12 concurrent user logon sessions per second, but please be aware the actual number that can be handled by your servers depends on your hardware configuration, and may be lower than the supported value.</span></span>
  
## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="9df56-115">我的用戶端記憶體不足！</span><span class="sxs-lookup"><span data-stu-id="9df56-115">My clients are running out of memory!</span></span> <span data-ttu-id="9df56-116">我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="9df56-116">What should I do?</span></span>

<span data-ttu-id="9df56-117">如果用戶端記憶體不足，您應該減少每個商務用 Skype Server 前端集區登入的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="9df56-117">If clients are running out of memory, you should reduce the number of users logged on per Skype for Business Server Front End pool.</span></span> <span data-ttu-id="9df56-118">如果問題持續發生，您也可以選擇擴充前端集區。</span><span class="sxs-lookup"><span data-stu-id="9df56-118">You can also choose to scale out Front End pools if the problem is persistent.</span></span>
  
## <a name="can-i-run-this-tool-on-a-skype-for-business-server-itself"></a><span data-ttu-id="9df56-119">我是否可以在商務用 Skype server 上執行此工具？</span><span class="sxs-lookup"><span data-stu-id="9df56-119">Can I run this tool on a Skype for Business server, itself?</span></span>

<span data-ttu-id="9df56-120">您不應該這麼做。</span><span class="sxs-lookup"><span data-stu-id="9df56-120">You shouldn't do that.</span></span> <span data-ttu-id="9df56-121">此案例不受支援，因為二進位不相符，也可能會因為目標是度量伺服器上的資源消耗。</span><span class="sxs-lookup"><span data-stu-id="9df56-121">This scenario isn't supported because it may fail due to a binary mismatch, and also because the goal is to measure resource consumption on the server.</span></span> <span data-ttu-id="9df56-122">實際執行工具會影響伺服器效能，並使您的資料和度量無效。</span><span class="sxs-lookup"><span data-stu-id="9df56-122">Actually running the tool there would impact server performance and invalidate your data and measurements.</span></span>
  
## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="9df56-123">我可以在虛擬伺服器或 Microsoft Hyper-V Server 2008/2012 上執行 LyncPerfTool.exe 嗎？</span><span class="sxs-lookup"><span data-stu-id="9df56-123">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="9df56-124">是您可以。</span><span class="sxs-lookup"><span data-stu-id="9df56-124">Yes you can.</span></span>
  
## <a name="what-does-mpop-mean"></a><span data-ttu-id="9df56-125">MPOP 的含義為何？</span><span class="sxs-lookup"><span data-stu-id="9df56-125">What does MPOP mean?</span></span>

<span data-ttu-id="9df56-126">MPOP 是一種簡短的方式，說「多點顯示」。</span><span class="sxs-lookup"><span data-stu-id="9df56-126">MPOP is a shortened way of saying "multiple points of presence".</span></span> <span data-ttu-id="9df56-127">MPOP 是要模擬使用者從多部機器或裝置登入商務用 Skype 2015 用戶端的案例。</span><span class="sxs-lookup"><span data-stu-id="9df56-127">MPOP is meant to simulate scenarios where users are logged on to Skype for Business 2015 client from multiple machines or devices.</span></span> <span data-ttu-id="9df56-128">請注意，在 LyncPerfTool.exe 中，每個端點都使用預設設定檔。</span><span class="sxs-lookup"><span data-stu-id="9df56-128">Be aware that, in LyncPerfTool.exe, each endpoint uses the default profile.</span></span> <span data-ttu-id="9df56-129">換句話說，設定檔不會在兩個目前狀態點間分割。</span><span class="sxs-lookup"><span data-stu-id="9df56-129">In other words, the profile isn't split between two points of presence.</span></span>
  
## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="9df56-130">我已開始 LyncPerfTool.exe 但不會發生任何情況。</span><span class="sxs-lookup"><span data-stu-id="9df56-130">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="9df56-131">What's going on?</span><span class="sxs-lookup"><span data-stu-id="9df56-131">What's going on?</span></span>

<span data-ttu-id="9df56-132">檢查伺服器上的作用中端點計數器總數，以查看使用者是否正在連線。</span><span class="sxs-lookup"><span data-stu-id="9df56-132">Check the Total Active Endpoints counter on the servers to see if the users are connecting.</span></span> <span data-ttu-id="9df56-133">如果使用者未連接，請驗證商務用 Skype Server 2015 設定。</span><span class="sxs-lookup"><span data-stu-id="9df56-133">If the users aren't connecting, verify your Skype for Business Server 2015 configuration.</span></span> <span data-ttu-id="9df56-134">您所看到的問題通常是因為其中一個伺服器名稱、使用者前置詞或密碼不正確。</span><span class="sxs-lookup"><span data-stu-id="9df56-134">The issue you're seeing usually occurs because one of server name, user prefix, or password, is incorrect.</span></span> <span data-ttu-id="9df56-135">請注意，外部用戶端應指定 Access Proxy 和 TargetServer 值。</span><span class="sxs-lookup"><span data-stu-id="9df56-135">Take note that external clients should specify Access Proxy and TargetServer values.</span></span> <span data-ttu-id="9df56-136">確認設定檔中的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="9df56-136">Verify the port number in the configuration file.</span></span>
  
## <a name="how-can-i-be-sure-that-something-is-being-measured"></a><span data-ttu-id="9df56-137">如何確定已度量專案？</span><span class="sxs-lookup"><span data-stu-id="9df56-137">How can I be sure that something is being measured?</span></span>

<span data-ttu-id="9df56-138">有 LyncPerfTool 的效能計數器會指出使用者是否連線並執行動作，但確定行動的最簡單方法，就是以商務用 Skype 2015 用戶端登入其中一個帳戶，並自行執行這些動作。</span><span class="sxs-lookup"><span data-stu-id="9df56-138">There are LyncPerfTool performance counters that indicate whether or not users are connecting and performing actions, but the easiest way to make sure actions are being measured is to log on to one of the accounts with a Skype for Business 2015 client and do those actions yourself.</span></span> <span data-ttu-id="9df56-139">檢查結果，以確認已採取度量。</span><span class="sxs-lookup"><span data-stu-id="9df56-139">Check the results to confirm measurements were taken.</span></span>
  
## <a name="i-have-lync-server-2010-capacity-planning-tools-andor-lync-server-2013-capacity-planning-tools-installed-is-that-okay"></a><span data-ttu-id="9df56-140">我已安裝 Lync Server 2010 容量規劃工具和/或 Lync Server 2013 容量規劃工具。</span><span class="sxs-lookup"><span data-stu-id="9df56-140">I have Lync Server 2010 Capacity Planning Tools and/or Lync Server 2013 Capacity Planning tools installed.</span></span> <span data-ttu-id="9df56-141">這好嗎？</span><span class="sxs-lookup"><span data-stu-id="9df56-141">Is that okay?</span></span>

 <span data-ttu-id="9df56-142">這些工具有互通性問題！</span><span class="sxs-lookup"><span data-stu-id="9df56-142">These tools have interoperability issues!</span></span> <span data-ttu-id="9df56-143">您必須卸載所有舊版工具，才能從商務用 Skype Server 2015 壓力和效能工具取得有效的資料。</span><span class="sxs-lookup"><span data-stu-id="9df56-143">You must uninstall all the previous versions of these tools to get valid data from the Skype for Business Server 2015 Stress and Performance tool.</span></span>
  
## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="9df56-144">壓力和效能工具是否會設定 CAA 的呼叫資訊伺服器拓撲？</span><span class="sxs-lookup"><span data-stu-id="9df56-144">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="9df56-145">否，工具不會這麼做。</span><span class="sxs-lookup"><span data-stu-id="9df56-145">No, the tools won't do this.</span></span> <span data-ttu-id="9df56-146">工具只會建立使用者、連絡人及通訊群組清單，以模擬使用者負載。</span><span class="sxs-lookup"><span data-stu-id="9df56-146">The tools only create users, contacts, and distribution lists, to simulate user load.</span></span>
  
## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="9df56-147">工具支援的使用者數目上限為何？</span><span class="sxs-lookup"><span data-stu-id="9df56-147">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="9df56-148">在測試中，我們已建立最多80000個使用者，以及執行這些工具的30000使用者所執行的測試。</span><span class="sxs-lookup"><span data-stu-id="9df56-148">In testing, we've created up to a total of 80,000 users, and executed tests totaling 30,000 users running these tools.</span></span> <span data-ttu-id="9df56-149">我們建議最多120000個使用者，但技術限制允許更高的值。</span><span class="sxs-lookup"><span data-stu-id="9df56-149">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher values.</span></span> <span data-ttu-id="9df56-150">請記住，這些值取決於環境中的伺服器和硬體。</span><span class="sxs-lookup"><span data-stu-id="9df56-150">Remember that these values depend on the server and hardware in your environment.</span></span>
  

