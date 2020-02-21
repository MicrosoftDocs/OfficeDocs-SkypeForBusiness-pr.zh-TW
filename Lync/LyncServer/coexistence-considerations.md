---
title: 共存考量
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b31b8f3e534fc7b060f194f84310050a0386d8c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a><span data-ttu-id="65539-102">共存考量</span><span class="sxs-lookup"><span data-stu-id="65539-102">Coexistence considerations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65539-103">_**主題上次修改日期：** 2012年-10-06_</span><span class="sxs-lookup"><span data-stu-id="65539-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="65539-104">在移轉之後，只有在 Lync Server 2013，Persistent Chat Server 集區會存在，而且您可以解除委任舊版部署。</span><span class="sxs-lookup"><span data-stu-id="65539-104">After migration, only a Lync Server 2013, Persistent Chat Server pool will exist, and you can decommission your legacy deployment.</span></span>

<span data-ttu-id="65539-105">移轉完成之前及完全解除委任目前 Group Chat 伺服器部署之前，您可能會有任何下列的部署：</span><span class="sxs-lookup"><span data-stu-id="65539-105">Before migration completes and before you have decommissioned your current Group Chat Server deployment completely, you may have any of the following deployments:</span></span>

  - <span data-ttu-id="65539-106">Lync Server 2013，Persistent Chat Server 集區，必須裝載於 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="65539-106">Lync Server 2013, Persistent Chat Server pool, which must be homed on a Lync Server 2013 pool.</span></span>

  - <span data-ttu-id="65539-107">Lync Server 2010，Group Chat 集區，必須裝載於 Lync Server 2010 集區。</span><span class="sxs-lookup"><span data-stu-id="65539-107">Lync Server 2010, Group Chat pool, which must be homed on a Lync Server 2010 pool.</span></span>

  - <span data-ttu-id="65539-108">Office Communications Server 2007 R2 群組聊天集區，必須裝載於 Office Communications Server 2007 R2 集區。</span><span class="sxs-lookup"><span data-stu-id="65539-108">Office Communications Server 2007 R2 Group Chat pool, which must be homed on an Office Communications Server 2007 R2 pool.</span></span>

<span data-ttu-id="65539-109">這些部署可以並排存在。</span><span class="sxs-lookup"><span data-stu-id="65539-109">These deployments can exist side by side.</span></span> <span data-ttu-id="65539-110">不過類別、 聊天室及增益集一個部署中不互動中隨附的部署。</span><span class="sxs-lookup"><span data-stu-id="65539-110">However the categories, rooms, and add-ins in one deployment do not interact with those in the accompanying deployment.</span></span>

<span data-ttu-id="65539-111">使用手動組態時，舊版用戶端 （Group Chat 用戶端） 可以連線至一個集區，一次 Office Communications Server 2007 R2、 Lync Server 2010，Group Chat，或 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="65539-111">Using manual configuration, a legacy client (Group Chat client) can connect to one pool at a time for Office Communications Server 2007 R2, Lync Server 2010, Group Chat, or Lync Server 2013.</span></span>

<span data-ttu-id="65539-112">Lync 2013 （用戶端） 可以只與 Lync Server 2013，Persistent Chat Server 集區，不與舊版的 Group Chat Server 集區互動。</span><span class="sxs-lookup"><span data-stu-id="65539-112">The Lync 2013 (client) can interact only with the Lync Server 2013, Persistent Chat Server pool, not with legacy Group Chat Server pools.</span></span> <span data-ttu-id="65539-113">若要使用常設聊天室 Lync 2013 （用戶端） 中，使用者必須位於 Lync 2013 並啟用原則。</span><span class="sxs-lookup"><span data-stu-id="65539-113">To use Persistent Chat in a Lync 2013 (client), the user must be homed on Lync 2013 and enabled by policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

