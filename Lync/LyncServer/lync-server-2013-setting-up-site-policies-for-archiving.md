---
title: Lync Server 2013：設定封存的網站原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up site policies for Archiving
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205325(v=OCS.15)
ms:contentKeyID: 48185613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c3845289399c005a7d4d67e07629f71e86b6184
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="cdef4-102">在 Lync Server 2013 中設定封存的網站原則</span><span class="sxs-lookup"><span data-stu-id="cdef4-102">Setting up site policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cdef4-103">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="cdef4-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="cdef4-104">您可以為每個網站建立及設定封存原則，以啟用或停用特定網站的封存。</span><span class="sxs-lookup"><span data-stu-id="cdef4-104">You can enable or disable Archiving for specific sites by creating and configuring an Archiving policy for each of those sites.</span></span> <span data-ttu-id="cdef4-105">網站原則會覆寫全域原則，但使用者原則會覆寫網站原則。</span><span class="sxs-lookup"><span data-stu-id="cdef4-105">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="cdef4-106">封存原則只有在您未使用 Microsoft Exchange 整合時才會套用，否則，如果您使用 Microsoft Exchange 整合，但有部分使用者未位於 Exchange 2013，且其信箱置於 In-Place 保留狀態，則僅適用。</span><span class="sxs-lookup"><span data-stu-id="cdef4-106">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="cdef4-107">如需有關封存原則如何運作（包括全域、網站及使用者原則的階層）的詳細資訊，請參閱[Lync Server 2013](lync-server-2013-how-archiving-works.md)規劃檔、部署檔或作業檔中的封存運作方式。</span><span class="sxs-lookup"><span data-stu-id="cdef4-107">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cdef4-108">如果您為部署啟用 Microsoft Exchange 整合，Exchange In-Place 保留原則會控制是否為位於 Exchange 2013 上的使用者啟用封存，並將其信箱置於 In-Place 保留狀態。</span><span class="sxs-lookup"><span data-stu-id="cdef4-108">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="cdef4-109">如需詳細資訊，請參閱部署檔中的<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定</A>封存的原則。</span><span class="sxs-lookup"><span data-stu-id="cdef4-109">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="cdef4-110">您應該先在封存設定中指定所有適當的選項，才能在封存原則中封存內部或外部通訊。</span><span class="sxs-lookup"><span data-stu-id="cdef4-110">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="cdef4-111">如需詳細資訊，請參閱部署檔中的在<A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013</A>中設定封存選項。</span><span class="sxs-lookup"><span data-stu-id="cdef4-111">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a><span data-ttu-id="cdef4-112">若要建立網站的封存原則</span><span class="sxs-lookup"><span data-stu-id="cdef4-112">To create an archiving policy for a site</span></span>

1.  <span data-ttu-id="cdef4-113">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="cdef4-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cdef4-114">開啟瀏覽器視窗，然後輸入管理 URL，以開啟 Lync Server 2013 控制台。</span><span class="sxs-lookup"><span data-stu-id="cdef4-114">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span>

3.  <span data-ttu-id="cdef4-115">在左側導覽列中，依序按一下 **[監控和封存]** 和 **[封存原則]**。</span><span class="sxs-lookup"><span data-stu-id="cdef4-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="cdef4-116">如需有關封存原則如何運作（包括全域、網站及使用者原則的階層）的詳細資訊，請參閱[Lync Server 2013](lync-server-2013-how-archiving-works.md)規劃檔、部署檔或作業檔中的封存運作方式。</span><span class="sxs-lookup"><span data-stu-id="cdef4-116">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

4.  <span data-ttu-id="cdef4-117">按一下 [新增]\*\*\*\*，然後按一下 [站台原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cdef4-117">Click **New**, and then click **Site policy**.</span></span>

5.  <span data-ttu-id="cdef4-118">在 [**選取網站**] 中，按一下要套用原則的網站。</span><span class="sxs-lookup"><span data-stu-id="cdef4-118">In **Select a site**, click the site to which the policy is to be applied.</span></span>

6.  <span data-ttu-id="cdef4-119">在 **[新增封存原則]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="cdef4-119">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="cdef4-120">在 [**名稱**] 中，指定網站原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="cdef4-120">In **Name**, specify the name for the site policy.</span></span>
    
      - <span data-ttu-id="cdef4-121">在 [**描述**] 中，提供網站原則 (的相關資訊（例如，Redmond) 的網站原則）。</span><span class="sxs-lookup"><span data-stu-id="cdef4-121">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
      - <span data-ttu-id="cdef4-122">若要控制指定網站的內部通訊封存，請選取或清除 [封存**內部通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="cdef4-122">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="cdef4-123">若要控制指定網站的外部通訊封存，請選取或清除 [封存**外部通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="cdef4-123">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>

7.  <span data-ttu-id="cdef4-124">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="cdef4-124">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

