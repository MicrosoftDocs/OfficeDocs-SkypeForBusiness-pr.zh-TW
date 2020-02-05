---
title: 在商務用 Skype Server 中新增位置原則至網路網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: 在商務用 Skype Server Enterprise Voice 中，為網路網站指派 E9-1-1 位置原則。
ms.openlocfilehash: ef6395b2239256abce82612b4863a667ce3b27ab
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768276"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a><span data-ttu-id="4d52c-103">在商務用 Skype Server 中新增位置原則至網路網站</span><span class="sxs-lookup"><span data-stu-id="4d52c-103">Add a location policy to a network site in Skype for Business Server</span></span>
 
<span data-ttu-id="4d52c-104">在商務用 Skype Server Enterprise Voice 中，為網路網站指派 E9-1-1 位置原則。</span><span class="sxs-lookup"><span data-stu-id="4d52c-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="4d52c-105">下列範例示範如何將在 [商務用 Skype 伺服器] 的 [[建立位置原則](create-location-policies.md)] 中定義的**雷蒙德**位置原則新增到現有的網路網站，以及如何建立使用**雷蒙德**位置原則的新網路網站。</span><span class="sxs-lookup"><span data-stu-id="4d52c-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="4d52c-106">如需使用網路網站的詳細資訊，請參閱適用于下列 Cmdlet 的 Lync Server 管理命令介面檔：</span><span class="sxs-lookup"><span data-stu-id="4d52c-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="4d52c-107">**新-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="4d52c-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="4d52c-108">**CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="4d52c-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="4d52c-109">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="4d52c-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="4d52c-110">**移除-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="4d52c-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="4d52c-111">將位置原則指派給現有的網路網站</span><span class="sxs-lookup"><span data-stu-id="4d52c-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="4d52c-112">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="4d52c-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4d52c-113">執行下列 Cmdlet 來修改現有的網路網站。</span><span class="sxs-lookup"><span data-stu-id="4d52c-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="4d52c-114">將**雷德蒙**標記的位置原則指派給名為 [**雷蒙德**] 的現有網路網站。</span><span class="sxs-lookup"><span data-stu-id="4d52c-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="4d52c-115">將位置原則指派給新的網路網站</span><span class="sxs-lookup"><span data-stu-id="4d52c-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="4d52c-116">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="4d52c-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4d52c-117">執行下列 Cmdlet 以建立新的網路網站。</span><span class="sxs-lookup"><span data-stu-id="4d52c-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="4d52c-118">在網路區域中建立新的網路網站，並指派**雷德蒙**標記的位置原則。</span><span class="sxs-lookup"><span data-stu-id="4d52c-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


