---
title: 在商務用 Skype Server 中刪除現有的封存原則
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
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 摘要：瞭解如何刪除商務用 Skype 伺服器的封存原則。
ms.openlocfilehash: 2baad7d862b1b6739019a4459492bfb3b67e04cc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095387"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="9c97c-103">在商務用 Skype Server 中刪除現有的封存原則</span><span class="sxs-lookup"><span data-stu-id="9c97c-103">Delete an existing archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="9c97c-104">**摘要：** 瞭解如何刪除商務用 Skype 伺服器的封存原則。</span><span class="sxs-lookup"><span data-stu-id="9c97c-104">**Summary:** Learn how to delete an archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="9c97c-105">您可以刪除使用者原則或網站原則，但不能刪除全域原則。</span><span class="sxs-lookup"><span data-stu-id="9c97c-105">You can delete a user policy or site policy, but not the global policy.</span></span> <span data-ttu-id="9c97c-106">如果您刪除全域原則，商務用 Skype 伺服器會自動將原則重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="9c97c-106">If you delete the global policy, Skype for Business Server automatically resets the policy to the default values.</span></span>
  
## <a name="delete-a-policy-by-using-the-control-panel"></a><span data-ttu-id="9c97c-107">使用控制台刪除原則</span><span class="sxs-lookup"><span data-stu-id="9c97c-107">Delete a policy by using the Control Panel</span></span>

1. <span data-ttu-id="9c97c-108">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="9c97c-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="9c97c-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="9c97c-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="9c97c-110">在左側導覽列中，依序按一下 **[監控和封存]** 和 **[封存原則]**。</span><span class="sxs-lookup"><span data-stu-id="9c97c-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="9c97c-111">在封存原則清單中，依序按一下您要刪除的使用者或網站原則、**[編輯]** 和 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="9c97c-111">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="9c97c-112">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="9c97c-112">Click **Commit**.</span></span>
    
## <a name="delete-a-policy-by-using-windows-powershell"></a><span data-ttu-id="9c97c-113">使用 Windows PowerShell 刪除原則</span><span class="sxs-lookup"><span data-stu-id="9c97c-113">Delete a policy by using Windows PowerShell</span></span>

<span data-ttu-id="9c97c-114">您也可以使用 **Remove-grant-csarchivingpolicy** Cmdlet 刪除封存原則。</span><span class="sxs-lookup"><span data-stu-id="9c97c-114">You can also delete archiving policies by using the **Remove-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="9c97c-115">例如，下列命令會刪除 Identity 為 site： Redmond 的原則。</span><span class="sxs-lookup"><span data-stu-id="9c97c-115">For example, the following command deletes the policy with the Identity site:Redmond.</span></span> <span data-ttu-id="9c97c-116">當刪除在網站層級設定的原則時，系統會自動依全域封存原則來控制先前由網站原則管理的使用者：</span><span class="sxs-lookup"><span data-stu-id="9c97c-116">When a policy configured at the site level is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

<span data-ttu-id="9c97c-117">此命令會移除所有套用至每個使用者層級的封存原則：</span><span class="sxs-lookup"><span data-stu-id="9c97c-117">This command removes all the archiving policies applied to the per-user level:</span></span>
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

<span data-ttu-id="9c97c-118">這個命令會移除所有已停用內部封存的封存原則：</span><span class="sxs-lookup"><span data-stu-id="9c97c-118">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

<span data-ttu-id="9c97c-119">如需詳細資訊，請參閱 [grant-csarchivingpolicy](/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="9c97c-119">For more information, see the help topic for the [Remove-CsArchivingPolicy](/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>