---
title: Lync Server 2013： XMPP 同盟合作夥伴的協商設定
description: Lync Server 2013： XMPP 同盟協力廠商的協商設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ac3d9c69d407dc750a1afb35f0a448869a88f09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578639"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="54582-103">Lync Server 2013 中 XMPP 同盟合作夥伴的協商設定</span><span class="sxs-lookup"><span data-stu-id="54582-103">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54582-104">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="54582-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="54582-105">XMPP 合作夥伴設定中的協商類型設定具有多種可能的組合。</span><span class="sxs-lookup"><span data-stu-id="54582-105">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="54582-106">並非所有的組合都是有效的。</span><span class="sxs-lookup"><span data-stu-id="54582-106">Not all of these combinations are valid.</span></span> <span data-ttu-id="54582-107">本主題所述的表格會定義有效且不正確設定。</span><span class="sxs-lookup"><span data-stu-id="54582-107">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="54582-108">通用設定會顯示在第一個表格中，第二個表格會詳細說明所有可能的組合。</span><span class="sxs-lookup"><span data-stu-id="54582-108">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="54582-109">請注意，除非也可以使用「*傳輸層安全性* (TLS) ，**否則**不能讓*簡單驗證及安全性層* (SASL) 。</span><span class="sxs-lookup"><span data-stu-id="54582-109">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="54582-110">SASL 會以未加密的 (可讀取的) 格式傳送，除非受到另一種方式（如 TLS）保護，否則決不會傳送。</span><span class="sxs-lookup"><span data-stu-id="54582-110">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="54582-111">一般 XMPP 同盟協商方法</span><span class="sxs-lookup"><span data-stu-id="54582-111">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="54582-112">傳輸層安全性 (TLS)</span><span class="sxs-lookup"><span data-stu-id="54582-112">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="54582-113">簡單驗證及安全性層 (SASL) </span><span class="sxs-lookup"><span data-stu-id="54582-113">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="54582-114">回撥驗證</span><span class="sxs-lookup"><span data-stu-id="54582-114">Dialback Authentication</span></span></th>
<th><span data-ttu-id="54582-115">預期的驗證方法 (s) </span><span class="sxs-lookup"><span data-stu-id="54582-115">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="54582-116">注意事項</span><span class="sxs-lookup"><span data-stu-id="54582-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54582-117">必要</span><span class="sxs-lookup"><span data-stu-id="54582-117">Required</span></span></p></td>
<td><p><span data-ttu-id="54582-118">必要</span><span class="sxs-lookup"><span data-stu-id="54582-118">Required</span></span></p></td>
<td><p><span data-ttu-id="54582-119">False</span><span class="sxs-lookup"><span data-stu-id="54582-119">False</span></span></p></td>
<td><p><span data-ttu-id="54582-120">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="54582-120">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="54582-121">需要 TLS 和 SASL，有助於確保 SASL 郵件資料流程安全。</span><span class="sxs-lookup"><span data-stu-id="54582-121">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="54582-122">如果 XMPP 同盟協力廠商未將 TLS 設定為 [必要] 或 [選用]，則無法使用回撥方法。</span><span class="sxs-lookup"><span data-stu-id="54582-122">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54582-123">必要</span><span class="sxs-lookup"><span data-stu-id="54582-123">Required</span></span></p></td>
<td><p><span data-ttu-id="54582-124">選用</span><span class="sxs-lookup"><span data-stu-id="54582-124">Optional</span></span></p></td>
<td><p><span data-ttu-id="54582-125">是</span><span class="sxs-lookup"><span data-stu-id="54582-125">True</span></span></p></td>
<td><p><span data-ttu-id="54582-126">SASL over TLS、TLS 回撥、TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="54582-126">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="54582-127">在需要 TLS 的情況下，如果 XMPP 同盟協力廠商已將 SASL 設定為選用或必要的 SASL。</span><span class="sxs-lookup"><span data-stu-id="54582-127">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="54582-128">如果無法使用 SASL，將會使用以 TLS 進行回撥。</span><span class="sxs-lookup"><span data-stu-id="54582-128">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54582-129">選用</span><span class="sxs-lookup"><span data-stu-id="54582-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="54582-130">選用</span><span class="sxs-lookup"><span data-stu-id="54582-130">Optional</span></span></p></td>
<td><p><span data-ttu-id="54582-131">是</span><span class="sxs-lookup"><span data-stu-id="54582-131">True</span></span></p></td>
<td><p><span data-ttu-id="54582-132">SASL over TLS、TLS 回撥、TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="54582-132">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="54582-133">在提供的協商方法中非常靈活，這些設定會依賴 XMPP 同盟協力廠商的設定。</span><span class="sxs-lookup"><span data-stu-id="54582-133">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="54582-134">如果合作夥伴具有 TLS 選用或必要，但不支援 SASL，則 TLS 回撥將可供使用。</span><span class="sxs-lookup"><span data-stu-id="54582-134">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="54582-135">如果夥伴的 TLS 和 SASL 設定為 [選用] 或 [必要]，則會使用在 SASL 上的最佳選取 TLS。</span><span class="sxs-lookup"><span data-stu-id="54582-135">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54582-136">不支援</span><span class="sxs-lookup"><span data-stu-id="54582-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54582-137">不支援</span><span class="sxs-lookup"><span data-stu-id="54582-137">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54582-138">是</span><span class="sxs-lookup"><span data-stu-id="54582-138">True</span></span></p></td>
<td><p><span data-ttu-id="54582-139">TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="54582-139">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="54582-140">在許多情況下，TCP 回撥是唯一可行的解決方案。</span><span class="sxs-lookup"><span data-stu-id="54582-140">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="54582-141">比其他選項還不可取，它提供一定層級的信任。</span><span class="sxs-lookup"><span data-stu-id="54582-141">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="54582-142">XMPP 同盟協商方法矩陣-完成</span><span class="sxs-lookup"><span data-stu-id="54582-142">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="54582-143">傳輸層安全性 (TLS)</span><span class="sxs-lookup"><span data-stu-id="54582-143">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="54582-144">簡單驗證及安全性層 (SASL) </span><span class="sxs-lookup"><span data-stu-id="54582-144">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="54582-145">回撥驗證</span><span class="sxs-lookup"><span data-stu-id="54582-145">Dialback Authentication</span></span></th>
<th><span data-ttu-id="54582-146">預期的驗證方法</span><span class="sxs-lookup"><span data-stu-id="54582-146">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="54582-147">無效設定的附注、警告或錯誤</span><span class="sxs-lookup"><span data-stu-id="54582-147">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54582-148">必要</span><span class="sxs-lookup"><span data-stu-id="54582-148">Required</span></span></p></td>
<td><p><span data-ttu-id="54582-149">必要</span><span class="sxs-lookup"><span data-stu-id="54582-149">Required</span></span></p></td>
<td><p><span data-ttu-id="54582-150">是</span><span class="sxs-lookup"><span data-stu-id="54582-150">True</span></span></p></td>
<td><p><span data-ttu-id="54582-151">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="54582-151">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54582-152">如果需要 SASL 和 TLS，則回撥不會運作。</span><span class="sxs-lookup"><span data-stu-id="54582-152">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54582-153">必要</span><span class="sxs-lookup"><span data-stu-id="54582-153">Required</span></span></p></td>
<td><p><span data-ttu-id="54582-154">必要</span><span class="sxs-lookup"><span data-stu-id="54582-154">Required</span></span></p></td>
<td><p><span data-ttu-id="54582-155">False</span><span class="sxs-lookup"><span data-stu-id="54582-155">False</span></span></p></td>
<td><p><span data-ttu-id="54582-156">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="54582-156">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54582-157">選用</span><span class="sxs-lookup"><span data-stu-id="54582-157">Optional</span></span></p></td>
<td><p><span data-ttu-id="54582-158">必要</span><span class="sxs-lookup"><span data-stu-id="54582-158">Required</span></span></p></td>
<td><p><span data-ttu-id="54582-159">是</span><span class="sxs-lookup"><span data-stu-id="54582-159">True</span></span></p></td>
<td><p><span data-ttu-id="54582-160">SASL over TLS、TLS 回撥、TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="54582-160">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54582-161">SASL 要求 TLS。</span><span class="sxs-lookup"><span data-stu-id="54582-161">SASL requires TLS.</span></span> <span data-ttu-id="54582-162">允許 TLS 為選用可能會導致會話協商失敗。</span><span class="sxs-lookup"><span data-stu-id="54582-162">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54582-163">選用</span><span class="sxs-lookup"><span data-stu-id="54582-163">Optional</span></span></p></td>
<td><p><span data-ttu-id="54582-164">必要</span><span class="sxs-lookup"><span data-stu-id="54582-164">Required</span></span></p></td>
<td><p><span data-ttu-id="54582-165">False</span><span class="sxs-lookup"><span data-stu-id="54582-165">False</span></span></p></td>
<td><p><span data-ttu-id="54582-166">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="54582-166">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54582-167">SASL 要求 TLS。</span><span class="sxs-lookup"><span data-stu-id="54582-167">SASL requires TLS.</span></span> <span data-ttu-id="54582-168">允許 TLS 為選用可能會導致會話協商失敗。</span><span class="sxs-lookup"><span data-stu-id="54582-168">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54582-169">不支援</span><span class="sxs-lookup"><span data-stu-id="54582-169">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54582-170">必要</span><span class="sxs-lookup"><span data-stu-id="54582-170">Required</span></span></p></td>
<td><p><span data-ttu-id="54582-171">是</span><span class="sxs-lookup"><span data-stu-id="54582-171">True</span></span></p></td>
<td><p><span data-ttu-id="54582-172">TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="54582-172">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54582-173">SASL 要求 TLS。</span><span class="sxs-lookup"><span data-stu-id="54582-173">SASL requires TLS.</span></span> <span data-ttu-id="54582-174">允許 TLS 為選用可能會導致會話協商失敗。</span><span class="sxs-lookup"><span data-stu-id="54582-174">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54582-175">不支援</span><span class="sxs-lookup"><span data-stu-id="54582-175">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54582-176">必要</span><span class="sxs-lookup"><span data-stu-id="54582-176">Required</span></span></p></td>
<td><p><span data-ttu-id="54582-177">False</span><span class="sxs-lookup"><span data-stu-id="54582-177">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54582-178">無效設定</span><span class="sxs-lookup"><span data-stu-id="54582-178">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54582-179">因為 SASL 需要 TLS，而 TLS 無法使用，所以 SASL/TLS 無法成功。</span><span class="sxs-lookup"><span data-stu-id="54582-179">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="54582-180">TCP 回撥是設定為 false，且無法使用。</span><span class="sxs-lookup"><span data-stu-id="54582-180">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54582-181">必要</span><span class="sxs-lookup"><span data-stu-id="54582-181">Required</span></span></p></td>
<td><p><span data-ttu-id="54582-182">選用</span><span class="sxs-lookup"><span data-stu-id="54582-182">Optional</span></span></p></td>
<td><p><span data-ttu-id="54582-183">是</span><span class="sxs-lookup"><span data-stu-id="54582-183">True</span></span></p></td>
<td><p><span data-ttu-id="54582-184">SASL over TLS，TLS 回撥</span><span class="sxs-lookup"><span data-stu-id="54582-184">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54582-185">必要</span><span class="sxs-lookup"><span data-stu-id="54582-185">Required</span></span></p></td>
<td><p><span data-ttu-id="54582-186">選用</span><span class="sxs-lookup"><span data-stu-id="54582-186">Optional</span></span></p></td>
<td><p><span data-ttu-id="54582-187">False</span><span class="sxs-lookup"><span data-stu-id="54582-187">False</span></span></p></td>
<td><p><span data-ttu-id="54582-188">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="54582-188">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54582-189">選用</span><span class="sxs-lookup"><span data-stu-id="54582-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="54582-190">選用</span><span class="sxs-lookup"><span data-stu-id="54582-190">Optional</span></span></p></td>
<td><p><span data-ttu-id="54582-191">是</span><span class="sxs-lookup"><span data-stu-id="54582-191">True</span></span></p></td>
<td><p><span data-ttu-id="54582-192">SASL over TLS、TLS 回撥、TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="54582-192">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54582-193">SASL 要求 TLS。</span><span class="sxs-lookup"><span data-stu-id="54582-193">SASL requires TLS.</span></span> <span data-ttu-id="54582-194">允許 TLS 為選用可能會導致會話協商失敗。</span><span class="sxs-lookup"><span data-stu-id="54582-194">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54582-195">選用</span><span class="sxs-lookup"><span data-stu-id="54582-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="54582-196">選用</span><span class="sxs-lookup"><span data-stu-id="54582-196">Optional</span></span></p></td>
<td><p><span data-ttu-id="54582-197">False</span><span class="sxs-lookup"><span data-stu-id="54582-197">False</span></span></p></td>
<td><p><span data-ttu-id="54582-198">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="54582-198">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54582-199">SASL 要求 TLS。</span><span class="sxs-lookup"><span data-stu-id="54582-199">SASL requires TLS.</span></span> <span data-ttu-id="54582-200">允許 TLS 為選用可能會導致會話協商失敗。</span><span class="sxs-lookup"><span data-stu-id="54582-200">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54582-201">不支援</span><span class="sxs-lookup"><span data-stu-id="54582-201">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54582-202">選用</span><span class="sxs-lookup"><span data-stu-id="54582-202">Optional</span></span></p></td>
<td><p><span data-ttu-id="54582-203">是</span><span class="sxs-lookup"><span data-stu-id="54582-203">True</span></span></p></td>
<td><p><span data-ttu-id="54582-204">TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="54582-204">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54582-205">SASL 要求 TLS。</span><span class="sxs-lookup"><span data-stu-id="54582-205">SASL requires TLS.</span></span> <span data-ttu-id="54582-206">允許 TLS 為選用可能會導致會話協商失敗。</span><span class="sxs-lookup"><span data-stu-id="54582-206">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54582-207">不支援</span><span class="sxs-lookup"><span data-stu-id="54582-207">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54582-208">選用</span><span class="sxs-lookup"><span data-stu-id="54582-208">Optional</span></span></p></td>
<td><p><span data-ttu-id="54582-209">False</span><span class="sxs-lookup"><span data-stu-id="54582-209">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54582-210">無效設定</span><span class="sxs-lookup"><span data-stu-id="54582-210">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54582-211">SASL 要求 TLS。</span><span class="sxs-lookup"><span data-stu-id="54582-211">SASL requires TLS.</span></span> <span data-ttu-id="54582-212">允許 TLS 為選用可能會導致會話協商失敗。</span><span class="sxs-lookup"><span data-stu-id="54582-212">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54582-213">必要</span><span class="sxs-lookup"><span data-stu-id="54582-213">Required</span></span></p></td>
<td><p><span data-ttu-id="54582-214">不支援</span><span class="sxs-lookup"><span data-stu-id="54582-214">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54582-215">是</span><span class="sxs-lookup"><span data-stu-id="54582-215">True</span></span></p></td>
<td><p><span data-ttu-id="54582-216">TLS 回撥</span><span class="sxs-lookup"><span data-stu-id="54582-216">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="54582-217">設定允許 TLS 回撥。</span><span class="sxs-lookup"><span data-stu-id="54582-217">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54582-218">必要</span><span class="sxs-lookup"><span data-stu-id="54582-218">Required</span></span></p></td>
<td><p><span data-ttu-id="54582-219">不支援</span><span class="sxs-lookup"><span data-stu-id="54582-219">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54582-220">False</span><span class="sxs-lookup"><span data-stu-id="54582-220">False</span></span></p></td>
<td><p><span data-ttu-id="54582-221">無效設定</span><span class="sxs-lookup"><span data-stu-id="54582-221">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54582-222">必須啟用 SASL 或回撥。</span><span class="sxs-lookup"><span data-stu-id="54582-222">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54582-223">選用</span><span class="sxs-lookup"><span data-stu-id="54582-223">Optional</span></span></p></td>
<td><p><span data-ttu-id="54582-224">不支援</span><span class="sxs-lookup"><span data-stu-id="54582-224">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54582-225">是</span><span class="sxs-lookup"><span data-stu-id="54582-225">True</span></span></p></td>
<td><p><span data-ttu-id="54582-226">TLS 回撥，TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="54582-226">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="54582-227">根據其他端點的協商選擇，會接受 TCP 或 TLS 回撥。</span><span class="sxs-lookup"><span data-stu-id="54582-227">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54582-228">選用</span><span class="sxs-lookup"><span data-stu-id="54582-228">Optional</span></span></p></td>
<td><p><span data-ttu-id="54582-229">不支援</span><span class="sxs-lookup"><span data-stu-id="54582-229">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54582-230">False</span><span class="sxs-lookup"><span data-stu-id="54582-230">False</span></span></p></td>
<td><p><span data-ttu-id="54582-231">無效設定</span><span class="sxs-lookup"><span data-stu-id="54582-231">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54582-232">必須啟用 SASL 或回撥。</span><span class="sxs-lookup"><span data-stu-id="54582-232">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54582-233">不支援</span><span class="sxs-lookup"><span data-stu-id="54582-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54582-234">不支援</span><span class="sxs-lookup"><span data-stu-id="54582-234">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54582-235">是</span><span class="sxs-lookup"><span data-stu-id="54582-235">True</span></span></p></td>
<td><p><span data-ttu-id="54582-236">TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="54582-236">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="54582-237">TCP 回撥是唯一可用的協商方法</span><span class="sxs-lookup"><span data-stu-id="54582-237">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54582-238">不支援</span><span class="sxs-lookup"><span data-stu-id="54582-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54582-239">不支援</span><span class="sxs-lookup"><span data-stu-id="54582-239">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="54582-240">False</span><span class="sxs-lookup"><span data-stu-id="54582-240">False</span></span></p></td>
<td><p><span data-ttu-id="54582-241">無效設定</span><span class="sxs-lookup"><span data-stu-id="54582-241">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="54582-242">必須啟用 SASL 或回撥。</span><span class="sxs-lookup"><span data-stu-id="54582-242">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

