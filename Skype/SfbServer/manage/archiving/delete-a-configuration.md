---
title: 在商務用 Skype Server 中刪除封存設定
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
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 摘要：瞭解如何在商務用 Skype Server 中刪除封存設定。
ms.openlocfilehash: 43913485ce18660b6c7fa7ce747ceeaaebd49923
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095407"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="39f18-103">在商務用 Skype Server 中刪除封存設定</span><span class="sxs-lookup"><span data-stu-id="39f18-103">Delete an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="39f18-104">**摘要：** 瞭解如何在商務用 Skype Server 中刪除封存設定。</span><span class="sxs-lookup"><span data-stu-id="39f18-104">**Summary:** Learn how to delete an archiving configuration in Skype for Business Server.</span></span>
  
<span data-ttu-id="39f18-105">您可以刪除網站設定或集區設定，但無法刪除全域設定。</span><span class="sxs-lookup"><span data-stu-id="39f18-105">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="39f18-106">如果您刪除全域設定，它會自動重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="39f18-106">If you delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a><span data-ttu-id="39f18-107">使用控制台刪除封存設定</span><span class="sxs-lookup"><span data-stu-id="39f18-107">Delete an archiving configuration by using the Control Panel</span></span>

<span data-ttu-id="39f18-108">若要使用 [控制台] 刪除封存設定，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="39f18-108">To delete an archiving configuration by using the Control Panel:</span></span>
  
1. <span data-ttu-id="39f18-109">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="39f18-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="39f18-110">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="39f18-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="39f18-111">在左導覽列中 **，按一下 [\*\*\*\*監視與** 封存]，然後按一下 [封存設定]。</span><span class="sxs-lookup"><span data-stu-id="39f18-111">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="39f18-112">在封存設定清單中，按一下您要刪除的網站或集區設定，然後按一下 [ **編輯**]，再按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="39f18-112">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="39f18-113">您也可以按一下 [通用] 設定，但只有在您想要將全域設定重設為預設值時，才選擇此選項。</span><span class="sxs-lookup"><span data-stu-id="39f18-113">You can also click the Global configuration, but choose this option only if you want to reset the Global configuration to the default values.</span></span> 
  
5. <span data-ttu-id="39f18-114">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="39f18-114">Click **Commit**.</span></span>
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a><span data-ttu-id="39f18-115">使用 Windows PowerShell 刪除封存設定</span><span class="sxs-lookup"><span data-stu-id="39f18-115">Delete an archiving configuration by using Windows PowerShell</span></span>

<span data-ttu-id="39f18-116">您也可以使用 **Remove-CsArchivingConfiguration** Cmdlet 刪除封存設定。</span><span class="sxs-lookup"><span data-stu-id="39f18-116">You can also delete an archiving configuration by using the **Remove-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="39f18-117">例如，下列命令會移除套用至 Redmond 網站的封存設定設定。</span><span class="sxs-lookup"><span data-stu-id="39f18-117">For example, the following command removes the archiving configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="39f18-118">在刪除網站範圍內設定的原則時，以前由網站原則管理的使用者將會自動受全域封存原則管理：</span><span class="sxs-lookup"><span data-stu-id="39f18-118">When a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="39f18-119">下列命令會移除套用至服務範圍的所有封存設定：</span><span class="sxs-lookup"><span data-stu-id="39f18-119">The following command removes all the archiving configuration settings applied to the service scope:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

<span data-ttu-id="39f18-120">下一個命令會移除已停用 Exchange 封存的所有封存設定設定：</span><span class="sxs-lookup"><span data-stu-id="39f18-120">The next command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

<span data-ttu-id="39f18-121">您也可以使用 **Remove-CsArchivingConfiguration** Cmdlet，將全域設定重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="39f18-121">You can also use the **Remove-CsArchivingConfiguration** cmdlet to reset the global settings to default values.</span></span> <span data-ttu-id="39f18-122">例如，假設您已在全域層級啟用 IM 會話封存，則為下列命令會將值重設為預設值 [無]，這樣會停用全域層級的封存：</span><span class="sxs-lookup"><span data-stu-id="39f18-122">For example, suppose you have enabled IM session archiving at the global level; the following command will reset the value to the default of None, which will disable archiving at the global level:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

<span data-ttu-id="39f18-123">如需詳細資訊，請參閱 [Remove-CsArchivingConfiguration](/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="39f18-123">For more information, see the help topic for the [Remove-CsArchivingConfiguration](/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>