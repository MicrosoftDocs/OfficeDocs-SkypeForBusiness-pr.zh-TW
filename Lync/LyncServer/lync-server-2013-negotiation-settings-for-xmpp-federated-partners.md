---
title: Lync Server 2013：XMPP 同盟夥伴的交涉設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02d72870e4060be6aa4ec428159af7ab19cb68b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="bc381-102">Lync Server 2013 中 XMPP 同盟夥伴的交涉設定</span><span class="sxs-lookup"><span data-stu-id="bc381-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc381-103">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="bc381-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="bc381-104">XMPP 合作夥伴設定中協商類型的設定有多種可能的組合。</span><span class="sxs-lookup"><span data-stu-id="bc381-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="bc381-105">並非所有這些組合都是有效的。</span><span class="sxs-lookup"><span data-stu-id="bc381-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="bc381-106">本主題中所述的表格將定義有效和不正確設定。</span><span class="sxs-lookup"><span data-stu-id="bc381-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="bc381-107">常見的設定會顯示在第一個資料表中，第二個數據表描述所有可能的組合。</span><span class="sxs-lookup"><span data-stu-id="bc381-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="bc381-108">請注意，除非也提供*傳輸層安全性*（TLS），**否則**您不能有*簡單的驗證與安全性層*（SASL）。</span><span class="sxs-lookup"><span data-stu-id="bc381-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="bc381-109">SASL 是以未加密（可讀）的格式傳送，除非受到其他方法（例如 TLS）保護，否則切勿傳送。</span><span class="sxs-lookup"><span data-stu-id="bc381-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="bc381-110">常見的 XMPP 聯盟協商方法</span><span class="sxs-lookup"><span data-stu-id="bc381-110">Common XMPP Federation Negotiation Methods</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc381-111">傳輸層安全性（TLS）</span><span class="sxs-lookup"><span data-stu-id="bc381-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="bc381-112">簡單驗證與安全性層（SASL）</span><span class="sxs-lookup"><span data-stu-id="bc381-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="bc381-113">回撥（驗證）</span><span class="sxs-lookup"><span data-stu-id="bc381-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="bc381-114">預期的驗證方法</span><span class="sxs-lookup"><span data-stu-id="bc381-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="bc381-115">筆記</span><span class="sxs-lookup"><span data-stu-id="bc381-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc381-116">必要</span><span class="sxs-lookup"><span data-stu-id="bc381-116">Required</span></span></p></td>
<td><p><span data-ttu-id="bc381-117">必要</span><span class="sxs-lookup"><span data-stu-id="bc381-117">Required</span></span></p></td>
<td><p><span data-ttu-id="bc381-118">虛假</span><span class="sxs-lookup"><span data-stu-id="bc381-118">False</span></span></p></td>
<td><p><span data-ttu-id="bc381-119">TLS 之上的 SASL</span><span class="sxs-lookup"><span data-stu-id="bc381-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="bc381-120">TLS 和 SASL 所需的資訊有助於確保 SASL 訊息資料流程是安全的。</span><span class="sxs-lookup"><span data-stu-id="bc381-120">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="bc381-121">如果 XMPP 聯盟合作夥伴未將 TLS 設定為 [必要] 或 [選用]，就無法使用回撥，且無法用於 fallback 方法。</span><span class="sxs-lookup"><span data-stu-id="bc381-121">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc381-122">必要</span><span class="sxs-lookup"><span data-stu-id="bc381-122">Required</span></span></p></td>
<td><p><span data-ttu-id="bc381-123">選用</span><span class="sxs-lookup"><span data-stu-id="bc381-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="bc381-124">滿足</span><span class="sxs-lookup"><span data-stu-id="bc381-124">True</span></span></p></td>
<td><p><span data-ttu-id="bc381-125">TLS 上的 SASL、TLS 回撥、TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="bc381-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="bc381-126">如果 XMPP 聯盟合作夥伴已將 [SASL] 設定為 [選用] 或 [所需的 SASL]，請使用 TLS。</span><span class="sxs-lookup"><span data-stu-id="bc381-126">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="bc381-127">如果沒有可用的 SASL，將會使用 TLS 上的回撥。</span><span class="sxs-lookup"><span data-stu-id="bc381-127">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc381-128">選用</span><span class="sxs-lookup"><span data-stu-id="bc381-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="bc381-129">選用</span><span class="sxs-lookup"><span data-stu-id="bc381-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="bc381-130">滿足</span><span class="sxs-lookup"><span data-stu-id="bc381-130">True</span></span></p></td>
<td><p><span data-ttu-id="bc381-131">TLS 上的 SASL、TLS 回撥、TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="bc381-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="bc381-132">在提供的協商方法中非常靈活，這些設定會依賴 XMPP 聯盟夥伴的設定。</span><span class="sxs-lookup"><span data-stu-id="bc381-132">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="bc381-133">如果合作夥伴選用 TLS 選擇性或必要，但不支援 SASL，則可以使用 TLS 回撥。</span><span class="sxs-lookup"><span data-stu-id="bc381-133">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="bc381-134">如果合作夥伴將 TLS 和 SASL 設定為 [選用] 或 [必要]，則會使用在 SASL 上最佳的 TLS 選取。</span><span class="sxs-lookup"><span data-stu-id="bc381-134">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc381-135">不支援</span><span class="sxs-lookup"><span data-stu-id="bc381-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="bc381-136">不支援</span><span class="sxs-lookup"><span data-stu-id="bc381-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="bc381-137">滿足</span><span class="sxs-lookup"><span data-stu-id="bc381-137">True</span></span></p></td>
<td><p><span data-ttu-id="bc381-138">TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="bc381-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="bc381-139">在許多情況下，TCP 回撥是唯一可行的解決方法。</span><span class="sxs-lookup"><span data-stu-id="bc381-139">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="bc381-140">比其他選項更不可取，它會提供一定層面的信任。</span><span class="sxs-lookup"><span data-stu-id="bc381-140">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="bc381-141">XMPP 同盟協商方法矩陣-完成</span><span class="sxs-lookup"><span data-stu-id="bc381-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc381-142">傳輸層安全性（TLS）</span><span class="sxs-lookup"><span data-stu-id="bc381-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="bc381-143">簡單驗證與安全性層（SASL）</span><span class="sxs-lookup"><span data-stu-id="bc381-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="bc381-144">回撥（驗證）</span><span class="sxs-lookup"><span data-stu-id="bc381-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="bc381-145">預期驗證方法</span><span class="sxs-lookup"><span data-stu-id="bc381-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="bc381-146">無法正確設定的記事、警告或錯誤</span><span class="sxs-lookup"><span data-stu-id="bc381-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc381-147">必要</span><span class="sxs-lookup"><span data-stu-id="bc381-147">Required</span></span></p></td>
<td><p><span data-ttu-id="bc381-148">必要</span><span class="sxs-lookup"><span data-stu-id="bc381-148">Required</span></span></p></td>
<td><p><span data-ttu-id="bc381-149">滿足</span><span class="sxs-lookup"><span data-stu-id="bc381-149">True</span></span></p></td>
<td><p><span data-ttu-id="bc381-150">TLS 之上的 SASL</span><span class="sxs-lookup"><span data-stu-id="bc381-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="bc381-151">如果需要 SASL 和 TLS，回撥將無法運作。</span><span class="sxs-lookup"><span data-stu-id="bc381-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc381-152">必要</span><span class="sxs-lookup"><span data-stu-id="bc381-152">Required</span></span></p></td>
<td><p><span data-ttu-id="bc381-153">必要</span><span class="sxs-lookup"><span data-stu-id="bc381-153">Required</span></span></p></td>
<td><p><span data-ttu-id="bc381-154">虛假</span><span class="sxs-lookup"><span data-stu-id="bc381-154">False</span></span></p></td>
<td><p><span data-ttu-id="bc381-155">TLS 之上的 SASL</span><span class="sxs-lookup"><span data-stu-id="bc381-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc381-156">選用</span><span class="sxs-lookup"><span data-stu-id="bc381-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="bc381-157">必要</span><span class="sxs-lookup"><span data-stu-id="bc381-157">Required</span></span></p></td>
<td><p><span data-ttu-id="bc381-158">滿足</span><span class="sxs-lookup"><span data-stu-id="bc381-158">True</span></span></p></td>
<td><p><span data-ttu-id="bc381-159">TLS 上的 SASL、TLS 回撥、TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="bc381-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="bc381-160">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="bc381-160">SASL requires TLS.</span></span> <span data-ttu-id="bc381-161">[允許 TLS 為選用] 可能會導致會話協商失敗。</span><span class="sxs-lookup"><span data-stu-id="bc381-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc381-162">選用</span><span class="sxs-lookup"><span data-stu-id="bc381-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="bc381-163">必要</span><span class="sxs-lookup"><span data-stu-id="bc381-163">Required</span></span></p></td>
<td><p><span data-ttu-id="bc381-164">虛假</span><span class="sxs-lookup"><span data-stu-id="bc381-164">False</span></span></p></td>
<td><p><span data-ttu-id="bc381-165">TLS 之上的 SASL</span><span class="sxs-lookup"><span data-stu-id="bc381-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="bc381-166">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="bc381-166">SASL requires TLS.</span></span> <span data-ttu-id="bc381-167">[允許 TLS 為選用] 可能會導致會話協商失敗。</span><span class="sxs-lookup"><span data-stu-id="bc381-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc381-168">不支援</span><span class="sxs-lookup"><span data-stu-id="bc381-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="bc381-169">必要</span><span class="sxs-lookup"><span data-stu-id="bc381-169">Required</span></span></p></td>
<td><p><span data-ttu-id="bc381-170">滿足</span><span class="sxs-lookup"><span data-stu-id="bc381-170">True</span></span></p></td>
<td><p><span data-ttu-id="bc381-171">TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="bc381-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="bc381-172">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="bc381-172">SASL requires TLS.</span></span> <span data-ttu-id="bc381-173">[允許 TLS 為選用] 可能會導致會話協商失敗。</span><span class="sxs-lookup"><span data-stu-id="bc381-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc381-174">不支援</span><span class="sxs-lookup"><span data-stu-id="bc381-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="bc381-175">必要</span><span class="sxs-lookup"><span data-stu-id="bc381-175">Required</span></span></p></td>
<td><p><span data-ttu-id="bc381-176">虛假</span><span class="sxs-lookup"><span data-stu-id="bc381-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="bc381-177">不正確設定</span><span class="sxs-lookup"><span data-stu-id="bc381-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="bc381-178">因為 SASL 需要 TLS，而且 TLS 無法使用，所以 SASL/TLS 無法成功。</span><span class="sxs-lookup"><span data-stu-id="bc381-178">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="bc381-179">TCP 回撥是設定為 false，而且無法使用。</span><span class="sxs-lookup"><span data-stu-id="bc381-179">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc381-180">必要</span><span class="sxs-lookup"><span data-stu-id="bc381-180">Required</span></span></p></td>
<td><p><span data-ttu-id="bc381-181">選用</span><span class="sxs-lookup"><span data-stu-id="bc381-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="bc381-182">滿足</span><span class="sxs-lookup"><span data-stu-id="bc381-182">True</span></span></p></td>
<td><p><span data-ttu-id="bc381-183">TLS 上的 SASL，TLS 回撥</span><span class="sxs-lookup"><span data-stu-id="bc381-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc381-184">必要</span><span class="sxs-lookup"><span data-stu-id="bc381-184">Required</span></span></p></td>
<td><p><span data-ttu-id="bc381-185">選用</span><span class="sxs-lookup"><span data-stu-id="bc381-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="bc381-186">虛假</span><span class="sxs-lookup"><span data-stu-id="bc381-186">False</span></span></p></td>
<td><p><span data-ttu-id="bc381-187">TLS 之上的 SASL</span><span class="sxs-lookup"><span data-stu-id="bc381-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc381-188">選用</span><span class="sxs-lookup"><span data-stu-id="bc381-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="bc381-189">選用</span><span class="sxs-lookup"><span data-stu-id="bc381-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="bc381-190">滿足</span><span class="sxs-lookup"><span data-stu-id="bc381-190">True</span></span></p></td>
<td><p><span data-ttu-id="bc381-191">TLS 上的 SASL、TLS 回撥、TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="bc381-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="bc381-192">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="bc381-192">SASL requires TLS.</span></span> <span data-ttu-id="bc381-193">[允許 TLS 為選用] 可能會導致會話協商失敗。</span><span class="sxs-lookup"><span data-stu-id="bc381-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc381-194">選用</span><span class="sxs-lookup"><span data-stu-id="bc381-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="bc381-195">選用</span><span class="sxs-lookup"><span data-stu-id="bc381-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="bc381-196">虛假</span><span class="sxs-lookup"><span data-stu-id="bc381-196">False</span></span></p></td>
<td><p><span data-ttu-id="bc381-197">TLS 之上的 SASL</span><span class="sxs-lookup"><span data-stu-id="bc381-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="bc381-198">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="bc381-198">SASL requires TLS.</span></span> <span data-ttu-id="bc381-199">[允許 TLS 為選用] 可能會導致會話協商失敗。</span><span class="sxs-lookup"><span data-stu-id="bc381-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc381-200">不支援</span><span class="sxs-lookup"><span data-stu-id="bc381-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="bc381-201">選用</span><span class="sxs-lookup"><span data-stu-id="bc381-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="bc381-202">滿足</span><span class="sxs-lookup"><span data-stu-id="bc381-202">True</span></span></p></td>
<td><p><span data-ttu-id="bc381-203">TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="bc381-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="bc381-204">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="bc381-204">SASL requires TLS.</span></span> <span data-ttu-id="bc381-205">[允許 TLS 為選用] 可能會導致會話協商失敗。</span><span class="sxs-lookup"><span data-stu-id="bc381-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc381-206">不支援</span><span class="sxs-lookup"><span data-stu-id="bc381-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="bc381-207">選用</span><span class="sxs-lookup"><span data-stu-id="bc381-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="bc381-208">虛假</span><span class="sxs-lookup"><span data-stu-id="bc381-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="bc381-209">不正確設定</span><span class="sxs-lookup"><span data-stu-id="bc381-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="bc381-210">SASL 需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="bc381-210">SASL requires TLS.</span></span> <span data-ttu-id="bc381-211">[允許 TLS 為選用] 可能會導致會話協商失敗。</span><span class="sxs-lookup"><span data-stu-id="bc381-211">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc381-212">必要</span><span class="sxs-lookup"><span data-stu-id="bc381-212">Required</span></span></p></td>
<td><p><span data-ttu-id="bc381-213">不支援</span><span class="sxs-lookup"><span data-stu-id="bc381-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="bc381-214">滿足</span><span class="sxs-lookup"><span data-stu-id="bc381-214">True</span></span></p></td>
<td><p><span data-ttu-id="bc381-215">TLS 回撥</span><span class="sxs-lookup"><span data-stu-id="bc381-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="bc381-216">[配置] 允許 TLS 回撥。</span><span class="sxs-lookup"><span data-stu-id="bc381-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc381-217">必要</span><span class="sxs-lookup"><span data-stu-id="bc381-217">Required</span></span></p></td>
<td><p><span data-ttu-id="bc381-218">不支援</span><span class="sxs-lookup"><span data-stu-id="bc381-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="bc381-219">虛假</span><span class="sxs-lookup"><span data-stu-id="bc381-219">False</span></span></p></td>
<td><p><span data-ttu-id="bc381-220">不正確設定</span><span class="sxs-lookup"><span data-stu-id="bc381-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="bc381-221">必須啟用 SASL 或回撥。</span><span class="sxs-lookup"><span data-stu-id="bc381-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc381-222">選用</span><span class="sxs-lookup"><span data-stu-id="bc381-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="bc381-223">不支援</span><span class="sxs-lookup"><span data-stu-id="bc381-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="bc381-224">滿足</span><span class="sxs-lookup"><span data-stu-id="bc381-224">True</span></span></p></td>
<td><p><span data-ttu-id="bc381-225">TLS 回撥，TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="bc381-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="bc381-226">根據另一個端點的協商選項，將會接受 TCP 或 TLS 回撥。</span><span class="sxs-lookup"><span data-stu-id="bc381-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc381-227">選用</span><span class="sxs-lookup"><span data-stu-id="bc381-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="bc381-228">不支援</span><span class="sxs-lookup"><span data-stu-id="bc381-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="bc381-229">虛假</span><span class="sxs-lookup"><span data-stu-id="bc381-229">False</span></span></p></td>
<td><p><span data-ttu-id="bc381-230">不正確設定</span><span class="sxs-lookup"><span data-stu-id="bc381-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="bc381-231">必須啟用 SASL 或回撥。</span><span class="sxs-lookup"><span data-stu-id="bc381-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc381-232">不支援</span><span class="sxs-lookup"><span data-stu-id="bc381-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="bc381-233">不支援</span><span class="sxs-lookup"><span data-stu-id="bc381-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="bc381-234">滿足</span><span class="sxs-lookup"><span data-stu-id="bc381-234">True</span></span></p></td>
<td><p><span data-ttu-id="bc381-235">TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="bc381-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="bc381-236">TCP 回撥是唯一可用的協商方法</span><span class="sxs-lookup"><span data-stu-id="bc381-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc381-237">不支援</span><span class="sxs-lookup"><span data-stu-id="bc381-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="bc381-238">不支援</span><span class="sxs-lookup"><span data-stu-id="bc381-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="bc381-239">虛假</span><span class="sxs-lookup"><span data-stu-id="bc381-239">False</span></span></p></td>
<td><p><span data-ttu-id="bc381-240">不正確設定</span><span class="sxs-lookup"><span data-stu-id="bc381-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="bc381-241">必須啟用 SASL 或回撥。</span><span class="sxs-lookup"><span data-stu-id="bc381-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

