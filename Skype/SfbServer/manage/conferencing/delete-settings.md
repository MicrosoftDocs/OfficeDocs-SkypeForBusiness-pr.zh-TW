---
title: 在商務用 Skype Server 中刪除會議配置設定
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
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 摘要：瞭解如何在商務用 Skype Server 中刪除會議配置設定。
ms.openlocfilehash: b0c739f0149b4e28ca23df1437caab0505e1118d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119492"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="c3058-103">在商務用 Skype Server 中刪除會議配置設定</span><span class="sxs-lookup"><span data-stu-id="c3058-103">Delete meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="c3058-104">**摘要：** 瞭解如何在商務用 Skype Server 中刪除會議配置設定。</span><span class="sxs-lookup"><span data-stu-id="c3058-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="c3058-105">您可以使用商務用 Skype Server 控制台或使用商務用 Skype Server 管理命令介面來刪除會議配置設定。</span><span class="sxs-lookup"><span data-stu-id="c3058-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="c3058-106">您可以刪除網站或使用者設定，但無法刪除全域設定。</span><span class="sxs-lookup"><span data-stu-id="c3058-106">You can delete a site or user configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="c3058-107">如果您嘗試刪除全域設定，它會自動重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="c3058-107">If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c3058-108">使用商務用 Skype Server 控制台刪除會議配置設定</span><span class="sxs-lookup"><span data-stu-id="c3058-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c3058-109">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c3058-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="c3058-110">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="c3058-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="c3058-111">在左導覽列中，按一下 [ **會議**]，然後按一下 [ **會議** 設定]。</span><span class="sxs-lookup"><span data-stu-id="c3058-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="c3058-112">在會議設定清單中，按一下您要刪除的網站或集區設定，然後按一下 [ **編輯**]，再按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="c3058-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c3058-113">使用商務用 Skype Server 管理命令介面刪除會議設定設定</span><span class="sxs-lookup"><span data-stu-id="c3058-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="c3058-114">若要刪除會議設定，請使用 **Remove-CsMeetingConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c3058-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="c3058-115">下列命令會移除套用至 Redmond 網站的會議設定設定：</span><span class="sxs-lookup"><span data-stu-id="c3058-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="c3058-116">下一個命令會移除所有套用至網站範圍的會議設定設定：</span><span class="sxs-lookup"><span data-stu-id="c3058-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="c3058-117">如需詳細資訊，包括完整的參數清單，請參閱 [Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c3058-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
