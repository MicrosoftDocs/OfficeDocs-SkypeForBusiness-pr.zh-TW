---
title: 在商務用 Skype Server 中刪除封存配置
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
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 摘要：瞭解如何在商務用 Skype Server 中刪除存檔設定。
ms.openlocfilehash: 82415e2cac7293d991280c3fcee6e64d684f5c26
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818935"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="c6bac-103">在商務用 Skype Server 中刪除封存配置</span><span class="sxs-lookup"><span data-stu-id="c6bac-103">Delete an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="c6bac-104">**摘要：** 瞭解如何在商務用 Skype Server 中刪除封存配置。</span><span class="sxs-lookup"><span data-stu-id="c6bac-104">**Summary:** Learn how to delete an archiving configuration in Skype for Business Server.</span></span>
  
<span data-ttu-id="c6bac-105">您可以刪除網站配置或池設定，但無法刪除全域設定。</span><span class="sxs-lookup"><span data-stu-id="c6bac-105">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="c6bac-106">如果您刪除全域設定，系統會自動將其重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="c6bac-106">If you delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a><span data-ttu-id="c6bac-107">使用 [控制台] 刪除封存配置</span><span class="sxs-lookup"><span data-stu-id="c6bac-107">Delete an archiving configuration by using the Control Panel</span></span>

<span data-ttu-id="c6bac-108">若要使用 [控制] 面板刪除封存配置：</span><span class="sxs-lookup"><span data-stu-id="c6bac-108">To delete an archiving configuration by using the Control Panel:</span></span>
  
1. <span data-ttu-id="c6bac-109">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c6bac-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="c6bac-110">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="c6bac-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c6bac-111">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。</span><span class="sxs-lookup"><span data-stu-id="c6bac-111">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="c6bac-112">在封存配置清單中，按一下您要刪除的網站或池設定，按一下 [**編輯**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="c6bac-112">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c6bac-113">您也可以按一下全域設定，但如果您想要將全域設定重設為預設值，請選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="c6bac-113">You can also click the Global configuration, but choose this option only if you want to reset the Global configuration to the default values.</span></span> 
  
5. <span data-ttu-id="c6bac-114">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c6bac-114">Click **Commit**.</span></span>
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a><span data-ttu-id="c6bac-115">使用 Windows PowerShell 刪除封存配置</span><span class="sxs-lookup"><span data-stu-id="c6bac-115">Delete an archiving configuration by using Windows PowerShell</span></span>

<span data-ttu-id="c6bac-116">您也可以使用**CsArchivingConfiguration** Cmdlet 刪除封存配置。</span><span class="sxs-lookup"><span data-stu-id="c6bac-116">You can also delete an archiving configuration by using the **Remove-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="c6bac-117">例如，下列命令會移除套用至雷德蒙者網站的存檔設定設定。</span><span class="sxs-lookup"><span data-stu-id="c6bac-117">For example, the following command removes the archiving configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="c6bac-118">刪除網站範圍中設定的原則後，由全域存檔原則會自動控制先前由網站原則管理的使用者：</span><span class="sxs-lookup"><span data-stu-id="c6bac-118">When a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="c6bac-119">下列命令會移除所有已套用至服務範圍的存檔設定：</span><span class="sxs-lookup"><span data-stu-id="c6bac-119">The following command removes all the archiving configuration settings applied to the service scope:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

<span data-ttu-id="c6bac-120">[下一步] 命令會移除 Exchange 封存已停用的所有存檔設定：</span><span class="sxs-lookup"><span data-stu-id="c6bac-120">The next command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

<span data-ttu-id="c6bac-121">您也可以使用**CsArchivingConfiguration** Cmdlet，將全域設定重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="c6bac-121">You can also use the **Remove-CsArchivingConfiguration** cmdlet to reset the global settings to default values.</span></span> <span data-ttu-id="c6bac-122">例如，假設您已在全域層級啟用 IM 會話存檔;下列命令會將值重設為預設值（無），這會停用全域層級的存檔：</span><span class="sxs-lookup"><span data-stu-id="c6bac-122">For example, suppose you have enabled IM session archiving at the global level; the following command will reset the value to the default of None, which will disable archiving at the global level:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

<span data-ttu-id="c6bac-123">如需詳細資訊，請參閱[Remove CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="c6bac-123">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
