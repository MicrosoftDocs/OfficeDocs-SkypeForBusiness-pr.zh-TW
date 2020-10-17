---
title: Lync Server 2013：新增或移除前端伺服器
description: Lync Server 2013：新增或移除前端伺服器。
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
ms.openlocfilehash: 297bbf42dbba3d4f9926fd5ab9e0d7ed79349dc4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571999"
---
# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a><span data-ttu-id="078bb-103">在 Lync Server 2013 中新增或移除前端伺服器</span><span class="sxs-lookup"><span data-stu-id="078bb-103">Add or remove a Front End Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="078bb-104">_**主題上次修改日期：** 2016-01-21_</span><span class="sxs-lookup"><span data-stu-id="078bb-104">_**Topic Last Modified:** 2016-01-21_</span></span>

<span data-ttu-id="078bb-105">當您將前端伺服器新增至集區，或從集區中移除前端伺服器時，您必須重新開機集區。</span><span class="sxs-lookup"><span data-stu-id="078bb-105">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> <span data-ttu-id="078bb-106">若要避免任何服務中斷給使用者，請在新增或移除前端伺服器時使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="078bb-106">To prevent any interruption of service to users, use the following procedure when adding or removing a Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="078bb-107">若要將新伺服器新增至集區，請將新的集區伺服器更新成與集區中現有伺服器相同的累計更新層級。</span><span class="sxs-lookup"><span data-stu-id="078bb-107">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span>



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="078bb-108">新增或移除前端伺服器</span><span class="sxs-lookup"><span data-stu-id="078bb-108">To add or remove Front End servers</span></span>

1.  <span data-ttu-id="078bb-109">如果您要移除任何前端伺服器，請先停止這些伺服器的新連線。</span><span class="sxs-lookup"><span data-stu-id="078bb-109">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="078bb-110">若要這麼做，您可以使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="078bb-110">To do so, you can use the following cmdlet:</span></span>
    
        Stop-CsWindowsServices -Graceful

2.  <span data-ttu-id="078bb-111">當要移除的伺服器沒有目前的會話時，請停止其上的 Lync Server 服務。</span><span class="sxs-lookup"><span data-stu-id="078bb-111">When the servers being removed have no current sessions, stop Lync Server services on them.</span></span>

3.  <span data-ttu-id="078bb-112">開啟拓撲產生器，並新增或移除必要的伺服器。</span><span class="sxs-lookup"><span data-stu-id="078bb-112">Open Topology Builder, and add or remove the necessary servers.</span></span>

4.  <span data-ttu-id="078bb-113">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="078bb-113">Publish the topology.</span></span>

5.  <span data-ttu-id="078bb-114">如果集區從兩部以上的伺服器到兩部以上，或從兩部以上的伺服器到兩部以上，您必須輸入下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="078bb-114">If the pool has gone from having two Front End Servers to more than two, or gone from more than two servers to exactly two, you need to type the following cmdlet:</span></span>
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    <span data-ttu-id="078bb-115">如果集區有三部以上的伺服器，當您輸入此 Cmdlet 時，至少必須執行三台伺服器。</span><span class="sxs-lookup"><span data-stu-id="078bb-115">If the pool has three or more servers, then at least three of those servers must be running when you type this cmdlet.</span></span>

6.  <span data-ttu-id="078bb-116">重新開機集區中的所有前端伺服器，一次一個。</span><span class="sxs-lookup"><span data-stu-id="078bb-116">Restart all Front End Servers in the pool, one at a time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

