---
title: 在商務用 Skype Server 中設定媒體旁路通用設定，以使用網站與地區資訊
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
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: 設定媒體旁路，只供商務用 Skype Server Enterprise Voice 中的特定網站和區域使用。
ms.openlocfilehash: 58fd4fca90029a8a5f4cd82c6a9616ae66e69cd0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830583"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a><span data-ttu-id="1ed0c-103">在商務用 Skype Server 中設定媒體旁路通用設定，以使用網站與地區資訊</span><span class="sxs-lookup"><span data-stu-id="1ed0c-103">Configure media bypass global settings in Skype for Business Server to use site and region information</span></span>
 
<span data-ttu-id="1ed0c-104">設定媒體旁路，只供商務用 Skype Server Enterprise Voice 中的特定網站和區域使用。</span><span class="sxs-lookup"><span data-stu-id="1ed0c-104">Configure media bypass to be used for only certain sites and regions in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="1ed0c-105">如果您使用本主題中的步驟來設定媒體旁路的全域設定，假設您在所有的商務用 Skype 端點和任何對等的使用者之間，您在主幹連線上設定媒體旁路時，沒有適當的連線能力。</span><span class="sxs-lookup"><span data-stu-id="1ed0c-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you do not have good connectivity between all Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1ed0c-p101">若已啟用通話許可控制與媒體旁路進階 Enterprise Voice 功能，則網路地區和網路網站資訊會由這兩項功能共用。因此，如果您已經設定通話許可控制，則不需要使用下列程序特別針對媒體旁路來編輯網站與地區資訊。如果您尚未設定通話許可控制的網路地區和網站，而想要變更媒體旁路設定，請遵循此程序中的步驟。</span><span class="sxs-lookup"><span data-stu-id="1ed0c-p101">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span> 
  
<span data-ttu-id="1ed0c-109">若要讓媒體旁路正常運作，在拓撲產生器中定義的網站與設定網路地區和網站時所定義的網站之間，必須是一致的一致性。</span><span class="sxs-lookup"><span data-stu-id="1ed0c-109">For media bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="1ed0c-110">例如，如果您已在拓撲產生器中定義的分支網站，只部署了 PSTN 閘道，則該分支網站必須設定企業語音原則，讓分支網站使用者能夠透過分支網站的 PSTN 閘道路由傳送 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="1ed0c-110">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="1ed0c-111">設定媒體旁路的網站與地區資訊</span><span class="sxs-lookup"><span data-stu-id="1ed0c-111">To Configure Site and Region Information for Media Bypass</span></span>

1. <span data-ttu-id="1ed0c-112">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="1ed0c-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
2. <span data-ttu-id="1ed0c-113">在左導覽列中，按一下 **[網路組態]**。</span><span class="sxs-lookup"><span data-stu-id="1ed0c-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="1ed0c-114">連按兩下表格中的 **[全域]** 組態。</span><span class="sxs-lookup"><span data-stu-id="1ed0c-114">Double-click the **Global** configuration in the table.</span></span>
    
4. <span data-ttu-id="1ed0c-115">在 **[編輯通用設定]** 頁面上，選取 **[啟用媒體旁路]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1ed0c-115">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="1ed0c-116">按一下 **[使用網站和地區設定]**。</span><span class="sxs-lookup"><span data-stu-id="1ed0c-116">Click **Use sites and region configuration**.</span></span>
    
6. <span data-ttu-id="1ed0c-117">如有必要，請選取 **[啟用非對應網站的旁路]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1ed0c-117">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1ed0c-p103">如果您有一或多個與相同區域關聯的大型網站沒有頻寬限制 (例如，大型中央網站)，但也有一些與相同區域關聯的分支網站具有頻寬限制，請選取此核取方塊。當您啟用非對應網站的旁路時，設定作業比較精簡，因為您只需指定與分支網站關聯的子網路，而不需指定與所有網站關聯的所有子網路。如果已啟用通話許可控制，則建議您不要選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1ed0c-p103">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span> 
  
7. <span data-ttu-id="1ed0c-121">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="1ed0c-121">Click **Commit**.</span></span>
    
<span data-ttu-id="1ed0c-122">接下來，將子網新增至網站（如 [將子網與網路網站關聯](deploy-network.md#BKMK_AssociateSubnets)）中所述。</span><span class="sxs-lookup"><span data-stu-id="1ed0c-122">Next, add subnets to the network site, as described in [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets).</span></span> <span data-ttu-id="1ed0c-123">將所有子網與網站建立關聯之後，媒體旁路部署即完成。</span><span class="sxs-lookup"><span data-stu-id="1ed0c-123">After you associate all subnets with network sites, media bypass deployment is complete.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="1ed0c-124">如果您尚未建立網路地區和網路網站，您必須先予以建立，才能繼續進行媒體旁路部署。</span><span class="sxs-lookup"><span data-stu-id="1ed0c-124">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="1ed0c-125">如需詳細資訊，請參閱 [在商務用 Skype 中部署網路地區、網站和子網](deploy-network.md)。</span><span class="sxs-lookup"><span data-stu-id="1ed0c-125">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1ed0c-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1ed0c-126">See also</span></span>

[<span data-ttu-id="1ed0c-127">建立子網與網路網站的關聯</span><span class="sxs-lookup"><span data-stu-id="1ed0c-127">Associate a subnet with a network site</span></span>](deploy-network.md#BKMK_AssociateSubnets)

