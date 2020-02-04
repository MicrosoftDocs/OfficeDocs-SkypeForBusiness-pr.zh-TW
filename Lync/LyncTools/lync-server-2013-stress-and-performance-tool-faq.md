---
title: Lync Server 2013 應力與效能工具常見問題
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
ms.openlocfilehash: 9138a23ee1fa45f3da827832b568852952b0ae4d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a><span data-ttu-id="258d2-102">Lync Server 2013 應力與效能工具常見問題</span><span class="sxs-lookup"><span data-stu-id="258d2-102">Lync Server 2013 Stress and Performance Tool FAQ</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="258d2-103">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="258d2-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="258d2-104">常見問題</span><span class="sxs-lookup"><span data-stu-id="258d2-104">Frequently Asked Questions</span></span>

<span data-ttu-id="258d2-105">以下是 Lync Server 2013 應力和效能工具的一些常見問題。</span><span class="sxs-lookup"><span data-stu-id="258d2-105">Here are some frequently asked questions about the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="258d2-106">我可以在生產中執行 LyncPerfTool 嗎？</span><span class="sxs-lookup"><span data-stu-id="258d2-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="258d2-107">我們不建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="258d2-107">We do not recommend this.</span></span> <span data-ttu-id="258d2-108">這個工具會影響伺服器的效能、安全性和使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="258d2-108">This tool will impact server performance, security, and user experience.</span></span>

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a><span data-ttu-id="258d2-109">我是第一次登入使用者。</span><span class="sxs-lookup"><span data-stu-id="258d2-109">I am logging on my users for the first time.</span></span> <span data-ttu-id="258d2-110">為什麼伺服器是以這類高負載執行？</span><span class="sxs-lookup"><span data-stu-id="258d2-110">Why are the servers running at such high load?</span></span>

<span data-ttu-id="258d2-111">使用者第一次登入時，會發生其他的操作。</span><span class="sxs-lookup"><span data-stu-id="258d2-111">The first time the users log on, there are additional operations that occur.</span></span> <span data-ttu-id="258d2-112">因此，Microsoft SQL Server 後端伺服器的效能將會下降。</span><span class="sxs-lookup"><span data-stu-id="258d2-112">As a result, the performance on the Microsoft SQL Server Back End Server will be degraded.</span></span> <span data-ttu-id="258d2-113">我們建議您執行簡短測試，以記錄所有使用者，然後重新開機用戶端，然後再測量結果。</span><span class="sxs-lookup"><span data-stu-id="258d2-113">We recommend that you run a short test that logs on all of the users, and then restart the clients before you measure results.</span></span> <span data-ttu-id="258d2-114">我們每秒不支援超過12個併發使用者登入會話，但這取決於您的硬體設定。</span><span class="sxs-lookup"><span data-stu-id="258d2-114">We do not support more than 12 concurrent user logon sessions per second, but this depends on your hardware configuration.</span></span>

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="258d2-115">我的用戶端記憶體不足。</span><span class="sxs-lookup"><span data-stu-id="258d2-115">My clients are running out of memory.</span></span> <span data-ttu-id="258d2-116">我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="258d2-116">What should I do?</span></span>

<span data-ttu-id="258d2-117">如果用戶端記憶體不足，您必須減少每個電腦的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="258d2-117">If your clients are running out of memory, you need to reduce the number of users per computer.</span></span>

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a><span data-ttu-id="258d2-118">我的客戶隨時都是100% 的 CPU。</span><span class="sxs-lookup"><span data-stu-id="258d2-118">My clients are at 100 percent CPU all the time.</span></span> <span data-ttu-id="258d2-119">我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="258d2-119">What should I do?</span></span>

<span data-ttu-id="258d2-120">如果您的用戶端在所有使用者登入後都執行了極高的 CPU，您必須減少每個電腦的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="258d2-120">If your clients are running with very high CPU after all the users have logged on, you need to reduce the number of users per computer.</span></span> <span data-ttu-id="258d2-121">高 CPU 峰值是可接受的，但如果持續進行，您必須減少負載。</span><span class="sxs-lookup"><span data-stu-id="258d2-121">High CPU spikes are acceptable, but if it is sustained, you need to reduce the load.</span></span>

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a><span data-ttu-id="258d2-122">我可以在伺服器上執行該工具嗎？</span><span class="sxs-lookup"><span data-stu-id="258d2-122">Can I run the tool on the server itself?</span></span>

<span data-ttu-id="258d2-123">不。</span><span class="sxs-lookup"><span data-stu-id="258d2-123">No.</span></span> <span data-ttu-id="258d2-124">這個案例不受支援，而且可能會因為二進位不相符而失敗。</span><span class="sxs-lookup"><span data-stu-id="258d2-124">This scenario is not supported and may fail due to a binary mismatch.</span></span> <span data-ttu-id="258d2-125">此外，因為點是測量伺服器上的資源佔用，所以執行工具時會將度量轉譯成沒有意義。</span><span class="sxs-lookup"><span data-stu-id="258d2-125">Also, because the point is to measure resource consumption on the server, running the tool there would render the measurements meaningless.</span></span>

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="258d2-126">我可以在虛擬伺服器或 Microsoft Hyper-v Server 2008/2012 上執行 LyncPerfTool 嗎？</span><span class="sxs-lookup"><span data-stu-id="258d2-126">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="258d2-127">是。</span><span class="sxs-lookup"><span data-stu-id="258d2-127">Yes.</span></span>

</div>

<div>

## <a name="what-does-mpop-mean"></a><span data-ttu-id="258d2-128">MPOP 代表什麼意思？</span><span class="sxs-lookup"><span data-stu-id="258d2-128">What does MPOP mean?</span></span>

<span data-ttu-id="258d2-129">MPOP 代表多個目前狀態點。</span><span class="sxs-lookup"><span data-stu-id="258d2-129">MPOP stands for multiple points of presence.</span></span> <span data-ttu-id="258d2-130">它是用來模擬使用者從多個電腦登入 Lync 2013 的情況。</span><span class="sxs-lookup"><span data-stu-id="258d2-130">It is meant to simulate the scenario where users are logged on to Lync 2013 from multiple machines.</span></span> <span data-ttu-id="258d2-131">請注意，在 LyncPerfTool 中，每個端點都會使用預設設定檔（也就是設定檔不會在兩個目前狀態點之間分割）。</span><span class="sxs-lookup"><span data-stu-id="258d2-131">Note that in LyncPerfTool.exe, each endpoint uses the default profile (that is, the profile is not split between the two points of presence).</span></span>

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="258d2-132">我已開始 LyncPerfTool，但卻沒有發生任何事。</span><span class="sxs-lookup"><span data-stu-id="258d2-132">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="258d2-133">這是怎麼回事？</span><span class="sxs-lookup"><span data-stu-id="258d2-133">What’s going on?</span></span>

<span data-ttu-id="258d2-134">檢查用戶端上的 [總作用中端點] 計數器，查看使用者是否正在連線。</span><span class="sxs-lookup"><span data-stu-id="258d2-134">Check the Total Active Endpoints counter on the clients to see if the users are connecting.</span></span> <span data-ttu-id="258d2-135">如果使用者未連線，請確認您的 Lync Server 2013 設定。</span><span class="sxs-lookup"><span data-stu-id="258d2-135">If users are not connecting, verify your Lync Server 2013 configuration.</span></span> <span data-ttu-id="258d2-136">這個問題通常是因為伺服器名稱、使用者的首碼或密碼不正確。</span><span class="sxs-lookup"><span data-stu-id="258d2-136">This issue usually occurs because the server name, the user prefix, or the password is incorrect.</span></span> <span data-ttu-id="258d2-137">請注意，外部用戶端應該將訪問 Proxy 指定為 TargetServer 值。</span><span class="sxs-lookup"><span data-stu-id="258d2-137">Note that external clients should specify the Access Proxy as the TargetServer value.</span></span> <span data-ttu-id="258d2-138">驗證設定檔中的埠。</span><span class="sxs-lookup"><span data-stu-id="258d2-138">Verify the port in the configuration file.</span></span>

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a><span data-ttu-id="258d2-139">如何知道發生了什麼事？</span><span class="sxs-lookup"><span data-stu-id="258d2-139">How do I know something is happening?</span></span>

<span data-ttu-id="258d2-140">各種 LyncPerfTool 效能計數器會指出使用者是否要連接並執行動作。</span><span class="sxs-lookup"><span data-stu-id="258d2-140">The various LyncPerfTool performance counters indicate whether or not users are connecting and performing actions.</span></span> <span data-ttu-id="258d2-141">不過，一個簡單的檢查方法是使用 Lync 2013 登入其中一個帳戶，並執行您想要的動作。</span><span class="sxs-lookup"><span data-stu-id="258d2-141">However, an easy way to check is to log on to one of the accounts by using Lync 2013 and performing the action you want.</span></span>

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a><span data-ttu-id="258d2-142">我已安裝 [即時通訊伺服器 2007 R2 容量規劃工具] 和/或 [Lync Server 2010]。</span><span class="sxs-lookup"><span data-stu-id="258d2-142">I have Live Communications Server 2007 R2 Capacity Planning Tools and/or Lync Server 2010 installed.</span></span> <span data-ttu-id="258d2-143">那是確定嗎？</span><span class="sxs-lookup"><span data-stu-id="258d2-143">Is that OK?</span></span>

<span data-ttu-id="258d2-144">不。</span><span class="sxs-lookup"><span data-stu-id="258d2-144">No.</span></span> <span data-ttu-id="258d2-145">發生互通性問題，您必須卸載此產品的所有舊版版本。</span><span class="sxs-lookup"><span data-stu-id="258d2-145">There are interoperability issues, and you must uninstall all previous versions of this product.</span></span>

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="258d2-146">壓力與效能工具會設定 CAA 通話資訊伺服器拓撲嗎？</span><span class="sxs-lookup"><span data-stu-id="258d2-146">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="258d2-147">不。</span><span class="sxs-lookup"><span data-stu-id="258d2-147">No.</span></span> <span data-ttu-id="258d2-148">工具只會建立使用者、連絡人及通訊群組清單，並類比使用者負載。</span><span class="sxs-lookup"><span data-stu-id="258d2-148">The tools only create users, contacts, and distribution lists, and simulate user load.</span></span>

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="258d2-149">工具支援的使用者數目上限為何？</span><span class="sxs-lookup"><span data-stu-id="258d2-149">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="258d2-150">我們已建立最多80000個使用者，以及使用這些工具來總計30000個使用者所執行的測試。</span><span class="sxs-lookup"><span data-stu-id="258d2-150">We have created up to a total of 80,000 users and executed tests totaling 30,000 users, using these tools.</span></span> <span data-ttu-id="258d2-151">我們建議您最多120000個使用者，不過，您可以根據用戶端和伺服器硬體提供的技術限制來取得較高的價值。</span><span class="sxs-lookup"><span data-stu-id="258d2-151">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher value, depending on the client and server hardware available.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

