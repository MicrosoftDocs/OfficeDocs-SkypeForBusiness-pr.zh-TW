---
title: Lync Server 2013 容量規劃小算盤
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2013 capacity planning calculator
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56280894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b920f7fd0325c3232abb5670a2da66fc98352d38
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a><span data-ttu-id="dec28-102">使用 Lync Server 2013 的容量規劃 [小算盤]</span><span class="sxs-lookup"><span data-stu-id="dec28-102">Using the capacity planning calculator for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dec28-103">_**上次修改主題：** 2013年-11-21_</span><span class="sxs-lookup"><span data-stu-id="dec28-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="dec28-104">Microsoft® Lync™ Server 2013 容量規劃小算盤] 位於可供下載在<https://www.microsoft.com/download/details.aspx?id=36828>。</span><span class="sxs-lookup"><span data-stu-id="dec28-104">The Microsoft® Lync™ Server 2013 capacity planning calculator is available for download at <https://www.microsoft.com/download/details.aspx?id=36828>.</span></span> <span data-ttu-id="dec28-105">它被設計來協助您判斷伺服器的需求，根據使用者和組織已啟用的溝通形式的數字。</span><span class="sxs-lookup"><span data-stu-id="dec28-105">It is designed to assist you in determining server requirements based on numbers of users and communication modalities that are enabled at your organization.</span></span> <span data-ttu-id="dec28-106">您輸入您的組織設定檔]，和 [小算盤] 提供的建議，協助您規劃您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="dec28-106">You enter your organization’s profile, and the calculator provides recommendations that help you plan your topology.</span></span>

<span data-ttu-id="dec28-107">進行規劃時只是由 [小算盤] 所建立的建議。</span><span class="sxs-lookup"><span data-stu-id="dec28-107">The recommendations created by the calculator are for planning purposes only.</span></span> <span data-ttu-id="dec28-108">實際的負載模擬，才能確保已適當地佈建 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="dec28-108">Actual load simulation is required to ensure that Lync Server 2013 is adequately provisioned.</span></span> <span data-ttu-id="dec28-109">若要執行壓力測試模擬的負載下，使用[Lync Server 2013 壓力及效能工具](https://go.microsoft.com/fwlink/?linkid=282724)。</span><span class="sxs-lookup"><span data-stu-id="dec28-109">To perform stress testing under a simulated load, use the [Lync Server 2013 Stress and Performance Tool](https://go.microsoft.com/fwlink/?linkid=282724).</span></span>

<span data-ttu-id="dec28-110">您已決定您的使用者設定檔，並且想要啟用您的使用者形式之後，就可以使用 [小算盤] 可規劃伺服器、 記憶體及您所需要的頻寬的數目。</span><span class="sxs-lookup"><span data-stu-id="dec28-110">After you have determined your user profile and the modalities that you want to enable for your users, it is time to use the calculator to plan the number of servers, memory, and bandwidth that you need.</span></span> <span data-ttu-id="dec28-111">此版本的計算機不提供指引磁碟 I/O 的需求。</span><span class="sxs-lookup"><span data-stu-id="dec28-111">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>

<span data-ttu-id="dec28-112">此計算機補充[Microsoft Lync Server](https://go.microsoft.com/fwlink/?linkid=282725)和[Microsoft Lync Server](lync-server-2013-planning.md)。</span><span class="sxs-lookup"><span data-stu-id="dec28-112">This calculator complements the [Microsoft Lync Server](https://go.microsoft.com/fwlink/?linkid=282725) and [Microsoft Lync Server](lync-server-2013-planning.md).</span></span> <span data-ttu-id="dec28-113">您已檢閱快顯功能表，並使用規劃工具所建立的建議的拓撲之後，請使用 [小算盤]。</span><span class="sxs-lookup"><span data-stu-id="dec28-113">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>

<span data-ttu-id="dec28-114">您可以享有最 [小算盤] 如果您有關於您的特定使用者設定檔的精確、 詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="dec28-114">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="dec28-115">例如，已啟用語音的使用者，每位使用者每小時、 通話持續期間，並在會議中並行使用者的百分比的平均通話的百分比可以讓伺服器需求極大差異。</span><span class="sxs-lookup"><span data-stu-id="dec28-115">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="dec28-116">[小算盤] 所建立的建議的準確性取決於您所提供的資訊的正確性。</span><span class="sxs-lookup"><span data-stu-id="dec28-116">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>

<div>

## <a name="using-the-capacity-calculator"></a><span data-ttu-id="dec28-117">使用容量的小算盤</span><span class="sxs-lookup"><span data-stu-id="dec28-117">Using the Capacity Calculator</span></span>

<span data-ttu-id="dec28-118">小算盤] 位於 Microsoft Excel® 試算表。</span><span class="sxs-lookup"><span data-stu-id="dec28-118">The calculator is a Microsoft Excel® spreadsheet.</span></span> <span data-ttu-id="dec28-119">橙色無儲存格都是從您的輸入。</span><span class="sxs-lookup"><span data-stu-id="dec28-119">Orange-colored cells are for input from you.</span></span> <span data-ttu-id="dec28-120">預設值為輸入 (80000 位使用者在與十二個前端伺服器集區中的），但您可以變更這些值，根據貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="dec28-120">Default values are entered (80,000 users in one pool with twelve Front End Servers), but you can change these values according to your organization’s needs.</span></span>

<span data-ttu-id="dec28-121">使用模型包含下列各節。</span><span class="sxs-lookup"><span data-stu-id="dec28-121">The usage model contains the following sections.</span></span> <span data-ttu-id="dec28-122">若要計算容量需求，請輸入資料，如所述：</span><span class="sxs-lookup"><span data-stu-id="dec28-122">To calculate your capacity requirements, enter data as described:</span></span>

<span data-ttu-id="dec28-123">**立即訊息和目前狀態**</span><span class="sxs-lookup"><span data-stu-id="dec28-123">**Instant Messaging and Presence**</span></span>

  - <span data-ttu-id="dec28-124">[數字的使用者] 下方輸入會同時登入的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="dec28-124">Under Number of Users, type the number of users who will be concurrently signed in.</span></span> <span data-ttu-id="dec28-125">此數字通常為 80%的佈建的使用者總數。</span><span class="sxs-lookup"><span data-stu-id="dec28-125">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="dec28-126">在大部分情況下，100%的並行使用者將會啟用 IM 和目前狀態。</span><span class="sxs-lookup"><span data-stu-id="dec28-126">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="dec28-127">預設值為 80000。</span><span class="sxs-lookup"><span data-stu-id="dec28-127">The default is 80,000.</span></span>

  - <span data-ttu-id="dec28-128">在連絡人清單中的連絡人的平均數目表示我們正在用來驗證您的系統需求的連絡人數目。</span><span class="sxs-lookup"><span data-stu-id="dec28-128">Average number of contacts in Contact list indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="dec28-129">此數字不是可變更。</span><span class="sxs-lookup"><span data-stu-id="dec28-129">This number is not changeable.</span></span>

<span data-ttu-id="dec28-130">**企業語音**</span><span class="sxs-lookup"><span data-stu-id="dec28-130">**Enterprise Voice**</span></span>

  - <span data-ttu-id="dec28-131">在啟用 Enterprise Voice 的使用者，請輸入您的使用者啟用 Enterprise voice 的百分比。</span><span class="sxs-lookup"><span data-stu-id="dec28-131">In Users enabled for Enterprise Voice, type the percentage of your users who are enabled for Enterprise Voice.</span></span> <span data-ttu-id="dec28-132">預設值為 60%。</span><span class="sxs-lookup"><span data-stu-id="dec28-132">The default is 60%.</span></span>

  - <span data-ttu-id="dec28-133">在每位使用者每小時 （尖峰時） 通話的平均數目，輸入您預期一般使用者參與的尖峰負載時段每小時來電數目。</span><span class="sxs-lookup"><span data-stu-id="dec28-133">In Average number of calls per user per hour (peak), type the number of calls per hour that you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="dec28-134">預設值為 4。</span><span class="sxs-lookup"><span data-stu-id="dec28-134">The default is 4.</span></span>

  - <span data-ttu-id="dec28-135">在使用媒體的通話百分比略過，輸入您將會略過中繼伺服器的使用者所撥出通話的百分比。</span><span class="sxs-lookup"><span data-stu-id="dec28-135">In Percentage of calls that use media bypass, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="dec28-136">預設值是 65%。</span><span class="sxs-lookup"><span data-stu-id="dec28-136">The default is 65%.</span></span>

  - <span data-ttu-id="dec28-137">在語音使用者參與 UC-PSTN 通話的百分比，輸入也就是 UC-PSTN 通話貴組織的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="dec28-137">In Percentage of voice users involved in UC-PSTN calls, type the percentage of your organization’s calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="dec28-138">預設值為 60%</span><span class="sxs-lookup"><span data-stu-id="dec28-138">The default is 60%</span></span>

  - <span data-ttu-id="dec28-139">在語音使用者參與 UC-UC 通話的百分比顯示的使用者啟用 Enterprise Voice 會啟用僅適用於 UC-UC 通話的百分比。</span><span class="sxs-lookup"><span data-stu-id="dec28-139">In Percentage of voice users involved in UC-UC calls shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="dec28-140">此數字是根據計算您輸入的語音使用者啟用 UC-PSTN 通話百分比。</span><span class="sxs-lookup"><span data-stu-id="dec28-140">This number is calculated based on what you input for Percentage of voice users enabled for UC-PSTN calls.</span></span>

<span data-ttu-id="dec28-141">**會議**</span><span class="sxs-lookup"><span data-stu-id="dec28-141">**Conferencing**</span></span>

  - <span data-ttu-id="dec28-142">並行會議中的使用者百分比，輸入將會同時參與會議的使用者百分比。</span><span class="sxs-lookup"><span data-stu-id="dec28-142">In Percentage of users in concurrent conferences, type the percentage of users who will be concurrently participating in conferences.</span></span> <span data-ttu-id="dec28-143">預設值為 5%。</span><span class="sxs-lookup"><span data-stu-id="dec28-143">The default is 5%.</span></span>

  - <span data-ttu-id="dec28-144">在 [群組只 （沒有語音） IM 與會議的百分比，輸入的會議的會議，包括立即訊息僅限主動百分比亦即，不包含音訊的元件。</span><span class="sxs-lookup"><span data-stu-id="dec28-144">In Percentage of conferences with group IM only (no voice), type the percentage of conferences whose conferences will involve instant messaging only; that is, that do not include an audio component.</span></span> <span data-ttu-id="dec28-145">預設值為 10%</span><span class="sxs-lookup"><span data-stu-id="dec28-145">The default is 10%</span></span>

  - <span data-ttu-id="dec28-146">使用電話撥入式會議的使用者百分比，請輸入並行參與者在會議中將會使用電話撥入式會議的百分比。</span><span class="sxs-lookup"><span data-stu-id="dec28-146">In Percentage of users using dial-in conferencing, type the percentage of concurrent participants in conferences who will be using dial-in conferencing.</span></span> <span data-ttu-id="dec28-147">預設值為 15%。</span><span class="sxs-lookup"><span data-stu-id="dec28-147">The default is 15%.</span></span>

  - <span data-ttu-id="dec28-148">在使用語音會議的百分比，輸入將會包含音訊元件的會議的百分比。</span><span class="sxs-lookup"><span data-stu-id="dec28-148">In Percentage of conferences using voice, type the percentage of conferences that will include an audio component.</span></span>
    
      - <span data-ttu-id="dec28-149">如果 20%的語音會議也會包括一般的影片，選取 [包含視訊 （沒有多檢視） 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="dec28-149">If 20% of your voice conferences will also include regular video, select the Including video (no Multi View) check box.</span></span>
    
      - <span data-ttu-id="dec28-150">如果 20%的會議也會包括多重檢視視訊，選取 [包括多檢視] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="dec28-150">If 20% of your conferences will also include Multi-View video, select the Including Multi View check box.</span></span>
    
      - <span data-ttu-id="dec28-151">如果您的語音會議的 50%，也會包括應用程式共用，選取包含應用程式共用] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="dec28-151">If 50% of your voice conferences will also include application sharing, select the Including application sharing check box.</span></span>
    
      - <span data-ttu-id="dec28-152">如果語音會議中的 20%包含的資料上傳，例如 Microsoft PowerPoint® 簡報中，選取包含 web 會議] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="dec28-152">If 20% of your voice conferences include data uploads, such as Microsoft PowerPoint® presentations, select the Including web conferencing check box.</span></span>

<span data-ttu-id="dec28-153">**行動性**</span><span class="sxs-lookup"><span data-stu-id="dec28-153">**Mobility**</span></span>

  - <span data-ttu-id="dec28-154">在啟用行動使用者的百分比，輸入您將會連線至 Lync Server 使用行動裝置啟用的使用者百分比。</span><span class="sxs-lookup"><span data-stu-id="dec28-154">In Percentage of users enabled for Mobility, type the percentage of your users who will be enabled to connect to Lync Server using mobile devices.</span></span> <span data-ttu-id="dec28-155">預設值為 40%。</span><span class="sxs-lookup"><span data-stu-id="dec28-155">The default is 40%.</span></span>

<span data-ttu-id="dec28-156">當您輸入的所有必要資訊時，容量小算盤估計您的需求。</span><span class="sxs-lookup"><span data-stu-id="dec28-156">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="dec28-157">黃色的儲存格顯示 CPU、 記憶體和執行 Lync Server 2013 效能實驗室中測試為基礎的頻寬需求的計算的值。</span><span class="sxs-lookup"><span data-stu-id="dec28-157">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Lync Server 2013 performance labs.</span></span> <span data-ttu-id="dec28-158">數字所提供的指導方針，為不是每個單一的變化測試及驗證。</span><span class="sxs-lookup"><span data-stu-id="dec28-158">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="dec28-159">計算下列值：</span><span class="sxs-lookup"><span data-stu-id="dec28-159">The following values are calculated:</span></span>

  - <span data-ttu-id="dec28-160">Front End CPU： 如果整個負載正在處理一個前端伺服器的規格相同的伺服器所用的 CPU 使用率百分比 Microsoft 測試。</span><span class="sxs-lookup"><span data-stu-id="dec28-160">Front End CPU: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in Microsoft testing.</span></span>

  - <span data-ttu-id="dec28-161">網路以 Mbps： 在 [秒 mb (Mbps 的相對應的工作負載) 的頻寬需求。</span><span class="sxs-lookup"><span data-stu-id="dec28-161">Network in Mbps: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>

  - <span data-ttu-id="dec28-162">在 [GB 的記憶體： 在 (gb) 的相對應的工作負載所需的記憶體。</span><span class="sxs-lookup"><span data-stu-id="dec28-162">Memory in GB: Memory required in gigabytes (GB) for the corresponding workload.</span></span>

<span data-ttu-id="dec28-163">綠色的儲存格會顯示您所輸入的使用狀況模型的建議。</span><span class="sxs-lookup"><span data-stu-id="dec28-163">The green cells show recommendations for the usage model that you entered.</span></span>

  - <span data-ttu-id="dec28-164">前端伺服器總數： 所需的實體伺服器的數目取決於雙處理器，以執行 Lync Server 2013 的專用伺服器十六進位雙核心，2,260 兆週。</span><span class="sxs-lookup"><span data-stu-id="dec28-164">Total Front End Servers: The number of physical servers required are based on dedicated servers running Lync Server 2013 with dual processor, hex-core, with 2,260 megacycles.</span></span>

  - <span data-ttu-id="dec28-165">請注意，啟用超執行緒，建議證明的伺服器支援音訊/視訊提升效能。</span><span class="sxs-lookup"><span data-stu-id="dec28-165">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>

  - <span data-ttu-id="dec28-166">Edge Server: Edge Server 數目有需要，根據 30%的所有同時連線的使用者透過 Edge Server 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="dec28-166">Edge Servers: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="dec28-167">在 [小算盤] 中，無法變更此百分比。</span><span class="sxs-lookup"><span data-stu-id="dec28-167">This percentage cannot be changed in the calculator.</span></span>

  - <span data-ttu-id="dec28-168">封存/通話詳細記錄/經驗品質 services 儲存區： 所需的封存或監控功能，如果他們已啟用組織中的儲存區的數目。</span><span class="sxs-lookup"><span data-stu-id="dec28-168">Archiving/Call Detail Recording/Quality of Experience services Store: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>

  - <span data-ttu-id="dec28-169">後端資料庫伺服器所需 （集區所需）： 的後端資料庫支援的所選的工作負載所需的伺服器。</span><span class="sxs-lookup"><span data-stu-id="dec28-169">Back End Database Server Required (Pools Required): The number of back-end database servers required to support the selected workload.</span></span>

<span data-ttu-id="dec28-170">此外，總前端伺服器] 旁的列，提供詳細資訊是關於您的伺服器和網路上的負載結合的所有計劃工作負載。</span><span class="sxs-lookup"><span data-stu-id="dec28-170">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>

  - <span data-ttu-id="dec28-171">平均 CPU 負載： 平均 CPU 使用率每部前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="dec28-171">Average CPU Load: The average CPU usage per Front End server.</span></span>

  - <span data-ttu-id="dec28-172">網路以 Mbps： 所需的頻寬配置，以支援您所輸入的使用狀況模型。</span><span class="sxs-lookup"><span data-stu-id="dec28-172">Network in Mbps: The required bandwidth allocation to support the usage model that you entered.</span></span>

  - <span data-ttu-id="dec28-173">在 [GB 的記憶體： 以 gb 為單位，每一部前端伺服器所需的記憶體。</span><span class="sxs-lookup"><span data-stu-id="dec28-173">Memory in GB: Memory, in gigabytes, required for each Front End server.</span></span>

</div>

<div>

## <a name="adjusting-for-your-processors"></a><span data-ttu-id="dec28-174">調整您的處理器</span><span class="sxs-lookup"><span data-stu-id="dec28-174">Adjusting For Your Processors</span></span>

<span data-ttu-id="dec28-175">所有在試算表中的 CPU 使用量圖表假設每部伺服器具有雙處理器、 十六進位-核心 2.26 GHz，至少要有 32 GB 記憶體，與，而 8 或更多個 10000 RPM 硬碟磁碟機，每個至少 72 GB 可用磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="dec28-175">All the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>

<span data-ttu-id="dec28-176">如果您的伺服器有不同的處理器，您可以調整數據以符合您的硬體。</span><span class="sxs-lookup"><span data-stu-id="dec28-176">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

