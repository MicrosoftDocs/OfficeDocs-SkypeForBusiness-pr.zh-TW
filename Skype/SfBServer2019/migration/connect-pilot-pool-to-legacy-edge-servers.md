---
title: 將試驗集區連線到舊版 Edge Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在部署商務用 Skype Server 2019 之後，您必須為您的網站設定同盟路由。 為了使用舊版安裝所使用的同盟路由，商務用 Skype Server 2019 必須設定成使用此路由。
ms.openlocfilehash: 8243ebbf9540587dedd8e4ae3a51e22f9a315728
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753923"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="bbc27-104">將試驗集區連線到舊版 Edge Server</span><span class="sxs-lookup"><span data-stu-id="bbc27-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="bbc27-105">在部署商務用 Skype Server 2019 之後，您必須為您的網站設定同盟路由。</span><span class="sxs-lookup"><span data-stu-id="bbc27-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="bbc27-106">為了使用舊版安裝所使用的同盟路由，商務用 Skype Server 2019 必須設定成使用此路由。</span><span class="sxs-lookup"><span data-stu-id="bbc27-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="bbc27-107">若要讓商務用 Skype Server 2019 網站使用舊版部署的 Director 和 Edge Server，請使用拓撲產生器建立與舊版 Edge 集區的關聯。</span><span class="sxs-lookup"><span data-stu-id="bbc27-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="bbc27-108">使用拓撲產生器來與舊版 Edge 集區建立關聯</span><span class="sxs-lookup"><span data-stu-id="bbc27-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="bbc27-109">開啟拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="bbc27-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="bbc27-110">選取您的網站，它會直接位於**商務用 Skype Server**節點底下。</span><span class="sxs-lookup"><span data-stu-id="bbc27-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="bbc27-111">在 [動作]\*\*\*\* 功能表上，按一下 [編輯屬性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bbc27-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="bbc27-112">在左窗格中，選取 [**同盟路由**]。</span><span class="sxs-lookup"><span data-stu-id="bbc27-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="bbc27-113">在 [**網站同盟路由指派**] 底下，選取 [**啟用 SIP 同盟**]，然後選取舊版 Director 或舊版 Edge Server （如果未列出 Director）。</span><span class="sxs-lookup"><span data-stu-id="bbc27-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="bbc27-114">按一下 [確定]\*\*\*\* 關閉 [編輯內容]\*\*\*\* 頁面。</span><span class="sxs-lookup"><span data-stu-id="bbc27-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="bbc27-115">在 [拓撲產生器] 的 [商務用 Skype 伺服器 2019] 節點下，流覽至 [ **Standard edition server** ] 或 [ **Enterprise Edition 前端**集區]，以滑鼠右鍵按一下集區，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="bbc27-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="bbc27-116">在 [關聯]\*\*\*\* 底下，選取 [關聯 Edge 集區 (適用於媒體元件)]\*\*\*\* 旁邊的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bbc27-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="bbc27-117">從清單中，選取舊版 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="bbc27-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="bbc27-118">按一下 [確定]\*\*\*\* 關閉 [編輯內容]\*\*\*\* 頁面。</span><span class="sxs-lookup"><span data-stu-id="bbc27-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="bbc27-119">在 [**拓撲**產生器] 中，選取最頂端的節點（**商務用 Skype 伺服器**）。</span><span class="sxs-lookup"><span data-stu-id="bbc27-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="bbc27-120">從 [**動作**] 功能表中，按一下 [**發行拓撲**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bbc27-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="bbc27-121">當 [發行精靈]\*\*\*\* 完成之後，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bbc27-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

