---
title: Skype for Business 伺服器容量規劃小算盤
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要： 如何使用容量計算器工具。
ms.openlocfilehash: 1bb1c9cde82c1f2d6e487c3bc28520b630d59210
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031077"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a><span data-ttu-id="bc7da-103">Skype for Business 伺服器容量規劃小算盤</span><span class="sxs-lookup"><span data-stu-id="bc7da-103">Skype for Business Server Capacity Planning Calculator</span></span>
 
<span data-ttu-id="bc7da-104">**摘要：** 如何使用容量計算器工具。</span><span class="sxs-lookup"><span data-stu-id="bc7da-104">**Summary:** How to use the Capacity Calculator Tool.</span></span>

> [!NOTE]
> <span data-ttu-id="bc7da-105">本文的參考用 Skype Server 2015 下載項目，但它適用於：</span><span class="sxs-lookup"><span data-stu-id="bc7da-105">This article references Skype for Business Server 2015 downloads, but it applies to:</span></span>
> - <span data-ttu-id="bc7da-106">Skype for Business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="bc7da-106">Skype for Business Server 2019.</span></span>
> - <span data-ttu-id="bc7da-107">Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="bc7da-107">Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="bc7da-108">[Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196)與[Skype for Business Server 2019 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=57509)增強[Skype for Business 規劃工具](https://www.microsoft.com/download/details.aspx?id=50357)和部署文件 ([您用 Skype Server 2015 部署規劃](../plan-your-deployment/plan-your-deployment.md)及[規劃您 Skype for Business Server 2019 部署](../../SfBServer2019/plan/plan-your-deployment-2019.md)分別)。</span><span class="sxs-lookup"><span data-stu-id="bc7da-108">The [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196) and [Skype for Business Server 2019 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=57509) augment the [Skype for Business Planning Tool](https://www.microsoft.com/download/details.aspx?id=50357) and your deployment documentation ([Plan for your Skype for Business Server 2015 deployment](../plan-your-deployment/plan-your-deployment.md) and [Plan for your Skype for Business Server 2019 deployment](../../SfBServer2019/plan/plan-your-deployment-2019.md) respectively).</span></span> <span data-ttu-id="bc7da-109">您已檢閱快顯功能表，並使用規劃工具所建立的建議的拓撲之後，請使用 [小算盤]。</span><span class="sxs-lookup"><span data-stu-id="bc7da-109">Use the calculator after you have reviewed the guide and created a recommended topology by using the Planning Tool.</span></span>
  
<span data-ttu-id="bc7da-110">Skype for Business 伺服器容量計算器可協助您決定使用者數目和您的組織使用的通訊工具為基礎的伺服器需求。</span><span class="sxs-lookup"><span data-stu-id="bc7da-110">The Skype for Business Server Capacity Calculator helps you determine server requirements based on the number of users and the communication tools your organization uses.</span></span> <span data-ttu-id="bc7da-111">您已決定您的使用者設定檔，並且想要啟用使用者的功能之後，使用 [小算盤] 來判斷伺服器、 記憶體及您需要的頻寬的數目。</span><span class="sxs-lookup"><span data-stu-id="bc7da-111">After you have determined your user profile and the functions you want to enable for your users, use the calculator to determine the number of servers, memory, and bandwidth you will need.</span></span> <span data-ttu-id="bc7da-112">此版本的計算機不提供指引磁碟 I/O 的需求。</span><span class="sxs-lookup"><span data-stu-id="bc7da-112">This version of the calculator does not provide guidance for disk I/O requirements.</span></span>
  
<span data-ttu-id="bc7da-113">您可以享有最 [小算盤] 如果您有關於您的特定使用者設定檔的精確、 詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="bc7da-113">You can benefit most from the calculator if you have accurate, detailed information about your specific user profile.</span></span> <span data-ttu-id="bc7da-114">例如，已啟用語音的使用者，每位使用者每小時、 通話持續期間，並在會議中並行使用者的百分比的平均通話的百分比可以讓伺服器需求極大差異。</span><span class="sxs-lookup"><span data-stu-id="bc7da-114">For example, the percentage of voice-enabled users, average calls per user per hour, call duration, and the percentage of concurrent users in conferences can make a huge difference in server requirements.</span></span> <span data-ttu-id="bc7da-115">[小算盤] 所建立的建議的準確性取決於您所提供的資訊的正確性。</span><span class="sxs-lookup"><span data-stu-id="bc7da-115">The accuracy of the recommendations created by the calculator depends on the accuracy of the information that you provide.</span></span>
  
<span data-ttu-id="bc7da-116">一旦您已使用規劃工具和容量規劃小算盤，您應該模擬您建議與計劃的負載，以確保，Skype for Business Server 適當地佈建。</span><span class="sxs-lookup"><span data-stu-id="bc7da-116">Once you have used the Planning Tool and the Capacity Planning Calculator, you should simulate your proposed and planned load to ensure that Skype for Business Server will be adequately provisioned.</span></span> <span data-ttu-id="bc7da-117">若要執行壓力測試模擬的負載下，使用記載在[Skype for Business Server 壓力及效能工具](https://technet.microsoft.com/library/mt631400.aspx) [Skype for Business Server 壓力及效能工具](https://www.microsoft.com/download/details.aspx?id=50367)。</span><span class="sxs-lookup"><span data-stu-id="bc7da-117">To perform stress testing under a simulated load, use the [Skype for Business Server Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) documented at [Skype for Business Server Stress and Performance Tool](https://technet.microsoft.com/library/mt631400.aspx).</span></span>
  
## <a name="using-the-capacity-calculator"></a><span data-ttu-id="bc7da-118">使用容量的小算盤</span><span class="sxs-lookup"><span data-stu-id="bc7da-118">Using the Capacity Calculator</span></span>

<span data-ttu-id="bc7da-119">小算盤] 位於 Microsoft Excel 試算表。</span><span class="sxs-lookup"><span data-stu-id="bc7da-119">The calculator is a Microsoft Excel spreadsheet.</span></span> <span data-ttu-id="bc7da-120">您輸入的儲存格被彩色橙色。</span><span class="sxs-lookup"><span data-stu-id="bc7da-120">Your input cells are colored orange.</span></span> <span data-ttu-id="bc7da-121">預設值輸入中的儲存格 (如商務用 Skype Server 2015，與十二個前端伺服器，如 Skype for Business Server 2019，106,000 使用者十六個前端伺服器與一個集區中的一個集區中的 80000 位使用者)，但您應該變更這些值，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="bc7da-121">Default values are entered in the cells (For Skype for Business Server 2015, 80,000 users in one pool with twelve Front End Servers, while for Skype for Business Server 2019, 106,000 users in one pool with sixteen Front End Servers), but you should change these values to match your organization's needs.</span></span>
  
<span data-ttu-id="bc7da-122">使用模型包含下列各節。</span><span class="sxs-lookup"><span data-stu-id="bc7da-122">The usage model contains the following sections.</span></span> <span data-ttu-id="bc7da-123">若要計算容量需求，請輸入資料所述的工作表從頂端開始，並開始向下逐列：</span><span class="sxs-lookup"><span data-stu-id="bc7da-123">To calculate your capacity requirements, enter data as described starting at the top of the sheet and working down row by row:</span></span> 
  
 <span data-ttu-id="bc7da-124">**立即訊息和目前狀態**</span><span class="sxs-lookup"><span data-stu-id="bc7da-124">**Instant Messaging and Presence**</span></span>
  
- <span data-ttu-id="bc7da-125">[**使用者數量**] 下方輸入會一次登入的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="bc7da-125">Under **Number of Users**, type the number of users who will be signed in at once.</span></span> <span data-ttu-id="bc7da-126">此數字通常為 80%的佈建的使用者總數。</span><span class="sxs-lookup"><span data-stu-id="bc7da-126">This number is typically 80% of the total number of provisioned users.</span></span> <span data-ttu-id="bc7da-127">在大部分情況下，100%的並行使用者將會啟用 IM 和目前狀態。</span><span class="sxs-lookup"><span data-stu-id="bc7da-127">In most situations, 100% of your concurrent users will be enabled for IM and Presence.</span></span> <span data-ttu-id="bc7da-128">預設值為 80000 商務用 Skype Server 2015，與 Skype for Business Server 2019 的 106,000 使用者。</span><span class="sxs-lookup"><span data-stu-id="bc7da-128">The default is 80,000 for Skype for Business Server 2015, and 106,000 users for Skype for Business Server 2019.</span></span>
    
- <span data-ttu-id="bc7da-129">**在連絡人清單中的連絡人的平均數目**表示我們正在用來驗證您的系統需求的連絡人數目。</span><span class="sxs-lookup"><span data-stu-id="bc7da-129">**Average number of contacts in Contact list** indicates the number of contacts that we are using to validate your system requirements.</span></span> <span data-ttu-id="bc7da-130">此數字固定，並不是您應該變更。</span><span class="sxs-lookup"><span data-stu-id="bc7da-130">This number is fixed and not something you should change.</span></span>
    
  <span data-ttu-id="bc7da-131">**企業語音**</span><span class="sxs-lookup"><span data-stu-id="bc7da-131">**Enterprise Voice**</span></span>
  
- <span data-ttu-id="bc7da-132">在**使用者啟用 Enterprise Voice**，輸入您的使用者啟用 Enterprise Voice 的百分比。</span><span class="sxs-lookup"><span data-stu-id="bc7da-132">In **Users enabled for Enterprise Voice**, type the percentage of your users enabled for Enterprise Voice.</span></span> <span data-ttu-id="bc7da-133">預設值為 60%。</span><span class="sxs-lookup"><span data-stu-id="bc7da-133">The default is 60%.</span></span> 
    
- <span data-ttu-id="bc7da-134">在**每位使用者每小時 （尖峰時） 通話的平均數目**，輸入您預期一般使用者參與的尖峰負載時段每小時來電數目。</span><span class="sxs-lookup"><span data-stu-id="bc7da-134">In **Average number of calls per user per hour (peak)**, type the number of calls per hour you expect the average user to participate in during times of peak load.</span></span> <span data-ttu-id="bc7da-135">預設值為 4。</span><span class="sxs-lookup"><span data-stu-id="bc7da-135">The default is 4.</span></span> 
    
- <span data-ttu-id="bc7da-136">**使用媒體旁路的通話百分比**，請輸入您將會略過中繼伺服器的使用者所撥出通話的百分比。</span><span class="sxs-lookup"><span data-stu-id="bc7da-136">In **Percentage of calls that use media bypass**, type the percentage of calls placed by your users that will bypass the Mediation Server.</span></span> <span data-ttu-id="bc7da-137">預設值是 65%，但無法為較低，如果您改變會展現地理位置，或具有高百分比的使用者在家工作。</span><span class="sxs-lookup"><span data-stu-id="bc7da-137">The default is 65%, but could be lower if you are spread out geographically or have a large percentage of users who work from home.</span></span>
    
- <span data-ttu-id="bc7da-138">**語音使用者參與 UC-PSTN 通話的百分比**，請輸入貴組織的呼叫，也就是 UC-PSTN 通話的百分比。</span><span class="sxs-lookup"><span data-stu-id="bc7da-138">In **Percentage of voice users involved in UC-PSTN calls**, type the percentage of your organization's calls which are UC-PSTN phone calls.</span></span> <span data-ttu-id="bc7da-139">預設值為 60%。</span><span class="sxs-lookup"><span data-stu-id="bc7da-139">The default is 60%.</span></span>
    
- <span data-ttu-id="bc7da-140">**語音使用者參與 UC-UC 通話的百分比**顯示的使用者啟用 Enterprise Voice 會啟用僅適用於 UC-UC 通話的百分比。</span><span class="sxs-lookup"><span data-stu-id="bc7da-140">**Percentage of voice users involved in UC-UC calls** shows the percentage of users who are enabled for Enterprise Voice who will be enabled only for UC-UC calls.</span></span> <span data-ttu-id="bc7da-141">此數字是根據計算您輸入**的語音使用者啟用 UC-PSTN 通話**百分比。</span><span class="sxs-lookup"><span data-stu-id="bc7da-141">This number is calculated based on what you input for **Percentage of voice users enabled for UC-PSTN calls**.</span></span> 
    
  <span data-ttu-id="bc7da-142">**會議**</span><span class="sxs-lookup"><span data-stu-id="bc7da-142">**Conferencing**</span></span>
  
- <span data-ttu-id="bc7da-143">**並行會議中使用者的百分比**，請輸入使用者將參與會議在同一時間的百分比。</span><span class="sxs-lookup"><span data-stu-id="bc7da-143">In **Percentage of users in concurrent conferences**, type the percentage of users who will be participating in conferences at the same time.</span></span> <span data-ttu-id="bc7da-144">預設值為 5%。</span><span class="sxs-lookup"><span data-stu-id="bc7da-144">The default is 5%.</span></span> 
    
- <span data-ttu-id="bc7da-145">在**群組只 （沒有語音） IM 與會議的百分比**，輸入的立即訊息只會牽涉到，且不包含音訊會議的百分比。</span><span class="sxs-lookup"><span data-stu-id="bc7da-145">In **Percentage of conferences with group IM only (no voice)**, type the percentage of conferences that will involve instant messaging only and do not include audio.</span></span> <span data-ttu-id="bc7da-146">預設值為 10%</span><span class="sxs-lookup"><span data-stu-id="bc7da-146">The default is 10%</span></span>
    
- <span data-ttu-id="bc7da-147">在**百分比的使用者使用電話撥入式會議**，請輸入在會議中將會使用電話撥入式會議，一次的與會者百分比。</span><span class="sxs-lookup"><span data-stu-id="bc7da-147">In **Percentage of users using dial-in conferencing**, type the percentage of participants in conferences who will be using dial-in conferencing at one time.</span></span> <span data-ttu-id="bc7da-148">預設值為 15%。</span><span class="sxs-lookup"><span data-stu-id="bc7da-148">The default is 15%.</span></span>
    
- <span data-ttu-id="bc7da-149">**使用語音會議的百分比**，請輸入內含音訊會議的百分比。</span><span class="sxs-lookup"><span data-stu-id="bc7da-149">In **Percentage of conferences using voice**, type the percentage of conferences that will include audio.</span></span> 
    
  - <span data-ttu-id="bc7da-150">如果 20%的語音會議也會包括一般的影片，請選取 [**包括視訊 （沒有多檢視表）** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bc7da-150">If 20% of your voice conferences will also include regular video, select the **Including video (no Multi View)** check box.</span></span>
    
  - <span data-ttu-id="bc7da-151">如果 20%的會議也會包括多重檢視視訊，選取 [**包括多檢視**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bc7da-151">If 20% of your conferences will also include Multi-View video, select the **Including Multi View** check box.</span></span>
    
  - <span data-ttu-id="bc7da-152">如果您的語音會議的 50%，也會包括應用程式共用，選取 [**包括應用程式共用**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bc7da-152">If 50% of your voice conferences will also include application sharing, select the **Including application sharing** check box.</span></span>
    
  - <span data-ttu-id="bc7da-153">如果語音會議中的 20%包含的資料上傳 PowerPoint 簡報，例如選取 [**包括 web 會議**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bc7da-153">If 20% of your voice conferences include data uploads, such as PowerPoint presentations, select the **Including web conferencing** check box.</span></span>
    
  <span data-ttu-id="bc7da-154">**行動性**</span><span class="sxs-lookup"><span data-stu-id="bc7da-154">**Mobility**</span></span>
  
- <span data-ttu-id="bc7da-155">在**啟用行動使用者的百分比**，輸入您將會連線到 Skype for Business Server 使用行動裝置啟用的使用者百分比。</span><span class="sxs-lookup"><span data-stu-id="bc7da-155">In **Percentage of users enabled for Mobility**, type the percentage of your users who will be enabled to connect to Skype for Business Server using mobile devices.</span></span> <span data-ttu-id="bc7da-156">預設值為 40%。</span><span class="sxs-lookup"><span data-stu-id="bc7da-156">The default is 40%.</span></span> 
    
<span data-ttu-id="bc7da-157">當您輸入的所有必要資訊時，容量小算盤估計您的需求。</span><span class="sxs-lookup"><span data-stu-id="bc7da-157">When you have entered all the necessary information, the capacity calculator estimates your requirements.</span></span> <span data-ttu-id="bc7da-158">黃色的儲存格顯示 CPU、 記憶體及根據 skype for Business Server 效能實驗室執行測試的頻寬需求的計算的值。</span><span class="sxs-lookup"><span data-stu-id="bc7da-158">The yellow cells show calculated values for CPU, memory, and bandwidth requirements based on tests performed in Skype for Business Server performance labs.</span></span> <span data-ttu-id="bc7da-159">數字所提供的指導方針，為不是每個單一的變化測試及驗證。</span><span class="sxs-lookup"><span data-stu-id="bc7da-159">The numbers are provided as a guideline, not every single variation is tested and validated.</span></span> <span data-ttu-id="bc7da-160">計算下列值：</span><span class="sxs-lookup"><span data-stu-id="bc7da-160">The following values are calculated:</span></span> 
  
- <span data-ttu-id="bc7da-161">**Front End CPU**： 如果一部前端伺服器的規格相同的伺服器，用於測試 （請參閱本文結尾處的描述） 會被處理整個負載的百分比的 CPU 使用量。</span><span class="sxs-lookup"><span data-stu-id="bc7da-161">**Front End CPU**: Percentage of CPU usage if the entire load were being handled by one Front End Server of the same specifications as the server that was used in testing (see the description at the end of this article).</span></span>
    
- <span data-ttu-id="bc7da-162">**網路以 Mbps**： 在 [秒 mb (Mbps 的相對應的工作負載) 的頻寬需求。</span><span class="sxs-lookup"><span data-stu-id="bc7da-162">**Network in Mbps**: Bandwidth requirements in megabits per second (Mbps) for the corresponding workload.</span></span>
    
- <span data-ttu-id="bc7da-163">**在 [GB 的記憶體**： 在 (gb) 的相對應的工作負載所需的記憶體。</span><span class="sxs-lookup"><span data-stu-id="bc7da-163">**Memory in GB**: Memory required in gigabytes (GB) for the corresponding workload.</span></span>
    
<span data-ttu-id="bc7da-164">綠色的儲存格會顯示您所輸入的使用狀況模型的建議。</span><span class="sxs-lookup"><span data-stu-id="bc7da-164">The green cells show recommendations for the usage model that you entered.</span></span> 
  
- <span data-ttu-id="bc7da-165">**總前端伺服器**： 所需的實體伺服器的數目取決於執行用 Skype Server 2015 與雙處理器，專用伺服器十六進位核心、 2,260 兆週，或 Skype for Business Server 2019 與 Intel Xeon E5 2673 v3、 雙處理器、 十六進位核心。</span><span class="sxs-lookup"><span data-stu-id="bc7da-165">**Total Front End Servers**: The number of physical servers required are based on dedicated servers running Skype for Business Server 2015 with dual processor, hex-core, with 2,260 megacycles, or Skype for Business Server 2019 with Intel Xeon E5-2673 v3, dual processor, hex-core.</span></span>
    
    <span data-ttu-id="bc7da-166">請注意，啟用超執行緒，建議證明的伺服器支援音訊/視訊提升效能。</span><span class="sxs-lookup"><span data-stu-id="bc7da-166">Note that enabling hyperthreading is recommended and has been proven to improve performance for servers that support audio/video.</span></span>
    
- <span data-ttu-id="bc7da-167">**Edge Server**： 邊際伺服器的數目，根據 30%的所有同時連線的使用者透過 Edge Server 通訊所需。</span><span class="sxs-lookup"><span data-stu-id="bc7da-167">**Edge Servers**: The number of Edge Servers required, based on 30% of all concurrent users communicating through the Edge Servers.</span></span> <span data-ttu-id="bc7da-168">在 [小算盤] 中，無法變更此百分比。</span><span class="sxs-lookup"><span data-stu-id="bc7da-168">This percentage cannot be changed in the calculator.</span></span> 
    
- <span data-ttu-id="bc7da-169">**封存/通話詳細資料錄製/品質的體驗 services 儲存區**： 所需的封存或監控功能，如果他們已啟用組織中的儲存區的數目。</span><span class="sxs-lookup"><span data-stu-id="bc7da-169">**Archiving/Call Detail Recording/Quality of Experience services Store**: The number of stores required for Archiving or Monitoring features, if they are enabled in your organization.</span></span>
    
- <span data-ttu-id="bc7da-170">**後端資料庫伺服器必要 （集區所需）**： 支援的所選的工作負載所需的後端資料庫伺服器的數目。</span><span class="sxs-lookup"><span data-stu-id="bc7da-170">**Back End Database Server Required (Pools Required)**: The number of back-end database servers required to support the selected workload.</span></span>
    
<span data-ttu-id="bc7da-171">此外，總前端伺服器] 旁的列，提供詳細資訊是關於您的伺服器和網路上的負載結合的所有計劃工作負載。</span><span class="sxs-lookup"><span data-stu-id="bc7da-171">Additionally, in the row next to Total Front End Servers, more information is provided about the load on your servers and network for all the planned workloads combined.</span></span>
  
- <span data-ttu-id="bc7da-172">**平均 CPU 負載**： 每個前端伺服器的平均 CPU 使用率。</span><span class="sxs-lookup"><span data-stu-id="bc7da-172">**Average CPU Load**: The average CPU usage per Front End server.</span></span>
    
- <span data-ttu-id="bc7da-173">**網路以 Mbps**： 所需的頻寬配置，以支援您所輸入的使用狀況模型。</span><span class="sxs-lookup"><span data-stu-id="bc7da-173">**Network in Mbps**: The required bandwidth allocation to support the usage model that you entered.</span></span>
    
- <span data-ttu-id="bc7da-174">**在 [GB 的記憶體**： 以 gb 為單位，每一部前端伺服器所需的記憶體。</span><span class="sxs-lookup"><span data-stu-id="bc7da-174">**Memory in GB**: Memory, in gigabytes, required for each Front End server.</span></span>
    
### <a name="adjusting-for-your-processors"></a><span data-ttu-id="bc7da-175">調整您的處理器</span><span class="sxs-lookup"><span data-stu-id="bc7da-175">Adjusting For Your Processors</span></span>

<span data-ttu-id="bc7da-176">所有在試算表中的 CPU 使用量圖表假設每個商務用 Skype Server 2015 伺服器具有雙處理器、 十六進位-核心 2.26 GHz，至少要有 32 GB 記憶體，與，而 8 或更多個 10000 RPM 硬碟磁碟機，每個至少 72 GB 可用磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="bc7da-176">All the CPU usage figures in the spreadsheet assume that each Skype for Business Server 2015 server has a dual processor, hex-core with 2.26 GHz, at least 32 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span> <span data-ttu-id="bc7da-177">針對每個 Skype for Business Server 2019 伺服器中，所有在試算表中的 CPU 使用量圖表假設每個伺服器有雙處理器、 十六進位雙核心 Intel Xeon E5 2673 v3，至少 64 GB 的記憶體，與，而 8 或更多個 10000 RPM 硬碟磁碟機，每個至少 72 GB 可用磁碟 s速度。</span><span class="sxs-lookup"><span data-stu-id="bc7da-177">For each Skype for Business Server 2019 server, all the CPU usage figures in the spreadsheet assume that each server has a dual processor, hex-core with Intel Xeon E5-2673 v3, at least 64 GB of memory, and 8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span>
  
<span data-ttu-id="bc7da-178">如果您的伺服器有不同的處理器，您可以調整數據以符合您的硬體。</span><span class="sxs-lookup"><span data-stu-id="bc7da-178">If your servers have different processors, you can adjust the figures to match your hardware.</span></span>
  
