---
title: 在商務用 Skype Server 中刪除現有的存檔原則
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
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 摘要：瞭解如何刪除商務用 Skype Server 的存檔原則。
ms.openlocfilehash: 8e2a2c21f6d137fcdb87e69c041cf08143092be1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818925"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="d1e05-103">在商務用 Skype Server 中刪除現有的存檔原則</span><span class="sxs-lookup"><span data-stu-id="d1e05-103">Delete an existing archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="d1e05-104">**摘要：** 瞭解如何刪除商務用 Skype Server 的存檔原則。</span><span class="sxs-lookup"><span data-stu-id="d1e05-104">**Summary:** Learn how to delete an archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="d1e05-105">您可以刪除使用者原則或網站原則，但不能刪除全域原則。</span><span class="sxs-lookup"><span data-stu-id="d1e05-105">You can delete a user policy or site policy, but not the global policy.</span></span> <span data-ttu-id="d1e05-106">如果您刪除全域原則，商務用 Skype 伺服器會自動將原則重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="d1e05-106">If you delete the global policy, Skype for Business Server automatically resets the policy to the default values.</span></span>
  
## <a name="delete-a-policy-by-using-the-control-panel"></a><span data-ttu-id="d1e05-107">使用 [控制台] 刪除原則</span><span class="sxs-lookup"><span data-stu-id="d1e05-107">Delete a policy by using the Control Panel</span></span>

1. <span data-ttu-id="d1e05-108">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d1e05-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="d1e05-109">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="d1e05-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d1e05-110">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**原則**]。</span><span class="sxs-lookup"><span data-stu-id="d1e05-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="d1e05-111">在歸檔原則清單中，按一下您要刪除的使用者或網站原則，按一下 [**編輯**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="d1e05-111">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="d1e05-112">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d1e05-112">Click **Commit**.</span></span>
    
## <a name="delete-a-policy-by-using-windows-powershell"></a><span data-ttu-id="d1e05-113">使用 Windows PowerShell 刪除原則</span><span class="sxs-lookup"><span data-stu-id="d1e05-113">Delete a policy by using Windows PowerShell</span></span>

<span data-ttu-id="d1e05-114">您也可以使用**CsArchivingPolicy** Cmdlet 刪除存檔原則。</span><span class="sxs-lookup"><span data-stu-id="d1e05-114">You can also delete archiving policies by using the **Remove-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="d1e05-115">例如，下列命令會刪除具有身分識別網站：雷德蒙的原則。</span><span class="sxs-lookup"><span data-stu-id="d1e05-115">For example, the following command deletes the policy with the Identity site:Redmond.</span></span> <span data-ttu-id="d1e05-116">在網站層級設定的原則已刪除時，由「全域歸檔原則」所管理的使用者將會自動受全域存檔原則的管轄：</span><span class="sxs-lookup"><span data-stu-id="d1e05-116">When a policy configured at the site level is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

<span data-ttu-id="d1e05-117">這個命令會移除已套用至每個使用者層級的所有存檔原則：</span><span class="sxs-lookup"><span data-stu-id="d1e05-117">This command removes all the archiving policies applied to the per-user level:</span></span>
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

<span data-ttu-id="d1e05-118">這個命令會移除已停用內部封存的所有存檔原則：</span><span class="sxs-lookup"><span data-stu-id="d1e05-118">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

<span data-ttu-id="d1e05-119">如需詳細資訊，請參閱[Remove CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="d1e05-119">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
