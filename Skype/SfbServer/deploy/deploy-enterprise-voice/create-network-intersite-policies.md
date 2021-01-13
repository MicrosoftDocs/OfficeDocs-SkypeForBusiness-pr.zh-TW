---
title: 在商務用 Skype Server 中建立網路網站間原則
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
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: 建立網路間原則，以供商務用 Skype Server 中的企業語音通話許可控制使用。
ms.openlocfilehash: 69609da75fdfa87309743920eace59892a440f2b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822473"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="33b44-103">在商務用 Skype Server 中建立網路網站間原則</span><span class="sxs-lookup"><span data-stu-id="33b44-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="33b44-104">建立網路間原則，以供商務用 Skype Server 中的企業語音通話許可控制使用。</span><span class="sxs-lookup"><span data-stu-id="33b44-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="33b44-105">網路之間的網站間原則定義的頻寬限制是具有彼此的直接 WAN 連結的網站。</span><span class="sxs-lookup"><span data-stu-id="33b44-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="33b44-106">只有在兩個網站之間有直接的交叉連結時，  *才*  需要網路間原則。</span><span class="sxs-lookup"><span data-stu-id="33b44-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="33b44-107">在「北美地區」範例中，雷諾與阿布奎基網站之間有直接連結。</span><span class="sxs-lookup"><span data-stu-id="33b44-107">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="33b44-108">這兩個網站需要套用適當頻寬原則設定檔的網站間原則。</span><span class="sxs-lookup"><span data-stu-id="33b44-108">These two sites require an inter-site policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="33b44-109">下列範例會套用20Mb_Link 設定檔。</span><span class="sxs-lookup"><span data-stu-id="33b44-109">The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="33b44-110">建立網路間網站原則</span><span class="sxs-lookup"><span data-stu-id="33b44-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="33b44-111">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="33b44-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="33b44-112">執行 New-CsNetworkInterSitePolicy Cmdlet 來建立網路間原則，並為具有直接交叉連結的兩個網站套用適當的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="33b44-112">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="33b44-113">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="33b44-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="33b44-114">如有需要，請重複步驟2，為所有具有直接交叉連結的網站對建立網路間原則。</span><span class="sxs-lookup"><span data-stu-id="33b44-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="33b44-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="33b44-115">See also</span></span>

[<span data-ttu-id="33b44-116">新 CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="33b44-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="33b44-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="33b44-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="33b44-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="33b44-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="33b44-119">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="33b44-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
