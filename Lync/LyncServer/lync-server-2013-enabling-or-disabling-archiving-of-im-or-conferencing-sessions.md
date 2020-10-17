---
title: 啟用或停用封存 IM 或會議會話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling Archiving of IM or conferencing sessions
ms:assetid: aa4b5983-dbe1-4d64-8a18-fe2c33994e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182567(v=OCS.15)
ms:contentKeyID: 48185104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f2d9f08ade88a3c19dd861457a46200e7517a34
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515510"
---
# <a name="enabling-or-disabling-archiving-of-im-or-conferencing-sessions-in-lync-server-2013"></a><span data-ttu-id="51558-102">啟用或停用 Lync Server 2013 中的 IM 或會議會話的封存</span><span class="sxs-lookup"><span data-stu-id="51558-102">Enabling or disabling Archiving of IM or conferencing sessions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51558-103">_**主題上次修改日期：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="51558-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="51558-104">在 [Lync Server 2013 控制台] 中，您可以使用封存設定來啟用及停用 IM、會議會話或兩者的封存。</span><span class="sxs-lookup"><span data-stu-id="51558-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable archiving of IM, conferencing sessions, or both.</span></span> <span data-ttu-id="51558-105">這包含下列封存組態：</span><span class="sxs-lookup"><span data-stu-id="51558-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="51558-106">當您部署 Lync Server 2013 時，預設會建立全域設定。</span><span class="sxs-lookup"><span data-stu-id="51558-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="51558-107">選用的網站層級和集區層級組態，可建立及用於指定針對特定網站或集區如何實作封存。</span><span class="sxs-lookup"><span data-stu-id="51558-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="51558-108">您一開始部署封存時會設定封存組態，但是在部署後可以變更、新增及刪除組態。</span><span class="sxs-lookup"><span data-stu-id="51558-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="51558-109">如需如何執行封存設定的詳細資訊，包括您可以指定哪些選項以及封存設定的階層，請參閱規劃檔、部署檔或作業檔中的封存 [如何在 Lync Server 2013 中運作](lync-server-2013-how-archiving-works.md) 。</span><span class="sxs-lookup"><span data-stu-id="51558-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="51558-110">若要使用封存，您必須設定封存原則，以指定是否啟用內部通訊、外部通訊或同時適用于 Lync Server 2013 的使用者的封存。</span><span class="sxs-lookup"><span data-stu-id="51558-110">To use archiving, you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both for users homed on Lync Server 2013.</span></span> <span data-ttu-id="51558-111">依據預設，都不會啟用內部或外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="51558-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="51558-112">在任何原則中啟用封存之前，您應該為您的部署指定適當的封存設定，以及針對特定網站和集區（選用）指定適當的封存設定，如本節所述。</span><span class="sxs-lookup"><span data-stu-id="51558-112">Before enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="51558-113">如需啟用封存的詳細資訊，請參閱部署檔中的設定 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync Server 2013</A> 中的封存原則。</span><span class="sxs-lookup"><span data-stu-id="51558-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="51558-114">如果您在部署封存後決定要使用 Microsoft Exchange 整合將封存資料和檔案儲存在 Exchange 2013 伺服器上，而且所有使用者都位於 Exchange 2013 伺服器上，則應該從拓撲中移除 SQL Server 資料庫設定。</span><span class="sxs-lookup"><span data-stu-id="51558-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="51558-115">您必須使用拓撲產生器來執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="51558-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="51558-116">如需詳細資訊，請參閱 Operations 檔中的 <A href="lync-server-2013-changing-archiving-database-options.md">變更 Lync Server 2013</A> 中的封存資料庫選項。</span><span class="sxs-lookup"><span data-stu-id="51558-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-archiving-of-im-or-conferencing-sessions"></a><span data-ttu-id="51558-117">啟用或停用封存 IM 或會議會話</span><span class="sxs-lookup"><span data-stu-id="51558-117">To enable or disable archiving of IM or conferencing sessions</span></span>

1.  <span data-ttu-id="51558-118">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="51558-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="51558-119">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="51558-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="51558-120">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="51558-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="51558-121">在左導覽列中 **，按一下 [\*\*\*\*監視與**封存]，然後按一下 [封存設定]。</span><span class="sxs-lookup"><span data-stu-id="51558-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="51558-122">從封存設定清單中選取適當的全域、網站或集區設定，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="51558-122">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="51558-123">若只要啟用立即訊息 (IM) 工作階段的封存，請按一下 **[封存 IM 工作階段]**。</span><span class="sxs-lookup"><span data-stu-id="51558-123">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="51558-124">若要同時啟用 IM 會話和會議的封存，請按一下 [封存 **im 和會議會話**]。</span><span class="sxs-lookup"><span data-stu-id="51558-124">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
      - <span data-ttu-id="51558-125">若要停用原則的封存，請按一下 **[停用封存]**。</span><span class="sxs-lookup"><span data-stu-id="51558-125">To disable archiving for the policy, click **Disable archiving**.</span></span>

5.  <span data-ttu-id="51558-126">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="51558-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="51558-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="51558-127">See Also</span></span>


[<span data-ttu-id="51558-128">為您的組織、網站及集區管理 Lync Server 2013 中的封存設定選項</span><span class="sxs-lookup"><span data-stu-id="51558-128">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
[<span data-ttu-id="51558-129">在 Lync Server 2013 中設定和指派封存原則</span><span class="sxs-lookup"><span data-stu-id="51558-129">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

