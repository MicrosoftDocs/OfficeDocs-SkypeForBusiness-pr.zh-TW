---
title: Lync Server 2013： XMPP 同盟合作夥伴的協商設定
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
ms.openlocfilehash: bdb09d52970b5fd97395acda6a2e4fbc824a378d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505590"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="b914f-102">Lync Server 2013 中 XMPP 同盟合作夥伴的協商設定</span><span class="sxs-lookup"><span data-stu-id="b914f-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b914f-103">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="b914f-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="b914f-104">XMPP 合作夥伴設定中的協商類型設定具有多種可能的組合。</span><span class="sxs-lookup"><span data-stu-id="b914f-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="b914f-105">並非所有的組合都是有效的。</span><span class="sxs-lookup"><span data-stu-id="b914f-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="b914f-106">本主題所述的表格會定義有效且不正確設定。</span><span class="sxs-lookup"><span data-stu-id="b914f-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="b914f-107">通用設定會顯示在第一個表格中，第二個表格會詳細說明所有可能的組合。</span><span class="sxs-lookup"><span data-stu-id="b914f-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="b914f-108">請注意，除非也可以使用「*傳輸層安全性* (TLS) ，**否則**不能讓*簡單驗證及安全性層* (SASL) 。</span><span class="sxs-lookup"><span data-stu-id="b914f-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="b914f-109">SASL 會以未加密的 (可讀取的) 格式傳送，除非受到另一種方式（如 TLS）保護，否則決不會傳送。</span><span class="sxs-lookup"><span data-stu-id="b914f-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="b914f-110">一般 XMPP 同盟協商方法</span><span class="sxs-lookup"><span data-stu-id="b914f-110">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="b914f-111">傳輸層安全性 (TLS)</span><span class="sxs-lookup"><span data-stu-id="b914f-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="b914f-112">簡單驗證及安全性層 (SASL) </span><span class="sxs-lookup"><span data-stu-id="b914f-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="b914f-113">回撥驗證</span><span class="sxs-lookup"><span data-stu-id="b914f-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="b914f-114">預期的驗證方法 (s) </span><span class="sxs-lookup"><span data-stu-id="b914f-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="b914f-115">注意事項</span><span class="sxs-lookup"><span data-stu-id="b914f-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b914f-116">必要</span><span class="sxs-lookup"><span data-stu-id="b914f-116">Required</span></span></p></td>
<td><p><span data-ttu-id="b914f-117">必要</span><span class="sxs-lookup"><span data-stu-id="b914f-117">Required</span></span></p></td>
<td><p><span data-ttu-id="b914f-118">False</span><span class="sxs-lookup"><span data-stu-id="b914f-118">False</span></span></p></td>
<td><p><span data-ttu-id="b914f-119">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="b914f-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="b914f-120">需要 TLS 和 SASL，有助於確保 SASL 郵件資料流程安全。</span><span class="sxs-lookup"><span data-stu-id="b914f-120">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="b914f-121">如果 XMPP 同盟協力廠商未將 TLS 設定為 [必要] 或 [選用]，則無法使用回撥方法。</span><span class="sxs-lookup"><span data-stu-id="b914f-121">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b914f-122">必要</span><span class="sxs-lookup"><span data-stu-id="b914f-122">Required</span></span></p></td>
<td><p><span data-ttu-id="b914f-123">選用</span><span class="sxs-lookup"><span data-stu-id="b914f-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="b914f-124">是</span><span class="sxs-lookup"><span data-stu-id="b914f-124">True</span></span></p></td>
<td><p><span data-ttu-id="b914f-125">SASL over TLS、TLS 回撥、TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="b914f-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="b914f-126">在需要 TLS 的情況下，如果 XMPP 同盟協力廠商已將 SASL 設定為選用或必要的 SASL。</span><span class="sxs-lookup"><span data-stu-id="b914f-126">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="b914f-127">如果無法使用 SASL，將會使用以 TLS 進行回撥。</span><span class="sxs-lookup"><span data-stu-id="b914f-127">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b914f-128">選用</span><span class="sxs-lookup"><span data-stu-id="b914f-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="b914f-129">選用</span><span class="sxs-lookup"><span data-stu-id="b914f-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="b914f-130">是</span><span class="sxs-lookup"><span data-stu-id="b914f-130">True</span></span></p></td>
<td><p><span data-ttu-id="b914f-131">SASL over TLS、TLS 回撥、TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="b914f-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="b914f-132">在提供的協商方法中非常靈活，這些設定會依賴 XMPP 同盟協力廠商的設定。</span><span class="sxs-lookup"><span data-stu-id="b914f-132">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="b914f-133">如果合作夥伴具有 TLS 選用或必要，但不支援 SASL，則 TLS 回撥將可供使用。</span><span class="sxs-lookup"><span data-stu-id="b914f-133">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="b914f-134">如果夥伴的 TLS 和 SASL 設定為 [選用] 或 [必要]，則會使用在 SASL 上的最佳選取 TLS。</span><span class="sxs-lookup"><span data-stu-id="b914f-134">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b914f-135">不支援</span><span class="sxs-lookup"><span data-stu-id="b914f-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b914f-136">不支援</span><span class="sxs-lookup"><span data-stu-id="b914f-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b914f-137">是</span><span class="sxs-lookup"><span data-stu-id="b914f-137">True</span></span></p></td>
<td><p><span data-ttu-id="b914f-138">TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="b914f-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="b914f-139">在許多情況下，TCP 回撥是唯一可行的解決方案。</span><span class="sxs-lookup"><span data-stu-id="b914f-139">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="b914f-140">比其他選項還不可取，它提供一定層級的信任。</span><span class="sxs-lookup"><span data-stu-id="b914f-140">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="b914f-141">XMPP 同盟協商方法矩陣-完成</span><span class="sxs-lookup"><span data-stu-id="b914f-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="b914f-142">傳輸層安全性 (TLS)</span><span class="sxs-lookup"><span data-stu-id="b914f-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="b914f-143">簡單驗證及安全性層 (SASL) </span><span class="sxs-lookup"><span data-stu-id="b914f-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="b914f-144">回撥驗證</span><span class="sxs-lookup"><span data-stu-id="b914f-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="b914f-145">預期的驗證方法</span><span class="sxs-lookup"><span data-stu-id="b914f-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="b914f-146">無效設定的附注、警告或錯誤</span><span class="sxs-lookup"><span data-stu-id="b914f-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b914f-147">必要</span><span class="sxs-lookup"><span data-stu-id="b914f-147">Required</span></span></p></td>
<td><p><span data-ttu-id="b914f-148">必要</span><span class="sxs-lookup"><span data-stu-id="b914f-148">Required</span></span></p></td>
<td><p><span data-ttu-id="b914f-149">是</span><span class="sxs-lookup"><span data-stu-id="b914f-149">True</span></span></p></td>
<td><p><span data-ttu-id="b914f-150">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="b914f-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b914f-151">如果需要 SASL 和 TLS，則回撥不會運作。</span><span class="sxs-lookup"><span data-stu-id="b914f-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b914f-152">必要</span><span class="sxs-lookup"><span data-stu-id="b914f-152">Required</span></span></p></td>
<td><p><span data-ttu-id="b914f-153">必要</span><span class="sxs-lookup"><span data-stu-id="b914f-153">Required</span></span></p></td>
<td><p><span data-ttu-id="b914f-154">False</span><span class="sxs-lookup"><span data-stu-id="b914f-154">False</span></span></p></td>
<td><p><span data-ttu-id="b914f-155">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="b914f-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b914f-156">選用</span><span class="sxs-lookup"><span data-stu-id="b914f-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="b914f-157">必要</span><span class="sxs-lookup"><span data-stu-id="b914f-157">Required</span></span></p></td>
<td><p><span data-ttu-id="b914f-158">是</span><span class="sxs-lookup"><span data-stu-id="b914f-158">True</span></span></p></td>
<td><p><span data-ttu-id="b914f-159">SASL over TLS、TLS 回撥、TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="b914f-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b914f-160">SASL 要求 TLS。</span><span class="sxs-lookup"><span data-stu-id="b914f-160">SASL requires TLS.</span></span> <span data-ttu-id="b914f-161">允許 TLS 為選用可能會導致會話協商失敗。</span><span class="sxs-lookup"><span data-stu-id="b914f-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b914f-162">選用</span><span class="sxs-lookup"><span data-stu-id="b914f-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="b914f-163">必要</span><span class="sxs-lookup"><span data-stu-id="b914f-163">Required</span></span></p></td>
<td><p><span data-ttu-id="b914f-164">False</span><span class="sxs-lookup"><span data-stu-id="b914f-164">False</span></span></p></td>
<td><p><span data-ttu-id="b914f-165">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="b914f-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b914f-166">SASL 要求 TLS。</span><span class="sxs-lookup"><span data-stu-id="b914f-166">SASL requires TLS.</span></span> <span data-ttu-id="b914f-167">允許 TLS 為選用可能會導致會話協商失敗。</span><span class="sxs-lookup"><span data-stu-id="b914f-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b914f-168">不支援</span><span class="sxs-lookup"><span data-stu-id="b914f-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b914f-169">必要</span><span class="sxs-lookup"><span data-stu-id="b914f-169">Required</span></span></p></td>
<td><p><span data-ttu-id="b914f-170">是</span><span class="sxs-lookup"><span data-stu-id="b914f-170">True</span></span></p></td>
<td><p><span data-ttu-id="b914f-171">TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="b914f-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b914f-172">SASL 要求 TLS。</span><span class="sxs-lookup"><span data-stu-id="b914f-172">SASL requires TLS.</span></span> <span data-ttu-id="b914f-173">允許 TLS 為選用可能會導致會話協商失敗。</span><span class="sxs-lookup"><span data-stu-id="b914f-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b914f-174">不支援</span><span class="sxs-lookup"><span data-stu-id="b914f-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b914f-175">必要</span><span class="sxs-lookup"><span data-stu-id="b914f-175">Required</span></span></p></td>
<td><p><span data-ttu-id="b914f-176">False</span><span class="sxs-lookup"><span data-stu-id="b914f-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b914f-177">無效設定</span><span class="sxs-lookup"><span data-stu-id="b914f-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b914f-178">因為 SASL 需要 TLS，而 TLS 無法使用，所以 SASL/TLS 無法成功。</span><span class="sxs-lookup"><span data-stu-id="b914f-178">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="b914f-179">TCP 回撥是設定為 false，且無法使用。</span><span class="sxs-lookup"><span data-stu-id="b914f-179">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b914f-180">必要</span><span class="sxs-lookup"><span data-stu-id="b914f-180">Required</span></span></p></td>
<td><p><span data-ttu-id="b914f-181">選用</span><span class="sxs-lookup"><span data-stu-id="b914f-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="b914f-182">是</span><span class="sxs-lookup"><span data-stu-id="b914f-182">True</span></span></p></td>
<td><p><span data-ttu-id="b914f-183">SASL over TLS，TLS 回撥</span><span class="sxs-lookup"><span data-stu-id="b914f-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b914f-184">必要</span><span class="sxs-lookup"><span data-stu-id="b914f-184">Required</span></span></p></td>
<td><p><span data-ttu-id="b914f-185">選用</span><span class="sxs-lookup"><span data-stu-id="b914f-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="b914f-186">False</span><span class="sxs-lookup"><span data-stu-id="b914f-186">False</span></span></p></td>
<td><p><span data-ttu-id="b914f-187">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="b914f-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b914f-188">選用</span><span class="sxs-lookup"><span data-stu-id="b914f-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="b914f-189">選用</span><span class="sxs-lookup"><span data-stu-id="b914f-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="b914f-190">是</span><span class="sxs-lookup"><span data-stu-id="b914f-190">True</span></span></p></td>
<td><p><span data-ttu-id="b914f-191">SASL over TLS、TLS 回撥、TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="b914f-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b914f-192">SASL 要求 TLS。</span><span class="sxs-lookup"><span data-stu-id="b914f-192">SASL requires TLS.</span></span> <span data-ttu-id="b914f-193">允許 TLS 為選用可能會導致會話協商失敗。</span><span class="sxs-lookup"><span data-stu-id="b914f-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b914f-194">選用</span><span class="sxs-lookup"><span data-stu-id="b914f-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="b914f-195">選用</span><span class="sxs-lookup"><span data-stu-id="b914f-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="b914f-196">False</span><span class="sxs-lookup"><span data-stu-id="b914f-196">False</span></span></p></td>
<td><p><span data-ttu-id="b914f-197">SASL over TLS</span><span class="sxs-lookup"><span data-stu-id="b914f-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b914f-198">SASL 要求 TLS。</span><span class="sxs-lookup"><span data-stu-id="b914f-198">SASL requires TLS.</span></span> <span data-ttu-id="b914f-199">允許 TLS 為選用可能會導致會話協商失敗。</span><span class="sxs-lookup"><span data-stu-id="b914f-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b914f-200">不支援</span><span class="sxs-lookup"><span data-stu-id="b914f-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b914f-201">選用</span><span class="sxs-lookup"><span data-stu-id="b914f-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="b914f-202">是</span><span class="sxs-lookup"><span data-stu-id="b914f-202">True</span></span></p></td>
<td><p><span data-ttu-id="b914f-203">TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="b914f-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b914f-204">SASL 要求 TLS。</span><span class="sxs-lookup"><span data-stu-id="b914f-204">SASL requires TLS.</span></span> <span data-ttu-id="b914f-205">允許 TLS 為選用可能會導致會話協商失敗。</span><span class="sxs-lookup"><span data-stu-id="b914f-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b914f-206">不支援</span><span class="sxs-lookup"><span data-stu-id="b914f-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b914f-207">選用</span><span class="sxs-lookup"><span data-stu-id="b914f-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="b914f-208">False</span><span class="sxs-lookup"><span data-stu-id="b914f-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b914f-209">無效設定</span><span class="sxs-lookup"><span data-stu-id="b914f-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b914f-210">SASL 要求 TLS。</span><span class="sxs-lookup"><span data-stu-id="b914f-210">SASL requires TLS.</span></span> <span data-ttu-id="b914f-211">允許 TLS 為選用可能會導致會話協商失敗。</span><span class="sxs-lookup"><span data-stu-id="b914f-211">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b914f-212">必要</span><span class="sxs-lookup"><span data-stu-id="b914f-212">Required</span></span></p></td>
<td><p><span data-ttu-id="b914f-213">不支援</span><span class="sxs-lookup"><span data-stu-id="b914f-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b914f-214">是</span><span class="sxs-lookup"><span data-stu-id="b914f-214">True</span></span></p></td>
<td><p><span data-ttu-id="b914f-215">TLS 回撥</span><span class="sxs-lookup"><span data-stu-id="b914f-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="b914f-216">設定允許 TLS 回撥。</span><span class="sxs-lookup"><span data-stu-id="b914f-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b914f-217">必要</span><span class="sxs-lookup"><span data-stu-id="b914f-217">Required</span></span></p></td>
<td><p><span data-ttu-id="b914f-218">不支援</span><span class="sxs-lookup"><span data-stu-id="b914f-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b914f-219">False</span><span class="sxs-lookup"><span data-stu-id="b914f-219">False</span></span></p></td>
<td><p><span data-ttu-id="b914f-220">無效設定</span><span class="sxs-lookup"><span data-stu-id="b914f-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b914f-221">必須啟用 SASL 或回撥。</span><span class="sxs-lookup"><span data-stu-id="b914f-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b914f-222">選用</span><span class="sxs-lookup"><span data-stu-id="b914f-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="b914f-223">不支援</span><span class="sxs-lookup"><span data-stu-id="b914f-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b914f-224">是</span><span class="sxs-lookup"><span data-stu-id="b914f-224">True</span></span></p></td>
<td><p><span data-ttu-id="b914f-225">TLS 回撥，TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="b914f-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="b914f-226">根據其他端點的協商選擇，會接受 TCP 或 TLS 回撥。</span><span class="sxs-lookup"><span data-stu-id="b914f-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b914f-227">選用</span><span class="sxs-lookup"><span data-stu-id="b914f-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="b914f-228">不支援</span><span class="sxs-lookup"><span data-stu-id="b914f-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b914f-229">False</span><span class="sxs-lookup"><span data-stu-id="b914f-229">False</span></span></p></td>
<td><p><span data-ttu-id="b914f-230">無效設定</span><span class="sxs-lookup"><span data-stu-id="b914f-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b914f-231">必須啟用 SASL 或回撥。</span><span class="sxs-lookup"><span data-stu-id="b914f-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b914f-232">不支援</span><span class="sxs-lookup"><span data-stu-id="b914f-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b914f-233">不支援</span><span class="sxs-lookup"><span data-stu-id="b914f-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b914f-234">是</span><span class="sxs-lookup"><span data-stu-id="b914f-234">True</span></span></p></td>
<td><p><span data-ttu-id="b914f-235">TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="b914f-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="b914f-236">TCP 回撥是唯一可用的協商方法</span><span class="sxs-lookup"><span data-stu-id="b914f-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b914f-237">不支援</span><span class="sxs-lookup"><span data-stu-id="b914f-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b914f-238">不支援</span><span class="sxs-lookup"><span data-stu-id="b914f-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="b914f-239">False</span><span class="sxs-lookup"><span data-stu-id="b914f-239">False</span></span></p></td>
<td><p><span data-ttu-id="b914f-240">無效設定</span><span class="sxs-lookup"><span data-stu-id="b914f-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="b914f-241">必須啟用 SASL 或回撥。</span><span class="sxs-lookup"><span data-stu-id="b914f-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

