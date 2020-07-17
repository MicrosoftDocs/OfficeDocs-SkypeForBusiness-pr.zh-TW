---
title: 驗證試驗集區與舊版集區共存
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
description: 驗證試驗集區與舊版集區共存的處理常式。
ms.openlocfilehash: e9fe944c03c88aad2ca2b40f0e995842363e7a85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751655"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="6d82b-103">驗證試驗集區與舊版集區共存</span><span class="sxs-lookup"><span data-stu-id="6d82b-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="6d82b-104">**In this article**</span><span class="sxs-lookup"><span data-stu-id="6d82b-104">**In this article**</span></span>
  
[<span data-ttu-id="6d82b-105">驗證商務用 Skype Server 2019 服務已啟動</span><span class="sxs-lookup"><span data-stu-id="6d82b-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="6d82b-106">開啟商務用 Skype Server 2019 控制台</span><span class="sxs-lookup"><span data-stu-id="6d82b-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="6d82b-107">不要嘗試在舊版拓撲產生器中開啟拓撲</span><span class="sxs-lookup"><span data-stu-id="6d82b-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="6d82b-108">部署試驗集區之後，您必須使用系統管理工具來查看集區資訊，以確認兩個集區共存。</span><span class="sxs-lookup"><span data-stu-id="6d82b-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="6d82b-109">若為商務用 Skype Server 2019 集區和舊版集區，您必須使用商務用 Skype Server 2019 控制台和拓撲產生器工具。</span><span class="sxs-lookup"><span data-stu-id="6d82b-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="6d82b-110">驗證商務用 Skype Server 2019 服務已啟動</span><span class="sxs-lookup"><span data-stu-id="6d82b-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="6d82b-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="6d82b-111"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="6d82b-112">從商務用 Skype Server 2019 前端伺服器，流覽至 [管理工具 \ 服務] 小程式。</span><span class="sxs-lookup"><span data-stu-id="6d82b-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="6d82b-113">確認下列服務正在前端伺服器上執行：</span><span class="sxs-lookup"><span data-stu-id="6d82b-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="6d82b-114">集中式記錄服務代理程式</span><span class="sxs-lookup"><span data-stu-id="6d82b-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="6d82b-115">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="6d82b-115">Application Sharing</span></span>
    - <span data-ttu-id="6d82b-116">音訊測試服務</span><span class="sxs-lookup"><span data-stu-id="6d82b-116">Audio Test Service</span></span>
    - <span data-ttu-id="6d82b-117">會議 Audio/Video</span><span class="sxs-lookup"><span data-stu-id="6d82b-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="6d82b-118">通話駐留</span><span class="sxs-lookup"><span data-stu-id="6d82b-118">Call Park</span></span>
    - <span data-ttu-id="6d82b-119">會議宣告</span><span class="sxs-lookup"><span data-stu-id="6d82b-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="6d82b-120">會議助理</span><span class="sxs-lookup"><span data-stu-id="6d82b-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="6d82b-121">前端</span><span class="sxs-lookup"><span data-stu-id="6d82b-121">Front-End</span></span>
    - <span data-ttu-id="6d82b-122">IM 會議</span><span class="sxs-lookup"><span data-stu-id="6d82b-122">IM Conferencing</span></span>
    - <span data-ttu-id="6d82b-123">調解</span><span class="sxs-lookup"><span data-stu-id="6d82b-123">Mediation</span></span>
    - <span data-ttu-id="6d82b-124">複製副本複製器代理程式</span><span class="sxs-lookup"><span data-stu-id="6d82b-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="6d82b-125">回應群組</span><span class="sxs-lookup"><span data-stu-id="6d82b-125">Response Group</span></span>
    - <span data-ttu-id="6d82b-126">Web 會議</span><span class="sxs-lookup"><span data-stu-id="6d82b-126">Web Conferencing</span></span>
    - <span data-ttu-id="6d82b-127">XMPP 轉譯閘道</span><span class="sxs-lookup"><span data-stu-id="6d82b-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="6d82b-128">開啟商務用 Skype Server 2019 控制台</span><span class="sxs-lookup"><span data-stu-id="6d82b-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="6d82b-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="6d82b-129"><a name="sectionSection1"> </a></span></span>

<span data-ttu-id="6d82b-130">在商務用 Skype Server 2019 部署中的前端伺服器上，開啟商務用 Skype Server 2019 控制台，然後選取舊版集區。</span><span class="sxs-lookup"><span data-stu-id="6d82b-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="6d82b-131">重複此程式以開啟商務用 Skype Server 2019 集區。</span><span class="sxs-lookup"><span data-stu-id="6d82b-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6d82b-132">在商務用 Skype Server 2019 上，您必須在使用商務用 Skype Server 控制台之前，將 Silverlight 升級至 Silverlight 第5版。</span><span class="sxs-lookup"><span data-stu-id="6d82b-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="6d82b-133">此拓撲現在包括舊版和商務用 Skype Server 2019 伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="6d82b-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="6d82b-134">不要嘗試在舊版拓撲產生器中開啟拓撲</span><span class="sxs-lookup"><span data-stu-id="6d82b-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="6d82b-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="6d82b-135"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="6d82b-136">只能使用商務用 Skype Server 2019 拓撲產生器來查看拓撲。</span><span class="sxs-lookup"><span data-stu-id="6d82b-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="6d82b-137">商務用 Skype Server 2019 拓撲產生器必須用來為商務用 Skype Server 2019 和舊版安裝建立集區。</span><span class="sxs-lookup"><span data-stu-id="6d82b-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

