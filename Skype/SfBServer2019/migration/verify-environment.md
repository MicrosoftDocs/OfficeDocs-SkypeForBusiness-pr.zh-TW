---
title: 驗證舊版環境
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在共存狀態中部署商務用 Skype Server 2019 之前, 您必須確認已設定並啟動舊版服務。 在部署商務用 Skype Server 2019 試驗池之前, 請務必先找出舊版環境中存在的重要服務和功能。 在部署 Microsoft 商務用 Skype Server 2019 XMPP 的共存狀態與舊版 XMPP 部署之前, 您必須確認已設定並啟動舊版 XMPP 服務, 並找出舊版 XMPP 設定是由哪些聯盟夥伴提供作用.
ms.openlocfilehash: 9495c68085f3fc3495d4c2ced05be8b20039eb4e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189061"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="2b950-105">驗證舊版環境</span><span class="sxs-lookup"><span data-stu-id="2b950-105">Verify the legacy environment</span></span>

<span data-ttu-id="2b950-106">在共存狀態中部署商務用 Skype Server 2019 之前, 您必須確認已設定並啟動舊版服務。</span><span class="sxs-lookup"><span data-stu-id="2b950-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="2b950-107">在部署商務用 Skype Server 2019 試驗池之前, 請務必先找出舊版環境中存在的主要服務和功能。</span><span class="sxs-lookup"><span data-stu-id="2b950-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="2b950-108">在部署 Microsoft 商務用 Skype Server 2019 XMPP 的共存狀態與舊版 XMPP 部署之前, 您必須確認已設定並啟動舊版 XMPP 服務, 並找出舊版 XMPP 的聯盟夥伴配置支援。</span><span class="sxs-lookup"><span data-stu-id="2b950-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="2b950-109">驗證舊版部署需要進行下列作業:</span><span class="sxs-lookup"><span data-stu-id="2b950-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="2b950-110">確認舊版服務已啟動</span><span class="sxs-lookup"><span data-stu-id="2b950-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="2b950-111">查看拓撲和使用者</span><span class="sxs-lookup"><span data-stu-id="2b950-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="2b950-112">驗證同盟和 Edge 伺服器設定</span><span class="sxs-lookup"><span data-stu-id="2b950-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="2b950-113">驗證 XMPP 服務和聯盟夥伴</span><span class="sxs-lookup"><span data-stu-id="2b950-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="2b950-114">確認舊版服務已啟動</span><span class="sxs-lookup"><span data-stu-id="2b950-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="2b950-115">從舊版前端伺服器流覽至 [管理 Tools\Services] 小程式。</span><span class="sxs-lookup"><span data-stu-id="2b950-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="2b950-116">確認下列服務正在前端伺服器上執行:</span><span class="sxs-lookup"><span data-stu-id="2b950-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![在前端伺服器上執行的服務清單](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="2b950-118">在商務用 Skype Server [控制台] 中查看舊版拓撲</span><span class="sxs-lookup"><span data-stu-id="2b950-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="2b950-119">使用 RTCUniversalServerAdmins 群組成員的帳戶或 CsAdministrator 或 CsUserAdministrator 系統管理角色的成員登入前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="2b950-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="2b950-120">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="2b950-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="2b950-121">選取 [**拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="2b950-121">Select **Topology**.</span></span> <span data-ttu-id="2b950-122">確認舊版部署中的各種伺服器都已列出。</span><span class="sxs-lookup"><span data-stu-id="2b950-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![[控制台拓撲] 頁面](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="2b950-124">在商務用 Skype Server [控制台] 中查看舊版使用者</span><span class="sxs-lookup"><span data-stu-id="2b950-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="2b950-125">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="2b950-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="2b950-126">選取 [**使用者**], 然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="2b950-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="2b950-127">確認 [**註冊機構池**] 欄會針對所列的每位使用者, 指向舊版資源區。</span><span class="sxs-lookup"><span data-stu-id="2b950-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![[控制台] 列出使用者](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="2b950-129">驗證舊版邊緣與同盟設定</span><span class="sxs-lookup"><span data-stu-id="2b950-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="2b950-130">啟動拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="2b950-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="2b950-131">選取 [**從現有的部署下載拓撲**。</span><span class="sxs-lookup"><span data-stu-id="2b950-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="2b950-132">選擇檔案名, 然後使用預設的 tbxml 檔案類型來儲存拓撲。</span><span class="sxs-lookup"><span data-stu-id="2b950-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="2b950-133">展開舊版 [安裝] 節點, 以顯示部署中的各種伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="2b950-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="2b950-134">選取 [網站] 節點, 然後確認已設定 [**網站同盟路由指派**] 值。</span><span class="sxs-lookup"><span data-stu-id="2b950-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![拓撲產生器，網站同盟路由](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="2b950-136">選取 [標準版伺服器] 或 [企業版頂層端] 池。</span><span class="sxs-lookup"><span data-stu-id="2b950-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="2b950-137">判斷是否已針對低於 [**關聯**性] 的媒體設定 Edge 池。</span><span class="sxs-lookup"><span data-stu-id="2b950-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![顯示伺服器與集區的拓撲產生器](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="2b950-139">選取 [邊緣] 池, 並識別下一個躍點池是否已設定在**下一個躍點選取範圍**下方。</span><span class="sxs-lookup"><span data-stu-id="2b950-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![拓撲產生器，下一個躍點選取範圍](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="2b950-141">驗證舊版 XMPP 聯盟合作夥伴設定</span><span class="sxs-lookup"><span data-stu-id="2b950-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="2b950-142">從舊版 XMPP 伺服器流覽至 [管理 Tools\Services] 小程式。</span><span class="sxs-lookup"><span data-stu-id="2b950-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="2b950-143">確認已啟動 Office 通訊伺服器 XMPP 閘道服務。</span><span class="sxs-lookup"><span data-stu-id="2b950-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Office Communications Server XMPP 閘道服務](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

