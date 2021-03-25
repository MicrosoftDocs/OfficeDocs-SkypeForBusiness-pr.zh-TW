---
title: 修改商務用 Skype Server 中的會議原則
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
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 摘要：瞭解如何在商務用 Skype Server 中修改會議原則。
ms.openlocfilehash: 6bbba82c9785e074da492eb66cbdd943dc0cea35
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119422"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="0bc81-103">修改商務用 Skype Server 中的會議原則</span><span class="sxs-lookup"><span data-stu-id="0bc81-103">Modify conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="0bc81-104">**摘要：** 瞭解如何在商務用 Skype Server 中修改會議原則。</span><span class="sxs-lookup"><span data-stu-id="0bc81-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="0bc81-105">您可以使用商務用 Skype Server 控制台或使用商務用 Skype Server 管理命令介面，修改會議原則。</span><span class="sxs-lookup"><span data-stu-id="0bc81-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0bc81-106">使用商務用 Skype Server 控制台修改會議原則</span><span class="sxs-lookup"><span data-stu-id="0bc81-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="0bc81-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="0bc81-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="0bc81-108">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="0bc81-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0bc81-109">在左導覽列中，按一下 [ **會議**]，然後按一下 [ **會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="0bc81-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="0bc81-110">在會議原則清單中，按一下您要變更的原則，按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="0bc81-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="0bc81-111">在 [ **編輯會議原則**] 中，修改原則名稱以外的任何原則設定，但無法修改。</span><span class="sxs-lookup"><span data-stu-id="0bc81-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="0bc81-112">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="0bc81-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0bc81-113">使用商務用 Skype Server 管理命令介面來修改會議原則</span><span class="sxs-lookup"><span data-stu-id="0bc81-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="0bc81-114">若要修改會議原則，請使用 **Set-CsConferencingPolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0bc81-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="0bc81-115">下列範例會修改會議原則 SalesConferencingPolicy 的屬性值。</span><span class="sxs-lookup"><span data-stu-id="0bc81-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="0bc81-116">此命令會將 AllowConferenceRecording 屬性的值設定為 False：</span><span class="sxs-lookup"><span data-stu-id="0bc81-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="0bc81-117">如需詳細資訊，包括完整的語法及參數清單，請參閱 [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="0bc81-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
