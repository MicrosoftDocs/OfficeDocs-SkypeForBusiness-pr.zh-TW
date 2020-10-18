---
title: 使用 Exchange Server 整合時設定封存原則
description: 使用 Exchange Server 整合時設定封存原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up policies for Archiving when using Exchange Server integration
ms:assetid: 8b9b2bad-a4b3-42e1-85a7-04022e9442ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205063(v=OCS.15)
ms:contentKeyID: 48184742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8281d27101c049b1029a2005ed062a934438afc5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579459"
---
# <a name="setting-up-policies-for-archiving-in-lync-server-2013-when-using-exchange-server-integration"></a><span data-ttu-id="e5c67-103">使用 Exchange Server 整合時設定在 Lync Server 2013 中封存的原則</span><span class="sxs-lookup"><span data-stu-id="e5c67-103">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5c67-104">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="e5c67-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="e5c67-105">如果位於 Exchange 2013 的使用者已將其信箱置於 In-Place 保留狀態，Exchange In-Place 保留原則會控制這些使用者的封存。</span><span class="sxs-lookup"><span data-stu-id="e5c67-105">If users homed on Exchange 2013 have their mailboxes put on In-Place Hold, Exchange In-Place Hold policies control archiving for those users.</span></span> <span data-ttu-id="e5c67-106">如果您使用 Microsoft Exchange 整合進行部署，Exchange 2013 原則會覆寫位於 Exchange 2013 之使用者的 Lync Server 封存原則。</span><span class="sxs-lookup"><span data-stu-id="e5c67-106">If you use Microsoft Exchange integration for your deployment, Exchange 2013 policies override Lync Server Archiving policies for users who are homed on Exchange 2013.</span></span> <span data-ttu-id="e5c67-107">如需設定 Exchange 封存原則的詳細資訊，請參閱 Exchange 2013 檔。</span><span class="sxs-lookup"><span data-stu-id="e5c67-107">For information about configuring Exchange Archiving policies, see the Exchange 2013 documentation.</span></span> <span data-ttu-id="e5c67-108">如需針對駐留在 Lync Server 2013 之使用者設定使用者原則的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中設定封存的使用者原則](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="e5c67-108">For details about setting up user policies for users homed on Lync Server 2013, see [Setting up user policies for Archiving in Lync Server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) in the Deployment documentation.</span></span> <span data-ttu-id="e5c67-109">如需原則運作方式的詳細資訊，請參閱規劃檔、部署檔或作業檔中的 [如何在 Lync Server 2013 中運作](lync-server-2013-how-archiving-works.md) 封存。</span><span class="sxs-lookup"><span data-stu-id="e5c67-109">For details about how policies work, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="e5c67-110">如果您在相同樹系中部署 Exchange 2013 和 Lync Server 2013，Exchange 2013 In-Place 保留原則控制封存。</span><span class="sxs-lookup"><span data-stu-id="e5c67-110">If you deploy Exchange 2013 and Lync Server 2013 in the same forest, your Exchange 2013 In-Place Hold policies control archiving.</span></span> <span data-ttu-id="e5c67-111">若要在不同的樹系中部署 Exchange 2013 和 Lync Server 2013，請參閱 <A href="lync-server-2013-deployment-checklist-for-archiving.md">部署檢查清單中的</A>「在不同的樹系中部署 Lync Server 和 Microsoft Exchange」，以在 Lync Server 2013 中封存。</span><span class="sxs-lookup"><span data-stu-id="e5c67-111">If you deploy Exchange 2013 and Lync Server 2013 in separate forests, see “Deploying Lync Server and Microsoft Exchange in Different Forests” in <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

