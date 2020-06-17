---
title: 驗證舊版環境
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
description: 在共存狀態中部署商務用 Skype Server 2019 之前，您必須確認已設定並啟動舊版服務。 在部署商務用 Skype Server 2019 試驗集區之前，請務必先識別舊環境中存在的重要服務和功能。 在採用舊版 XMPP 部署的共存狀態中部署 Microsoft 商務用 Skype Server 2019 XMPP 之前，您必須確認舊版 XMPP 服務已設定並啟動，並識別舊版 XMPP 設定所支援的同盟合作夥伴。
ms.openlocfilehash: 2600cc2e6f4fac258431bcf505af10d1f8c212fe
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751675"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="13d8e-105">驗證舊版環境</span><span class="sxs-lookup"><span data-stu-id="13d8e-105">Verify the legacy environment</span></span>

<span data-ttu-id="13d8e-106">在共存狀態中部署商務用 Skype Server 2019 之前，您必須確認已設定並啟動舊版服務。</span><span class="sxs-lookup"><span data-stu-id="13d8e-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="13d8e-107">在部署商務用 Skype Server 2019 試驗集區之前，請務必先識別舊環境中存在的重要服務和功能。</span><span class="sxs-lookup"><span data-stu-id="13d8e-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="13d8e-108">在使用舊版 XMPP 部署的共存狀態中部署 Microsoft 商務用 Skype Server 2019 XMPP 之前，您必須確認舊版 XMPP 服務已設定並啟動，並識別舊版的 XMPP 設定所支援的同盟合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="13d8e-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="13d8e-109">驗證舊版部署需要下列各項：</span><span class="sxs-lookup"><span data-stu-id="13d8e-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="13d8e-110">驗證舊版服務是否已啟動</span><span class="sxs-lookup"><span data-stu-id="13d8e-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="13d8e-111">查看拓撲和使用者</span><span class="sxs-lookup"><span data-stu-id="13d8e-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="13d8e-112">驗證同盟及 Edge server 設定</span><span class="sxs-lookup"><span data-stu-id="13d8e-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="13d8e-113">驗證 XMPP 服務和同盟夥伴</span><span class="sxs-lookup"><span data-stu-id="13d8e-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="13d8e-114">確認舊版服務已啟動</span><span class="sxs-lookup"><span data-stu-id="13d8e-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="13d8e-115">在舊版前端伺服器上，流覽至 [管理工具 \ 服務] 小程式。</span><span class="sxs-lookup"><span data-stu-id="13d8e-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="13d8e-116">確認下列服務正在前端伺服器上執行：</span><span class="sxs-lookup"><span data-stu-id="13d8e-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![前端伺服器上執行的服務清單](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="13d8e-118">在商務用 Skype Server 控制台中檢查舊版拓撲</span><span class="sxs-lookup"><span data-stu-id="13d8e-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="13d8e-119">使用 RTCUniversalServerAdmins 群組的成員帳戶、CsAdministrator 成員帳戶或 CsUserAdministrator 系統管理角色的成員帳戶，登入前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="13d8e-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="13d8e-120">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="13d8e-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="13d8e-121">選取 [**拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="13d8e-121">Select **Topology**.</span></span> <span data-ttu-id="13d8e-122">確認舊版部署中的各種伺服器都已列出。</span><span class="sxs-lookup"><span data-stu-id="13d8e-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![控制台拓撲頁面](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="13d8e-124">在商務用 Skype Server 控制台中檢查舊版使用者</span><span class="sxs-lookup"><span data-stu-id="13d8e-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="13d8e-125">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="13d8e-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="13d8e-126">選取 [**使用者**]，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="13d8e-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="13d8e-127">確認 [**註冊集**區] 欄針對所列的每個使用者，指向舊版集區。</span><span class="sxs-lookup"><span data-stu-id="13d8e-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![列出使用者的控制台](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="13d8e-129">驗證舊版 Edge 及同盟設定</span><span class="sxs-lookup"><span data-stu-id="13d8e-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="13d8e-130">啟動拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="13d8e-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="13d8e-131">選取 [**從現有的部署下載拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="13d8e-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="13d8e-132">選擇檔案名，並以預設的 redmond.tbxml 檔案類型儲存拓撲。</span><span class="sxs-lookup"><span data-stu-id="13d8e-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="13d8e-133">展開 [舊版安裝] 節點，以顯示部署中的各種伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="13d8e-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="13d8e-134">選取 [網站] 節點，並確認已設定 [**網站同盟路由指派**] 值。</span><span class="sxs-lookup"><span data-stu-id="13d8e-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![拓撲產生器的網站同盟路由](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="13d8e-136">選取 [Standard Edition Server] 或 [Enterprise Edition 前端集區]。</span><span class="sxs-lookup"><span data-stu-id="13d8e-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="13d8e-137">決定是否已為下列的媒體設定 Edge 集區的**關聯**性。</span><span class="sxs-lookup"><span data-stu-id="13d8e-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![顯示伺服器和集區的拓撲產生器](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="13d8e-139">選取 Edge 集區，並識別下一個躍點集區是否已在**下一個躍點選取範圍**下設定。</span><span class="sxs-lookup"><span data-stu-id="13d8e-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![拓撲產生器，下一個躍點選取範圍](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="13d8e-141">驗證舊版 XMPP 同盟協力廠商設定</span><span class="sxs-lookup"><span data-stu-id="13d8e-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="13d8e-142">在舊版 XMPP 伺服器上，流覽至 [管理工具 \ 服務] 小程式。</span><span class="sxs-lookup"><span data-stu-id="13d8e-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="13d8e-143">確認已啟動 Office 通訊伺服器 XMPP 閘道服務。</span><span class="sxs-lookup"><span data-stu-id="13d8e-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Office 通訊伺服器 XMPP 閘道服務](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

