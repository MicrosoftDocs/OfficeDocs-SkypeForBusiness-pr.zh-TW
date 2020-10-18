---
title: Lync Server 2013 應力和效能工具常見問題
description: Lync Server 2013 壓力和效能工具常見問題解答。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 716325390bc33df209be3bdc67ed8b6cd7d1ec30
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573539"
---
# <a name="lync-server-2013-stress-and-performance-tool-faq"></a><span data-ttu-id="9d86a-103">Lync Server 2013 應力和效能工具常見問題</span><span class="sxs-lookup"><span data-stu-id="9d86a-103">Lync Server 2013 Stress and Performance Tool FAQ</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d86a-104">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="9d86a-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="9d86a-105">常見問題集</span><span class="sxs-lookup"><span data-stu-id="9d86a-105">Frequently Asked Questions</span></span>

<span data-ttu-id="9d86a-106">以下是有關 Lync Server 2013 壓力和效能工具的常見問題。</span><span class="sxs-lookup"><span data-stu-id="9d86a-106">Here are some frequently asked questions about the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="9d86a-107">我可以在生產環境中執行 LyncPerfTool.exe 嗎？</span><span class="sxs-lookup"><span data-stu-id="9d86a-107">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="9d86a-108">我們不建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="9d86a-108">We do not recommend this.</span></span> <span data-ttu-id="9d86a-109">此工具會影響伺服器的效能、安全性和使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="9d86a-109">This tool will impact server performance, security, and user experience.</span></span>

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a><span data-ttu-id="9d86a-110">我是第一次登入我的使用者。</span><span class="sxs-lookup"><span data-stu-id="9d86a-110">I am logging on my users for the first time.</span></span> <span data-ttu-id="9d86a-111">為什麼伺服器的執行是如此高負載的？</span><span class="sxs-lookup"><span data-stu-id="9d86a-111">Why are the servers running at such high load?</span></span>

<span data-ttu-id="9d86a-112">使用者第一次登入時，會發生其他作業。</span><span class="sxs-lookup"><span data-stu-id="9d86a-112">The first time the users log on, there are additional operations that occur.</span></span> <span data-ttu-id="9d86a-113">因此，Microsoft SQL Server 後端伺服器的效能將會降級。</span><span class="sxs-lookup"><span data-stu-id="9d86a-113">As a result, the performance on the Microsoft SQL Server Back End Server will be degraded.</span></span> <span data-ttu-id="9d86a-114">建議您執行簡短的測試，讓您在測量結果之前，先登入所有使用者，然後重新開機用戶端。</span><span class="sxs-lookup"><span data-stu-id="9d86a-114">We recommend that you run a short test that logs on all of the users, and then restart the clients before you measure results.</span></span> <span data-ttu-id="9d86a-115">我們不支援每秒超過12個同時使用者登入會話，但這取決於您的硬體設定。</span><span class="sxs-lookup"><span data-stu-id="9d86a-115">We do not support more than 12 concurrent user logon sessions per second, but this depends on your hardware configuration.</span></span>

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="9d86a-116">我的用戶端記憶體不足。</span><span class="sxs-lookup"><span data-stu-id="9d86a-116">My clients are running out of memory.</span></span> <span data-ttu-id="9d86a-117">我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="9d86a-117">What should I do?</span></span>

<span data-ttu-id="9d86a-118">如果您的用戶端記憶體不足，您必須減少每一部電腦的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="9d86a-118">If your clients are running out of memory, you need to reduce the number of users per computer.</span></span>

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a><span data-ttu-id="9d86a-119">現在，用戶端的 CPU 都是100%。</span><span class="sxs-lookup"><span data-stu-id="9d86a-119">My clients are at 100 percent CPU all the time.</span></span> <span data-ttu-id="9d86a-120">我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="9d86a-120">What should I do?</span></span>

<span data-ttu-id="9d86a-121">如果您的用戶端在所有使用者登入後都是以極高的 CPU 執行，則您必須減少每台電腦的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="9d86a-121">If your clients are running with very high CPU after all the users have logged on, you need to reduce the number of users per computer.</span></span> <span data-ttu-id="9d86a-122">高 CPU 峰值是可接受的，但是如果有持續的，您必須減少負載。</span><span class="sxs-lookup"><span data-stu-id="9d86a-122">High CPU spikes are acceptable, but if it is sustained, you need to reduce the load.</span></span>

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a><span data-ttu-id="9d86a-123">我是否可以在伺服器上執行此工具？</span><span class="sxs-lookup"><span data-stu-id="9d86a-123">Can I run the tool on the server itself?</span></span>

<span data-ttu-id="9d86a-124">否。</span><span class="sxs-lookup"><span data-stu-id="9d86a-124">No.</span></span> <span data-ttu-id="9d86a-125">這種案例不受支援，而且可能會因為二進位不符而失敗。</span><span class="sxs-lookup"><span data-stu-id="9d86a-125">This scenario is not supported and may fail due to a binary mismatch.</span></span> <span data-ttu-id="9d86a-126">此外，因為點是測量伺服器上的資源消耗，所以執行工具會使度量變得無意義。</span><span class="sxs-lookup"><span data-stu-id="9d86a-126">Also, because the point is to measure resource consumption on the server, running the tool there would render the measurements meaningless.</span></span>

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="9d86a-127">我可以在虛擬伺服器或 Microsoft Hyper-V Server 2008/2012 上執行 LyncPerfTool.exe 嗎？</span><span class="sxs-lookup"><span data-stu-id="9d86a-127">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="9d86a-128">是。</span><span class="sxs-lookup"><span data-stu-id="9d86a-128">Yes.</span></span>

</div>

<div>

## <a name="what-does-mpop-mean"></a><span data-ttu-id="9d86a-129">MPOP 的含義為何？</span><span class="sxs-lookup"><span data-stu-id="9d86a-129">What does MPOP mean?</span></span>

<span data-ttu-id="9d86a-130">MPOP 代表多點顯示狀態。</span><span class="sxs-lookup"><span data-stu-id="9d86a-130">MPOP stands for multiple points of presence.</span></span> <span data-ttu-id="9d86a-131">這是要模擬使用者從多部機器登入 Lync 2013 的案例。</span><span class="sxs-lookup"><span data-stu-id="9d86a-131">It is meant to simulate the scenario where users are logged on to Lync 2013 from multiple machines.</span></span> <span data-ttu-id="9d86a-132">請注意，在 LyncPerfTool.exe 中，每個端點都使用預設設定檔 (也就是說，設定檔不會分割兩個存在點) 。</span><span class="sxs-lookup"><span data-stu-id="9d86a-132">Note that in LyncPerfTool.exe, each endpoint uses the default profile (that is, the profile is not split between the two points of presence).</span></span>

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="9d86a-133">我已開始 LyncPerfTool.exe 但不會發生任何情況。</span><span class="sxs-lookup"><span data-stu-id="9d86a-133">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="9d86a-134">到底怎麼回事？</span><span class="sxs-lookup"><span data-stu-id="9d86a-134">What’s going on?</span></span>

<span data-ttu-id="9d86a-135">檢查用戶端上的作用中端點計數器總數，以查看使用者是否正在連線。</span><span class="sxs-lookup"><span data-stu-id="9d86a-135">Check the Total Active Endpoints counter on the clients to see if the users are connecting.</span></span> <span data-ttu-id="9d86a-136">如果使用者未連接，請驗證您的 Lync Server 2013 設定。</span><span class="sxs-lookup"><span data-stu-id="9d86a-136">If users are not connecting, verify your Lync Server 2013 configuration.</span></span> <span data-ttu-id="9d86a-137">發生此問題的原因通常是伺服器名稱、使用者前置詞或密碼不正確。</span><span class="sxs-lookup"><span data-stu-id="9d86a-137">This issue usually occurs because the server name, the user prefix, or the password is incorrect.</span></span> <span data-ttu-id="9d86a-138">請注意，外部用戶端應將存取 Proxy 指定為 TargetServer 值。</span><span class="sxs-lookup"><span data-stu-id="9d86a-138">Note that external clients should specify the Access Proxy as the TargetServer value.</span></span> <span data-ttu-id="9d86a-139">驗證設定檔中的埠。</span><span class="sxs-lookup"><span data-stu-id="9d86a-139">Verify the port in the configuration file.</span></span>

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a><span data-ttu-id="9d86a-140">如何知道發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="9d86a-140">How do I know something is happening?</span></span>

<span data-ttu-id="9d86a-141">各種 LyncPerfTool 效能計數器會指出使用者是否正在連線和執行動作。</span><span class="sxs-lookup"><span data-stu-id="9d86a-141">The various LyncPerfTool performance counters indicate whether or not users are connecting and performing actions.</span></span> <span data-ttu-id="9d86a-142">不過，一種簡單的方法是使用 Lync 2013 登入其中一個帳戶，並執行您想要的動作。</span><span class="sxs-lookup"><span data-stu-id="9d86a-142">However, an easy way to check is to log on to one of the accounts by using Lync 2013 and performing the action you want.</span></span>

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a><span data-ttu-id="9d86a-143">我已安裝 Live 迅 Server 2007 R2 容量規劃工具和/或 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="9d86a-143">I have Live Communications Server 2007 R2 Capacity Planning Tools and/or Lync Server 2010 installed.</span></span> <span data-ttu-id="9d86a-144">該是否正常？</span><span class="sxs-lookup"><span data-stu-id="9d86a-144">Is that OK?</span></span>

<span data-ttu-id="9d86a-145">否。</span><span class="sxs-lookup"><span data-stu-id="9d86a-145">No.</span></span> <span data-ttu-id="9d86a-146">發生互通性問題，您必須卸載此產品所有先前的版本。</span><span class="sxs-lookup"><span data-stu-id="9d86a-146">There are interoperability issues, and you must uninstall all previous versions of this product.</span></span>

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="9d86a-147">壓力和效能工具是否會設定 CAA 的呼叫資訊伺服器拓撲？</span><span class="sxs-lookup"><span data-stu-id="9d86a-147">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="9d86a-148">否。</span><span class="sxs-lookup"><span data-stu-id="9d86a-148">No.</span></span> <span data-ttu-id="9d86a-149">工具只會建立使用者、連絡人及通訊群組清單，並模擬使用者負載。</span><span class="sxs-lookup"><span data-stu-id="9d86a-149">The tools only create users, contacts, and distribution lists, and simulate user load.</span></span>

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="9d86a-150">工具支援的使用者數目上限為何？</span><span class="sxs-lookup"><span data-stu-id="9d86a-150">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="9d86a-151">我們已建立最多80000個使用者，並使用這些工具，建立總計30000使用者的執行測試。</span><span class="sxs-lookup"><span data-stu-id="9d86a-151">We have created up to a total of 80,000 users and executed tests totaling 30,000 users, using these tools.</span></span> <span data-ttu-id="9d86a-152">我們建議最多120000個使用者，但技術限制允許更高的價值，視用戶端和伺服器硬體可用而定。</span><span class="sxs-lookup"><span data-stu-id="9d86a-152">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher value, depending on the client and server hardware available.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

