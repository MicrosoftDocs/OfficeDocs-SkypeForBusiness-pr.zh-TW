---
title: 在商務用 Skype Server 中啟用或停用封存
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
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 摘要：瞭解如何在商務用 Skype Server 中啟用或停用封存。
ms.openlocfilehash: 8c970dba9a76abdb0c9417a5da5c7aa642fa059c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818915"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a><span data-ttu-id="313e1-103">在商務用 Skype Server 中啟用或停用封存</span><span class="sxs-lookup"><span data-stu-id="313e1-103">Enable or disable archiving in Skype for Business Server</span></span>

<span data-ttu-id="313e1-104">**摘要：** 瞭解如何在商務用 Skype Server 中啟用或停用封存。</span><span class="sxs-lookup"><span data-stu-id="313e1-104">**Summary:** Learn how to enable or disable archiving in Skype for Business Server.</span></span>
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a><span data-ttu-id="313e1-105">使用 [控制台] 啟用或停用封存</span><span class="sxs-lookup"><span data-stu-id="313e1-105">Enable or disable archiving by using the Control Panel</span></span>

1. <span data-ttu-id="313e1-106">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="313e1-106">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="313e1-107">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="313e1-107">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="313e1-108">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。</span><span class="sxs-lookup"><span data-stu-id="313e1-108">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="313e1-109">從存檔設定清單中選取適當的全域、網站或池設定，按一下 [**編輯**]，按一下 [**顯示詳細資料**]，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="313e1-109">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="313e1-110">若要只針對立即訊息（IM）會話啟用封存，請按一下 [封存**IM 會話**]。</span><span class="sxs-lookup"><span data-stu-id="313e1-110">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="313e1-111">若要在 IM 會話與會議中啟用封存功能，請按一下 [封存**im 及會議會話**]。</span><span class="sxs-lookup"><span data-stu-id="313e1-111">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
   - <span data-ttu-id="313e1-112">若要停用存檔以進行設定，請按一下 [**停**用封存]。</span><span class="sxs-lookup"><span data-stu-id="313e1-112">To disable archiving for the configuration, click **Disable archiving**.</span></span>
    
5. <span data-ttu-id="313e1-113">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="313e1-113">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a><span data-ttu-id="313e1-114">使用 Windows PowerShell 啟用或停用封存</span><span class="sxs-lookup"><span data-stu-id="313e1-114">Enable or disable archiving by using Windows PowerShell</span></span>

<span data-ttu-id="313e1-115">您也可以使用**CsArchivingConfiguration** Cmdlet 來啟用或停用封存。</span><span class="sxs-lookup"><span data-stu-id="313e1-115">You can also enable or disable archiving by using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="313e1-116">例如，下列命令會修改所有的存檔設定設定，以便只封存 IM 會話。</span><span class="sxs-lookup"><span data-stu-id="313e1-116">For example, the following command modifies the all of the archiving configuration settings so that only IM sessions are archived.</span></span> <span data-ttu-id="313e1-117">此命令會呼叫無任何參數的**CsArchivingConfiguration** Cmdlet，以傳回目前在組織中使用的所有存檔設定設定。</span><span class="sxs-lookup"><span data-stu-id="313e1-117">The command calls the **Get-CsArchivingConfiguration** cmdlet without any parameters in order to return all the archiving configuration settings currently in use in the organization.</span></span> <span data-ttu-id="313e1-118">然後，該集合會以管道傳送到**物件**Cmdlet，該 Cmdlet 只會選取 EnableArchiving 屬性等於（-eq） "ImAndWebConf" 的那些設定。</span><span class="sxs-lookup"><span data-stu-id="313e1-118">This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableArchiving property is equal to (-eq) "ImAndWebConf".</span></span> <span data-ttu-id="313e1-119">篩選後的集合接著會傳送到**CsArchivingConfiguration** Cmdlet，這會採用集合中的每個專案，並將 EnableArchiving 的值變更為 "ImOnly"：</span><span class="sxs-lookup"><span data-stu-id="313e1-119">The filtered collection is then piped to the **Set-CsArchivingConfiguration** cmdlet, which takes each item in the collection and changes the value of EnableArchiving to "ImOnly":</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
