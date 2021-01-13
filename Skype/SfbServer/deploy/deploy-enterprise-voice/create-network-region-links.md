---
title: 在商務用 Skype Server 中建立網路地區連結
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
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: 在商務用 Skype Server 中建立或修改網路地區連結，以供 Enterprise Voice 通話許可控制使用。
ms.openlocfilehash: 1b891a299e85836e4a69b4a6c6e9df9a52cb0cdc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822463"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a><span data-ttu-id="1c301-103">在商務用 Skype Server 中建立網路地區連結</span><span class="sxs-lookup"><span data-stu-id="1c301-103">Create network region links in Skype for Business Server</span></span>
 
<span data-ttu-id="1c301-104">在商務用 Skype Server 中建立或修改網路地區連結，以供 Enterprise Voice 通話許可控制使用。</span><span class="sxs-lookup"><span data-stu-id="1c301-104">Create or modify network region links, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="1c301-105">網路中的區域是透過實體 WAN 連線相互連結。</span><span class="sxs-lookup"><span data-stu-id="1c301-105">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="1c301-106">網路地區連結會在設定為通話許可控制的兩個地區之間建立連結 (CAC) 並設定這些地區之間音訊和影片流量的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="1c301-106">A network region link creates a link between two regions configured for Call Admission Control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>
  
<span data-ttu-id="1c301-107">這個範例拓撲有一個北美和 APAC 地區之間的連結，以及 EMEA 和 APAC 地區之間的連結。</span><span class="sxs-lookup"><span data-stu-id="1c301-107">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="1c301-108">每個地區連結都受 WAN 頻寬限制，如地區連結頻寬資訊表格中所述 [：在商務用 Skype Server 中收集通話許可控制的需求](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1c301-108">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1c301-109">使用商務用 Skype Server 管理命令介面建立網路地區連結</span><span class="sxs-lookup"><span data-stu-id="1c301-109">To create network region links by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="1c301-110">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="1c301-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="1c301-111">執行 New-CsNetworkRegionLink Cmdlet 來建立地區連結，並套用適當的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="1c301-111">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles.</span></span> <span data-ttu-id="1c301-112">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="1c301-112">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```powershell
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1c301-113">使用商務用 Skype Server 控制台建立網路地區連結</span><span class="sxs-lookup"><span data-stu-id="1c301-113">To create network region links by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1c301-114">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="1c301-114">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="1c301-115">在左導覽列中，按一下 **[網路組態]**。</span><span class="sxs-lookup"><span data-stu-id="1c301-115">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="1c301-116">按一下 [ **地區連結** ] 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="1c301-116">Click the **Region Link** navigation button.</span></span>
    
4. <span data-ttu-id="1c301-117">按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="1c301-117">Click **New**.</span></span>
    
5. <span data-ttu-id="1c301-118">在 [ **新增地區連結** ] 頁面上，按一下 [ **名稱** ]，然後輸入網路地區連結的名稱。</span><span class="sxs-lookup"><span data-stu-id="1c301-118">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>
    
6. <span data-ttu-id="1c301-119">按一下 [ **網路地區 #1**]，然後按一下清單中要連結至 [網路地區] 的網路地區 #2。</span><span class="sxs-lookup"><span data-stu-id="1c301-119">Click **Network Region #1**, and then click the network region in the list that you want to link to Network Region #2.</span></span>
    
7. <span data-ttu-id="1c301-120">按一下 [ **網路地區 #2**]，然後按一下清單中要連結至 [網路地區] 的網路地區 #1。</span><span class="sxs-lookup"><span data-stu-id="1c301-120">Click **Network Region #2**, and then click a network region in the list that you want to link to Network Region #1.</span></span>
    
8. <span data-ttu-id="1c301-121">（選用）按一下 [ **頻寬原則**]，然後選取您要套用到網路地區連結的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="1c301-121">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1c301-122">[！注意事項] 只有在網路地區連結受到頻寬限制，且您想要使用 CAC 來控制該連結上的媒體流量時，才套用頻寬原則。</span><span class="sxs-lookup"><span data-stu-id="1c301-122">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span> 
  
9. <span data-ttu-id="1c301-123">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="1c301-123">Click **Commit**.</span></span>
    
10. <span data-ttu-id="1c301-124">若要完成建立拓撲的網路地區連結，請使用其他地區的設定重複步驟4到9。</span><span class="sxs-lookup"><span data-stu-id="1c301-124">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1c301-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1c301-125">See also</span></span>

[<span data-ttu-id="1c301-126">新 CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="1c301-126">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="1c301-127">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="1c301-127">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="1c301-128">CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="1c301-128">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="1c301-129">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="1c301-129">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)
