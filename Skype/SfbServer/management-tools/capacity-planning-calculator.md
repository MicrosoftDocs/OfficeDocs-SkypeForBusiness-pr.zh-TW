---
title: 商務用 Skype Server 容量規劃電腦
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 摘要：如何使用容量計算機工具。
ms.openlocfilehash: ca7266f5a18e21dbb964f18a791de9b8903a7f0c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802993"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a><span data-ttu-id="22ee4-103">商務用 Skype Server 容量規劃電腦</span><span class="sxs-lookup"><span data-stu-id="22ee4-103">Skype for Business Server Capacity Planning Calculator</span></span>
 
<span data-ttu-id="22ee4-104">**摘要：** 如何使用容量計算機工具。</span><span class="sxs-lookup"><span data-stu-id="22ee4-104">**Summary:** How to use the Capacity Calculator Tool.</span></span>

> [!NOTE]
> <span data-ttu-id="22ee4-105">本文參考商務用 Skype Server 2015 下載，但適用于：</span><span class="sxs-lookup"><span data-stu-id="22ee4-105">This article references Skype for Business Server 2015 downloads, but it applies to:</span></span>
> - <span data-ttu-id="22ee4-106">商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="22ee4-106">Skype for Business Server 2019.</span></span>
> - <span data-ttu-id="22ee4-107">商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="22ee4-107">Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="22ee4-108">[商務用 Skype server 2015 容量計算機](https://www.microsoft.com/download/details.aspx?id=51196)和[商務用 Skype Server 2019 容量計算機](https://www.microsoft.com/download/details.aspx?id=57509)會增強商務用 skype[規劃工具](https://www.microsoft.com/download/details.aspx?id=50357)和部署檔 (規劃商務用 skype server [2015 部署](../plan-your-deployment/plan-your-deployment.md)，並[為您的商務用 skype 伺服器2019部署分別規劃](../../SfBServer2019/plan/plan-your-deployment-2019.md)) 。</span><span class="sxs-lookup"><span data-stu-id="22ee4-108">The [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196) and [Skype for Business Server 2019 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=57509) augment the [Skype for Business Planning Tool](https://www.microsoft.com/download/details.aspx?id=50357) and your deployment documentation ([Plan for your Skype for Business Server 2015 deployment](../plan-your-deployment/plan-your-deployment.md) and [Plan for your Skype for Business Server 2019 deployment](../../SfBServer2019/plan/plan-your-deployment-2019.md) respectively).</span></span> <span data-ttu-id="22ee4-109">在您複習指南並使用規劃工具建立建議的拓撲之後，使用計算機。</span><span class="sxs-lookup"><span data-stu-id="22ee4-109">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>
  
<span data-ttu-id="22ee4-110">商務用 Skype 伺服器容量計算機可協助您根據使用者人數及組織使用的通訊工具，來判斷伺服器的需求。</span><span class="sxs-lookup"><span data-stu-id="22ee4-110">The Skype for Business Server Capacity Calculator helps you determine server requirements based on the number of users and the communication tools your organization uses.</span></span> <span data-ttu-id="22ee4-111">判斷您的使用者設定檔以及您要為使用者啟用的功能之後，請使用計算機判斷所需的伺服器、記憶體及頻寬數目。</span><span class="sxs-lookup"><span data-stu-id="22ee4-111">After you have determined your user profile and the functions you want to enable for your users, use the calculator to determine the number of servers, memory, and bandwidth you will need.</span></span> <span data-ttu-id="22ee4-112">此版本的計算機不會提供磁片 I/O 需求的指導方針。</span><span class="sxs-lookup"><span data-stu-id="22ee4-112">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>
  
<span data-ttu-id="22ee4-113">如果您有特定使用者設定檔的確切詳細資訊，您可以從計算機獲得最大益處。</span><span class="sxs-lookup"><span data-stu-id="22ee4-113">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="22ee4-114">例如，啟用語音功能的使用者數目、每位使用者每小時平均通話量、通話持續時間，以及會議中並行使用者的百分比，都可能會對伺服器的需求造成極大的影響。</span><span class="sxs-lookup"><span data-stu-id="22ee4-114">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="22ee4-115">計算機所建立之建議的準確性取決於您提供的資訊準確性。</span><span class="sxs-lookup"><span data-stu-id="22ee4-115">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>
  
<span data-ttu-id="22ee4-116">當您使用規劃工具和容量規劃計算機之後，您應該模擬建議和計畫的負載，以確保已正確布建商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="22ee4-116">Once you have used the Planning Tool and the Capacity Planning Calculator, you should simulate your proposed and planned load to ensure that Skype for Business Server will be adequately provisioned.</span></span> <span data-ttu-id="22ee4-117">若要在模擬負載下執行壓力測試，請使用商務用[Skype server 壓力和效能工具](https://technet.microsoft.com/library/mt631400.aspx)中所記錄的[商務用 skype 伺服器壓力和效能工具](https://www.microsoft.com/download/details.aspx?id=50367)。</span><span class="sxs-lookup"><span data-stu-id="22ee4-117">To perform stress testing under a simulated load, use the [Skype for Business Server Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) documented at [Skype for Business Server Stress and Performance Tool](https://technet.microsoft.com/library/mt631400.aspx).</span></span>
  
## <a name="using-the-capacity-calculator"></a><span data-ttu-id="22ee4-118">使用容量計算機</span><span class="sxs-lookup"><span data-stu-id="22ee4-118">Using the Capacity Calculator</span></span>

<span data-ttu-id="22ee4-119">計算機是 Microsoft Excel 試算表。</span><span class="sxs-lookup"><span data-stu-id="22ee4-119">The calculator is a Microsoft Excel spreadsheet.</span></span> <span data-ttu-id="22ee4-120">您的輸入儲存格是彩色的橙色。</span><span class="sxs-lookup"><span data-stu-id="22ee4-120">Your input cells are colored orange.</span></span> <span data-ttu-id="22ee4-121">在 [商務用 skype Server 80000 2015] 的 [儲存格] (中輸入預設值，而在具有十二部前端伺服器的一個集區中，則會輸入預設值，但對於商務用 Skype Server 2019，一個集區中有十六部前端伺服器的106000使用者) ，但您應該變更這些值，以符合組織的需求。</span><span class="sxs-lookup"><span data-stu-id="22ee4-121">Default values are entered in the cells (For Skype for Business Server 2015, 80,000 users in one pool with twelve Front End Servers, while for Skype for Business Server 2019, 106,000 users in one pool with sixteen Front End Servers), but you should change these values to match your organization's needs.</span></span>
  
<span data-ttu-id="22ee4-122">使用模型包含下列章節。</span><span class="sxs-lookup"><span data-stu-id="22ee4-122">The usage model contains the following sections.</span></span> <span data-ttu-id="22ee4-123">若要計算您的容量需求，請輸入資料，如以下所述：從工作表頂端開始，並依列工作列：</span><span class="sxs-lookup"><span data-stu-id="22ee4-123">To calculate your capacity requirements, enter data as described starting at the top of the sheet and working down row by row:</span></span> 
  
 <span data-ttu-id="22ee4-124">**立即訊息與顯示狀態**</span><span class="sxs-lookup"><span data-stu-id="22ee4-124">**Instant Messaging and Presence**</span></span>
  
- <span data-ttu-id="22ee4-125">在 [ **使用者數目**] 底下，輸入將同時登入的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="22ee4-125">Under **Number of Users**, type the number of users who will be signed in at once.</span></span> <span data-ttu-id="22ee4-126">此數位通常是布建使用者總數的80%。</span><span class="sxs-lookup"><span data-stu-id="22ee4-126">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="22ee4-127">在大多數情況下，會為您的並行使用者啟用100% 的 IM 和目前狀態。</span><span class="sxs-lookup"><span data-stu-id="22ee4-127">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="22ee4-128">預設值為80000（適用于商務用 Skype Server 2015）和106000使用者的商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="22ee4-128">The default is 80,000 for Skype for Business Server 2015, and 106,000 users for Skype for Business Server 2019.</span></span>
    
- <span data-ttu-id="22ee4-129">**連絡人清單中的連絡人數目平均** 會指出我們所用的連絡人數目，以驗證您的系統需求。</span><span class="sxs-lookup"><span data-stu-id="22ee4-129">**Average number of contacts in Contact list** indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="22ee4-130">此號碼是固定的，而不是您應該變更的專案。</span><span class="sxs-lookup"><span data-stu-id="22ee4-130">This number is fixed and not something you should change.</span></span>
    
  <span data-ttu-id="22ee4-131">**企業語音**</span><span class="sxs-lookup"><span data-stu-id="22ee4-131">**Enterprise Voice**</span></span>
  
- <span data-ttu-id="22ee4-132">在 [ **企業語音啟用的使用者**] 中，輸入已啟用 enterprise voice 的使用者百分比。</span><span class="sxs-lookup"><span data-stu-id="22ee4-132">In **Users enabled for Enterprise Voice**, type the percentage of your users enabled for Enterprise Voice.</span></span> <span data-ttu-id="22ee4-133">預設值為60%。</span><span class="sxs-lookup"><span data-stu-id="22ee4-133">The default is 60%.</span></span> 
    
- <span data-ttu-id="22ee4-134">在 [ **每位使用者每小時平均通話數目] (峰值)** 中，輸入您預期平均使用者在尖峰負載的時間內參與平均使用者的每小時通話數目。</span><span class="sxs-lookup"><span data-stu-id="22ee4-134">In **Average number of calls per user per hour (peak)**, type the number of calls per hour you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="22ee4-135">預設值為4。</span><span class="sxs-lookup"><span data-stu-id="22ee4-135">The default is 4.</span></span> 
    
- <span data-ttu-id="22ee4-136">在 **使用媒體旁路的通話百分比** 中，輸入您的使用者所撥打的呼叫百分比，將會略過轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="22ee4-136">In **Percentage of calls that use media bypass**, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="22ee4-137">預設值為65%，但是如果您分散在不同地理位置或有大量的使用者在家中工作，則可能會較低的比例。</span><span class="sxs-lookup"><span data-stu-id="22ee4-137">The default is 65%, but could be lower if you are spread out geographically or have a large percentage of users who work from home.</span></span>
    
- <span data-ttu-id="22ee4-138">在 **UC-PSTN 通話的語音使用者百分比** 中，輸入您組織通話的百分比 UC-PSTN 電話。</span><span class="sxs-lookup"><span data-stu-id="22ee4-138">In **Percentage of voice users involved in UC-PSTN calls**, type the percentage of your organization's calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="22ee4-139">預設值為60%。</span><span class="sxs-lookup"><span data-stu-id="22ee4-139">The default is 60%.</span></span>
    
- <span data-ttu-id="22ee4-140">與 **UC-UC 通話相關之語音使用者的百分比**，會顯示已啟用 Enterprise voice 之使用者的百分比，只適用于 UC-UC 通話。</span><span class="sxs-lookup"><span data-stu-id="22ee4-140">**Percentage of voice users involved in UC-UC calls** shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="22ee4-141">這個數位是根據您為 **UC-PSTN 通話啟用之語音使用者百分比** 所輸入的專案而計算。</span><span class="sxs-lookup"><span data-stu-id="22ee4-141">This number is calculated based on what you input for **Percentage of voice users enabled for UC-PSTN calls**.</span></span> 
    
  <span data-ttu-id="22ee4-142">**會議**</span><span class="sxs-lookup"><span data-stu-id="22ee4-142">**Conferencing**</span></span>
  
- <span data-ttu-id="22ee4-143">在 [ **同時會議的使用者百分比**] 中，輸入同時參與會議的使用者百分比。</span><span class="sxs-lookup"><span data-stu-id="22ee4-143">In **Percentage of users in concurrent conferences**, type the percentage of users who will be participating in conferences at the same time.</span></span> <span data-ttu-id="22ee4-144">預設值為5%。</span><span class="sxs-lookup"><span data-stu-id="22ee4-144">The default is 5%.</span></span> 
    
- <span data-ttu-id="22ee4-145">在 [ **僅限群組 IM 的會議百分比 (無語音)**] 中，輸入只涉及立即訊息，且不包含音訊的會議百分比。</span><span class="sxs-lookup"><span data-stu-id="22ee4-145">In **Percentage of conferences with group IM only (no voice)**, type the percentage of conferences that will involve instant messaging only and do not include audio.</span></span> <span data-ttu-id="22ee4-146">預設值為10%</span><span class="sxs-lookup"><span data-stu-id="22ee4-146">The default is 10%</span></span>
    
- <span data-ttu-id="22ee4-147">在 **使用電話撥入式會議的使用者百分比** 中，輸入要在會議中一次使用電話撥入式會議的參與者百分比。</span><span class="sxs-lookup"><span data-stu-id="22ee4-147">In **Percentage of users using dial-in conferencing**, type the percentage of participants in conferences who will be using dial-in conferencing at one time.</span></span> <span data-ttu-id="22ee4-148">預設值為15%。</span><span class="sxs-lookup"><span data-stu-id="22ee4-148">The default is 15%.</span></span>
    
- <span data-ttu-id="22ee4-149">在 [ **使用語音的會議百分比**] 中，輸入要包含音訊的會議百分比。</span><span class="sxs-lookup"><span data-stu-id="22ee4-149">In **Percentage of conferences using voice**, type the percentage of conferences that will include audio.</span></span> 
    
  - <span data-ttu-id="22ee4-150">如果20% 的語音會議也會包含一般影片，請選取 [ **包含影片 (沒有多重查看)** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="22ee4-150">If 20% of your voice conferences will also include regular video, select the **Including video (no Multi View)** check box.</span></span>
    
  - <span data-ttu-id="22ee4-151">如果20% 的會議也會包含多個 View 影片，請選取 [ **包含多重查看** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="22ee4-151">If 20% of your conferences will also include Multi-View video, select the **Including Multi View** check box.</span></span>
    
  - <span data-ttu-id="22ee4-152">如果50% 的語音會議也會包含應用程式共用，請選取 [ **包括應用程式共用** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="22ee4-152">If 50% of your voice conferences will also include application sharing, select the **Including application sharing** check box.</span></span>
    
  - <span data-ttu-id="22ee4-153">如果20% 的語音會議包含資料上傳，例如 PowerPoint 簡報，請選取 [ **包含 web 會議** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="22ee4-153">If 20% of your voice conferences include data uploads, such as PowerPoint presentations, select the **Including web conferencing** check box.</span></span>
    
  <span data-ttu-id="22ee4-154">**行動性**</span><span class="sxs-lookup"><span data-stu-id="22ee4-154">**Mobility**</span></span>
  
- <span data-ttu-id="22ee4-155">在 [ **啟用行動的使用者百分比**] 中，輸入使用行動裝置啟用以連線至商務用 Skype 伺服器的使用者百分比。</span><span class="sxs-lookup"><span data-stu-id="22ee4-155">In **Percentage of users enabled for Mobility**, type the percentage of your users who will be enabled to connect to Skype for Business Server using mobile devices.</span></span> <span data-ttu-id="22ee4-156">預設值為40%。</span><span class="sxs-lookup"><span data-stu-id="22ee4-156">The default is 40%.</span></span> 
    
<span data-ttu-id="22ee4-157">當您輸入所有必要資訊之後，容量計算機會估計您的需求。</span><span class="sxs-lookup"><span data-stu-id="22ee4-157">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="22ee4-158">黃色儲存格會根據商務用 Skype Server performance labs 中所執行的測試，顯示 CPU、記憶體及頻寬需求的計算值。</span><span class="sxs-lookup"><span data-stu-id="22ee4-158">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Skype for Business Server performance labs.</span></span> <span data-ttu-id="22ee4-159">這些數位是以指導方針提供，並非每個單一變化都會經過測試及驗證。</span><span class="sxs-lookup"><span data-stu-id="22ee4-159">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="22ee4-160">計算下列值：</span><span class="sxs-lookup"><span data-stu-id="22ee4-160">The following values are calculated:</span></span> 
  
- <span data-ttu-id="22ee4-161">**前端 CPU**： cpu 使用量百分比如果整個負載的處理方式與測試中所用伺服器的規格相同，請參閱本文最後的描述) 中 (。</span><span class="sxs-lookup"><span data-stu-id="22ee4-161">**Front End CPU**: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in testing (see the description at the end of this article).</span></span>
    
- <span data-ttu-id="22ee4-162">**網路（以 mbps** 為單位）：相對於工作負載 (Mbps) 的頻寬需求（以 mb 為單位）。</span><span class="sxs-lookup"><span data-stu-id="22ee4-162">**Network in Mbps**: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>
    
- <span data-ttu-id="22ee4-163">**記憶體單位為 gb**：在對應工作量的 GB (gb) 中需要的記憶體。</span><span class="sxs-lookup"><span data-stu-id="22ee4-163">**Memory in GB**: Memory required in gigabytes (GB) for the corresponding workload.</span></span>
    
<span data-ttu-id="22ee4-164">綠色儲存格會顯示您輸入的使用模式建議。</span><span class="sxs-lookup"><span data-stu-id="22ee4-164">The green cells show recommendations for the usage model that you entered.</span></span> 
  
- <span data-ttu-id="22ee4-165">**前端伺服器總數**：所需的物理伺服器數目為以含雙處理器的商務用 skype server 2015 （含雙處理器，hex 核心，含2260的兆周期，或商務用 skype server 2019 搭配 Intel 強 2673 v3，雙處理器，hex-核心）為基礎的專用伺服器。</span><span class="sxs-lookup"><span data-stu-id="22ee4-165">**Total Front End Servers**: The number of physical servers required are based on dedicated servers running Skype for Business Server 2015 with dual processor, hex-core, with 2,260 megacycles, or Skype for Business Server 2019 with Intel Xeon E5-2673 v3, dual processor, hex-core.</span></span>
    
    <span data-ttu-id="22ee4-166">請注意，建議啟用超執行緒，並已驗證，以提升支援音訊/視頻之伺服器的效能。</span><span class="sxs-lookup"><span data-stu-id="22ee4-166">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>
    
- <span data-ttu-id="22ee4-167">**Edge server**：所需的 edge server 數目，取決於所有同時使用者透過 Edge server 進行通訊的使用者的30%。</span><span class="sxs-lookup"><span data-stu-id="22ee4-167">**Edge Servers**: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="22ee4-168">計算機中無法變更此百分比。</span><span class="sxs-lookup"><span data-stu-id="22ee4-168">This percentage cannot be changed in the calculator.</span></span> 
    
- <span data-ttu-id="22ee4-169">封存 **/通話詳細資料記錄/經驗品質服務存放區**：封存或監控功能所需的儲存區數目（如果在您的組織中已啟用）。</span><span class="sxs-lookup"><span data-stu-id="22ee4-169">**Archiving/Call Detail Recording/Quality of Experience services Store**: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>
    
- <span data-ttu-id="22ee4-170">需要 (集區所需的 **後端資料庫伺服器)**：支援所選工作負載所需的後端資料庫伺服器數目。</span><span class="sxs-lookup"><span data-stu-id="22ee4-170">**Back End Database Server Required (Pools Required)**: The number of back-end database servers required to support the selected workload.</span></span>
    
<span data-ttu-id="22ee4-171">此外，在前端伺服器總數的最後一列中，會提供更多關於伺服器和網路上的負載的資訊，以結合所有計劃的工作負載。</span><span class="sxs-lookup"><span data-stu-id="22ee4-171">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>
  
- <span data-ttu-id="22ee4-172">**平均 Cpu 負載**：每個前端伺服器的平均 cpu 使用量。</span><span class="sxs-lookup"><span data-stu-id="22ee4-172">**Average CPU Load**: The average CPU usage per Front End server.</span></span>
    
- <span data-ttu-id="22ee4-173">**網路（以 Mbps 為單位**）：支援您輸入的使用模式所需的頻寬配置。</span><span class="sxs-lookup"><span data-stu-id="22ee4-173">**Network in Mbps**: The required bandwidth allocation to support the usage model that you entered.</span></span>
    
- <span data-ttu-id="22ee4-174">**記憶體單位為 gb**：每一部前端伺服器所需的記憶體（gb）。</span><span class="sxs-lookup"><span data-stu-id="22ee4-174">**Memory in GB**: Memory, in gigabytes, required for each Front End server.</span></span>
    
### <a name="adjusting-for-your-processors"></a><span data-ttu-id="22ee4-175">調整您的處理器</span><span class="sxs-lookup"><span data-stu-id="22ee4-175">Adjusting For Your Processors</span></span>

<span data-ttu-id="22ee4-176">試算表中的所有 CPU 使用量圖假設每一部商務用 Skype Server 2015 伺服器都有雙處理器、hex 核心和 2.26 GHz，至少有 32 GB 的記憶體，以及8個或更多的 10000 RPM 硬碟，至少有 72 GB 的可用磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="22ee4-176">All the CPU usage figures in the spreadsheet assume that each Skype for Business Server 2015 server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span> <span data-ttu-id="22ee4-177">針對每個商務用 Skype Server 2019 server，試算表中的所有 CPU 使用狀況圖表都會假定每個伺服器都有雙處理器、hex 核心與 Intel 強 E5 2673 v3，至少 64 GB 的記憶體，以及8個或更多的 10000 RPM 硬碟，至少有 72 GB 的可用磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="22ee4-177">For each Skype for Business Server 2019 server, all the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with Intel Xeon E5-2673 v3, at least 64 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>
  
<span data-ttu-id="22ee4-178">如果您的伺服器具有不同的處理器，您可以調整這些圖形，使其符合您的硬體。</span><span class="sxs-lookup"><span data-stu-id="22ee4-178">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>
  
