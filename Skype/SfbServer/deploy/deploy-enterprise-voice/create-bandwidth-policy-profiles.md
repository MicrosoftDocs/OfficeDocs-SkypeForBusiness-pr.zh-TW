---
title: 在商務用 Skype Server 中建立頻寬原則設定檔
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: 在商務用 Skype Server 中建立或修改頻寬原則，以供 Enterprise Voice 通話許可控制使用。
ms.openlocfilehash: 9458c5576d2c89254c4ee6477ede33c010cb4a21
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093241"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="2ac4e-103">在商務用 Skype Server 中建立頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="2ac4e-103">Create bandwidth policy profiles in Skype for Business Server</span></span> 
 
<span data-ttu-id="2ac4e-104">在商務用 Skype Server 中建立或修改頻寬原則，以供 Enterprise Voice 通話許可控制使用。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-104">Create or modify bandwidth policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="2ac4e-105">頻寬原則定義即時音訊和影片形式的頻寬使用量限制。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-105">Bandwidth policies define limitations on bandwidth usage for real-time audio and video modalities.</span></span> <span data-ttu-id="2ac4e-106">頻寬原則會套用至 tobandwidth 原則設定檔，可套用至多個網站以取得通話許可控制。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-106">Bandwidth policies are applied tobandwidth policy profiles, which can be applied to multiple network sites for call admission control.</span></span>
  
<span data-ttu-id="2ac4e-107">如需您在 CAC 部署中應該設定什麼頻寬限制的指導方針，請參閱 [在商務用 Skype Server 中規劃通話許可控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-107">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
<span data-ttu-id="2ac4e-108">下列程式中建立的範例原則，會設定整體音訊流量、個別音訊會話、整體影片流量和個別影片的限制。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-108">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions.</span></span> <span data-ttu-id="2ac4e-109">例如，5Mb_Link 頻寬原則設定檔會設定下列限制：</span><span class="sxs-lookup"><span data-stu-id="2ac4e-109">For example, the 5Mb_Link bandwidth policy profile sets the following limits:</span></span> 
  
- <span data-ttu-id="2ac4e-110">音訊限制： 2000 kbps</span><span class="sxs-lookup"><span data-stu-id="2ac4e-110">Audio Limit: 2,000 kbps</span></span>
    
- <span data-ttu-id="2ac4e-111">音訊會話限制： 200 kbps</span><span class="sxs-lookup"><span data-stu-id="2ac4e-111">Audio Session Limit: 200 kbps</span></span>
    
- <span data-ttu-id="2ac4e-112">影片限制： 1400 kbps</span><span class="sxs-lookup"><span data-stu-id="2ac4e-112">Video Limit: 1,400 kbps</span></span>
    
- <span data-ttu-id="2ac4e-113">影片會話限制： 700 kbps</span><span class="sxs-lookup"><span data-stu-id="2ac4e-113">Video Session Limit: 700 kbps</span></span>
    
> [!NOTE]
> <span data-ttu-id="2ac4e-114">最小音訊會話限制值為 40 kbps。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-114">The minimum Audio Session Limit value is 40 kbps.</span></span> <span data-ttu-id="2ac4e-115">最小影片會話限制值為 100 kbps。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-115">The minimum Video Session Limit value is 100 kbps.</span></span> 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="2ac4e-116">使用商務用 Skype Server 管理命令介面建立頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="2ac4e-116">To create bandwidth policy profiles by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="2ac4e-117">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-117">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2ac4e-118">針對您要建立的每個頻寬原則設定檔，執行 New-CsNetworkBandwidthPolicyProfile Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-118">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="2ac4e-119">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="2ac4e-119">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="2ac4e-120">使用商務用 Skype Server 控制台建立頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="2ac4e-120">To create bandwidth policy profiles by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="2ac4e-121">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-121">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="2ac4e-122">在左導覽列中，按一下 **[網路組態]**。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-122">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="2ac4e-123">按一下 [ **原則設定檔** ] 瀏覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-123">Click the **Policy Profile** navigation button.</span></span>
    
4. <span data-ttu-id="2ac4e-124">按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-124">Click **New**.</span></span>
    
5. <span data-ttu-id="2ac4e-125">在 [ **新增原則設定檔** ] 頁面上，按一下 [ **名稱** ]，然後輸入頻寬原則設定檔的名稱。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-125">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>
    
6. <span data-ttu-id="2ac4e-126">按一下 [ **音訊限制**]，然後輸入允許所有音訊會話組合的最大 kbps 數。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-126">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>
    
7. <span data-ttu-id="2ac4e-127">按一下 [ **音訊會話限制**]，然後輸入每個個別音訊會話允許的最大 kbps 數。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-127">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>
    
8. <span data-ttu-id="2ac4e-128">按一下 [ **影片限制**]，然後輸入要允許所有視頻會話組合的最大 kbps 數。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-128">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>
    
9. <span data-ttu-id="2ac4e-129">按一下 [ **影片會話限制**]，然後輸入每個個別影片會話允許的最大 kbps 數。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-129">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>
    
10. <span data-ttu-id="2ac4e-130">（選用）按一下 [ **描述**]，然後輸入其他資訊以描述此頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-130">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>
    
11. <span data-ttu-id="2ac4e-131">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-131">Click **Commit**.</span></span>
    
12. <span data-ttu-id="2ac4e-132">若要完成建立拓撲的頻寬原則設定檔，請使用其他頻寬原則設定檔的設定重複步驟4到11。</span><span class="sxs-lookup"><span data-stu-id="2ac4e-132">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2ac4e-133">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2ac4e-133">See also</span></span>

[<span data-ttu-id="2ac4e-134">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="2ac4e-134">New-CsNetworkBandwidthPolicyProfile</span></span>](/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="2ac4e-135">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="2ac4e-135">Get-CsNetworkBandwidthPolicyProfile</span></span>](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="2ac4e-136">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="2ac4e-136">Set-CsNetworkBandwidthPolicyProfile</span></span>](/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="2ac4e-137">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="2ac4e-137">Remove-CsNetworkBandwidthPolicyProfile</span></span>](/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)