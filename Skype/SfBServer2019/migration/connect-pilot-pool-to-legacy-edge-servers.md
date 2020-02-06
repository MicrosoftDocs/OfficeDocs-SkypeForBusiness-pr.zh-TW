---
title: 將試驗集區連線到舊版 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 部署商務用 Skype Server 2019 之後，您必須為您的網站設定同盟路由。 若要使用舊版安裝所使用的同盟路由，商務用 Skype Server 2019 必須設定為使用這個路線。
ms.openlocfilehash: 6cc49da3cb27679ef295c7bbeca122aea5a89d10
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813701"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="98f2d-104">將試驗集區連線到舊版 Edge Server</span><span class="sxs-lookup"><span data-stu-id="98f2d-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="98f2d-105">部署商務用 Skype Server 2019 之後，您必須為您的網站設定同盟路由。</span><span class="sxs-lookup"><span data-stu-id="98f2d-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="98f2d-106">若要使用舊版安裝所使用的同盟路由，商務用 Skype Server 2019 必須設定為使用這個路線。</span><span class="sxs-lookup"><span data-stu-id="98f2d-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="98f2d-107">若要讓商務用 Skype Server 2019 網站使用舊版部署的控制器與邊緣伺服器，請使用拓撲建立器建立舊版邊緣池的關聯。</span><span class="sxs-lookup"><span data-stu-id="98f2d-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="98f2d-108">使用拓撲建立器關聯舊版 Edge 池</span><span class="sxs-lookup"><span data-stu-id="98f2d-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="98f2d-109">開啟拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="98f2d-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="98f2d-110">選取您的網站，這會直接位於**商務用 Skype Server**節點的正下方。</span><span class="sxs-lookup"><span data-stu-id="98f2d-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="98f2d-111">在 [**動作**] 功能表上，按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="98f2d-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="98f2d-112">在左窗格中，選取 [**同盟路由**]。</span><span class="sxs-lookup"><span data-stu-id="98f2d-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="98f2d-113">在 [**網站同盟路由指派**] 底下，選取 [**啟用 SIP 同盟**]，然後選取舊版控制器或舊版 Edge 伺服器（如果沒有列出任何導演）。</span><span class="sxs-lookup"><span data-stu-id="98f2d-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="98f2d-114">按一下 **[確定]** 以關閉 [**編輯屬性**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="98f2d-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="98f2d-115">在拓撲建立器中，在商務用 Skype Server 2019 節點底下，流覽至**標準版 server**或**Enterprise edition 前端池**，以滑鼠右鍵按一下該池，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="98f2d-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="98f2d-116">在 [**關聯**性] 底下，選取 [關聯邊緣池] 旁的核取方塊 **（適用于媒體元件）**。</span><span class="sxs-lookup"><span data-stu-id="98f2d-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="98f2d-117">從清單中選取舊版邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="98f2d-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="98f2d-118">按一下 **[確定]** 以關閉 [**編輯屬性**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="98f2d-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="98f2d-119">在 [**拓撲**建立器] 中，選取最上方的節點，即**商務用 Skype 伺服器**。</span><span class="sxs-lookup"><span data-stu-id="98f2d-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="98f2d-120">在 [**動作**] 功能表中，按一下 [**發佈拓撲**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="98f2d-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="98f2d-121">**發佈嚮導**完成後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="98f2d-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

