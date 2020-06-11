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
description: 直接路由式通訊協定
appliesto:
- Microsoft Teams
ms.openlocfilehash: 264e7e3de8031e8ac150c186078ff3d7ccff2f16
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691219"
---
# <a name="direct-routing---sip-protocol"></a><span data-ttu-id="fe429-103">直接路由 SIP 通訊協定</span><span class="sxs-lookup"><span data-stu-id="fe429-103">Direct Routing - SIP protocol</span></span>

<span data-ttu-id="fe429-104">本文說明直接路由如何實現會話初始通訊協定（SIP）。</span><span class="sxs-lookup"><span data-stu-id="fe429-104">This article describes how Direct Routing implements the Session Initiation Protocol (SIP).</span></span> <span data-ttu-id="fe429-105">若要在會話邊界控制器（SBC）與 SIP proxy 之間正確路由流量，某些 SIP 參數必須有特定的值。</span><span class="sxs-lookup"><span data-stu-id="fe429-105">To properly route traffic between a Session Border Controller (SBC) and the SIP proxy, some SIP parameters must have specific values.</span></span> <span data-ttu-id="fe429-106">本文適用于負責設定內部部署 SBC 與 SIP proxy 服務之間的連線的語音系統管理員。</span><span class="sxs-lookup"><span data-stu-id="fe429-106">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a><span data-ttu-id="fe429-107">處理傳入要求：尋找租使用者和使用者</span><span class="sxs-lookup"><span data-stu-id="fe429-107">Processing the incoming request: finding the tenant and user</span></span>

<span data-ttu-id="fe429-108">在撥入通話中，SIP proxy 需要尋找通話是目的地的租使用者，並在這個租使用者中找到特定使用者。</span><span class="sxs-lookup"><span data-stu-id="fe429-108">On an incoming call, the SIP proxy needs to find the tenant to which the call is destined and find the specific user within this tenant.</span></span> <span data-ttu-id="fe429-109">租使用者管理員可能會在多個租使用者中設定非已執行的號碼（例如 + 1001）。</span><span class="sxs-lookup"><span data-stu-id="fe429-109">The tenant administrator might configure non-DID numbers, for example +1001, in multiple tenants.</span></span> <span data-ttu-id="fe429-110">因此，請務必找出要在其上執行數位查閱的特定租使用者，因為在多個 Microsoft 365 或 Office 365 組織中，非使用中的號碼可能是相同的。</span><span class="sxs-lookup"><span data-stu-id="fe429-110">Therefore, it is important to find the specific tenant on which to perform the number lookup because the non-DID numbers might be the same in multiple Microsoft 365 or Office 365 organizations.</span></span>  

<span data-ttu-id="fe429-111">本節將說明 SIP proxy 如何找到租使用者與使用者，以及如何在傳入連線上執行 SBC 驗證。</span><span class="sxs-lookup"><span data-stu-id="fe429-111">This section describes how the SIP proxy finds the tenant and the user, and performs authentication of the SBC on the incoming connection.</span></span>

<span data-ttu-id="fe429-112">下列是撥入電話的 SIP 邀請訊息範例：</span><span class="sxs-lookup"><span data-stu-id="fe429-112">The following is an example of the SIP Invite message on an incoming call:</span></span>

| <span data-ttu-id="fe429-113">參數名稱</span><span class="sxs-lookup"><span data-stu-id="fe429-113">Parameter name</span></span> | <span data-ttu-id="fe429-114">值的範例</span><span class="sxs-lookup"><span data-stu-id="fe429-114">Example of the value</span></span> | 
| :---------------------  |:---------------------- |
| <span data-ttu-id="fe429-115">要求 URI</span><span class="sxs-lookup"><span data-stu-id="fe429-115">Request-URI</span></span> | <span data-ttu-id="fe429-116">邀請 sip:+18338006777@sip.pstnhub.microsoft.com SIP/2。0</span><span class="sxs-lookup"><span data-stu-id="fe429-116">INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0</span></span> |
| <span data-ttu-id="fe429-117">Via 頁首</span><span class="sxs-lookup"><span data-stu-id="fe429-117">Via Header</span></span> | <span data-ttu-id="fe429-118">Via： SIP/2.0/TLS sbc1 biz： 5058; 別名; 分支 = z9hG4bKac2121518978</span><span class="sxs-lookup"><span data-stu-id="fe429-118">Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978</span></span> | 
| <span data-ttu-id="fe429-119">Max-轉寄頁首</span><span class="sxs-lookup"><span data-stu-id="fe429-119">Max-Forwards header</span></span> | <span data-ttu-id="fe429-120">最大轉寄：68</span><span class="sxs-lookup"><span data-stu-id="fe429-120">Max-Forwards:68</span></span> |
| <span data-ttu-id="fe429-121">從頁首</span><span class="sxs-lookup"><span data-stu-id="fe429-121">From Header</span></span> | <span data-ttu-id="fe429-122">從頁首開始： <sip： 7168712781@sbc1. biz; 傳輸 = udp; tag = 1c747237679</span><span class="sxs-lookup"><span data-stu-id="fe429-122">From Header From: <sip:7168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679</span></span> |
| <span data-ttu-id="fe429-123">移至頁首</span><span class="sxs-lookup"><span data-stu-id="fe429-123">To Header</span></span> | <span data-ttu-id="fe429-124">至： sip:+183338006777@sbc1.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="fe429-124">To: sip:+183338006777@sbc1.adatum.biz</span></span> | 
| <span data-ttu-id="fe429-125">CSeq 頁首</span><span class="sxs-lookup"><span data-stu-id="fe429-125">CSeq header</span></span> | <span data-ttu-id="fe429-126">CSeq：1個邀請</span><span class="sxs-lookup"><span data-stu-id="fe429-126">CSeq: 1 INVITE</span></span> | 
| <span data-ttu-id="fe429-127">連絡人標題</span><span class="sxs-lookup"><span data-stu-id="fe429-127">Contact Header</span></span> | <span data-ttu-id="fe429-128">連絡人： <sip： 68712781@sbc1 biz; transport = tls></span><span class="sxs-lookup"><span data-stu-id="fe429-128">Contact: <sip: 68712781@sbc1.adatum.biz;transport=tls></span></span> | 

<span data-ttu-id="fe429-129">在收到邀請時，SIP proxy 會執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="fe429-129">On receiving the invite, the SIP proxy performs the following steps:</span></span>

1. <span data-ttu-id="fe429-130">檢查憑證。</span><span class="sxs-lookup"><span data-stu-id="fe429-130">Check the certificate.</span></span> <span data-ttu-id="fe429-131">在初始連線中，直連路由服務會取得連絡人標頭中所提供的 FQDN 名稱，並將其與所提供憑證的通用名稱或消費者替換名稱相符。</span><span class="sxs-lookup"><span data-stu-id="fe429-131">On the initial connection, the Direct Routing service takes the FQDN name presented in the Contact header and matches it to the Common Name or Subject Alternative name of the presented certificate.</span></span> <span data-ttu-id="fe429-132">SBC 名稱必須符合下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="fe429-132">The SBC name must match one of the following options:</span></span>

   - <span data-ttu-id="fe429-133">選項1。</span><span class="sxs-lookup"><span data-stu-id="fe429-133">Option 1.</span></span> <span data-ttu-id="fe429-134">在連絡人標題中提供的完整 FQDN 名稱，必須符合所提供憑證的通用名稱/消費者替換名稱。</span><span class="sxs-lookup"><span data-stu-id="fe429-134">The full FQDN name presented in the Contact header must match the Common Name/Subject Alternative name of the presented certificate.</span></span>  

   - <span data-ttu-id="fe429-135">選項2。</span><span class="sxs-lookup"><span data-stu-id="fe429-135">Option 2.</span></span> <span data-ttu-id="fe429-136">在連絡人標題中顯示的 FQDN 名稱網域部分（例如，FQDN 名稱 sbc1.adatum.biz 的 adatum.biz），必須符合常見名稱/消費者替換名稱（例如 \*. adatum.biz）中的萬用字元值。</span><span class="sxs-lookup"><span data-stu-id="fe429-136">The domain portion of the FQDN name presented in the Contact header (for example adatum.biz of the FQDN name sbc1.adatum.biz) must match the wildcard value in Common Name/Subject Alternative Name (for example \*.adatum.biz).</span></span>

2. <span data-ttu-id="fe429-137">嘗試使用在連絡人標題中提供的完整 FQDN 名稱尋找租使用者。</span><span class="sxs-lookup"><span data-stu-id="fe429-137">Try to find a tenant using the full FQDN name presented in the Contact header.</span></span>  

   <span data-ttu-id="fe429-138">檢查連絡人標題（sbc1.adatum.biz）的 FQDN 名稱是否已在任何 Microsoft 365 或 Office 365 組織中註冊為 DNS 名稱。</span><span class="sxs-lookup"><span data-stu-id="fe429-138">Check if the FQDN name from the Contact header (sbc1.adatum.biz) is registered as a DNS name in any Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="fe429-139">如果找到，則會在已將 SBC FQDN 註冊為功能變數名稱的租使用者中執行使用者查閱。</span><span class="sxs-lookup"><span data-stu-id="fe429-139">If found, the lookup of the user is performed in the tenant that has the SBC FQDN registered as a Domain name.</span></span> <span data-ttu-id="fe429-140">如果找不到，則會套用步驟3。</span><span class="sxs-lookup"><span data-stu-id="fe429-140">If not found, Step 3 applies.</span></span>   

3. <span data-ttu-id="fe429-141">步驟3只有在步驟2失敗時才適用。</span><span class="sxs-lookup"><span data-stu-id="fe429-141">Step 3 only applies if Step 2 failed.</span></span> 

   <span data-ttu-id="fe429-142">從 FQDN 中移除主機部分（FQDN： sbc12.adatum.biz，在移除主機部分： adatum.biz）後，檢查該名稱是否已在任何 Microsoft 365 或 Office 365 組織中註冊為 DNS 名稱。</span><span class="sxs-lookup"><span data-stu-id="fe429-142">Remove the host portion from the FQDN, presented in the Contact header (FQDN: sbc12.adatum.biz, after removing the host portion: adatum.biz), and check if this name is registered as a DNS name in any Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="fe429-143">如果找到，則會在此租使用者中執行使用者查閱。</span><span class="sxs-lookup"><span data-stu-id="fe429-143">If found, the user lookup is performed in this tenant.</span></span> <span data-ttu-id="fe429-144">如果找不到，通話就會失敗。</span><span class="sxs-lookup"><span data-stu-id="fe429-144">If not found, the call fails.</span></span>

4. <span data-ttu-id="fe429-145">使用在 Request URI 中所提供的電話號碼，在步驟2或3中發現的租使用者中執行反向號碼查閱。</span><span class="sxs-lookup"><span data-stu-id="fe429-145">Using the phone number presented in the Request-URI, perform the reverse number lookup within the tenant found in Step 2 or 3.</span></span> <span data-ttu-id="fe429-146">在上一個步驟中找到的租使用者內，將所提供的電話號碼與使用者 SIP URI 相符。</span><span class="sxs-lookup"><span data-stu-id="fe429-146">Match the presented phone number to a user SIP URI within the tenant found on the previous step.</span></span>

5. <span data-ttu-id="fe429-147">套用主幹設定。</span><span class="sxs-lookup"><span data-stu-id="fe429-147">Apply trunk settings.</span></span> <span data-ttu-id="fe429-148">尋找此 SBC 的租使用者管理員所設定的參數。</span><span class="sxs-lookup"><span data-stu-id="fe429-148">Find the parameters set by the tenant admin for this SBC.</span></span>

   <span data-ttu-id="fe429-149">Microsoft 不支援在 Microsoft SIP proxy 與成對式 SBC 之間擁有協力廠商 SIP proxy 或使用者代理伺服器，這可能會修改成對 SBC 所建立的要求 URI。</span><span class="sxs-lookup"><span data-stu-id="fe429-149">Microsoft does not support having a third-party SIP proxy or User Agent Server between the Microsoft SIP proxy and the paired SBC, which might modify the Request URI created by the paired SBC.</span></span>

   <span data-ttu-id="fe429-150">這兩個查閱（步驟2和3）的需求，在這篇文章的稍後部分中，您需要有一個 SBC 互相連接到許多租使用者的情形（載波案例）。</span><span class="sxs-lookup"><span data-stu-id="fe429-150">The requirements for the two lookups (steps 2 and 3) needed for the scenario where one SBC is interconnected to many tenants (carrier scenario) are covered later in this article.</span></span>

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a><span data-ttu-id="fe429-151">連絡人標題與要求 URI 的詳細需求</span><span class="sxs-lookup"><span data-stu-id="fe429-151">Detailed requirements for Contact header and Request-URI</span></span>

#### <a name="contact-header"></a><span data-ttu-id="fe429-152">連絡人標題</span><span class="sxs-lookup"><span data-stu-id="fe429-152">Contact header</span></span>

<span data-ttu-id="fe429-153">針對所有來電至 Microsoft SIP proxy，連絡人報頭在 URI 主機名稱中必須有成對的 SBC FQDN，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fe429-153">For all incoming calls to the Microsoft SIP proxy, the Contact header must have the paired SBC FQDN in the URI hostname as follows:</span></span>

<span data-ttu-id="fe429-154">語法： Contact： <sip： SBC 的電話或 sip address@FQDN; transport = tls></span><span class="sxs-lookup"><span data-stu-id="fe429-154">Syntax: Contact:  <sip:phone or sip address@FQDN of the SBC;transport=tls></span></span> 

<span data-ttu-id="fe429-155">此名稱也必須在所提供之憑證的 [通用名稱] 或 [消費者替換名稱] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="fe429-155">This name must also be in the Common Name or Subject Alternative name field(s) of the presented certificate.</span></span> <span data-ttu-id="fe429-156">Microsoft 支援在憑證的 [通用名稱] 或 [Subject 替換名稱] 欄位中，使用名稱的萬用字元。</span><span class="sxs-lookup"><span data-stu-id="fe429-156">Microsoft supports using wildcard values of the name(s) in the Common Name or Subject Alternative Name fields of the certificate.</span></span>   

<span data-ttu-id="fe429-157">在[RFC 2818 （section 3.1）](https://tools.ietf.org/html/rfc2818#section-3.1)中描述了萬用字元支援。</span><span class="sxs-lookup"><span data-stu-id="fe429-157">The support for wildcards is described in [RFC 2818, section 3.1](https://tools.ietf.org/html/rfc2818#section-3.1).</span></span> <span data-ttu-id="fe429-158">說</span><span class="sxs-lookup"><span data-stu-id="fe429-158">Specifically:</span></span>

<span data-ttu-id="fe429-159">*[名稱可能包含 \* 要與任何單一網功能變數名稱稱元件或元件片段相符的萬用字元字元。例如， \* . a.com 與 foo.a.com （而不是 bar.foo.a.com）相符 \* foo.com，但不符合 bar.com。」*</span><span class="sxs-lookup"><span data-stu-id="fe429-159">*"Names may contain the wildcard character \* which is considered to match any single domain name component or component fragment. E.g., \*.a.com matches foo.a.com but not bar.foo.a.com. f\*.com matches foo.com but not bar.com."*</span></span>

<span data-ttu-id="fe429-160">如果由 SBC 傳送 SIP 訊息中的連絡人標頭中有多個值，則只會使用連絡人標題第一個值的 FQDN 部分。</span><span class="sxs-lookup"><span data-stu-id="fe429-160">If more than one value in the Contact header presented in a SIP message is sent by the SBC, only the FQDN portion of the first value of the Contact header is used.</span></span>

#### <a name="request-uri"></a><span data-ttu-id="fe429-161">要求 URI</span><span class="sxs-lookup"><span data-stu-id="fe429-161">Request-URI</span></span> 

<span data-ttu-id="fe429-162">針對所有來電，要求 URI 是用來將電話號碼與使用者進行相符。</span><span class="sxs-lookup"><span data-stu-id="fe429-162">For all incoming calls, the Request-URI is used to match the phone number to a user.</span></span>   

<span data-ttu-id="fe429-163">目前電話號碼必須包含加號（+），如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="fe429-163">Currently The phone number must contain a plus sign (+) as shown in the following example.</span></span> 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a><span data-ttu-id="fe429-164">連絡人與記錄-路由標題考慮</span><span class="sxs-lookup"><span data-stu-id="fe429-164">Contact and Record-Route headers considerations</span></span>

<span data-ttu-id="fe429-165">SIP proxy 需要針對新的對話用戶端事務（例如再見或重新邀請），以及在回復 SIP 選項時，計算下一個躍點 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fe429-165">The SIP proxy needs to calculate the next hop FQDN for new in-dialog client transactions (for example Bye or Re-Invite), and when replying to SIP Options.</span></span> <span data-ttu-id="fe429-166">使用連絡人或記錄-路線。</span><span class="sxs-lookup"><span data-stu-id="fe429-166">Either Contact or Record-Route are used.</span></span> 

<span data-ttu-id="fe429-167">根據 RFC 3261，任何可能會產生新對話方塊的要求中，都必須有連絡人標頭。</span><span class="sxs-lookup"><span data-stu-id="fe429-167">According to RFC 3261, Contact header is required in any request that can result in a new dialog.</span></span> <span data-ttu-id="fe429-168">只有在 proxy 想要在對話方塊中保留未來要求的路徑時，才需要記錄路由。</span><span class="sxs-lookup"><span data-stu-id="fe429-168">The Record-Route is only required if a proxy wants to stay on the path of future requests in a dialog.</span></span> 

<span data-ttu-id="fe429-169">Microsoft 建議只使用連絡人標頭的原因如下：</span><span class="sxs-lookup"><span data-stu-id="fe429-169">Microsoft recommends using only Contact header for the following reasons:</span></span>

- <span data-ttu-id="fe429-170">根據 RFC 3261，如果 proxy 想要在對話方塊中保留未來要求的路徑，這並不重要，就是 Microsoft SIP proxy 與成對的 SBC 之間的所有流量都不是必要的。</span><span class="sxs-lookup"><span data-stu-id="fe429-170">Per RFC 3261, Record-Route is used if a proxy wants to stay on the path of future requests in a dialog, which is not essential as all traffic goes between the Microsoft SIP proxy and the paired SBC.</span></span> <span data-ttu-id="fe429-171">在 SBC 與 Microsoft SIP proxy 之間，不需要使用中間 proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="fe429-171">There is no need for an intermediate proxy server between the SBC and Microsoft SIP proxy.</span></span>

- <span data-ttu-id="fe429-172">Microsoft SIP proxy 只會使用連絡人頭（而非記錄路由）來決定傳送輸出 ping 選項時的下一個躍點。</span><span class="sxs-lookup"><span data-stu-id="fe429-172">The Microsoft SIP proxy uses only Contact header (not Record-Route) to determine the next hop when sending outbound ping Options.</span></span> <span data-ttu-id="fe429-173">只設定一個參數（連絡人），而不是兩個（連絡人與記錄-路線），可簡化管理。</span><span class="sxs-lookup"><span data-stu-id="fe429-173">Configuring only one parameter (Contact) instead of two (Contact and Record-Route) simplifies the administration.</span></span>

<span data-ttu-id="fe429-174">若要計算下一個躍點，SIP proxy 會使用：</span><span class="sxs-lookup"><span data-stu-id="fe429-174">To calculate the next hop, the SIP proxy uses:</span></span>

- <span data-ttu-id="fe429-175">優先順序1。</span><span class="sxs-lookup"><span data-stu-id="fe429-175">Priority 1.</span></span> <span data-ttu-id="fe429-176">頂層記錄-路線。</span><span class="sxs-lookup"><span data-stu-id="fe429-176">Top-level Record-Route.</span></span> <span data-ttu-id="fe429-177">如果頂層記錄-路由包含 FQDN 名稱或 IP，則會使用 FQDN 名稱或 IP 來產生輸出的內連接對話方塊連線。</span><span class="sxs-lookup"><span data-stu-id="fe429-177">If the top-level Record-Route contains the FQDN name or IP, the FQDN name or IP is used to make the outbound in-dialog connection.</span></span>

- <span data-ttu-id="fe429-178">[優先順序 2]。</span><span class="sxs-lookup"><span data-stu-id="fe429-178">Priority 2.</span></span> <span data-ttu-id="fe429-179">連絡人標頭。</span><span class="sxs-lookup"><span data-stu-id="fe429-179">Contact header.</span></span> <span data-ttu-id="fe429-180">如果記錄-路由不存在，SIP proxy 會查詢連絡人標頭的值，以產生輸出連線。</span><span class="sxs-lookup"><span data-stu-id="fe429-180">If Record-Route does not exist, the SIP proxy will look up the value of the Contact header to make the outbound connection.</span></span> <span data-ttu-id="fe429-181">（這是建議的配置。）</span><span class="sxs-lookup"><span data-stu-id="fe429-181">(This is the recommended configuration.)</span></span>

<span data-ttu-id="fe429-182">如果使用了連絡人與記錄路線，則 SBC 管理員必須讓其值保持相同，這會造成系統管理的額外負荷。</span><span class="sxs-lookup"><span data-stu-id="fe429-182">If both Contact and Record-Route are used, the SBC administrator must keep their values identical, which causes administrative overhead.</span></span> 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a><span data-ttu-id="fe429-183">在連絡人或記錄-路線中使用 FQDN 名稱</span><span class="sxs-lookup"><span data-stu-id="fe429-183">Use of FQDN name in Contact or Record-Route</span></span>

<span data-ttu-id="fe429-184">不論是記錄-路由或連絡人，都不支援 IP 位址的使用。</span><span class="sxs-lookup"><span data-stu-id="fe429-184">Use of an IP address is not supported in either Record-Route or Contact.</span></span> <span data-ttu-id="fe429-185">唯一受支援的選項是 FQDN，必須符合 SBC 憑證的通用名稱或消費者替換名稱（在憑證中支援通配值）。</span><span class="sxs-lookup"><span data-stu-id="fe429-185">The only supported option is an FQDN, which must match either the Common Name or Subject Alternative Name of the SBC certificate (wildcard values in the certificate are supported).</span></span>

- <span data-ttu-id="fe429-186">如果您的 IP 位址是記錄-路由或連絡人，則憑證檢查失敗且通話失敗。</span><span class="sxs-lookup"><span data-stu-id="fe429-186">If an IP address is presented in Record-route or Contact, the certificate check fails and the call fails.</span></span>

- <span data-ttu-id="fe429-187">如果 FQDN 不符合所提供憑證中常見或消費者備用名稱的值，通話就會失敗。</span><span class="sxs-lookup"><span data-stu-id="fe429-187">If the FQDN does not match the value of the Common or Subject Alternative Name in the presented certificate, the call fails.</span></span> 

## <a name="inbound-call-sip-dialog-description"></a><span data-ttu-id="fe429-188">入站通話： SIP 對話方塊描述</span><span class="sxs-lookup"><span data-stu-id="fe429-188">Inbound call: SIP dialog description</span></span>

<span data-ttu-id="fe429-189">下表摘要列出非旁路及旁路模式之間的通話流程差異與相似性：</span><span class="sxs-lookup"><span data-stu-id="fe429-189">The following table below summarizes the call flow differences and similarities between non-bypass and bypass modes:</span></span>

| <span data-ttu-id="fe429-190">參數名稱</span><span class="sxs-lookup"><span data-stu-id="fe429-190">Parameter name</span></span> | <span data-ttu-id="fe429-191">非旁路模式</span><span class="sxs-lookup"><span data-stu-id="fe429-191">Non-bypass mode</span></span> | <span data-ttu-id="fe429-192">旁路模式</span><span class="sxs-lookup"><span data-stu-id="fe429-192">Bypass mode</span></span>
| :---------------------  |:---------------------- |:----------------|
| <span data-ttu-id="fe429-193">183和200訊息中的媒體候選人來自</span><span class="sxs-lookup"><span data-stu-id="fe429-193">Media candidates in 183 and 200 messages coming from</span></span> | <span data-ttu-id="fe429-194">媒體處理器</span><span class="sxs-lookup"><span data-stu-id="fe429-194">Media processors</span></span> | <span data-ttu-id="fe429-195">台</span><span class="sxs-lookup"><span data-stu-id="fe429-195">Clients</span></span> | 
| <span data-ttu-id="fe429-196">SBC 可以接收的183訊息數</span><span class="sxs-lookup"><span data-stu-id="fe429-196">Number of 183 messages SBC can receive</span></span> | <span data-ttu-id="fe429-197">每個會話一個</span><span class="sxs-lookup"><span data-stu-id="fe429-197">One per session</span></span> | <span data-ttu-id="fe429-198">條</span><span class="sxs-lookup"><span data-stu-id="fe429-198">Multiple</span></span> | 
| <span data-ttu-id="fe429-199">通話可以是臨時的答案（183）</span><span class="sxs-lookup"><span data-stu-id="fe429-199">Call can be with provisional answer (183)</span></span> | <span data-ttu-id="fe429-200">是</span><span class="sxs-lookup"><span data-stu-id="fe429-200">Yes</span></span> | <span data-ttu-id="fe429-201">是</span><span class="sxs-lookup"><span data-stu-id="fe429-201">Yes</span></span> |
| <span data-ttu-id="fe429-202">通話可能不會有臨時答案（183）</span><span class="sxs-lookup"><span data-stu-id="fe429-202">Call can be without provisional answer (183)</span></span> | <span data-ttu-id="fe429-203">是</span><span class="sxs-lookup"><span data-stu-id="fe429-203">Yes</span></span> | <span data-ttu-id="fe429-204">是</span><span class="sxs-lookup"><span data-stu-id="fe429-204">Yes</span></span> |

###  <a name="non-media-bypass-flow"></a><span data-ttu-id="fe429-205">非媒體旁路流程</span><span class="sxs-lookup"><span data-stu-id="fe429-205">Non-media bypass flow</span></span>

<span data-ttu-id="fe429-206">團隊使用者可能同時擁有多個端點。</span><span class="sxs-lookup"><span data-stu-id="fe429-206">A Teams user might have multiple endpoints at the same time.</span></span> <span data-ttu-id="fe429-207">例如，Windows 用戶端、iPhone 版團隊用戶端和團隊手機（團隊 Android 用戶端）的團隊。</span><span class="sxs-lookup"><span data-stu-id="fe429-207">For example, Teams for Windows client, Teams for iPhone client, and Teams Phone (Teams Android client).</span></span> <span data-ttu-id="fe429-208">每個端點可能會以下列方式通知 HTTP rest：</span><span class="sxs-lookup"><span data-stu-id="fe429-208">Each endpoint might signal an HTTP rest as follows:</span></span>

-   <span data-ttu-id="fe429-209">呼叫進度–由 SIP proxy 將其轉換成 SIP 訊息180。</span><span class="sxs-lookup"><span data-stu-id="fe429-209">Call progress – converted by the SIP proxy to the SIP message 180.</span></span> <span data-ttu-id="fe429-210">在接收郵件180時，SBC 必須產生本機響鈴。</span><span class="sxs-lookup"><span data-stu-id="fe429-210">On receiving message 180, the SBC must generate local ringing.</span></span>

-   <span data-ttu-id="fe429-211">媒體答案–由 SIP proxy 轉換成在會話描述通訊協定（SDP）中有媒體候選人的訊息183。</span><span class="sxs-lookup"><span data-stu-id="fe429-211">Media answer – converted by the SIP proxy to message 183 with media candidates in Session Description Protocol (SDP).</span></span> <span data-ttu-id="fe429-212">在接收郵件183時，SBC 預期會連線至在 SDP 訊息中收到的媒體候選人。</span><span class="sxs-lookup"><span data-stu-id="fe429-212">On receiving message 183, the SBC expects to connect to the media candidates received in the SDP message.</span></span> <span data-ttu-id="fe429-213">請注意，在某些情況下，可能不會產生媒體答案，而且終點可能會以「已接受通話」訊息回答。</span><span class="sxs-lookup"><span data-stu-id="fe429-213">Note that in some cases the Media answer might not be generated, and the end point might answer with “Call Accepted” message.</span></span>

-   <span data-ttu-id="fe429-214">呼叫已接受–由 SIP proxy 轉換為 SIP 訊息200與 SDP。</span><span class="sxs-lookup"><span data-stu-id="fe429-214">Call accepted – converted by the SIP proxy to SIP message 200 with SDP.</span></span> <span data-ttu-id="fe429-215">在接收郵件200時，SBC 預期會在所提供的 SDP 候選人中傳送和接收媒體。</span><span class="sxs-lookup"><span data-stu-id="fe429-215">On receiving message 200, the SBC is expected to send and receive media to and from the provided SDP candidates.</span></span>

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a><span data-ttu-id="fe429-216">使用臨時應答的多個端點</span><span class="sxs-lookup"><span data-stu-id="fe429-216">Multiple endpoints ringing with provisional answer</span></span>

1.  <span data-ttu-id="fe429-217">收到 SBC 中的第一個邀請之後，SIP proxy 就會傳送「SIP SIP/2.0 100 嘗試」訊息，並將有關來電的所有最終使用者端點通知給所有。</span><span class="sxs-lookup"><span data-stu-id="fe429-217">On receiving the first Invite from the SBC, the SIP proxy sends the message "SIP SIP/2.0 100 Trying" and notifies all end user endpoints about the incoming call.</span></span> 

2.  <span data-ttu-id="fe429-218">收到通知時，每個端點都會開始響鈴並傳送「呼叫進度」訊息給 SIP proxy。</span><span class="sxs-lookup"><span data-stu-id="fe429-218">Upon notification, each endpoint will start ringing and sending "Call progress” messages to the SIP proxy.</span></span> <span data-ttu-id="fe429-219">因為團隊使用者可以有多個端點，所以 SIP proxy 可能會收到多個呼叫進度訊息。</span><span class="sxs-lookup"><span data-stu-id="fe429-219">Because a Teams user can have multiple end points, the SIP proxy might receive multiple Call Progress messages.</span></span>

3.  <span data-ttu-id="fe429-220">針對從用戶端收到的每個呼叫進度訊息，SIP proxy 會將呼叫進度訊息轉換為 SIP 訊息 "SIP SIP/2.0 180 嘗試"。</span><span class="sxs-lookup"><span data-stu-id="fe429-220">For every Call Progress message received from the clients, the SIP proxy converts the Call Progress message to the SIP message "SIP SIP/2.0 180 Trying".</span></span> <span data-ttu-id="fe429-221">傳送這類訊息的間隔是由從呼叫控制器接收郵件的間隔所定義。</span><span class="sxs-lookup"><span data-stu-id="fe429-221">The interval for sending such messages is defined by the interval of the receiving messages from the Call Controller.</span></span> <span data-ttu-id="fe429-222">在下圖中，SIP proxy 產生 2 180 的訊息。</span><span class="sxs-lookup"><span data-stu-id="fe429-222">In the following diagram, there are two 180 messages generated by the SIP proxy.</span></span> <span data-ttu-id="fe429-223">這些訊息來自使用者的兩個團隊端點。</span><span class="sxs-lookup"><span data-stu-id="fe429-223">These messages come from the two Teams endpoints of the user.</span></span> <span data-ttu-id="fe429-224">用戶端每個都有唯一的標記識別項。</span><span class="sxs-lookup"><span data-stu-id="fe429-224">The clients each have a unique Tag ID.</span></span>  <span data-ttu-id="fe429-225">來自不同端點的每一封郵件都將是一個獨立的會話（[至] 欄位中的參數「標記」會不同）。</span><span class="sxs-lookup"><span data-stu-id="fe429-225">Every message coming from a different endpoint will be a separate session (the parameter “tag” in the “To” field will be different).</span></span> <span data-ttu-id="fe429-226">但端點可能不會產生訊息180並立即傳送訊息183，如下列圖表所示。</span><span class="sxs-lookup"><span data-stu-id="fe429-226">But an endpoint might not generate message 180 and send message 183 right away as shown in the following diagram.</span></span>

4.  <span data-ttu-id="fe429-227">當端點使用端點媒體候選人的 IP 位址產生媒體答案訊息時，SIP proxy 會將收到的訊息轉換為「SIP 183 會話進度」訊息，並將來自用戶端的 SDP 從媒體處理器取代。</span><span class="sxs-lookup"><span data-stu-id="fe429-227">Once an endpoint generates a Media Answer message with the IP addresses of endpoint’s media candidates, the SIP proxy converts the message received to a "SIP 183 Session Progress" message with the SDP from the client replaced by the SDP from the Media Processor.</span></span> <span data-ttu-id="fe429-228">在下圖中，分叉2的端點已接聽通話。</span><span class="sxs-lookup"><span data-stu-id="fe429-228">In the following diagram, the endpoint from Fork 2 answered the call.</span></span> <span data-ttu-id="fe429-229">如果主幹是非繞過的，183 SIP 訊息只會產生一次（Ring Bot 或用戶端結束點）。</span><span class="sxs-lookup"><span data-stu-id="fe429-229">If the trunk is non-bypassed, the 183 SIP message is generated only once (either Ring Bot or Client End Point).</span></span> <span data-ttu-id="fe429-230">183可能會出現在現有的分叉或開始新的物件。</span><span class="sxs-lookup"><span data-stu-id="fe429-230">The 183 might come on an existing fork or start a new one.</span></span>

5.  <span data-ttu-id="fe429-231">來電接受訊息會與接受通話之端點的最終候選人一起傳送。</span><span class="sxs-lookup"><span data-stu-id="fe429-231">A Call Acceptance message is sent with the final candidates of the endpoint that accepted the call.</span></span> <span data-ttu-id="fe429-232">[通話接受] 訊息會轉換為 SIP 訊息200。</span><span class="sxs-lookup"><span data-stu-id="fe429-232">The Call Acceptance message is converted to SIP message 200.</span></span> 

![顯示多個端點與臨時應答鈴聲的圖表](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a><span data-ttu-id="fe429-234">多個端點鈴聲沒有臨時答案</span><span class="sxs-lookup"><span data-stu-id="fe429-234">Multiple endpoints ringing without provisional answer</span></span>

1.  <span data-ttu-id="fe429-235">收到 SBC 中的第一個邀請之後，SIP proxy 就會傳送「SIP SIP/2.0 100 嘗試」訊息，並將有關來電的所有最終使用者端點通知給所有。</span><span class="sxs-lookup"><span data-stu-id="fe429-235">On receiving the first Invite from the SBC, the SIP proxy sends the message "SIP SIP/2.0 100 Trying" and notifies all end user endpoints about the incoming call.</span></span> 

2.  <span data-ttu-id="fe429-236">收到通知時，每個端點都會開始響鈴，並將「通話進度」訊息傳送給 SIP proxy。</span><span class="sxs-lookup"><span data-stu-id="fe429-236">Upon notification, each endpoint will start ringing and sending the message "Call progress” to the SIP proxy.</span></span> <span data-ttu-id="fe429-237">因為團隊使用者可以有多個端點，所以 SIP proxy 可能會收到多個呼叫進度訊息。</span><span class="sxs-lookup"><span data-stu-id="fe429-237">Because a Teams user can have multiple end points, the SIP proxy might receive multiple Call Progress messages.</span></span>

3.  <span data-ttu-id="fe429-238">針對從用戶端收到的每個呼叫進度訊息，SIP proxy 會將呼叫進度訊息轉換為 SIP 訊息 "SIP SIP/2.0 180 嘗試"。</span><span class="sxs-lookup"><span data-stu-id="fe429-238">For every Call Progress message received from the clients, the SIP proxy converts the Call Progress message to the SIP message "SIP SIP/2.0 180 Trying".</span></span>  <span data-ttu-id="fe429-239">傳送訊息的間隔是由從呼叫控制器接收郵件的間隔所定義。</span><span class="sxs-lookup"><span data-stu-id="fe429-239">The interval for sending the messages is defined by the interval of receiving the messages from the Call Controller.</span></span> <span data-ttu-id="fe429-240">在下圖中，有 SIP proxy 產生的 2 180 郵件，這表示使用者登入三個小組用戶端，而每個用戶端都會傳送呼叫進度。</span><span class="sxs-lookup"><span data-stu-id="fe429-240">On the picture below there are two 180 messages generated by the SIP proxy, meaning that user logged into three Teams clients and each client send the call progress.</span></span> <span data-ttu-id="fe429-241">每封郵件都將是一個單獨的會話（[至] 欄位中的參數 "標記" 不一樣）</span><span class="sxs-lookup"><span data-stu-id="fe429-241">Every message will be a separate session (parameter “tag” in “To” field is different)</span></span>

4.  <span data-ttu-id="fe429-242">來電接受訊息會與接受通話之端點的最終候選人一起傳送。</span><span class="sxs-lookup"><span data-stu-id="fe429-242">A Call Acceptance message is sent with the final candidates of the endpoint that accepted the call.</span></span> <span data-ttu-id="fe429-243">[通話接受] 訊息會轉換為 SIP 訊息200。</span><span class="sxs-lookup"><span data-stu-id="fe429-243">The Call Acceptance message is converted to SIP message 200.</span></span> 

![圖表顯示多個端點的響鈴，沒有臨時答案](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a><span data-ttu-id="fe429-245">媒體旁路流程</span><span class="sxs-lookup"><span data-stu-id="fe429-245">Media bypass flow</span></span>

<span data-ttu-id="fe429-246">媒體略過案例中會使用相同的訊息（100嘗試、180、183）。</span><span class="sxs-lookup"><span data-stu-id="fe429-246">The same messages (100 Trying, 180, 183) are used in the media bypass scenario.</span></span> 

<span data-ttu-id="fe429-247">下面的架構顯示旁路通話流程的範例。</span><span class="sxs-lookup"><span data-stu-id="fe429-247">The schema below shows an example of the bypass call flow.</span></span> <span data-ttu-id="fe429-248">請注意，媒體候選人可能來自不同的端點。</span><span class="sxs-lookup"><span data-stu-id="fe429-248">Note that the media candidates can come from different endpoints.</span></span> 

![顯示多個端點與臨時應答鈴聲的圖表](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a><span data-ttu-id="fe429-250">[取代] 選項</span><span class="sxs-lookup"><span data-stu-id="fe429-250">Replaces option</span></span>

<span data-ttu-id="fe429-251">SBC 必須支援以 replace 取代的邀請。</span><span class="sxs-lookup"><span data-stu-id="fe429-251">The SBC must support Invite with Replaces.</span></span>

## <a name="size-of-sdp-considerations"></a><span data-ttu-id="fe429-252">SDP 考慮的大小</span><span class="sxs-lookup"><span data-stu-id="fe429-252">Size of SDP considerations</span></span>

<span data-ttu-id="fe429-253">直接路由介面可能會傳送超過1500個位元組的 SIP 訊息。</span><span class="sxs-lookup"><span data-stu-id="fe429-253">The Direct Routing interface might send a SIP message exceeding 1,500 bytes.</span></span>  <span data-ttu-id="fe429-254">SDP 的大小主要會造成這個問題。</span><span class="sxs-lookup"><span data-stu-id="fe429-254">The size of SDP primarily causes this.</span></span> <span data-ttu-id="fe429-255">不過，如果在 SBC 後有 UDP 幹線，可能會在從 Microsoft SIP proxy 轉寄到不修改中繼的情況下，拒絕該訊息。</span><span class="sxs-lookup"><span data-stu-id="fe429-255">However, if there is a UDP trunk behind the SBC, it might reject the message if it is forwarded from the Microsoft SIP proxy to the trunk unmodified.</span></span> <span data-ttu-id="fe429-256">Microsoft 建議您在將訊息傳送至 UDP trunks 時，在 SBC 上去除一些值。</span><span class="sxs-lookup"><span data-stu-id="fe429-256">Microsoft recommends stripping some values in SDP on the SBC when sending the message to the UDP trunks.</span></span> <span data-ttu-id="fe429-257">例如，您可以移除 ICE 候選或未使用的編解碼器。</span><span class="sxs-lookup"><span data-stu-id="fe429-257">For example, the ICE candidates or unused codecs can be removed.</span></span>

## <a name="call-transfer"></a><span data-ttu-id="fe429-258">來電轉接</span><span class="sxs-lookup"><span data-stu-id="fe429-258">Call transfer</span></span>

<span data-ttu-id="fe429-259">直接路由支援兩種來電轉接方法：</span><span class="sxs-lookup"><span data-stu-id="fe429-259">Direct Routing supports two methods for call transfer:</span></span>

- <span data-ttu-id="fe429-260">選項1。</span><span class="sxs-lookup"><span data-stu-id="fe429-260">Option 1.</span></span> <span data-ttu-id="fe429-261">SIP proxy 進程會從本機參照用戶端，並做為 Referee，如 RFC 3892 的7.1 一節所述。</span><span class="sxs-lookup"><span data-stu-id="fe429-261">SIP proxy processes Refer from the client locally and acts as a Referee as described in section 7.1 of RFC 3892.</span></span>

  <span data-ttu-id="fe429-262">使用此選項時，SIP proxy 會終止傳輸並新增邀請。</span><span class="sxs-lookup"><span data-stu-id="fe429-262">With this option, the SIP proxy terminates the transfer and adds a new Invite.</span></span> 


- <span data-ttu-id="fe429-263">選項2。</span><span class="sxs-lookup"><span data-stu-id="fe429-263">Option 2.</span></span> <span data-ttu-id="fe429-264">SIP proxy 會傳送參照給 SBC 並充當 Transferor，如 RFC 5589 的第6節所述。</span><span class="sxs-lookup"><span data-stu-id="fe429-264">SIP proxy sends the Refer to the SBC and acts as a Transferor as describing in Section 6 of RFC 5589.</span></span>

  <span data-ttu-id="fe429-265">使用此選項時，SIP proxy 會傳送對 SBC 的參照，並預期 SBC 完全處理傳輸。</span><span class="sxs-lookup"><span data-stu-id="fe429-265">With this option, the SIP proxy sends a Refer to the SBC and expects the SBC to handle the Transfer fully.</span></span>

<span data-ttu-id="fe429-266">SIP proxy 會根據 SBC 所報告的功能，選取該方法。</span><span class="sxs-lookup"><span data-stu-id="fe429-266">The SIP proxy selects the method based on the capabilities reported by the SBC.</span></span> <span data-ttu-id="fe429-267">如果 SBC 指出它支援「參考」這個方法，SIP proxy 將會使用 Option 2 進行來電轉接。</span><span class="sxs-lookup"><span data-stu-id="fe429-267">If the SBC indicates that it supports the method “Refer”, the SIP proxy will use Option 2 for call transfers.</span></span>

<span data-ttu-id="fe429-268">下列是一個 SBC 範例，該範例會傳送支援 method 方法的訊息：</span><span class="sxs-lookup"><span data-stu-id="fe429-268">The following is an example of an SBC sending the message that the Refer method is supported:</span></span>

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

<span data-ttu-id="fe429-269">如果 SBC 不指出該參照為支援的方法，直連路由將使用選項1（SIP proxy 充當 Referee）。</span><span class="sxs-lookup"><span data-stu-id="fe429-269">If the SBC doesn’t indicate that Refer as a supported method, Direct Routing will use Option 1 (SIP proxy acts as a Referee) .</span></span> <span data-ttu-id="fe429-270">SBC 也必須發出支援 Notify 方法的信號：</span><span class="sxs-lookup"><span data-stu-id="fe429-270">The SBC  must also signal that it supports the Notify method:</span></span>

<span data-ttu-id="fe429-271">指示不支援此參考方法的 SBC 範例：</span><span class="sxs-lookup"><span data-stu-id="fe429-271">Example of SBC indicating that Refer method is not supported:</span></span>

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a><span data-ttu-id="fe429-272">SIP proxy 進程是從本機引用用戶端，並做為 Referee</span><span class="sxs-lookup"><span data-stu-id="fe429-272">SIP proxy processes Refer from the client locally and acts as a Referee</span></span>

<span data-ttu-id="fe429-273">如果 SBC 指出不支援 method 方法，SIP proxy 就會充當 Referee。</span><span class="sxs-lookup"><span data-stu-id="fe429-273">If the SBC indicated that the Refer method is not supported, the SIP proxy acts as a Referee.</span></span> 

<span data-ttu-id="fe429-274">來自用戶端的參考要求將會在 SIP proxy 上終止。</span><span class="sxs-lookup"><span data-stu-id="fe429-274">The Refer request that comes from the client will be terminated on the SIP proxy.</span></span> <span data-ttu-id="fe429-275">（來自用戶端的參照要求在下圖中顯示為「來電轉接至 Dave」。</span><span class="sxs-lookup"><span data-stu-id="fe429-275">(The Refer request from the client is shown as “Call transfer to Dave” in the following diagram.</span></span>  <span data-ttu-id="fe429-276">如需詳細資訊，請參閱[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt)的7.1 節。</span><span class="sxs-lookup"><span data-stu-id="fe429-276">For more information, see section 7.1 of [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt).</span></span> 

![顯示多個端點與臨時應答鈴聲的圖表](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a><span data-ttu-id="fe429-278">SIP proxy 傳送參照給 SBC 並充當 Transferor</span><span class="sxs-lookup"><span data-stu-id="fe429-278">SIP proxy send the Refer to the SBC and acts as a Transferor</span></span>

<span data-ttu-id="fe429-279">這是來電轉接的首選方法，對於尋找媒體略過認證的裝置是強制性的。</span><span class="sxs-lookup"><span data-stu-id="fe429-279">This is the preferred method for call transfers, and it is mandatory for devices seeking media bypass certification.</span></span> <span data-ttu-id="fe429-280">在媒體旁路模式中不支援不含 SBC 即可處理引用的來電轉接。</span><span class="sxs-lookup"><span data-stu-id="fe429-280">Call Transfer without the SBC being able to handle Refer is not supported in media bypass mode.</span></span> 

<span data-ttu-id="fe429-281">標準將在 RFC 5589 的第6節中說明。</span><span class="sxs-lookup"><span data-stu-id="fe429-281">The standard is explained in Section 6 of RFC 5589.</span></span> <span data-ttu-id="fe429-282">相關 Rfc 包括：</span><span class="sxs-lookup"><span data-stu-id="fe429-282">The related RFCs are:</span></span>

- [<span data-ttu-id="fe429-283">會話初始通訊協定（SIP）通話控制-轉移</span><span class="sxs-lookup"><span data-stu-id="fe429-283">Session Initiation Protocol (SIP) Call Control - Transfer</span></span>](https://tools.ietf.org/html/rfc5589)

- [<span data-ttu-id="fe429-284">會話初始通訊協定（SIP）「取代」標頭</span><span class="sxs-lookup"><span data-stu-id="fe429-284">Session Initiation Protocol (SIP) "Replaces" Header</span></span>](https://tools.ietf.org/html/rfc3891)

- [<span data-ttu-id="fe429-285">會話初始通訊協定（SIP）「參照者」機制</span><span class="sxs-lookup"><span data-stu-id="fe429-285">Session Initiation Protocol (SIP) "Referred-By" mechanism</span></span>](https://tools.ietf.org/html/rfc3892)

<span data-ttu-id="fe429-286">此選項假設 SIP proxy 充當 Transferor，並將 [參閱] 訊息傳送給 SBC。</span><span class="sxs-lookup"><span data-stu-id="fe429-286">This option assumes that the SIP proxy acts as a Transferor and sends a Refer message to the SBC.</span></span> <span data-ttu-id="fe429-287">SBC 是作為 Transferee，並處理參考以產生新的傳送優惠。</span><span class="sxs-lookup"><span data-stu-id="fe429-287">The SBC acts as a Transferee and handles the Refer to generate a new offer for transfer.</span></span> <span data-ttu-id="fe429-288">可能有兩種情況：</span><span class="sxs-lookup"><span data-stu-id="fe429-288">There are two possible cases:</span></span>

- <span data-ttu-id="fe429-289">通話會轉接至外部 PSTN 參與者。</span><span class="sxs-lookup"><span data-stu-id="fe429-289">The call is transferred to an external PSTN participant.</span></span> 
- <span data-ttu-id="fe429-290">通話是透過 SBC 從某個團隊使用者轉接給同一個租使用者中的另一個小組使用者。</span><span class="sxs-lookup"><span data-stu-id="fe429-290">The call is transferred from one Teams user to another Teams user in the same tenant via the SBC.</span></span> 

<span data-ttu-id="fe429-291">如果通話是透過 SBC 從某個團隊使用者轉接到另一個，則 SBC 預期會使用參考訊息中接收的資訊，為傳輸目標（團隊使用者）發出新的邀請（開始新的對話方塊）。</span><span class="sxs-lookup"><span data-stu-id="fe429-291">If the call is transferred from one Teams user to another via the SBC, the SBC is expected to issue a new invite (start a new dialog) for the transfer target (the Teams user) using the information received in the Refer message.</span></span> 

<span data-ttu-id="fe429-292">若要在內部填入要求交易的 [To/Transferor] 欄位，SIP proxy 需要在 [參考資料]/[參照者] 標頭內傳達這項資訊。</span><span class="sxs-lookup"><span data-stu-id="fe429-292">To populate the To/Transferor fields for the transaction of the request internally, the SIP proxy needs to convey this information  inside the REFER-TO/REFERRED-BY headers.</span></span> 

<span data-ttu-id="fe429-293">SIP proxy 會將「參考」視為 SIP URI，由主機名稱中的 SIP proxy FQDN 以及下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="fe429-293">The SIP proxy will form the REFER-TO as a SIP URI comprised of a SIP proxy FQDN in the hostname and either one of the following:</span></span>

- <span data-ttu-id="fe429-294">如果傳輸目標是電話號碼，則是 URI 的使用者名稱部分中的 E. 164 電話號碼，或者</span><span class="sxs-lookup"><span data-stu-id="fe429-294">An E.164 phone number in the username part of the URI in case the transfer target is a phone number, or</span></span>

- <span data-ttu-id="fe429-295">分別對完整轉接目標 MRI 與租使用者識別碼進行編碼的 x-y 和 x-y 參數</span><span class="sxs-lookup"><span data-stu-id="fe429-295">x-m and x-t parameters encoding the full transfer target MRI and tenant ID respectively</span></span> 

<span data-ttu-id="fe429-296">[被參照] 標頭是一個 SIP URI，其上有 transferor MRI，以及 transferor 租使用者識別碼和其他傳輸內容參數，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="fe429-296">The REFERRED-BY header is a SIP URI with transferor MRI encoded in it as well as transferor tenant ID and other transfer context parameters as shown in the following table:</span></span>

| <span data-ttu-id="fe429-297">參數</span><span class="sxs-lookup"><span data-stu-id="fe429-297">Parameter</span></span> | <span data-ttu-id="fe429-298">值</span><span class="sxs-lookup"><span data-stu-id="fe429-298">Value</span></span> | <span data-ttu-id="fe429-299">說明</span><span class="sxs-lookup"><span data-stu-id="fe429-299">Description</span></span> |  
|:---------------------  |:---------------------- |:---------------------- |
| <span data-ttu-id="fe429-300">x-m</span><span class="sxs-lookup"><span data-stu-id="fe429-300">x-m</span></span> | <span data-ttu-id="fe429-301">MRI</span><span class="sxs-lookup"><span data-stu-id="fe429-301">MRI</span></span> | <span data-ttu-id="fe429-302">以 [抄送] 填充的 transferor/轉讓目標的完整 MRI</span><span class="sxs-lookup"><span data-stu-id="fe429-302">Full MRI of transferor/transfer target as populated by CC</span></span> |
| <span data-ttu-id="fe429-303">x-y</span><span class="sxs-lookup"><span data-stu-id="fe429-303">x-t</span></span> | <span data-ttu-id="fe429-304">租使用者識別碼</span><span class="sxs-lookup"><span data-stu-id="fe429-304">Tenant ID</span></span> | <span data-ttu-id="fe429-305">x-y 的租使用者識別碼（由 CC 填入）選用的租使用者識別碼</span><span class="sxs-lookup"><span data-stu-id="fe429-305">x-t Tenant ID Optional Tenant Id as populated by CC</span></span> |
| <span data-ttu-id="fe429-306">x-ti</span><span class="sxs-lookup"><span data-stu-id="fe429-306">x-ti</span></span> | <span data-ttu-id="fe429-307">Transferor 相關識別碼</span><span class="sxs-lookup"><span data-stu-id="fe429-307">Transferor Correlation Id</span></span> | <span data-ttu-id="fe429-308">呼叫 transferor 的相關識別碼</span><span class="sxs-lookup"><span data-stu-id="fe429-308">Correlation Id of the call to the transferor</span></span> |
| <span data-ttu-id="fe429-309">x-tt</span><span class="sxs-lookup"><span data-stu-id="fe429-309">x-tt</span></span> | <span data-ttu-id="fe429-310">傳輸目標通話 URI</span><span class="sxs-lookup"><span data-stu-id="fe429-310">Transfer target call URI</span></span> | <span data-ttu-id="fe429-311">已編碼的呼叫取代 URI</span><span class="sxs-lookup"><span data-stu-id="fe429-311">Encoded call replacement URI</span></span> |

<span data-ttu-id="fe429-312">在這種情況下，[參考頁首] 的大小最多可以為400符號。</span><span class="sxs-lookup"><span data-stu-id="fe429-312">The size of the Refer Header can be up to 400 symbols in this case.</span></span> <span data-ttu-id="fe429-313">SBC 必須支援使用大小最大至400符號的資訊來處理參考訊息。</span><span class="sxs-lookup"><span data-stu-id="fe429-313">The SBC must support handling Refer messages with size up to 400 symbols.</span></span>

![顯示多個端點與臨時應答鈴聲的圖表](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a><span data-ttu-id="fe429-315">會話計時器</span><span class="sxs-lookup"><span data-stu-id="fe429-315">Session timer</span></span>

<span data-ttu-id="fe429-316">SIP proxy 支援（永遠提供）非旁路呼叫中的會話計時器，但不會在旁路呼叫中提供。</span><span class="sxs-lookup"><span data-stu-id="fe429-316">The SIP proxy supports (always offers) the Session Timer on non-bypass calls but does not offer it on bypass calls.</span></span> <span data-ttu-id="fe429-317">由 SBC 使用會話計時器並不是強制性的做法。</span><span class="sxs-lookup"><span data-stu-id="fe429-317">Use of the Session Timer by the SBC is not mandatory.</span></span>

##  <a name="use-of-request-uri-parameter-userphone"></a><span data-ttu-id="fe429-318">使用 Request-URI 參數 user = phone</span><span class="sxs-lookup"><span data-stu-id="fe429-318">Use of Request-URI parameter user=phone</span></span>

<span data-ttu-id="fe429-319">SIP proxy 會分析要求-URI，如果參數使用者 = phone 存在，服務會將要求 URI 處理為電話號碼，並將該號碼與使用者進行相符。</span><span class="sxs-lookup"><span data-stu-id="fe429-319">The SIP proxy analyses the Request-URI and if the parameter user=phone is present, the service will handle the Request-URI as a phone number, matching the number to a user.</span></span> <span data-ttu-id="fe429-320">如果參數不存在，SIP proxy 會套用啟發式來判斷要求 URI 使用者類型（電話號碼或 SIP 位址）。</span><span class="sxs-lookup"><span data-stu-id="fe429-320">If parameter is not present the SIP proxy applies heuristics to determine  the Request-URI user type (phone number or a SIP address).</span></span>

<span data-ttu-id="fe429-321">Microsof [建議] 請務必套用 user = 電話參數，以簡化通話設定處理常式。</span><span class="sxs-lookup"><span data-stu-id="fe429-321">Microsof recommends always applying the user=phone parameter to simplify the call setup process.</span></span>

## <a name="history-info-header"></a><span data-ttu-id="fe429-322">[歷程記錄-資訊] 標題</span><span class="sxs-lookup"><span data-stu-id="fe429-322">History-Info header</span></span>

<span data-ttu-id="fe429-323">[歷程記錄-資訊] 標頭是用來 retargeting SIP 要求，而「提供（s）可捕獲要求歷程記錄資訊以針對網路和使用者提供多種服務的標準機制」。</span><span class="sxs-lookup"><span data-stu-id="fe429-323">The History-Info header is used for retargeting SIP requests and “provide(s) a standard mechanism for capturing the request history information to enable a wide variety of services for networks and end-users.”</span></span> <span data-ttu-id="fe429-324">如需詳細資訊，請參閱[RFC 4244 – Section 1.1](http://www.ietf.org/rfc/rfc4244.txt)。</span><span class="sxs-lookup"><span data-stu-id="fe429-324">For more information, see [RFC 4244 – Section 1.1](http://www.ietf.org/rfc/rfc4244.txt).</span></span> <span data-ttu-id="fe429-325">針對 Microsoft Phone System，此標頭是用於 Simulring 和來電轉接案例中。</span><span class="sxs-lookup"><span data-stu-id="fe429-325">For Microsoft Phone System, this header is used in Simulring and Call Forwarding scenarios.</span></span>  

<span data-ttu-id="fe429-326">如果傳送，則會啟用 [歷程記錄] 資訊，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fe429-326">If sending, the History-Info is enabled as follows:</span></span>

- <span data-ttu-id="fe429-327">SIP proxy 會在個別的歷程記錄資訊專案中插入一個包含相關電話號碼的參數，這些內容包含傳送至 PSTN 控制器的歷程記錄資訊標頭。</span><span class="sxs-lookup"><span data-stu-id="fe429-327">The SIP proxy will insert a parameter containing the associated phone number in individual History-Info entries that comprise the History-Info header sent to the PSTN Controller.</span></span>  <span data-ttu-id="fe429-328">PSTN 控制器只使用具有電話號碼參數的專案，會重建新的歷程記錄資訊標頭，並透過 SIP proxy 將它傳送給 SIP 中繼提供者。</span><span class="sxs-lookup"><span data-stu-id="fe429-328">Using only entries that have the phone number parameter, the PSTN Controller will rebuild a new History-Info header, and pass it on to the SIP trunk provider via SIP proxy.</span></span>

- <span data-ttu-id="fe429-329">[歷程記錄-資訊] 標題會新增至同時撥打及來電轉接的情況。</span><span class="sxs-lookup"><span data-stu-id="fe429-329">History-Info header will be added for simultaneous ring and call forwarding cases.</span></span>

- <span data-ttu-id="fe429-330">將不會針對來電轉接案例新增 [歷程記錄-資訊] 標題。</span><span class="sxs-lookup"><span data-stu-id="fe429-330">History-Info header will not be added for call transfer cases.</span></span>

- <span data-ttu-id="fe429-331">已重建歷程記錄資訊標題中的個別歷程記錄專案會將電話號碼參數與直接路由 FQDN （sip.pstnhub.microsoft.com）組合在一起，並設為 URI 的主機元件;[user = phone "的參數會新增為 SIP URI 的一部分。</span><span class="sxs-lookup"><span data-stu-id="fe429-331">An individual history entry in the reconstructed History-Info header will have the phone number parameter provided combined with the Direct Routing FQDN (sip.pstnhub.microsoft.com) set as the host part of the URI; a parameter of ‘user=phone’ will be added as part of the SIP URI.</span></span>  <span data-ttu-id="fe429-332">與原始歷程記錄-資訊頭相關聯的任何其他參數（除了電話內容參數之外），都將會在重新構造的歷程記錄資訊標頭中傳遞。</span><span class="sxs-lookup"><span data-stu-id="fe429-332">Any other parameters associated with the original History-Info header, except for phone context parameters, will be passed through in the re-constructed History-Info header.</span></span>  <span data-ttu-id="fe429-333">請注意，只有當 SIP 幹線提供者是受信任的對等專案時，才能轉寄私人（由 RFC 4244 的3.3 區段中定義的機制所決定）。</span><span class="sxs-lookup"><span data-stu-id="fe429-333">Note that entries that are private (as determined by the mechanisms defined in Section 3.3 of RFC 4244) will be forwarded as is because  the SIP trunk provider is a trusted peer.</span></span>

- <span data-ttu-id="fe429-334">[入站記錄]-資訊將會被忽略。</span><span class="sxs-lookup"><span data-stu-id="fe429-334">Inbound History-Info is ignored.</span></span>

<span data-ttu-id="fe429-335">以下是 SIP proxy 傳送之歷程記錄資訊標頭的格式：</span><span class="sxs-lookup"><span data-stu-id="fe429-335">Following is the format of the History-info header sent by the SIP proxy:</span></span>

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

<span data-ttu-id="fe429-336">如果呼叫重新導向數次，則每次重新導向的相關資訊都會隨附適當的原因（依時間順序排列）。</span><span class="sxs-lookup"><span data-stu-id="fe429-336">If the call was redirected several times, information about every redirect is included with the appropriate reason in chronological order.</span></span>


<span data-ttu-id="fe429-337">頁首範例：</span><span class="sxs-lookup"><span data-stu-id="fe429-337">Header Example:</span></span>

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

<span data-ttu-id="fe429-338">[歷程記錄]-資訊受到強制 TLS 機制的保護。</span><span class="sxs-lookup"><span data-stu-id="fe429-338">The History-Info is protected by a mandatory TLS mechanism.</span></span> 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a><span data-ttu-id="fe429-339">指向直接路由與容錯移轉機制的 SBC 連接</span><span class="sxs-lookup"><span data-stu-id="fe429-339">SBC connection to Direct Routing and failover mechanism</span></span>

<span data-ttu-id="fe429-340">請參閱[直接路由規劃](direct-routing-plan.md#failover-mechanism-for-sip-signaling)中 SIP 信號的容錯移轉機制區段。</span><span class="sxs-lookup"><span data-stu-id="fe429-340">See the section Failover mechanism for SIP signaling in [Plan for Direct Routing](direct-routing-plan.md#failover-mechanism-for-sip-signaling).</span></span>

## <a name="retry-after"></a><span data-ttu-id="fe429-341">Retry-在</span><span class="sxs-lookup"><span data-stu-id="fe429-341">Retry-After</span></span>

<span data-ttu-id="fe429-342">如果直接路由資料中心處於忙碌狀態，則服務可以在 SBC 中以一秒的間隔傳送一個 Retry 訊息。</span><span class="sxs-lookup"><span data-stu-id="fe429-342">If a Direct Routing datacenter is busy, the service can send a Retry-After message with a one-second interval to the SBC.</span></span> <span data-ttu-id="fe429-343">當 SBC 收到503訊息，並以重試標頭回應邀請之後，SBC 必須終止該連線，然後嘗試下一個可用的 Microsoft 資料中心。</span><span class="sxs-lookup"><span data-stu-id="fe429-343">When the SBC receives a 503 message with a Retry-After header in response to an INVITE, the SBC must terminate that connection and try the next available Microsoft datacenter.</span></span> 

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a><span data-ttu-id="fe429-344">ICE 重新開機：媒體旁路來電轉接到不支援媒體旁路的端點</span><span class="sxs-lookup"><span data-stu-id="fe429-344">ICE Restart: Media bypass call transferred to an endpoint that does not support media bypass</span></span>

<span data-ttu-id="fe429-345">SBC 必須支援以[RFC 5245 （章節9.1.1.1）](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)所述的 ICE 重新開機。</span><span class="sxs-lookup"><span data-stu-id="fe429-345">The SBC must support ICE restarts as described in [RFC 5245, section 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span>

<span data-ttu-id="fe429-346">[直接路由] 中的 [重新開機] 是根據 RFC 的下列幾個段落來實現：</span><span class="sxs-lookup"><span data-stu-id="fe429-346">The restart in Direct Routing is implemented according to the following paragraphs of the RFC:</span></span>

<span data-ttu-id="fe429-347">*若要重新開機 ICE，工程師必須在優惠中變更媒體資料流程的 ice 密碼和 ice ufrag。 請注意，您可以在一個優惠中使用會話階層屬性，但在後續優惠中提供相同的 ice 密碼或 ice ufrag 做為媒體層級屬性。 這不會變更密碼，只會變更其表示形式，也不會導致 ICE 重新開機。*</span><span class="sxs-lookup"><span data-stu-id="fe429-347">*To restart ICE, an agent MUST change both the ice-pwd and the ice-ufrag for the media stream in an offer.  Note that it is permissible to use a session-level attribute in one offer, but to provide the same ice-pwd or ice-ufrag as a media-level attribute in a subsequent offer.  This is not a change in password, just a change in its representation, and does not cause an ICE restart.*</span></span>

<span data-ttu-id="fe429-348">*代理程式會將此媒體資料流程的其他欄位設定為在這個媒體資料流程的初始提供（請參閱4.3 節）。 因此，候選人集合可能包含部分、無或所有舊版的候選人，而且可能會包含一組全新的候選項目，如4.1.1 一節所述。*</span><span class="sxs-lookup"><span data-stu-id="fe429-348">*An agent sets the rest of the fields in the SDP for this media stream as it would in an initial offer of this media stream (see Section 4.3).  Consequently, the set of candidates MAY include some, none, or all of the previous candidates for that stream and MAY include a totally new set of candidates gathered as described in Section 4.1.1.*</span></span>

<span data-ttu-id="fe429-349">如果通話是使用媒體略過建立，且通話是傳送到商務用 Skype 用戶端，則直接傳送必須插入媒體處理器，這是因為直接路由無法與使用媒體旁路的商務用 Skype 用戶端搭配使用。</span><span class="sxs-lookup"><span data-stu-id="fe429-349">If the call was initially established with media bypass, and the call is transferred to a Skype for Business client, Direct Routing needs to insert a Media Processor--this is because Direct Routing cannot be used with a Skype for Business client with media bypass.</span></span> <span data-ttu-id="fe429-350">直接傳送：透過變更冰密碼和冰 ufrag，並在 reinvite 中提供新的媒體候選人，以開始 ICE 重新開機程式。</span><span class="sxs-lookup"><span data-stu-id="fe429-350">Direct Routing starts the ICE restart process by  changing the ice-pwd and ice-ufrag and offering new media candidates in a reinvite.</span></span> 


