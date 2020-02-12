---
title: 商務用 Skype Server 中簡單 Url 的 DNS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 摘要：在針對商務用 Skype Server 執行 DNS 記錄之前，請先查看本主題中的簡單 URL 考慮。
ms.openlocfilehash: 3296e3678d1d38f021b792a2362f61de66796d0f
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888472"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a><span data-ttu-id="889de-103">商務用 Skype Server 中簡單 Url 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="889de-103">DNS requirements for simple URLs in Skype for Business Server</span></span>

<span data-ttu-id="889de-104">**摘要：** 在針對商務用 Skype 伺服器執行 DNS 記錄之前，請先查看本主題中的簡單 URL 考慮。</span><span class="sxs-lookup"><span data-stu-id="889de-104">**Summary:** Review the Simple URL considerations in this topic before implementing DNS records for Skype for Business Server.</span></span>

<span data-ttu-id="889de-105">簡單的 Url 能讓您的使用者更容易加入會議，以及讓系統管理員更容易取得商務用 Skype Server 管理工具。</span><span class="sxs-lookup"><span data-stu-id="889de-105">Simple URLs make joining meetings easier for your users, and make getting to Skype for Business Server administrative tools easier for administrators.</span></span> <span data-ttu-id="889de-106">簡單的 Url 會使用自己的網域，而不應與您定義的任何 SIP 網域相符。</span><span class="sxs-lookup"><span data-stu-id="889de-106">Simple URLs use their own domain, which must not match any of the SIP domains you define.</span></span> 

<span data-ttu-id="889de-107">商務用 Skype 伺服器支援下列三個簡單的 Url： [開會]、[撥入] 和 [管理員]。您必須設定適用于 [開會及撥入] 的簡單 Url，且 [管理員簡易 URL] 是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="889de-107">Skype for Business Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="889de-108">您需要支援簡單 Url 的網域名稱系統（DNS）記錄，取決於您如何定義這些簡單的 Url，以及是否要支援簡單 Url 的災害復原。</span><span class="sxs-lookup"><span data-stu-id="889de-108">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span> 

## <a name="simple-url-scope"></a><span data-ttu-id="889de-109">簡單的 URL 範圍</span><span class="sxs-lookup"><span data-stu-id="889de-109">Simple URL scope</span></span>

<span data-ttu-id="889de-110">您可以將簡單的 Url 設定為擁有全域範圍，或者您可以為組織中的每個中心網站指定不同的簡單 Url。</span><span class="sxs-lookup"><span data-stu-id="889de-110">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="889de-111">如果同時指定全域簡單 URL 和網站簡單的 URL，則網站簡單的 URL 具有優先權。</span><span class="sxs-lookup"><span data-stu-id="889de-111">If both a global simple URL and a site simple URL are specified, the site simple URL has precedence.</span></span> 

<span data-ttu-id="889de-112">在大部分的情況下，建議您只在全域層級設定簡單的 Url，讓使用者的 [符合簡單 URL] 不會隨著從某個網站移至另一個網站而變更。</span><span class="sxs-lookup"><span data-stu-id="889de-112">In most cases, we recommend that you set simple URLs only at the global level, so that a user's Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="889de-113">例外情況是，組織必須在不同的網站上為撥入使用者使用不同的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="889de-113">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="889de-114">請注意，如果您在網站上將一個簡單的 URL （例如撥入式簡易 URL）設定為網站層級的簡單 URL，您也必須將該網站上的其他簡單 Url 設定為網站層級。</span><span class="sxs-lookup"><span data-stu-id="889de-114">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<span data-ttu-id="889de-115">您可以在拓撲產生器中設定全域簡單的 Url。</span><span class="sxs-lookup"><span data-stu-id="889de-115">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="889de-116">若要在網站層級設定簡單的 URL，請使用 CsSimpleURLConfiguration Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="889de-116">To set a simple URL at the site level, use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

<span data-ttu-id="889de-117">定義簡單的 URL 時，也必須在您的 DNS 設定中設定 A 和/或 AAAA 記錄。</span><span class="sxs-lookup"><span data-stu-id="889de-117">Defining a simple URL will also require setting an A and/or AAAA record in your DNS configuration.</span></span>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="889de-118">簡單的 URL 命名與驗證規則</span><span class="sxs-lookup"><span data-stu-id="889de-118">Simple URL naming and validation rules</span></span>
<span data-ttu-id="889de-119"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="889de-119"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="889de-120">[拓撲建立器] 和 [商務用 Skype 伺服器管理 Shell] Cmdlet 會針對您的簡單 Url 強制執行數個驗證規則。</span><span class="sxs-lookup"><span data-stu-id="889de-120">Topology Builder and the Skype for Business Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="889de-121">您必須將簡單的 Url 設定為 [符合] 或 [撥入]，但為 [管理員] 設定一個則是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="889de-121">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="889de-122">每個 SIP 網域都必須有一個單獨的 [符合簡單 URL]，但您只需要一個簡單的 URL，而且只有一個系統管理員就能為整個組織提供簡單的 URL。</span><span class="sxs-lookup"><span data-stu-id="889de-122">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="889de-123">貴組織中的每個簡單 URL 都必須有唯一的名稱，而且不能是另一個簡單 URL 的首碼（例如，您無法將 SfB2015.contoso.com/Meet 設為您的 [您的內輟] 簡單 url，而 SfB2015.contoso.com/Meet/Dialin 為您的撥入簡易 URL）。</span><span class="sxs-lookup"><span data-stu-id="889de-123">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set SfB2015.contoso.com/Meet as your Meet simple URL and SfB2015.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="889de-124">簡單的 URL 名稱不能包含任何一個池的 FQDN，或任何埠資訊（例如， https://FQDN:88/meet不允許）。</span><span class="sxs-lookup"><span data-stu-id="889de-124">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="889de-125">所有簡單的 Url 都必須以 HTTPs://首碼開頭。</span><span class="sxs-lookup"><span data-stu-id="889de-125">All simple URLs must start with the https:// prefix.</span></span> 

<span data-ttu-id="889de-126">簡單的 Url 只能包含字母數位字元（即 a-z、A-Z、0-9 及句號（.）。</span><span class="sxs-lookup"><span data-stu-id="889de-126">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.).</span></span> <span data-ttu-id="889de-127">如果您使用其他字元，則簡單的 Url 可能無法如期運作。</span><span class="sxs-lookup"><span data-stu-id="889de-127">If you use other characters, the simple URLs might not work as expected.</span></span>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="889de-128">在部署之後變更簡單的 Url</span><span class="sxs-lookup"><span data-stu-id="889de-128">Changing Simple URLs after deployment</span></span>
<span data-ttu-id="889de-129"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="889de-129"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="889de-130">如果您在初始部署之後變更簡單的 URL，您必須知道變更對您的 DNS 記錄及簡單 Url 的憑證有何影響。</span><span class="sxs-lookup"><span data-stu-id="889de-130">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="889de-131">如果簡單 URL 的基底發生變更，則您也必須變更 DNS 記錄和憑證。</span><span class="sxs-lookup"><span data-stu-id="889de-131">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="889de-132">例如，從https://SfB2015.contoso.com/Meet SfB2015.contoso.com https://meet.contoso.com變更為 MEET.CONTOSO.COM 的基底 URL，因此您必須將 DNS 記錄和憑證變更為參照 meet.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="889de-132">For example, changing from https://SfB2015.contoso.com/Meet to https://meet.contoso.com changes the base URL from SfB2015.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="889de-133">如果您將簡單的 URL 改https://SfB2015.contoso.com/Meet為https://SfB2015.contoso.com/Meetings[寄件者]，則 SFB2015.CONTOSO.COM 的基底 url 會保持不變，因此不需要變更 DNS 或憑證。</span><span class="sxs-lookup"><span data-stu-id="889de-133">If you changed the simple URL from https://SfB2015.contoso.com/Meet to https://SfB2015.contoso.com/Meetings, the base URL of SfB2015.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="889de-134">不過，每當您變更簡單的 URL 名稱時，您必須在每個控制器和前端伺服器上執行**Enable-CsComputer** ，以登錄變更。</span><span class="sxs-lookup"><span data-stu-id="889de-134">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

## <a name="naming-examples-for-simple-urls"></a><span data-ttu-id="889de-135">簡單 Url 的命名範例</span><span class="sxs-lookup"><span data-stu-id="889de-135">Naming examples for Simple URLs</span></span>
<span data-ttu-id="889de-136"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="889de-136"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="889de-137">有三個建議選項可用於命名您的簡單 Url。</span><span class="sxs-lookup"><span data-stu-id="889de-137">There are three recommended options for naming your simple URLs.</span></span> <span data-ttu-id="889de-138">您選擇的選項會對您設定 DNS A 記錄的方式，以及支援簡易 Url 的憑證有何影響。</span><span class="sxs-lookup"><span data-stu-id="889de-138">Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs.</span></span> <span data-ttu-id="889de-139">在每個選項中，您必須針對組織中的每個 SIP 網域設定一個 [符合簡單 URL]。</span><span class="sxs-lookup"><span data-stu-id="889de-139">In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span> 

<span data-ttu-id="889de-140">您永遠只需要在整個組織中使用一個簡單的 URL 進行撥入，另一個用於管理員，不論您有多少 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="889de-140">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="889de-141">在選項1中，您為每個簡單的 URL 建立新的 SIP 功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="889de-141">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="889de-142">如果您使用這個選項，則每個簡單的 URL 都需要一個單獨的 DNS A 記錄，而且每個符合簡單 URL 的名稱都必須在您的憑證中命名。</span><span class="sxs-lookup"><span data-stu-id="889de-142">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

<span data-ttu-id="889de-143">**簡單 URL 命名選項1**</span><span class="sxs-lookup"><span data-stu-id="889de-143">**Simple URL Naming Option 1**</span></span>


| <span data-ttu-id="889de-144">**簡單的 URL**</span><span class="sxs-lookup"><span data-stu-id="889de-144">**Simple URL**</span></span> <br/> | <span data-ttu-id="889de-145">**範例**</span><span class="sxs-lookup"><span data-stu-id="889de-145">**Example**</span></span> <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="889de-146">符合</span><span class="sxs-lookup"><span data-stu-id="889de-146">Meet</span></span>  <br/>          | <span data-ttu-id="889de-147">https://meet.contoso.comhttps://meet.fabrikam.com等等（針對貴組織中的每個 SIP 網域一個）</span><span class="sxs-lookup"><span data-stu-id="889de-147">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span>  <br/> |
| <span data-ttu-id="889de-148">撥入</span><span class="sxs-lookup"><span data-stu-id="889de-148">Dial-in</span></span>  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| <span data-ttu-id="889de-149">管理員</span><span class="sxs-lookup"><span data-stu-id="889de-149">Admin</span></span>  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

<span data-ttu-id="889de-150">有了選項2，簡單的 Url 就會以功能變數名稱 SfB2015.contoso.com 為基礎。</span><span class="sxs-lookup"><span data-stu-id="889de-150">With Option 2, simple URLs are based on the domain name SfB2015.contoso.com.</span></span> <span data-ttu-id="889de-151">因此，您只需要一個 DNS A 記錄，即可啟用所有三種類型的簡單 Url。</span><span class="sxs-lookup"><span data-stu-id="889de-151">Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="889de-152">這個 DNS A 記錄參照 SfB2015.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="889de-152">This DNS A record references SfB2015.contoso.com.</span></span> <span data-ttu-id="889de-153">此外，貴組織中的其他 SIP 網域，您仍然需要獨立的 DNS A 記錄。</span><span class="sxs-lookup"><span data-stu-id="889de-153">Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span> 

<span data-ttu-id="889de-154">**簡單 URL 命名選項2**</span><span class="sxs-lookup"><span data-stu-id="889de-154">**Simple URL Naming Option 2**</span></span>


| <span data-ttu-id="889de-155">**簡單的 URL**</span><span class="sxs-lookup"><span data-stu-id="889de-155">**Simple URL**</span></span> <br/> | <span data-ttu-id="889de-156">**範例**</span><span class="sxs-lookup"><span data-stu-id="889de-156">**Example**</span></span> <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="889de-157">符合</span><span class="sxs-lookup"><span data-stu-id="889de-157">Meet</span></span>  <br/>          | <span data-ttu-id="889de-158">https://SfB2015.contoso.com/Meethttps://SfB2015.fabrikam.com/Meet等等（針對貴組織中的每個 SIP 網域一個）</span><span class="sxs-lookup"><span data-stu-id="889de-158">https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span>  <br/> |
| <span data-ttu-id="889de-159">撥入</span><span class="sxs-lookup"><span data-stu-id="889de-159">Dial-in</span></span>  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| <span data-ttu-id="889de-160">管理員</span><span class="sxs-lookup"><span data-stu-id="889de-160">Admin</span></span>  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

<span data-ttu-id="889de-161">如果您有多個 SIP 網域，而您想要將它們放在不同的基本 Url 中，但想要將這些簡單 Url 的 DNS 記錄與證書需求降至最低，選項3是最實用的。</span><span class="sxs-lookup"><span data-stu-id="889de-161">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span> 

<span data-ttu-id="889de-162">**簡單 URL 命名選項3**</span><span class="sxs-lookup"><span data-stu-id="889de-162">**Simple URL Naming Option 3**</span></span>


| <span data-ttu-id="889de-163">**簡單的 URL**</span><span class="sxs-lookup"><span data-stu-id="889de-163">**Simple URL**</span></span> <br/> | <span data-ttu-id="889de-164">**範例**</span><span class="sxs-lookup"><span data-stu-id="889de-164">**Example**</span></span> <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="889de-165">符合</span><span class="sxs-lookup"><span data-stu-id="889de-165">Meet</span></span>  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| <span data-ttu-id="889de-166">撥入</span><span class="sxs-lookup"><span data-stu-id="889de-166">Dial-in</span></span>  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| <span data-ttu-id="889de-167">管理員</span><span class="sxs-lookup"><span data-stu-id="889de-167">Admin</span></span>  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="889de-168">簡單 Url 的災害復原選項</span><span class="sxs-lookup"><span data-stu-id="889de-168">Disaster Recovery option for simple URLs</span></span>
<span data-ttu-id="889de-169"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="889de-169"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="889de-170">如果您有多個包含前端池的網站，而且您的 DNS 提供者支援 GeoDNS，您可以針對簡單的 Url 設定您的 DNS 記錄，以支援災害復原，因此即使一個完整的前端池已停止，簡單的 URL 功能仍會繼續。</span><span class="sxs-lookup"><span data-stu-id="889de-170">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="889de-171">這個災害復原功能支援 [開會] 和 [撥入] 簡單的 Url。</span><span class="sxs-lookup"><span data-stu-id="889de-171">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="889de-172">若要設定這一點，請建立兩個 GeoDNS 位址。</span><span class="sxs-lookup"><span data-stu-id="889de-172">To configure this, create two GeoDNS addresses.</span></span> <span data-ttu-id="889de-173">每個位址都有兩個 DNS A 或 CNAME 記錄，可解析成成對組成的兩個池以進行災害復原。</span><span class="sxs-lookup"><span data-stu-id="889de-173">Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes.</span></span> <span data-ttu-id="889de-174">一個 GeoDNS 位址用於內部存取，並解析為兩個池的內部網路 FQDN 或負載平衡器 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="889de-174">One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="889de-175">其他 GeoDNS 位址是用於外部存取，並解析為兩個池的外部 web FQDN 或負載平衡器 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="889de-175">The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="889de-176">下列是使用池之 Fqdn 的 [符合簡單 URL] 的範例。</span><span class="sxs-lookup"><span data-stu-id="889de-176">The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span> 

```console
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```console
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

<span data-ttu-id="889de-177">然後建立可將您的符合簡單 URL （例如 meet.contoso.com）解析成兩個 GeoDNS 位址的 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="889de-177">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

> [!NOTE]
> <span data-ttu-id="889de-178">如果您的網路使用的是 hairpinning （透過外部連結路由所有簡單的 URL 流量，包括來自貴組織內部的流量），則您只需設定外部 GeoDNS 位址，並將您的 [符合簡單 URL] 解析為僅限外部地址。</span><span class="sxs-lookup"><span data-stu-id="889de-178">If your network uses hairpinning (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>

<span data-ttu-id="889de-179">當您使用此方法時，您可以設定每個 GeoDNS 位址，以使用迴圈複用方法將要求發佈到兩個池，或主要連線到一個池（例如位於地理位置較近的池中），並使用其他池（例如連接失敗。</span><span class="sxs-lookup"><span data-stu-id="889de-179">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span> 

<span data-ttu-id="889de-180">您可以針對撥入簡易 URL 設定相同的配置。</span><span class="sxs-lookup"><span data-stu-id="889de-180">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="889de-181">若要這樣做，請建立如先前範例中的其他記錄， `dialin`並`meet`在 DNS 記錄中取代。</span><span class="sxs-lookup"><span data-stu-id="889de-181">To do so, create additional records like those in the previous example, substituting  `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="889de-182">針對系統管理員簡易 URL，請使用本節前面所列的三個選項之一。</span><span class="sxs-lookup"><span data-stu-id="889de-182">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="889de-183">設定此設定之後，您必須使用監視應用程式來設定 HTTP 監視來監視失敗。</span><span class="sxs-lookup"><span data-stu-id="889de-183">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="889de-184">如果是外部存取，請在 [顯示器] 上確認 HTTPS： lyncdiscover。<sipdomain></span><span class="sxs-lookup"><span data-stu-id="889de-184">For external access, monitor to make sure that HTTPS GET lyncdiscover.<sipdomain></span></span> <span data-ttu-id="889de-185">兩個池的外部 web FQDN 或負載平衡器 IP 位址要求成功。</span><span class="sxs-lookup"><span data-stu-id="889de-185">requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="889de-186">例如，下列要求不能包含任何**ACCEPT**標頭，而且必須傳回**200 OK**。</span><span class="sxs-lookup"><span data-stu-id="889de-186">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="889de-187">針對內部存取，您必須在兩個池的內部網路 FQDN 或負載平衡器 IP 位址上，監視埠5061。</span><span class="sxs-lookup"><span data-stu-id="889de-187">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="889de-188">如果偵測到任何連線失敗，這些池的 VIP 必須關閉埠80、443和4443。</span><span class="sxs-lookup"><span data-stu-id="889de-188">If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 4443.</span></span>


