---
title: 使用 Exchange Server 整合設定存檔原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up policies for Archiving when using Exchange Server integration
ms:assetid: 8b9b2bad-a4b3-42e1-85a7-04022e9442ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205063(v=OCS.15)
ms:contentKeyID: 48184742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78e5f5bf1bcfa9b11a96722df1f6ff7535912bb1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-policies-for-archiving-in-lync-server-2013-when-using-exchange-server-integration"></a><span data-ttu-id="41d87-102">使用 Exchange Server 整合時，在 Lync Server 2013 中設定存檔原則</span><span class="sxs-lookup"><span data-stu-id="41d87-102">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41d87-103">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="41d87-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="41d87-104">如果您駐留在 Exchange 2013 的使用者將其信箱放在適當位置，Exchange 就地保留原則會控制這些使用者的封存。</span><span class="sxs-lookup"><span data-stu-id="41d87-104">If users homed on Exchange 2013 have their mailboxes put on In-Place Hold, Exchange In-Place Hold policies control archiving for those users.</span></span> <span data-ttu-id="41d87-105">如果您是針對您的部署使用 Microsoft Exchange 整合，Exchange 2013 原則會覆寫託管于 Exchange 2013 的使用者的 Lync Server 封存原則。</span><span class="sxs-lookup"><span data-stu-id="41d87-105">If you use Microsoft Exchange integration for your deployment, Exchange 2013 policies override Lync Server Archiving policies for users who are homed on Exchange 2013.</span></span> <span data-ttu-id="41d87-106">如需設定 Exchange 歸檔原則的相關資訊，請參閱 Exchange 2013 檔。</span><span class="sxs-lookup"><span data-stu-id="41d87-106">For information about configuring Exchange Archiving policies, see the Exchange 2013 documentation.</span></span> <span data-ttu-id="41d87-107">如需針對駐留在 Lync Server 2013 的使用者設定使用者原則的詳細資訊，請參閱部署檔中的 [[在 Lync Server 2013 中設定存檔的使用者原則](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)]。</span><span class="sxs-lookup"><span data-stu-id="41d87-107">For details about setting up user policies for users homed on Lync Server 2013, see [Setting up user policies for Archiving in Lync Server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) in the Deployment documentation.</span></span> <span data-ttu-id="41d87-108">如需原則運作方式的詳細資訊，請參閱在規劃檔、部署檔或作業檔中，在[Lync Server 2013](lync-server-2013-how-archiving-works.md)中進行封存的工作。</span><span class="sxs-lookup"><span data-stu-id="41d87-108">For details about how policies work, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="41d87-109">如果您在同一個林中部署 Exchange 2013 和 Lync Server 2013，您的 Exchange 2013 就地保留原則會控制封存。</span><span class="sxs-lookup"><span data-stu-id="41d87-109">If you deploy Exchange 2013 and Lync Server 2013 in the same forest, your Exchange 2013 In-Place Hold policies control archiving.</span></span> <span data-ttu-id="41d87-110">如果您在個別的目錄林中部署 Exchange 2013 和 Lync Server 2013，請參閱在<A href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 中進行封存之部署檢查清單中的</A>「部署 Lync Server 和 Microsoft Exchange （在不同的林中）」）。</span><span class="sxs-lookup"><span data-stu-id="41d87-110">If you deploy Exchange 2013 and Lync Server 2013 in separate forests, see “Deploying Lync Server and Microsoft Exchange in Different Forests” in <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

