---
title: 為 Skype 會議廣播設定內部部署
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
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 摘要：瞭解為您的內部部署商務用 Skype Server 混合部署執行的 Skype 會議廣播所需執行的步驟。
ms.openlocfilehash: c016d60b416c7b6d935b15718f3f1a10f439b9ab
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820703"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="3d9d8-103">為 Skype 會議廣播設定內部部署</span><span class="sxs-lookup"><span data-stu-id="3d9d8-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="3d9d8-104">**摘要：** 瞭解為您的內部部署商務用 Skype Server 混合部署執行的 Skype 會議廣播所需執行的步驟。</span><span class="sxs-lookup"><span data-stu-id="3d9d8-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="3d9d8-105">Skype 會議廣播是 Office 365 的一部分線上服務。</span><span class="sxs-lookup"><span data-stu-id="3d9d8-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="3d9d8-106">如果您正在執行商務用 Skype Server 內部部署，且想要在您的環境中使用 Skype 會議廣播，您必須遵循本主題中的設定步驟。</span><span class="sxs-lookup"><span data-stu-id="3d9d8-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="3d9d8-107">開始之前，您的環境必須設定為搭配商務用 Skype Online 的混合環境。</span><span class="sxs-lookup"><span data-stu-id="3d9d8-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="3d9d8-108">如需詳細資訊，請參閱 [規劃商務用 Skype server 與商務用 Skype online 之間的混合式連線性](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) ，以及 [在商務用 Skype server 與商務用 Skype online 之間部署混合式連線](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="3d9d8-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="3d9d8-109">為 Skype 會議廣播設定混合式環境</span><span class="sxs-lookup"><span data-stu-id="3d9d8-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="3d9d8-110">您必須執行下列動作來準備您的環境以進行 Skype 會議廣播：</span><span class="sxs-lookup"><span data-stu-id="3d9d8-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="3d9d8-111">設定與商務用 Skype Online 資源的同盟</span><span class="sxs-lookup"><span data-stu-id="3d9d8-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="3d9d8-112">設定 SIP 同盟網域</span><span class="sxs-lookup"><span data-stu-id="3d9d8-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="3d9d8-113">設定與商務用 Skype Online 資源的同盟</span><span class="sxs-lookup"><span data-stu-id="3d9d8-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="3d9d8-114">若要啟用與商務用 Skype Online 資源的同盟，您必須設定 SIP 同盟提供者的外部存取。</span><span class="sxs-lookup"><span data-stu-id="3d9d8-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="3d9d8-115">若要使用商務用 Skype Server 控制台執行這項作業，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="3d9d8-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="3d9d8-116">啟動商務用 Skype Server 控制台，然後選取左側的 [ **外部存取** ]。</span><span class="sxs-lookup"><span data-stu-id="3d9d8-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="3d9d8-117">選取 [ **SIP 同盟提供者** ]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="3d9d8-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="3d9d8-118">使用下列設定來設定新的提供者：</span><span class="sxs-lookup"><span data-stu-id="3d9d8-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="3d9d8-119">**啟用與此提供者的通訊：**</span><span class="sxs-lookup"><span data-stu-id="3d9d8-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="3d9d8-120">已選取</span><span class="sxs-lookup"><span data-stu-id="3d9d8-120">Selected</span></span>  <br/> |
|<span data-ttu-id="3d9d8-121">**提供者名稱：**</span><span class="sxs-lookup"><span data-stu-id="3d9d8-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="3d9d8-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="3d9d8-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="3d9d8-123">**Access Edge service (FQDN) ：**</span><span class="sxs-lookup"><span data-stu-id="3d9d8-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="3d9d8-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d9d8-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="3d9d8-125">**預設驗證層級：**</span><span class="sxs-lookup"><span data-stu-id="3d9d8-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="3d9d8-126">允許使用者與使用此提供者的所有人進行通訊。</span><span class="sxs-lookup"><span data-stu-id="3d9d8-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="3d9d8-127">您也可以在商務用 skype Server 管理命令介面中執行下列指令程式，以啟用商務用 Skype Online 資源的同盟。</span><span class="sxs-lookup"><span data-stu-id="3d9d8-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="3d9d8-128">設定 SIP 同盟網域</span><span class="sxs-lookup"><span data-stu-id="3d9d8-128">Configure SIP federated domains</span></span>

<span data-ttu-id="3d9d8-129">接下來，您必須將 SIP 同盟網域新增至允許的網域清單。</span><span class="sxs-lookup"><span data-stu-id="3d9d8-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="3d9d8-130">針對所列的每個網域重複這些步驟，以建立4個新的 SIP 同盟網域。</span><span class="sxs-lookup"><span data-stu-id="3d9d8-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="3d9d8-131">這些網域包括在商務用 Skype Online 中所使用的地區性資料中心。</span><span class="sxs-lookup"><span data-stu-id="3d9d8-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="3d9d8-132">啟動商務用 Skype Server 控制台，然後選取左側的 [ **外部存取** ]。</span><span class="sxs-lookup"><span data-stu-id="3d9d8-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="3d9d8-133">選取 [ **SIP 同盟網域** ]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="3d9d8-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="3d9d8-134">針對 [ **功能變數名稱 (] 或 [FQDN) ：**]，輸入網域，針對下列每個網域重複此程式：</span><span class="sxs-lookup"><span data-stu-id="3d9d8-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="3d9d8-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d9d8-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="3d9d8-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d9d8-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="3d9d8-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d9d8-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="3d9d8-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="3d9d8-138">resources.lync.com</span></span>
    
<span data-ttu-id="3d9d8-139">您也可以在商務用 Skype Server 管理命令介面中執行下列 Cmdlet，以設定 SIP 同盟網域的外部存取：</span><span class="sxs-lookup"><span data-stu-id="3d9d8-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="3d9d8-140">完成這些設定步驟之後，您就可以開始在您的部署中使用 Skype 會議廣播。</span><span class="sxs-lookup"><span data-stu-id="3d9d8-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="3d9d8-141">如需有關 Skype 會議廣播的詳細資訊，請參閱 [什麼是 Skype 會議廣播？](https://go.microsoft.com/fwlink/?LinkId=617071) 和 [Skype 會議廣播管理員指南](https://go.microsoft.com/fwlink/?LinkId=617075)。</span><span class="sxs-lookup"><span data-stu-id="3d9d8-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

