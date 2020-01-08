---
title: Lync Server 2013：設定存檔的全域原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the global policy for Archiving
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48184192
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ccb5ba267c3dc94e14f00cf96f240fa2f0e91b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a><span data-ttu-id="740a1-102">在 Lync Server 2013 中設定存檔的全域原則</span><span class="sxs-lookup"><span data-stu-id="740a1-102">Configuring the global policy for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="740a1-103">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="740a1-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="740a1-104">當您部署前端伺服器時，Lync Server 會建立一個全域原則來存檔。</span><span class="sxs-lookup"><span data-stu-id="740a1-104">When you deploy your Front End Servers, Lync Server creates a global policy for Archiving.</span></span> <span data-ttu-id="740a1-105">根據預設，會停用全域原則中的封存。</span><span class="sxs-lookup"><span data-stu-id="740a1-105">By default, Archiving is disabled in the global policy.</span></span> <span data-ttu-id="740a1-106">全域原則會控制是否針對整個部署啟用封存，除非您設定網站或使用者原則，而這會覆寫全域原則，或是您針對部分或全部使用 Microsoft Exchange 整合您的使用者。</span><span class="sxs-lookup"><span data-stu-id="740a1-106">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="740a1-107">如果您使用的是 Microsoft Exchange 整合，全域原則就不會套用至任何託管于 Exchange 2013 的使用者，並將信箱放在就地保留中。</span><span class="sxs-lookup"><span data-stu-id="740a1-107">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange 2013 and have the mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="740a1-108">如需有關歸檔原則運作方式的詳細資料，包括全域、網站和使用者原則的階層，請參閱 Lync Server 2013 規劃檔、部署檔或作業檔[中的存檔運作方式](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="740a1-108">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="740a1-109">如果您針對您的部署啟用 Microsoft Exchange 整合，Exchange 就地保留原則會控制是否針對託管于 Exchange 2013 的使用者啟用封存，並將其信箱放在就地保留中。</span><span class="sxs-lookup"><span data-stu-id="740a1-109">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="740a1-110">如需詳細資訊，請參閱在部署檔中<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定存檔原則</A>。</span><span class="sxs-lookup"><span data-stu-id="740a1-110">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="740a1-111">在啟用封存前，您應該先在封存配置中指定所有適當的選項。</span><span class="sxs-lookup"><span data-stu-id="740a1-111">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="740a1-112">如需詳細資訊，請參閱部署檔中的<A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013</A>中的 [設定封存選項]。</span><span class="sxs-lookup"><span data-stu-id="740a1-112">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a><span data-ttu-id="740a1-113">在使用 Lync Server 封存資料庫時設定要存檔的全域原則</span><span class="sxs-lookup"><span data-stu-id="740a1-113">To configure the global policy for archiving when using Lync Server Archiving databases</span></span>

1.  <span data-ttu-id="740a1-114">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="740a1-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="740a1-115">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server 2013 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="740a1-115">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="740a1-116">如需可用於啟動 Lync Server 2013 [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="740a1-116">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="740a1-117">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**原則**]。</span><span class="sxs-lookup"><span data-stu-id="740a1-117">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="740a1-118">在 [**存檔原則**] 頁面上，按一下 [**全域**]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="740a1-118">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="740a1-119">在 [**編輯封存原則-全域**] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="740a1-119">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="740a1-120">在 [**名稱**] 中，如果您不想使用預設的全域名稱，請指定全域原則的新名稱。</span><span class="sxs-lookup"><span data-stu-id="740a1-120">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span>
    
      - <span data-ttu-id="740a1-121">在 [**描述**] 中，提供原則的相關資訊（例如， *divisionName*的全域原則）。</span><span class="sxs-lookup"><span data-stu-id="740a1-121">In **Description**, provide information about what the policy is (for example, Global policy for *divisionName*).</span></span>
    
      - <span data-ttu-id="740a1-122">若要控制未透過網站原則或使用者原則專門控制之所有網站和使用者的內部通訊的封存，請選取或清除 [封存**內部通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="740a1-122">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="740a1-123">若要控制未透過網站原則或使用者原則專門控制之所有網站和使用者的外部通訊的封存，請選取或清除 [封存**外部通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="740a1-123">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="740a1-124">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="740a1-124">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

