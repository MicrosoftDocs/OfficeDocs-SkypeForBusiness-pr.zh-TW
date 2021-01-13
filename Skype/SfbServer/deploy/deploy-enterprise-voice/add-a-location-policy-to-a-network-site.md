---
title: 在商務用 Skype Server 中將位置原則新增至網路網站
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: 在商務用 Skype Server Enterprise Voice 中，將 E9-1-1 位置原則指派給網路網站。
ms.openlocfilehash: 887c2fcab63acd5d143ba80f6be6976e8fe2b39f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804273"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a><span data-ttu-id="c4087-103">在商務用 Skype Server 中將位置原則新增至網路網站</span><span class="sxs-lookup"><span data-stu-id="c4087-103">Add a location policy to a network site in Skype for Business Server</span></span>
 
<span data-ttu-id="c4087-104">在商務用 Skype Server Enterprise Voice 中，將 E9-1-1 位置原則指派給網路網站。</span><span class="sxs-lookup"><span data-stu-id="c4087-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="c4087-105">下列範例顯示如何將在「[商務用 Skype 伺服器」中建立位置](create-location-policies.md)原則中定義的 **Redmond** 位置原則新增至現有的網路網站，以及如何建立使用 **Redmond** 位置原則的新網路網站。</span><span class="sxs-lookup"><span data-stu-id="c4087-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="c4087-106">如需使用網路網站的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c4087-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="c4087-107">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="c4087-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="c4087-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="c4087-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="c4087-109">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="c4087-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="c4087-110">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="c4087-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="c4087-111">若要指派位置原則給現有網路網站</span><span class="sxs-lookup"><span data-stu-id="c4087-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="c4087-112">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="c4087-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c4087-113">執行下列 Cmdlet 來修改現有的網路網站。</span><span class="sxs-lookup"><span data-stu-id="c4087-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="c4087-114">將 **雷德蒙** 標位置原則指派給名為 **redmond** 的現有網路網站。</span><span class="sxs-lookup"><span data-stu-id="c4087-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="c4087-115">若要指派位置原則給新的網路網站</span><span class="sxs-lookup"><span data-stu-id="c4087-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="c4087-116">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="c4087-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c4087-117">執行下列 Cmdlet 來建立新的網路網站。</span><span class="sxs-lookup"><span data-stu-id="c4087-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="c4087-118">在網路地區中建立新的網路網站，並指派具有 **Redmond** 標記的位置原則。</span><span class="sxs-lookup"><span data-stu-id="c4087-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


