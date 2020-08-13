---
title: Lync Server 2013：還原 Lync Server 集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Lync Server pool
ms:assetid: 6fe80fb3-38ad-4931-a07b-1763b61aa448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202176(v=OCS.15)
ms:contentKeyID: 51541488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 294b276dbfe12af7b6b2fbd1bca285920431ce9c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-lync-server-pool-in-lync-server-2013"></a><span data-ttu-id="2d859-102">在 Lync Server 2013 中還原 Lync Server 集區</span><span class="sxs-lookup"><span data-stu-id="2d859-102">Restoring a Lync Server pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d859-103">_**主題上次修改日期：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="2d859-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="2d859-104">您的 Lync Server 部署可能包含下列任一類型的集區：</span><span class="sxs-lookup"><span data-stu-id="2d859-104">Your Lync Server deployment may include any of the following types of pools:</span></span>

  - <span data-ttu-id="2d859-105">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="2d859-105">Front End Server</span></span>

  - <span data-ttu-id="2d859-106">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="2d859-106">Mediation Server</span></span>

  - <span data-ttu-id="2d859-107">常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="2d859-107">Persistent Chat Server</span></span>

  - <span data-ttu-id="2d859-108">Edge Server</span><span class="sxs-lookup"><span data-stu-id="2d859-108">Edge Server</span></span>

<span data-ttu-id="2d859-109">如果整個集區經歷中斷，請針對集區中的每個成員伺服器執行下列程式。</span><span class="sxs-lookup"><span data-stu-id="2d859-109">If an entire pool experiences an outage, follow these procedures for each member server in the pool.</span></span>

  - <span data-ttu-id="2d859-110">若為前端集區，請先還原後端伺服器，然後還原每一部前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="2d859-110">For a Front End pool, restore the Back End Server first, and then restore each Front End Server.</span></span> <span data-ttu-id="2d859-111">如需詳細資訊，請參閱在 lync server [2013 中還原 Enterprise Edition 後端伺服器](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) 及 [還原 lync server 2013 中的 enterprise edition 成員伺服器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。</span><span class="sxs-lookup"><span data-stu-id="2d859-111">For details, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) and [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

  - <span data-ttu-id="2d859-112">若是所有其他類型的集區，則請還原每個成員伺服器。</span><span class="sxs-lookup"><span data-stu-id="2d859-112">For all other types of pools, restore each member server.</span></span> <span data-ttu-id="2d859-113">如需詳細資訊，請參閱 [在 Lync server 2013 中還原 Enterprise Edition 成員伺服器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。</span><span class="sxs-lookup"><span data-stu-id="2d859-113">For details, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

