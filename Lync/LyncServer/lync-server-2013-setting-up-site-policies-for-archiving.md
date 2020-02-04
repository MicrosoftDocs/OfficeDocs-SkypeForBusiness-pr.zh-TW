---
title: Lync Server 2013：設定用於存檔的網站原則
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
ms.openlocfilehash: 1ebb1efdfff09f51b13ada9d1e2aa571ab88c888
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="78587-102">在 Lync Server 2013 中設定用於存檔的網站原則</span><span class="sxs-lookup"><span data-stu-id="78587-102">Setting up site policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78587-103">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="78587-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="78587-104">您可以建立並設定每個網站的存檔原則，以啟用或停用特定網站的封存。</span><span class="sxs-lookup"><span data-stu-id="78587-104">You can enable or disable Archiving for specific sites by creating and configuring an Archiving policy for each of those sites.</span></span> <span data-ttu-id="78587-105">網站原則會覆寫全域原則，但使用者原則會覆寫網站原則。</span><span class="sxs-lookup"><span data-stu-id="78587-105">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="78587-106">如果您不使用 Microsoft Exchange 整合，或如果您使用的是 Microsoft Exchange 整合，但不是駐留在 Exchange 2013 的部分使用者，且其信箱放在就地保留中，則只適用存檔原則。</span><span class="sxs-lookup"><span data-stu-id="78587-106">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="78587-107">如需有關歸檔原則運作方式的詳細資料，包括全域、網站和使用者原則的階層，請參閱 Lync Server 2013 規劃檔、部署檔或作業檔[中的存檔運作方式](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="78587-107">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="78587-108">如果您針對您的部署啟用 Microsoft Exchange 整合，Exchange 就地保留原則會控制是否針對託管于 Exchange 2013 的使用者啟用封存，並將其信箱放在就地保留中。</span><span class="sxs-lookup"><span data-stu-id="78587-108">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="78587-109">如需詳細資訊，請參閱在部署檔中<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定存檔原則</A>。</span><span class="sxs-lookup"><span data-stu-id="78587-109">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="78587-110">您應該先在封存配置中指定所有適當的選項，才能在歸檔原則中封存內部或外部通訊。</span><span class="sxs-lookup"><span data-stu-id="78587-110">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="78587-111">如需詳細資訊，請參閱部署檔中的<A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013</A>中的 [設定封存選項]。</span><span class="sxs-lookup"><span data-stu-id="78587-111">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a><span data-ttu-id="78587-112">建立網站的存檔原則</span><span class="sxs-lookup"><span data-stu-id="78587-112">To create an archiving policy for a site</span></span>

1.  <span data-ttu-id="78587-113">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="78587-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="78587-114">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server 2013 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="78587-114">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span>

3.  <span data-ttu-id="78587-115">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**原則**]。</span><span class="sxs-lookup"><span data-stu-id="78587-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="78587-116">如需有關歸檔原則運作方式的詳細資料，包括全域、網站和使用者原則的階層，請參閱 Lync Server 2013 規劃檔、部署檔或作業檔[中的存檔運作方式](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="78587-116">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

4.  <span data-ttu-id="78587-117">按一下 [新增]\*\*\*\*，然後按一下 [站台原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="78587-117">Click **New**, and then click **Site policy**.</span></span>

5.  <span data-ttu-id="78587-118">在 [**選取網站**] 中，按一下要套用原則的網站。</span><span class="sxs-lookup"><span data-stu-id="78587-118">In **Select a site**, click the site to which the policy is to be applied.</span></span>

6.  <span data-ttu-id="78587-119">在**新**的 [封存原則] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="78587-119">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="78587-120">在 [**名稱**] 中，指定網站原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="78587-120">In **Name**, specify the name for the site policy.</span></span>
    
      - <span data-ttu-id="78587-121">在 [**描述**] 中，提供網站原則的相關資訊（例如，雷蒙德的網站原則）。</span><span class="sxs-lookup"><span data-stu-id="78587-121">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
      - <span data-ttu-id="78587-122">若要控制指定網站內部通訊的歸檔，請選取或清除 [封存**內部通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="78587-122">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="78587-123">若要控制指定網站外部通訊的存檔，請選取或清除 [封存**外部通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="78587-123">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>

7.  <span data-ttu-id="78587-124">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="78587-124">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

