---
title: Lync Server 2013：翻譯規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22b6fbacf068f6a1a388a968989259afec81d17a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a><span data-ttu-id="70803-102">Lync Server 2013 中的翻譯規則</span><span class="sxs-lookup"><span data-stu-id="70803-102">Translation rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70803-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="70803-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="70803-104">Lync Server 2013 企業語音要求將所有撥號字串標準化為 E.i 格式，以執行反向數位查閱（RNL）。</span><span class="sxs-lookup"><span data-stu-id="70803-104">Lync Server 2013 Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="70803-105">在 Microsoft Lync Server 2010 中，只能針對呼叫的號碼支援翻譯規則。</span><span class="sxs-lookup"><span data-stu-id="70803-105">In Microsoft Lync Server 2010, translation rules are supported only for called numbers.</span></span> <span data-ttu-id="70803-106">Microsoft Lync Server 2013 中的新功能在通話編號中也支援翻譯規則。</span><span class="sxs-lookup"><span data-stu-id="70803-106">New in Microsoft Lync Server 2013, translation rules are also supported for calling numbers.</span></span> <span data-ttu-id="70803-107">*幹線對等*（也就是關聯的閘道、私人分支 EXCHANGE （PBX）或 SIP 幹線）可能需要使用本機撥號格式。</span><span class="sxs-lookup"><span data-stu-id="70803-107">The *trunk peer* (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="70803-108">若要將數位（164格式）轉換成本機撥號格式，您可以定義一或多個翻譯規則，在將要求 URI 傳送到幹線對等前，先進行處理。</span><span class="sxs-lookup"><span data-stu-id="70803-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="70803-109">例如，您可以撰寫轉譯規則，從撥號字串的開頭移除 +44 並替換成 0144。</span><span class="sxs-lookup"><span data-stu-id="70803-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="70803-110">透過在伺服器上執行輸出路由轉換，您可以減少每個個別中繼對等的設定需求，以將電話號碼轉譯為本機撥號格式。</span><span class="sxs-lookup"><span data-stu-id="70803-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="70803-111">當您規劃哪些閘道以及要與特定的中繼伺服器群集建立關聯的閘道數時，可能會對幹線對等進行類似的本機撥號需求群組有所説明。</span><span class="sxs-lookup"><span data-stu-id="70803-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="70803-112">這樣可以減少所需翻譯規則的數目，以及撰寫它們所需的時間。</span><span class="sxs-lookup"><span data-stu-id="70803-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="70803-113">將一或多個翻譯規則與企業語音幹線設定建立關聯，就應該使用此替代方法，以在幹線對等上設定翻譯規則。</span><span class="sxs-lookup"><span data-stu-id="70803-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="70803-114">如果您已在幹線對等上設定翻譯規則，請不要將翻譯規則與企業語音幹線配置建立關聯，因為這兩個規則可能會衝突。</span><span class="sxs-lookup"><span data-stu-id="70803-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>



</div>

<div>

## <a name="example-translation-rules"></a><span data-ttu-id="70803-115">翻譯規則範例</span><span class="sxs-lookup"><span data-stu-id="70803-115">Example Translation Rules</span></span>

<span data-ttu-id="70803-116">下列翻譯規則範例會示範如何在伺服器上開發規則，將數位從 E.i 格式轉譯為幹線對等的本機格式。</span><span class="sxs-lookup"><span data-stu-id="70803-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="70803-117">如需如何實現翻譯規則的詳細資料，請參閱在部署檔中的[Lync Server 2013 定義翻譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="70803-117">For details about how to implement translation rules, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>


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
<th><span data-ttu-id="70803-118">描述</span><span class="sxs-lookup"><span data-stu-id="70803-118">Description</span></span></th>
<th><span data-ttu-id="70803-119">起始位數</span><span class="sxs-lookup"><span data-stu-id="70803-119">Starting Digits</span></span></th>
<th><span data-ttu-id="70803-120">全長</span><span class="sxs-lookup"><span data-stu-id="70803-120">Length</span></span></th>
<th><span data-ttu-id="70803-121">移除的位數</span><span class="sxs-lookup"><span data-stu-id="70803-121">Digits to Remove</span></span></th>
<th><span data-ttu-id="70803-122">要新增的位數</span><span class="sxs-lookup"><span data-stu-id="70803-122">Digits to Add</span></span></th>
<th><span data-ttu-id="70803-123">相符的模式</span><span class="sxs-lookup"><span data-stu-id="70803-123">Matching Pattern</span></span></th>
<th><span data-ttu-id="70803-124">翻譯</span><span class="sxs-lookup"><span data-stu-id="70803-124">Translation</span></span></th>
<th><span data-ttu-id="70803-125">範例</span><span class="sxs-lookup"><span data-stu-id="70803-125">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70803-126">美國的傳統長途電話撥號</span><span class="sxs-lookup"><span data-stu-id="70803-126">Conventional long-distance dialing in U.S.</span></span></p>
<p><span data-ttu-id="70803-127">（去除 "+"）</span><span class="sxs-lookup"><span data-stu-id="70803-127">(strip out the ‘+’)</span></span></p></td>
<td><p><span data-ttu-id="70803-128">+ 1</span><span class="sxs-lookup"><span data-stu-id="70803-128">+1</span></span></p></td>
<td><p><span data-ttu-id="70803-129">恰好12</span><span class="sxs-lookup"><span data-stu-id="70803-129">Exactly 12</span></span></p></td>
<td><p><span data-ttu-id="70803-130">1</span><span class="sxs-lookup"><span data-stu-id="70803-130">1</span></span></p></td>
<td><p><span data-ttu-id="70803-131">0</span><span class="sxs-lookup"><span data-stu-id="70803-131">0</span></span></p></td>
<td><p><span data-ttu-id="70803-132">^\+（1 \ d{10}） $</span><span class="sxs-lookup"><span data-stu-id="70803-132">^\+(1\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="70803-133">$1</span><span class="sxs-lookup"><span data-stu-id="70803-133">$1</span></span></p></td>
<td><p><span data-ttu-id="70803-134">+ 14255551010 變成14255551010</span><span class="sxs-lookup"><span data-stu-id="70803-134">+14255551010 becomes 14255551010</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70803-135">美國國際長途撥號</span><span class="sxs-lookup"><span data-stu-id="70803-135">U.S. international long-distance dialing</span></span></p>
<p><span data-ttu-id="70803-136">（去除 "+" 並加上011）</span><span class="sxs-lookup"><span data-stu-id="70803-136">(strip out ‘+’ and add 011)</span></span></p></td>
<td><p>+</p></td>
<td><p><span data-ttu-id="70803-137">至少11</span><span class="sxs-lookup"><span data-stu-id="70803-137">At least 11</span></span></p></td>
<td><p><span data-ttu-id="70803-138">1</span><span class="sxs-lookup"><span data-stu-id="70803-138">1</span></span></p></td>
<td><p><span data-ttu-id="70803-139">011</span><span class="sxs-lookup"><span data-stu-id="70803-139">011</span></span></p></td>
<td><p><span data-ttu-id="70803-140">^\+（\d{9}\d +） $</span><span class="sxs-lookup"><span data-stu-id="70803-140">^\+(\d{9}\d+)$</span></span></p></td>
<td><p><span data-ttu-id="70803-141">011 $ 1</span><span class="sxs-lookup"><span data-stu-id="70803-141">011$1</span></span></p></td>
<td><p><span data-ttu-id="70803-142">+ 441235551010 變成011441235551010</span><span class="sxs-lookup"><span data-stu-id="70803-142">+441235551010 becomes 011441235551010</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

