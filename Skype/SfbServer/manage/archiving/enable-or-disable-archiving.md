---
title: 啟用或停用商務用 Skype Server 中的封存
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
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 摘要：瞭解如何啟用或停用商務用 Skype Server 中的封存。
ms.openlocfilehash: 6d8f6f24bd4b10f7d33a00e218a494d6e8a823d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817593"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a><span data-ttu-id="e8a37-103">啟用或停用商務用 Skype Server 中的封存</span><span class="sxs-lookup"><span data-stu-id="e8a37-103">Enable or disable archiving in Skype for Business Server</span></span>

<span data-ttu-id="e8a37-104">**摘要：** 瞭解如何啟用或停用商務用 Skype Server 中的封存。</span><span class="sxs-lookup"><span data-stu-id="e8a37-104">**Summary:** Learn how to enable or disable archiving in Skype for Business Server.</span></span>
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a><span data-ttu-id="e8a37-105">使用控制台啟用或停用封存</span><span class="sxs-lookup"><span data-stu-id="e8a37-105">Enable or disable archiving by using the Control Panel</span></span>

1. <span data-ttu-id="e8a37-106">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e8a37-106">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="e8a37-107">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="e8a37-107">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e8a37-108">在左導覽列中 **，按一下 [\*\*\*\*監視與** 封存]，然後按一下 [封存設定]。</span><span class="sxs-lookup"><span data-stu-id="e8a37-108">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="e8a37-109">從封存設定清單中選取適當的全域、網站或集區設定，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e8a37-109">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="e8a37-110">若只要啟用立即訊息 (IM) 工作階段的封存，請按一下 **[封存 IM 工作階段]**。</span><span class="sxs-lookup"><span data-stu-id="e8a37-110">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="e8a37-111">若要同時啟用 IM 會話和會議的封存，請按一下 [封存 **im 和會議會話**]。</span><span class="sxs-lookup"><span data-stu-id="e8a37-111">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
   - <span data-ttu-id="e8a37-112">若要停用設定的封存，請按一下 [ **停** 用封存]。</span><span class="sxs-lookup"><span data-stu-id="e8a37-112">To disable archiving for the configuration, click **Disable archiving**.</span></span>
    
5. <span data-ttu-id="e8a37-113">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="e8a37-113">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a><span data-ttu-id="e8a37-114">使用 Windows PowerShell 啟用或停用封存</span><span class="sxs-lookup"><span data-stu-id="e8a37-114">Enable or disable archiving by using Windows PowerShell</span></span>

<span data-ttu-id="e8a37-115">您也可以使用 **get-csarchivingconfiguration** Cmdlet 來啟用或停用封存。</span><span class="sxs-lookup"><span data-stu-id="e8a37-115">You can also enable or disable archiving by using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="e8a37-116">例如，下列命令會修改所有的封存設定設定，以便只封存 IM 會話。</span><span class="sxs-lookup"><span data-stu-id="e8a37-116">For example, the following command modifies the all of the archiving configuration settings so that only IM sessions are archived.</span></span> <span data-ttu-id="e8a37-117">此命令會呼叫不含任何參數的 **Get-CsArchivingConfiguration** Cmdlet，以傳回組織目前使用的所有封存設定設定。</span><span class="sxs-lookup"><span data-stu-id="e8a37-117">The command calls the **Get-CsArchivingConfiguration** cmdlet without any parameters in order to return all the archiving configuration settings currently in use in the organization.</span></span> <span data-ttu-id="e8a37-118">然後，此集合會管線傳送至 **Where-Object** Cmdlet，該指令程式只會選取 EnableArchiving 屬性等於 (-eq) "ImAndWebConf" 的設定。</span><span class="sxs-lookup"><span data-stu-id="e8a37-118">This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableArchiving property is equal to (-eq) "ImAndWebConf".</span></span> <span data-ttu-id="e8a37-119">然後將篩選後的集合管線傳送至 **get-csarchivingconfiguration 指令程式** ，該指令程式會採用集合中的每個專案，並將 EnableArchiving 的值變更為 "ImOnly"：</span><span class="sxs-lookup"><span data-stu-id="e8a37-119">The filtered collection is then piped to the **Set-CsArchivingConfiguration** cmdlet, which takes each item in the collection and changes the value of EnableArchiving to "ImOnly":</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
