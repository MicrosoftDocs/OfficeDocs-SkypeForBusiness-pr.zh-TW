---
title: 驗證試驗集區與舊版集區共存
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
description: 使用舊版池來驗證試驗池共存的程式。
ms.openlocfilehash: 386ea4a7857fcdef7d45e5d8029ff4bf31293819
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812671"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="3392e-103">驗證試驗集區與舊版集區共存</span><span class="sxs-lookup"><span data-stu-id="3392e-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="3392e-104">**本文內容**</span><span class="sxs-lookup"><span data-stu-id="3392e-104">**In this article**</span></span>
  
[<span data-ttu-id="3392e-105">確認已開始使用商務用 Skype Server 2019 服務</span><span class="sxs-lookup"><span data-stu-id="3392e-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
<span data-ttu-id="3392e-106">[開啟商務用 Skype Server 2019 的 [控制台]](#sectionSection1)</span><span class="sxs-lookup"><span data-stu-id="3392e-106">[Open the Skype for Business Server 2019 Control Panel](#sectionSection1)</span></span>
  
[<span data-ttu-id="3392e-107">不要嘗試在舊版拓撲建立器中開啟拓撲</span><span class="sxs-lookup"><span data-stu-id="3392e-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="3392e-108">部署試生產池之後，您必須使用 [管理工具] 來查看池資訊，以驗證這兩個池的共存性。</span><span class="sxs-lookup"><span data-stu-id="3392e-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="3392e-109">針對商務用 Skype Server 2019 池與舊版池，您必須使用商務用 Skype Server 2019 的控制台與拓撲建立工具。</span><span class="sxs-lookup"><span data-stu-id="3392e-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="3392e-110">確認已開始使用商務用 Skype Server 2019 服務</span><span class="sxs-lookup"><span data-stu-id="3392e-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="3392e-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="3392e-111"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="3392e-112">從商務用 Skype Server 2019 前端伺服器，流覽至系統管理 Tools\Services 小程式。</span><span class="sxs-lookup"><span data-stu-id="3392e-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="3392e-113">確認下列服務正在前端伺服器上執行：</span><span class="sxs-lookup"><span data-stu-id="3392e-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="3392e-114">集中式記錄服務代理程式</span><span class="sxs-lookup"><span data-stu-id="3392e-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="3392e-115">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="3392e-115">Application Sharing</span></span>
    - <span data-ttu-id="3392e-116">音訊測試服務</span><span class="sxs-lookup"><span data-stu-id="3392e-116">Audio Test Service</span></span>
    - <span data-ttu-id="3392e-117">音訊/視訊會議</span><span class="sxs-lookup"><span data-stu-id="3392e-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="3392e-118">通話駐留</span><span class="sxs-lookup"><span data-stu-id="3392e-118">Call Park</span></span>
    - <span data-ttu-id="3392e-119">會議公告</span><span class="sxs-lookup"><span data-stu-id="3392e-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="3392e-120">會議助理</span><span class="sxs-lookup"><span data-stu-id="3392e-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="3392e-121">前端</span><span class="sxs-lookup"><span data-stu-id="3392e-121">Front-End</span></span>
    - <span data-ttu-id="3392e-122">IM 會議</span><span class="sxs-lookup"><span data-stu-id="3392e-122">IM Conferencing</span></span>
    - <span data-ttu-id="3392e-123">仲介</span><span class="sxs-lookup"><span data-stu-id="3392e-123">Mediation</span></span>
    - <span data-ttu-id="3392e-124">複本複製器代理程式</span><span class="sxs-lookup"><span data-stu-id="3392e-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="3392e-125">回應群組</span><span class="sxs-lookup"><span data-stu-id="3392e-125">Response Group</span></span>
    - <span data-ttu-id="3392e-126">Web 會議</span><span class="sxs-lookup"><span data-stu-id="3392e-126">Web Conferencing</span></span>
    - <span data-ttu-id="3392e-127">XMPP 翻譯閘道</span><span class="sxs-lookup"><span data-stu-id="3392e-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="3392e-128">開啟商務用 Skype Server 2019 的 [控制台]</span><span class="sxs-lookup"><span data-stu-id="3392e-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="3392e-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="3392e-129"><a name="sectionSection1"> </a></span></span>

<span data-ttu-id="3392e-130">在商務用 Skype Server 2019 部署中，在前端伺服器上開啟 [商務用 Skype Server 2019] 控制台，然後選取 [舊版] 池。</span><span class="sxs-lookup"><span data-stu-id="3392e-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="3392e-131">重複此程式以開啟商務用 Skype Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="3392e-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3392e-132">在商務用 Skype Server 2019 上，您必須先將 Silverlight 升級至 Silverlight 版本5，然後才能使用商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="3392e-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="3392e-133">此拓朴現在包含舊版及商務用 Skype Server 2019 伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="3392e-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="3392e-134">不要嘗試在舊版拓撲建立器中開啟拓撲</span><span class="sxs-lookup"><span data-stu-id="3392e-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="3392e-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="3392e-135"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="3392e-136">只能使用商務用 Skype Server 2019 拓撲產生器來查看拓撲。</span><span class="sxs-lookup"><span data-stu-id="3392e-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="3392e-137">商務用 Skype Server 2019 拓撲產生器必須用來建立商務用 Skype Server 2019 和舊版安裝的 pool。</span><span class="sxs-lookup"><span data-stu-id="3392e-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

