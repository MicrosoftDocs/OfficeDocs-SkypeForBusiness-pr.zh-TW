---
title: Lync Server 2013：在 Lync Server 中設定存檔的使用者原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa8f377c2a78275419c7d4906a51a9550864b8ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="07ca9-102">在 Lync Server 2013 中設定存檔的使用者原則</span><span class="sxs-lookup"><span data-stu-id="07ca9-102">Setting up user policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07ca9-103">_**主題上次修改日期：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="07ca9-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="07ca9-104">針對駐留在 Lync Server 2013 的特定使用者啟用或停用封存需要建立及設定一或多個使用者原則，然後將適當的原則套用至特定的使用者或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="07ca9-104">Enabling or disabling Archiving for specific users homed on Lync Server 2013 requires creating and configuring one or more user policies, and then applying the appropriate policy to specific users or user groups.</span></span> <span data-ttu-id="07ca9-105">使用者原則會覆寫網站和全域原則，但只適用于駐留在 Lync Server 2013 的使用者。</span><span class="sxs-lookup"><span data-stu-id="07ca9-105">User policies override site and global policies, but only for users homed on Lync Server 2013.</span></span>

<span data-ttu-id="07ca9-106">使用者永遠都是在 Lync Server 中託管。</span><span class="sxs-lookup"><span data-stu-id="07ca9-106">Users are always homed in Lync Server.</span></span> <span data-ttu-id="07ca9-107">如果已啟用 Microsoft Exchange 整合，則信箱是 Microsoft Exchange Server 2013 的使用者，不需要在 Lync Server 管理中擁有其存檔原則。</span><span class="sxs-lookup"><span data-stu-id="07ca9-107">If Microsoft Exchange integration is enabled, users whose mailboxes are in Microsoft Exchange Server 2013 don’t need to have their Archiving policies in Lync Server managed.</span></span> <span data-ttu-id="07ca9-108">這些擁有存檔的使用者將由 Exchange 就地保留進行管理。</span><span class="sxs-lookup"><span data-stu-id="07ca9-108">These users with Archiving will be managed by Exchange In-Place Hold.</span></span>

<span data-ttu-id="07ca9-109">如需有關歸檔原則運作方式的詳細資料，包括全域、網站和使用者原則的階層，請參閱規劃檔、部署檔或作業檔中的 [[在 Lync Server 2013 存檔中的運作方式](lync-server-2013-how-archiving-works.md)]。</span><span class="sxs-lookup"><span data-stu-id="07ca9-109">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07ca9-110">如果您已針對您的部署啟用 Microsoft Exchange 整合，請按 Exchange 就地保留原則控制是否已針對託管于 Exchange 2013 的使用者啟用封存。</span><span class="sxs-lookup"><span data-stu-id="07ca9-110">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013.</span></span> <span data-ttu-id="07ca9-111">針對這些使用者的存檔要求他們將其信箱放在就地保留中。</span><span class="sxs-lookup"><span data-stu-id="07ca9-111">Archiving for these users requires that they have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="07ca9-112">如需詳細資訊，請參閱在部署檔中<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定存檔原則</A>。</span><span class="sxs-lookup"><span data-stu-id="07ca9-112">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="07ca9-113">在啟用封存前，您應該先在封存配置中指定所有適當的選項。</span><span class="sxs-lookup"><span data-stu-id="07ca9-113">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="07ca9-114">如需詳細資訊，請參閱部署檔中的<A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013</A>中的 [設定封存選項]。</span><span class="sxs-lookup"><span data-stu-id="07ca9-114">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="07ca9-115">本節內容</span><span class="sxs-lookup"><span data-stu-id="07ca9-115">In This Section</span></span>

  - [<span data-ttu-id="07ca9-116">在 Lync Server 2013 中建立及設定用於存檔的使用者原則</span><span class="sxs-lookup"><span data-stu-id="07ca9-116">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="07ca9-117">在 Lync Server 2013 中將 Lync Server 存檔原則套用至使用者</span><span class="sxs-lookup"><span data-stu-id="07ca9-117">Applying a Lync Server Archiving policy to a user in Lync Server 2013</span></span>](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

