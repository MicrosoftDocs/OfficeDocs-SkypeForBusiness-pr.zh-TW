---
title: 商務用 Skype Server 容量規劃計算機
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: '摘要: 如何使用 [產能] 計算機工具。'
ms.openlocfilehash: 24e268c6ecc3cc48fbfb4405f1e5e6b008639944
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186835"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a><span data-ttu-id="da1ba-103">商務用 Skype Server 容量規劃計算機</span><span class="sxs-lookup"><span data-stu-id="da1ba-103">Skype for Business Server Capacity Planning Calculator</span></span>
 
<span data-ttu-id="da1ba-104">**摘要:** 如何使用 [容量] 計算機工具。</span><span class="sxs-lookup"><span data-stu-id="da1ba-104">**Summary:** How to use the Capacity Calculator Tool.</span></span>

> [!NOTE]
> <span data-ttu-id="da1ba-105">本文參考商務用 Skype Server 2015 下載, 但適用于:</span><span class="sxs-lookup"><span data-stu-id="da1ba-105">This article references Skype for Business Server 2015 downloads, but it applies to:</span></span>
> - <span data-ttu-id="da1ba-106">商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="da1ba-106">Skype for Business Server 2019.</span></span>
> - <span data-ttu-id="da1ba-107">商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="da1ba-107">Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="da1ba-108">[商務用 Skype server 2015 容量計算機](https://www.microsoft.com/en-us/download/details.aspx?id=51196)及[商務用 Skype Server 2019 容量計算機](https://www.microsoft.com/en-us/download/details.aspx?id=57509)增加商務用[skype 規劃工具](https://www.microsoft.com/en-us/download/details.aspx?id=50357)和您的部署檔 ([適用于商務用 skype 的方案)。](../plan-your-deployment/plan-your-deployment.md)[針對您的商務用 Skype server 2019 部署](../../SfBServer2019/plan/plan-your-deployment-2019.md), 分別進行伺服器2015部署和規劃。</span><span class="sxs-lookup"><span data-stu-id="da1ba-108">The [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=51196) and [Skype for Business Server 2019 Capacity Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=57509) augment the [Skype for Business Planning Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50357) and your deployment documentation ([Plan for your Skype for Business Server 2015 deployment](../plan-your-deployment/plan-your-deployment.md) and [Plan for your Skype for Business Server 2019 deployment](../../SfBServer2019/plan/plan-your-deployment-2019.md) respectively).</span></span> <span data-ttu-id="da1ba-109">在您查看指南並使用規劃工具建立建議的拓撲之後, 請使用計算機。</span><span class="sxs-lookup"><span data-stu-id="da1ba-109">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>
  
<span data-ttu-id="da1ba-110">商務用 Skype 伺服器容量計算機可協助您根據貴組織使用的使用者數目和通訊工具來判斷伺服器需求。</span><span class="sxs-lookup"><span data-stu-id="da1ba-110">The Skype for Business Server Capacity Calculator helps you determine server requirements based on the number of users and the communication tools your organization uses.</span></span> <span data-ttu-id="da1ba-111">確定您的使用者設定檔和您想要為使用者啟用的函數之後, 請使用計算機來判斷您需要的伺服器、記憶體和頻寬數目。</span><span class="sxs-lookup"><span data-stu-id="da1ba-111">After you have determined your user profile and the functions you want to enable for your users, use the calculator to determine the number of servers, memory, and bandwidth you will need.</span></span> <span data-ttu-id="da1ba-112">這個版本的計算機不會提供磁片輸入/輸出需求的指導方針。</span><span class="sxs-lookup"><span data-stu-id="da1ba-112">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>
  
<span data-ttu-id="da1ba-113">如果您有有關特定使用者設定檔的準確、詳細資訊, 您可以從計算機中取得最大的益處。</span><span class="sxs-lookup"><span data-stu-id="da1ba-113">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="da1ba-114">例如, 語音啟用使用者的百分比、每個使用者每小時的平均通話數、通話持續時間, 以及會議中併發使用者的百分比, 可能會對伺服器需求產生巨大的差異。</span><span class="sxs-lookup"><span data-stu-id="da1ba-114">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="da1ba-115">計算機所建立之建議的精確度取決於您所提供資訊的準確性。</span><span class="sxs-lookup"><span data-stu-id="da1ba-115">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>
  
<span data-ttu-id="da1ba-116">在您使用規劃工具和容量規劃計算機之後, 您應該模擬您提議和規劃的載入, 以確保已充分供應商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="da1ba-116">Once you have used the Planning Tool and the Capacity Planning Calculator, you should simulate your proposed and planned load to ensure that Skype for Business Server will be adequately provisioned.</span></span> <span data-ttu-id="da1ba-117">若要在模擬的負載下執行壓力測試, 請使用商務用 skype server 壓力與[效能工具](https://technet.microsoft.com/en-us/library/mt631400.aspx)所記錄的[商務用 skype Server 壓力與效能工具](https://www.microsoft.com/en-us/download/details.aspx?id=50367)。</span><span class="sxs-lookup"><span data-stu-id="da1ba-117">To perform stress testing under a simulated load, use the [Skype for Business Server Stress and Performance Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) documented at [Skype for Business Server Stress and Performance Tool](https://technet.microsoft.com/en-us/library/mt631400.aspx).</span></span>
  
## <a name="using-the-capacity-calculator"></a><span data-ttu-id="da1ba-118">使用 [容量] 計算機</span><span class="sxs-lookup"><span data-stu-id="da1ba-118">Using the Capacity Calculator</span></span>

<span data-ttu-id="da1ba-119">計算機就是 Microsoft Excel 試算表。</span><span class="sxs-lookup"><span data-stu-id="da1ba-119">The calculator is a Microsoft Excel spreadsheet.</span></span> <span data-ttu-id="da1ba-120">您的輸入儲存格的色彩為橙色。</span><span class="sxs-lookup"><span data-stu-id="da1ba-120">Your input cells are colored orange.</span></span> <span data-ttu-id="da1ba-121">預設值是在儲存格中輸入 (針對商務用 Skype Server 2015, 在一個池中有12個前端伺服器的80000使用者), 而對於商務用 Skype Server 2019, 則是一個池中有十六個前端伺服器的106000使用者, 但是您應該將這些值變更為符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="da1ba-121">Default values are entered in the cells (For Skype for Business Server 2015, 80,000 users in one pool with twelve Front End Servers, while for Skype for Business Server 2019, 106,000 users in one pool with sixteen Front End Servers), but you should change these values to match your organization's needs.</span></span>
  
<span data-ttu-id="da1ba-122">使用方式模型包含下列各節。</span><span class="sxs-lookup"><span data-stu-id="da1ba-122">The usage model contains the following sections.</span></span> <span data-ttu-id="da1ba-123">若要計算您的容量需求, 請按照從工作表頂端開始的說明輸入資料, 並依資料列的方式進行工作:</span><span class="sxs-lookup"><span data-stu-id="da1ba-123">To calculate your capacity requirements, enter data as described starting at the top of the sheet and working down row by row:</span></span> 
  
 <span data-ttu-id="da1ba-124">**立即訊息和目前狀態**</span><span class="sxs-lookup"><span data-stu-id="da1ba-124">**Instant Messaging and Presence**</span></span>
  
- <span data-ttu-id="da1ba-125">在 [**使用者數目**] 底下, 輸入要一次登入的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="da1ba-125">Under **Number of Users**, type the number of users who will be signed in at once.</span></span> <span data-ttu-id="da1ba-126">這個數位通常是已置備使用者總數的 80%。</span><span class="sxs-lookup"><span data-stu-id="da1ba-126">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="da1ba-127">在大部分的情況下, 會針對您併發的使用者啟用 IM 和目前狀態的 100%。</span><span class="sxs-lookup"><span data-stu-id="da1ba-127">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="da1ba-128">預設值為 80000 (適用于商務用 Skype Server 2015), 以及106000商務用 Skype Server 2019 的使用者。</span><span class="sxs-lookup"><span data-stu-id="da1ba-128">The default is 80,000 for Skype for Business Server 2015, and 106,000 users for Skype for Business Server 2019.</span></span>
    
- <span data-ttu-id="da1ba-129">**連絡人清單中的連絡人平均數量**會指出我們用來驗證您系統需求的連絡人數目。</span><span class="sxs-lookup"><span data-stu-id="da1ba-129">**Average number of contacts in Contact list** indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="da1ba-130">這個數位是固定的, 不是您應該變更的內容。</span><span class="sxs-lookup"><span data-stu-id="da1ba-130">This number is fixed and not something you should change.</span></span>
    
  <span data-ttu-id="da1ba-131">**企業語音**</span><span class="sxs-lookup"><span data-stu-id="da1ba-131">**Enterprise Voice**</span></span>
  
- <span data-ttu-id="da1ba-132">在 [**企業語音啟用的使用者**] 中, 輸入您在企業語音啟用的使用者百分比。</span><span class="sxs-lookup"><span data-stu-id="da1ba-132">In **Users enabled for Enterprise Voice**, type the percentage of your users enabled for Enterprise Voice.</span></span> <span data-ttu-id="da1ba-133">預設值為 60%。</span><span class="sxs-lookup"><span data-stu-id="da1ba-133">The default is 60%.</span></span> 
    
- <span data-ttu-id="da1ba-134">在每個**使用者每小時的平均通話數 (峰值)** 中, 輸入您預計平均使用者在高峰負載期間要參與的通話次數。</span><span class="sxs-lookup"><span data-stu-id="da1ba-134">In **Average number of calls per user per hour (peak)**, type the number of calls per hour you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="da1ba-135">預設值為4。</span><span class="sxs-lookup"><span data-stu-id="da1ba-135">The default is 4.</span></span> 
    
- <span data-ttu-id="da1ba-136">在**使用 [媒體旁路] 的呼叫百分比**中, 輸入使用者將繞過中繼伺服器的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="da1ba-136">In **Percentage of calls that use media bypass**, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="da1ba-137">預設值為 65%, 但如果您散佈在地理位置, 或是從家用工作的大量使用者, 則可能會降低。</span><span class="sxs-lookup"><span data-stu-id="da1ba-137">The default is 65%, but could be lower if you are spread out geographically or have a large percentage of users who work from home.</span></span>
    
- <span data-ttu-id="da1ba-138">在**UC pstn 通話中所涉及的語音使用者百分比**中, 輸入貴組織通話的百分比, 即「UC-pstn 電話」。</span><span class="sxs-lookup"><span data-stu-id="da1ba-138">In **Percentage of voice users involved in UC-PSTN calls**, type the percentage of your organization's calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="da1ba-139">預設值為 60%。</span><span class="sxs-lookup"><span data-stu-id="da1ba-139">The default is 60%.</span></span>
    
- <span data-ttu-id="da1ba-140">**在 uc uc 通話中所涉及的語音使用者百分比**, 會顯示已啟用之企業語音的使用者百分比, 只適用于 uc-uc 通話。</span><span class="sxs-lookup"><span data-stu-id="da1ba-140">**Percentage of voice users involved in UC-UC calls** shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="da1ba-141">這個數位是根據您為**啟用 UC PSTN 通話的語音使用者百分比**所輸入的內容而計算。</span><span class="sxs-lookup"><span data-stu-id="da1ba-141">This number is calculated based on what you input for **Percentage of voice users enabled for UC-PSTN calls**.</span></span> 
    
  <span data-ttu-id="da1ba-142">**會議**</span><span class="sxs-lookup"><span data-stu-id="da1ba-142">**Conferencing**</span></span>
  
- <span data-ttu-id="da1ba-143">在**並行會議中的使用者百分比**中, 輸入將參與會議的使用者百分比。</span><span class="sxs-lookup"><span data-stu-id="da1ba-143">In **Percentage of users in concurrent conferences**, type the percentage of users who will be participating in conferences at the same time.</span></span> <span data-ttu-id="da1ba-144">預設值為 5%。</span><span class="sxs-lookup"><span data-stu-id="da1ba-144">The default is 5%.</span></span> 
    
- <span data-ttu-id="da1ba-145">在**只有「群組 IM」 (無語音) 的會議**中, 輸入將只涉及立即訊息且不包含音訊的會議百分比。</span><span class="sxs-lookup"><span data-stu-id="da1ba-145">In **Percentage of conferences with group IM only (no voice)**, type the percentage of conferences that will involve instant messaging only and do not include audio.</span></span> <span data-ttu-id="da1ba-146">預設值為 10%</span><span class="sxs-lookup"><span data-stu-id="da1ba-146">The default is 10%</span></span>
    
- <span data-ttu-id="da1ba-147">**使用電話撥入式會議的使用者百分比**, 輸入會議中一次使用電話撥入式會議的參與者百分比。</span><span class="sxs-lookup"><span data-stu-id="da1ba-147">In **Percentage of users using dial-in conferencing**, type the percentage of participants in conferences who will be using dial-in conferencing at one time.</span></span> <span data-ttu-id="da1ba-148">預設值為 15%。</span><span class="sxs-lookup"><span data-stu-id="da1ba-148">The default is 15%.</span></span>
    
- <span data-ttu-id="da1ba-149">在**使用語音的會議百分比**中, 輸入將包含音訊的會議百分比。</span><span class="sxs-lookup"><span data-stu-id="da1ba-149">In **Percentage of conferences using voice**, type the percentage of conferences that will include audio.</span></span> 
    
  - <span data-ttu-id="da1ba-150">如果 20% 的語音會議也會包含一般影片, 請選取 [**包含影片 (無多重視圖)** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="da1ba-150">If 20% of your voice conferences will also include regular video, select the **Including video (no Multi View)** check box.</span></span>
    
  - <span data-ttu-id="da1ba-151">如果 20% 的會議也會包含多個觀賞影片, 請選取 [**包括多重視圖**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="da1ba-151">If 20% of your conferences will also include Multi-View video, select the **Including Multi View** check box.</span></span>
    
  - <span data-ttu-id="da1ba-152">如果您的語音會議 50% 也會包含應用程式共用, 請選取 [**包括應用程式共用**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="da1ba-152">If 50% of your voice conferences will also include application sharing, select the **Including application sharing** check box.</span></span>
    
  - <span data-ttu-id="da1ba-153">如果您的 20% 的語音會議包含資料上傳 (例如 PowerPoint 簡報), 請選取 [**包括 web 會議**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="da1ba-153">If 20% of your voice conferences include data uploads, such as PowerPoint presentations, select the **Including web conferencing** check box.</span></span>
    
  <span data-ttu-id="da1ba-154">**行動不便**</span><span class="sxs-lookup"><span data-stu-id="da1ba-154">**Mobility**</span></span>
  
- <span data-ttu-id="da1ba-155">在**啟用行動裝置的使用者百分比**中, 輸入可使用行動裝置連線到商務用 Skype Server 的使用者百分比。</span><span class="sxs-lookup"><span data-stu-id="da1ba-155">In **Percentage of users enabled for Mobility**, type the percentage of your users who will be enabled to connect to Skype for Business Server using mobile devices.</span></span> <span data-ttu-id="da1ba-156">預設值為 40%。</span><span class="sxs-lookup"><span data-stu-id="da1ba-156">The default is 40%.</span></span> 
    
<span data-ttu-id="da1ba-157">輸入所有必要的資訊後, [容量] 計算機就會估計您的需求。</span><span class="sxs-lookup"><span data-stu-id="da1ba-157">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="da1ba-158">黃色的儲存格會根據商務用 Skype Server 效能實驗中執行的測試, 顯示 CPU、記憶體和頻寬需求的計算值。</span><span class="sxs-lookup"><span data-stu-id="da1ba-158">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Skype for Business Server performance labs.</span></span> <span data-ttu-id="da1ba-159">這些數位是作為指導原則提供的, 並非每個單一變化都經過測試和驗證。</span><span class="sxs-lookup"><span data-stu-id="da1ba-159">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="da1ba-160">會計算下列值:</span><span class="sxs-lookup"><span data-stu-id="da1ba-160">The following values are calculated:</span></span> 
  
- <span data-ttu-id="da1ba-161">**前端 cpu**: [cpu 使用量] 的百分比 (如果整個負載是由與測試中所用伺服器相同的規格) 處理 (請參閱本文結尾的說明)。</span><span class="sxs-lookup"><span data-stu-id="da1ba-161">**Front End CPU**: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in testing (see the description at the end of this article).</span></span>
    
- <span data-ttu-id="da1ba-162">**網路 (mbps**): 頻寬需求, 以每秒百萬位元 (Mbps) 為對應的工作負載。</span><span class="sxs-lookup"><span data-stu-id="da1ba-162">**Network in Mbps**: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>
    
- <span data-ttu-id="da1ba-163">**GB 記憶體**: 以千百萬位元組 (gb) 為對應的工作負荷所需的記憶體。</span><span class="sxs-lookup"><span data-stu-id="da1ba-163">**Memory in GB**: Memory required in gigabytes (GB) for the corresponding workload.</span></span>
    
<span data-ttu-id="da1ba-164">綠色的儲存格會顯示您輸入之使用方式模型的建議。</span><span class="sxs-lookup"><span data-stu-id="da1ba-164">The green cells show recommendations for the usage model that you entered.</span></span> 
  
- <span data-ttu-id="da1ba-165">**總前端伺服器**數: 所需的物理伺服器數目是以含雙處理器、十六進位 (含2260兆周期) 或商務用 skype server 2019 的專用2015伺服器 (在使用英特爾至強 E5 2673 v3, 雙處理器, 十六進位-核心。</span><span class="sxs-lookup"><span data-stu-id="da1ba-165">**Total Front End Servers**: The number of physical servers required are based on dedicated servers running Skype for Business Server 2015 with dual processor, hex-core, with 2,260 megacycles, or Skype for Business Server 2019 with Intel Xeon E5-2673 v3, dual processor, hex-core.</span></span>
    
    <span data-ttu-id="da1ba-166">請注意, 建議啟用超執行緒, 且已證實可改善支援音訊/視頻之伺服器的效能。</span><span class="sxs-lookup"><span data-stu-id="da1ba-166">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>
    
- <span data-ttu-id="da1ba-167">**Edge 伺服器**: 根據所有並行使用者透過邊緣伺服器進行通訊的 30%, 所需的邊緣伺服器數目。</span><span class="sxs-lookup"><span data-stu-id="da1ba-167">**Edge Servers**: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="da1ba-168">此百分比不能在計算機中變更。</span><span class="sxs-lookup"><span data-stu-id="da1ba-168">This percentage cannot be changed in the calculator.</span></span> 
    
- <span data-ttu-id="da1ba-169">封存 **/通話詳細資料記錄/體驗服務商店**: 如果您的組織已啟用, 則封存或監視功能所需的存放區數。</span><span class="sxs-lookup"><span data-stu-id="da1ba-169">**Archiving/Call Detail Recording/Quality of Experience services Store**: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>
    
- <span data-ttu-id="da1ba-170">**需要後端資料庫伺服器 (需要緩衝集區)**: 支援所選工作負荷所需的後端資料庫伺服器數目。</span><span class="sxs-lookup"><span data-stu-id="da1ba-170">**Back End Database Server Required (Pools Required)**: The number of back-end database servers required to support the selected workload.</span></span>
    
<span data-ttu-id="da1ba-171">此外, 在總前端伺服器旁邊的列中, 會提供更多關於您的伺服器和網路上的負載的詳細資訊, 讓所有計劃的工作負載結合在一起。</span><span class="sxs-lookup"><span data-stu-id="da1ba-171">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>
  
- <span data-ttu-id="da1ba-172">**平均 Cpu 負載**: 每個前端伺服器的平均 cpu 使用量。</span><span class="sxs-lookup"><span data-stu-id="da1ba-172">**Average CPU Load**: The average CPU usage per Front End server.</span></span>
    
- <span data-ttu-id="da1ba-173">**Network (Mbps**): 支援您輸入之使用方式模型所需的頻寬配置。</span><span class="sxs-lookup"><span data-stu-id="da1ba-173">**Network in Mbps**: The required bandwidth allocation to support the usage model that you entered.</span></span>
    
- <span data-ttu-id="da1ba-174">**GB**: 每個前端伺服器所需的記憶體, 以 gb 為限。</span><span class="sxs-lookup"><span data-stu-id="da1ba-174">**Memory in GB**: Memory, in gigabytes, required for each Front End server.</span></span>
    
### <a name="adjusting-for-your-processors"></a><span data-ttu-id="da1ba-175">調整您的處理器</span><span class="sxs-lookup"><span data-stu-id="da1ba-175">Adjusting For Your Processors</span></span>

<span data-ttu-id="da1ba-176">試算表中的所有 CPU 使用方式是假設每個商務用 Skype Server 2015 伺服器都有雙處理器、十六進位與 2.26 GHz、至少 32 GB 的記憶體, 以及至少有 72 GB 可用磁碟空間的8個或更多個 10000 RPM 硬碟磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="da1ba-176">All the CPU usage figures in the spreadsheet assume that each Skype for Business Server 2015 server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span> <span data-ttu-id="da1ba-177">針對每個商務用 Skype Server 2019 伺服器, 試算表中的所有 CPU 使用量資料都假設每個伺服器都有雙處理器、十六進位-含英特爾至強 E5 的 2673 v3、至少 64 GB 的記憶體, 以及至少有 72 GB 可用磁片的8個或更多 10000 RPM 的硬碟磁片磁碟機複雜.</span><span class="sxs-lookup"><span data-stu-id="da1ba-177">For each Skype for Business Server 2019 server, all the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with Intel Xeon E5-2673 v3, at least 64 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>
  
<span data-ttu-id="da1ba-178">如果您的伺服器有不同的處理器, 您可以調整這些資料來符合您的硬體。</span><span class="sxs-lookup"><span data-stu-id="da1ba-178">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>
  
