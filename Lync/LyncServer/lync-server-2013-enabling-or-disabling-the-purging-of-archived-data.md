---
title: Lync Server 2013：啟用或停用封存資料的清除
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling the purging of archived data
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48183678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 308ba7b91fbe776ed49d72c54e2986ad95d080fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500940"
---
# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a><span data-ttu-id="b30b6-102">啟用或停用 Lync Server 2013 中的封存資料清除功能</span><span class="sxs-lookup"><span data-stu-id="b30b6-102">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b30b6-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b30b6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b30b6-104">在 [Lync Server 2013 控制台] 中，您可以使用封存設定來啟用及停用清除及設定清除的執行方式。</span><span class="sxs-lookup"><span data-stu-id="b30b6-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable purging and configure how purging is implemented.</span></span> <span data-ttu-id="b30b6-105">這包含下列封存組態：</span><span class="sxs-lookup"><span data-stu-id="b30b6-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="b30b6-106">當您部署 Lync Server 2013 時，預設會建立全域設定。</span><span class="sxs-lookup"><span data-stu-id="b30b6-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="b30b6-107">選用的網站層級和集區層級組態，可建立及用於指定針對特定網站或集區如何實作封存。</span><span class="sxs-lookup"><span data-stu-id="b30b6-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="b30b6-108">您一開始部署封存時會設定封存組態，但是在部署後可以變更、新增及刪除組態。</span><span class="sxs-lookup"><span data-stu-id="b30b6-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="b30b6-109">如需如何執行封存設定的詳細資訊，包括您可以指定哪些選項以及封存設定的階層，請參閱規劃檔、部署檔或作業檔中的封存 [如何在 Lync Server 2013 中運作](lync-server-2013-how-archiving-works.md) 。</span><span class="sxs-lookup"><span data-stu-id="b30b6-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b30b6-110">若要將封存用於位於 Lync Server 2013 的使用者，您必須設定封存原則，以指定是否啟用內部通訊、外部通訊或兩者的封存。</span><span class="sxs-lookup"><span data-stu-id="b30b6-110">To use archiving for users who are homed on Lync Server 2013 you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="b30b6-111">預設並沒有啟用內部或外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="b30b6-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="b30b6-112">以任何原則啟用封存之前，您應先為部署指定適用的封存組態，然後如上一節中所述，選用地針對網站與集區指定封存組態。</span><span class="sxs-lookup"><span data-stu-id="b30b6-112">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="b30b6-113">如需啟用封存的詳細資訊，請參閱部署檔中的設定 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync Server 2013</A> 中的封存原則。</span><span class="sxs-lookup"><span data-stu-id="b30b6-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="b30b6-114">如果您在部署封存後決定要使用 Microsoft Exchange 整合將封存資料和檔案儲存在 Exchange 2013 伺服器上，而且所有使用者都位於 Exchange 2013 伺服器上，則應該從拓撲中移除 SQL Server 資料庫設定。</span><span class="sxs-lookup"><span data-stu-id="b30b6-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="b30b6-115">您必須使用拓撲產生器來執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="b30b6-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="b30b6-116">如需詳細資訊，請參閱 Operations 檔中的 <A href="lync-server-2013-changing-archiving-database-options.md">變更 Lync Server 2013</A> 中的封存資料庫選項。</span><span class="sxs-lookup"><span data-stu-id="b30b6-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a><span data-ttu-id="b30b6-117">啟用或停用封存的清除功能</span><span class="sxs-lookup"><span data-stu-id="b30b6-117">To enable or disable purging for archiving</span></span>

1.  <span data-ttu-id="b30b6-118">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b30b6-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b30b6-119">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="b30b6-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b30b6-120">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="b30b6-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b30b6-121">在左導覽列中 **，按一下 [\*\*\*\*監視與**封存]，然後按一下 [封存設定]。</span><span class="sxs-lookup"><span data-stu-id="b30b6-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="b30b6-122">按一下封存組態清單中適當的全域、網站或集區組態名稱，再依序按一下 [編輯]\*\*\*\* 和 [顯示詳細資料]\*\*\*\*，然後執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="b30b6-122">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="b30b6-123">若要啟用清除，請選取 **[啟用封存資料的清除]** 核取方塊，然後執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="b30b6-123">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
        
          - <span data-ttu-id="b30b6-124">若要清除所有記錄，請按一下 **[在最大持續期限 (天) 後清除匯出的封存資料和儲存的封存資料]**，然後指定天數。</span><span class="sxs-lookup"><span data-stu-id="b30b6-124">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="b30b6-125">若只要清除已匯出的資料，請按一下 **[只清除匯出的封存資料]**。</span><span class="sxs-lookup"><span data-stu-id="b30b6-125">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
      - <span data-ttu-id="b30b6-126">若要停用清除，請清除 **[啟用封存資料的清除]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b30b6-126">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>

5.  <span data-ttu-id="b30b6-127">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="b30b6-127">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b30b6-128">使用 Windows PowerShell Cmdlet 來啟用或停用封存資料的清除</span><span class="sxs-lookup"><span data-stu-id="b30b6-128">Enabling or Disabling the Purging of Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b30b6-129">啟用和停用封存資料的自動清除可使用 Windows PowerShell 和 **get-csarchivingconfiguration** Cmdlet 來管理。</span><span class="sxs-lookup"><span data-stu-id="b30b6-129">Enabling and disabling the automated purging of archiving data can be managed by using Windows PowerShell and the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="b30b6-130">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b30b6-130">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b30b6-131">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="b30b6-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a><span data-ttu-id="b30b6-132">啟用所有封存資料的清除</span><span class="sxs-lookup"><span data-stu-id="b30b6-132">To enable the purging of all archiving data</span></span>

  - <span data-ttu-id="b30b6-133">若要啟用所有封存資料的清除，請將 **EnablePurging** 屬性設為 true ($True)。</span><span class="sxs-lookup"><span data-stu-id="b30b6-133">To enable the purging of all archiving data set the **EnablePurging** property to true ($True).</span></span> <span data-ttu-id="b30b6-134">例如：</span><span class="sxs-lookup"><span data-stu-id="b30b6-134">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    <span data-ttu-id="b30b6-135">在執行這個命令之後，Lync Server 會清除所有比指定的 **KeepArchivingDataForDays** 屬性值還舊的封存記錄。</span><span class="sxs-lookup"><span data-stu-id="b30b6-135">After this command is run, then every day Lync Server will purge all archiving records older than the value specified for the **KeepArchivingDataForDays** property.</span></span>

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a><span data-ttu-id="b30b6-136">僅啟用匯出的封存資料的清除</span><span class="sxs-lookup"><span data-stu-id="b30b6-136">To enable the purging only of exported archiving data</span></span>

  - <span data-ttu-id="b30b6-137">若要使用 [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) Cmdlet 來限制清除已匯出至資料檔案 (的封存記錄，) 您也必須將 PurgeExportedArchivesOnly 屬性設定為 True ($True) 。</span><span class="sxs-lookup"><span data-stu-id="b30b6-137">To limit purging to archiving records that have been exported to a data file (by using the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet) you must also set the PurgeExportedArchivesOnly property to True ($True).</span></span> <span data-ttu-id="b30b6-138">例如：</span><span class="sxs-lookup"><span data-stu-id="b30b6-138">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    <span data-ttu-id="b30b6-139">在執行這個命令之後，Lync Server 只會清除符合兩個準則的封存記錄： 1) 這些記錄會舊于 **KeepArchivingDataForDays** 屬性指定的值。而且，2) 使用 **Export-CsArchivingData** Cmdlet 匯出。</span><span class="sxs-lookup"><span data-stu-id="b30b6-139">After this command is run, Lync Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the **KeepArchivingDataForDays** property; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a><span data-ttu-id="b30b6-140">停用所有封存資料的清除</span><span class="sxs-lookup"><span data-stu-id="b30b6-140">To disable the purging of all archiving data</span></span>

  - <span data-ttu-id="b30b6-141">若要停用封存記錄的自動清除，請將 **EnablePurging** 屬性設為 False ($False)。</span><span class="sxs-lookup"><span data-stu-id="b30b6-141">To disable the automated purging of archiving records, set the **EnablePurging** property to False ($False).</span></span> <span data-ttu-id="b30b6-142">例如：</span><span class="sxs-lookup"><span data-stu-id="b30b6-142">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

<span data-ttu-id="b30b6-143">如需詳細資訊，包括清除封存資料的其他選項，請參閱 [get-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) 指令程式的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="b30b6-143">For more information, including additional options for purging archiving data, see the help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b30b6-144">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b30b6-144">See Also</span></span>


[<span data-ttu-id="b30b6-145">Lync Server 2013 中的封存運作方式</span><span class="sxs-lookup"><span data-stu-id="b30b6-145">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="b30b6-146">在 Lync Server 2013 中設定和指派封存原則</span><span class="sxs-lookup"><span data-stu-id="b30b6-146">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[<span data-ttu-id="b30b6-147">為您的組織、網站及集區管理 Lync Server 2013 中的封存設定選項</span><span class="sxs-lookup"><span data-stu-id="b30b6-147">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

