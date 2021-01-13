---
title: 修改商務用 Skype Server 中的會議設定設定
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
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 摘要：瞭解如何在商務用 Skype Server 中修改會議配置設定。
ms.openlocfilehash: 80ba12266ebc45fdae3256f5238ecf18415734c8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827993"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="8d762-103">修改商務用 Skype Server 中的會議設定設定</span><span class="sxs-lookup"><span data-stu-id="8d762-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="8d762-104">**摘要：** 瞭解如何在商務用 Skype Server 中修改會議配置設定。</span><span class="sxs-lookup"><span data-stu-id="8d762-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="8d762-105">您可以使用商務用 Skype Server 控制台或使用商務用 Skype Server 管理命令介面，修改會議設定設定。</span><span class="sxs-lookup"><span data-stu-id="8d762-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8d762-106">使用商務用 Skype Server 控制台修改會議配置設定</span><span class="sxs-lookup"><span data-stu-id="8d762-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8d762-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="8d762-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="8d762-108">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="8d762-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="8d762-109">在左導覽列中，按一下 [ **會議**]，然後按一下 [ **會議** 設定]。</span><span class="sxs-lookup"><span data-stu-id="8d762-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="8d762-110">在會議設定清單中，按一下您要變更的設定，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="8d762-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="8d762-111">在 [ **編輯會議** 設定] 中，修改設定名稱以外的任何設定，但無法修改。</span><span class="sxs-lookup"><span data-stu-id="8d762-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="8d762-112">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="8d762-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8d762-113">使用商務用 Skype Server 管理命令介面來修改會議設定設定</span><span class="sxs-lookup"><span data-stu-id="8d762-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="8d762-114">若要修改會議配置設定，請使用 **Set-CsMeetingConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8d762-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="8d762-115">下列範例所示的命令會修改指派給 Redmond 網站 ( 身分識別 site： Redmond) 的會議設定設定。</span><span class="sxs-lookup"><span data-stu-id="8d762-115">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond).</span></span> <span data-ttu-id="8d762-116">在此情況下，DesignateAsPresenter 屬性的值會設定為 [所有人]：</span><span class="sxs-lookup"><span data-stu-id="8d762-116">In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="8d762-117">如需詳細資訊，包括完整的參數清單，請參閱 [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="8d762-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

