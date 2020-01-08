---
title: 啟用或停用 IM 或會議會話的功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling Archiving of IM or conferencing sessions
ms:assetid: aa4b5983-dbe1-4d64-8a18-fe2c33994e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182567(v=OCS.15)
ms:contentKeyID: 48185104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65712cf15ae73ec7cdb49dc7652348085a4c93d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977267"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-archiving-of-im-or-conferencing-sessions-in-lync-server-2013"></a><span data-ttu-id="73ffb-102">在 Lync Server 2013 中啟用或停用 IM 或會議會話的封存</span><span class="sxs-lookup"><span data-stu-id="73ffb-102">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73ffb-103">_**主題上次修改日期：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="73ffb-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="73ffb-104">在 Lync Server 2013 的 [控制台] 中，您可以使用 [封存] 設定來啟用和停用 IM、會議會話或兩者的封存。</span><span class="sxs-lookup"><span data-stu-id="73ffb-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable archiving of IM, conferencing sessions, or both.</span></span> <span data-ttu-id="73ffb-105">這包括下列歸檔設定：</span><span class="sxs-lookup"><span data-stu-id="73ffb-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="73ffb-106">當您部署 Lync Server 2013 時預設會建立的全域配置。</span><span class="sxs-lookup"><span data-stu-id="73ffb-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="73ffb-107">您可以建立及用來指定如何針對特定網站或池實施封存的選擇性網站層級和池層級設定。</span><span class="sxs-lookup"><span data-stu-id="73ffb-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="73ffb-108">您最初是在部署封存時設定封存配置，但您可以在部署之後變更、新增及刪除配置。</span><span class="sxs-lookup"><span data-stu-id="73ffb-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="73ffb-109">如需有關如何實施封存配置的詳細資料，包括您可以指定哪些選項，以及歸檔設定的階層，請參閱規劃檔、部署檔或作業檔中的 [[在 Lync Server 2013 中的存檔運作方式](lync-server-2013-how-archiving-works.md)]。</span><span class="sxs-lookup"><span data-stu-id="73ffb-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="73ffb-110">若要使用封存，您必須設定封存原則，以指定是否要針對內部通訊啟用封存，或針對駐留在 Lync Server 2013 的使用者。</span><span class="sxs-lookup"><span data-stu-id="73ffb-110">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="73ffb-111">根據預設，不會針對內部或外部通訊啟用封存。</span><span class="sxs-lookup"><span data-stu-id="73ffb-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="73ffb-112">在任何原則中啟用封存前，您應該為您的部署指定適當的歸檔設定，也可以針對特定的網站和池指定適當的存檔配置，如本節所述。</span><span class="sxs-lookup"><span data-stu-id="73ffb-112">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="73ffb-113">如需啟用封存的詳細資料，請參閱在部署檔中設定<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync Server 2013 中的存檔原則</A>。</span><span class="sxs-lookup"><span data-stu-id="73ffb-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="73ffb-114">如果您在部署存檔後決定要使用 Microsoft Exchange 整合來儲存 Exchange 2013 伺服器上的封存資料和檔案，且您的所有使用者都是位於 Exchange 2013 伺服器上，那麼您應該移除 SQL Server 資料庫配置從您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="73ffb-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="73ffb-115">您必須使用拓撲 Builder 建立器。</span><span class="sxs-lookup"><span data-stu-id="73ffb-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="73ffb-116">如需詳細資訊，請參閱在作業檔中<A href="lync-server-2013-changing-archiving-database-options.md">變更 Lync Server 2013</A>中的封存資料庫選項。</span><span class="sxs-lookup"><span data-stu-id="73ffb-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-archiving-of-im-or-conferencing-sessions"></a><span data-ttu-id="73ffb-117">啟用或停用 IM 或會議會話的功能</span><span class="sxs-lookup"><span data-stu-id="73ffb-117">To enable or disable archiving of IM or conferencing sessions</span></span>

1.  <span data-ttu-id="73ffb-118">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="73ffb-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="73ffb-119">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="73ffb-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="73ffb-120">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="73ffb-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="73ffb-121">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。</span><span class="sxs-lookup"><span data-stu-id="73ffb-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="73ffb-122">從存檔設定清單中選取適當的全域、網站或池設定，按一下 [**編輯**]，按一下 [**顯示詳細資料**]，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="73ffb-122">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="73ffb-123">若要只針對立即訊息（IM）會話啟用封存，請按一下 [封存**IM 會話**]。</span><span class="sxs-lookup"><span data-stu-id="73ffb-123">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="73ffb-124">若要在 IM 會話與會議中啟用封存功能，請按一下 [封存**im 及會議會話**]。</span><span class="sxs-lookup"><span data-stu-id="73ffb-124">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
      - <span data-ttu-id="73ffb-125">若要停用原則封存，請按一下 [**停**用封存]。</span><span class="sxs-lookup"><span data-stu-id="73ffb-125">To disable archiving for the policy, click **Disable archiving**.</span></span>

5.  <span data-ttu-id="73ffb-126">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="73ffb-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="73ffb-127">請參閱</span><span class="sxs-lookup"><span data-stu-id="73ffb-127">See Also</span></span>


[<span data-ttu-id="73ffb-128">管理您組織、網站和池的 Lync Server 2013 中的封存配置選項</span><span class="sxs-lookup"><span data-stu-id="73ffb-128">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
[<span data-ttu-id="73ffb-129">在 Lync Server 2013 中設定及指派存檔原則</span><span class="sxs-lookup"><span data-stu-id="73ffb-129">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

