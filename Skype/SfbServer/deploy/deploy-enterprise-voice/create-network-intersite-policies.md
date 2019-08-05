---
title: 在商務用 Skype Server 中建立網路站間原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: 建立網路間策略, 這些原則是由商務用 Skype Server 中的企業語音通話許可控制所使用。
ms.openlocfilehash: dceb48d0e87706d71de8c69b5622fbab468273b4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190444"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="3377f-103">在商務用 Skype Server 中建立網路站間原則</span><span class="sxs-lookup"><span data-stu-id="3377f-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="3377f-104">建立網路間策略, 這些原則是由商務用 Skype Server 中的企業語音通話許可控制所使用。</span><span class="sxs-lookup"><span data-stu-id="3377f-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="3377f-105">網路間原則: 定義在它們之間有直接 WAN 連結的網站之間的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="3377f-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3377f-106">*只有*在兩個網路網站之間有直接的交叉連結時, 才能使用網路間原則原則。</span><span class="sxs-lookup"><span data-stu-id="3377f-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="3377f-107">在北美的 [北美] 地區, Reno 和 Albuquerque 網站之間有直接連結。</span><span class="sxs-lookup"><span data-stu-id="3377f-107">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="3377f-108">這兩個網站需要一個網站間原則, 以套用適當的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="3377f-108">These two sites require an inter-site policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="3377f-109">下列範例會套用20Mb_Link 設定檔。</span><span class="sxs-lookup"><span data-stu-id="3377f-109">The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="3377f-110">建立網路站間原則原則</span><span class="sxs-lookup"><span data-stu-id="3377f-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="3377f-111">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="3377f-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="3377f-112">執行新的 CsNetworkInterSitePolicy Cmdlet 來建立網路間原則原則, 並針對有直接交叉連結的兩個網站套用適當的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="3377f-112">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="3377f-113">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="3377f-113">For example, run:</span></span>
    
   ```
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="3377f-114">如有需要, 請重複步驟 2, 為所有具備直接交叉連結的網路網站組建立網路站間原則。</span><span class="sxs-lookup"><span data-stu-id="3377f-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3377f-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3377f-115">See also</span></span>

[<span data-ttu-id="3377f-116">新-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="3377f-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="3377f-117">CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="3377f-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="3377f-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="3377f-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="3377f-119">移除-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="3377f-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
