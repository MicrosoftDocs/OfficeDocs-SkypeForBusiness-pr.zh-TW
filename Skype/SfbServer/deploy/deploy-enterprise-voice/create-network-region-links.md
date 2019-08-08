---
title: 在商務用 Skype Server 中建立網路區域連結
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: 在商務用 Skype Server 中建立或修改 [企業語音通話許可控制] 所使用的網路區域連結。
ms.openlocfilehash: 2b2eb99fa59125c93d97b902b6fbaad122ffdcdf
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233691"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a><span data-ttu-id="c5f67-103">在商務用 Skype Server 中建立網路區域連結</span><span class="sxs-lookup"><span data-stu-id="c5f67-103">Create network region links in Skype for Business Server</span></span>
 
<span data-ttu-id="c5f67-104">在商務用 Skype Server 中建立或修改 [企業語音通話許可控制] 所使用的網路區域連結。</span><span class="sxs-lookup"><span data-stu-id="c5f67-104">Create or modify network region links, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="c5f67-105">網路中的區域是透過物理 WAN 連線來連結。</span><span class="sxs-lookup"><span data-stu-id="c5f67-105">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="c5f67-106">[網路區域] 連結會建立兩個設定為 [呼叫許可控制] (CAC) 的區域之間的連結, 並設定這些區域之間音訊與視頻流量的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="c5f67-106">A network region link creates a link between two regions configured for Call Admission Control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>
  
<span data-ttu-id="c5f67-107">此範例拓撲在北美與 APAC 區域之間有連結, 以及 EMEA 與 APAC 區域之間的連結。</span><span class="sxs-lookup"><span data-stu-id="c5f67-107">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="c5f67-108">上述每一個區域連結都受 WAN 頻寬的限制, 如地區連結頻寬資訊資料表中所述[: 在商務用 Skype Server 中收集通話許可控制需求](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c5f67-108">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c5f67-109">使用商務用 Skype Server Management Shell 建立網路區域連結</span><span class="sxs-lookup"><span data-stu-id="c5f67-109">To create network region links by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="c5f67-110">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="c5f67-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c5f67-111">執行新的 CsNetworkRegionLink Cmdlet 來建立區域連結, 並套用適當的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="c5f67-111">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles.</span></span> <span data-ttu-id="c5f67-112">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="c5f67-112">For example, run:</span></span>
    
   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c5f67-113">使用商務用 Skype Server [控制台] 建立網路區域連結</span><span class="sxs-lookup"><span data-stu-id="c5f67-113">To create network region links by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c5f67-114">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="c5f67-114">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="c5f67-115">在左側導覽列中, 按一下 [**網路**設定]。</span><span class="sxs-lookup"><span data-stu-id="c5f67-115">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="c5f67-116">按一下 [**地區] 連結**瀏覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="c5f67-116">Click the **Region Link** navigation button.</span></span>
    
4. <span data-ttu-id="c5f67-117">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="c5f67-117">Click **New**.</span></span>
    
5. <span data-ttu-id="c5f67-118">在 [**新增區域連結**] 頁面上, 按一下 [**名稱**], 然後輸入網路區域連結的名稱。</span><span class="sxs-lookup"><span data-stu-id="c5f67-118">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>
    
6. <span data-ttu-id="c5f67-119">按一下 [**網路區域 #1**], 然後按一下清單中您要連結至 [網路區域] 的網路區域 #2。</span><span class="sxs-lookup"><span data-stu-id="c5f67-119">Click **Network Region #1**, and then click the network region in the list that you want to link to Network Region #2.</span></span>
    
7. <span data-ttu-id="c5f67-120">按一下 [**網路區域 #2**], 然後在清單中按一下您想要連結至 [網路區域] 的網路區域 #1。</span><span class="sxs-lookup"><span data-stu-id="c5f67-120">Click **Network Region #2**, and then click a network region in the list that you want to link to Network Region #1.</span></span>
    
8. <span data-ttu-id="c5f67-121">或者, 按一下 [**頻寬原則**], 然後選取您要套用到 [網路區域] 連結的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="c5f67-121">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c5f67-122">只有在 [網路區域] 連結受到頻寬限制且您想要使用 CAC 來控制該連結上的媒體流量時, 才能套用頻寬原則。</span><span class="sxs-lookup"><span data-stu-id="c5f67-122">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span> 
  
9. <span data-ttu-id="c5f67-123">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c5f67-123">Click **Commit**.</span></span>
    
10. <span data-ttu-id="c5f67-124">若要為您的拓撲建立網路區域連結, 請重複步驟4到 9, 以及其他地區的設定。</span><span class="sxs-lookup"><span data-stu-id="c5f67-124">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c5f67-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c5f67-125">See also</span></span>

[<span data-ttu-id="c5f67-126">新-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="c5f67-126">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="c5f67-127">CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="c5f67-127">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="c5f67-128">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="c5f67-128">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="c5f67-129">移除-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="c5f67-129">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)
