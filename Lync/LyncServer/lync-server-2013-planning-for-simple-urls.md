---
title: Lync Server 2013：規劃簡易 URLs
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
ms.openlocfilehash: f7d5ae03267b266b1ef2abbacc2e3fce06e034ec
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513520"
---
# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="5510a-102">在 Lync Server 2013 中規劃簡易 URLs</span><span class="sxs-lookup"><span data-stu-id="5510a-102">Planning for simple URLs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5510a-103">_**主題上次修改日期：** 2015-12-11_</span><span class="sxs-lookup"><span data-stu-id="5510a-103">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="5510a-104">簡單 URLs 使您的使用者加入會議變得更容易，並讓系統管理員更輕鬆取得 Lync Server 系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="5510a-104">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="5510a-105">Lync Server 支援三種簡單的 URLs：</span><span class="sxs-lookup"><span data-stu-id="5510a-105">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="5510a-106">「**開會**」是網站或組織中所有會議的基礎 URL。</span><span class="sxs-lookup"><span data-stu-id="5510a-106">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="5510a-107">符合簡易 URL 的範例是 https://meet.contoso.com 。</span><span class="sxs-lookup"><span data-stu-id="5510a-107">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="5510a-108">特定會議的 URL 可能是 https://meet.contoso.com/ *username*/7322994。</span><span class="sxs-lookup"><span data-stu-id="5510a-108">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="5510a-109">使用符合簡易 URL 時，加入會議的連結就很容易理解，而且易於進行通訊和發佈。</span><span class="sxs-lookup"><span data-stu-id="5510a-109">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="5510a-110">**撥入** 功能可讓您存取電話撥入式會議設定網頁。</span><span class="sxs-lookup"><span data-stu-id="5510a-110">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="5510a-111">此頁面會以其可用語言、指派會議資訊 (，也就是針對不需要排程) 的會議，以及在會議 DTMF 中的控制措施，以及支援管理個人識別碼) 的個人 (標識號，以及所指派的會議資訊。</span><span class="sxs-lookup"><span data-stu-id="5510a-111">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="5510a-112">撥入簡易 URL 會包含在所有會議邀請中，讓想要撥入會議的使用者可以存取必要的電話號碼和 PIN 碼資訊。</span><span class="sxs-lookup"><span data-stu-id="5510a-112">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="5510a-113">撥入式簡易 URL 的範例是 https://dialin.contoso.com 。</span><span class="sxs-lookup"><span data-stu-id="5510a-113">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="5510a-114">系統**管理員**可讓您快速存取 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="5510a-114">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="5510a-115">從組織防火牆內部的任何電腦，管理員都可以在瀏覽器中輸入系統管理員簡易 URL，以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="5510a-115">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="5510a-116">系統管理員簡易 URL 是您組織內部。</span><span class="sxs-lookup"><span data-stu-id="5510a-116">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="5510a-117">管理員簡易 URL 的範例是 https://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5510a-117">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="5510a-118">簡單 URL 範圍</span><span class="sxs-lookup"><span data-stu-id="5510a-118">Simple URL Scope</span></span>

<span data-ttu-id="5510a-119">您可以將您的簡易 URLs 設定為具有全域範圍，也可以為組織中的每個中央網站指定不同的簡單 URLs。</span><span class="sxs-lookup"><span data-stu-id="5510a-119">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="5510a-120">如果同時指定全域範圍簡易 url 和網站範圍簡易 URL，則網站範圍的簡單 URL 具有優先權。</span><span class="sxs-lookup"><span data-stu-id="5510a-120">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="5510a-121">在大多數情況下，我們建議您只在全域層級設定簡單 URLs，如此一來，如果使用者的符合簡易 URL 從一個網站移動到另一個網站，就不會變更。</span><span class="sxs-lookup"><span data-stu-id="5510a-121">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="5510a-122">例外狀況是組織必須針對不同網站上的撥入使用者使用不同的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="5510a-122">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="5510a-123">請注意，如果您設定一個簡易 URL (例如，將網站上的撥入簡易 URL) 設定為網站層級的簡易 URL，您也必須將該網站上的其他簡單 URLs 也設定為網站層級。</span><span class="sxs-lookup"><span data-stu-id="5510a-123">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5510a-124">如果您選擇使用網站範圍的簡易 URLs，您的使用者將無法在不同網站中的 Front-End 集區間移動，除非使用者重新設定所有排程的會議，而不是讓會議簡單 URLs 在網站之間有所不同。</span><span class="sxs-lookup"><span data-stu-id="5510a-124">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="5510a-125">這包括容錯移轉案例，其中集區的備份關係位於不同的網站。</span><span class="sxs-lookup"><span data-stu-id="5510a-125">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="5510a-126">當您需要在部署網站範圍簡易 URLs 的網站之間進行容錯移轉時，使用者將無法加入其會議，因為 URL 的範圍。</span><span class="sxs-lookup"><span data-stu-id="5510a-126">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="5510a-127">如需詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>。</span><span class="sxs-lookup"><span data-stu-id="5510a-127">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="5510a-128">您可以在拓撲產生器中設定全域簡單的 URLs。</span><span class="sxs-lookup"><span data-stu-id="5510a-128">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="5510a-129">若要在網站層級設定簡單 URL，您必須使用 Set-CsSimpleURLConfiguration Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5510a-129">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="5510a-130">命名您的簡易 URLs</span><span class="sxs-lookup"><span data-stu-id="5510a-130">Naming Your Simple URLs</span></span>

<span data-ttu-id="5510a-131">有三個建議選項可用於命名您的簡易 URLs。</span><span class="sxs-lookup"><span data-stu-id="5510a-131">There are three recommended options for naming your simple URLs.</span></span> <span data-ttu-id="5510a-132">您選擇的哪個選項會影響您設定 DNS A 記錄的方式，以及支援簡易 URLs 的憑證。</span><span class="sxs-lookup"><span data-stu-id="5510a-132">Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs.</span></span> <span data-ttu-id="5510a-133">在每個選項中，您必須為組織中的每個 SIP 網域設定一個符合簡易 URL 的功能。</span><span class="sxs-lookup"><span data-stu-id="5510a-133">In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="5510a-134">在整個組織中，您永遠只需要一個簡易 URL，以進行撥入，一個用於管理，不論您有多少 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="5510a-134">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="5510a-135">如需必要的 DNS A 記錄和憑證的詳細資訊，請參閱規劃檔中的 Lync server 2013 中的 [簡易 URLs 的 dns 需求](lync-server-2013-dns-requirements-for-simple-urls.md) 和 [lync server 2013 中的內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md) 。</span><span class="sxs-lookup"><span data-stu-id="5510a-135">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="5510a-136">在選項1中，您可以為每個簡單 URL 建立新的 SIP 功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="5510a-136">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="5510a-137">如果您使用此選項，則每個簡單 URL 都必須有個別的 DNS A 記錄，而且每個符合簡易 URL 的憑證皆必須在您的憑證中命名。</span><span class="sxs-lookup"><span data-stu-id="5510a-137">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="5510a-138">簡單 URL 命名選項1</span><span class="sxs-lookup"><span data-stu-id="5510a-138">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5510a-139"><strong>簡單 URL</strong></span><span class="sxs-lookup"><span data-stu-id="5510a-139"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="5510a-140"><strong>範例</strong></span><span class="sxs-lookup"><span data-stu-id="5510a-140"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5510a-141">滿足</span><span class="sxs-lookup"><span data-stu-id="5510a-141">Meet</span></span></p></td>
<td><p><span data-ttu-id="5510a-142">https://meet.contoso.com、等等 https://meet.fabrikam.com 等等 (組織中的每個 SIP 網域) </span><span class="sxs-lookup"><span data-stu-id="5510a-142">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5510a-143">撥入</span><span class="sxs-lookup"><span data-stu-id="5510a-143">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5510a-144">系統管理員</span><span class="sxs-lookup"><span data-stu-id="5510a-144">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5510a-145">使用選項2，簡單 URLs 是以功能變數名稱 lync.contoso.com 為基礎。</span><span class="sxs-lookup"><span data-stu-id="5510a-145">With Option 2, simple URLs are based on the domain name lync.contoso.com.</span></span> <span data-ttu-id="5510a-146">因此，您只需要一個 DNS A 記錄，即可啟用所有三種類型的簡單 URLs。</span><span class="sxs-lookup"><span data-stu-id="5510a-146">Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="5510a-147">此 DNS A 記錄參照 lync.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="5510a-147">This DNS A record references lync.contoso.com.</span></span> <span data-ttu-id="5510a-148">此外，您的組織中的其他 SIP 網域仍然需要不同的 DNS A 記錄。</span><span class="sxs-lookup"><span data-stu-id="5510a-148">Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="5510a-149">簡單 URL 命名選項2</span><span class="sxs-lookup"><span data-stu-id="5510a-149">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5510a-150"><strong>簡單 URL</strong></span><span class="sxs-lookup"><span data-stu-id="5510a-150"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="5510a-151"><strong>範例</strong></span><span class="sxs-lookup"><span data-stu-id="5510a-151"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5510a-152">滿足</span><span class="sxs-lookup"><span data-stu-id="5510a-152">Meet</span></span></p></td>
<td><p><span data-ttu-id="5510a-153">https://lync.contoso.com/Meet、等等 https://lync.fabrikam.com/Meet 等等 (組織中的每個 SIP 網域) </span><span class="sxs-lookup"><span data-stu-id="5510a-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5510a-154">撥入</span><span class="sxs-lookup"><span data-stu-id="5510a-154">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5510a-155">系統管理員</span><span class="sxs-lookup"><span data-stu-id="5510a-155">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5510a-156">如果您有多個 SIP 網域，而您想要讓其具有個別的符合簡易 URLs，但想要將這些簡易 URLs 的 DNS 記錄和憑證需求降至最低，則選項3最為有用。</span><span class="sxs-lookup"><span data-stu-id="5510a-156">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="5510a-157">簡單 URL 命名選項3</span><span class="sxs-lookup"><span data-stu-id="5510a-157">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5510a-158"><strong>簡單 URL</strong></span><span class="sxs-lookup"><span data-stu-id="5510a-158"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="5510a-159"><strong>範例</strong></span><span class="sxs-lookup"><span data-stu-id="5510a-159"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5510a-160">滿足</span><span class="sxs-lookup"><span data-stu-id="5510a-160">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5510a-161">撥入</span><span class="sxs-lookup"><span data-stu-id="5510a-161">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5510a-162">系統管理員</span><span class="sxs-lookup"><span data-stu-id="5510a-162">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="5510a-163">簡單 URL 命名和驗證規則</span><span class="sxs-lookup"><span data-stu-id="5510a-163">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="5510a-164">拓撲產生器和 Lync Server 管理命令介面指令程式會針對您的簡易 URLs 執行數種驗證規則。</span><span class="sxs-lookup"><span data-stu-id="5510a-164">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="5510a-165">您必須為符合和撥入設定簡單的 URLs，但為 Admin 設定一個是選用的。</span><span class="sxs-lookup"><span data-stu-id="5510a-165">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="5510a-166">每個 SIP 網域都必須有個別的符合簡單 URL，但是您只需要一個撥入簡易 URL 和一個系統管理員簡易 URL 給整個組織。</span><span class="sxs-lookup"><span data-stu-id="5510a-166">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="5510a-167">組織中的每個簡易 URL 都必須有唯一的名稱，而且不能是另一個簡單 URL 的首碼 (例如，您無法將 lync.contoso.com/Meet 設定為您的 [lync.contoso.com/Meet/Dialin] 簡單 url，而為您的撥入簡易 URL) 。</span><span class="sxs-lookup"><span data-stu-id="5510a-167">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="5510a-168">簡單 URL 名稱不能包含任何集區的 FQDN，或任何埠資訊 (例如， https://FQDN:88/meet 不允許) 。</span><span class="sxs-lookup"><span data-stu-id="5510a-168">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="5510a-169">所有的簡單 URLs 都必須以 HTTPs://前置詞開頭。</span><span class="sxs-lookup"><span data-stu-id="5510a-169">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="5510a-170">簡單 URLs 只能包含字母數位字元 (即 a-z、A-Z、0-9 和句點 (。 ) 。</span><span class="sxs-lookup"><span data-stu-id="5510a-170">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.).</span></span> <span data-ttu-id="5510a-171">如果您使用其他字元，則簡單 URLs 可能無法如預期那樣運作。</span><span class="sxs-lookup"><span data-stu-id="5510a-171">If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="5510a-172">在部署後變更簡單 URLs</span><span class="sxs-lookup"><span data-stu-id="5510a-172">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="5510a-173">如果您在初始部署後變更簡單 URL，您必須注意變更會如何影響您的 DNS 記錄和憑證以取得簡易 URLs。</span><span class="sxs-lookup"><span data-stu-id="5510a-173">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="5510a-174">如果簡單 URL 的基底變更，您也必須變更 DNS 記錄和憑證。</span><span class="sxs-lookup"><span data-stu-id="5510a-174">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="5510a-175">例如，從 lync.contoso.com 變更 https://lync.contoso.com/Meet 為 https://meet.contoso.com meet.contoso.com 時，您必須變更 DNS 記錄和憑證，以參照 meet.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="5510a-175">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="5510a-176">如果您已將簡易 URL 變更 https://lync.contoso.com/Meet 為 https://lync.contoso.com/Meetings ，lync.contoso.com 的基底 url 會保持不變，因此不需要任何 DNS 或憑證變更。</span><span class="sxs-lookup"><span data-stu-id="5510a-176">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="5510a-177">不過，每當您變更簡易 URL 名稱時，您必須在每個 Director 和前端伺服器上執行 **Enable-CsComputer** ，以註冊變更。</span><span class="sxs-lookup"><span data-stu-id="5510a-177">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5510a-178">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5510a-178">See Also</span></span>


[<span data-ttu-id="5510a-179">Lync Server 2013 中簡易 URLs 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="5510a-179">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

