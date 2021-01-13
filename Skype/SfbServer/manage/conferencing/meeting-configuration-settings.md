---
title: 在商務用 Skype Server 中管理會議配置設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 摘要：瞭解如何在商務用 Skype Server 中管理會議配置設定。
ms.openlocfilehash: c34723219839061e36b2684dff81efd5cd914843
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828083"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="a8144-103">在商務用 Skype Server 中管理會議配置設定</span><span class="sxs-lookup"><span data-stu-id="a8144-103">Manage meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="a8144-104">**摘要：** 瞭解如何在商務用 Skype Server 中管理會議配置設定。</span><span class="sxs-lookup"><span data-stu-id="a8144-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="a8144-105">本主題說明如何管理會議配置設定。</span><span class="sxs-lookup"><span data-stu-id="a8144-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="a8144-106">如需如何規劃及部署會議的詳細資訊，請參閱在商務用 skype server 中 [規劃會議](../../plan-your-deployment/conferencing/conferencing.md) ，以及 [在商務用 Skype server 中部署會議](../../deploy/deploy-conferencing/deploy-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="a8144-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="a8144-107">會議設定設定會口述使用者可以建立的會議類型，除了控制 (，甚至) 匿名使用者和電話撥入式會議使用者是否可以加入這些會議。</span><span class="sxs-lookup"><span data-stu-id="a8144-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="a8144-108">請注意，這些設定只會影響排程的會議;它們不會影響在商務用 Skype 中按一下 [立即開會] 選項所建立的特定會議。</span><span class="sxs-lookup"><span data-stu-id="a8144-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="a8144-109">會議配置設定定義下列專案：</span><span class="sxs-lookup"><span data-stu-id="a8144-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="a8144-110">是否將以公用交換電話網路 (PSTN) 撥入的使用者帶到大廳</span><span class="sxs-lookup"><span data-stu-id="a8144-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="a8144-111">誰可以成為簡報者</span><span class="sxs-lookup"><span data-stu-id="a8144-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="a8144-112">是否依預設值指派會議類型</span><span class="sxs-lookup"><span data-stu-id="a8144-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="a8144-113">預設是否允許匿名 (未授權) 使用者加入</span><span class="sxs-lookup"><span data-stu-id="a8144-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="a8144-114">您可以使用商務用 Skype Server 控制台或使用商務用 Skype Server 管理命令介面來定義會議的特性。</span><span class="sxs-lookup"><span data-stu-id="a8144-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="a8144-115">您可以指定預設) 、網站層級或集區層級所建立之全域層級 (的會議設定。</span><span class="sxs-lookup"><span data-stu-id="a8144-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="a8144-116">根據預設，全域設定會定義會議經驗。</span><span class="sxs-lookup"><span data-stu-id="a8144-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="a8144-117">如果您建立集區層級設定，這些設定會套用至該集區所主控的所有會議。</span><span class="sxs-lookup"><span data-stu-id="a8144-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="a8144-118">如果您未建立集區層級設定，則會套用網站層級設定（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="a8144-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="a8144-119">如果您未定義網站層級設定，全域設定會套用至所有會議。</span><span class="sxs-lookup"><span data-stu-id="a8144-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a8144-120">使用商務用 Skype Server 控制台管理會議設定</span><span class="sxs-lookup"><span data-stu-id="a8144-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="a8144-121">若要使用商務用 Skype Server 控制台管理會議設定：</span><span class="sxs-lookup"><span data-stu-id="a8144-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="a8144-122">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="a8144-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="a8144-123">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="a8144-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a8144-124">在左導覽列中，按一下 [ **會議**]，然後按一下 [ **會議** 設定]。</span><span class="sxs-lookup"><span data-stu-id="a8144-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a8144-125">使用商務用 Skype Server 管理命令介面來管理會議設定</span><span class="sxs-lookup"><span data-stu-id="a8144-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="a8144-126">若要使用商務用 Skype Server 管理命令介面來管理會議，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="a8144-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="a8144-127">**會議組態設定**</span><span class="sxs-lookup"><span data-stu-id="a8144-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="a8144-128">**指令程式**</span><span class="sxs-lookup"><span data-stu-id="a8144-128">**Cmdlet**</span></span>|<span data-ttu-id="a8144-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="a8144-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a8144-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a8144-130">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="a8144-131">會傳回組織中目前使用之會議設定設定的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a8144-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="a8144-132">New-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a8144-132">New-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="a8144-133">在網站或服務範圍建立新的會議組態設定集合。</span><span class="sxs-lookup"><span data-stu-id="a8144-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="a8144-134">Remove-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a8144-134">Remove-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="a8144-135">會刪除現有的會議配置設定集合。</span><span class="sxs-lookup"><span data-stu-id="a8144-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="a8144-136">Set-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="a8144-136">Set-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="a8144-137">修改組織中目前使用的會議設定設定。</span><span class="sxs-lookup"><span data-stu-id="a8144-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
   

