---
title: Lync Server 2013：設定封存的全域原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the global policy for Archiving
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48184192
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 589c249f772b130eeed80abb97e272b8053dfdc4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532380"
---
# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a><span data-ttu-id="9d0d6-102">在 Lync Server 2013 中設定封存的全域原則</span><span class="sxs-lookup"><span data-stu-id="9d0d6-102">Configuring the global policy for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d0d6-103">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="9d0d6-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="9d0d6-104">當您部署前端伺服器時，Lync Server 會建立通用的封存原則。</span><span class="sxs-lookup"><span data-stu-id="9d0d6-104">When you deploy your Front End Servers, Lync Server creates a global policy for Archiving.</span></span> <span data-ttu-id="9d0d6-105">預設會在全域原則中停用封存。</span><span class="sxs-lookup"><span data-stu-id="9d0d6-105">By default, Archiving is disabled in the global policy.</span></span> <span data-ttu-id="9d0d6-106">「全域」原則會控制是否對整個部署啟用內部和外部通訊的封存，除非您設定網站或使用者原則，以覆寫全域原則，或您針對部分或所有使用者使用 Microsoft Exchange 整合。</span><span class="sxs-lookup"><span data-stu-id="9d0d6-106">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="9d0d6-107">如果您使用 Microsoft Exchange 整合，全域原則不會套用到所有位於 Exchange 2013 上的使用者，而且會將信箱置於 In-Place 保留狀態。</span><span class="sxs-lookup"><span data-stu-id="9d0d6-107">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange 2013 and have the mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="9d0d6-108">如需有關封存原則如何運作（包括全域、網站及使用者原則的階層）的詳細資訊，請參閱 [Lync Server 2013](lync-server-2013-how-archiving-works.md) 規劃檔、部署檔或作業檔中的封存運作方式。</span><span class="sxs-lookup"><span data-stu-id="9d0d6-108">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9d0d6-109">如果您為部署啟用 Microsoft Exchange 整合，Exchange In-Place 保留原則會控制是否為位於 Exchange 2013 上的使用者啟用封存，並將其信箱置於 In-Place 保留狀態。</span><span class="sxs-lookup"><span data-stu-id="9d0d6-109">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="9d0d6-110">如需詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定</A> 封存的原則。</span><span class="sxs-lookup"><span data-stu-id="9d0d6-110">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="9d0d6-111">啟用封存前，應在封存組態中指定所有適當的選項。</span><span class="sxs-lookup"><span data-stu-id="9d0d6-111">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="9d0d6-112">如需詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013</A> 中設定封存選項。</span><span class="sxs-lookup"><span data-stu-id="9d0d6-112">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a><span data-ttu-id="9d0d6-113">使用 Lync Server 封存資料庫時設定封存的全域原則</span><span class="sxs-lookup"><span data-stu-id="9d0d6-113">To configure the global policy for archiving when using Lync Server Archiving databases</span></span>

1.  <span data-ttu-id="9d0d6-114">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="9d0d6-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9d0d6-115">開啟瀏覽器視窗，然後輸入管理 URL，以開啟 Lync Server 2013 控制台。</span><span class="sxs-lookup"><span data-stu-id="9d0d6-115">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="9d0d6-116">如需可用於啟動 Lync Server 2013 控制台之不同方法的詳細資訊，請參閱 [Open Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="9d0d6-116">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9d0d6-117">在左側導覽列中，依序按一下 **[監控和封存]** 和 **[封存原則]**。</span><span class="sxs-lookup"><span data-stu-id="9d0d6-117">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="9d0d6-118">在 **[封存原則]** 頁面上，依序按一下 **[通用]** 和 **[編輯]**，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="9d0d6-118">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="9d0d6-119">在 [編輯封存原則 - 通用]\*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="9d0d6-119">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="9d0d6-120">如果您不想要使用此預設全域名稱，請在 **[名稱]** 中指定全域原則的新名稱。</span><span class="sxs-lookup"><span data-stu-id="9d0d6-120">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span>
    
      - <span data-ttu-id="9d0d6-121">在 **[描述]** 中，提供有關使用者原則的資訊 (例如，*divisionName* 的全域原則)。</span><span class="sxs-lookup"><span data-stu-id="9d0d6-121">In **Description**, provide information about what the policy is (for example, Global policy for *divisionName*).</span></span>
    
      - <span data-ttu-id="9d0d6-122">若要控制未特別透過網站原則或使用者原則控制之所有網站及使用者的內部通訊封存，請選取或清除 **[封存內部通訊]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="9d0d6-122">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="9d0d6-123">若要控制未特別透過網站原則或使用者原則控制之所有網站及使用者的外部通訊封存，請選取或清除 [封存外部通訊]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="9d0d6-123">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="9d0d6-124">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="9d0d6-124">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

