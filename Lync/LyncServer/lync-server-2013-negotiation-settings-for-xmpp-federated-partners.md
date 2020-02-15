---
title: Lync Server 2013： 交涉設定為 XMPP 同盟協力廠商
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
ms.openlocfilehash: c190e4a45a70bd527aa8fc6323a671d481f04872
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="45fb4-102">交涉設定為 XMPP 同盟協力廠商在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45fb4-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45fb4-103">_**主題上次修改日期：** 2012年-10-21_</span><span class="sxs-lookup"><span data-stu-id="45fb4-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="45fb4-104">設定中的 XMPP 協力廠商的交涉類型的設定有各種可能的組合。</span><span class="sxs-lookup"><span data-stu-id="45fb4-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="45fb4-105">並非所有的這些組合都有效。</span><span class="sxs-lookup"><span data-stu-id="45fb4-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="45fb4-106">本主題中詳述的表格會定義有效及無效的設定。</span><span class="sxs-lookup"><span data-stu-id="45fb4-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="45fb4-107">一般設定一文中所述的第一個表格，其中所有可能組合第二個表格。</span><span class="sxs-lookup"><span data-stu-id="45fb4-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="45fb4-108">請注意，您不能有*簡單驗證及安全性階層*(SASL)\**除非\*\*\*傳輸層安全性*(TLS) 也是可用的。</span><span class="sxs-lookup"><span data-stu-id="45fb4-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="45fb4-109">SASL 傳送以未加密 （讀取） 的格式，且應該永遠不容許傳輸除非由另一個方法，例如 TLS 保護。</span><span class="sxs-lookup"><span data-stu-id="45fb4-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="45fb4-110">常見的 XMPP 同盟交涉方法</span><span class="sxs-lookup"><span data-stu-id="45fb4-110">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="45fb4-111">傳輸層安全性 (TLS)</span><span class="sxs-lookup"><span data-stu-id="45fb4-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="45fb4-112">簡單驗證及安全性階層 (SASL)</span><span class="sxs-lookup"><span data-stu-id="45fb4-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="45fb4-113">回撥驗證</span><span class="sxs-lookup"><span data-stu-id="45fb4-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="45fb4-114">預期的驗證方法</span><span class="sxs-lookup"><span data-stu-id="45fb4-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="45fb4-115">附註</span><span class="sxs-lookup"><span data-stu-id="45fb4-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45fb4-116">必要</span><span class="sxs-lookup"><span data-stu-id="45fb4-116">Required</span></span></p></td>
<td><p><span data-ttu-id="45fb4-117">必要</span><span class="sxs-lookup"><span data-stu-id="45fb4-117">Required</span></span></p></td>
<td><p><span data-ttu-id="45fb4-118">False</span><span class="sxs-lookup"><span data-stu-id="45fb4-118">False</span></span></p></td>
<td><p><span data-ttu-id="45fb4-119">SASL 優於 TLS</span><span class="sxs-lookup"><span data-stu-id="45fb4-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="45fb4-120">需要協助確保 SASL 郵件資料流是安全的 TLS 和 SASL。</span><span class="sxs-lookup"><span data-stu-id="45fb4-120">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="45fb4-121">回撥不提供，如果 XMPP 同盟協力廠商不必要或選用設定 TLS 無法用於後援方法。</span><span class="sxs-lookup"><span data-stu-id="45fb4-121">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45fb4-122">必要</span><span class="sxs-lookup"><span data-stu-id="45fb4-122">Required</span></span></p></td>
<td><p><span data-ttu-id="45fb4-123">選擇性</span><span class="sxs-lookup"><span data-stu-id="45fb4-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="45fb4-124">True</span><span class="sxs-lookup"><span data-stu-id="45fb4-124">True</span></span></p></td>
<td><p><span data-ttu-id="45fb4-125">SASL 優於 TLS、 TLS 回撥、 TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="45fb4-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="45fb4-126">依需要 TLS，會使用 XMPP 同盟協力廠商已將 SASL 設定為選用或必要 SASL。</span><span class="sxs-lookup"><span data-stu-id="45fb4-126">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="45fb4-127">如果無法使用 SASL，則會使用透過 TLS 的回撥。</span><span class="sxs-lookup"><span data-stu-id="45fb4-127">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45fb4-128">選用</span><span class="sxs-lookup"><span data-stu-id="45fb4-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="45fb4-129">選用</span><span class="sxs-lookup"><span data-stu-id="45fb4-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="45fb4-130">True</span><span class="sxs-lookup"><span data-stu-id="45fb4-130">True</span></span></p></td>
<td><p><span data-ttu-id="45fb4-131">SASL 優於 TLS、 TLS 回撥、 TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="45fb4-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="45fb4-132">雖然很有彈性中提供的交涉方法，這些設定會依賴 XMPP 同盟協力廠商的設定。</span><span class="sxs-lookup"><span data-stu-id="45fb4-132">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="45fb4-133">如果協力廠商 TLS 選用或必要，但不是支援 SASL，則可使用 TLS 回撥。</span><span class="sxs-lookup"><span data-stu-id="45fb4-133">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="45fb4-134">如果協力廠商 TLS 和 SASL 設為選用或必要，會使用 TLS over SASL 最佳選擇。</span><span class="sxs-lookup"><span data-stu-id="45fb4-134">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45fb4-135">不支援</span><span class="sxs-lookup"><span data-stu-id="45fb4-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="45fb4-136">不支援</span><span class="sxs-lookup"><span data-stu-id="45fb4-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="45fb4-137">True</span><span class="sxs-lookup"><span data-stu-id="45fb4-137">True</span></span></p></td>
<td><p><span data-ttu-id="45fb4-138">TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="45fb4-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="45fb4-139">在許多情況下，TCP 回撥是唯一可能的解決方案。</span><span class="sxs-lookup"><span data-stu-id="45fb4-139">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="45fb4-140">較不建議比其他選項，但是它提供某種程度的信任。</span><span class="sxs-lookup"><span data-stu-id="45fb4-140">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="45fb4-141">XMPP 同盟交涉方法矩陣： 完成</span><span class="sxs-lookup"><span data-stu-id="45fb4-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="45fb4-142">傳輸層安全性 (TLS)</span><span class="sxs-lookup"><span data-stu-id="45fb4-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="45fb4-143">簡單驗證及安全性階層 (SASL)</span><span class="sxs-lookup"><span data-stu-id="45fb4-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="45fb4-144">回撥驗證</span><span class="sxs-lookup"><span data-stu-id="45fb4-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="45fb4-145">預期的驗證方法</span><span class="sxs-lookup"><span data-stu-id="45fb4-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="45fb4-146">備忘稿、 警告或錯誤不正確的設定</span><span class="sxs-lookup"><span data-stu-id="45fb4-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45fb4-147">必要</span><span class="sxs-lookup"><span data-stu-id="45fb4-147">Required</span></span></p></td>
<td><p><span data-ttu-id="45fb4-148">必要</span><span class="sxs-lookup"><span data-stu-id="45fb4-148">Required</span></span></p></td>
<td><p><span data-ttu-id="45fb4-149">True</span><span class="sxs-lookup"><span data-stu-id="45fb4-149">True</span></span></p></td>
<td><p><span data-ttu-id="45fb4-150">SASL 優於 TLS</span><span class="sxs-lookup"><span data-stu-id="45fb4-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="45fb4-151">如果需要 SASL 與 TLS 的回撥將無法運作。</span><span class="sxs-lookup"><span data-stu-id="45fb4-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45fb4-152">必要</span><span class="sxs-lookup"><span data-stu-id="45fb4-152">Required</span></span></p></td>
<td><p><span data-ttu-id="45fb4-153">必要</span><span class="sxs-lookup"><span data-stu-id="45fb4-153">Required</span></span></p></td>
<td><p><span data-ttu-id="45fb4-154">False</span><span class="sxs-lookup"><span data-stu-id="45fb4-154">False</span></span></p></td>
<td><p><span data-ttu-id="45fb4-155">SASL 優於 TLS</span><span class="sxs-lookup"><span data-stu-id="45fb4-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45fb4-156">選用</span><span class="sxs-lookup"><span data-stu-id="45fb4-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="45fb4-157">必要</span><span class="sxs-lookup"><span data-stu-id="45fb4-157">Required</span></span></p></td>
<td><p><span data-ttu-id="45fb4-158">True</span><span class="sxs-lookup"><span data-stu-id="45fb4-158">True</span></span></p></td>
<td><p><span data-ttu-id="45fb4-159">SASL 優於 TLS、 TLS 回撥、 TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="45fb4-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="45fb4-160">SASL 要求 TLS。</span><span class="sxs-lookup"><span data-stu-id="45fb4-160">SASL requires TLS.</span></span> <span data-ttu-id="45fb4-161">允許為選用的 TLS，可能會造成失敗的工作階段交涉。</span><span class="sxs-lookup"><span data-stu-id="45fb4-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45fb4-162">選用</span><span class="sxs-lookup"><span data-stu-id="45fb4-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="45fb4-163">必要</span><span class="sxs-lookup"><span data-stu-id="45fb4-163">Required</span></span></p></td>
<td><p><span data-ttu-id="45fb4-164">False</span><span class="sxs-lookup"><span data-stu-id="45fb4-164">False</span></span></p></td>
<td><p><span data-ttu-id="45fb4-165">SASL 優於 TLS</span><span class="sxs-lookup"><span data-stu-id="45fb4-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="45fb4-166">SASL 要求 TLS。</span><span class="sxs-lookup"><span data-stu-id="45fb4-166">SASL requires TLS.</span></span> <span data-ttu-id="45fb4-167">允許為選用的 TLS，可能會造成失敗的工作階段交涉。</span><span class="sxs-lookup"><span data-stu-id="45fb4-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45fb4-168">不支援</span><span class="sxs-lookup"><span data-stu-id="45fb4-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="45fb4-169">必要</span><span class="sxs-lookup"><span data-stu-id="45fb4-169">Required</span></span></p></td>
<td><p><span data-ttu-id="45fb4-170">True</span><span class="sxs-lookup"><span data-stu-id="45fb4-170">True</span></span></p></td>
<td><p><span data-ttu-id="45fb4-171">TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="45fb4-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="45fb4-172">SASL 要求 TLS。</span><span class="sxs-lookup"><span data-stu-id="45fb4-172">SASL requires TLS.</span></span> <span data-ttu-id="45fb4-173">允許為選用的 TLS，可能會造成失敗的工作階段交涉。</span><span class="sxs-lookup"><span data-stu-id="45fb4-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45fb4-174">不支援</span><span class="sxs-lookup"><span data-stu-id="45fb4-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="45fb4-175">必要</span><span class="sxs-lookup"><span data-stu-id="45fb4-175">Required</span></span></p></td>
<td><p><span data-ttu-id="45fb4-176">False</span><span class="sxs-lookup"><span data-stu-id="45fb4-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="45fb4-177">無效組態</span><span class="sxs-lookup"><span data-stu-id="45fb4-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="45fb4-178">因為 SASL 需要 TLS、 TLS 不提供，SASL/TLS 無法成功。</span><span class="sxs-lookup"><span data-stu-id="45fb4-178">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="45fb4-179">TCP 回撥設定為 false，並無法使用。</span><span class="sxs-lookup"><span data-stu-id="45fb4-179">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45fb4-180">必要</span><span class="sxs-lookup"><span data-stu-id="45fb4-180">Required</span></span></p></td>
<td><p><span data-ttu-id="45fb4-181">選擇性</span><span class="sxs-lookup"><span data-stu-id="45fb4-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="45fb4-182">True</span><span class="sxs-lookup"><span data-stu-id="45fb4-182">True</span></span></p></td>
<td><p><span data-ttu-id="45fb4-183">SASL 優於 TLS、 TLS 回撥</span><span class="sxs-lookup"><span data-stu-id="45fb4-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45fb4-184">必要</span><span class="sxs-lookup"><span data-stu-id="45fb4-184">Required</span></span></p></td>
<td><p><span data-ttu-id="45fb4-185">選擇性</span><span class="sxs-lookup"><span data-stu-id="45fb4-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="45fb4-186">False</span><span class="sxs-lookup"><span data-stu-id="45fb4-186">False</span></span></p></td>
<td><p><span data-ttu-id="45fb4-187">SASL 優於 TLS</span><span class="sxs-lookup"><span data-stu-id="45fb4-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45fb4-188">選用</span><span class="sxs-lookup"><span data-stu-id="45fb4-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="45fb4-189">選用</span><span class="sxs-lookup"><span data-stu-id="45fb4-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="45fb4-190">True</span><span class="sxs-lookup"><span data-stu-id="45fb4-190">True</span></span></p></td>
<td><p><span data-ttu-id="45fb4-191">SASL 優於 TLS、 TLS 回撥、 TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="45fb4-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="45fb4-192">SASL 要求 TLS。</span><span class="sxs-lookup"><span data-stu-id="45fb4-192">SASL requires TLS.</span></span> <span data-ttu-id="45fb4-193">允許為選用的 TLS，可能會造成失敗的工作階段交涉。</span><span class="sxs-lookup"><span data-stu-id="45fb4-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45fb4-194">選用</span><span class="sxs-lookup"><span data-stu-id="45fb4-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="45fb4-195">選用</span><span class="sxs-lookup"><span data-stu-id="45fb4-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="45fb4-196">False</span><span class="sxs-lookup"><span data-stu-id="45fb4-196">False</span></span></p></td>
<td><p><span data-ttu-id="45fb4-197">SASL 優於 TLS</span><span class="sxs-lookup"><span data-stu-id="45fb4-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="45fb4-198">SASL 要求 TLS。</span><span class="sxs-lookup"><span data-stu-id="45fb4-198">SASL requires TLS.</span></span> <span data-ttu-id="45fb4-199">允許為選用的 TLS，可能會造成失敗的工作階段交涉。</span><span class="sxs-lookup"><span data-stu-id="45fb4-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45fb4-200">不支援</span><span class="sxs-lookup"><span data-stu-id="45fb4-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="45fb4-201">選用</span><span class="sxs-lookup"><span data-stu-id="45fb4-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="45fb4-202">True</span><span class="sxs-lookup"><span data-stu-id="45fb4-202">True</span></span></p></td>
<td><p><span data-ttu-id="45fb4-203">TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="45fb4-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="45fb4-204">SASL 要求 TLS。</span><span class="sxs-lookup"><span data-stu-id="45fb4-204">SASL requires TLS.</span></span> <span data-ttu-id="45fb4-205">允許為選用的 TLS，可能會造成失敗的工作階段交涉。</span><span class="sxs-lookup"><span data-stu-id="45fb4-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45fb4-206">不支援</span><span class="sxs-lookup"><span data-stu-id="45fb4-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="45fb4-207">選用</span><span class="sxs-lookup"><span data-stu-id="45fb4-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="45fb4-208">False</span><span class="sxs-lookup"><span data-stu-id="45fb4-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="45fb4-209">無效組態</span><span class="sxs-lookup"><span data-stu-id="45fb4-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="45fb4-210">SASL 要求 TLS。</span><span class="sxs-lookup"><span data-stu-id="45fb4-210">SASL requires TLS.</span></span> <span data-ttu-id="45fb4-211">允許為選用的 TLS，可能會造成失敗的工作階段交涉。</span><span class="sxs-lookup"><span data-stu-id="45fb4-211">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45fb4-212">必要</span><span class="sxs-lookup"><span data-stu-id="45fb4-212">Required</span></span></p></td>
<td><p><span data-ttu-id="45fb4-213">不支援</span><span class="sxs-lookup"><span data-stu-id="45fb4-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="45fb4-214">True</span><span class="sxs-lookup"><span data-stu-id="45fb4-214">True</span></span></p></td>
<td><p><span data-ttu-id="45fb4-215">TLS 回撥</span><span class="sxs-lookup"><span data-stu-id="45fb4-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="45fb4-216">組態可用於 TLS 回撥。</span><span class="sxs-lookup"><span data-stu-id="45fb4-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45fb4-217">必要</span><span class="sxs-lookup"><span data-stu-id="45fb4-217">Required</span></span></p></td>
<td><p><span data-ttu-id="45fb4-218">不支援</span><span class="sxs-lookup"><span data-stu-id="45fb4-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="45fb4-219">False</span><span class="sxs-lookup"><span data-stu-id="45fb4-219">False</span></span></p></td>
<td><p><span data-ttu-id="45fb4-220">無效組態</span><span class="sxs-lookup"><span data-stu-id="45fb4-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="45fb4-221">SASL 或回撥必須啟用。</span><span class="sxs-lookup"><span data-stu-id="45fb4-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45fb4-222">選用</span><span class="sxs-lookup"><span data-stu-id="45fb4-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="45fb4-223">不支援</span><span class="sxs-lookup"><span data-stu-id="45fb4-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="45fb4-224">True</span><span class="sxs-lookup"><span data-stu-id="45fb4-224">True</span></span></p></td>
<td><p><span data-ttu-id="45fb4-225">TLS 回撥、 TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="45fb4-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="45fb4-226">根據其他端點的交涉選擇，TCP 或 TLS 回撥將被接受。</span><span class="sxs-lookup"><span data-stu-id="45fb4-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45fb4-227">選用</span><span class="sxs-lookup"><span data-stu-id="45fb4-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="45fb4-228">不支援</span><span class="sxs-lookup"><span data-stu-id="45fb4-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="45fb4-229">False</span><span class="sxs-lookup"><span data-stu-id="45fb4-229">False</span></span></p></td>
<td><p><span data-ttu-id="45fb4-230">無效組態</span><span class="sxs-lookup"><span data-stu-id="45fb4-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="45fb4-231">SASL 或回撥必須啟用。</span><span class="sxs-lookup"><span data-stu-id="45fb4-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45fb4-232">不支援</span><span class="sxs-lookup"><span data-stu-id="45fb4-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="45fb4-233">不支援</span><span class="sxs-lookup"><span data-stu-id="45fb4-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="45fb4-234">True</span><span class="sxs-lookup"><span data-stu-id="45fb4-234">True</span></span></p></td>
<td><p><span data-ttu-id="45fb4-235">TCP 回撥</span><span class="sxs-lookup"><span data-stu-id="45fb4-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="45fb4-236">TCP 回撥是可用的唯一的交涉方法</span><span class="sxs-lookup"><span data-stu-id="45fb4-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45fb4-237">不支援</span><span class="sxs-lookup"><span data-stu-id="45fb4-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="45fb4-238">不支援</span><span class="sxs-lookup"><span data-stu-id="45fb4-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="45fb4-239">False</span><span class="sxs-lookup"><span data-stu-id="45fb4-239">False</span></span></p></td>
<td><p><span data-ttu-id="45fb4-240">無效組態</span><span class="sxs-lookup"><span data-stu-id="45fb4-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="45fb4-241">SASL 或回撥必須啟用。</span><span class="sxs-lookup"><span data-stu-id="45fb4-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

