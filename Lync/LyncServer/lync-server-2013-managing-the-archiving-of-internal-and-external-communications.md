---
title: 管理內部與外部通訊的存檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a9e3c0a0708075eecc28282021f98724325ff6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a><span data-ttu-id="95d5d-102">在 Lync Server 2013 中管理內部和外部通訊的存檔</span><span class="sxs-lookup"><span data-stu-id="95d5d-102">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95d5d-103">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="95d5d-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="95d5d-104">在 Lync Server 2013 中，如果您不使用 Microsoft Exchange 整合，或者您的使用者未駐留在 Exchange 2013 上，且其信箱放在外，您可以使用封存原則來啟用和停用內部通訊與外部通訊的封存就地保留。</span><span class="sxs-lookup"><span data-stu-id="95d5d-104">In Lync Server 2013, you use Archiving policies to enable and disable archiving for internal communications and external communications if you do not use Microsoft Exchange integration or you have users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="95d5d-105">這包括下列歸檔原則：</span><span class="sxs-lookup"><span data-stu-id="95d5d-105">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="95d5d-106">部署 Lync Server 2013 時預設建立的全域原則。</span><span class="sxs-lookup"><span data-stu-id="95d5d-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="95d5d-107">您可以建立及使用的選擇性網站層級和使用者層級原則，以指定如何針對特定網站或使用者執行封存。</span><span class="sxs-lookup"><span data-stu-id="95d5d-107">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="95d5d-108">您最初是在部署封存時設定封存原則，但是您可以在部署之後變更、新增及刪除原則。</span><span class="sxs-lookup"><span data-stu-id="95d5d-108">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="95d5d-109">在 Lync Server 2013 的 [控制台] 中，您可以使用 [封存**與監控**] 群組的 [**存檔原則**] 頁面，來管理全域層級、網站層級及使用者層級的原則。</span><span class="sxs-lookup"><span data-stu-id="95d5d-109">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span> <span data-ttu-id="95d5d-110">如果您將 Lync Server storage 與 Exchange 2013 儲存整合，Exchange 使用者原則就會優先于 Lync Server 2013 封存原則。</span><span class="sxs-lookup"><span data-stu-id="95d5d-110">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies.</span></span>

<span data-ttu-id="95d5d-111">如需如何執行原則的詳細資料，包括原則的階層，請參閱規劃檔、部署檔或作業檔中的 [[在 Lync Server 2013 存檔中的運作方式](lync-server-2013-how-archiving-works.md)]。</span><span class="sxs-lookup"><span data-stu-id="95d5d-111">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="95d5d-112">若要控制封存的實現，您必須指定歸檔設定中的選項，例如是否要封存 IM 或會議、使用重要模式，以及清除選項。</span><span class="sxs-lookup"><span data-stu-id="95d5d-112">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="95d5d-113">根據預設，全域存檔設定或任何網站或池封存設定中不會啟用任何選項。</span><span class="sxs-lookup"><span data-stu-id="95d5d-113">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="95d5d-114">您應該先在封存配置中指定所有適當的選項，才能在歸檔原則中啟用內部或外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="95d5d-114">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="95d5d-115">如需詳細資訊，請參閱在作業檔中<A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">針對貴組織、網站和池管理 Lync Server 2013 中的 [封存配置選項</A>]。</span><span class="sxs-lookup"><span data-stu-id="95d5d-115">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="95d5d-116">如果您針對您的部署啟用 Microsoft Exchange 整合，Exchange 原則會控制是否針對託管于 Exchange 2013 的使用者啟用封存，並將其信箱放在就地保留中。</span><span class="sxs-lookup"><span data-stu-id="95d5d-116">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="95d5d-117">如需詳細資訊，請參閱在部署檔中<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定存檔原則</A>。</span><span class="sxs-lookup"><span data-stu-id="95d5d-117">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="95d5d-118">本節內容</span><span class="sxs-lookup"><span data-stu-id="95d5d-118">In This Section</span></span>

  - [<span data-ttu-id="95d5d-119">在 Lync Server 2013 中建立存檔原則，以啟用或停用特定網站或使用者的內部或外部通訊的存檔</span><span class="sxs-lookup"><span data-stu-id="95d5d-119">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users</span></span>](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md)

  - [<span data-ttu-id="95d5d-120">在 Lync Server 2013 中變更存檔原則，以啟用或停用貴組織、網站或使用者的內部或外部通訊的封存功能</span><span class="sxs-lookup"><span data-stu-id="95d5d-120">Changing an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for your organization, sites, or users</span></span>](lync-server-2013-changing-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-your-organization-sites-or-us.md)

  - [<span data-ttu-id="95d5d-121">將存檔原則套用至 Lync Server 2013 中的使用者</span><span class="sxs-lookup"><span data-stu-id="95d5d-121">Applying an Archiving policy to users in Lync Server 2013</span></span>](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [<span data-ttu-id="95d5d-122">使用 Exchange Server 整合時，在 Lync Server 2013 中設定存檔原則</span><span class="sxs-lookup"><span data-stu-id="95d5d-122">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [<span data-ttu-id="95d5d-123">刪除 Lync Server 2013 中的存檔原則</span><span class="sxs-lookup"><span data-stu-id="95d5d-123">Deleting an Archiving policy in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

