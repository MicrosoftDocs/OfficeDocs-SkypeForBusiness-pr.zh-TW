---
title: Lync Server 2013：建立封存設定以管理特定網站或集區的封存
description: Lync Server 2013：建立封存設定以管理特定網站或集區的封存。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating an Archiving configuration to manage Archiving for specific sites or pools
ms:assetid: c5c864a6-96c7-4bbb-ab7c-61eb1744246c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205251(v=OCS.15)
ms:contentKeyID: 48185361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ab19f2d8900693ef0fcb14d8f6d862b22c355bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563109"
---
# <a name="creating-an-archiving-configuration-in-lync-server-2013-to-manage-archiving-for-specific-sites-or-pools"></a><span data-ttu-id="c68dc-103">在 Lync Server 2013 中建立封存設定，以管理特定網站或集區的封存</span><span class="sxs-lookup"><span data-stu-id="c68dc-103">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c68dc-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c68dc-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c68dc-105">在 [Lync Server 2013 控制台] 中，您可以使用封存設定來控制如何在部署中實施封存。</span><span class="sxs-lookup"><span data-stu-id="c68dc-105">In Lync Server 2013 Control Panel, you use Archiving configurations to control how archiving is implemented in your deployment.</span></span> <span data-ttu-id="c68dc-106">這包含下列封存組態：</span><span class="sxs-lookup"><span data-stu-id="c68dc-106">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="c68dc-107">當您部署 Lync Server 2013 時，預設會建立全域設定。</span><span class="sxs-lookup"><span data-stu-id="c68dc-107">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="c68dc-108">選用的網站層級和集區層級組態，可建立及用於指定針對特定網站或集區如何實作封存。</span><span class="sxs-lookup"><span data-stu-id="c68dc-108">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="c68dc-109">您一開始部署封存時會設定封存組態，但是在部署後可以變更、新增及刪除組態。</span><span class="sxs-lookup"><span data-stu-id="c68dc-109">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="c68dc-110">如需如何執行封存設定的詳細資訊，包括您可以指定哪些選項以及封存設定的階層，請參閱規劃檔、部署檔或作業檔中的封存 [如何在 Lync Server 2013 中運作](lync-server-2013-how-archiving-works.md) 。</span><span class="sxs-lookup"><span data-stu-id="c68dc-110">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c68dc-111">若要使用封存，您必須設定封存原則，以指定是否啟用內部通訊、外部通訊或同時適用于 Lync Server 2013 的使用者的封存。</span><span class="sxs-lookup"><span data-stu-id="c68dc-111">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="c68dc-112">依據預設，都不會啟用內部或外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="c68dc-112">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="c68dc-113">在任何原則中啟用封存之前，您應該為您的部署指定適當的封存設定，以及針對特定網站和集區（選用）指定適當的封存設定，如本節所述。</span><span class="sxs-lookup"><span data-stu-id="c68dc-113">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="c68dc-114">如需啟用封存的詳細資訊，請參閱部署檔中的設定 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync Server 2013</A> 中的封存原則。</span><span class="sxs-lookup"><span data-stu-id="c68dc-114">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="c68dc-115">如果您在部署封存後決定要使用 Microsoft Exchange 整合將封存資料和檔案儲存在 Exchange 2013 伺服器上，而且所有使用者都位於 Exchange 2013 伺服器上，則應該從拓撲中移除 SQL Server 資料庫設定。</span><span class="sxs-lookup"><span data-stu-id="c68dc-115">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="c68dc-116">您必須使用拓撲產生器來執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="c68dc-116">You must use Topology Builder to do this.</span></span> <span data-ttu-id="c68dc-117">如需詳細資訊，請參閱 Operations 檔中的 <A href="lync-server-2013-changing-archiving-database-options.md">變更 Lync Server 2013</A> 中的封存資料庫選項。</span><span class="sxs-lookup"><span data-stu-id="c68dc-117">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-create-an-archiving-configuration-for-a-site-or-pool"></a><span data-ttu-id="c68dc-118">為網站或集區建立封存設定</span><span class="sxs-lookup"><span data-stu-id="c68dc-118">To create an archiving configuration for a site or pool</span></span>

1.  <span data-ttu-id="c68dc-119">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c68dc-119">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c68dc-120">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="c68dc-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c68dc-121">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c68dc-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c68dc-122">在左導覽列中 **，按一下 [\*\*\*\*監視與**封存]，然後按一下 [封存設定]。</span><span class="sxs-lookup"><span data-stu-id="c68dc-122">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="c68dc-123">在 [ **封存** 設定] 頁面上，按一下 [ **新增**]，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="c68dc-123">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="c68dc-124">若要建立網站封存設定，請按一下 [ **網站** 設定]，然後在 [ **選取網站**] 中選取要設定封存的網站。</span><span class="sxs-lookup"><span data-stu-id="c68dc-124">To create a site archiving configuration, click **Site Configuration** and then, in **Select a site**, select the site to be configured for archiving.</span></span>
    
      - <span data-ttu-id="c68dc-125">若要建立集區封存設定，請按一下 [ **集** 區設定]，然後在 [ **選取集**區] 中選取要設定封存的集區。</span><span class="sxs-lookup"><span data-stu-id="c68dc-125">To create a pool archiving configuration, click **Pool Configuration** and then, in **Select a pool**, select the pool to be configured for archiving.</span></span>

5.  <span data-ttu-id="c68dc-126">在 **[建立新的封存設定]** 的 **[封存設定]** 下拉式清單方塊中，執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="c68dc-126">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
      - <span data-ttu-id="c68dc-127">若只要啟用立即訊息 (IM) 工作階段的封存，請按一下 **[封存 IM 工作階段]**。</span><span class="sxs-lookup"><span data-stu-id="c68dc-127">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="c68dc-128">若要同時啟用 IM 會話和 web 會議的封存，請按一下 [封存 **im 和 web 會議會話**]。</span><span class="sxs-lookup"><span data-stu-id="c68dc-128">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
      - <span data-ttu-id="c68dc-129">若要停用原則的封存，請按一下 **[停用封存]**。</span><span class="sxs-lookup"><span data-stu-id="c68dc-129">To disable archiving for the policy, click **Disable archiving**.</span></span>

6.  <span data-ttu-id="c68dc-130">此外，在 **[建立新的封存設定]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c68dc-130">Also in **New Archiving Setting**, do the following:</span></span>
    
      - <span data-ttu-id="c68dc-131">若要在封存無法使用時封鎖活動，請選取 **[封存失敗時封鎖立即訊息 (IM) 和 Web 會議工作階段]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c68dc-131">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="c68dc-132">若要使用 Microsoft Exchange Server 儲存封存資料，請按一下 [ **Microsoft exchange 整合** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c68dc-132">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="c68dc-133">若要啟用資料清除，請選取 **[啟用封存資料的清除]** 核取方塊，然後執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="c68dc-133">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="c68dc-134">若要指定在特定天數後進行清除，請按一下 **[在最大持續期限 (天) 後清除匯出的封存資料和儲存的封存資料]**，然後指定天數。</span><span class="sxs-lookup"><span data-stu-id="c68dc-134">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="c68dc-135">若要限制只清除已匯出的封存資料，請按一下 **[只清除匯出的封存資料]**。</span><span class="sxs-lookup"><span data-stu-id="c68dc-135">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

7.  <span data-ttu-id="c68dc-136">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="c68dc-136">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c68dc-137">使用 Windows PowerShell Cmdlet 建立封存配置設定</span><span class="sxs-lookup"><span data-stu-id="c68dc-137">Creating Archiving Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c68dc-138">您可以使用 Windows PowerShell 和 New-CsArchivingConfiguration Cmdlet 來建立封存設定設定。</span><span class="sxs-lookup"><span data-stu-id="c68dc-138">Archiving configuration settings can be created by using Windows PowerShell and the New-CsArchivingConfiguration cmdlet.</span></span> <span data-ttu-id="c68dc-139">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c68dc-139">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c68dc-140">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="c68dc-140">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-for-a-site"></a><span data-ttu-id="c68dc-141">為網站建立新的封存配置設定集合</span><span class="sxs-lookup"><span data-stu-id="c68dc-141">To create a new collection of archiving configuration settings for a site</span></span>

  - <span data-ttu-id="c68dc-142">下列命令會為 Redmond 網站建立新的封存配置設定集合：</span><span class="sxs-lookup"><span data-stu-id="c68dc-142">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-that-only-allow-im-archiving"></a><span data-ttu-id="c68dc-143">若要建立只允許 IM 封存的新封存配置設定集合</span><span class="sxs-lookup"><span data-stu-id="c68dc-143">To create a new collection of archiving configuration settings that only allow IM archiving</span></span>

  - <span data-ttu-id="c68dc-144">因為上述命令未指定參數 (除了必要的 Identity 參數)，新的組態設定集合會將預設值用於其所有屬性。</span><span class="sxs-lookup"><span data-stu-id="c68dc-144">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="c68dc-145">若要使用不同的屬性值來建立設定，只要包含適當的參數及參數值即可。</span><span class="sxs-lookup"><span data-stu-id="c68dc-145">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="c68dc-146">例如，若要建立封存設定的集合，根據預設，允許封存立即訊息會話，只會使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="c68dc-146">For example, to create a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions, only use a command like this:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-archiving-configuration-settings"></a><span data-ttu-id="c68dc-147">在建立封存配置設定時指定多個屬性值</span><span class="sxs-lookup"><span data-stu-id="c68dc-147">To specify multiple property values when creating archiving configuration settings</span></span>

  - <span data-ttu-id="c68dc-148">多項屬性值可透過加入多個參數加以修改。</span><span class="sxs-lookup"><span data-stu-id="c68dc-148">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="c68dc-149">例如，此命令會將新設定設定為封存立即訊息會話，並封鎖封存服務的立即訊息無法使用：</span><span class="sxs-lookup"><span data-stu-id="c68dc-149">For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True

</div>

<span data-ttu-id="c68dc-150">如需詳細資訊，請參閱 [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="c68dc-150">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c68dc-151">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c68dc-151">See Also</span></span>


[<span data-ttu-id="c68dc-152">Lync Server 2013 中的封存運作方式</span><span class="sxs-lookup"><span data-stu-id="c68dc-152">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="c68dc-153">為您的組織、網站及集區管理 Lync Server 2013 中的封存設定選項</span><span class="sxs-lookup"><span data-stu-id="c68dc-153">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

