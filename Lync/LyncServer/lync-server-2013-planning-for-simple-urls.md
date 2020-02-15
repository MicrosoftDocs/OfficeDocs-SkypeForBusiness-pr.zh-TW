---
title: Lync Server 2013： 規劃簡單 Url
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
ms.openlocfilehash: d36e730aeef637c12102fbf425c04235d72eb382
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="11cf6-102">規劃 Lync Server 2013 中的簡單 Url</span><span class="sxs-lookup"><span data-stu-id="11cf6-102">Planning for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11cf6-103">_**主題上次修改日期：** 2015年-12-11_</span><span class="sxs-lookup"><span data-stu-id="11cf6-103">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="11cf6-104">簡單 Url 加入會議更輕鬆地進行您的使用者，並讓 [Lync Server 系統管理工具更容易的取得您的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="11cf6-104">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="11cf6-105">Lync Server 支援三個簡單 Url:</span><span class="sxs-lookup"><span data-stu-id="11cf6-105">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="11cf6-106">**符合**用於做為基底 URL 的網站或組織中的所有會議。</span><span class="sxs-lookup"><span data-stu-id="11cf6-106">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="11cf6-107">範例的 Meet 簡單 URL 是https://meet.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="11cf6-107">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="11cf6-108">可能是特定會議 URL https://meet.contoso.com/ *username*/7322994。</span><span class="sxs-lookup"><span data-stu-id="11cf6-108">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="11cf6-109">Meet 簡單 URL，來加入會議的連結有可更容易理解，且更容易溝通與分送。</span><span class="sxs-lookup"><span data-stu-id="11cf6-109">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="11cf6-110">**撥號對應表中**啟用 [存取電話撥入式會議設定網頁。</span><span class="sxs-lookup"><span data-stu-id="11cf6-110">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="11cf6-111">此頁面會顯示會議撥入號碼與其可用的語言，指派會議資訊 (也就是不需要排定的會議)，在會議 DTMF 控制項，並支援管理個人識別號碼 （Pin 碼），並指派會議資訊。</span><span class="sxs-lookup"><span data-stu-id="11cf6-111">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="11cf6-112">撥入簡單 URL 包含所有會議邀請中，讓要撥入會議的使用者可以存取的必要的電話號碼及 pin 碼資訊。</span><span class="sxs-lookup"><span data-stu-id="11cf6-112">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="11cf6-113">撥入簡單 URL 的範例是https://dialin.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="11cf6-113">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="11cf6-114">**系統管理員**可讓您快速存取 Lync Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="11cf6-114">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="11cf6-115">從您的組織防火牆內的任何電腦，系統管理員可以在瀏覽器中輸入 Admin 簡單 URL 開啟 Lync Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="11cf6-115">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="11cf6-116">Admin 簡單 URL 是您組織內部。</span><span class="sxs-lookup"><span data-stu-id="11cf6-116">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="11cf6-117">Admin 簡單 URL 的範例https://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="11cf6-117">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="11cf6-118">簡單 URL 範圍</span><span class="sxs-lookup"><span data-stu-id="11cf6-118">Simple URL Scope</span></span>

<span data-ttu-id="11cf6-119">您可以設定進行全域範圍，簡單 Url，或您可以指定貴組織中的每個中央網站不同的簡單 Url。</span><span class="sxs-lookup"><span data-stu-id="11cf6-119">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="11cf6-120">如果指定全域範圍簡單 URL 及網站範圍簡單 URL，則網站範圍的簡單 URL 的優先順序。</span><span class="sxs-lookup"><span data-stu-id="11cf6-120">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="11cf6-121">在大多數情況下，我們建議您只在全域層級，設定簡單 Url，讓使用者的 Meet 簡單 URL 不會變更，如果他們從一個網站移至另一個。</span><span class="sxs-lookup"><span data-stu-id="11cf6-121">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="11cf6-122">例外狀況可能需要使用不同的電話號碼的電話撥入式使用者在不同站台的組織。</span><span class="sxs-lookup"><span data-stu-id="11cf6-122">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="11cf6-123">請注意，是否您是網站層級的簡單 URL 的網站在設定一個簡單 URL （例如 dial-in 簡單 URL)，您也必須設定其他簡單 Url，該網站也是網站層級。</span><span class="sxs-lookup"><span data-stu-id="11cf6-123">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="11cf6-124">如果您選擇使用網站範圍的簡單 Url，則您的使用者，將無法在不同的站台沒有為會議的簡單 Url 的不同站台之間所有其排程的會議： 這些使用者的前端集區之間移動。</span><span class="sxs-lookup"><span data-stu-id="11cf6-124">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="11cf6-125">這包括容錯移轉案例中的備份關係的集區，是在個別的網站。</span><span class="sxs-lookup"><span data-stu-id="11cf6-125">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="11cf6-126">當您要容錯移轉之間部署所在網站範圍設定簡單 Url 的網站，使用者將無法加入其會議因為 URL 的範圍。</span><span class="sxs-lookup"><span data-stu-id="11cf6-126">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="11cf6-127">如需詳細資訊，請檢查<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-cssimpleurlconfiguration</A>。</span><span class="sxs-lookup"><span data-stu-id="11cf6-127">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="11cf6-128">您可以在拓撲產生器設定通用簡單 Url。</span><span class="sxs-lookup"><span data-stu-id="11cf6-128">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="11cf6-129">若要在網站層級設定簡單 URL，您必須使用 Set CsSimpleURLConfiguration 指令程式。</span><span class="sxs-lookup"><span data-stu-id="11cf6-129">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="11cf6-130">簡單 Url 命名</span><span class="sxs-lookup"><span data-stu-id="11cf6-130">Naming Your Simple URLs</span></span>

<span data-ttu-id="11cf6-131">有三個簡單 Url 命名的建議的選項。</span><span class="sxs-lookup"><span data-stu-id="11cf6-131">There are three recommended options for naming your simple URLs.</span></span> <span data-ttu-id="11cf6-132">您選擇哪個選項具有影響您如何設定您的 DNS A 記錄和支援簡單 Url 的憑證。</span><span class="sxs-lookup"><span data-stu-id="11cf6-132">Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs.</span></span> <span data-ttu-id="11cf6-133">在每個選項，您必須在組織中設定每個 SIP 網域的一個 Meet 簡單 URL。</span><span class="sxs-lookup"><span data-stu-id="11cf6-133">In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="11cf6-134">您一律在整個組織的撥入與一個 Admin，無論您有多少的 SIP 網域需要只是一個簡單的 URL。</span><span class="sxs-lookup"><span data-stu-id="11cf6-134">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="11cf6-135">如需必要的 DNS A 記錄與憑證的詳細資訊，請參閱規劃文件中的[Lync Server 2013 中的簡單 Url 的 DNS 需求](lync-server-2013-dns-requirements-for-simple-urls.md)和[Lync Server 2013 中的內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="11cf6-135">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="11cf6-136">在選項 1 中，您可以建立新的 SIP 網域名稱的每個簡單 URL。</span><span class="sxs-lookup"><span data-stu-id="11cf6-136">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="11cf6-137">如果您使用此選項，您需要個別的 DNS A 記錄，針對每個簡單 URL，以及每個 Meet 簡單 URL 必須命名為在憑證中。</span><span class="sxs-lookup"><span data-stu-id="11cf6-137">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="11cf6-138">簡單 URL 命名選項 1</span><span class="sxs-lookup"><span data-stu-id="11cf6-138">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11cf6-139"><strong>簡單 URL</strong></span><span class="sxs-lookup"><span data-stu-id="11cf6-139"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="11cf6-140"><strong>範例</strong></span><span class="sxs-lookup"><span data-stu-id="11cf6-140"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11cf6-141">符合</span><span class="sxs-lookup"><span data-stu-id="11cf6-141">Meet</span></span></p></td>
<td><p><span data-ttu-id="11cf6-142">https://meet.contoso.comhttps://meet.fabrikam.com等等 （一個組織中每個 SIP 網域）</span><span class="sxs-lookup"><span data-stu-id="11cf6-142">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11cf6-143">電話撥入式</span><span class="sxs-lookup"><span data-stu-id="11cf6-143">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11cf6-144">系統管理</span><span class="sxs-lookup"><span data-stu-id="11cf6-144">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="11cf6-145">選項 2 使用網域名稱 lync.contoso.com 根據簡單 Url。</span><span class="sxs-lookup"><span data-stu-id="11cf6-145">With Option 2, simple URLs are based on the domain name lync.contoso.com.</span></span> <span data-ttu-id="11cf6-146">因此，您必須只能有一個 DNS A 記錄可讓所有三種簡單 Url。</span><span class="sxs-lookup"><span data-stu-id="11cf6-146">Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="11cf6-147">此 DNS A 記錄參照 lync.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="11cf6-147">This DNS A record references lync.contoso.com.</span></span> <span data-ttu-id="11cf6-148">此外，您仍然需要個別的 DNS A 記錄的其他 SIP 網域貴組織中。</span><span class="sxs-lookup"><span data-stu-id="11cf6-148">Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="11cf6-149">簡單 URL 命名選項 2</span><span class="sxs-lookup"><span data-stu-id="11cf6-149">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11cf6-150"><strong>簡單 URL</strong></span><span class="sxs-lookup"><span data-stu-id="11cf6-150"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="11cf6-151"><strong>範例</strong></span><span class="sxs-lookup"><span data-stu-id="11cf6-151"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11cf6-152">符合</span><span class="sxs-lookup"><span data-stu-id="11cf6-152">Meet</span></span></p></td>
<td><p><span data-ttu-id="11cf6-153">https://lync.contoso.com/Meethttps://lync.fabrikam.com/Meet等等 （一個組織中每個 SIP 網域）</span><span class="sxs-lookup"><span data-stu-id="11cf6-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11cf6-154">電話撥入式</span><span class="sxs-lookup"><span data-stu-id="11cf6-154">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11cf6-155">系統管理</span><span class="sxs-lookup"><span data-stu-id="11cf6-155">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="11cf6-156">選項 3 是最有用的如果您有許多 SIP 網域，且您想要有個別的 Meet 簡單 Url，但想要減少這些簡單 Url 的 DNS 記錄與憑證需求。</span><span class="sxs-lookup"><span data-stu-id="11cf6-156">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="11cf6-157">簡單 URL 命名選項 3</span><span class="sxs-lookup"><span data-stu-id="11cf6-157">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11cf6-158"><strong>簡單 URL</strong></span><span class="sxs-lookup"><span data-stu-id="11cf6-158"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="11cf6-159"><strong>範例</strong></span><span class="sxs-lookup"><span data-stu-id="11cf6-159"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11cf6-160">符合</span><span class="sxs-lookup"><span data-stu-id="11cf6-160">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11cf6-161">電話撥入式</span><span class="sxs-lookup"><span data-stu-id="11cf6-161">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11cf6-162">系統管理</span><span class="sxs-lookup"><span data-stu-id="11cf6-162">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="11cf6-163">簡單 URL 命名與驗證規則</span><span class="sxs-lookup"><span data-stu-id="11cf6-163">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="11cf6-164">拓撲產生器和 Lync Server 管理命令介面指令程式強化簡單 Url 幾個驗證規則。</span><span class="sxs-lookup"><span data-stu-id="11cf6-164">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="11cf6-165">您需要設定簡單 Url 的 Meet 和 Dialin，但設定另一個適用於系統管理員是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="11cf6-165">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="11cf6-166">每個 SIP 網域必須有個別的 Meet 簡單 URL，但必須只能有一個撥入簡單 URL 與一個 Admin 簡單 URL 為整個組織。</span><span class="sxs-lookup"><span data-stu-id="11cf6-166">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="11cf6-167">您組織中的每個簡單 URL 都必須有唯一名稱，且不能為另一個簡單 URL 的前置詞 （例如，您無法設定為將 Meet 簡單 URL 的 lync.contoso.com/Meet 和 lync.contoso.com/Meet/Dialin 做為您的撥入簡單 URL）。</span><span class="sxs-lookup"><span data-stu-id="11cf6-167">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="11cf6-168">簡單 URL 名稱不得包含任何集區，或任何連接埠資訊的 FQDN (例如，https://FQDN:88/meet不允許)。</span><span class="sxs-lookup"><span data-stu-id="11cf6-168">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="11cf6-169">所有簡單 Url 的開頭必須 https:// 前置詞。</span><span class="sxs-lookup"><span data-stu-id="11cf6-169">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="11cf6-170">簡單 Url 可以僅包含英數字元 （也就是 a 到 z、 A 到 Z、 0-9 和句點 （.）。</span><span class="sxs-lookup"><span data-stu-id="11cf6-170">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.).</span></span> <span data-ttu-id="11cf6-171">如果您使用其他字元，簡單 Url 可能無法如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="11cf6-171">If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="11cf6-172">部署後變更簡單 Url</span><span class="sxs-lookup"><span data-stu-id="11cf6-172">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="11cf6-173">如果您變更簡單 URL 初始部署之後，您必須知道如何變更會影響您的 DNS 記錄和憑證簡單 url。</span><span class="sxs-lookup"><span data-stu-id="11cf6-173">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="11cf6-174">如果變更之基底的簡單 URL，然後您必須變更 DNS 記錄及憑證也。</span><span class="sxs-lookup"><span data-stu-id="11cf6-174">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="11cf6-175">例如，從變更https://lync.contoso.com/Meet以https://meet.contoso.com基底 URL 從變成 lync.contoso.com meet.contoso.com，所以您需要變更 DNS 記錄和憑證，以參照 meet.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="11cf6-175">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="11cf6-176">如果您變更從簡單 URLhttps://lync.contoso.com/Meet以https://lync.contoso.com/Meetings、 lync.contoso.com 的基底 URL 保持不變，因此沒有 DNS 或需要憑證的變更。</span><span class="sxs-lookup"><span data-stu-id="11cf6-176">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="11cf6-177">每當您變更了簡單 URL 名稱，但是，您必須執行**Enable-cscomputer**上每個 Director 與前端伺服器，以登錄變更。</span><span class="sxs-lookup"><span data-stu-id="11cf6-177">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="11cf6-178">另請參閱</span><span class="sxs-lookup"><span data-stu-id="11cf6-178">See Also</span></span>


[<span data-ttu-id="11cf6-179">Lync Server 2013 中的簡單 Url 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="11cf6-179">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

