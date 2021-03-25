---
title: 在商務用 Skype Server 中刪除會議原則
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
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 摘要：瞭解如何在商務用 Skype Server 中刪除會議原則。
ms.openlocfilehash: 9aadaf82aea7f057cf1969f06d4257992b64a86a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119502"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="2d016-103">在商務用 Skype Server 中刪除會議原則</span><span class="sxs-lookup"><span data-stu-id="2d016-103">Delete conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="2d016-104">**摘要：** 瞭解如何在商務用 Skype Server 中刪除會議原則。</span><span class="sxs-lookup"><span data-stu-id="2d016-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="2d016-105">您可以使用商務用 Skype Server 控制台或使用商務用 Skype Server 管理命令介面來刪除會議原則。</span><span class="sxs-lookup"><span data-stu-id="2d016-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="2d016-106">使用商務用 Skype Server 控制台刪除會議原則</span><span class="sxs-lookup"><span data-stu-id="2d016-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="2d016-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="2d016-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="2d016-108">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="2d016-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="2d016-109">在左導覽列中，按一下 [ **會議**]，然後按一下 [ **會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="2d016-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="2d016-110">在會議原則清單中，按一下您要刪除的網站或使用者原則，按一下 [ **編輯**]，然後按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="2d016-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="2d016-111">使用商務用 Skype Server 管理命令介面刪除會議原則</span><span class="sxs-lookup"><span data-stu-id="2d016-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="2d016-112">若要刪除會議原則，請使用 **Remove-CsConferencingPolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2d016-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="2d016-113">下列命令可移除具有 Identity RedmondConferencingPolicy 的會議原則：</span><span class="sxs-lookup"><span data-stu-id="2d016-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="2d016-114">下一個命令會刪除任何允許外部使用者錄製會議的會議原則：</span><span class="sxs-lookup"><span data-stu-id="2d016-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="2d016-115">如需詳細資訊，包括完整的語法及參數清單，請參閱 [Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="2d016-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
