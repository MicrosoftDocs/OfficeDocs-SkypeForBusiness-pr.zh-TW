---
title: Lync Server 2013：規劃簡單 URL
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 224ca0315aff2618500182398cfe792c9626b883
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="1278e-102">在 Lync Server 2013 中規劃簡單 URL</span><span class="sxs-lookup"><span data-stu-id="1278e-102">Planning for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1278e-103">_**主題上次修改日期：** 2015-12-11_</span><span class="sxs-lookup"><span data-stu-id="1278e-103">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="1278e-104">簡單的 Url 可讓您更輕鬆地加入會議，並讓您的系統管理員更輕鬆地進入 Lync Server 管理工具。</span><span class="sxs-lookup"><span data-stu-id="1278e-104">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="1278e-105">Lync Server 支援三個簡單的 Url：</span><span class="sxs-lookup"><span data-stu-id="1278e-105">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="1278e-106">[**開會**] 是用來做為網站或組織中所有會議的基底 URL。</span><span class="sxs-lookup"><span data-stu-id="1278e-106">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="1278e-107">[符合簡單 URL] 的範例是https://meet.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="1278e-107">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="1278e-108">特定會議的 URL 可能是https://meet.contoso.com/[使用者*名稱*/7322994]。</span><span class="sxs-lookup"><span data-stu-id="1278e-108">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="1278e-109">使用 [符合簡單的 URL]，加入會議的連結就很容易理解，且易於溝通及發佈。</span><span class="sxs-lookup"><span data-stu-id="1278e-109">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="1278e-110">[**撥**入] 可讓您存取 [電話撥入式會議] 設定網頁。</span><span class="sxs-lookup"><span data-stu-id="1278e-110">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="1278e-111">此頁面會以其可用語言、指派的會議資訊（也就是不需要排程的會議）及會議中的 DTMF 控制來顯示會議撥入號碼，並支援個人身分識別號碼的管理（PIN）及指派的會議資訊。</span><span class="sxs-lookup"><span data-stu-id="1278e-111">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="1278e-112">[撥入] 簡單 URL 包含在所有會議邀請中，讓想要撥入會議的使用者可以存取必要的電話號碼和 PIN 資訊。</span><span class="sxs-lookup"><span data-stu-id="1278e-112">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="1278e-113">電話撥入式簡單 URL 的範例是https://dialin.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="1278e-113">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="1278e-114">[系統**管理**] 可讓您快速存取 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="1278e-114">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="1278e-115">從組織防火牆內的任何電腦，管理員都可以在瀏覽器中輸入 [管理員] 簡單 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="1278e-115">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="1278e-116">系統管理員簡易 URL 是貴組織的內部。</span><span class="sxs-lookup"><span data-stu-id="1278e-116">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="1278e-117">系統管理簡單 URL 的範例https://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1278e-117">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="1278e-118">簡單的 URL 範圍</span><span class="sxs-lookup"><span data-stu-id="1278e-118">Simple URL Scope</span></span>

<span data-ttu-id="1278e-119">您可以將簡單的 Url 設定為擁有全域範圍，或者您可以為組織中的每個中心網站指定不同的簡單 Url。</span><span class="sxs-lookup"><span data-stu-id="1278e-119">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="1278e-120">如果全域範圍簡單 URL 和網站範圍的簡單 URL 都已指定，則網站範圍簡單 URL 就會有優先順序。</span><span class="sxs-lookup"><span data-stu-id="1278e-120">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="1278e-121">在大部分的情況下，建議您只在全域層級設定簡單的 Url，讓使用者的 [符合簡單 URL] 不會隨著從某個網站移至另一個網站而變更。</span><span class="sxs-lookup"><span data-stu-id="1278e-121">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="1278e-122">例外情況是，組織必須在不同的網站上為撥入使用者使用不同的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="1278e-122">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="1278e-123">請注意，如果您在網站上將一個簡單的 URL （例如撥入式簡易 URL）設定為網站層級的簡單 URL，您也必須將該網站上的其他簡單 Url 設定為網站層級。</span><span class="sxs-lookup"><span data-stu-id="1278e-123">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1278e-124">如果您選擇使用網站範圍簡單的 Url，您的使用者將無法在不同網站中的前端池間移動，而不會讓這些使用者重新排定所有排程會議，因為網站之間的會議簡單 Url 是不一樣的。</span><span class="sxs-lookup"><span data-stu-id="1278e-124">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="1278e-125">這包括容錯移轉案例，其中，備份關係中的池位於不同的網站中。</span><span class="sxs-lookup"><span data-stu-id="1278e-125">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="1278e-126">如果您需要在網站設定簡單 Url 的網站之間進行容錯移轉，使用者將無法加入其會議，因為 URL 的範圍。</span><span class="sxs-lookup"><span data-stu-id="1278e-126">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="1278e-127">如需進一步資訊，請核<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">取 CsSimpleUrlConfiguration</A>。</span><span class="sxs-lookup"><span data-stu-id="1278e-127">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="1278e-128">您可以在拓撲產生器中設定全域簡單的 Url。</span><span class="sxs-lookup"><span data-stu-id="1278e-128">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="1278e-129">若要在網站層級設定簡單的 URL，您必須使用 CsSimpleURLConfiguration Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1278e-129">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="1278e-130">命名您的簡單 Url</span><span class="sxs-lookup"><span data-stu-id="1278e-130">Naming Your Simple URLs</span></span>

<span data-ttu-id="1278e-131">有三個建議選項可用於命名您的簡單 Url。</span><span class="sxs-lookup"><span data-stu-id="1278e-131">There are three recommended options for naming your simple URLs.</span></span> <span data-ttu-id="1278e-132">您選擇的選項會對您設定 DNS A 記錄的方式，以及支援簡易 Url 的憑證有何影響。</span><span class="sxs-lookup"><span data-stu-id="1278e-132">Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs.</span></span> <span data-ttu-id="1278e-133">在每個選項中，您必須針對組織中的每個 SIP 網域設定一個 [符合簡單 URL]。</span><span class="sxs-lookup"><span data-stu-id="1278e-133">In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="1278e-134">您永遠只需要在整個組織中使用一個簡單的 URL 進行撥入，另一個用於管理員，不論您有多少 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="1278e-134">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="1278e-135">如需有關必要 DNS A 記錄和憑證的詳細資料，請參閱規劃檔中的 lync [server 2013 簡單 url 的 DNS 需求](lync-server-2013-dns-requirements-for-simple-urls.md)和[lync server 2013 中的內部伺服器憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="1278e-135">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="1278e-136">在選項1中，您為每個簡單的 URL 建立新的 SIP 功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="1278e-136">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="1278e-137">如果您使用這個選項，則每個簡單的 URL 都需要一個單獨的 DNS A 記錄，而且每個符合簡單 URL 的名稱都必須在您的憑證中命名。</span><span class="sxs-lookup"><span data-stu-id="1278e-137">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="1278e-138">簡單 URL 命名選項1</span><span class="sxs-lookup"><span data-stu-id="1278e-138">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1278e-139"><strong>簡單的 URL</strong></span><span class="sxs-lookup"><span data-stu-id="1278e-139"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="1278e-140"><strong>範例</strong></span><span class="sxs-lookup"><span data-stu-id="1278e-140"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1278e-141">符合</span><span class="sxs-lookup"><span data-stu-id="1278e-141">Meet</span></span></p></td>
<td><p><span data-ttu-id="1278e-142">https://meet.contoso.comhttps://meet.fabrikam.com等等（針對貴組織中的每個 SIP 網域一個）</span><span class="sxs-lookup"><span data-stu-id="1278e-142">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1278e-143">撥入</span><span class="sxs-lookup"><span data-stu-id="1278e-143">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1278e-144">管理員</span><span class="sxs-lookup"><span data-stu-id="1278e-144">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1278e-145">有了選項2，簡單的 Url 就會以功能變數名稱 lync.contoso.com 為基礎。</span><span class="sxs-lookup"><span data-stu-id="1278e-145">With Option 2, simple URLs are based on the domain name lync.contoso.com.</span></span> <span data-ttu-id="1278e-146">因此，您只需要一個 DNS A 記錄，即可啟用所有三種類型的簡單 Url。</span><span class="sxs-lookup"><span data-stu-id="1278e-146">Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="1278e-147">這個 DNS A 記錄參照 lync.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="1278e-147">This DNS A record references lync.contoso.com.</span></span> <span data-ttu-id="1278e-148">此外，貴組織中的其他 SIP 網域，您仍然需要獨立的 DNS A 記錄。</span><span class="sxs-lookup"><span data-stu-id="1278e-148">Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="1278e-149">簡單 URL 命名選項2</span><span class="sxs-lookup"><span data-stu-id="1278e-149">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1278e-150"><strong>簡單的 URL</strong></span><span class="sxs-lookup"><span data-stu-id="1278e-150"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="1278e-151"><strong>範例</strong></span><span class="sxs-lookup"><span data-stu-id="1278e-151"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1278e-152">符合</span><span class="sxs-lookup"><span data-stu-id="1278e-152">Meet</span></span></p></td>
<td><p><span data-ttu-id="1278e-153">https://lync.contoso.com/Meethttps://lync.fabrikam.com/Meet等等（針對貴組織中的每個 SIP 網域一個）</span><span class="sxs-lookup"><span data-stu-id="1278e-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1278e-154">撥入</span><span class="sxs-lookup"><span data-stu-id="1278e-154">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1278e-155">管理員</span><span class="sxs-lookup"><span data-stu-id="1278e-155">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1278e-156">如果您有多個 SIP 網域，而您想要將它們放在不同的基本 Url 中，但想要將這些簡單 Url 的 DNS 記錄與證書需求降至最低，選項3是最實用的。</span><span class="sxs-lookup"><span data-stu-id="1278e-156">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="1278e-157">簡單 URL 命名選項3</span><span class="sxs-lookup"><span data-stu-id="1278e-157">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1278e-158"><strong>簡單的 URL</strong></span><span class="sxs-lookup"><span data-stu-id="1278e-158"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="1278e-159"><strong>範例</strong></span><span class="sxs-lookup"><span data-stu-id="1278e-159"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1278e-160">符合</span><span class="sxs-lookup"><span data-stu-id="1278e-160">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1278e-161">撥入</span><span class="sxs-lookup"><span data-stu-id="1278e-161">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1278e-162">管理員</span><span class="sxs-lookup"><span data-stu-id="1278e-162">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="1278e-163">簡單的 URL 命名與驗證規則</span><span class="sxs-lookup"><span data-stu-id="1278e-163">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="1278e-164">拓撲建立器和 Lync Server 管理命令介面 Cmdlet 會針對您的簡單 Url 強制執行數個驗證規則。</span><span class="sxs-lookup"><span data-stu-id="1278e-164">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="1278e-165">您必須將簡單的 Url 設定為 [符合] 或 [撥入]，但為 [管理員] 設定一個則是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="1278e-165">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="1278e-166">每個 SIP 網域都必須有一個單獨的 [符合簡單 URL]，但您只需要一個簡單的 URL，而且只有一個系統管理員就能為整個組織提供簡單的 URL。</span><span class="sxs-lookup"><span data-stu-id="1278e-166">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="1278e-167">貴組織中的每個簡單 URL 都必須有唯一的名稱，而且不能是另一個簡單 URL 的首碼（例如，您無法將 lync.contoso.com/Meet 設為您的 [您的內輟] 簡單 url，而 lync.contoso.com/Meet/Dialin 為您的撥入簡易 URL）。</span><span class="sxs-lookup"><span data-stu-id="1278e-167">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="1278e-168">簡單的 URL 名稱不能包含任何一個池的 FQDN，或任何埠資訊（例如， https://FQDN:88/meet不允許）。</span><span class="sxs-lookup"><span data-stu-id="1278e-168">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="1278e-169">所有簡單的 Url 都必須以 HTTPs://首碼開頭。</span><span class="sxs-lookup"><span data-stu-id="1278e-169">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="1278e-170">簡單的 Url 只能包含字母數位字元（即 a-z、A-Z、0-9 及句號（.）。</span><span class="sxs-lookup"><span data-stu-id="1278e-170">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.).</span></span> <span data-ttu-id="1278e-171">如果您使用其他字元，則簡單的 Url 可能無法如期運作。</span><span class="sxs-lookup"><span data-stu-id="1278e-171">If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="1278e-172">在部署之後變更簡單的 Url</span><span class="sxs-lookup"><span data-stu-id="1278e-172">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="1278e-173">如果您在初始部署之後變更簡單的 URL，您必須知道變更對您的 DNS 記錄及簡單 Url 的憑證有何影響。</span><span class="sxs-lookup"><span data-stu-id="1278e-173">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="1278e-174">如果簡單 URL 的基底發生變更，則您也必須變更 DNS 記錄和憑證。</span><span class="sxs-lookup"><span data-stu-id="1278e-174">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="1278e-175">例如，從https://lync.contoso.com/Meet lync.contoso.com https://meet.contoso.com變更為 MEET.CONTOSO.COM 的基底 URL，因此您必須將 DNS 記錄和憑證變更為參照 meet.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="1278e-175">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="1278e-176">如果您將簡單的 URL 改https://lync.contoso.com/Meet為https://lync.contoso.com/Meetings[寄件者]，則 LYNC.CONTOSO.COM 的基底 url 會保持不變，因此不需要變更 DNS 或憑證。</span><span class="sxs-lookup"><span data-stu-id="1278e-176">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="1278e-177">不過，每當您變更簡單的 URL 名稱時，您必須在每個控制器和前端伺服器上執行**Enable-CsComputer** ，以登錄變更。</span><span class="sxs-lookup"><span data-stu-id="1278e-177">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1278e-178">請參閱</span><span class="sxs-lookup"><span data-stu-id="1278e-178">See Also</span></span>


[<span data-ttu-id="1278e-179">Lync Server 2013 中簡單 URL 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="1278e-179">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

