---
title: Lync Server 2013：新增或移除前端伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1fe1e81d3983b89d4f68111179c3adc7409bee2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a><span data-ttu-id="b5c45-102">在 Lync Server 2013 中新增或移除前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b5c45-102">Add or remove a Front End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5c45-103">_**主題上次修改日期：** 2016-01-21_</span><span class="sxs-lookup"><span data-stu-id="b5c45-103">_**Topic Last Modified:** 2016-01-21_</span></span>

<span data-ttu-id="b5c45-104">當您將前端伺服器新增到池中，或從池中移除前端伺服器時，您必須重新開機該池。</span><span class="sxs-lookup"><span data-stu-id="b5c45-104">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> <span data-ttu-id="b5c45-105">若要避免任何服務中斷給使用者，請在新增或移除前端伺服器時，請使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="b5c45-105">To prevent any interruption of service to users, use the following procedure when adding or removing a Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b5c45-106">如果您要新增伺服器至池中，請將新的池伺服器更新為與池中現有伺服器相同的累加更新層級。</span><span class="sxs-lookup"><span data-stu-id="b5c45-106">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span>



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="b5c45-107">新增或移除前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b5c45-107">To add or remove Front End servers</span></span>

1.  <span data-ttu-id="b5c45-108">如果您要移除任何前端伺服器，請先停止與這些伺服器建立新連線。</span><span class="sxs-lookup"><span data-stu-id="b5c45-108">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="b5c45-109">若要這樣做，您可以使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b5c45-109">To do so, you can use the following cmdlet:</span></span>
    
        Stop-CsWindowsServices -Graceful

2.  <span data-ttu-id="b5c45-110">如果要移除的伺服器沒有目前的會話，請在這些伺服器上停止 Lync Server 服務。</span><span class="sxs-lookup"><span data-stu-id="b5c45-110">When the servers being removed have no current sessions, stop Lync Server services on them.</span></span>

3.  <span data-ttu-id="b5c45-111">開啟拓撲建立器，然後新增或移除必要的伺服器。</span><span class="sxs-lookup"><span data-stu-id="b5c45-111">Open Topology Builder, and add or remove the necessary servers.</span></span>

4.  <span data-ttu-id="b5c45-112">發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="b5c45-112">Publish the topology.</span></span>

5.  <span data-ttu-id="b5c45-113">如果該池已超出兩個前端伺服器的數目，或從超過兩個伺服器，則必須輸入下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b5c45-113">If the pool has gone from having two Front End Servers to more than two, or gone from more than two servers to exactly two, you need to type the following cmdlet:</span></span>
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    <span data-ttu-id="b5c45-114">如果該池有三個以上的伺服器，則在您輸入這個 Cmdlet 時，至少必須執行其中三個伺服器。</span><span class="sxs-lookup"><span data-stu-id="b5c45-114">If the pool has three or more servers, then at least three of those servers must be running when you type this cmdlet.</span></span>

6.  <span data-ttu-id="b5c45-115">一次重新開機一個池中的所有前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="b5c45-115">Restart all Front End Servers in the pool, one at a time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

