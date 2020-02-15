---
title: The Skype for Business Server 2015 壓力及效能工具的效能案例
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
description: 您必須設定商務用 Skype Server 2015 進行效能和負載測試，使用 [壓力及效能工具執行的工作。
ms.openlocfilehash: 5531627ab7d5072d32dfcf60fed41eac47f5373f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983848"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="84093-103">The Skype for Business Server 2015 壓力及效能工具的效能案例</span><span class="sxs-lookup"><span data-stu-id="84093-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="84093-104">您必須設定商務用 Skype Server 2015 進行效能和負載測試，使用 [壓力及效能工具執行的工作。</span><span class="sxs-lookup"><span data-stu-id="84093-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="84093-105">若要執行 Skype for Business Server 2015 壓力及效能工具 (LyncPerfTool)，商務用 Skype Server 2015 拓撲必須先設定相關給您的案例。</span><span class="sxs-lookup"><span data-stu-id="84093-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="84093-106">如果商務用 Skype Server 2015 未設定，或未正確設定，您的負載模擬是很可能會失敗。</span><span class="sxs-lookup"><span data-stu-id="84093-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="84093-107">與 Skype for Business Server 2015 壓力及效能工具，我們提供範例 Skype for Business Server 管理命令介面指令碼和基本的資源檔案的[工具下載](https://www.microsoft.com/download/details.aspx?id=50367)的一部分。</span><span class="sxs-lookup"><span data-stu-id="84093-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="84093-108">這些可以用於做為起點設定您 Skype for Business Server 部署。</span><span class="sxs-lookup"><span data-stu-id="84093-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="84093-109">本文將告訴您提供的 Windows PowerShell 範例。</span><span class="sxs-lookup"><span data-stu-id="84093-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="84093-110">本主題將協助您說明如何設定用 Skype Server 2015 通常，我們有的其他規劃及部署主題。</span><span class="sxs-lookup"><span data-stu-id="84093-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="84093-111">如需使用 Windows PowerShell in Skype Server 2015 的詳細資訊，請參閱 < Skype for Business Server Management Shell 文件在此處插入簡介。</span><span class="sxs-lookup"><span data-stu-id="84093-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="84093-112">關於執行 Skype for Business Server 管理命令介面指令碼</span><span class="sxs-lookup"><span data-stu-id="84093-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="84093-113">我們提供範例 PowerShell 指令碼可用來準備您的負載模擬。</span><span class="sxs-lookup"><span data-stu-id="84093-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="84093-114">因為這些指令碼供負載模擬，您會發現他們既簡單又寬鬆]。</span><span class="sxs-lookup"><span data-stu-id="84093-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="84093-115">可能不適合實際執行環境。</span><span class="sxs-lookup"><span data-stu-id="84093-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="84093-116">再次我們壓力，這些指令碼範例，您必須重新檢閱並在許多情況下進行的變更與環境相關才能進行實際運用。</span><span class="sxs-lookup"><span data-stu-id="84093-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="84093-117">在最低限度下，我們應該會需要修改回應服務群組 」 (RSG) 指令碼，與您記住 （若要指定指派給代理人群組的代理程式） 的拓撲。</span><span class="sxs-lookup"><span data-stu-id="84093-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="84093-118">但您不需要執行，如果您不需要。</span><span class="sxs-lookup"><span data-stu-id="84093-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="84093-119">請謹慎檢閱和了解這些範例中。</span><span class="sxs-lookup"><span data-stu-id="84093-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="84093-120">指令碼將會覆寫任何現有的設定，在拓撲中執行時。</span><span class="sxs-lookup"><span data-stu-id="84093-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="84093-121">壓力及效能工具的用戶端版本名稱</span><span class="sxs-lookup"><span data-stu-id="84093-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="84093-122">您可能需要設定用戶端版本檢查原則，如果您先前已變更的設定與預設值。</span><span class="sxs-lookup"><span data-stu-id="84093-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="84093-123">如果您不確定這一點，檢查[用戶端版本檢查文件](https://msdn.microsoft.com/vsto/jj923060)。</span><span class="sxs-lookup"><span data-stu-id="84093-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/vsto/jj923060).</span></span>
  
<span data-ttu-id="84093-124">壓力及效能工具預設會使用下列的使用者代理程式版本通訊用 Skype Server 2015 時：</span><span class="sxs-lookup"><span data-stu-id="84093-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="84093-125">LSPT/15.0.0.0 (Skype for Business Server 2015 壓力及效能工具)</span><span class="sxs-lookup"><span data-stu-id="84093-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="84093-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="84093-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="84093-127">在 [LyncPerfTool 行動力 (UCWA) 用戶端：</span><span class="sxs-lookup"><span data-stu-id="84093-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="84093-128">UCWA Qfe 工具/Web 會議</span><span class="sxs-lookup"><span data-stu-id="84093-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="84093-129">UCWA Qfe 工具/行動</span><span class="sxs-lookup"><span data-stu-id="84093-129">UCWA Perf Tool/Mobile</span></span>
    

