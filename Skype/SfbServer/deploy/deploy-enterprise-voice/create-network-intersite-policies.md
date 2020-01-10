---
title: 在商務用 Skype Server 中建立網路站間原則
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
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: 建立網路間策略，這些原則是由商務用 Skype Server 中的企業語音通話許可控制所使用。
ms.openlocfilehash: ce1826a1205216791f056a46fa625d26e0362f1f
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001743"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="6afea-103">在商務用 Skype Server 中建立網路站間原則</span><span class="sxs-lookup"><span data-stu-id="6afea-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="6afea-104">建立網路間策略，這些原則是由商務用 Skype Server 中的企業語音通話許可控制所使用。</span><span class="sxs-lookup"><span data-stu-id="6afea-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="6afea-105">網路間原則：定義在它們之間有直接 WAN 連結的網站之間的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="6afea-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6afea-106">*只有*在兩個網路網站之間有直接的交叉連結時，才能使用網路間原則原則。</span><span class="sxs-lookup"><span data-stu-id="6afea-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="6afea-107">在北美的 [北美] 地區，Reno 和 Albuquerque 網站之間有直接連結。</span><span class="sxs-lookup"><span data-stu-id="6afea-107">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="6afea-108">這兩個網站需要一個網站間原則，以套用適當的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="6afea-108">These two sites require an inter-site policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="6afea-109">下列範例會套用20Mb_Link 設定檔。</span><span class="sxs-lookup"><span data-stu-id="6afea-109">The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="6afea-110">建立網路站間原則原則</span><span class="sxs-lookup"><span data-stu-id="6afea-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="6afea-111">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="6afea-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6afea-112">執行新的 CsNetworkInterSitePolicy Cmdlet 來建立網路間原則原則，並針對有直接交叉連結的兩個網站套用適當的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="6afea-112">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="6afea-113">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="6afea-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="6afea-114">如有需要，請重複步驟2，為所有具備直接交叉連結的網路網站組建立網路站間原則。</span><span class="sxs-lookup"><span data-stu-id="6afea-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6afea-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6afea-115">See also</span></span>

[<span data-ttu-id="6afea-116">新-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="6afea-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="6afea-117">CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="6afea-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="6afea-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="6afea-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="6afea-119">移除-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="6afea-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
