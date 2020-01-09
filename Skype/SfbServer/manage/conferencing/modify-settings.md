---
title: 在商務用 Skype Server 中修改會議設定設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 摘要：瞭解如何在商務用 Skype Server 中修改會議設定設定。
ms.openlocfilehash: 2e9d8a737a2bfc48cdcbe39540a22e4c236003b3
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992850"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="0f22b-103">在商務用 Skype Server 中修改會議設定設定</span><span class="sxs-lookup"><span data-stu-id="0f22b-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="0f22b-104">**摘要：** 瞭解如何在商務用 Skype Server 中修改會議設定設定。</span><span class="sxs-lookup"><span data-stu-id="0f22b-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="0f22b-105">您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server Management Shell 來修改會議設定設定。</span><span class="sxs-lookup"><span data-stu-id="0f22b-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0f22b-106">使用商務用 Skype Server [控制台] 修改會議設定設定</span><span class="sxs-lookup"><span data-stu-id="0f22b-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="0f22b-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="0f22b-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="0f22b-108">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="0f22b-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0f22b-109">在左側導覽列中，按一下 [**會議**]，然後按一下 [**會議配置**]。</span><span class="sxs-lookup"><span data-stu-id="0f22b-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="0f22b-110">在會議配置清單中，按一下您要變更的設定，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="0f22b-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="0f22b-111">在 [**編輯會議**設定] 中，修改任何設定的設定，除了不能修改的配置名稱。</span><span class="sxs-lookup"><span data-stu-id="0f22b-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="0f22b-112">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f22b-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0f22b-113">使用商務用 Skype Server Management Shell 來修改會議設定設定</span><span class="sxs-lookup"><span data-stu-id="0f22b-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="0f22b-114">若要修改會議設定設定，請使用**CsMeetingConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0f22b-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="0f22b-115">下列範例所示的命令會修改指派給雷德蒙者網站（身分識別網站：雷蒙德）的會議設定設定。</span><span class="sxs-lookup"><span data-stu-id="0f22b-115">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond).</span></span> <span data-ttu-id="0f22b-116">在這種情況下，DesignateAsPresenter 屬性的值會設定為 [所有人]：</span><span class="sxs-lookup"><span data-stu-id="0f22b-116">In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="0f22b-117">如需詳細資訊（包括完整的參數清單），請參閱[設定 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="0f22b-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

