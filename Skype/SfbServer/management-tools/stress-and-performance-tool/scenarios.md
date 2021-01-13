---
title: 商務用 Skype Server 2015 應力和效能工具的效能案例
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 使用壓力和效能工具，將商務用 Skype Server 2015 設定為執行效能和負載測試時所需執行的工作。
ms.openlocfilehash: 3edc945f09ef5b2c7c6ecdefcbc66166f0945aec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814703"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="ec469-103">商務用 Skype Server 2015 應力和效能工具的效能案例</span><span class="sxs-lookup"><span data-stu-id="ec469-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="ec469-104">使用壓力和效能工具，將商務用 Skype Server 2015 設定為執行效能和負載測試時所需執行的工作。</span><span class="sxs-lookup"><span data-stu-id="ec469-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="ec469-105">若要執行商務用 Skype Server 2015 應力和效能工具 (LyncPerfTool) ，必須先針對與您相關的案例，設定商務用 Skype Server 2015 拓撲。</span><span class="sxs-lookup"><span data-stu-id="ec469-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="ec469-106">如果未設定商務用 Skype Server 2015，或設定不正確，您的負載模擬很可能會失敗。</span><span class="sxs-lookup"><span data-stu-id="ec469-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="ec469-107">透過商務用 Skype Server 2015 應力和效能工具，我們會在 [下載工具](https://www.microsoft.com/download/details.aspx?id=50367)時，供應商務用 Skype Server 管理命令介面腳本和基本資源檔案的範例。</span><span class="sxs-lookup"><span data-stu-id="ec469-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="ec469-108">這些可以做為設定商務用 Skype Server 部署的開始點。</span><span class="sxs-lookup"><span data-stu-id="ec469-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="ec469-109">本文說明所提供的 Windows PowerShell 範例。</span><span class="sxs-lookup"><span data-stu-id="ec469-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ec469-110">本主題不會協助您說明如何設定商務用 Skype Server 2015。一般而言，我們有其他的規劃及部署主題。</span><span class="sxs-lookup"><span data-stu-id="ec469-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="ec469-111">如需在商務用 Skype Server 2015 中使用 Windows PowerShell 的詳細資訊，請參閱此處的插入簡介中的商務用 Skype Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="ec469-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="ec469-112">關於執行商務用 Skype Server 管理命令介面腳本</span><span class="sxs-lookup"><span data-stu-id="ec469-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="ec469-113">我們會提供可用於準備負載模擬的範例 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="ec469-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="ec469-114">因為這些腳本是用來進行負載模擬，所以您會發現這些腳本很簡單且具有容許的效果。</span><span class="sxs-lookup"><span data-stu-id="ec469-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="ec469-115">這可能不適合您的實際執行環境。</span><span class="sxs-lookup"><span data-stu-id="ec469-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="ec469-116">同樣地，我們很強調這些腳本是範例，您必須加以檢查，而且在許多情況下，在您的環境中進行相關變更之後，才能夠實際使用它們。</span><span class="sxs-lookup"><span data-stu-id="ec469-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="ec469-117">在最低限度下，我們預計您必須修改回應服務群組 (RSG) 腳本，以 (指定指派給代理人群組的代理程式) 。</span><span class="sxs-lookup"><span data-stu-id="ec469-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="ec469-118">不過，如果您不需要執行，則不需要執行。</span><span class="sxs-lookup"><span data-stu-id="ec469-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="ec469-119">請小心檢查和瞭解這些範例。</span><span class="sxs-lookup"><span data-stu-id="ec469-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="ec469-120">執行時，腳本會覆寫拓撲中的任何現有設定。</span><span class="sxs-lookup"><span data-stu-id="ec469-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="ec469-121">應力和效能工具用戶端版本名稱</span><span class="sxs-lookup"><span data-stu-id="ec469-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="ec469-122">如果您先前已變更預設值的設定，您可能需要設定用戶端版本檢查原則。</span><span class="sxs-lookup"><span data-stu-id="ec469-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="ec469-123">如果您不確定這一點，請查看 [用戶端版本檢查檔](https://msdn.microsoft.com/vsto/jj923060)。</span><span class="sxs-lookup"><span data-stu-id="ec469-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/vsto/jj923060).</span></span>
  
<span data-ttu-id="ec469-124">當與商務用 Skype Server 2015 通訊時，壓力和效能工具預設會使用下列使用者代理程式版本：</span><span class="sxs-lookup"><span data-stu-id="ec469-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="ec469-125">LSPT/15.0.0.0 (商務用 Skype Server 2015 應力和效能工具) </span><span class="sxs-lookup"><span data-stu-id="ec469-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="ec469-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="ec469-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="ec469-127">針對 LyncPerfTool 中的行動性 (UCWA) 用戶端：</span><span class="sxs-lookup"><span data-stu-id="ec469-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="ec469-128">UCWA Perf 工具/Web 會議</span><span class="sxs-lookup"><span data-stu-id="ec469-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="ec469-129">UCWA Perf 工具/行動裝置</span><span class="sxs-lookup"><span data-stu-id="ec469-129">UCWA Perf Tool/Mobile</span></span>
    

