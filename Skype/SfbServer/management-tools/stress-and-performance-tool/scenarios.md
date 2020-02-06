---
title: 商務用 Skype Server 2015 應力與效能工具的效能案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: 使用壓力與效能工具設定商務用 Skype Server 2015 以執行效能與載入測試時所需執行的工作。
ms.openlocfilehash: 343378d0b0d763d8a290e8d1e930a64c5d114bdb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803873"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="b8c36-103">商務用 Skype Server 2015 應力與效能工具的效能案例</span><span class="sxs-lookup"><span data-stu-id="b8c36-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="b8c36-104">使用壓力與效能工具設定商務用 Skype Server 2015 以執行效能與載入測試時所需執行的工作。</span><span class="sxs-lookup"><span data-stu-id="b8c36-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="b8c36-105">若要執行商務用 Skype Server 2015 的壓力與效能工具（LyncPerfTool），必須先針對與您相關的案例設定商務用 Skype Server 2015 拓撲。</span><span class="sxs-lookup"><span data-stu-id="b8c36-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="b8c36-106">如果未設定商務用 Skype Server 2015，或設定不正確，您的負載模擬很可能會失敗。</span><span class="sxs-lookup"><span data-stu-id="b8c36-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="b8c36-107">使用商務用 Skype Server 2015 的壓力與效能工具，我們提供的是商務用 Skype Server Management Shell 腳本和基本資源[檔案的範例。](https://www.microsoft.com/download/details.aspx?id=50367)</span><span class="sxs-lookup"><span data-stu-id="b8c36-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="b8c36-108">這些都可以用來做為設定您的商務用 Skype Server 部署的起點。</span><span class="sxs-lookup"><span data-stu-id="b8c36-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="b8c36-109">本文將說明提供的 Windows PowerShell 範例。</span><span class="sxs-lookup"><span data-stu-id="b8c36-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b8c36-110">本主題無法協助您描述如何設定商務用 Skype Server 2015，我們通常會提供其他規劃與部署主題。</span><span class="sxs-lookup"><span data-stu-id="b8c36-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="b8c36-111">如需在商務用 Skype Server 2015 中使用 Windows PowerShell 的詳細資料，請參閱這裡的 [插入簡介] 中的商務用 Skype Server Management 命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="b8c36-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="b8c36-112">關於執行商務用 Skype Server management 命令介面腳本</span><span class="sxs-lookup"><span data-stu-id="b8c36-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="b8c36-113">我們正在提供您可以用來準備負載模擬的範例 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="b8c36-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="b8c36-114">因為這些腳本是用來進行負載模擬，所以您會發現它們很簡單且可供使用。</span><span class="sxs-lookup"><span data-stu-id="b8c36-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="b8c36-115">這可能不適合您的生產環境。</span><span class="sxs-lookup"><span data-stu-id="b8c36-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="b8c36-116">我們再次強調，這些腳本是範例，您需要複習這些程式，而且在許多情況下，您必須先對您的環境進行變更，才能實際使用它們。</span><span class="sxs-lookup"><span data-stu-id="b8c36-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="b8c36-117">我們會預計您必須使用您的拓撲來修改回應服務群組（RSG）腳本（以指定指派給 agent 群組的代理程式）。</span><span class="sxs-lookup"><span data-stu-id="b8c36-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="b8c36-118">但如果您不需要的話，您就不需要執行此程式。</span><span class="sxs-lookup"><span data-stu-id="b8c36-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b8c36-119">請小心閱讀並瞭解這些範例。</span><span class="sxs-lookup"><span data-stu-id="b8c36-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="b8c36-120">在執行時，腳本會覆寫拓撲中任何現有的設定。</span><span class="sxs-lookup"><span data-stu-id="b8c36-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="b8c36-121">壓力與效能工具用戶端版本名稱</span><span class="sxs-lookup"><span data-stu-id="b8c36-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="b8c36-122">如果您先前已變更預設值的設定，您可能需要設定用戶端版本檢查原則。</span><span class="sxs-lookup"><span data-stu-id="b8c36-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="b8c36-123">如果您不確定這一點，請核取[用戶端版本檢查檔](https://msdn.microsoft.com/en-us/vsto/jj923060)。</span><span class="sxs-lookup"><span data-stu-id="b8c36-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/en-us/vsto/jj923060).</span></span>
  
<span data-ttu-id="b8c36-124">當與商務用 Skype Server 2015 通訊時，[壓力] 和 [效能] 工具預設會使用下列使用者代理版本：</span><span class="sxs-lookup"><span data-stu-id="b8c36-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="b8c36-125">LSPT/15.0.0.0 （商務用 Skype Server 2015 應力與效能工具）</span><span class="sxs-lookup"><span data-stu-id="b8c36-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="b8c36-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="b8c36-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="b8c36-127">在 LyncPerfTool 中針對行動（UCWA）用戶端：</span><span class="sxs-lookup"><span data-stu-id="b8c36-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="b8c36-128">UCWA Perf 工具/Web 會議</span><span class="sxs-lookup"><span data-stu-id="b8c36-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="b8c36-129">UCWA Perf 工具/行動裝置</span><span class="sxs-lookup"><span data-stu-id="b8c36-129">UCWA Perf Tool/Mobile</span></span>
    

