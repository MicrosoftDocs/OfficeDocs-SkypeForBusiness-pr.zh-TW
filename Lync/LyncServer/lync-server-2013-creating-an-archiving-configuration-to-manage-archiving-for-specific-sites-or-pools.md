---
title: Lync Server 2013：建立存檔設定以管理特定網站或池中的存檔
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
ms.openlocfilehash: 3b0495a15d19adba9ac21fb7817347a16b78bc13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-an-archiving-configuration-in-lync-server-2013-to-manage-archiving-for-specific-sites-or-pools"></a><span data-ttu-id="6a9cd-102">在 Lync Server 2013 中建立存檔設定，以管理特定網站或池中的存檔</span><span class="sxs-lookup"><span data-stu-id="6a9cd-102">Creating an Archiving configuration in Lync Server 2013 to manage Archiving for specific sites or pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a9cd-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="6a9cd-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="6a9cd-104">在 Lync Server 2013 的 [控制台] 中，您可以使用封存配置來控制在您的部署中實現封存的方式。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-104">In Lync Server 2013 Control Panel, you use Archiving configurations to control how archiving is implemented in your deployment.</span></span> <span data-ttu-id="6a9cd-105">這包括下列歸檔設定：</span><span class="sxs-lookup"><span data-stu-id="6a9cd-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="6a9cd-106">當您部署 Lync Server 2013 時預設會建立的全域配置。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="6a9cd-107">您可以建立及用來指定如何針對特定網站或池實施封存的選擇性網站層級和池層級設定。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="6a9cd-108">您最初是在部署封存時設定封存配置，但您可以在部署之後變更、新增及刪除配置。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="6a9cd-109">如需有關如何實施封存配置的詳細資料，包括您可以指定哪些選項，以及歸檔設定的階層，請參閱規劃檔、部署檔或作業檔中的 [[在 Lync Server 2013 中的存檔運作方式](lync-server-2013-how-archiving-works.md)]。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6a9cd-110">若要使用封存，您必須設定封存原則，以指定是否要針對內部通訊啟用封存，或針對駐留在 Lync Server 2013 的使用者。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-110">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="6a9cd-111">根據預設，不會針對內部或外部通訊啟用封存。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="6a9cd-112">在任何原則中啟用封存前，您應該為您的部署指定適當的歸檔設定，也可以針對特定的網站和池指定適當的存檔配置，如本節所述。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-112">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="6a9cd-113">如需啟用封存的詳細資料，請參閱在部署檔中設定<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync Server 2013 中的存檔原則</A>。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="6a9cd-114">如果您在部署存檔後決定要使用 Microsoft Exchange 整合來儲存 Exchange 2013 伺服器上的封存資料和檔案，且您的所有使用者都是位於 Exchange 2013 伺服器上，那麼您應該移除 SQL Server 資料庫配置從您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="6a9cd-115">您必須使用拓撲 Builder 建立器。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="6a9cd-116">如需詳細資訊，請參閱在作業檔中<A href="lync-server-2013-changing-archiving-database-options.md">變更 Lync Server 2013</A>中的封存資料庫選項。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-create-an-archiving-configuration-for-a-site-or-pool"></a><span data-ttu-id="6a9cd-117">為網站或文件庫建立封存配置</span><span class="sxs-lookup"><span data-stu-id="6a9cd-117">To create an archiving configuration for a site or pool</span></span>

1.  <span data-ttu-id="6a9cd-118">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6a9cd-119">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6a9cd-120">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6a9cd-121">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="6a9cd-122">在 [**存檔**設定] 頁面上，按一下 [**新增**]，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="6a9cd-122">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="6a9cd-123">若要建立網站封存設定，請按一下 [**網站**設定]，然後在 [**選取網站**] 中，選取要設定為要存檔的網站。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-123">To create a site archiving configuration, click **Site Configuration** and then, in **Select a site**, select the site to be configured for archiving.</span></span>
    
      - <span data-ttu-id="6a9cd-124">若要建立池存檔設定，請按一下 [**池**設定]，然後在 [**選取池**] 中，選取要設定為要存檔的池。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-124">To create a pool archiving configuration, click **Pool Configuration** and then, in **Select a pool**, select the pool to be configured for archiving.</span></span>

5.  <span data-ttu-id="6a9cd-125">在 [**新增封存設定**] 的 [**存檔設定**] 下拉式清單方塊中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="6a9cd-125">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
      - <span data-ttu-id="6a9cd-126">若要只針對立即訊息（IM）會話啟用封存，請按一下 [封存**IM 會話**]。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-126">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="6a9cd-127">若要在 IM 會話和網路會議中同時啟用封存功能，請按一下 [封存**im 和網路會議會話**]。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-127">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
      - <span data-ttu-id="6a9cd-128">若要停用原則封存，請按一下 [**停**用封存]。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-128">To disable archiving for the policy, click **Disable archiving**.</span></span>

6.  <span data-ttu-id="6a9cd-129">此外，在 [新增封存]**設定**中，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="6a9cd-129">Also in **New Archiving Setting**, do the following:</span></span>
    
      - <span data-ttu-id="6a9cd-130">若要在封存無法使用時封鎖活動，請選取 [**如果封存失敗，封鎖立即訊息（IM）或 web 會議會話**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-130">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="6a9cd-131">若要使用 Microsoft Exchange Server 儲存存檔資料，請按一下 [ **Microsoft exchange 整合**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-131">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="6a9cd-132">若要啟用資料清除，請選取 [**啟用 [清除封存資料**] 核取方塊，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="6a9cd-132">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="6a9cd-133">若要指定在特定天數後進行清除，請按一下 **[清除匯出的存檔資料]，並儲存在最長持續時間（天數）之後的儲存封存資料**，然後指定天數。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-133">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="6a9cd-134">若要限制清除以封存已匯出的資料，請按一下 [**僅清除匯出的存檔資料**]。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-134">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

7.  <span data-ttu-id="6a9cd-135">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6a9cd-136">使用 Windows PowerShell Cmdlet 建立封存配置設定</span><span class="sxs-lookup"><span data-stu-id="6a9cd-136">Creating Archiving Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6a9cd-137">您可以使用 Windows PowerShell 和 CsArchivingConfiguration Cmdlet 來建立封存配置設定。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-137">Archiving configuration settings can be created by using Windows PowerShell and the New-CsArchivingConfiguration cmdlet.</span></span> <span data-ttu-id="6a9cd-138">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-138">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6a9cd-139">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-139">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-for-a-site"></a><span data-ttu-id="6a9cd-140">若要建立新的網站封存配置設定集合</span><span class="sxs-lookup"><span data-stu-id="6a9cd-140">To create a new collection of archiving configuration settings for a site</span></span>

  - <span data-ttu-id="6a9cd-141">下列命令會建立新的 [雷德蒙] 網站存檔設定的集合：</span><span class="sxs-lookup"><span data-stu-id="6a9cd-141">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-that-only-allow-im-archiving"></a><span data-ttu-id="6a9cd-142">若要建立只允許 IM 存檔的新的封存設定設定集合</span><span class="sxs-lookup"><span data-stu-id="6a9cd-142">To create a new collection of archiving configuration settings that only allow IM archiving</span></span>

  - <span data-ttu-id="6a9cd-143">因為在上述命令中沒有指定任何參數（強制身分識別參數以外），所以新的配置設定集合會將預設值用於其所有屬性。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-143">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="6a9cd-144">若要建立使用不同屬性值的設定，只要包含適當的參數和參數值即可。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-144">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="6a9cd-145">例如，若要建立一組封存設定，並根據預設，允許封存立即訊息會話，請只使用如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="6a9cd-145">For example, to create a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions, only use a command like this:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-archiving-configuration-settings"></a><span data-ttu-id="6a9cd-146">若要在建立存檔設定時指定多個屬性值</span><span class="sxs-lookup"><span data-stu-id="6a9cd-146">To specify multiple property values when creating archiving configuration settings</span></span>

  - <span data-ttu-id="6a9cd-147">您可以透過包含多個參數來修改多個屬性值。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-147">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="6a9cd-148">例如，這個命令會將新設定設為封存立即訊息會話，並封鎖封存服務的立即訊息無法使用：</span><span class="sxs-lookup"><span data-stu-id="6a9cd-148">For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True

</div>

<span data-ttu-id="6a9cd-149">如需詳細資訊，請參閱[新版-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="6a9cd-149">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6a9cd-150">請參閱</span><span class="sxs-lookup"><span data-stu-id="6a9cd-150">See Also</span></span>


[<span data-ttu-id="6a9cd-151">存檔在 Lync Server 2013 中的運作方式</span><span class="sxs-lookup"><span data-stu-id="6a9cd-151">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="6a9cd-152">管理您組織、網站和池的 Lync Server 2013 中的封存配置選項</span><span class="sxs-lookup"><span data-stu-id="6a9cd-152">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

