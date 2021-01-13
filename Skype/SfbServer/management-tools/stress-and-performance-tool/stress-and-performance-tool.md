---
title: 商務用 Skype Server 2015 應力和效能工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: 在非實際執行或測試環境中進行容量規劃和效能調整時，會使用商務用 Skype Server 2015 的壓力和效能工具。
ms.openlocfilehash: 551e4e5f985fc18439a4f277685034e86c7cdfb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814923"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="86ec5-103">商務用 Skype Server 2015 應力和效能工具</span><span class="sxs-lookup"><span data-stu-id="86ec5-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="86ec5-104">在非實際執行或測試環境中進行容量規劃和效能調整時，會使用商務用 Skype Server 2015 的壓力和效能工具。</span><span class="sxs-lookup"><span data-stu-id="86ec5-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="86ec5-105">商務用 Skype Server 2015 應力和效能工具組含的工具可以簡化您的商務用 Skype Server 2015 的容量規劃。</span><span class="sxs-lookup"><span data-stu-id="86ec5-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="86ec5-106">商務用 Skype Server 2015 應力和效能工具可協助您：</span><span class="sxs-lookup"><span data-stu-id="86ec5-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="86ec5-107">簡化商務用 Skype 伺服器的硬體規劃</span><span class="sxs-lookup"><span data-stu-id="86ec5-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="86ec5-108">提供更多有關效能調整的知識和最佳作法</span><span class="sxs-lookup"><span data-stu-id="86ec5-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="86ec5-109">度量商務用 Skype 伺服器部署的效能</span><span class="sxs-lookup"><span data-stu-id="86ec5-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="86ec5-110">您通常會在您使用 [商務用 Skype server 2015 規劃工具](../../management-tools/planning-tool/planning-tool.md) 來設計拓撲，並使用 [商務用 Skype Server 2015 容量規劃計算機](../../management-tools/capacity-planning-calculator.md)來精煉拓撲之後，使用此工具。</span><span class="sxs-lookup"><span data-stu-id="86ec5-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="86ec5-111">不會更新商務用 Skype Server 2019 的工具。</span><span class="sxs-lookup"><span data-stu-id="86ec5-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="86ec5-112">測試</span><span class="sxs-lookup"><span data-stu-id="86ec5-112">Tests</span></span>

<span data-ttu-id="86ec5-113">壓力和效能工具可以模擬下列類型的使用者負載：</span><span class="sxs-lookup"><span data-stu-id="86ec5-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="86ec5-114">立即訊息 (IM) 和目前狀態</span><span class="sxs-lookup"><span data-stu-id="86ec5-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="86ec5-115">音訊會議</span><span class="sxs-lookup"><span data-stu-id="86ec5-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="86ec5-116">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="86ec5-116">Application sharing</span></span>  <br/> |<span data-ttu-id="86ec5-117">Voice over IP (VoIP) ，包括公用交換電話網路 (PTSN) 模擬</span><span class="sxs-lookup"><span data-stu-id="86ec5-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="86ec5-118">Web Access 用戶端會議</span><span class="sxs-lookup"><span data-stu-id="86ec5-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="86ec5-119">會議自動語音應答</span><span class="sxs-lookup"><span data-stu-id="86ec5-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="86ec5-120">回應群組</span><span class="sxs-lookup"><span data-stu-id="86ec5-120">Response Groups</span></span>  <br/> |<span data-ttu-id="86ec5-121">通訊群組清單延伸</span><span class="sxs-lookup"><span data-stu-id="86ec5-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="86ec5-122">通訊錄下載和通訊錄查詢</span><span class="sxs-lookup"><span data-stu-id="86ec5-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="86ec5-123">增強型 911 (E911) 通話和位置設定檔 (撥號對應表) </span><span class="sxs-lookup"><span data-stu-id="86ec5-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="86ec5-124">重視</span><span class="sxs-lookup"><span data-stu-id="86ec5-124">MultiView</span></span>  <br/> |<span data-ttu-id="86ec5-125">資料共同作業</span><span class="sxs-lookup"><span data-stu-id="86ec5-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="86ec5-126">行動性</span><span class="sxs-lookup"><span data-stu-id="86ec5-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="86ec5-127">商務用 Skype Server 2015 應力和效能工具隨附的應用程式和檔案</span><span class="sxs-lookup"><span data-stu-id="86ec5-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="86ec5-128">這些應用程式是商務用 Skype Server 壓力和效能工具的一部分：</span><span class="sxs-lookup"><span data-stu-id="86ec5-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="86ec5-129">**工具**</span><span class="sxs-lookup"><span data-stu-id="86ec5-129">**Tool**</span></span>|<span data-ttu-id="86ec5-130">**描述**</span><span class="sxs-lookup"><span data-stu-id="86ec5-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="86ec5-131">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="86ec5-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="86ec5-132">此工具用來建立使用者和連絡人。</span><span class="sxs-lookup"><span data-stu-id="86ec5-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="86ec5-133">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="86ec5-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="86ec5-134">用來設定所模擬之使用者負載的特性。</span><span class="sxs-lookup"><span data-stu-id="86ec5-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="86ec5-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="86ec5-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="86ec5-136">模擬使用者負載的工具。</span><span class="sxs-lookup"><span data-stu-id="86ec5-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="86ec5-137">預設的 tmx</span><span class="sxs-lookup"><span data-stu-id="86ec5-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="86ec5-138">需要使用商務用 Skype Server 2015 記錄工具。</span><span class="sxs-lookup"><span data-stu-id="86ec5-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="86ec5-139">布建腳本範例</span><span class="sxs-lookup"><span data-stu-id="86ec5-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="86ec5-140">根據特定案例，用來設定執行負載測試的拓撲。</span><span class="sxs-lookup"><span data-stu-id="86ec5-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="86ec5-141">您可能需要加以修改，使其與您的特定環境相關。</span><span class="sxs-lookup"><span data-stu-id="86ec5-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="86ec5-142">本節中的主題</span><span class="sxs-lookup"><span data-stu-id="86ec5-142">Topics in this section</span></span>

<span data-ttu-id="86ec5-143">若需要深入瞭解，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="86ec5-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="86ec5-144">Skype for Busines 應力和效能工具的必要條件和設定</span><span class="sxs-lookup"><span data-stu-id="86ec5-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="86ec5-145">商務用 Skype Server 2015 應力和效能工具的效能案例</span><span class="sxs-lookup"><span data-stu-id="86ec5-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="86ec5-146">在壓力和效能案例中布建拓撲以執行負載</span><span class="sxs-lookup"><span data-stu-id="86ec5-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="86ec5-147">設定商務用 Skype Server 2015 應力和效能工具的原則</span><span class="sxs-lookup"><span data-stu-id="86ec5-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="86ec5-148">使用商務用 Skype Server 2015 應力和效能工具</span><span class="sxs-lookup"><span data-stu-id="86ec5-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="86ec5-149">商務用 Skype Server 2015 的常見問題解答和效能工具</span><span class="sxs-lookup"><span data-stu-id="86ec5-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

