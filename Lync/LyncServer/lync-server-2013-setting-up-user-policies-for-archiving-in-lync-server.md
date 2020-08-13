---
title: Lync Server 2013：在 Lync Server 中設定封存的使用者原則
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
ms.openlocfilehash: 8e032dd276ee41a711ded56d33a065d515b182ab
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="46aad-102">在 Lync Server 2013 中設定封存的使用者原則</span><span class="sxs-lookup"><span data-stu-id="46aad-102">Setting up user policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46aad-103">_**主題上次修改日期：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="46aad-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="46aad-104">啟用或停用駐留在 Lync Server 2013 之特定使用者的封存，需要建立及設定一或多個使用者原則，然後將適當的原則套用至特定使用者或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="46aad-104">Enabling or disabling Archiving for specific users homed on Lync Server 2013 requires creating and configuring one or more user policies, and then applying the appropriate policy to specific users or user groups.</span></span> <span data-ttu-id="46aad-105">使用者原則會覆寫網站和全域原則，但僅限於位於 Lync Server 2013 的使用者。</span><span class="sxs-lookup"><span data-stu-id="46aad-105">User policies override site and global policies, but only for users homed on Lync Server 2013.</span></span>

<span data-ttu-id="46aad-106">使用者永遠都是在 Lync Server 中託管。</span><span class="sxs-lookup"><span data-stu-id="46aad-106">Users are always homed in Lync Server.</span></span> <span data-ttu-id="46aad-107">如果啟用 Microsoft Exchange 整合，其信箱在 Microsoft Exchange Server 2013 中的使用者不需要在 Lync Server 中管理其封存原則。</span><span class="sxs-lookup"><span data-stu-id="46aad-107">If Microsoft Exchange integration is enabled, users whose mailboxes are in Microsoft Exchange Server 2013 don’t need to have their Archiving policies in Lync Server managed.</span></span> <span data-ttu-id="46aad-108">這些具有封存的使用者將由 Exchange In-Place 保留進行管理。</span><span class="sxs-lookup"><span data-stu-id="46aad-108">These users with Archiving will be managed by Exchange In-Place Hold.</span></span>

<span data-ttu-id="46aad-109">如需有關封存原則如何運作（包括全域、網站及使用者原則的階層）的詳細資訊，請參閱規劃檔、部署檔或作業檔中的封存[在 Lync Server 2013 中的運作方式](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="46aad-109">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46aad-110">如果您已針對您的部署啟用 Microsoft Exchange 整合，Exchange In-Place 保留原則會控制是否為位於 Exchange 2013 上的使用者啟用封存功能。</span><span class="sxs-lookup"><span data-stu-id="46aad-110">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013.</span></span> <span data-ttu-id="46aad-111">若要針對這些使用者啟用封存，則其信箱必須為就地保留狀態。</span><span class="sxs-lookup"><span data-stu-id="46aad-111">Archiving for these users requires that they have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="46aad-112">如需詳細資訊，請參閱部署檔中的<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定</A>封存的原則。</span><span class="sxs-lookup"><span data-stu-id="46aad-112">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="46aad-113">啟用封存前，應在封存組態中指定所有適當的選項。</span><span class="sxs-lookup"><span data-stu-id="46aad-113">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="46aad-114">如需詳細資訊，請參閱部署檔中的在<A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013</A>中設定封存選項。</span><span class="sxs-lookup"><span data-stu-id="46aad-114">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="46aad-115">本章節內容</span><span class="sxs-lookup"><span data-stu-id="46aad-115">In This Section</span></span>

  - [<span data-ttu-id="46aad-116">在 Lync Server 2013 中建立及設定封存的使用者原則</span><span class="sxs-lookup"><span data-stu-id="46aad-116">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="46aad-117">將 Lync Server 封存原則套用至 Lync Server 2013 中的使用者</span><span class="sxs-lookup"><span data-stu-id="46aad-117">Applying a Lync Server Archiving policy to a user in Lync Server 2013</span></span>](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

