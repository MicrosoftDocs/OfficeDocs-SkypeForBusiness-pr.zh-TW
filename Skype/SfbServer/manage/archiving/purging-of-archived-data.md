---
title: 在商務用 Skype Server 中管理已封存資料的清除
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
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 摘要：瞭解如何管理商務用 Skype Server 的封存資料清除。
ms.openlocfilehash: aecc78f84b3cd4b745a96e534535c98c1739c156
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828533"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a><span data-ttu-id="b7850-103">在商務用 Skype Server 中管理已封存資料的清除</span><span class="sxs-lookup"><span data-stu-id="b7850-103">Manage purging of archived data in Skype for Business Server</span></span>

<span data-ttu-id="b7850-104">**摘要：** 瞭解如何管理商務用 Skype Server 的封存資料清除。</span><span class="sxs-lookup"><span data-stu-id="b7850-104">**Summary:** Learn how to manage purging of archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="b7850-105">封存資料庫不適用於長期保留，但商務用 Skype 伺服器不會提供電子探索 (搜尋) 的封存資料的解決方案，因此資料需要移至其他儲存區。</span><span class="sxs-lookup"><span data-stu-id="b7850-105">The Archiving database is not intended for long-term retention, and Skype for Business Server does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="b7850-106">商務用 Skype 伺服器提供會話匯出工具，可供您用來將封存的資料匯出至可搜尋的記錄。</span><span class="sxs-lookup"><span data-stu-id="b7850-106">Skype for Business Server provides a session export tool that you can use to export archived data into searchable transcripts.</span></span> <span data-ttu-id="b7850-107">您必須定義何時清除已封存及匯出的資料。</span><span class="sxs-lookup"><span data-stu-id="b7850-107">You need to define when to purge archived and exported data.</span></span> 
  
<span data-ttu-id="b7850-108">如需使用 **Export-CsArchivingData** Cmdlet 匯出資料的詳細資訊，請參閱 [在商務用 Skype Server 中匯出封存的資料](export-archived-data.md)。</span><span class="sxs-lookup"><span data-stu-id="b7850-108">For more information about exporting data by using the **Export-CsArchivingData** cmdlet, see [Export archived data in Skype for Business Server](export-archived-data.md).</span></span>
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a><span data-ttu-id="b7850-109">使用控制台管理資料清除</span><span class="sxs-lookup"><span data-stu-id="b7850-109">Manage purging of data by using the Control Panel</span></span>

<span data-ttu-id="b7850-110">若要使用 [控制台] 管理封存資料的清除，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b7850-110">To manage purging of archived data by using the Control Panel:</span></span>
  
1. <span data-ttu-id="b7850-111">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b7850-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="b7850-112">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="b7850-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="b7850-113">在左導覽列中 **，按一下 [\*\*\*\*監視與** 封存]，然後按一下 [封存設定]。</span><span class="sxs-lookup"><span data-stu-id="b7850-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="b7850-114">按一下封存組態清單中適當的全域、網站或集區組態名稱，再依序按一下 [編輯] 和 [顯示詳細資料]，然後執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="b7850-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="b7850-115">若要啟用清除，請選取 **[啟用封存資料的清除]** 核取方塊，然後執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="b7850-115">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
    
     - <span data-ttu-id="b7850-116">若要清除所有記錄，請按一下 **[在最大持續期限 (天) 後清除匯出的封存資料和儲存的封存資料]**，然後指定天數。</span><span class="sxs-lookup"><span data-stu-id="b7850-116">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="b7850-117">若只要清除已匯出的資料，請按一下 **[只清除匯出的封存資料]**。</span><span class="sxs-lookup"><span data-stu-id="b7850-117">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
   - <span data-ttu-id="b7850-118">若要停用清除，請清除 **[啟用封存資料的清除]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b7850-118">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>
    
5. <span data-ttu-id="b7850-119">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="b7850-119">Click **Commit**.</span></span>
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a><span data-ttu-id="b7850-120">使用 Windows PowerShell 管理資料清除</span><span class="sxs-lookup"><span data-stu-id="b7850-120">Manage purging of data by using Windows PowerShell</span></span>

<span data-ttu-id="b7850-121">您可以使用下列 Windows PowerShell Cmdlet 來管理封存資料的清除：</span><span class="sxs-lookup"><span data-stu-id="b7850-121">You can manage purging of archived data by using the following Windows PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="b7850-122">**Set-get-csarchivingconfiguration** Cmdlet 搭配 EnablePurging 參數可讓您啟用或停用封存資料的清除。</span><span class="sxs-lookup"><span data-stu-id="b7850-122">**Set-CsArchivingConfiguration** cmdlet with the EnablePurging parameter lets you enable or disable purging of archived data.</span></span>
    
- <span data-ttu-id="b7850-123">**Invoke-CsArchivingDatabasePurge** 可讓您手動清除封存資料庫中的記錄。</span><span class="sxs-lookup"><span data-stu-id="b7850-123">**Invoke-CsArchivingDatabasePurge** lets you manually purge records from the Archiving database.</span></span>
    
<span data-ttu-id="b7850-124">例如，下列命令可啟用所有封存資料的清除。</span><span class="sxs-lookup"><span data-stu-id="b7850-124">For example, the following command enables the purging of all archived data.</span></span> <span data-ttu-id="b7850-125">在執行此命令之後，商務用 Skype 伺服器將會清除超過為 KeepArchivingDataForDays 參數指定之值的所有封存記錄。</span><span class="sxs-lookup"><span data-stu-id="b7850-125">After this command is run, Skype for Business Server will purge all archiving records older than the value specified for the KeepArchivingDataForDays parameter.</span></span> 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

<span data-ttu-id="b7850-126">下列命令會限制使用 **Export-CSArchivingData** Cmdlet) ，清除已匯出至資料檔案 (已封存記錄。</span><span class="sxs-lookup"><span data-stu-id="b7850-126">The following command limits purging to archived records that have been exported to a data file (by using the **Export-CSArchivingData** cmdlet).</span></span> <span data-ttu-id="b7850-127">您也必須將 PurgeExportedArchivesOnly 參數設定為 True ($True) ：</span><span class="sxs-lookup"><span data-stu-id="b7850-127">You must also set the PurgeExportedArchivesOnly parameter to True ($True):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

<span data-ttu-id="b7850-128">在執行這個命令之後，商務用 Skype 伺服器只會清除符合兩個準則的封存記錄： 1) 這些記錄會舊于 KeepArchivingDataForDays 參數所指定的值。而且，2) 使用 **Export-CsArchivingData** Cmdlet 匯出。</span><span class="sxs-lookup"><span data-stu-id="b7850-128">After this command is run, Skype for Business Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the KeepArchivingDataForDays parameter; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>
  
<span data-ttu-id="b7850-129">若要停用自動清除封存記錄，請將 EnablePurging 參數設定為 False ($False) ：</span><span class="sxs-lookup"><span data-stu-id="b7850-129">To disable the automated purging of archiving records, set the EnablePurging parameter to False ($False):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

<span data-ttu-id="b7850-130">下列範例會使用 **Invoke-CsArchivingDatabasePurge** Cmdlet，從 atl-sql-001.contoso.com 上的封存資料庫中清除超過24小時的所有記錄。</span><span class="sxs-lookup"><span data-stu-id="b7850-130">The following example uses the **Invoke-CsArchivingDatabasePurge** cmdlet to purge all the records more than 24 hours old from the archiving database on atl-sql-001.contoso.com.</span></span> <span data-ttu-id="b7850-131">為了確保刪除所有記錄（包括尚未匯出的記錄），PurgeExportedArchivesOnly 參數會設定為 False ($False) ：</span><span class="sxs-lookup"><span data-stu-id="b7850-131">To ensure that all the records are deleted, including records that have not been exported, the PurgeExportedArchivesOnly parameter is set to False ($False):</span></span>
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
