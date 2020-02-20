---
title: Lync Server 2013： 設定通話駐留軌道表
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
ms.openlocfilehash: 03cb3556ab0111d7bc61de6bc0914b5a3514a7cd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a><span data-ttu-id="0f621-102">Lync Server 2013 中設定通話駐留軌道表</span><span class="sxs-lookup"><span data-stu-id="0f621-102">Configure the Call Park orbit table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f621-103">_**主題上次修改日期：** 2012年-09-10_</span><span class="sxs-lookup"><span data-stu-id="0f621-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="0f621-104">通話駐留使用軌道駐留通話。</span><span class="sxs-lookup"><span data-stu-id="0f621-104">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="0f621-105">使用者可以駐留與擷取通話之前，您必須設定通話駐留軌道表。</span><span class="sxs-lookup"><span data-stu-id="0f621-105">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="0f621-106">您需要指定範圍的分機號碼 （軌道） 組織會保留駐留通話，並定義這些範圍的路由，藉由指定的通話駐留集區處理每個範圍。</span><span class="sxs-lookup"><span data-stu-id="0f621-106">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="0f621-107">當您定義軌道範圍時，目標是具有足夠的軌道，因此任何一個軌道不會重複使用過快，但不是太軌道您限制適用於使用者的分機或其他服務的數目。</span><span class="sxs-lookup"><span data-stu-id="0f621-107">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="0f621-108">您可以建立多個通話駐留軌道範圍，每個 Lync 伺服器集區部署通話駐留應用程式的位置。</span><span class="sxs-lookup"><span data-stu-id="0f621-108">You can create multiple Call Park orbit ranges for each Lync Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="0f621-109">每個通話駐留軌道範圍必須擁有的全域唯一的名稱以及一組獨特的副檔名。</span><span class="sxs-lookup"><span data-stu-id="0f621-109">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0f621-110">軌道範圍通常圍繞 100 或更少的軌道。</span><span class="sxs-lookup"><span data-stu-id="0f621-110">An orbit range typically encompasses 100 or fewer orbits.</span></span> <span data-ttu-id="0f621-111">前提是它小於最大值為 10000 軌道範圍每以及每個集區有 50000 個以下的軌道，每個範圍可以是更大。</span><span class="sxs-lookup"><span data-stu-id="0f621-111">Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool.</span></span> <span data-ttu-id="0f621-112">如果範圍是太小，軌道更快速地重複使用。</span><span class="sxs-lookup"><span data-stu-id="0f621-112">If a range is too small, the orbits are reused more quickly.</span></span>



</div>

<span data-ttu-id="0f621-113">針對軌道範圍使用虛擬分機 （沒有任何使用者或電話指派給他們的分機） 區塊。</span><span class="sxs-lookup"><span data-stu-id="0f621-113">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0f621-114">不支援將直接向內撥號 (DID) 號碼指派為中通話駐留軌道數字軌道表。</span><span class="sxs-lookup"><span data-stu-id="0f621-114">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0f621-115">本章節內容</span><span class="sxs-lookup"><span data-stu-id="0f621-115">In This Section</span></span>

[<span data-ttu-id="0f621-116">建立或修改通話駐留軌道範圍在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f621-116">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

