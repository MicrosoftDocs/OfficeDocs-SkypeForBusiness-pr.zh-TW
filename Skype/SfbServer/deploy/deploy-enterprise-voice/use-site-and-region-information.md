---
title: 在商務用 Skype Server 中設定媒體旁路全域設定以使用網站和區域資訊
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
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: 將 [旁路媒體] 設定為僅適用于商務用 Skype Server Enterprise Voice 中的特定網站和區域。
ms.openlocfilehash: 3a9dc907dd516151e8b6ddd509a43b49c87e3b9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193260"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a><span data-ttu-id="6cbcc-103">在商務用 Skype Server 中設定媒體旁路全域設定以使用網站和區域資訊</span><span class="sxs-lookup"><span data-stu-id="6cbcc-103">Configure media bypass global settings in Skype for Business Server to use site and region information</span></span>
 
<span data-ttu-id="6cbcc-104">將 [旁路媒體] 設定為僅適用于商務用 Skype Server Enterprise Voice 中的特定網站和區域。</span><span class="sxs-lookup"><span data-stu-id="6cbcc-104">Configure media bypass to be used for only certain sites and regions in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="6cbcc-105">如果您使用本主題中的步驟來設定媒體旁路的全域設定, 假設您在所有的商務用 Skype 端點和任何對等的用戶端, 都無法在幹線連線上設定媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="6cbcc-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you do not have good connectivity between all Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6cbcc-106">網路區域和網路網站資訊都是在 [呼叫許可控制] 中共用, 當兩個專案都啟用時, 媒體就會繞過高級企業語音功能。</span><span class="sxs-lookup"><span data-stu-id="6cbcc-106">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled.</span></span> <span data-ttu-id="6cbcc-107">因此, 如果您已設定 [通話許可控制], 則不需要您使用下列程式來編輯專門針對媒體旁路的網站和區域資訊。</span><span class="sxs-lookup"><span data-stu-id="6cbcc-107">Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass.</span></span> <span data-ttu-id="6cbcc-108">如果您尚未設定 [通話許可控制] 的網路區域和網站, 且您想要變更媒體旁路設定, 請遵循此程式中的步驟。</span><span class="sxs-lookup"><span data-stu-id="6cbcc-108">Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span> 
  
<span data-ttu-id="6cbcc-109">若要讓 [媒體旁路] 正常運作, 在拓撲建立器中定義的網站與在您設定網路區域和網路網站時所定義的網站, 都必須是一致性。</span><span class="sxs-lookup"><span data-stu-id="6cbcc-109">For media bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="6cbcc-110">例如, 如果您在拓撲建立器中定義了一個已部署 PSTN 閘道的分支網站, 則必須使用企業語音原則來設定分支網站, 讓分支網站使用者能夠透過 PSTN 路由其 PSTN 通話分支網站上的閘道。</span><span class="sxs-lookup"><span data-stu-id="6cbcc-110">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="6cbcc-111">若要設定媒體旁路的網站和區域資訊</span><span class="sxs-lookup"><span data-stu-id="6cbcc-111">To Configure Site and Region Information for Media Bypass</span></span>

1. <span data-ttu-id="6cbcc-112">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="6cbcc-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
2. <span data-ttu-id="6cbcc-113">在左側導覽列中, 按一下 [**網路**設定]。</span><span class="sxs-lookup"><span data-stu-id="6cbcc-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="6cbcc-114">在資料表中按兩下**全域**配置。</span><span class="sxs-lookup"><span data-stu-id="6cbcc-114">Double-click the **Global** configuration in the table.</span></span>
    
4. <span data-ttu-id="6cbcc-115">在 [**編輯全域設定**] 頁面上, 選取 [**啟用旁路媒體**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6cbcc-115">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="6cbcc-116">按一下 [**使用網站和地區**設定]。</span><span class="sxs-lookup"><span data-stu-id="6cbcc-116">Click **Use sites and region configuration**.</span></span>
    
6. <span data-ttu-id="6cbcc-117">如有需要, 請選取 [為**未對應的網站啟用旁路**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6cbcc-117">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6cbcc-118">只有當您有一個或多個大型網站與不含頻寬限制 (例如大型中央網站) 的同一個區域相關聯時, 才選取此核取方塊, 但您還有一些與有頻寬的相同區域相關聯的分支網站限制.</span><span class="sxs-lookup"><span data-stu-id="6cbcc-118">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="6cbcc-119">當您針對未對應的網站啟用 [旁路] 時, 系統會簡化配置, 讓您只指定與分支網站相關聯的子網, 而不需要指定與所有網站相關聯的所有子網。</span><span class="sxs-lookup"><span data-stu-id="6cbcc-119">When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="6cbcc-120">如果已啟用 [通話許可控制], 建議您不要選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6cbcc-120">We recommend that you do not select this check box if call admission control is enabled.</span></span> 
  
7. <span data-ttu-id="6cbcc-121">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6cbcc-121">Click **Commit**.</span></span>
    
<span data-ttu-id="6cbcc-122">接著, 將子網新增至網路網站, 如[將子網與網路網站建立關聯](deploy-network.md#BKMK_AssociateSubnets)中所述。</span><span class="sxs-lookup"><span data-stu-id="6cbcc-122">Next, add subnets to the network site, as described in [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets).</span></span> <span data-ttu-id="6cbcc-123">將所有子網與網路網站建立關聯之後, 就會完成媒體略過部署。</span><span class="sxs-lookup"><span data-stu-id="6cbcc-123">After you associate all subnets with network sites, media bypass deployment is complete.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="6cbcc-124">如果您還沒有建立網路區域和網路網站, 您必須先建立這些區域, 才能繼續進行媒體旁路部署。</span><span class="sxs-lookup"><span data-stu-id="6cbcc-124">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="6cbcc-125">如需詳細資訊, 請參閱[在商務用 Skype 中部署網路區域、網站和子網](deploy-network.md)。</span><span class="sxs-lookup"><span data-stu-id="6cbcc-125">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6cbcc-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6cbcc-126">See also</span></span>

[<span data-ttu-id="6cbcc-127">建立子網路與網路站台的關聯</span><span class="sxs-lookup"><span data-stu-id="6cbcc-127">Associate a subnet with a network site</span></span>](deploy-network.md#BKMK_AssociateSubnets)

