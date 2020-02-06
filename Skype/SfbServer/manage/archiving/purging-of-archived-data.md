---
title: 在商務用 Skype Server 中管理已歸檔資料的清除
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
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 摘要：瞭解如何管理商務用 Skype Server 的存檔資料清除。
ms.openlocfilehash: 7953c6085183e3ace0e395f0c8751897acd49380
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818875"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a><span data-ttu-id="cea87-103">在商務用 Skype Server 中管理已歸檔資料的清除</span><span class="sxs-lookup"><span data-stu-id="cea87-103">Manage purging of archived data in Skype for Business Server</span></span>

<span data-ttu-id="cea87-104">**摘要：** 瞭解如何管理商務用 Skype Server 的存檔資料清除。</span><span class="sxs-lookup"><span data-stu-id="cea87-104">**Summary:** Learn how to manage purging of archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="cea87-105">存檔資料庫不是用於長期保留，商務用 Skype 伺服器不會提供電子探索（搜尋）方案來儲存已歸檔的資料，因此需要將資料移到其他儲存空間。</span><span class="sxs-lookup"><span data-stu-id="cea87-105">The Archiving database is not intended for long-term retention, and Skype for Business Server does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="cea87-106">商務用 Skype 伺服器提供會話匯出工具，可供您用來將存檔的資料匯出至可搜尋的腳本。</span><span class="sxs-lookup"><span data-stu-id="cea87-106">Skype for Business Server provides a session export tool that you can use to export archived data into searchable transcripts.</span></span> <span data-ttu-id="cea87-107">您必須定義何時清除封存和匯出的資料。</span><span class="sxs-lookup"><span data-stu-id="cea87-107">You need to define when to purge archived and exported data.</span></span> 
  
<span data-ttu-id="cea87-108">如需使用**Export CsArchivingData** Cmdlet 匯出資料的詳細資訊，請參閱[在商務用 Skype Server 中匯出封存的資料](export-archived-data.md)。</span><span class="sxs-lookup"><span data-stu-id="cea87-108">For more information about exporting data by using the **Export-CsArchivingData** cmdlet, see [Export archived data in Skype for Business Server](export-archived-data.md).</span></span>
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a><span data-ttu-id="cea87-109">使用 [控制台] 管理資料清除</span><span class="sxs-lookup"><span data-stu-id="cea87-109">Manage purging of data by using the Control Panel</span></span>

<span data-ttu-id="cea87-110">若要使用 [控制台] 管理已封存的資料，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="cea87-110">To manage purging of archived data by using the Control Panel:</span></span>
  
1. <span data-ttu-id="cea87-111">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="cea87-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="cea87-112">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="cea87-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="cea87-113">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。</span><span class="sxs-lookup"><span data-stu-id="cea87-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="cea87-114">在歸檔設定清單中，按一下適當的全域、網站或池設定的名稱，按一下 [**編輯**]，按一下 [**顯示詳細資料**]，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="cea87-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="cea87-115">若要啟用清除，請選取 [**允許清除封存資料**] 核取方塊，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="cea87-115">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
    
     - <span data-ttu-id="cea87-116">若要清除所有記錄，請按一下 [**清除匯出的封存資料]，並儲存已儲存的存檔資料（天數）**，然後指定天數。</span><span class="sxs-lookup"><span data-stu-id="cea87-116">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="cea87-117">若只要清除已匯出的資料，請按一下 [**僅清除匯出的存檔資料**]。</span><span class="sxs-lookup"><span data-stu-id="cea87-117">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
   - <span data-ttu-id="cea87-118">若要停用清除，請清除 [**允許清除封存資料**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="cea87-118">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>
    
5. <span data-ttu-id="cea87-119">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cea87-119">Click **Commit**.</span></span>
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a><span data-ttu-id="cea87-120">使用 Windows PowerShell 管理資料清除</span><span class="sxs-lookup"><span data-stu-id="cea87-120">Manage purging of data by using Windows PowerShell</span></span>

<span data-ttu-id="cea87-121">您可以使用下列 Windows PowerShell Cmdlet 來管理封存的資料清除：</span><span class="sxs-lookup"><span data-stu-id="cea87-121">You can manage purging of archived data by using the following Windows PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="cea87-122">**CsArchivingConfiguration** Cmdlet 與 EnablePurging 參數可讓您啟用或停用清除已封存的資料。</span><span class="sxs-lookup"><span data-stu-id="cea87-122">**Set-CsArchivingConfiguration** cmdlet with the EnablePurging parameter lets you enable or disable purging of archived data.</span></span>
    
- <span data-ttu-id="cea87-123">**Invoke-CsArchivingDatabasePurge**可讓您從封存資料庫手動清除記錄。</span><span class="sxs-lookup"><span data-stu-id="cea87-123">**Invoke-CsArchivingDatabasePurge** lets you manually purge records from the Archiving database.</span></span>
    
<span data-ttu-id="cea87-124">例如，下列命令可讓您清除所有封存的資料。</span><span class="sxs-lookup"><span data-stu-id="cea87-124">For example, the following command enables the purging of all archived data.</span></span> <span data-ttu-id="cea87-125">執行此命令之後，商務用 Skype Server 將清除早于指定的 KeepArchivingDataForDays 參數值的所有封存記錄。</span><span class="sxs-lookup"><span data-stu-id="cea87-125">After this command is run, Skype for Business Server will purge all archiving records older than the value specified for the KeepArchivingDataForDays parameter.</span></span> 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

<span data-ttu-id="cea87-126">下列命令會限制清除到已匯出到資料檔之已歸檔記錄（使用**Export CSArchivingData** Cmdlet）。</span><span class="sxs-lookup"><span data-stu-id="cea87-126">The following command limits purging to archived records that have been exported to a data file (by using the **Export-CSArchivingData** cmdlet).</span></span> <span data-ttu-id="cea87-127">您也必須將 PurgeExportedArchivesOnly 參數設定為 True （$True）：</span><span class="sxs-lookup"><span data-stu-id="cea87-127">You must also set the PurgeExportedArchivesOnly parameter to True ($True):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

<span data-ttu-id="cea87-128">執行此命令之後，商務用 Skype 伺服器將只會清除符合兩個準則的封存記錄：1）它們比指定給 KeepArchivingDataForDays 參數的值還舊;而且，2）它們已使用**Export CsArchivingData** Cmdlet 進行匯出。</span><span class="sxs-lookup"><span data-stu-id="cea87-128">After this command is run, Skype for Business Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the KeepArchivingDataForDays parameter; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>
  
<span data-ttu-id="cea87-129">若要停用自動清除封存記錄，請將 EnablePurging 參數設定為 False （$False）：</span><span class="sxs-lookup"><span data-stu-id="cea87-129">To disable the automated purging of archiving records, set the EnablePurging parameter to False ($False):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

<span data-ttu-id="cea87-130">下列範例使用**CsArchivingDatabasePurge** Cmdlet，在 atl-sql-001.contoso.com 上的存檔資料庫中，清除超過24小時的所有記錄。</span><span class="sxs-lookup"><span data-stu-id="cea87-130">The following example uses the **Invoke-CsArchivingDatabasePurge** cmdlet to purge all the records more than 24 hours old from the archiving database on atl-sql-001.contoso.com.</span></span> <span data-ttu-id="cea87-131">若要確保所有記錄都已刪除，包括尚未匯出的記錄，PurgeExportedArchivesOnly 參數會設定為 False （$False）：</span><span class="sxs-lookup"><span data-stu-id="cea87-131">To ensure that all the records are deleted, including records that have not been exported, the PurgeExportedArchivesOnly parameter is set to False ($False):</span></span>
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
