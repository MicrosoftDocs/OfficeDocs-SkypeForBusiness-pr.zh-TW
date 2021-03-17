---
title: 電話系統直接路由
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: 直接路由通訊協定
appliesto:
- Microsoft Teams
ms.openlocfilehash: 26d6555b82db1939b879ecafc113ced186528f80
ms.sourcegitcommit: 360c78c66386fe00afe535681f51254eda886edf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2021
ms.locfileid: "50837000"
---
# <a name="direct-routing---sip-protocol"></a><span data-ttu-id="4c412-103">直接路由 - SIP 通訊協定</span><span class="sxs-lookup"><span data-stu-id="4c412-103">Direct Routing - SIP protocol</span></span>

<span data-ttu-id="4c412-104">本文將說明直接路由如何將會話初始通訊協定 (SIP) 。</span><span class="sxs-lookup"><span data-stu-id="4c412-104">This article describes how Direct Routing implements the Session Initiation Protocol (SIP).</span></span> <span data-ttu-id="4c412-105">若要正確路由會話邊界控制器 (SBC) SIP Proxy 之間的流量，某些 SIP 參數必須具有特定值。</span><span class="sxs-lookup"><span data-stu-id="4c412-105">To properly route traffic between a Session Border Controller (SBC) and the SIP proxy, some SIP parameters must have specific values.</span></span> <span data-ttu-id="4c412-106">本文適用于負責在內部部署 SBC 與 SIP Proxy 服務之間建立連接之語音系統管理員。</span><span class="sxs-lookup"><span data-stu-id="4c412-106">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a><span data-ttu-id="4c412-107">處理傳入要求：尋找租使用者和使用者</span><span class="sxs-lookup"><span data-stu-id="4c412-107">Processing the incoming request: finding the tenant and user</span></span>

<span data-ttu-id="4c412-108">在可以處理傳入或外接通話之前，在 SIP Proxy 和 SBC 之間交換 OPTIONS 訊息。</span><span class="sxs-lookup"><span data-stu-id="4c412-108">Before an incoming or outbound call can be processed, OPTIONS messages are exchanged between SIP Proxy and the SBC.</span></span> <span data-ttu-id="4c412-109">這些選項訊息允許 SIP Proxy 提供 SBC 允許的功能。</span><span class="sxs-lookup"><span data-stu-id="4c412-109">These OPTIONS messages allow SIP Proxy to provide the allowed capabilities to SBC.</span></span> <span data-ttu-id="4c412-110">在 200OK 回應 (選項的) ，讓 SBC 與 SIP Proxy 之間的進一步通訊，以建立通話，這一點非常重要。</span><span class="sxs-lookup"><span data-stu-id="4c412-110">It is important for OPTIONS negotiation to be successful (200OK response), allowing for further communication between SBC and SIP Proxy for establishing calls.</span></span> <span data-ttu-id="4c412-111">選項訊息中 SIP Proxy 的 SIP 標題如下例所示：</span><span class="sxs-lookup"><span data-stu-id="4c412-111">The SIP headers in an OPTIONS messages to SIP Proxy are provided as an example below:</span></span>

| <span data-ttu-id="4c412-112">參數名稱</span><span class="sxs-lookup"><span data-stu-id="4c412-112">Parameter name</span></span> | <span data-ttu-id="4c412-113">值範例</span><span class="sxs-lookup"><span data-stu-id="4c412-113">Example of the value</span></span> | 
| :---------------------  |:---------------------- |
| <span data-ttu-id="4c412-114">Request-URI</span><span class="sxs-lookup"><span data-stu-id="4c412-114">Request-URI</span></span> | <span data-ttu-id="4c412-115">選項 sip：sip.pstnhub.microsoft.com：5061 SIP /2.0</span><span class="sxs-lookup"><span data-stu-id="4c412-115">OPTIONS sip:sip.pstnhub.microsoft.com:5061 SIP /2.0</span></span> |
| <span data-ttu-id="4c412-116">透過標題</span><span class="sxs-lookup"><span data-stu-id="4c412-116">Via Header</span></span> | <span data-ttu-id="4c412-117">Via：SIP/2.0/TLS sbc1.adatum.biz：5058;alias;branch=z9hG4bKac2121518978</span><span class="sxs-lookup"><span data-stu-id="4c412-117">Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978</span></span> | 
| <span data-ttu-id="4c412-118">Max-Forwards頁標題</span><span class="sxs-lookup"><span data-stu-id="4c412-118">Max-Forwards header</span></span> | <span data-ttu-id="4c412-119">Max-Forwards：68</span><span class="sxs-lookup"><span data-stu-id="4c412-119">Max-Forwards:68</span></span> |
| <span data-ttu-id="4c412-120">從頁頭</span><span class="sxs-lookup"><span data-stu-id="4c412-120">From Header</span></span> | <span data-ttu-id="4c412-121">從頁頭來源： <sip:sbc1.adatum.biz:5058></span><span class="sxs-lookup"><span data-stu-id="4c412-121">From Header From: <sip:sbc1.adatum.biz:5058></span></span> |
| <span data-ttu-id="4c412-122">至頁標題</span><span class="sxs-lookup"><span data-stu-id="4c412-122">To Header</span></span> | <span data-ttu-id="4c412-123">自： <sip:sip.pstnhub.microsoft.com:5061></span><span class="sxs-lookup"><span data-stu-id="4c412-123">To: <sip:sip.pstnhub.microsoft.com:5061></span></span> |
| <span data-ttu-id="4c412-124">CSeq 標頭</span><span class="sxs-lookup"><span data-stu-id="4c412-124">CSeq header</span></span> | <span data-ttu-id="4c412-125">CSeq：1 INVITE</span><span class="sxs-lookup"><span data-stu-id="4c412-125">CSeq: 1 INVITE</span></span> | 
| <span data-ttu-id="4c412-126">連絡人標題</span><span class="sxs-lookup"><span data-stu-id="4c412-126">Contact Header</span></span> | <span data-ttu-id="4c412-127">聯繫： <sip:sbc1.adatum.biz:50588;transport=tls></span><span class="sxs-lookup"><span data-stu-id="4c412-127">Contact: <sip:sbc1.adatum.biz:50588;transport=tls></span></span> |

> [!NOTE]
> <span data-ttu-id="4c412-128">SIP 標頭在使用的 SIP URI 中不包含 userinfo。</span><span class="sxs-lookup"><span data-stu-id="4c412-128">The SIP headers do not contain userinfo in the SIP URI in use.</span></span> <span data-ttu-id="4c412-129">根據 [RFC 3261，第 19.1.1](https://tools.ietf.org/html/rfc3261#section-19.1.1)節，URI 的使用者資訊部分為選擇性，當目的地主機沒有使用者的概念，或當 hosst 本身為所識別的資源時，可能會不存在。</span><span class="sxs-lookup"><span data-stu-id="4c412-129">As per [RFC 3261, section 19.1.1](https://tools.ietf.org/html/rfc3261#section-19.1.1), the userinfo part of a URI is optional and MAY be absent when the destination host does not have a notion of users or when the hosst itself is the resource being identified.</span></span> <span data-ttu-id="4c412-130">如果 SIP URI 中出現 @ 符號，則使用者欄位不能是空的。</span><span class="sxs-lookup"><span data-stu-id="4c412-130">If the @ sign is present in a SIP URI, the user field MUST NOT be empty.</span></span>

<span data-ttu-id="4c412-131">在來電中，SIP Proxy 必須尋找該通話的目的地租使用者，並在此租使用者中尋找特定使用者。</span><span class="sxs-lookup"><span data-stu-id="4c412-131">On an incoming call, the SIP proxy needs to find the tenant to which the call is destined and find the specific user within this tenant.</span></span> <span data-ttu-id="4c412-132">租使用者系統管理員可能會在多個租使用者中設定非 DID 號碼，例如 +1001。</span><span class="sxs-lookup"><span data-stu-id="4c412-132">The tenant administrator might configure non-DID numbers, for example +1001, in multiple tenants.</span></span> <span data-ttu-id="4c412-133">因此，尋找要執行數位尋找的特定租使用者非常重要，因為多個 Microsoft 365 或 Office 365 組織中非 DID 號碼可能相同。</span><span class="sxs-lookup"><span data-stu-id="4c412-133">Therefore, it is important to find the specific tenant on which to perform the number lookup because the non-DID numbers might be the same in multiple Microsoft 365 or Office 365 organizations.</span></span>  

<span data-ttu-id="4c412-134">本節說明 SIP Proxy 如何尋找租使用者和使用者，以及如何在傳入連接上執行 SBC 的驗證。</span><span class="sxs-lookup"><span data-stu-id="4c412-134">This section describes how the SIP proxy finds the tenant and the user, and performs authentication of the SBC on the incoming connection.</span></span>

<span data-ttu-id="4c412-135">以下是來電上 SIP 邀請訊息的範例：</span><span class="sxs-lookup"><span data-stu-id="4c412-135">The following is an example of the SIP Invite message on an incoming call:</span></span>

| <span data-ttu-id="4c412-136">參數名稱</span><span class="sxs-lookup"><span data-stu-id="4c412-136">Parameter name</span></span> | <span data-ttu-id="4c412-137">值範例</span><span class="sxs-lookup"><span data-stu-id="4c412-137">Example of the value</span></span> | 
| :---------------------  |:---------------------- |
| <span data-ttu-id="4c412-138">Request-URI</span><span class="sxs-lookup"><span data-stu-id="4c412-138">Request-URI</span></span> | <span data-ttu-id="4c412-139">邀請 sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0</span><span class="sxs-lookup"><span data-stu-id="4c412-139">INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0</span></span> |
| <span data-ttu-id="4c412-140">透過標題</span><span class="sxs-lookup"><span data-stu-id="4c412-140">Via Header</span></span> | <span data-ttu-id="4c412-141">Via：SIP/2.0/TLS sbc1.adatum.biz：5058;alias;branch=z9hG4bKac2121518978</span><span class="sxs-lookup"><span data-stu-id="4c412-141">Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978</span></span> | 
| <span data-ttu-id="4c412-142">Max-Forwards頁標題</span><span class="sxs-lookup"><span data-stu-id="4c412-142">Max-Forwards header</span></span> | <span data-ttu-id="4c412-143">Max-Forwards：68</span><span class="sxs-lookup"><span data-stu-id="4c412-143">Max-Forwards:68</span></span> |
| <span data-ttu-id="4c412-144">從頁頭</span><span class="sxs-lookup"><span data-stu-id="4c412-144">From Header</span></span> | <span data-ttu-id="4c412-145">從頁<：7168712781@sbc1 <.adatum.biz;transport=udp;tag=1c747237679</span><span class="sxs-lookup"><span data-stu-id="4c412-145">From Header From: <sip:7168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679</span></span> |
| <span data-ttu-id="4c412-146">至頁標題</span><span class="sxs-lookup"><span data-stu-id="4c412-146">To Header</span></span> | <span data-ttu-id="4c412-147">至：sip:+183338006777@sbc1.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4c412-147">To: sip:+183338006777@sbc1.adatum.biz</span></span> | 
| <span data-ttu-id="4c412-148">CSeq 標頭</span><span class="sxs-lookup"><span data-stu-id="4c412-148">CSeq header</span></span> | <span data-ttu-id="4c412-149">CSeq：1 INVITE</span><span class="sxs-lookup"><span data-stu-id="4c412-149">CSeq: 1 INVITE</span></span> | 
| <span data-ttu-id="4c412-150">連絡人標題</span><span class="sxs-lookup"><span data-stu-id="4c412-150">Contact Header</span></span> | <span data-ttu-id="4c412-151">連絡人：<sip：68712781@sbc1.adatum.biz：5058;transport=tls></span><span class="sxs-lookup"><span data-stu-id="4c412-151">Contact: <sip: 68712781@sbc1.adatum.biz:5058;transport=tls></span></span> | 

<span data-ttu-id="4c412-152">在收到邀請時，SIP Proxy 會執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="4c412-152">On receiving the invite, the SIP proxy performs the following steps:</span></span>

1. <span data-ttu-id="4c412-153">檢查憑證。</span><span class="sxs-lookup"><span data-stu-id="4c412-153">Check the certificate.</span></span> <span data-ttu-id="4c412-154">在初始連接上，直接路由服務會採用連絡人標題中呈現的 FQDN 名稱，並比對到所提交憑證的公用名稱或主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="4c412-154">On the initial connection, the Direct Routing service takes the FQDN name presented in the Contact header and matches it to the Common Name or Subject Alternative name of the presented certificate.</span></span> <span data-ttu-id="4c412-155">SBC 名稱必須與下列其中一個選項相符：</span><span class="sxs-lookup"><span data-stu-id="4c412-155">The SBC name must match one of the following options:</span></span>

   - <span data-ttu-id="4c412-156">選項 1.</span><span class="sxs-lookup"><span data-stu-id="4c412-156">Option 1.</span></span> <span data-ttu-id="4c412-157">連絡人標題中顯示的完整 FQDN 名稱必須與所提交憑證的公用名稱/主體替代名稱相符。</span><span class="sxs-lookup"><span data-stu-id="4c412-157">The full FQDN name presented in the Contact header must match the Common Name/Subject Alternative name of the presented certificate.</span></span>  

   - <span data-ttu-id="4c412-158">選項 2.</span><span class="sxs-lookup"><span data-stu-id="4c412-158">Option 2.</span></span> <span data-ttu-id="4c412-159">在連絡人標題 (例如 FQDN 名稱 adatum.biz 中呈現的 FQDN 名稱的網域部分 sbc1.adatum.biz) 必須與 Common Name/Subject 替換名稱 (例如 \*.adatum.biz) 中的萬用字元值相符。</span><span class="sxs-lookup"><span data-stu-id="4c412-159">The domain portion of the FQDN name presented in the Contact header (for example adatum.biz of the FQDN name sbc1.adatum.biz) must match the wildcard value in Common Name/Subject Alternative Name (for example \*.adatum.biz).</span></span>

2. <span data-ttu-id="4c412-160">嘗試使用連絡人標題中顯示的完整 FQDN 名稱來尋找租使用者。</span><span class="sxs-lookup"><span data-stu-id="4c412-160">Try to find a tenant using the full FQDN name presented in the Contact header.</span></span>  

   <span data-ttu-id="4c412-161">檢查連絡人標題中的 FQDN 名稱 (sbc1.adatum.biz) 在任何 Microsoft 365 或 Office 365 組織中註冊為 DNS 名稱。</span><span class="sxs-lookup"><span data-stu-id="4c412-161">Check if the FQDN name from the Contact header (sbc1.adatum.biz) is registered as a DNS name in any Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="4c412-162">如果找到，使用者的尋找是在已註冊為功能變數名稱的 SBC FQDN 的租使用者中執行。</span><span class="sxs-lookup"><span data-stu-id="4c412-162">If found, the lookup of the user is performed in the tenant that has the SBC FQDN registered as a Domain name.</span></span> <span data-ttu-id="4c412-163">如果找不到，則適用步驟 3。</span><span class="sxs-lookup"><span data-stu-id="4c412-163">If not found, Step 3 applies.</span></span>   

3. <span data-ttu-id="4c412-164">步驟 3 僅適用于步驟 2 失敗的情況。</span><span class="sxs-lookup"><span data-stu-id="4c412-164">Step 3 only applies if Step 2 failed.</span></span> 

   <span data-ttu-id="4c412-165">移除主機部分 ：adatum.biz) 之後，從 FQDN 移除 FQDN 的主機部分，如連絡人標題 (FQDN：sbc12.adatum.biz，並檢查此名稱是否在任何 Microsoft 365 或 Office 365 組織中註冊為 DNS 名稱。</span><span class="sxs-lookup"><span data-stu-id="4c412-165">Remove the host portion from the FQDN, presented in the Contact header (FQDN: sbc12.adatum.biz, after removing the host portion: adatum.biz), and check if this name is registered as a DNS name in any Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="4c412-166">如果找到，會在此租使用者中執行使用者查找。</span><span class="sxs-lookup"><span data-stu-id="4c412-166">If found, the user lookup is performed in this tenant.</span></span> <span data-ttu-id="4c412-167">如果找不到，通話會失敗。</span><span class="sxs-lookup"><span data-stu-id="4c412-167">If not found, the call fails.</span></span>

4. <span data-ttu-id="4c412-168">使用 Request-URI 中提供的電話號碼，在步驟 2 或 3 找到的租使用者中執行反向號碼尋找。</span><span class="sxs-lookup"><span data-stu-id="4c412-168">Using the phone number presented in the Request-URI, perform the reverse number lookup within the tenant found in Step 2 or 3.</span></span> <span data-ttu-id="4c412-169">在上一個步驟找到的租使用者中，將呈現的電話號碼與使用者 SIP URI 相符。</span><span class="sxs-lookup"><span data-stu-id="4c412-169">Match the presented phone number to a user SIP URI within the tenant found on the previous step.</span></span>

5. <span data-ttu-id="4c412-170">使用主幹設定。</span><span class="sxs-lookup"><span data-stu-id="4c412-170">Apply trunk settings.</span></span> <span data-ttu-id="4c412-171">尋找租使用者系統管理員為此 SBC 所設定的參數。</span><span class="sxs-lookup"><span data-stu-id="4c412-171">Find the parameters set by the tenant admin for this SBC.</span></span>

   <span data-ttu-id="4c412-172">Microsoft 不支援在 Microsoft SIP Proxy 與配對 SBC 之間擁有協力廠商 SIP Proxy 或使用者代理伺服器，這可能會修改配對 SBC 所建立的要求 URI。</span><span class="sxs-lookup"><span data-stu-id="4c412-172">Microsoft does not support having a third-party SIP proxy or User Agent Server between the Microsoft SIP proxy and the paired SBC, which might modify the Request URI created by the paired SBC.</span></span>

   <span data-ttu-id="4c412-173">本文稍後將 (SBC 與許多租使用者 (電信企業案例) 進行互連時所需的步驟 2 和) 3) 。</span><span class="sxs-lookup"><span data-stu-id="4c412-173">The requirements for the two lookups (steps 2 and 3) needed for the scenario where one SBC is interconnected to many tenants (carrier scenario) are covered later in this article.</span></span>

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a><span data-ttu-id="4c412-174">連絡人標題和 Request-URI 的詳細需求</span><span class="sxs-lookup"><span data-stu-id="4c412-174">Detailed requirements for Contact header and Request-URI</span></span>

#### <a name="contact-header"></a><span data-ttu-id="4c412-175">連絡人標題</span><span class="sxs-lookup"><span data-stu-id="4c412-175">Contact header</span></span>

<span data-ttu-id="4c412-176">針對所有傳入的 SIP (OPTIONS、INVITE) 到 Microsoft SIP Proxy，連絡人標題必須在 URI 主機名稱中具有配對的 SBC FQDN，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4c412-176">For all incoming SIP messages (OPTIONS, INVITE) to the Microsoft SIP proxy, the Contact header must have the paired SBC FQDN in the URI hostname as follows:</span></span>

<span data-ttu-id="4c412-177">語法：連絡人：<sip：phone 或 sip address@FQDN sBC;transport=tls></span><span class="sxs-lookup"><span data-stu-id="4c412-177">Syntax: Contact:  <sip:phone or sip address@FQDN of the SBC;transport=tls></span></span> 

<span data-ttu-id="4c412-178">根據 [RFC 3261，第 11.1](https://tools.ietf.org/html/rfc3261#section-11.1)節，連絡人標題欄位可能存在於 OPTIONS 訊息中。</span><span class="sxs-lookup"><span data-stu-id="4c412-178">As per [RFC 3261, section 11.1](https://tools.ietf.org/html/rfc3261#section-11.1), a Contact header field MAY be present in an OPTIONS message.</span></span> <span data-ttu-id="4c412-179">在直接路由中，連絡人標題為必填項。</span><span class="sxs-lookup"><span data-stu-id="4c412-179">In Direct Routing the contact header is required.</span></span> <span data-ttu-id="4c412-180">針對上述格式的 INVITE 郵件，對於 OPTIONS 郵件，使用者資訊可以從 SIP URI 中移除，且只能以以下格式送出 FQDN：</span><span class="sxs-lookup"><span data-stu-id="4c412-180">For INVITE messages in format above, for OPTIONS messages the userinfo can be removed from SIP URI and only FQDN sent in format as follows:</span></span>

<span data-ttu-id="4c412-181">語法：Contact：<sip：SBC 的 FQDN;transport=tls></span><span class="sxs-lookup"><span data-stu-id="4c412-181">Syntax: Contact:  <sip:FQDN of the SBC;transport=tls></span></span>

<span data-ttu-id="4c412-182">FQDN (名稱) 也必須在所提交憑證的 (或) 名稱欄位。</span><span class="sxs-lookup"><span data-stu-id="4c412-182">This name (FQDN) must also be in the Common Name or Subject Alternative name field(s) of the presented certificate.</span></span> <span data-ttu-id="4c412-183">Microsoft 支援在憑證的 (或) 名稱欄位中使用名稱的萬用字元值。</span><span class="sxs-lookup"><span data-stu-id="4c412-183">Microsoft supports using wildcard values of the name(s) in the Common Name or Subject Alternative Name fields of the certificate.</span></span>   

<span data-ttu-id="4c412-184">RFC [2818 第 3.1](https://tools.ietf.org/html/rfc2818#section-3.1)節說明萬用字元的支援。</span><span class="sxs-lookup"><span data-stu-id="4c412-184">The support for wildcards is described in [RFC 2818, section 3.1](https://tools.ietf.org/html/rfc2818#section-3.1).</span></span> <span data-ttu-id="4c412-185">特別：</span><span class="sxs-lookup"><span data-stu-id="4c412-185">Specifically:</span></span>

<span data-ttu-id="4c412-186">*「名稱可能包含萬用字元，視為符合任何 \* 單一功能變數名稱元件或元件片段。例如 \* ，.a.com 符合 foo.a.com，bar.foo.a.com. f .com foo.com \* 不 bar.com」。*</span><span class="sxs-lookup"><span data-stu-id="4c412-186">*"Names may contain the wildcard character \* which is considered to match any single domain name component or component fragment. E.g., \*.a.com matches foo.a.com but not bar.foo.a.com. f\*.com matches foo.com but not bar.com."*</span></span>

<span data-ttu-id="4c412-187">如果 SBC 會送出 SIP 郵件中呈現的連絡人標題中的多個值，則只會使用連絡人標題第一個值的 FQDN 部分。</span><span class="sxs-lookup"><span data-stu-id="4c412-187">If more than one value in the Contact header presented in a SIP message is sent by the SBC, only the FQDN portion of the first value of the Contact header is used.</span></span>

<span data-ttu-id="4c412-188">根據直接路由的經驗，FQDN 必須用來填入 SIP URI，而不是 IP。</span><span class="sxs-lookup"><span data-stu-id="4c412-188">As rule of thumb for Direct Routing, it is important that FQDN is used to populate SIP URI instead of IP.</span></span> <span data-ttu-id="4c412-189">接收 INVITE 或 OPTIONS 訊息給 SIP Proxy 的連絡人標頭，其中主機名稱是由 IP 代表，而不是 FQDN，因此會以 403 禁止拒絕連接。</span><span class="sxs-lookup"><span data-stu-id="4c412-189">An incoming INVITE or OPTIONS message to SIP Proxy with Contact header where hostname is represented by IP and not FQDN, the connection will be refused with 403 Forbidden.</span></span>

#### <a name="request-uri"></a><span data-ttu-id="4c412-190">Request-URI</span><span class="sxs-lookup"><span data-stu-id="4c412-190">Request-URI</span></span> 

<span data-ttu-id="4c412-191">針對所有來電，Request-URI 會用來將電話號碼與使用者相符。</span><span class="sxs-lookup"><span data-stu-id="4c412-191">For all incoming calls, the Request-URI is used to match the phone number to a user.</span></span>   

<span data-ttu-id="4c412-192">目前電話號碼必須包含加 (+) 如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="4c412-192">Currently The phone number must contain a plus sign (+) as shown in the following example.</span></span> 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a><span data-ttu-id="4c412-193">連絡人和Record-Route標題的考慮</span><span class="sxs-lookup"><span data-stu-id="4c412-193">Contact and Record-Route headers considerations</span></span>

<span data-ttu-id="4c412-194">SIP Proxy 需要計算新對話方塊用戶端交易的下一躍點 FQDN (例如 Bye 或重新邀請) ，以及回復 SIP 選項時。</span><span class="sxs-lookup"><span data-stu-id="4c412-194">The SIP proxy needs to calculate the next hop FQDN for new in-dialog client transactions (for example Bye or Re-Invite), and when replying to SIP Options.</span></span> <span data-ttu-id="4c412-195">使用連絡人Record-Route或連絡人。</span><span class="sxs-lookup"><span data-stu-id="4c412-195">Either Contact or Record-Route are used.</span></span> 

<span data-ttu-id="4c412-196">根據 [RFC 3261 第 8.1.1.8](https://tools.ietf.org/html/rfc3261#section-8.1.1.8)節，任何可能導致新對話方塊的要求都需要連絡人標題。</span><span class="sxs-lookup"><span data-stu-id="4c412-196">According to [RFC 3261, section 8.1.1.8](https://tools.ietf.org/html/rfc3261#section-8.1.1.8), Contact header is required in any request that can result in a new dialog.</span></span> <span data-ttu-id="4c412-197">只有Record-Route Proxy 想要在對話方塊中維持未來要求的路徑時，才需要執行此要求。</span><span class="sxs-lookup"><span data-stu-id="4c412-197">The Record-Route is only required if a proxy wants to stay on the path of future requests in a dialog.</span></span> <span data-ttu-id="4c412-198">如果 Proxy SBC 與直接路由的 Local [Media 優化](https://docs.microsoft.com/MicrosoftTeams/direct-routing-media-optimization)一起使用，則需要將記錄路由進行配置，因為 Proxy SBC 必須留在路由中。</span><span class="sxs-lookup"><span data-stu-id="4c412-198">If a proxy SBC is in use with [Local Media Optimization for Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-media-optimization), a record route will need to be configured as the proxy SBC needs to stay in the route.</span></span> 

<span data-ttu-id="4c412-199">若未使用 Proxy SBC，Microsoft 建議只使用連絡人標題：</span><span class="sxs-lookup"><span data-stu-id="4c412-199">Microsoft recommends using only Contact header if a proxy SBC is not used:</span></span>

- <span data-ttu-id="4c412-200">每個 [RFC 3261，第 20.30](https://tools.ietf.org/html/rfc3261#section-20.30)節 ，Record-Route 是當 Proxy 想要在對話方塊中維持未來要求的路徑時，會使用 ，如果系統未針對 Microsoft SIP Proxy 與配對 SBC 之間的所有流量進行任何 Proxy SBC 的組組，則不需要此方式。</span><span class="sxs-lookup"><span data-stu-id="4c412-200">Per [RFC 3261, section 20.30](https://tools.ietf.org/html/rfc3261#section-20.30), Record-Route is used if a proxy wants to stay on the path of future requests in a dialog, which is not essential if no proxy SBC is configured as all traffic goes between the Microsoft SIP proxy and the paired SBC.</span></span> 

- <span data-ttu-id="4c412-201">Microsoft SIP Proxy 只會使用連絡人標題 (而非 Record-Route) 傳送出站 ping 選項時決定下一個躍點。</span><span class="sxs-lookup"><span data-stu-id="4c412-201">The Microsoft SIP proxy uses only Contact header (not Record-Route) to determine the next hop when sending outbound ping Options.</span></span> <span data-ttu-id="4c412-202">若不使用 proxy SBC (，) 只設定一個參數， (Contact 和 Record-Route) 可簡化系統管理。</span><span class="sxs-lookup"><span data-stu-id="4c412-202">Configuring only one parameter (Contact) instead of two (Contact and Record-Route) simplifies the administration if a proxy SBC is not in use.</span></span> 

<span data-ttu-id="4c412-203">若要計算下一個躍點，SIP Proxy 會使用：</span><span class="sxs-lookup"><span data-stu-id="4c412-203">To calculate the next hop, the SIP proxy uses:</span></span>

- <span data-ttu-id="4c412-204">優先順序 1。</span><span class="sxs-lookup"><span data-stu-id="4c412-204">Priority 1.</span></span> <span data-ttu-id="4c412-205">頂層的 Record-Route。</span><span class="sxs-lookup"><span data-stu-id="4c412-205">Top-level Record-Route.</span></span> <span data-ttu-id="4c412-206">如果頂層Record-Route包含 FQDN 名稱，FQDN 名稱會用來建立出站對話方塊連接。</span><span class="sxs-lookup"><span data-stu-id="4c412-206">If the top-level Record-Route contains the FQDN name, the FQDN name is used to make the outbound in-dialog connection.</span></span>

- <span data-ttu-id="4c412-207">優先順序 2。</span><span class="sxs-lookup"><span data-stu-id="4c412-207">Priority 2.</span></span> <span data-ttu-id="4c412-208">連絡人標題。</span><span class="sxs-lookup"><span data-stu-id="4c412-208">Contact header.</span></span> <span data-ttu-id="4c412-209">如果Record-Route，SIP Proxy 會尋找連絡人標頭的值，以建立外發連接。</span><span class="sxs-lookup"><span data-stu-id="4c412-209">If Record-Route does not exist, the SIP proxy will look up the value of the Contact header to make the outbound connection.</span></span> <span data-ttu-id="4c412-210"> (這是建議的組) </span><span class="sxs-lookup"><span data-stu-id="4c412-210">(This is the recommended configuration.)</span></span>

<span data-ttu-id="4c412-211">如果同時使用連絡人Record-Route，SBC 系統管理員必須保持其值相同，這會造成系統管理負荷。</span><span class="sxs-lookup"><span data-stu-id="4c412-211">If both Contact and Record-Route are used, the SBC administrator must keep their values identical, which causes administrative overhead.</span></span> 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a><span data-ttu-id="4c412-212">在連絡人或連絡人中使用 FQDN Record-Route</span><span class="sxs-lookup"><span data-stu-id="4c412-212">Use of FQDN name in Contact or Record-Route</span></span>

<span data-ttu-id="4c412-213">在連絡人或連絡人中不支援使用 IP 位址Record-Route IP 位址。</span><span class="sxs-lookup"><span data-stu-id="4c412-213">Use of an IP address is not supported in either Record-Route or Contact.</span></span> <span data-ttu-id="4c412-214">唯一支援的選項是 FQDN，它必須與 SBC 憑證的公用名稱或主體替代名稱相符 (憑證中的萬用字元值) 。</span><span class="sxs-lookup"><span data-stu-id="4c412-214">The only supported option is an FQDN, which must match either the Common Name or Subject Alternative Name of the SBC certificate (wildcard values in the certificate are supported).</span></span>

- <span data-ttu-id="4c412-215">如果在 Record-route 或 Contact 中顯示 IP 位址，憑證檢查失敗且通話失敗。</span><span class="sxs-lookup"><span data-stu-id="4c412-215">If an IP address is presented in Record-route or Contact, the certificate check fails and the call fails.</span></span>

- <span data-ttu-id="4c412-216">如果 FQDN 與所提交憑證中的通用或主體替代名稱值不相符，則通話會失敗。</span><span class="sxs-lookup"><span data-stu-id="4c412-216">If the FQDN does not match the value of the Common or Subject Alternative Name in the presented certificate, the call fails.</span></span> 

## <a name="inbound-call-sip-dialog-description"></a><span data-ttu-id="4c412-217">輸入通話：SIP 對話方塊描述</span><span class="sxs-lookup"><span data-stu-id="4c412-217">Inbound call: SIP dialog description</span></span>

<span data-ttu-id="4c412-218">下表摘要列出非旁路和旁路模式之間的通話流程差異和相似性：</span><span class="sxs-lookup"><span data-stu-id="4c412-218">The following table below summarizes the call flow differences and similarities between non-bypass and bypass modes:</span></span>

| <span data-ttu-id="4c412-219">參數名稱</span><span class="sxs-lookup"><span data-stu-id="4c412-219">Parameter name</span></span> | <span data-ttu-id="4c412-220">非旁路模式</span><span class="sxs-lookup"><span data-stu-id="4c412-220">Non-bypass mode</span></span> | <span data-ttu-id="4c412-221">旁路模式</span><span class="sxs-lookup"><span data-stu-id="4c412-221">Bypass mode</span></span>
| :---------------------  |:---------------------- |:----------------|
| <span data-ttu-id="4c412-222">來自 183 和 200 個訊息的媒體候選人</span><span class="sxs-lookup"><span data-stu-id="4c412-222">Media candidates in 183 and 200 messages coming from</span></span> | <span data-ttu-id="4c412-223">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="4c412-223">Media processors</span></span> | <span data-ttu-id="4c412-224">用戶端</span><span class="sxs-lookup"><span data-stu-id="4c412-224">Clients</span></span> | 
| <span data-ttu-id="4c412-225">SBC 可接收的 183 個郵件數目</span><span class="sxs-lookup"><span data-stu-id="4c412-225">Number of 183 messages SBC can receive</span></span> | <span data-ttu-id="4c412-226">每個會話一個</span><span class="sxs-lookup"><span data-stu-id="4c412-226">One per session</span></span> | <span data-ttu-id="4c412-227">多個</span><span class="sxs-lookup"><span data-stu-id="4c412-227">Multiple</span></span> | 
| <span data-ttu-id="4c412-228">通話可以在 183 (暫時) </span><span class="sxs-lookup"><span data-stu-id="4c412-228">Call can be with provisional answer (183)</span></span> | <span data-ttu-id="4c412-229">是</span><span class="sxs-lookup"><span data-stu-id="4c412-229">Yes</span></span> | <span data-ttu-id="4c412-230">是</span><span class="sxs-lookup"><span data-stu-id="4c412-230">Yes</span></span> |
| <span data-ttu-id="4c412-231">通話可以在 183 (中) </span><span class="sxs-lookup"><span data-stu-id="4c412-231">Call can be without provisional answer (183)</span></span> | <span data-ttu-id="4c412-232">是</span><span class="sxs-lookup"><span data-stu-id="4c412-232">Yes</span></span> | <span data-ttu-id="4c412-233">是</span><span class="sxs-lookup"><span data-stu-id="4c412-233">Yes</span></span> |

###  <a name="non-media-bypass-flow"></a><span data-ttu-id="4c412-234">非媒體旁路流程</span><span class="sxs-lookup"><span data-stu-id="4c412-234">Non-media bypass flow</span></span>

<span data-ttu-id="4c412-235">Teams 使用者可能同時有多個端點。</span><span class="sxs-lookup"><span data-stu-id="4c412-235">A Teams user might have multiple endpoints at the same time.</span></span> <span data-ttu-id="4c412-236">例如，Windows 版 Teams 用戶端、iPhone 版 Teams 用戶端和 Teams Phone (Teams Android 用戶端) 。</span><span class="sxs-lookup"><span data-stu-id="4c412-236">For example, Teams for Windows client, Teams for iPhone client, and Teams Phone (Teams Android client).</span></span> <span data-ttu-id="4c412-237">每個端點可能會發出 HTTP 的休息訊號，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4c412-237">Each endpoint might signal an HTTP rest as follows:</span></span>

-   <span data-ttu-id="4c412-238">通話進度 - 由 SIP Proxy 轉換成 SIP 訊息 180。</span><span class="sxs-lookup"><span data-stu-id="4c412-238">Call progress – converted by the SIP proxy to the SIP message 180.</span></span> <span data-ttu-id="4c412-239">收到訊息 180 時，SBC 必須產生本地響鈴。</span><span class="sxs-lookup"><span data-stu-id="4c412-239">On receiving message 180, the SBC must generate local ringing.</span></span>

-   <span data-ttu-id="4c412-240">媒體答案 - 由 SIP Proxy 轉換成訊息 183，在會話描述通訊協定或 SDP (中) 。</span><span class="sxs-lookup"><span data-stu-id="4c412-240">Media answer – converted by the SIP proxy to message 183 with media candidates in Session Description Protocol (SDP).</span></span> <span data-ttu-id="4c412-241">在收到郵件 183 時，SBC 預期會連接到 SDP 訊息中收到的媒體候選者。</span><span class="sxs-lookup"><span data-stu-id="4c412-241">On receiving message 183, the SBC expects to connect to the media candidates received in the SDP message.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="4c412-242">在某些情況下，媒體答案可能不會產生，而結尾可能會以「已接受通話」訊息來回答。</span><span class="sxs-lookup"><span data-stu-id="4c412-242">In some cases the Media answer might not be generated, and the end point might answer with “Call Accepted” message.</span></span>

-   <span data-ttu-id="4c412-243">已接受通話 - 由 SIP Proxy 轉換成 SIP 訊息 200 與 SDP。</span><span class="sxs-lookup"><span data-stu-id="4c412-243">Call accepted – converted by the SIP proxy to SIP message 200 with SDP.</span></span> <span data-ttu-id="4c412-244">收到訊息 200 時，SBC 預期會傳送和接收來自提供的 SDP 候選人的媒體。</span><span class="sxs-lookup"><span data-stu-id="4c412-244">On receiving message 200, the SBC is expected to send and receive media to and from the provided SDP candidates.</span></span>

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a><span data-ttu-id="4c412-245">多個端點以暫發性答案響鈴</span><span class="sxs-lookup"><span data-stu-id="4c412-245">Multiple endpoints ringing with provisional answer</span></span>

1.  <span data-ttu-id="4c412-246">從 SBC 接收第一個邀請時，SIP Proxy 會傳送「SIP/2.0 100 嘗試」訊息，並通知所有使用者端點有關來電。</span><span class="sxs-lookup"><span data-stu-id="4c412-246">On receiving the first Invite from the SBC, the SIP proxy sends the message "SIP SIP/2.0 100 Trying" and notifies all end user endpoints about the incoming call.</span></span> 

2.  <span data-ttu-id="4c412-247">通知後，每個端點都會開始響鈴，並傳送「通話進度」訊息至 SIP Proxy。</span><span class="sxs-lookup"><span data-stu-id="4c412-247">Upon notification, each endpoint will start ringing and sending "Call progress” messages to the SIP proxy.</span></span> <span data-ttu-id="4c412-248">因為 Teams 使用者可以有多個終點，SIP Proxy 可能會收到多個通話進度訊息。</span><span class="sxs-lookup"><span data-stu-id="4c412-248">Because a Teams user can have multiple end points, the SIP proxy might receive multiple Call Progress messages.</span></span>

3.  <span data-ttu-id="4c412-249">針對從用戶端收到的每一則通話進度訊息，SIP Proxy 會將通話進度訊息轉換為 SIP 訊息「SIP/2.0 180 嘗試」。</span><span class="sxs-lookup"><span data-stu-id="4c412-249">For every Call Progress message received from the clients, the SIP proxy converts the Call Progress message to the SIP message "SIP SIP/2.0 180 Trying".</span></span> <span data-ttu-id="4c412-250">傳送這類郵件的間隔是由從呼叫控制器接收郵件的間隔所定義。</span><span class="sxs-lookup"><span data-stu-id="4c412-250">The interval for sending such messages is defined by the interval of the receiving messages from the Call Controller.</span></span> <span data-ttu-id="4c412-251">在下列圖表中，SIP Proxy 產生兩個 180 個郵件。</span><span class="sxs-lookup"><span data-stu-id="4c412-251">In the following diagram, there are two 180 messages generated by the SIP proxy.</span></span> <span data-ttu-id="4c412-252">這些訊息來自使用者的兩個 Teams 端點。</span><span class="sxs-lookup"><span data-stu-id="4c412-252">These messages come from the two Teams endpoints of the user.</span></span> <span data-ttu-id="4c412-253">每個用戶端都有唯一的標記識別項。</span><span class="sxs-lookup"><span data-stu-id="4c412-253">The clients each have a unique Tag ID.</span></span>  <span data-ttu-id="4c412-254">每個來自不同端點的郵件都會是一個獨立的會話 (在 "To" 欄位中的參數 "tag" 會) 。</span><span class="sxs-lookup"><span data-stu-id="4c412-254">Every message coming from a different endpoint will be a separate session (the parameter “tag” in the “To” field will be different).</span></span> <span data-ttu-id="4c412-255">但端點可能不會立即產生訊息 180 並傳送訊息 183，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="4c412-255">But an endpoint might not generate message 180 and send message 183 right away as shown in the following diagram.</span></span>

4.  <span data-ttu-id="4c412-256">端點產生包含端點媒體候選者 IP 位址的 Media Answer 訊息後，SIP Proxy 會將收到的訊息轉換成「SIP 183 會話進度」訊息，而用戶端的 SDP 會由媒體處理器的 SDP 取代。</span><span class="sxs-lookup"><span data-stu-id="4c412-256">Once an endpoint generates a Media Answer message with the IP addresses of endpoint’s media candidates, the SIP proxy converts the message received to a "SIP 183 Session Progress" message with the SDP from the client replaced by the SDP from the Media Processor.</span></span> <span data-ttu-id="4c412-257">在下列圖表中，Fork 2 的端點已接電話。</span><span class="sxs-lookup"><span data-stu-id="4c412-257">In the following diagram, the endpoint from Fork 2 answered the call.</span></span> <span data-ttu-id="4c412-258">如果主幹未受到忽略，則只有一次 183 SIP 訊息會 (Ring Bot 或用戶端) 。</span><span class="sxs-lookup"><span data-stu-id="4c412-258">If the trunk is non-bypassed, the 183 SIP message is generated only once (either Ring Bot or Client End Point).</span></span> <span data-ttu-id="4c412-259">183 可能位於現有的分叉上，或開始新的分叉。</span><span class="sxs-lookup"><span data-stu-id="4c412-259">The 183 might come on an existing fork or start a new one.</span></span>

5.  <span data-ttu-id="4c412-260">電話接受訊息會與接受通話之端點的最終候選者一起送出。</span><span class="sxs-lookup"><span data-stu-id="4c412-260">A Call Acceptance message is sent with the final candidates of the endpoint that accepted the call.</span></span> <span data-ttu-id="4c412-261">通話接受訊息會轉換成 SIP 訊息 200。</span><span class="sxs-lookup"><span data-stu-id="4c412-261">The Call Acceptance message is converted to SIP message 200.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4c412-262">![顯示多個端點以暫時答案響鈴的圖表](media/direct-routing-protocols-1.png)</span><span class="sxs-lookup"><span data-stu-id="4c412-262">![Diagram showing multiple endpoints ringing with provisional answer](media/direct-routing-protocols-1.png)</span></span>

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a><span data-ttu-id="4c412-263">多個端點在響鈴時沒有暫時的答案</span><span class="sxs-lookup"><span data-stu-id="4c412-263">Multiple endpoints ringing without provisional answer</span></span>

1.  <span data-ttu-id="4c412-264">從 SBC 接收第一個邀請時，SIP Proxy 會傳送「SIP/2.0 100 嘗試」訊息，並通知所有使用者端點有關來電。</span><span class="sxs-lookup"><span data-stu-id="4c412-264">On receiving the first Invite from the SBC, the SIP proxy sends the message "SIP SIP/2.0 100 Trying" and notifies all end user endpoints about the incoming call.</span></span> 

2.  <span data-ttu-id="4c412-265">通知後，每個端點都會開始響鈴，並傳送「通話進度」訊息至 SIP Proxy。</span><span class="sxs-lookup"><span data-stu-id="4c412-265">Upon notification, each endpoint will start ringing and sending the message "Call progress” to the SIP proxy.</span></span> <span data-ttu-id="4c412-266">因為 Teams 使用者可以有多個終點，SIP Proxy 可能會收到多個通話進度訊息。</span><span class="sxs-lookup"><span data-stu-id="4c412-266">Because a Teams user can have multiple end points, the SIP proxy might receive multiple Call Progress messages.</span></span>

3.  <span data-ttu-id="4c412-267">針對從用戶端收到的每一則通話進度訊息，SIP Proxy 會將通話進度訊息轉換為 SIP 訊息「SIP/2.0 180 嘗試」。</span><span class="sxs-lookup"><span data-stu-id="4c412-267">For every Call Progress message received from the clients, the SIP proxy converts the Call Progress message to the SIP message "SIP SIP/2.0 180 Trying".</span></span>  <span data-ttu-id="4c412-268">傳送郵件的間隔是由從呼叫控制器接收郵件的間隔所定義。</span><span class="sxs-lookup"><span data-stu-id="4c412-268">The interval for sending the messages is defined by the interval of receiving the messages from the Call Controller.</span></span> <span data-ttu-id="4c412-269">下圖顯示 SIP Proxy 產生的兩則 180 則訊息，這表示使用者登入三個 Teams 用戶端，而每個用戶端會傳送通話進度。</span><span class="sxs-lookup"><span data-stu-id="4c412-269">On the picture below there are two 180 messages generated by the SIP proxy, meaning that user logged into three Teams clients and each client send the call progress.</span></span> <span data-ttu-id="4c412-270">每封郵件都會是個別的會話， ("To" 欄位中的參數"標記"與) </span><span class="sxs-lookup"><span data-stu-id="4c412-270">Every message will be a separate session (parameter “tag” in “To” field is different)</span></span>

4.  <span data-ttu-id="4c412-271">電話接受訊息會與接受通話之端點的最終候選者一起送出。</span><span class="sxs-lookup"><span data-stu-id="4c412-271">A Call Acceptance message is sent with the final candidates of the endpoint that accepted the call.</span></span> <span data-ttu-id="4c412-272">通話接受訊息會轉換成 SIP 訊息 200。</span><span class="sxs-lookup"><span data-stu-id="4c412-272">The Call Acceptance message is converted to SIP message 200.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4c412-273">![顯示多個端點響鈴且沒有暫時答案的圖表](media/direct-routing-protocols-2.png)</span><span class="sxs-lookup"><span data-stu-id="4c412-273">![Diagram showing multiple endpoints ringing without provisional answer](media/direct-routing-protocols-2.png)</span></span>

### <a name="media-bypass-flow"></a><span data-ttu-id="4c412-274">媒體旁路流程</span><span class="sxs-lookup"><span data-stu-id="4c412-274">Media bypass flow</span></span>

<span data-ttu-id="4c412-275">在媒體旁 (100 嘗試、180、183) 使用相同的訊息。</span><span class="sxs-lookup"><span data-stu-id="4c412-275">The same messages (100 Trying, 180, 183) are used in the media bypass scenario.</span></span> 

<span data-ttu-id="4c412-276">下列架構顯示旁路通話流程的範例。</span><span class="sxs-lookup"><span data-stu-id="4c412-276">The schema below shows an example of the bypass call flow.</span></span> 

> [!NOTE]
> <span data-ttu-id="4c412-277">媒體候選者可能來自不同的端點。</span><span class="sxs-lookup"><span data-stu-id="4c412-277">The media candidates can come from different endpoints.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4c412-278">![顯示多個端點以暫時答案響鈴的圖表](media/direct-routing-protocols-3.png)</span><span class="sxs-lookup"><span data-stu-id="4c412-278">![Diagram showing multiple endpoints ringing with provisional answer](media/direct-routing-protocols-3.png)</span></span>

## <a name="replaces-option"></a><span data-ttu-id="4c412-279">取代選項</span><span class="sxs-lookup"><span data-stu-id="4c412-279">Replaces option</span></span>

<span data-ttu-id="4c412-280">SBC 必須支援使用取代邀請。</span><span class="sxs-lookup"><span data-stu-id="4c412-280">The SBC must support Invite with Replaces.</span></span>

## <a name="size-of-sdp-considerations"></a><span data-ttu-id="4c412-281">SDP 考慮的大小</span><span class="sxs-lookup"><span data-stu-id="4c412-281">Size of SDP considerations</span></span>

<span data-ttu-id="4c412-282">直接路由介面可能會傳送超過 1，500 位元組的 SIP 訊息。</span><span class="sxs-lookup"><span data-stu-id="4c412-282">The Direct Routing interface might send a SIP message exceeding 1,500 bytes.</span></span>  <span data-ttu-id="4c412-283">SDP 的大小主要會導致此原因。</span><span class="sxs-lookup"><span data-stu-id="4c412-283">The size of SDP primarily causes this.</span></span> <span data-ttu-id="4c412-284">不過，如果 SBC 後面有 UDP 主幹，如果郵件從 Microsoft SIP Proxy 轉往未修改的主幹，它可能會拒絕該郵件。</span><span class="sxs-lookup"><span data-stu-id="4c412-284">However, if there is a UDP trunk behind the SBC, it might reject the message if it is forwarded from the Microsoft SIP proxy to the trunk unmodified.</span></span> <span data-ttu-id="4c412-285">Microsoft 建議在將郵件傳送至 UDP 主幹時，在 SBC 上剪除 SDP 中的某些值。</span><span class="sxs-lookup"><span data-stu-id="4c412-285">Microsoft recommends stripping some values in SDP on the SBC when sending the message to the UDP trunks.</span></span> <span data-ttu-id="4c412-286">例如，可以移除 ICE 候選程式或未使用的編解碼器。</span><span class="sxs-lookup"><span data-stu-id="4c412-286">For example, the ICE candidates or unused codecs can be removed.</span></span>

## <a name="call-transfer"></a><span data-ttu-id="4c412-287">來電轉接</span><span class="sxs-lookup"><span data-stu-id="4c412-287">Call transfer</span></span>

<span data-ttu-id="4c412-288">直接路由支援兩種來電轉接方法：</span><span class="sxs-lookup"><span data-stu-id="4c412-288">Direct Routing supports two methods for call transfer:</span></span>

- <span data-ttu-id="4c412-289">選項 1.</span><span class="sxs-lookup"><span data-stu-id="4c412-289">Option 1.</span></span> <span data-ttu-id="4c412-290">SIP Proxy 程式 從用戶端本地參照，並擔任 RFC 3892 第 7.1 節所述的仲裁人。</span><span class="sxs-lookup"><span data-stu-id="4c412-290">SIP proxy processes Refer from the client locally and acts as a Referee as described in section 7.1 of RFC 3892.</span></span>

  <span data-ttu-id="4c412-291">使用此選項，SIP Proxy 會終止傳輸並新增邀請。</span><span class="sxs-lookup"><span data-stu-id="4c412-291">With this option, the SIP proxy terminates the transfer and adds a new Invite.</span></span> 


- <span data-ttu-id="4c412-292">選項 2.</span><span class="sxs-lookup"><span data-stu-id="4c412-292">Option 2.</span></span> <span data-ttu-id="4c412-293">SIP Proxy 會傳送參照 SBC，並做為 RFC 5589 第 6 節所述之傳輸者。</span><span class="sxs-lookup"><span data-stu-id="4c412-293">SIP proxy sends the Refer to the SBC and acts as a Transferor as describing in Section 6 of RFC 5589.</span></span>

  <span data-ttu-id="4c412-294">使用此選項時，SIP Proxy 會傳送一個參照到 SBC，並預期 SBC 會完全處理傳輸。</span><span class="sxs-lookup"><span data-stu-id="4c412-294">With this option, the SIP proxy sends a Refer to the SBC and expects the SBC to handle the Transfer fully.</span></span>

<span data-ttu-id="4c412-295">SIP Proxy 會根據 SBC 報告的功能來選取方法。</span><span class="sxs-lookup"><span data-stu-id="4c412-295">The SIP proxy selects the method based on the capabilities reported by the SBC.</span></span> <span data-ttu-id="4c412-296">如果 SBC 指出它支援「參照」方法，SIP Proxy 會針對來電轉接使用選項 2。</span><span class="sxs-lookup"><span data-stu-id="4c412-296">If the SBC indicates that it supports the method “Refer”, the SIP proxy will use Option 2 for call transfers.</span></span>

<span data-ttu-id="4c412-297">以下是 SBC 傳送支援引用方法之訊息的範例：</span><span class="sxs-lookup"><span data-stu-id="4c412-297">The following is an example of an SBC sending the message that the Refer method is supported:</span></span>

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

<span data-ttu-id="4c412-298">如果 SBC 未指出引用為支援的方法，則直接路由會使用選項 1 (SIP Proxy 會做為仲裁) 。</span><span class="sxs-lookup"><span data-stu-id="4c412-298">If the SBC doesn’t indicate that Refer as a supported method, Direct Routing will use Option 1 (SIP proxy acts as a Referee) .</span></span> <span data-ttu-id="4c412-299">SBC 也必須發出支援 Notify 方法的訊號：</span><span class="sxs-lookup"><span data-stu-id="4c412-299">The SBC  must also signal that it supports the Notify method:</span></span>

<span data-ttu-id="4c412-300">表示不支援引用方法的 SBC 範例：</span><span class="sxs-lookup"><span data-stu-id="4c412-300">Example of SBC indicating that Refer method is not supported:</span></span>

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a><span data-ttu-id="4c412-301">SIP Proxy 程式 從用戶端本地引用，並擔任仲裁者</span><span class="sxs-lookup"><span data-stu-id="4c412-301">SIP proxy processes Refer from the client locally and acts as a Referee</span></span>

<span data-ttu-id="4c412-302">如果 SBC 指出不支援引用方法，SIP Proxy 會做為仲裁者。</span><span class="sxs-lookup"><span data-stu-id="4c412-302">If the SBC indicated that the Refer method is not supported, the SIP proxy acts as a Referee.</span></span> 

<span data-ttu-id="4c412-303">來自用戶端的參考要求將在 SIP Proxy 上終止。</span><span class="sxs-lookup"><span data-stu-id="4c412-303">The Refer request that comes from the client will be terminated on the SIP proxy.</span></span> <span data-ttu-id="4c412-304"> (下圖中，用戶端的 「轉接至 Dave」要求會顯示為「來電轉接至 Dave」。</span><span class="sxs-lookup"><span data-stu-id="4c412-304">(The Refer request from the client is shown as “Call transfer to Dave” in the following diagram.</span></span>  <span data-ttu-id="4c412-305">詳細資訊，請參閱 [RFC 3892 的第 7.1 節](https://www.ietf.org/rfc/rfc3892.txt)。</span><span class="sxs-lookup"><span data-stu-id="4c412-305">For more information, see section 7.1 of [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt).</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4c412-306">![顯示多個端點以暫時答案響鈴的圖表](media/direct-routing-protocols-4.png)</span><span class="sxs-lookup"><span data-stu-id="4c412-306">![Diagram showing multiple endpoints ringing with provisional answer](media/direct-routing-protocols-4.png)</span></span>

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a><span data-ttu-id="4c412-307">SIP Proxy 會傳送參照到 SBC，並做為傳輸者</span><span class="sxs-lookup"><span data-stu-id="4c412-307">SIP proxy send the Refer to the SBC and acts as a Transferor</span></span>

<span data-ttu-id="4c412-308">這是來電轉接的首選方法，對於尋求媒體旁路認證的裝置，這是必填項。</span><span class="sxs-lookup"><span data-stu-id="4c412-308">This is the preferred method for call transfers, and it is mandatory for devices seeking media bypass certification.</span></span> <span data-ttu-id="4c412-309">媒體旁路模式中不支援 SBC 無法處理引用的來電轉接。</span><span class="sxs-lookup"><span data-stu-id="4c412-309">Call Transfer without the SBC being able to handle Refer is not supported in media bypass mode.</span></span> 

<span data-ttu-id="4c412-310">RFC 5589 的第 6 節說明標準。</span><span class="sxs-lookup"><span data-stu-id="4c412-310">The standard is explained in Section 6 of RFC 5589.</span></span> <span data-ttu-id="4c412-311">相關的 RFC 為：</span><span class="sxs-lookup"><span data-stu-id="4c412-311">The related RFCs are:</span></span>

- [<span data-ttu-id="4c412-312">SIP 的會話初始 (呼叫) - 傳輸</span><span class="sxs-lookup"><span data-stu-id="4c412-312">Session Initiation Protocol (SIP) Call Control - Transfer</span></span>](https://tools.ietf.org/html/rfc5589)

- [<span data-ttu-id="4c412-313">SIP 中的會話初始 (「) 取代」標頭</span><span class="sxs-lookup"><span data-stu-id="4c412-313">Session Initiation Protocol (SIP) "Replaces" Header</span></span>](https://tools.ietf.org/html/rfc3891)

- [<span data-ttu-id="4c412-314">SIP 的會話初始 (「) 」機制</span><span class="sxs-lookup"><span data-stu-id="4c412-314">Session Initiation Protocol (SIP) "Referred-By" mechanism</span></span>](https://tools.ietf.org/html/rfc3892)

<span data-ttu-id="4c412-315">此選項會假設 SIP Proxy 會做為傳輸者，並將參考訊息傳送給 SBC。</span><span class="sxs-lookup"><span data-stu-id="4c412-315">This option assumes that the SIP proxy acts as a Transferor and sends a Refer message to the SBC.</span></span> <span data-ttu-id="4c412-316">SBC 會做為受讓人，並處理參照以產生新的移轉優惠。</span><span class="sxs-lookup"><span data-stu-id="4c412-316">The SBC acts as a Transferee and handles the Refer to generate a new offer for transfer.</span></span> <span data-ttu-id="4c412-317">有兩種可能的情況：</span><span class="sxs-lookup"><span data-stu-id="4c412-317">There are two possible cases:</span></span>

- <span data-ttu-id="4c412-318">通話會轉接給外部 PSTN 參與者。</span><span class="sxs-lookup"><span data-stu-id="4c412-318">The call is transferred to an external PSTN participant.</span></span> 
- <span data-ttu-id="4c412-319">通話會透過 SBC 從一個 Teams 使用者轉接至同一租使用者中的另一個 Teams 使用者。</span><span class="sxs-lookup"><span data-stu-id="4c412-319">The call is transferred from one Teams user to another Teams user in the same tenant via the SBC.</span></span> 

<span data-ttu-id="4c412-320">如果通話是透過 SBC 從一個 Teams 使用者轉接到另一個，SBC 會使用 [參考訊息中收到的資訊 (啟動移轉目標) 的新對話方塊 (Teams 使用者) 。</span><span class="sxs-lookup"><span data-stu-id="4c412-320">If the call is transferred from one Teams user to another via the SBC, the SBC is expected to issue a new invite (start a new dialog) for the transfer target (the Teams user) using the information received in the Refer message.</span></span> 

<span data-ttu-id="4c412-321">若要在內部填入要求交易之 To/Transferor 欄位，SIP Proxy 需要在 REFER-TO/REFERRED-BY 標頭內傳達此資訊。</span><span class="sxs-lookup"><span data-stu-id="4c412-321">To populate the To/Transferor fields for the transaction of the request internally, the SIP proxy needs to convey this information  inside the REFER-TO/REFERRED-BY headers.</span></span> 

<span data-ttu-id="4c412-322">SIP Proxy 會以 SIP URI 的形式形成 REFER-TO，包含主機名稱中的 SIP Proxy FQDN，以及下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="4c412-322">The SIP proxy will form the REFER-TO as a SIP URI comprised of a SIP proxy FQDN in the hostname and either one of the following:</span></span>

- <span data-ttu-id="4c412-323">如果傳輸目標為電話號碼，則 URI 使用者名稱部分中的 E.164 電話號碼，或</span><span class="sxs-lookup"><span data-stu-id="4c412-323">An E.164 phone number in the username part of the URI in case the transfer target is a phone number, or</span></span>

- <span data-ttu-id="4c412-324">分別編碼完整傳輸目標 MRI 和租使用者識別碼的 x-m 和 x-t 參數</span><span class="sxs-lookup"><span data-stu-id="4c412-324">x-m and x-t parameters encoding the full transfer target MRI and tenant ID respectively</span></span> 

<span data-ttu-id="4c412-325">REFERRED-BY 標頭是 SIP URI，其內編碼為傳輸器或 MRI，以及傳輸器租使用者識別碼和其他傳輸上下文參數，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="4c412-325">The REFERRED-BY header is a SIP URI with transferor MRI encoded in it as well as transferor tenant ID and other transfer context parameters as shown in the following table:</span></span>

| <span data-ttu-id="4c412-326">參數</span><span class="sxs-lookup"><span data-stu-id="4c412-326">Parameter</span></span> | <span data-ttu-id="4c412-327">值</span><span class="sxs-lookup"><span data-stu-id="4c412-327">Value</span></span> | <span data-ttu-id="4c412-328">說明</span><span class="sxs-lookup"><span data-stu-id="4c412-328">Description</span></span> |  
|:---------------------  |:---------------------- |:---------------------- |
| <span data-ttu-id="4c412-329">x-m</span><span class="sxs-lookup"><span data-stu-id="4c412-329">x-m</span></span> | <span data-ttu-id="4c412-330">Mri</span><span class="sxs-lookup"><span data-stu-id="4c412-330">MRI</span></span> | <span data-ttu-id="4c412-331">由 CC 填上之傳輸器/傳輸目標的完整 MRI</span><span class="sxs-lookup"><span data-stu-id="4c412-331">Full MRI of transferor/transfer target as populated by CC</span></span> |
| <span data-ttu-id="4c412-332">x-t</span><span class="sxs-lookup"><span data-stu-id="4c412-332">x-t</span></span> | <span data-ttu-id="4c412-333">租用戶識別碼</span><span class="sxs-lookup"><span data-stu-id="4c412-333">Tenant ID</span></span> | <span data-ttu-id="4c412-334">X-t 租使用者識別碼 選擇性租使用者識別碼，以 CC 填上</span><span class="sxs-lookup"><span data-stu-id="4c412-334">x-t Tenant ID Optional Tenant ID as populated by CC</span></span> |
| <span data-ttu-id="4c412-335">x-ti</span><span class="sxs-lookup"><span data-stu-id="4c412-335">x-ti</span></span> | <span data-ttu-id="4c412-336">傳輸器關聯識別碼</span><span class="sxs-lookup"><span data-stu-id="4c412-336">Transferor Correlation Id</span></span> | <span data-ttu-id="4c412-337">來電轉接者的相關識別碼</span><span class="sxs-lookup"><span data-stu-id="4c412-337">Correlation ID of the call to the transferor</span></span> |
| <span data-ttu-id="4c412-338">x-tt</span><span class="sxs-lookup"><span data-stu-id="4c412-338">x-tt</span></span> | <span data-ttu-id="4c412-339">傳輸目標通話 URI</span><span class="sxs-lookup"><span data-stu-id="4c412-339">Transfer target call URI</span></span> | <span data-ttu-id="4c412-340">編碼呼叫取代 URI</span><span class="sxs-lookup"><span data-stu-id="4c412-340">Encoded call replacement URI</span></span> |

<span data-ttu-id="4c412-341">在這種情況下，參考頁眉的大小最多隻能是 400 個符號。</span><span class="sxs-lookup"><span data-stu-id="4c412-341">The size of the Refer Header can be up to 400 symbols in this case.</span></span> <span data-ttu-id="4c412-342">SBC 必須支援處理大小最多 400 個符號的參考郵件。</span><span class="sxs-lookup"><span data-stu-id="4c412-342">The SBC must support handling Refer messages with size up to 400 symbols.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4c412-343">![顯示多個端點以暫時答案響鈴的圖表](media/direct-routing-protocols-5.png)</span><span class="sxs-lookup"><span data-stu-id="4c412-343">![Diagram showing multiple endpoints ringing with provisional answer](media/direct-routing-protocols-5.png)</span></span>

## <a name="session-timer"></a><span data-ttu-id="4c412-344">會話計時器</span><span class="sxs-lookup"><span data-stu-id="4c412-344">Session timer</span></span>

<span data-ttu-id="4c412-345">SIP Proxy 支援 (，) 非旁路通話時提供會話計時器，但不在旁路通話時提供。</span><span class="sxs-lookup"><span data-stu-id="4c412-345">The SIP proxy supports (always offers) the Session Timer on non-bypass calls but does not offer it on bypass calls.</span></span> <span data-ttu-id="4c412-346">SBC 不會強制使用會話計時器。</span><span class="sxs-lookup"><span data-stu-id="4c412-346">Use of the Session Timer by the SBC is not mandatory.</span></span>

##  <a name="use-of-request-uri-parameter-userphone"></a><span data-ttu-id="4c412-347">Request-URI 參數 user=phone 的使用</span><span class="sxs-lookup"><span data-stu-id="4c412-347">Use of Request-URI parameter user=phone</span></span>

<span data-ttu-id="4c412-348">SIP Proxy 會分析 Request-URI，如果使用者=phone 有參數存在，服務會以電話號碼處理 Request-URI，將號碼與使用者配對。</span><span class="sxs-lookup"><span data-stu-id="4c412-348">The SIP proxy analyses the Request-URI and if the parameter user=phone is present, the service will handle the Request-URI as a phone number, matching the number to a user.</span></span> <span data-ttu-id="4c412-349">如果參數不存在，SIP Proxy 會採用啟發式來判斷 Request-URI 使用者類型 (電話號碼或 SIP 位址) 。</span><span class="sxs-lookup"><span data-stu-id="4c412-349">If parameter is not present the SIP proxy applies heuristics to determine  the Request-URI user type (phone number or a SIP address).</span></span>

<span data-ttu-id="4c412-350">Microsoft 建議一直使用 user=phone 參數，以簡化通話設定程式。</span><span class="sxs-lookup"><span data-stu-id="4c412-350">Microsoft recommends always applying the user=phone parameter to simplify the call setup process.</span></span>

## <a name="history-info-header"></a><span data-ttu-id="4c412-351">History-Info頁標題</span><span class="sxs-lookup"><span data-stu-id="4c412-351">History-Info header</span></span>

<span data-ttu-id="4c412-352">History-Info頁標題用於重新置放 SIP 要求，並「提供 (s) 一種標準機制，以捕獲要求歷程記錄資訊，為網路和使用者啟用各式各樣的服務」。</span><span class="sxs-lookup"><span data-stu-id="4c412-352">The History-Info header is used for retargeting SIP requests and “provide(s) a standard mechanism for capturing the request history information to enable a wide variety of services for networks and end-users.”</span></span> <span data-ttu-id="4c412-353">詳細資訊，請參閱 [RFC 4244 – 第 1.1 節](http://www.ietf.org/rfc/rfc4244.txt)。</span><span class="sxs-lookup"><span data-stu-id="4c412-353">For more information, see [RFC 4244 – Section 1.1](http://www.ietf.org/rfc/rfc4244.txt).</span></span> <span data-ttu-id="4c412-354">針對 Microsoft Phone System，此標頭用於 Simulring 和呼叫轉轉案例。</span><span class="sxs-lookup"><span data-stu-id="4c412-354">For Microsoft Phone System, this header is used in Simulring and Call Forwarding scenarios.</span></span>  

<span data-ttu-id="4c412-355">如果傳送，History-Info啟用方式如下：</span><span class="sxs-lookup"><span data-stu-id="4c412-355">If sending, the History-Info is enabled as follows:</span></span>

- <span data-ttu-id="4c412-356">SIP Proxy 會個別插入包含關聯電話號碼的參數History-Info組成要History-Info PSTN 控制器的標頭。</span><span class="sxs-lookup"><span data-stu-id="4c412-356">The SIP proxy will insert a parameter containing the associated phone number in individual History-Info entries that comprise the History-Info header sent to the PSTN Controller.</span></span>  <span data-ttu-id="4c412-357">PSTN 控制器只會使用具有電話號碼參數History-Info，然後透過 SIP Proxy 將它傳遞到 SIP 主幹提供者。</span><span class="sxs-lookup"><span data-stu-id="4c412-357">Using only entries that have the phone number parameter, the PSTN Controller will rebuild a new History-Info header, and pass it on to the SIP trunk provider via SIP proxy.</span></span>

- <span data-ttu-id="4c412-358">History-Info同時撥打和呼叫轉譯的情況下，會新增一個標題。</span><span class="sxs-lookup"><span data-stu-id="4c412-358">History-Info header will be added for simultaneous ring and call forwarding cases.</span></span>

- <span data-ttu-id="4c412-359">History-Info通話轉接案例不會新增標題。</span><span class="sxs-lookup"><span data-stu-id="4c412-359">History-Info header will not be added for call transfer cases.</span></span>

- <span data-ttu-id="4c412-360">重新建立之 History-Info 標題中的個別歷程記錄專案會提供電話號碼參數，並結合直接路由 FQDN (sip.pstnhub.microsoft.com) 設為 URI 的主機部分;'user=phone' 的參數會新增為 SIP URI 的一部分。</span><span class="sxs-lookup"><span data-stu-id="4c412-360">An individual history entry in the reconstructed History-Info header will have the phone number parameter provided combined with the Direct Routing FQDN (sip.pstnhub.microsoft.com) set as the host part of the URI; a parameter of ‘user=phone’ will be added as part of the SIP URI.</span></span>  <span data-ttu-id="4c412-361">與原始頁History-Info關聯的任何其他參數，除了電話上下文參數之外，都會在重新建構的 History-Info標頭中傳遞。</span><span class="sxs-lookup"><span data-stu-id="4c412-361">Any other parameters associated with the original History-Info header, except for phone context parameters, will be passed through in the re-constructed History-Info header.</span></span>  

  > [!NOTE]
  > <span data-ttu-id="4c412-362">根據 RFC 4244) 第 3.3 節所定義的機制所決定，私人專案將會轉) 因為 SIP 主幹提供者是信任的對等體。 (</span><span class="sxs-lookup"><span data-stu-id="4c412-362">Entries that are private (as determined by the mechanisms defined in Section 3.3 of RFC 4244) will be forwarded as is because  the SIP trunk provider is a trusted peer.</span></span>

- <span data-ttu-id="4c412-363">內History-Info會被忽略。</span><span class="sxs-lookup"><span data-stu-id="4c412-363">Inbound History-Info is ignored.</span></span>

<span data-ttu-id="4c412-364">以下是 SIP Proxy 所送出之歷程記錄資訊標題的格式：</span><span class="sxs-lookup"><span data-stu-id="4c412-364">Following is the format of the History-info header sent by the SIP proxy:</span></span>

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

<span data-ttu-id="4c412-365">如果呼叫已重新導向數次，每個重新導向的資訊會以時間順序包含適當的原因。</span><span class="sxs-lookup"><span data-stu-id="4c412-365">If the call was redirected several times, information about every redirect is included with the appropriate reason in chronological order.</span></span>


<span data-ttu-id="4c412-366">標題範例：</span><span class="sxs-lookup"><span data-stu-id="4c412-366">Header Example:</span></span>

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

<span data-ttu-id="4c412-367">系統History-Info受強制 TLS 機制保護。</span><span class="sxs-lookup"><span data-stu-id="4c412-367">The History-Info is protected by a mandatory TLS mechanism.</span></span> 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a><span data-ttu-id="4c412-368">直接路由和容錯移轉機制的 SBC 連接</span><span class="sxs-lookup"><span data-stu-id="4c412-368">SBC connection to Direct Routing and failover mechanism</span></span>

<span data-ttu-id="4c412-369">請參閱直接路由規劃中的 SIP 信令容錯移轉 [機制一節](direct-routing-plan.md#failover-mechanism-for-sip-signaling)。</span><span class="sxs-lookup"><span data-stu-id="4c412-369">See the section Failover mechanism for SIP signaling in [Plan for Direct Routing](direct-routing-plan.md#failover-mechanism-for-sip-signaling).</span></span>

## <a name="retry-after"></a><span data-ttu-id="4c412-370">Retry-After</span><span class="sxs-lookup"><span data-stu-id="4c412-370">Retry-After</span></span>

<span data-ttu-id="4c412-371">如果直接路由資料中心忙碌，服務可以傳送一Retry-After一秒間隔的訊息給 SBC。</span><span class="sxs-lookup"><span data-stu-id="4c412-371">If a Direct Routing datacenter is busy, the service can send a Retry-After message with a one-second interval to the SBC.</span></span> <span data-ttu-id="4c412-372">當 SBC 收到包含 Retry-After 標頭的 503 郵件以回應 INVITE 時，SBC 必須終止該連接，並嘗試下一個可用的 Microsoft 資料中心。</span><span class="sxs-lookup"><span data-stu-id="4c412-372">When the SBC receives a 503 message with a Retry-After header in response to an INVITE, the SBC must terminate that connection and try the next available Microsoft datacenter.</span></span> 

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a><span data-ttu-id="4c412-373">ICE 重新開機：轉接到不支援媒體旁路的端點的媒體旁路通話</span><span class="sxs-lookup"><span data-stu-id="4c412-373">ICE Restart: Media bypass call transferred to an endpoint that does not support media bypass</span></span>

<span data-ttu-id="4c412-374">SBC 必須支援 [RFC 5245 第 9.1.1.1 節](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)中所述的 ICE 重新開機。</span><span class="sxs-lookup"><span data-stu-id="4c412-374">The SBC must support ICE restarts as described in [RFC 5245, section 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span>

<span data-ttu-id="4c412-375">直接路由中的重新開機會根據 RFC 的下列段落進行：</span><span class="sxs-lookup"><span data-stu-id="4c412-375">The restart in Direct Routing is implemented according to the following paragraphs of the RFC:</span></span>

<span data-ttu-id="4c412-376">*若要重新開機 ICE，代理人必須同時變更優惠中媒體流的冰-pwd 和 ice-ufrag。 請注意，在一個優惠中允許使用工作階段層級屬性，但提供與後續優惠中媒體層級屬性相同的 ice-pwd 或 ice-ufrag。 這不是密碼的變更，只是其表示方式的變更，而且不會造成 ICE 重新開機。*</span><span class="sxs-lookup"><span data-stu-id="4c412-376">*To restart ICE, an agent MUST change both the ice-pwd and the ice-ufrag for the media stream in an offer.  Note that it is permissible to use a session-level attribute in one offer, but to provide the same ice-pwd or ice-ufrag as a media-level attribute in a subsequent offer.  This is not a change in password, just a change in its representation, and does not cause an ICE restart.*</span></span>

<span data-ttu-id="4c412-377">*代理程式會設定此媒體流 SDP 中其餘的欄位，就像初次提供此媒體流時一樣 (請參閱第 4.3 節) 。 因此，一組候選者可能包含該串流的部分、無或所有先前的候選者，而 MAY 則包含第 4.1.1 節所述收集的一組全新的候選者。*</span><span class="sxs-lookup"><span data-stu-id="4c412-377">*An agent sets the rest of the fields in the SDP for this media stream as it would in an initial offer of this media stream (see Section 4.3).  Consequently, the set of candidates MAY include some, none, or all of the previous candidates for that stream and MAY include a totally new set of candidates gathered as described in Section 4.1.1.*</span></span>

<span data-ttu-id="4c412-378">如果通話最初是使用媒體旁路建立，而通話已轉接至商務用 Skype 用戶端，則直接路由需要插入媒體處理器，這是因為直接路由無法與具有媒體旁路的商務用 Skype 用戶端一起使用。</span><span class="sxs-lookup"><span data-stu-id="4c412-378">If the call was initially established with media bypass, and the call is transferred to a Skype for Business client, Direct Routing needs to insert a Media Processor--this is because Direct Routing cannot be used with a Skype for Business client with media bypass.</span></span> <span data-ttu-id="4c412-379">直接路由會變更 ice-pwd 和 ice-ufrag，並再次提供新的媒體候選項目，以啟動 ICE 重新開機程式。</span><span class="sxs-lookup"><span data-stu-id="4c412-379">Direct Routing starts the ICE restart process by  changing the ice-pwd and ice-ufrag and offering new media candidates in a reinvite.</span></span> 


