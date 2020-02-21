---
title: Lync Server 2013 壓力及效能工具常見問題集
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
ms.openlocfilehash: 590453f6270ebcd2beebbb26b8035f9e33cc2cd7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a><span data-ttu-id="5a405-102">Lync Server 2013 壓力及效能工具常見問題集</span><span class="sxs-lookup"><span data-stu-id="5a405-102">Lync Server 2013 Stress and Performance Tool FAQ</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a405-103">_**上次修改主題：** 2013年-02-24_</span><span class="sxs-lookup"><span data-stu-id="5a405-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="5a405-104">常見問題集</span><span class="sxs-lookup"><span data-stu-id="5a405-104">Frequently Asked Questions</span></span>

<span data-ttu-id="5a405-105">以下是一些常見問題的 Lync Server 2013 壓力及效能工具。</span><span class="sxs-lookup"><span data-stu-id="5a405-105">Here are some frequently asked questions about the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="5a405-106">可以在生產環境中執行 LyncPerfTool.exe 嗎？</span><span class="sxs-lookup"><span data-stu-id="5a405-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="5a405-107">我們不建議這。</span><span class="sxs-lookup"><span data-stu-id="5a405-107">We do not recommend this.</span></span> <span data-ttu-id="5a405-108">此工具會影響伺服器效能、 安全性及使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="5a405-108">This tool will impact server performance, security, and user experience.</span></span>

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a><span data-ttu-id="5a405-109">我已經在第一次登入我的使用者。</span><span class="sxs-lookup"><span data-stu-id="5a405-109">I am logging on my users for the first time.</span></span> <span data-ttu-id="5a405-110">為什麼的伺服器會在這類高負載執行？</span><span class="sxs-lookup"><span data-stu-id="5a405-110">Why are the servers running at such high load?</span></span>

<span data-ttu-id="5a405-111">第一次使用者登入，有發生的其他作業。</span><span class="sxs-lookup"><span data-stu-id="5a405-111">The first time the users log on, there are additional operations that occur.</span></span> <span data-ttu-id="5a405-112">因此，在 Microsoft SQL Server 後端伺服器上的效能會降低。</span><span class="sxs-lookup"><span data-stu-id="5a405-112">As a result, the performance on the Microsoft SQL Server Back End Server will be degraded.</span></span> <span data-ttu-id="5a405-113">我們建議您執行的簡短的測試，記錄上的所有使用者，並之前測量結果，然後重新啟動用戶端。</span><span class="sxs-lookup"><span data-stu-id="5a405-113">We recommend that you run a short test that logs on all of the users, and then restart the clients before you measure results.</span></span> <span data-ttu-id="5a405-114">我們不支援超過 12 個並行使用者登入工作階段，每秒，但這取決於您的硬體設定。</span><span class="sxs-lookup"><span data-stu-id="5a405-114">We do not support more than 12 concurrent user logon sessions per second, but this depends on your hardware configuration.</span></span>

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="5a405-115">我的用戶端都執行記憶體不足。</span><span class="sxs-lookup"><span data-stu-id="5a405-115">My clients are running out of memory.</span></span> <span data-ttu-id="5a405-116">我該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="5a405-116">What should I do?</span></span>

<span data-ttu-id="5a405-117">如果您的用戶端都執行記憶體不足，您需要降低每部電腦的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="5a405-117">If your clients are running out of memory, you need to reduce the number of users per computer.</span></span>

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a><span data-ttu-id="5a405-118">我的用戶端在都是 100%的 cpu 使用量所有的時間。</span><span class="sxs-lookup"><span data-stu-id="5a405-118">My clients are at 100 percent CPU all the time.</span></span> <span data-ttu-id="5a405-119">我該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="5a405-119">What should I do?</span></span>

<span data-ttu-id="5a405-120">如果您的用戶端執行極高的 CPU 與所有使用者已都登入之後，您需要降低每部電腦的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="5a405-120">If your clients are running with very high CPU after all the users have logged on, you need to reduce the number of users per computer.</span></span> <span data-ttu-id="5a405-121">高 CPU 突發性都可接受的但如果它承受，您需要降低的負載。</span><span class="sxs-lookup"><span data-stu-id="5a405-121">High CPU spikes are acceptable, but if it is sustained, you need to reduce the load.</span></span>

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a><span data-ttu-id="5a405-122">可在本身的伺服器上執行工具？</span><span class="sxs-lookup"><span data-stu-id="5a405-122">Can I run the tool on the server itself?</span></span>

<span data-ttu-id="5a405-123">否。</span><span class="sxs-lookup"><span data-stu-id="5a405-123">No.</span></span> <span data-ttu-id="5a405-124">此案例中不受支援，而且由於二進位不符可能會失敗。</span><span class="sxs-lookup"><span data-stu-id="5a405-124">This scenario is not supported and may fail due to a binary mismatch.</span></span> <span data-ttu-id="5a405-125">此外，由於點是測量伺服器上的資源消耗量，那里執行此工具會轉譯度量單位從沒有意義。</span><span class="sxs-lookup"><span data-stu-id="5a405-125">Also, because the point is to measure resource consumption on the server, running the tool there would render the measurements meaningless.</span></span>

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="5a405-126">虛擬伺服器上或在 Microsoft HYPER-V Server 2008/2012年可以執行 LyncPerfTool.exe 嗎？</span><span class="sxs-lookup"><span data-stu-id="5a405-126">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="5a405-127">是。</span><span class="sxs-lookup"><span data-stu-id="5a405-127">Yes.</span></span>

</div>

<div>

## <a name="what-does-mpop-mean"></a><span data-ttu-id="5a405-128">MPOP 是什麼意思？</span><span class="sxs-lookup"><span data-stu-id="5a405-128">What does MPOP mean?</span></span>

<span data-ttu-id="5a405-129">MPOP 代表多個存在點。</span><span class="sxs-lookup"><span data-stu-id="5a405-129">MPOP stands for multiple points of presence.</span></span> <span data-ttu-id="5a405-130">它是用來模擬其中使用者已登入 Lync 2013 從多部電腦的案例。</span><span class="sxs-lookup"><span data-stu-id="5a405-130">It is meant to simulate the scenario where users are logged on to Lync 2013 from multiple machines.</span></span> <span data-ttu-id="5a405-131">請注意，在 LyncPerfTool.exe，每個端點會使用預設的設定檔 （也就是設定檔不會分割之間的目前狀態的兩個點）。</span><span class="sxs-lookup"><span data-stu-id="5a405-131">Note that in LyncPerfTool.exe, each endpoint uses the default profile (that is, the profile is not split between the two points of presence).</span></span>

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="5a405-132">我開始 LyncPerfTool.exe 但 nothing 的情形。</span><span class="sxs-lookup"><span data-stu-id="5a405-132">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="5a405-133">到底怎麼回事？</span><span class="sxs-lookup"><span data-stu-id="5a405-133">What’s going on?</span></span>

<span data-ttu-id="5a405-134">請檢查以查看使用者是否所連線之用戶端上的總作用中的端點計數器。</span><span class="sxs-lookup"><span data-stu-id="5a405-134">Check the Total Active Endpoints counter on the clients to see if the users are connecting.</span></span> <span data-ttu-id="5a405-135">如果使用者未連線，請確認您的 Lync Server 2013 設定。</span><span class="sxs-lookup"><span data-stu-id="5a405-135">If users are not connecting, verify your Lync Server 2013 configuration.</span></span> <span data-ttu-id="5a405-136">因為伺服器名稱、 使用者前置詞或密碼不正確，通常就會發生這個問題。</span><span class="sxs-lookup"><span data-stu-id="5a405-136">This issue usually occurs because the server name, the user prefix, or the password is incorrect.</span></span> <span data-ttu-id="5a405-137">請注意外部用戶端為 TargetServer 值，指定 Access Proxy。</span><span class="sxs-lookup"><span data-stu-id="5a405-137">Note that external clients should specify the Access Proxy as the TargetServer value.</span></span> <span data-ttu-id="5a405-138">確認組態檔中的連接埠。</span><span class="sxs-lookup"><span data-stu-id="5a405-138">Verify the port in the configuration file.</span></span>

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a><span data-ttu-id="5a405-139">如何知道某個項目的情形？</span><span class="sxs-lookup"><span data-stu-id="5a405-139">How do I know something is happening?</span></span>

<span data-ttu-id="5a405-140">各種 LyncPerfTool 效能計數器指出使用者連線並執行的動作。</span><span class="sxs-lookup"><span data-stu-id="5a405-140">The various LyncPerfTool performance counters indicate whether or not users are connecting and performing actions.</span></span> <span data-ttu-id="5a405-141">不過，簡單的方法來檢查是登入帳戶的其中一個使用 Lync 2013，並執行您想要的動作。</span><span class="sxs-lookup"><span data-stu-id="5a405-141">However, an easy way to check is to log on to one of the accounts by using Lync 2013 and performing the action you want.</span></span>

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a><span data-ttu-id="5a405-142">我有 Live Communications Server 2007 R2 的容量規劃工具及/或 Lync Server 2010 安裝。</span><span class="sxs-lookup"><span data-stu-id="5a405-142">I have Live Communications Server 2007 R2 Capacity Planning Tools and/or Lync Server 2010 installed.</span></span> <span data-ttu-id="5a405-143">這是確定嗎？</span><span class="sxs-lookup"><span data-stu-id="5a405-143">Is that OK?</span></span>

<span data-ttu-id="5a405-144">否。</span><span class="sxs-lookup"><span data-stu-id="5a405-144">No.</span></span> <span data-ttu-id="5a405-145">互通性問題，您必須先解除安裝所有舊版的這項產品。</span><span class="sxs-lookup"><span data-stu-id="5a405-145">There are interoperability issues, and you must uninstall all previous versions of this product.</span></span>

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="5a405-146">會設定 CAA 通話資訊伺服器拓撲的壓力及效能工具？</span><span class="sxs-lookup"><span data-stu-id="5a405-146">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="5a405-147">否。</span><span class="sxs-lookup"><span data-stu-id="5a405-147">No.</span></span> <span data-ttu-id="5a405-148">工具只會建立使用者、 連絡人和通訊群組清單及模擬使用者負載。</span><span class="sxs-lookup"><span data-stu-id="5a405-148">The tools only create users, contacts, and distribution lists, and simulate user load.</span></span>

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="5a405-149">工具支援的使用者數目上限為何？</span><span class="sxs-lookup"><span data-stu-id="5a405-149">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="5a405-150">我們已建立合計 80000 位使用者最多，並執行測試加總 30000 位使用者，使用這些工具。</span><span class="sxs-lookup"><span data-stu-id="5a405-150">We have created up to a total of 80,000 users and executed tests totaling 30,000 users, using these tools.</span></span> <span data-ttu-id="5a405-151">雖然技術限制允許較高的值，根據可用的用戶端和伺服器硬體，建議最大值為 120000 使用者。</span><span class="sxs-lookup"><span data-stu-id="5a405-151">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher value, depending on the client and server hardware available.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

