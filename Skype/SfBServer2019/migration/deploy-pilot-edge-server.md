---
title: 部署試驗 Edge Server
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
description: 本主題著重于部署商務用 Skype Server 2019 Edge Server 之前，請先注意您應注意的配置設定。 商務用 Skype Server 2019 的部署和設定流程非常類似于商務用 Skype Server 2015。 本節只著重在部署試驗集區時應該考量的要點。 如需詳細步驟，請參閱部署檔中的部署商務用 Skype Server 2019 中的外部使用者存取，它會說明部署程式，也會提供外部使用者存取的設定資訊。
ms.openlocfilehash: 00c371b917f2649dba9011fbbce6162b153822d1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752865"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="962d9-106">部署試驗 Edge Server</span><span class="sxs-lookup"><span data-stu-id="962d9-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="962d9-107">本主題著重于部署商務用 Skype Server 2019 Edge Server 之前，請先注意您應注意的配置設定。</span><span class="sxs-lookup"><span data-stu-id="962d9-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="962d9-108">商務用 Skype Server 2019 的部署和設定流程非常類似于商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="962d9-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="962d9-109">本節只著重在部署試驗集區時應該考量的要點。</span><span class="sxs-lookup"><span data-stu-id="962d9-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="962d9-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span><span class="sxs-lookup"><span data-stu-id="962d9-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="962d9-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span><span class="sxs-lookup"><span data-stu-id="962d9-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="962d9-112">定義 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="962d9-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="962d9-113">以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。</span><span class="sxs-lookup"><span data-stu-id="962d9-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="962d9-114">流覽至商務用 Skype Server 2019 節點。</span><span class="sxs-lookup"><span data-stu-id="962d9-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="962d9-115">用滑鼠右鍵按一下 [Edge 集區]\*\*\*\*，然後按一下 [新增 Edge 集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="962d9-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![[定義新的 Edge 集區] 對話方塊](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="962d9-117">Edge 集區可以是 [多部電腦集區]\*\*\*\* 或 [單一電腦集區]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="962d9-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![[定義 Edge 集區 FQDN] 對話方塊](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="962d9-119">在「選取功能」\*\*\*\* 頁面上，請勿啟用同盟或 XMPP 同盟。</span><span class="sxs-lookup"><span data-stu-id="962d9-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="962d9-120">同盟和 XMPP 同盟目前是透過舊版 Edge Server 路由傳送。</span><span class="sxs-lookup"><span data-stu-id="962d9-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="962d9-121">在移轉的後期階段，將會設定這些功能。</span><span class="sxs-lookup"><span data-stu-id="962d9-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="962d9-122">繼續完成下列嚮導頁面：**外部 fqdn**、**定義內部 ip 位址**，以及**定義外部 ip 位址**。</span><span class="sxs-lookup"><span data-stu-id="962d9-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="962d9-123">在 [**定義下一個躍點伺服器**] 頁面上，選取舊版 Edge 集區的下一個躍點 Director。</span><span class="sxs-lookup"><span data-stu-id="962d9-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![[定義下一個躍點] 對話方塊](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="962d9-125">在 [**建立前端或**中繼集區] 頁面上，請勿在此時間建立集區與此 Edge 集區的關聯。</span><span class="sxs-lookup"><span data-stu-id="962d9-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="962d9-126">外部媒體流量目前是透過舊版 Edge Server 路由傳送。</span><span class="sxs-lookup"><span data-stu-id="962d9-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="962d9-127">這項設定到了移轉的後期階段還會再調整。</span><span class="sxs-lookup"><span data-stu-id="962d9-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![[建立前端集區的關聯] 對話方塊](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="962d9-129">按一下 **[完成]**，然後**發行**拓撲。</span><span class="sxs-lookup"><span data-stu-id="962d9-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="962d9-130">遵循部署檔中的步驟，在新 Edge Server 上安裝檔案、設定憑證，然後啟動服務。</span><span class="sxs-lookup"><span data-stu-id="962d9-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="962d9-131">請務必遵循部署檔中主題的指導方針。</span><span class="sxs-lookup"><span data-stu-id="962d9-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="962d9-132">本節只提供安裝這些伺服器角色時，部分組態設定的指示。</span><span class="sxs-lookup"><span data-stu-id="962d9-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="962d9-133">現在，您應該會同時部署舊版 Edge Server 與商務用 Skype Server 2019 Edge server 部署。</span><span class="sxs-lookup"><span data-stu-id="962d9-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="962d9-134">確認部署雙方皆可正常運作、服務已啟用，且您也能管理每個部署，接著，就可以前往下一個階段。</span><span class="sxs-lookup"><span data-stu-id="962d9-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

