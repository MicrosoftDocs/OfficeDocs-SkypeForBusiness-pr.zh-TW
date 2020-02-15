---
title: Lync Server 2013： 新增或移除前端伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a13a7d618b7d7f8883d43e6aed7ac456bb5ab6c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a><span data-ttu-id="0b3ac-102">新增或移除 Lync Server 2013 中的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="0b3ac-102">Add or remove a Front End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b3ac-103">_**主題上次修改日期：** 2016年-01-21_</span><span class="sxs-lookup"><span data-stu-id="0b3ac-103">_**Topic Last Modified:** 2016-01-21_</span></span>

<span data-ttu-id="0b3ac-104">當您將前端伺服器新增至集區，或從集區移除前端伺服器時，您需要重新啟動集區。</span><span class="sxs-lookup"><span data-stu-id="0b3ac-104">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> <span data-ttu-id="0b3ac-105">若要避免服務中斷的使用者，請使用下列程序時新增或移除前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="0b3ac-105">To prevent any interruption of service to users, use the following procedure when adding or removing a Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b3ac-106">如果您正在加入新的伺服器集區，請更新您新的集區伺服器，以在相同的累計更新層級為現有的伺服器集區中。</span><span class="sxs-lookup"><span data-stu-id="0b3ac-106">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span>



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="0b3ac-107">若要新增或移除前端伺服器</span><span class="sxs-lookup"><span data-stu-id="0b3ac-107">To add or remove Front End servers</span></span>

1.  <span data-ttu-id="0b3ac-108">如果您要移除任何前端伺服器，請先停止這些伺服器的新連線。</span><span class="sxs-lookup"><span data-stu-id="0b3ac-108">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="0b3ac-109">若要這麼做，您可以使用下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0b3ac-109">To do so, you can use the following cmdlet:</span></span>
    
        Stop-CsWindowsServices -Graceful

2.  <span data-ttu-id="0b3ac-110">當正在移除的伺服器沒有目前的工作階段時，請在其上停止 Lync Server 服務。</span><span class="sxs-lookup"><span data-stu-id="0b3ac-110">When the servers being removed have no current sessions, stop Lync Server services on them.</span></span>

3.  <span data-ttu-id="0b3ac-111">開啟拓撲產生器，並新增或移除必要的伺服器。</span><span class="sxs-lookup"><span data-stu-id="0b3ac-111">Open Topology Builder, and add or remove the necessary servers.</span></span>

4.  <span data-ttu-id="0b3ac-112">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="0b3ac-112">Publish the topology.</span></span>

5.  <span data-ttu-id="0b3ac-113">如果集區已從擁有兩個前端伺服器到兩個以上，或兩台變成實際上兩個以上的伺服器，您需要輸入下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0b3ac-113">If the pool has gone from having two Front End Servers to more than two, or gone from more than two servers to exactly two, you need to type the following cmdlet:</span></span>
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    <span data-ttu-id="0b3ac-114">如果集區中有三個或多個伺服器，然後至少三個這些伺服器必須執行當您輸入此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0b3ac-114">If the pool has three or more servers, then at least three of those servers must be running when you type this cmdlet.</span></span>

6.  <span data-ttu-id="0b3ac-115">重新啟動所有前端伺服器集區，一次一個。</span><span class="sxs-lookup"><span data-stu-id="0b3ac-115">Restart all Front End Servers in the pool, one at a time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

