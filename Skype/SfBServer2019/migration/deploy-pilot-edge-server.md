---
title: 部署試點邊緣伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本主題重點說明在部署商務用 Skype Server 2019 Edge 伺服器之前, 您應該知道的配置設定。 商務用 skype Server 2019 的部署和設定處理常式與商務用 Skype Server 2015 非常類似。 此區段只會醒目提示您要考慮的重要重點, 做為您的試驗池部署的一部分。 如需詳細步驟, 請參閱部署檔中的商務用 Skype Server 2019 部署外部使用者存取 (描述部署程式), 同時提供外部使用者存取的設定資訊。
ms.openlocfilehash: f692eb5ad4a24b47a8bab7a56be218eab04af7dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189094"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="5b9d2-106">部署試點邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="5b9d2-106">Deploy pilot Edge Server</span></span>

<span data-ttu-id="5b9d2-107">本主題重點說明在部署商務用 Skype Server 2019 Edge 伺服器之前, 您應該注意的配置設定。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-107">This topic highlights configuration settings you should be aware of before deploying your Skype for Business Server 2019 Edge Server.</span></span> <span data-ttu-id="5b9d2-108">商務用 skype Server 2019 的部署和設定處理常式與商務用 Skype Server 2015 非常類似。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-108">The deployment and configuration processes for Skype for Business Server 2019 are very similar to Skype for Business Server 2015.</span></span> <span data-ttu-id="5b9d2-109">此區段只會醒目提示您要考慮的重要重點, 做為您的試驗池部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-109">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
<span data-ttu-id="5b9d2-110">當您流覽 [**定義新的邊緣池**] 嚮導時, 請參閱下列步驟中所示的 [金鑰設定] 設定。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-110">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="5b9d2-111">請注意, 只有幾頁會顯示 [**定義新的邊緣池**] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-111">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span> 
  
### <a name="to-define-an-edge-pool"></a><span data-ttu-id="5b9d2-112">定義邊緣池</span><span class="sxs-lookup"><span data-stu-id="5b9d2-112">To define an Edge Pool</span></span>

1. <span data-ttu-id="5b9d2-113">登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-113">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="5b9d2-114">流覽至商務用 Skype Server 2019 節點。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-114">Navigate to the Skype for Business Server 2019 node.</span></span> <span data-ttu-id="5b9d2-115">以滑鼠右鍵按一下 [**邊緣池**], 然後按一下 [**新增邊緣池**]。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-115">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
     ![[定義新的 Edge 集區] 對話方塊](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. <span data-ttu-id="5b9d2-117">Edge 池可以是**多個電腦池**或**單一電腦池**。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-117">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
     ![[定義 Edge 集區 FQDN] 對話方塊](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. <span data-ttu-id="5b9d2-119">在 [**選取功能**] 頁面上, 不要啟用同盟或 XMPP 同盟。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-119">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="5b9d2-120">同盟與 XMPP 同盟目前是透過舊版 Edge 伺服器路由。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-120">Federation and XMPP federation are both currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="5b9d2-121">這些功能將會在稍後的遷移階段進行設定。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-121">These features will be configured in a later phase of migration.</span></span> 

  
5. <span data-ttu-id="5b9d2-122">繼續完成下列嚮導頁面:**外部 fqdn**、**定義內部 ip 位址**, 以及**定義外部 ip 位址**。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-122">Continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>
    
6. <span data-ttu-id="5b9d2-123">在 [**定義下一個躍點伺服器]** 頁面上, 選取舊版 Edge 池下一個躍點的主管。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-123">On the **Define the next hop server** page, select the Director for the next hop of the legacy Edge pool.</span></span> 
    
     ![[定義下一個躍點] 對話方塊](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. <span data-ttu-id="5b9d2-125">在 [**關聯前端或轉送池**] 頁面上, 請勿在此時將池與此 Edge 池建立關聯。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="5b9d2-126">外部媒體流量目前是透過舊版 Edge 伺服器路由。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-126">External media traffic is currently routed through the legacy Edge Server.</span></span> <span data-ttu-id="5b9d2-127">此設定將會在稍後的遷移階段進行設定。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-127">This setting will be configured in a later phase of migration.</span></span> 
    
     ![[建立前端集區的關聯] 對話方塊](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. <span data-ttu-id="5b9d2-129">按一下 **[完成]**, 然後**發佈**拓撲。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-129">Click **Finish**, and then **Publish** the topology.</span></span> 
    
9. <span data-ttu-id="5b9d2-130">依照部署檔中的步驟, 在新的 Edge 伺服器上安裝檔案、設定憑證, 然後啟動服務。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-130">Follow the steps in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span> 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
<span data-ttu-id="5b9d2-131">請務必遵循部署檔中主題中的指導方針。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-131">It's very important that you follow the guidelines in the topics in the Deployment documentation.</span></span> <span data-ttu-id="5b9d2-132">本節僅提供安裝這些伺服器角色時設定設定的一些指導方針。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span> 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
<span data-ttu-id="5b9d2-133">您現在應該會與商務用 Skype Server 2019 Edge 伺服器部署並行部署舊版 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-133">You should now have a legacy Edge Server deployed in parallel with a Skype for Business Server 2019 Edge server deployment.</span></span> <span data-ttu-id="5b9d2-134">確認這兩個部署都能正常運作、服務已啟動, 而且您可以在移至下一個階段之前管理每個部署。</span><span class="sxs-lookup"><span data-stu-id="5b9d2-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span> 
  

