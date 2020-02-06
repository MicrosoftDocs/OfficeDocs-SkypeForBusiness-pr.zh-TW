---
title: 在商務用 Skype Server 中管理會議原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 摘要：瞭解如何在商務用 Skype Server 中管理會議原則。
ms.openlocfilehash: fc069093b9cc7cf5ce0e1e1f1efc0ee9e18e335d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818644"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="09fcf-103">在商務用 Skype Server 中管理會議原則</span><span class="sxs-lookup"><span data-stu-id="09fcf-103">Manage conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="09fcf-104">**摘要：** 瞭解如何在商務用 Skype Server 中管理會議原則。</span><span class="sxs-lookup"><span data-stu-id="09fcf-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="09fcf-105">本主題說明如何管理會議原則。</span><span class="sxs-lookup"><span data-stu-id="09fcf-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="09fcf-106">如需如何規劃及部署會議的詳細資訊，請參閱[在商務用 Skype server 中規劃會議](../../plan-your-deployment/conferencing/conferencing.md)，以及[在商務用 Skype 伺服器中部署會議](../../deploy/deploy-conferencing/deploy-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="09fcf-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="09fcf-107">會議原則可讓您定義各種排程和參與選項，包括從會議是否可以將 IP 音訊與影片加入到可參與的人數上限。</span><span class="sxs-lookup"><span data-stu-id="09fcf-107">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend.</span></span> <span data-ttu-id="09fcf-108">您可以使用會議原則來管理會議的安全性、頻寬和法律方面。</span><span class="sxs-lookup"><span data-stu-id="09fcf-108">You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="09fcf-109">您可以在三個層級定義會議原則：全域範圍、網站範圍和使用者範圍。</span><span class="sxs-lookup"><span data-stu-id="09fcf-109">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="09fcf-110">[設定] 會將最窄範圍的特定使用者套用至最廣泛的範圍。</span><span class="sxs-lookup"><span data-stu-id="09fcf-110">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="09fcf-111">如果您將原則指派給使用者，這些設定就會優先使用。</span><span class="sxs-lookup"><span data-stu-id="09fcf-111">If you assign a policy to a user, those settings take precedence.</span></span> <span data-ttu-id="09fcf-112">如果您沒有指派使用者原則，就會套用 [網站設定]。</span><span class="sxs-lookup"><span data-stu-id="09fcf-112">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="09fcf-113">如果沒有適用的使用者或網站原則，全域原則就會提供預設設定。</span><span class="sxs-lookup"><span data-stu-id="09fcf-113">If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="09fcf-114">全域原則預設存在，所以您無法建立新的全域原則。</span><span class="sxs-lookup"><span data-stu-id="09fcf-114">A global policy exists by default, so you cannot create a new global policy.</span></span> <span data-ttu-id="09fcf-115">您也無法刪除現有的全域原則，但您可以變更現有的全域原則，來自訂您的預設設定。</span><span class="sxs-lookup"><span data-stu-id="09fcf-115">You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="09fcf-116">使用商務用 Skype Server [控制台] 管理會議原則</span><span class="sxs-lookup"><span data-stu-id="09fcf-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="09fcf-117">若要使用商務用 Skype Server [控制台] 管理會議原則，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="09fcf-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="09fcf-118">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="09fcf-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="09fcf-119">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="09fcf-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="09fcf-120">在左側導覽列中，按一下 [**會議**]，然後按一下 [**會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="09fcf-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="09fcf-121">使用商務用 Skype Server Management Shell 管理會議原則</span><span class="sxs-lookup"><span data-stu-id="09fcf-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="09fcf-122">若要使用商務用 Skype Server Management Shell 管理會議，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="09fcf-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="09fcf-123">**會議原則設定**</span><span class="sxs-lookup"><span data-stu-id="09fcf-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="09fcf-124">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="09fcf-124">**Cmdlet**</span></span>|<span data-ttu-id="09fcf-125">**說明**</span><span class="sxs-lookup"><span data-stu-id="09fcf-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="09fcf-126">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="09fcf-126">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="09fcf-127">傳回已設定為在您組織中使用之會議原則的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="09fcf-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="09fcf-128">授與 CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="09fcf-128">Grant-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="09fcf-129">在每個使用者範圍指派會議原則。</span><span class="sxs-lookup"><span data-stu-id="09fcf-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="09fcf-130">New-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="09fcf-130">New-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="09fcf-131">建立新的會議原則供您的組織使用。</span><span class="sxs-lookup"><span data-stu-id="09fcf-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="09fcf-132">Remove-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="09fcf-132">Remove-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="09fcf-133">移除指定的會議原則。</span><span class="sxs-lookup"><span data-stu-id="09fcf-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="09fcf-134">Set-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="09fcf-134">Set-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="09fcf-135">修改現有的會議原則。</span><span class="sxs-lookup"><span data-stu-id="09fcf-135">Modifies an existing conferencing policy.</span></span>  <br/> |
   

