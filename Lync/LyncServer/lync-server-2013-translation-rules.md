---
title: Lync Server 2013：轉譯規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 783d2bb8de49fc7660998fcf3cbcb7cdb5c18e8b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530350"
---
# <a name="translation-rules-in-lync-server-2013"></a><span data-ttu-id="2ce0b-102">Lync Server 2013 中的轉譯規則</span><span class="sxs-lookup"><span data-stu-id="2ce0b-102">Translation rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ce0b-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="2ce0b-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="2ce0b-104">Lync Server 2013 Enterprise Voice 要求所有撥號字串都正常化為 e.164 格式，以執行反向號碼查閱 (RNL) 。</span><span class="sxs-lookup"><span data-stu-id="2ce0b-104">Lync Server 2013 Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="2ce0b-105">在 Microsoft Lync Server 2010 中，只支援呼叫的號碼的轉譯規則。</span><span class="sxs-lookup"><span data-stu-id="2ce0b-105">In Microsoft Lync Server 2010, translation rules are supported only for called numbers.</span></span> <span data-ttu-id="2ce0b-106">Microsoft Lync Server 2013 中的新功能，翻譯規則也支援通話號碼。</span><span class="sxs-lookup"><span data-stu-id="2ce0b-106">New in Microsoft Lync Server 2013, translation rules are also supported for calling numbers.</span></span> <span data-ttu-id="2ce0b-107">*「主幹對等」*(亦即相關聯的閘道、專用交換機 (PBX) 或 SIP 主幹) 可能要求號碼必須為本地撥號格式。</span><span class="sxs-lookup"><span data-stu-id="2ce0b-107">The *trunk peer* (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="2ce0b-108">若要將號碼從 E.164 格式轉譯為本地撥號格式，則可以先定義一或多個轉譯規則來操作要求 URI，再將其路由傳送至主幹對等。</span><span class="sxs-lookup"><span data-stu-id="2ce0b-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="2ce0b-109">例如，您可以撰寫轉譯規則，移除撥號字串開頭的 +44，並改為 0144。</span><span class="sxs-lookup"><span data-stu-id="2ce0b-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="2ce0b-110">在伺服器上執行輸出路由轉譯，則可以減少在每個個別主幹對等上的設定需求，以將電話號碼轉譯為區域撥號格式。</span><span class="sxs-lookup"><span data-stu-id="2ce0b-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="2ce0b-111">當您規劃要與特定的轉送伺服器叢集產生關聯的閘道和數目的閘道時，群組主幹對等的功能可能會非常實用，具有類似的本機撥號需求。</span><span class="sxs-lookup"><span data-stu-id="2ce0b-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="2ce0b-112">如此，可減少所需的轉譯規則數目以及寫入它們所需的時間。</span><span class="sxs-lookup"><span data-stu-id="2ce0b-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2ce0b-113">將一個或多個轉譯規則與企業語音主幹設定相關聯，應做為其他方式，以在主幹對等上設定轉譯規則。</span><span class="sxs-lookup"><span data-stu-id="2ce0b-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="2ce0b-114">如果您已在主幹對等上設定轉譯規則，請勿將轉譯規則與 Enterprise Voice 主幹設定產生關聯，因為這兩個規則可能會衝突。</span><span class="sxs-lookup"><span data-stu-id="2ce0b-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>



</div>

<div>

## <a name="example-translation-rules"></a><span data-ttu-id="2ce0b-115">範例轉譯規則</span><span class="sxs-lookup"><span data-stu-id="2ce0b-115">Example Translation Rules</span></span>

<span data-ttu-id="2ce0b-116">下列轉譯規則範例顯示如何在伺服器上開發規則，以將號碼從 E.164 格式轉譯為主幹對等的區域格式。</span><span class="sxs-lookup"><span data-stu-id="2ce0b-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="2ce0b-117">如需如何執行轉譯規則的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md) 。</span><span class="sxs-lookup"><span data-stu-id="2ce0b-117">For details about how to implement translation rules, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ce0b-118">描述</span><span class="sxs-lookup"><span data-stu-id="2ce0b-118">Description</span></span></th>
<th><span data-ttu-id="2ce0b-119">開頭數字</span><span class="sxs-lookup"><span data-stu-id="2ce0b-119">Starting Digits</span></span></th>
<th><span data-ttu-id="2ce0b-120">長度</span><span class="sxs-lookup"><span data-stu-id="2ce0b-120">Length</span></span></th>
<th><span data-ttu-id="2ce0b-121">要移除的數字</span><span class="sxs-lookup"><span data-stu-id="2ce0b-121">Digits to Remove</span></span></th>
<th><span data-ttu-id="2ce0b-122">要加入的數字</span><span class="sxs-lookup"><span data-stu-id="2ce0b-122">Digits to Add</span></span></th>
<th><span data-ttu-id="2ce0b-123">比對模式</span><span class="sxs-lookup"><span data-stu-id="2ce0b-123">Matching Pattern</span></span></th>
<th><span data-ttu-id="2ce0b-124">Translation</span><span class="sxs-lookup"><span data-stu-id="2ce0b-124">Translation</span></span></th>
<th><span data-ttu-id="2ce0b-125">範例</span><span class="sxs-lookup"><span data-stu-id="2ce0b-125">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ce0b-126">美國的傳統長途撥號</span><span class="sxs-lookup"><span data-stu-id="2ce0b-126">Conventional long-distance dialing in U.S.</span></span></p>
<p><span data-ttu-id="2ce0b-127">(除去 ‘+’)</span><span class="sxs-lookup"><span data-stu-id="2ce0b-127">(strip out the ‘+’)</span></span></p></td>
<td><p><span data-ttu-id="2ce0b-128">+ 1</span><span class="sxs-lookup"><span data-stu-id="2ce0b-128">+1</span></span></p></td>
<td><p><span data-ttu-id="2ce0b-129">剛好 12 個</span><span class="sxs-lookup"><span data-stu-id="2ce0b-129">Exactly 12</span></span></p></td>
<td><p><span data-ttu-id="2ce0b-130">1 </span><span class="sxs-lookup"><span data-stu-id="2ce0b-130">1</span></span></p></td>
<td><p><span data-ttu-id="2ce0b-131">0</span><span class="sxs-lookup"><span data-stu-id="2ce0b-131">0</span></span></p></td>
<td><p><span data-ttu-id="2ce0b-132">^\+ (1 維 {10}) $</span><span class="sxs-lookup"><span data-stu-id="2ce0b-132">^\+(1\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="2ce0b-133">$1</span><span class="sxs-lookup"><span data-stu-id="2ce0b-133">$1</span></span></p></td>
<td><p><span data-ttu-id="2ce0b-134">+14255551010 變成 14255551010</span><span class="sxs-lookup"><span data-stu-id="2ce0b-134">+14255551010 becomes 14255551010</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ce0b-135">美國國際長途撥號</span><span class="sxs-lookup"><span data-stu-id="2ce0b-135">U.S. international long-distance dialing</span></span></p>
<p><span data-ttu-id="2ce0b-136">(除去 ‘+’ 並加上 011)</span><span class="sxs-lookup"><span data-stu-id="2ce0b-136">(strip out ‘+’ and add 011)</span></span></p></td>
<td><p>+</p></td>
<td><p><span data-ttu-id="2ce0b-137">至少 11 個</span><span class="sxs-lookup"><span data-stu-id="2ce0b-137">At least 11</span></span></p></td>
<td><p><span data-ttu-id="2ce0b-138">1 </span><span class="sxs-lookup"><span data-stu-id="2ce0b-138">1</span></span></p></td>
<td><p><span data-ttu-id="2ce0b-139">011</span><span class="sxs-lookup"><span data-stu-id="2ce0b-139">011</span></span></p></td>
<td><p><span data-ttu-id="2ce0b-140">^\+ ( \d {9} \d +) $</span><span class="sxs-lookup"><span data-stu-id="2ce0b-140">^\+(\d{9}\d+)$</span></span></p></td>
<td><p><span data-ttu-id="2ce0b-141">011 $ 1</span><span class="sxs-lookup"><span data-stu-id="2ce0b-141">011$1</span></span></p></td>
<td><p><span data-ttu-id="2ce0b-142">+441235551010 變成 011441235551010</span><span class="sxs-lookup"><span data-stu-id="2ce0b-142">+441235551010 becomes 011441235551010</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

