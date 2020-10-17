---
title: Lync Server 2013：設定通話駐留軌道表格
description: Lync Server 2013：設定通話駐留軌道表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce9fb35c2958a426888d83d075064c88ddae4bfa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544979"
---
# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a><span data-ttu-id="6f6cb-103">在 Lync Server 2013 中設定通話駐留軌道表格</span><span class="sxs-lookup"><span data-stu-id="6f6cb-103">Configure the Call Park orbit table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f6cb-104">_**主題上次修改日期：** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="6f6cb-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="6f6cb-105">通話駐留使用軌道進行停車通話。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-105">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="6f6cb-106">您必須先設定通話駐留軌道表格，使用者才能駐留及取回通話。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="6f6cb-107">您必須指定您的組織將保留用於停車通話的分機號碼範圍 (的軌道式) ，並指定處理每個範圍的通話駐留集區，以定義這些範圍的路由。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="6f6cb-108">當您定義軌道範圍時，目標是具有足夠的軌道，因此，任何一個軌道都不會很快地重複使用，但卻不是這麼多的軌道來限制使用者或其他服務可使用的延伸數目。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="6f6cb-109">您可以針對部署通話駐留應用程式的每個 Lync 伺服器集區，建立多個通話駐留軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-109">You can create multiple Call Park orbit ranges for each Lync Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="6f6cb-110">每個通話駐留軌道範圍必須具有全域唯一名稱和一組唯一的延伸。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6f6cb-111">軌道範圍通常會包含100或更少的軌道。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-111">An orbit range typically encompasses 100 or fewer orbits.</span></span> <span data-ttu-id="6f6cb-112">每個範圍都可以大量增加，只要小於每個範圍的10000軌道的最大值，且每個集區的每個集數目小於50000的軌道。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-112">Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool.</span></span> <span data-ttu-id="6f6cb-113">如果範圍太小，則軌道的重複使用速度變快。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-113">If a range is too small, the orbits are reused more quickly.</span></span>



</div>

<span data-ttu-id="6f6cb-114">使用虛擬分機區塊 (未獲指派使用者或電話的分機) 用於軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-114">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6f6cb-115">指派直接向內撥號 (，不支援通話駐留軌道表格中的軌道編號) 數位。</span><span class="sxs-lookup"><span data-stu-id="6f6cb-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6f6cb-116">本章節內容</span><span class="sxs-lookup"><span data-stu-id="6f6cb-116">In This Section</span></span>

[<span data-ttu-id="6f6cb-117">在 Lync Server 2013 中建立或修改通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="6f6cb-117">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

