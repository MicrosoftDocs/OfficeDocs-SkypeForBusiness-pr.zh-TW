---
title: 商務用 Skype Server 中簡易 URLs 的 DNS 需求
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 摘要：在為商務用 Skype Server 實施 DNS 記錄之前，請參閱本主題中的簡易 URL 考慮。
ms.openlocfilehash: d1c4213e1fe28c6f42cd4fa14f48bc8ce9b7bdf1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834583"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a><span data-ttu-id="c7ca4-103">商務用 Skype Server 中簡易 URLs 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="c7ca4-103">DNS requirements for simple URLs in Skype for Business Server</span></span>

<span data-ttu-id="c7ca4-104">**摘要：** 在為商務用 Skype Server 實施 DNS 記錄之前，請參閱本主題中的簡易 URL 考慮。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-104">**Summary:** Review the Simple URL considerations in this topic before implementing DNS records for Skype for Business Server.</span></span>

<span data-ttu-id="c7ca4-105">簡單 URLs 使您的使用者加入會議變得更容易，並讓系統管理員更輕鬆取得商務用 Skype Server 的系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-105">Simple URLs make joining meetings easier for your users, and make getting to Skype for Business Server administrative tools easier for administrators.</span></span> <span data-ttu-id="c7ca4-106">簡易 URLs 會使用自己的網域，而不能比對任何您定義的 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-106">Simple URLs use their own domain, which must not match any of the SIP domains you define.</span></span> 

<span data-ttu-id="c7ca4-107">商務用 Skype 伺服器支援下列三個簡單 URLs：「開會」、「Dial-In」和「系統管理」。您必須設定「符合」和「Dial-In」的簡易 URLs，且 Admin 簡易 URL 是選用的。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-107">Skype for Business Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="c7ca4-108">需要用來支援簡單 URL 的網域名稱系統 (DNS) 記錄，視您定義這些簡單 URL 的方式而定，以及是否要支援簡單 URL 的災害復原。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-108">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span> 

## <a name="simple-url-scope"></a><span data-ttu-id="c7ca4-109">簡單 URL 範圍</span><span class="sxs-lookup"><span data-stu-id="c7ca4-109">Simple URL scope</span></span>

<span data-ttu-id="c7ca4-110">您可以將您的簡易 URLs 設定為具有全域範圍，也可以為組織中的每個中央網站指定不同的簡單 URLs。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-110">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="c7ca4-111">如果同時指定全域簡單 URL 和網站簡易 url，則網站簡易 URL 具有優先權。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-111">If both a global simple URL and a site simple URL are specified, the site simple URL has precedence.</span></span> 

<span data-ttu-id="c7ca4-112">在大多數情況下，我們建議您只在全域層級設定簡單 URLs，如此一來，如果使用者的符合簡易 URL 從一個網站移動到另一個網站，就不會變更。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-112">In most cases, we recommend that you set simple URLs only at the global level, so that a user's Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="c7ca4-113">例外狀況是組織必須針對不同網站上的撥入使用者使用不同的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-113">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="c7ca4-114">請注意，如果您設定一個簡易 URL (例如，將網站上的撥入簡易 URL) 設定為網站層級的簡易 URL，您也必須將該網站上的其他簡單 URLs 也設定為網站層級。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-114">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<span data-ttu-id="c7ca4-115">您可以在拓撲產生器中設定全域簡單的 URLs。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-115">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="c7ca4-116">若要在網站層級設定簡單 URL，請使用 Set-CsSimpleURLConfiguration Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-116">To set a simple URL at the site level, use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

<span data-ttu-id="c7ca4-117">定義簡單 URL 時，也需要在您的 DNS 設定中設定 A 和/或 AAAA 記錄。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-117">Defining a simple URL will also require setting an A and/or AAAA record in your DNS configuration.</span></span>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="c7ca4-118">簡單 URL 命名和驗證規則</span><span class="sxs-lookup"><span data-stu-id="c7ca4-118">Simple URL naming and validation rules</span></span>
<span data-ttu-id="c7ca4-119"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="c7ca4-119"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="c7ca4-120">拓撲產生器和商務用 Skype Server 管理命令介面指令程式會針對您的簡易 URLs 執行數種驗證規則。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-120">Topology Builder and the Skype for Business Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="c7ca4-121">您必須為符合和撥入設定簡單的 URLs，但為 Admin 設定一個是選用的。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-121">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="c7ca4-122">每個 SIP 網域都必須有個別的符合簡單 URL，但是您只需要一個撥入簡易 URL 和一個系統管理員簡易 URL 給整個組織。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-122">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="c7ca4-123">組織中的每個簡易 URL 都必須有唯一的名稱，而且不能是另一個簡單 URL 的首碼 (例如，您無法將 SfB2015.contoso.com/Meet 設定為您的 [SfB2015.contoso.com/Meet/Dialin] 簡單 url，而為您的撥入簡易 URL) 。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-123">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set SfB2015.contoso.com/Meet as your Meet simple URL and SfB2015.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="c7ca4-124">簡單 URL 名稱不能包含任何集區的 FQDN，或任何埠資訊 (例如， https://FQDN:88/meet 不允許) 。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-124">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="c7ca4-125">所有的簡單 URLs 都必須以 HTTPs://前置詞開頭。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-125">All simple URLs must start with the https:// prefix.</span></span> 

<span data-ttu-id="c7ca4-126">簡單 URLs 只能包含字母數位字元 (即 a-z、A-Z、0-9 和句點 (。 ) 。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-126">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.).</span></span> <span data-ttu-id="c7ca4-127">如果您使用其他字元，則簡單 URLs 可能無法如預期那樣運作。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-127">If you use other characters, the simple URLs might not work as expected.</span></span>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="c7ca4-128">在部署後變更簡單 URLs</span><span class="sxs-lookup"><span data-stu-id="c7ca4-128">Changing Simple URLs after deployment</span></span>
<span data-ttu-id="c7ca4-129"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="c7ca4-129"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="c7ca4-130">如果您在初始部署後變更簡單 URL，您必須注意變更會如何影響您的 DNS 記錄和憑證以取得簡易 URLs。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-130">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="c7ca4-131">如果簡單 URL 的基底變更，您也必須變更 DNS 記錄和憑證。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-131">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="c7ca4-132">例如，從 SfB2015.contoso.com 變更 https://SfB2015.contoso.com/Meet 為 https://meet.contoso.com meet.contoso.com 時，您必須變更 DNS 記錄和憑證，以參照 meet.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-132">For example, changing from https://SfB2015.contoso.com/Meet to https://meet.contoso.com changes the base URL from SfB2015.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="c7ca4-133">如果您已將簡易 URL 變更 https://SfB2015.contoso.com/Meet 為 https://SfB2015.contoso.com/Meetings ，SfB2015.contoso.com 的基底 url 會保持不變，因此不需要任何 DNS 或憑證變更。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-133">If you changed the simple URL from https://SfB2015.contoso.com/Meet to https://SfB2015.contoso.com/Meetings, the base URL of SfB2015.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="c7ca4-134">不過，每當您變更簡易 URL 名稱時，您必須在每個 Director 和前端伺服器上執行 **Enable-CsComputer** ，以註冊變更。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-134">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

## <a name="naming-examples-for-simple-urls"></a><span data-ttu-id="c7ca4-135">簡單 URLs 的命名範例</span><span class="sxs-lookup"><span data-stu-id="c7ca4-135">Naming examples for Simple URLs</span></span>
<span data-ttu-id="c7ca4-136"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="c7ca4-136"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="c7ca4-137">有三個建議選項可用於命名您的簡易 URLs。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-137">There are three recommended options for naming your simple URLs.</span></span> <span data-ttu-id="c7ca4-138">您選擇的哪個選項會影響您設定 DNS A 記錄的方式，以及支援簡易 URLs 的憑證。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-138">Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs.</span></span> <span data-ttu-id="c7ca4-139">在每個選項中，您必須為組織中的每個 SIP 網域設定一個符合簡易 URL 的功能。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-139">In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span> 

<span data-ttu-id="c7ca4-140">在整個組織中，您永遠只需要一個簡易 URL，以進行撥入，一個用於管理，不論您有多少 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-140">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="c7ca4-141">在選項1中，您可以為每個簡單 URL 建立新的 SIP 功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-141">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="c7ca4-142">如果您使用此選項，則每個簡單 URL 都必須有個別的 DNS A 記錄，而且每個符合簡易 URL 的憑證皆必須在您的憑證中命名。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-142">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

<span data-ttu-id="c7ca4-143">**簡單 URL 命名選項1**</span><span class="sxs-lookup"><span data-stu-id="c7ca4-143">**Simple URL Naming Option 1**</span></span>


| <span data-ttu-id="c7ca4-144">**簡單 URL**</span><span class="sxs-lookup"><span data-stu-id="c7ca4-144">**Simple URL**</span></span> <br/> | <span data-ttu-id="c7ca4-145">**範例**</span><span class="sxs-lookup"><span data-stu-id="c7ca4-145">**Example**</span></span> <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="c7ca4-146">滿足</span><span class="sxs-lookup"><span data-stu-id="c7ca4-146">Meet</span></span>  <br/>          | <span data-ttu-id="c7ca4-147">https://meet.contoso.com、等等 https://meet.fabrikam.com 等等 (組織中的每個 SIP 網域) </span><span class="sxs-lookup"><span data-stu-id="c7ca4-147">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span>  <br/> |
| <span data-ttu-id="c7ca4-148">撥入</span><span class="sxs-lookup"><span data-stu-id="c7ca4-148">Dial-in</span></span>  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| <span data-ttu-id="c7ca4-149">系統管理員</span><span class="sxs-lookup"><span data-stu-id="c7ca4-149">Admin</span></span>  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

<span data-ttu-id="c7ca4-150">使用選項2，簡單 URLs 是以功能變數名稱 SfB2015.contoso.com 為基礎。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-150">With Option 2, simple URLs are based on the domain name SfB2015.contoso.com.</span></span> <span data-ttu-id="c7ca4-151">因此，您只需要一個 DNS A 記錄，即可啟用所有三種類型的簡單 URLs。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-151">Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="c7ca4-152">此 DNS A 記錄參照 SfB2015.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-152">This DNS A record references SfB2015.contoso.com.</span></span> <span data-ttu-id="c7ca4-153">此外，您的組織中的其他 SIP 網域仍然需要不同的 DNS A 記錄。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-153">Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span> 

<span data-ttu-id="c7ca4-154">**簡單 URL 命名選項2**</span><span class="sxs-lookup"><span data-stu-id="c7ca4-154">**Simple URL Naming Option 2**</span></span>


| <span data-ttu-id="c7ca4-155">**簡單 URL**</span><span class="sxs-lookup"><span data-stu-id="c7ca4-155">**Simple URL**</span></span> <br/> | <span data-ttu-id="c7ca4-156">**範例**</span><span class="sxs-lookup"><span data-stu-id="c7ca4-156">**Example**</span></span> <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="c7ca4-157">滿足</span><span class="sxs-lookup"><span data-stu-id="c7ca4-157">Meet</span></span>  <br/>          | <span data-ttu-id="c7ca4-158">https://SfB2015.contoso.com/Meet、等等 https://SfB2015.fabrikam.com/Meet 等等 (組織中的每個 SIP 網域) </span><span class="sxs-lookup"><span data-stu-id="c7ca4-158">https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span>  <br/> |
| <span data-ttu-id="c7ca4-159">撥入</span><span class="sxs-lookup"><span data-stu-id="c7ca4-159">Dial-in</span></span>  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| <span data-ttu-id="c7ca4-160">系統管理員</span><span class="sxs-lookup"><span data-stu-id="c7ca4-160">Admin</span></span>  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

<span data-ttu-id="c7ca4-161">如果您有多個 SIP 網域，而您想要讓其具有個別的符合簡易 URLs，但想要將這些簡易 URLs 的 DNS 記錄和憑證需求降至最低，則選項3最為有用。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-161">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span> 

<span data-ttu-id="c7ca4-162">**簡單 URL 命名選項3**</span><span class="sxs-lookup"><span data-stu-id="c7ca4-162">**Simple URL Naming Option 3**</span></span>


| <span data-ttu-id="c7ca4-163">**簡單 URL**</span><span class="sxs-lookup"><span data-stu-id="c7ca4-163">**Simple URL**</span></span> <br/> | <span data-ttu-id="c7ca4-164">**範例**</span><span class="sxs-lookup"><span data-stu-id="c7ca4-164">**Example**</span></span> <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="c7ca4-165">滿足</span><span class="sxs-lookup"><span data-stu-id="c7ca4-165">Meet</span></span>  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| <span data-ttu-id="c7ca4-166">撥入</span><span class="sxs-lookup"><span data-stu-id="c7ca4-166">Dial-in</span></span>  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| <span data-ttu-id="c7ca4-167">系統管理員</span><span class="sxs-lookup"><span data-stu-id="c7ca4-167">Admin</span></span>  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="c7ca4-168">簡易 URLs 的嚴重損壞修復選項</span><span class="sxs-lookup"><span data-stu-id="c7ca4-168">Disaster Recovery option for simple URLs</span></span>
<span data-ttu-id="c7ca4-169"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="c7ca4-169"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="c7ca4-170">如果您有多個網站包含前端集區，而您的 DNS 提供者支援 GeoDNS，您可以設定您的 DNS 記錄以進行簡單的 URLs 以支援嚴重損壞修復，這樣一來，即使一部整個前端集區已停機，也能繼續簡易 URL 功能。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-170">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="c7ca4-171">此災害復原功能支援 Meet 及 Dial-In 簡單 URL。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-171">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="c7ca4-p113">如要如此設定，請建立兩個 GeoDNS 位址。每個位址都包含兩個 DNS A 或 CNAME 記錄，這兩個記錄會解析為針對災害復原目的而配對的兩個集區。一個 GeoDNS 位址用於內部存取，並解析為該兩個集區的內部 Web FQDN 或負載平衡器 IP 位址。另一個 GeoDNS 位址用於外部存取，並解析為該兩個集區的外部 Web FQDN 或負載平衡器 IP 位址。下列範例針對 Meet 簡單 URL，並使用集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-p113">To configure this, create two GeoDNS addresses. Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes. One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools. The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools. The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span> 

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

<span data-ttu-id="c7ca4-177">然後建立 CNAME 記錄，其中會將 Meet 簡單 URL (例如 meet.contoso.com) 解析為兩個 GeoDNS 位址。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-177">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

> [!NOTE]
> <span data-ttu-id="c7ca4-178">如果網路使用「髮夾」 (將所有簡單 URL 流量透過外部連結路由，包括來自組織內的流量)，則可僅設定外部 GeoDNS 位址，並將 Meet 簡單 URL 僅解析為該外部位址。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-178">If your network uses hairpinning (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>

<span data-ttu-id="c7ca4-179">使用此方法時，可設定每個 GeoDNS 位址使用循環配置資源方法來散發要求至兩個集區，或者主要連線至一個集區 (例如地理位置上較近的集區)，然後僅在連線失敗時才使用另一個集區。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-179">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span> 

<span data-ttu-id="c7ca4-180">針對 Dial-In 簡單 URL 也可以設定相同的組態。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-180">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="c7ca4-181">若要這麼做，請建立如先前範例中的其他記錄，並以  `dialin` `meet` DNS 記錄取代。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-181">To do so, create additional records like those in the previous example, substituting  `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="c7ca4-182">針對 Admin 簡單 URL，請使用本節中先前列出的三個選項。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-182">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="c7ca4-183">此組態一旦設定，就必須使用監控應用程式，設定 HTTP 監控以監看失敗。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-183">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="c7ca4-184">若要進行外部存取，請確定 HTTPS 取得 lyncdiscover。<sipdomain></span><span class="sxs-lookup"><span data-stu-id="c7ca4-184">For external access, monitor to make sure that HTTPS GET lyncdiscover.<sipdomain></span></span> <span data-ttu-id="c7ca4-185">兩個集區的外部 web FQDN 或負載平衡器 IP 位址要求都成功。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-185">requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="c7ca4-186">例如，下列要求不得包含任何 **ACCEPT** 標頭且必須傳回 **200 OK**。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-186">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="c7ca4-187">針對內部存取，則必須監控該兩個集區之內部 Web FQDN 或負載平衡器 IP 位址的連接埠 5061。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-187">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="c7ca4-188">如果偵測到任何連線失敗，這些集區的 VIP 必須關閉埠80、443及4443。</span><span class="sxs-lookup"><span data-stu-id="c7ca4-188">If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 4443.</span></span>


