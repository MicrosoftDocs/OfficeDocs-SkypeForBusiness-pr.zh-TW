---
title: Lync Server 2013：設定通話駐留軌道表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b306733c42e125a97c6bee4a4a42c4d96b7ebd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a><span data-ttu-id="e4a90-102">在 Lync Server 2013 中設定通話駐留軌道表格</span><span class="sxs-lookup"><span data-stu-id="e4a90-102">Configure the Call Park orbit table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4a90-103">_**主題上次修改日期：** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="e4a90-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="e4a90-104">通話寄存使用 [軌道式] 進行停車通話。</span><span class="sxs-lookup"><span data-stu-id="e4a90-104">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="e4a90-105">您必須先設定 [通話公園軌道] 表格，才能停止並取回通話。</span><span class="sxs-lookup"><span data-stu-id="e4a90-105">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="e4a90-106">您必須指定貴組織將針對停車通話保留的延伸數位（軌道式）範圍，並指定哪個呼叫駐留器池處理每個範圍，以定義這些範圍的路線。</span><span class="sxs-lookup"><span data-stu-id="e4a90-106">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="e4a90-107">當您定義軌道範圍時，目標是有足夠的 [軌道式]，所以任何一個軌道都不會過快地重複使用，但卻不是您要限制使用者或其他服務可用的延伸數目。</span><span class="sxs-lookup"><span data-stu-id="e4a90-107">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="e4a90-108">您可以為部署通話駐留應用程式的每個 Lync 伺服器池建立多個通話駐留軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="e4a90-108">You can create multiple Call Park orbit ranges for each Lync Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="e4a90-109">每個呼叫公園的軌道範圍都必須有全域唯一的名稱，以及一組唯一的延伸。</span><span class="sxs-lookup"><span data-stu-id="e4a90-109">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e4a90-110">軌道範圍通常會包含100或更少的軌道式。</span><span class="sxs-lookup"><span data-stu-id="e4a90-110">An orbit range typically encompasses 100 or fewer orbits.</span></span> <span data-ttu-id="e4a90-111">每個範圍都可以大許多，只要它小於每個範圍的10000軌道式，且每個池子的每個泳池不超過50000的 [軌道式]。</span><span class="sxs-lookup"><span data-stu-id="e4a90-111">Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool.</span></span> <span data-ttu-id="e4a90-112">如果範圍太小，則會更快速地重複使用 [軌道式]。</span><span class="sxs-lookup"><span data-stu-id="e4a90-112">If a range is too small, the orbits are reused more quickly.</span></span>



</div>

<span data-ttu-id="e4a90-113">針對您的軌道範圍，使用虛擬延伸組塊（沒有指派使用者或電話的延伸）。</span><span class="sxs-lookup"><span data-stu-id="e4a90-113">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e4a90-114">在 [通話駐留軌道] 表格中，將直向內撥（所做的）號碼指派為軌道編號，不受支援。</span><span class="sxs-lookup"><span data-stu-id="e4a90-114">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e4a90-115">本節內容</span><span class="sxs-lookup"><span data-stu-id="e4a90-115">In This Section</span></span>

[<span data-ttu-id="e4a90-116">在 Lync Server 2013 中建立或修改通話駐留軌道的範圍</span><span class="sxs-lookup"><span data-stu-id="e4a90-116">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

