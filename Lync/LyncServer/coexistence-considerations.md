---
title: 共存考慮
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: cdad93eaf8debbc616099c1454d5e39438a63474
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499670"
---
# <a name="coexistence-considerations"></a><span data-ttu-id="f5618-102">共存考慮</span><span class="sxs-lookup"><span data-stu-id="f5618-102">Coexistence considerations</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5618-103">_**主題上次修改日期：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="f5618-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="f5618-104">遷移後，只會存在 Lync Server 2013、Persistent Chat Server 集區，您也可解除委任舊版部署。</span><span class="sxs-lookup"><span data-stu-id="f5618-104">After migration, only a Lync Server 2013, Persistent Chat Server pool will exist, and you can decommission your legacy deployment.</span></span>

<span data-ttu-id="f5618-105">在遷移完成之前以及完全解除委任目前的群組聊天伺服器部署之前，您可能會有下列任何部署：</span><span class="sxs-lookup"><span data-stu-id="f5618-105">Before migration completes and before you have decommissioned your current Group Chat Server deployment completely, you may have any of the following deployments:</span></span>

  - <span data-ttu-id="f5618-106">Lync Server 2013，Persistent Chat Server 集區，必須裝載在 Lync Server 2013 集區上。</span><span class="sxs-lookup"><span data-stu-id="f5618-106">Lync Server 2013, Persistent Chat Server pool, which must be homed on a Lync Server 2013 pool.</span></span>

  - <span data-ttu-id="f5618-107">Lync Server 2010，群組聊天集區，必須裝載在 Lync Server 2010 集區上。</span><span class="sxs-lookup"><span data-stu-id="f5618-107">Lync Server 2010, Group Chat pool, which must be homed on a Lync Server 2010 pool.</span></span>

  - <span data-ttu-id="f5618-108">Office 通訊伺服器 2007 R2 群組聊天集區，必須位於 Office 通訊伺服器 2007 R2 集區。</span><span class="sxs-lookup"><span data-stu-id="f5618-108">Office Communications Server 2007 R2 Group Chat pool, which must be homed on an Office Communications Server 2007 R2 pool.</span></span>

<span data-ttu-id="f5618-109">這些部署可能並排存在。</span><span class="sxs-lookup"><span data-stu-id="f5618-109">These deployments can exist side by side.</span></span> <span data-ttu-id="f5618-110">不過，一個部署中的類別、聊天室及增益集不會與伴隨之部署中的增益集進行互動。</span><span class="sxs-lookup"><span data-stu-id="f5618-110">However the categories, rooms, and add-ins in one deployment do not interact with those in the accompanying deployment.</span></span>

<span data-ttu-id="f5618-111">使用手動設定時，舊版用戶端 (群組聊天用戶端) 可以一次連線至一個集區，以進行 Office 通訊伺服器 2007 R2、Lync Server 2010、群組聊天或 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="f5618-111">Using manual configuration, a legacy client (Group Chat client) can connect to one pool at a time for Office Communications Server 2007 R2, Lync Server 2010, Group Chat, or Lync Server 2013.</span></span>

<span data-ttu-id="f5618-112">Lync 2013 (用戶端) 只能與 Lync Server 2013、Persistent Chat Server 集區互動，而不能與舊版群組聊天伺服器集區互動。</span><span class="sxs-lookup"><span data-stu-id="f5618-112">The Lync 2013 (client) can interact only with the Lync Server 2013, Persistent Chat Server pool, not with legacy Group Chat Server pools.</span></span> <span data-ttu-id="f5618-113">若要在 Lync 2013 (用戶端) 中使用持續性聊天，使用者必須在 Lync 2013 上，並由原則啟用。</span><span class="sxs-lookup"><span data-stu-id="f5618-113">To use Persistent Chat in a Lync 2013 (client), the user must be homed on Lync 2013 and enabled by policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

