---
title: 在商務用 Skype Server 中管理會議原則
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
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 摘要：瞭解如何在商務用 Skype Server 中管理會議原則。
ms.openlocfilehash: 39855aac09b88852d0931c9b8fbdb8e2e9187c71
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099099"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="44fb8-103">在商務用 Skype Server 中管理會議原則</span><span class="sxs-lookup"><span data-stu-id="44fb8-103">Manage conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="44fb8-104">**摘要：** 瞭解如何在商務用 Skype Server 中管理會議原則。</span><span class="sxs-lookup"><span data-stu-id="44fb8-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="44fb8-105">本主題說明如何管理會議原則。</span><span class="sxs-lookup"><span data-stu-id="44fb8-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="44fb8-106">如需如何規劃及部署會議的詳細資訊，請參閱在商務用 skype server 中 [規劃會議](../../plan-your-deployment/conferencing/conferencing.md) ，以及 [在商務用 Skype server 中部署會議](../../deploy/deploy-conferencing/deploy-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="44fb8-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="44fb8-107">會議原則可讓您定義各種各樣的排程和參與選項，範圍是從會議是否可包含 IP 音訊和影片到可參加會議的人員人數上限。</span><span class="sxs-lookup"><span data-stu-id="44fb8-107">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend.</span></span> <span data-ttu-id="44fb8-108">您可以使用會議原則來管理會議的安全性、頻寬和法律方面。</span><span class="sxs-lookup"><span data-stu-id="44fb8-108">You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="44fb8-109">您可在三個層級定義會議原則：通用範圍、站台範圍，以及使用者範圍。</span><span class="sxs-lookup"><span data-stu-id="44fb8-109">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="44fb8-110">設定值會依據最窄的範圍到最寬的範圍，依序套用至特定使用者。</span><span class="sxs-lookup"><span data-stu-id="44fb8-110">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="44fb8-111">如果您將原則指派給使用者，這些設定會優先。</span><span class="sxs-lookup"><span data-stu-id="44fb8-111">If you assign a policy to a user, those settings take precedence.</span></span> <span data-ttu-id="44fb8-112">如果未指派使用者原則，則會套用站台設定。</span><span class="sxs-lookup"><span data-stu-id="44fb8-112">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="44fb8-113">如果未套用使用者或站台原則，則由通用原則提供預設值。</span><span class="sxs-lookup"><span data-stu-id="44fb8-113">If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="44fb8-p104">由於通用原則預設已經存在，因此您無法建立新的通用原則。您也無法刪除現有的通用原則，但您可以變更現有通用原則，自訂您自己的預設值。</span><span class="sxs-lookup"><span data-stu-id="44fb8-p104">A global policy exists by default, so you cannot create a new global policy. You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="44fb8-116">使用商務用 Skype Server 控制台管理會議原則</span><span class="sxs-lookup"><span data-stu-id="44fb8-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="44fb8-117">若要使用商務用 Skype Server 控制台管理會議原則：</span><span class="sxs-lookup"><span data-stu-id="44fb8-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="44fb8-118">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="44fb8-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="44fb8-119">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="44fb8-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="44fb8-120">在左導覽列中，按一下 [ **會議**]，然後按一下 [ **會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="44fb8-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="44fb8-121">使用商務用 Skype Server 管理命令介面來管理會議原則</span><span class="sxs-lookup"><span data-stu-id="44fb8-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="44fb8-122">若要使用商務用 Skype Server 管理命令介面來管理會議，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="44fb8-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="44fb8-123">**會議原則設定**</span><span class="sxs-lookup"><span data-stu-id="44fb8-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="44fb8-124">**指令程式**</span><span class="sxs-lookup"><span data-stu-id="44fb8-124">**Cmdlet**</span></span>|<span data-ttu-id="44fb8-125">**描述**</span><span class="sxs-lookup"><span data-stu-id="44fb8-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="44fb8-126">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="44fb8-126">Get-CsConferencingPolicy</span></span>](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="44fb8-127">傳回已設定供組織使用之會議原則的資訊。</span><span class="sxs-lookup"><span data-stu-id="44fb8-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="44fb8-128">Grant-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="44fb8-128">Grant-CsConferencingPolicy</span></span>](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="44fb8-129">在每個使用者範圍指派會議原則。</span><span class="sxs-lookup"><span data-stu-id="44fb8-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="44fb8-130">New-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="44fb8-130">New-CsConferencingPolicy</span></span>](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="44fb8-131">建立新的會議原則供您的組織使用。</span><span class="sxs-lookup"><span data-stu-id="44fb8-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="44fb8-132">Remove-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="44fb8-132">Remove-CsConferencingPolicy</span></span>](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="44fb8-133">移除指定的會議原則。</span><span class="sxs-lookup"><span data-stu-id="44fb8-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="44fb8-134">Set-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="44fb8-134">Set-CsConferencingPolicy</span></span>](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="44fb8-135">修改現有的會議原則。</span><span class="sxs-lookup"><span data-stu-id="44fb8-135">Modifies an existing conferencing policy.</span></span>  <br/> |
