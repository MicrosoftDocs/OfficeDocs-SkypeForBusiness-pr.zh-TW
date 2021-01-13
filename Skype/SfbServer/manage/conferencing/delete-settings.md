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
ms.openlocfilehash: 418ce7418be5a09658626491121dd2e2b3542110
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828177"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="0c2d7-103">在商務用 Skype Server 中刪除會議配置設定</span><span class="sxs-lookup"><span data-stu-id="0c2d7-103">Delete meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="0c2d7-104">**摘要：** 瞭解如何在商務用 Skype Server 中刪除會議配置設定。</span><span class="sxs-lookup"><span data-stu-id="0c2d7-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="0c2d7-105">您可以使用商務用 Skype Server 控制台或使用商務用 Skype Server 管理命令介面來刪除會議配置設定。</span><span class="sxs-lookup"><span data-stu-id="0c2d7-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="0c2d7-106">您可以刪除網站或使用者設定，但無法刪除全域設定。</span><span class="sxs-lookup"><span data-stu-id="0c2d7-106">You can delete a site or user configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="0c2d7-107">如果您嘗試刪除全域設定，它會自動重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="0c2d7-107">If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0c2d7-108">使用商務用 Skype Server 控制台刪除會議配置設定</span><span class="sxs-lookup"><span data-stu-id="0c2d7-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="0c2d7-109">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="0c2d7-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="0c2d7-110">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="0c2d7-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0c2d7-111">在左導覽列中，按一下 [ **會議**]，然後按一下 [ **會議** 設定]。</span><span class="sxs-lookup"><span data-stu-id="0c2d7-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="0c2d7-112">在會議設定清單中，按一下您要刪除的網站或集區設定，然後按一下 [ **編輯**]，再按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="0c2d7-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0c2d7-113">使用商務用 Skype Server 管理命令介面刪除會議設定設定</span><span class="sxs-lookup"><span data-stu-id="0c2d7-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="0c2d7-114">若要刪除會議設定，請使用 **Remove-CsMeetingConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0c2d7-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="0c2d7-115">下列命令會移除套用至 Redmond 網站的會議設定設定：</span><span class="sxs-lookup"><span data-stu-id="0c2d7-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="0c2d7-116">下一個命令會移除所有套用至網站範圍的會議設定設定：</span><span class="sxs-lookup"><span data-stu-id="0c2d7-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="0c2d7-117">如需詳細資訊，包括完整的參數清單，請參閱 [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="0c2d7-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
  

