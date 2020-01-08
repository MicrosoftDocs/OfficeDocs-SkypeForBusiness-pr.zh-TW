---
title: Lync Server 2013：內部伺服器的憑證需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4a3f1eb54321c6cac7548d282bd3cea31c3f24a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="e411f-102">Lync Server 2013 中內部伺服器的憑證需求</span><span class="sxs-lookup"><span data-stu-id="e411f-102">Certificate requirements for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e411f-103">_**主題上次修改日期：** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="e411f-103">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="e411f-104">執行 Lync Server 且需要證書的內部伺服器包括標準版 Server、Enterprise Edition 前端伺服器、中繼伺服器和控制器。</span><span class="sxs-lookup"><span data-stu-id="e411f-104">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="e411f-105">下表顯示這些伺服器的憑證需求。</span><span class="sxs-lookup"><span data-stu-id="e411f-105">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="e411f-106">您可以使用 [Lync Server 憑證] 嚮導來要求這些憑證。</span><span class="sxs-lookup"><span data-stu-id="e411f-106">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="e411f-107">對於與前端池、前端伺服器或控制器上的簡單 Url 相關聯的主體替換名稱，支援萬用字元憑證。</span><span class="sxs-lookup"><span data-stu-id="e411f-107">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="e411f-108">如需萬用字元憑證支援的詳細資訊，請參閱<A href="lync-server-2013-wildcard-certificate-support.md">Lync Server 2013 中的萬用字元支援</A>。</span><span class="sxs-lookup"><span data-stu-id="e411f-108">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="e411f-109">雖然建議內部伺服器使用內部企業憑證授權單位（CA），但是您也可以使用公用 CA。</span><span class="sxs-lookup"><span data-stu-id="e411f-109">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="e411f-110">若要在公用 Ca 清單中提供符合整合通訊（UC）憑證之特定需求的憑證，並與 Microsoft 合作，以確保他們能使用 Lync Server 認證嚮導，請參閱 Microsoft 知識庫929395、「Exchange Server 的整合通訊憑證合作夥伴及通訊伺服器」的文章[https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)。</span><span class="sxs-lookup"><span data-stu-id="e411f-110">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="e411f-111">與其他應用程式和伺服器通訊（例如 Exchange 2013）需要其他應用程式和產品所支援的憑證。</span><span class="sxs-lookup"><span data-stu-id="e411f-111">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="e411f-112">針對2013版本，Lync Server 2013 及其他 Microsoft Server 產品（包括 Exchange 2013 和 SharePoint Server）支援開啟授權（OAuth）通訊協定，以進行伺服器對伺服器驗證和授權。</span><span class="sxs-lookup"><span data-stu-id="e411f-112">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="e411f-113">如需詳細資訊，請參閱在部署檔或作業檔中[管理 Lync server 2013 中的伺服器到伺服器驗證（OAuth）和合作夥伴應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="e411f-113">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="e411f-114">針對執行 Windows 7 作業系統、windows server 2008 作業系統、Windows Server 2008 R2 作業系統、Windows Vista 作業系統及 Microsoft Lync Phone Edition 的用戶端連線，Lync Server 2013 包含支援（但不需要）使用 SHA-256 加密雜湊函數簽署的憑證。</span><span class="sxs-lookup"><span data-stu-id="e411f-114">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="e411f-115">若要使用 SHA-256 支援外部存取，外部憑證是由使用 SHA-256 的公用 CA 所頒發。</span><span class="sxs-lookup"><span data-stu-id="e411f-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="e411f-116">下表顯示前端池和標準版伺服器的伺服器角色的憑證需求。</span><span class="sxs-lookup"><span data-stu-id="e411f-116">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers.</span></span> <span data-ttu-id="e411f-117">所有這些都是標準的 web 伺服器憑證、私人金鑰、無法匯出的。</span><span class="sxs-lookup"><span data-stu-id="e411f-117">All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="e411f-118">請注意，當您使用 [憑證] 嚮導來要求證書時，系統會自動設定伺服器增強型金鑰用法（EKU）。</span><span class="sxs-lookup"><span data-stu-id="e411f-118">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e411f-119">每個證書的易記名稱在電腦存放區中都必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e411f-119">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e411f-120">如果您已在 DNS 中設定 sipinternal.contoso.com 或 sipexternal.contoso.com，您將需要在證書的受領人備用名稱中新增它們。</span><span class="sxs-lookup"><span data-stu-id="e411f-120">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="e411f-121">標準版伺服器的憑證</span><span class="sxs-lookup"><span data-stu-id="e411f-121">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="e411f-122">憑證</span><span class="sxs-lookup"><span data-stu-id="e411f-122">Certificate</span></span></th>
<th><span data-ttu-id="e411f-123">消費者名稱/通用名稱</span><span class="sxs-lookup"><span data-stu-id="e411f-123">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="e411f-124">消費者替換名稱</span><span class="sxs-lookup"><span data-stu-id="e411f-124">Subject alternative name</span></span></th>
<th><span data-ttu-id="e411f-125">範例</span><span class="sxs-lookup"><span data-stu-id="e411f-125">Example</span></span></th>
<th><span data-ttu-id="e411f-126">批註</span><span class="sxs-lookup"><span data-stu-id="e411f-126">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e411f-127">設置</span><span class="sxs-lookup"><span data-stu-id="e411f-127">Default</span></span></p></td>
<td><p><span data-ttu-id="e411f-128">池的完整功能變數名稱（FQDN）</span><span class="sxs-lookup"><span data-stu-id="e411f-128">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="e411f-129">[池] 和 [伺服器的 FQDN] 的 FQDN</span><span class="sxs-lookup"><span data-stu-id="e411f-129">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="e411f-130">如果您有多個 SIP 網域，且已啟用自動用戶端設定，證書嚮導會偵測並新增每個支援的 SIP 網域 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="e411f-130">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="e411f-131">如果此池是用戶端的自動登入伺服器，且在群組原則中需要嚴格的網域名稱系統（DNS）相符，您也需要 sipdomain （適用于您擁有的每個 SIP 網域）中的專案。</span><span class="sxs-lookup"><span data-stu-id="e411f-131">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="e411f-132">SN = se01;SAN = se01</span><span class="sxs-lookup"><span data-stu-id="e411f-132">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="e411f-133">如果此池是用戶端的自動登入伺服器，且在 [群組原則] 中需要嚴格的 DNS 相符，您也需要 SAN = sip. .com;SAN = sip. .com</span><span class="sxs-lookup"><span data-stu-id="e411f-133">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="e411f-134">在標準版伺服器上，伺服器 FQDN 與 [池 FQDN] 相同。</span><span class="sxs-lookup"><span data-stu-id="e411f-134">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="e411f-135">此嚮導會偵測您在安裝期間指定的任何 SIP 網域，並自動將其新增到 [使用中] 替換名稱。</span><span class="sxs-lookup"><span data-stu-id="e411f-135">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="e411f-136">您也可以使用此憑證進行伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="e411f-136">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e411f-137">網頁內部</span><span class="sxs-lookup"><span data-stu-id="e411f-137">Web internal</span></span></p></td>
<td><p><span data-ttu-id="e411f-138">伺服器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="e411f-138">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="e411f-139">下列各項：</span><span class="sxs-lookup"><span data-stu-id="e411f-139">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e411f-140">內部網路 FQDN （與伺服器的 FQDN 相同）</span><span class="sxs-lookup"><span data-stu-id="e411f-140">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="e411f-141">符合簡單的 Url</span><span class="sxs-lookup"><span data-stu-id="e411f-141">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="e411f-142">電話撥入式簡易 URL</span><span class="sxs-lookup"><span data-stu-id="e411f-142">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="e411f-143">系統管理簡易 URL</span><span class="sxs-lookup"><span data-stu-id="e411f-143">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="e411f-144">或者，簡單 Url 的萬用字元專案</span><span class="sxs-lookup"><span data-stu-id="e411f-144">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e411f-145">SN = se01;SAN = se01;SAN = 滿足 contoso. .com;SAN = 符合 fabrikam .com;SAN = 撥入. .com;SAN = admin. .com</span><span class="sxs-lookup"><span data-stu-id="e411f-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="e411f-146">使用萬用字元憑證：</span><span class="sxs-lookup"><span data-stu-id="e411f-146">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="e411f-147">SN = se01;SAN = se01;SAN = \*. .com</span><span class="sxs-lookup"><span data-stu-id="e411f-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e411f-148">您無法在拓撲建立器中覆寫內部網頁 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e411f-148">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="e411f-149">如果您有多個符合簡單的 Url，您必須將它們全部包含為 subject 替換名稱。</span><span class="sxs-lookup"><span data-stu-id="e411f-149">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="e411f-150">簡單的 URL 專案支援萬用字元專案。</span><span class="sxs-lookup"><span data-stu-id="e411f-150">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e411f-151">網頁外部</span><span class="sxs-lookup"><span data-stu-id="e411f-151">Web external</span></span></p></td>
<td><p><span data-ttu-id="e411f-152">伺服器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="e411f-152">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="e411f-153">下列各項：</span><span class="sxs-lookup"><span data-stu-id="e411f-153">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e411f-154">外部 web FQDN</span><span class="sxs-lookup"><span data-stu-id="e411f-154">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="e411f-155">電話撥入式簡易 URL</span><span class="sxs-lookup"><span data-stu-id="e411f-155">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="e411f-156">符合每個 SIP 網域的簡單 Url</span><span class="sxs-lookup"><span data-stu-id="e411f-156">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="e411f-157">或者，簡單 Url 的萬用字元專案</span><span class="sxs-lookup"><span data-stu-id="e411f-157">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e411f-158">SN = se01;SAN = webcon01;SAN = 滿足 contoso. .com;SAN = 符合 fabrikam .com;SAN = 撥入. .com</span><span class="sxs-lookup"><span data-stu-id="e411f-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="e411f-159">使用萬用字元憑證：</span><span class="sxs-lookup"><span data-stu-id="e411f-159">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="e411f-160">SN = se01;SAN = webcon01;SAN = \*. .com</span><span class="sxs-lookup"><span data-stu-id="e411f-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e411f-161">如果您有多個符合簡單的 Url，您必須將它們全部包含為 subject 替換名稱。</span><span class="sxs-lookup"><span data-stu-id="e411f-161">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="e411f-162">簡單的 URL 專案支援萬用字元專案。</span><span class="sxs-lookup"><span data-stu-id="e411f-162">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="e411f-163">前端伺服器在前端池中的憑證</span><span class="sxs-lookup"><span data-stu-id="e411f-163">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="e411f-164">憑證</span><span class="sxs-lookup"><span data-stu-id="e411f-164">Certificate</span></span></th>
<th><span data-ttu-id="e411f-165">消費者名稱/通用名稱</span><span class="sxs-lookup"><span data-stu-id="e411f-165">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="e411f-166">消費者替換名稱</span><span class="sxs-lookup"><span data-stu-id="e411f-166">Subject alternative name</span></span></th>
<th><span data-ttu-id="e411f-167">範例</span><span class="sxs-lookup"><span data-stu-id="e411f-167">Example</span></span></th>
<th><span data-ttu-id="e411f-168">批註</span><span class="sxs-lookup"><span data-stu-id="e411f-168">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e411f-169">設置</span><span class="sxs-lookup"><span data-stu-id="e411f-169">Default</span></span></p></td>
<td><p><span data-ttu-id="e411f-170">池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="e411f-170">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="e411f-171">伺服器的 [pool] 和 [FQDN]。</span><span class="sxs-lookup"><span data-stu-id="e411f-171">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="e411f-172">如果您有多個 SIP 網域，且已啟用自動用戶端設定，證書嚮導會偵測並新增每個支援的 SIP 網域 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="e411f-172">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="e411f-173">如果此池是用戶端的自動登入伺服器，且在 [群組原則] 中需要嚴格的 DNS 相符，您也需要 sipdomain （針對您擁有的每個 SIP 網域）輸入的專案。</span><span class="sxs-lookup"><span data-stu-id="e411f-173">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="e411f-174">SN = eepool;SAN = eepool;SAN = ee01</span><span class="sxs-lookup"><span data-stu-id="e411f-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="e411f-175">如果此池是用戶端的自動登入伺服器，且在 [群組原則] 中需要嚴格的 DNS 相符，您也需要 SAN = sip. .com;SAN = sip. .com</span><span class="sxs-lookup"><span data-stu-id="e411f-175">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="e411f-176">此嚮導會偵測您在安裝期間指定的任何 SIP 網域，並自動將其新增到 [使用中] 替換名稱。</span><span class="sxs-lookup"><span data-stu-id="e411f-176">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="e411f-177">您也可以使用此憑證進行伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="e411f-177">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e411f-178">網頁內部</span><span class="sxs-lookup"><span data-stu-id="e411f-178">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="e411f-179">池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="e411f-179">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="e411f-180">下列各項：</span><span class="sxs-lookup"><span data-stu-id="e411f-180">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e411f-181">內部網路 FQDN （與伺服器的 FQDN 不同）</span><span class="sxs-lookup"><span data-stu-id="e411f-181">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="e411f-182">伺服器 FQDN</span><span class="sxs-lookup"><span data-stu-id="e411f-182">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="e411f-183">Lync 池 FQDN</span><span class="sxs-lookup"><span data-stu-id="e411f-183">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="e411f-184">符合簡單的 Url</span><span class="sxs-lookup"><span data-stu-id="e411f-184">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="e411f-185">電話撥入式簡易 URL</span><span class="sxs-lookup"><span data-stu-id="e411f-185">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="e411f-186">系統管理簡易 URL</span><span class="sxs-lookup"><span data-stu-id="e411f-186">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="e411f-187">或者，簡單 Url 的萬用字元專案</span><span class="sxs-lookup"><span data-stu-id="e411f-187">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e411f-188">SN = ee01;SAN = ee01;SAN = 滿足 contoso. .com;SAN = 符合 fabrikam .com;SAN = 撥入. .com;SAN = admin. .com</span><span class="sxs-lookup"><span data-stu-id="e411f-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="e411f-189">使用萬用字元憑證：</span><span class="sxs-lookup"><span data-stu-id="e411f-189">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="e411f-190">SN = ee01;SAN = ee01;SAN = \*. .com</span><span class="sxs-lookup"><span data-stu-id="e411f-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e411f-191">如果您有多個符合簡單的 Url，您必須將它們全部包含為 subject 替換名稱。</span><span class="sxs-lookup"><span data-stu-id="e411f-191">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="e411f-192">簡單的 URL 專案支援萬用字元專案。</span><span class="sxs-lookup"><span data-stu-id="e411f-192">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e411f-193">網頁外部</span><span class="sxs-lookup"><span data-stu-id="e411f-193">Web external</span></span></p></td>
<td><p><span data-ttu-id="e411f-194">池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="e411f-194">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="e411f-195">下列各項：</span><span class="sxs-lookup"><span data-stu-id="e411f-195">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e411f-196">外部 web FQDN</span><span class="sxs-lookup"><span data-stu-id="e411f-196">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="e411f-197">電話撥入式簡易 URL</span><span class="sxs-lookup"><span data-stu-id="e411f-197">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="e411f-198">系統管理簡易 URL</span><span class="sxs-lookup"><span data-stu-id="e411f-198">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="e411f-199">或者，簡單 Url 的萬用字元專案</span><span class="sxs-lookup"><span data-stu-id="e411f-199">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e411f-200">SN = ee01;SAN = webcon01;SAN = 滿足 contoso. .com;SAN = 符合 fabrikam .com;SAN = 撥入. .com</span><span class="sxs-lookup"><span data-stu-id="e411f-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="e411f-201">使用萬用字元憑證：</span><span class="sxs-lookup"><span data-stu-id="e411f-201">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="e411f-202">SN = ee01;SAN = webcon01;SAN = \*. .com</span><span class="sxs-lookup"><span data-stu-id="e411f-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e411f-203">如果您有多個符合簡單的 Url，您必須將它們全部包含為 subject 替換名稱。</span><span class="sxs-lookup"><span data-stu-id="e411f-203">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="e411f-204">簡單的 URL 專案支援萬用字元專案。</span><span class="sxs-lookup"><span data-stu-id="e411f-204">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="e411f-205">主管的憑證</span><span class="sxs-lookup"><span data-stu-id="e411f-205">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e411f-206">憑證</span><span class="sxs-lookup"><span data-stu-id="e411f-206">Certificate</span></span></th>
<th><span data-ttu-id="e411f-207">消費者名稱/通用名稱</span><span class="sxs-lookup"><span data-stu-id="e411f-207">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="e411f-208">消費者替換名稱</span><span class="sxs-lookup"><span data-stu-id="e411f-208">Subject alternative name</span></span></th>
<th><span data-ttu-id="e411f-209">範例</span><span class="sxs-lookup"><span data-stu-id="e411f-209">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e411f-210">設置</span><span class="sxs-lookup"><span data-stu-id="e411f-210">Default</span></span></p></td>
<td><p><span data-ttu-id="e411f-211">主管池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="e411f-211">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="e411f-212">主管的 FQDN，控制器池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="e411f-212">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="e411f-213">如果此池是用戶端的自動登入伺服器，且在 [群組原則] 中需要嚴格的 DNS 相符，您也需要 sipdomain （針對您擁有的每個 SIP 網域）輸入的專案。</span><span class="sxs-lookup"><span data-stu-id="e411f-213">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="e411f-214">SN = dir-pool.contoso.com;SAN = dir-pool.contoso.com;SAN = dir01</span><span class="sxs-lookup"><span data-stu-id="e411f-214">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="e411f-215">如果此主管池是用戶端的自動登入伺服器，且在 [群組原則] 中需要嚴格的 DNS 相符，您也需要 SAN = sip. .com;SAN = sip. .com</span><span class="sxs-lookup"><span data-stu-id="e411f-215">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e411f-216">網頁內部</span><span class="sxs-lookup"><span data-stu-id="e411f-216">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="e411f-217">伺服器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="e411f-217">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="e411f-218">下列各項：</span><span class="sxs-lookup"><span data-stu-id="e411f-218">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e411f-219">內部網路 FQDN （與伺服器的 FQDN 相同）</span><span class="sxs-lookup"><span data-stu-id="e411f-219">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="e411f-220">伺服器 FQDN</span><span class="sxs-lookup"><span data-stu-id="e411f-220">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="e411f-221">Lync 池 FQDN</span><span class="sxs-lookup"><span data-stu-id="e411f-221">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="e411f-222">符合簡單的 Url</span><span class="sxs-lookup"><span data-stu-id="e411f-222">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="e411f-223">電話撥入式簡易 URL</span><span class="sxs-lookup"><span data-stu-id="e411f-223">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="e411f-224">系統管理簡易 URL</span><span class="sxs-lookup"><span data-stu-id="e411f-224">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="e411f-225">或者，簡單 Url 的萬用字元專案</span><span class="sxs-lookup"><span data-stu-id="e411f-225">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e411f-226">SN = dir01;SAN = dir01;SAN = 滿足 contoso. .com;SAN = 符合 fabrikam .com;SAN = 撥入. .com;SAN = admin. .com</span><span class="sxs-lookup"><span data-stu-id="e411f-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="e411f-227">SN = dir01;SAN = dir01 （contoso. .com） SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="e411f-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e411f-228">網頁外部</span><span class="sxs-lookup"><span data-stu-id="e411f-228">Web external</span></span></p></td>
<td><p><span data-ttu-id="e411f-229">伺服器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="e411f-229">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="e411f-230">下列各項：</span><span class="sxs-lookup"><span data-stu-id="e411f-230">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e411f-231">外部 web FQDN</span><span class="sxs-lookup"><span data-stu-id="e411f-231">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="e411f-232">電話撥入式簡易 URL</span><span class="sxs-lookup"><span data-stu-id="e411f-232">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="e411f-233">系統管理簡易 URL</span><span class="sxs-lookup"><span data-stu-id="e411f-233">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="e411f-234">或者，簡單 Url 的萬用字元專案</span><span class="sxs-lookup"><span data-stu-id="e411f-234">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e411f-235">控制器外部 web FQDN 必須與前端池或前端伺服器不同。</span><span class="sxs-lookup"><span data-stu-id="e411f-235">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="e411f-236">SN = dir01;SAN = directorwebcon01 （contoso .com） SAN = 符合 contoso;SAN = 符合 fabrikam .com;SAN = 撥入. .com</span><span class="sxs-lookup"><span data-stu-id="e411f-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="e411f-237">SN = dir01;SAN = directorwebcon01 （contoso. .com） SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="e411f-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e411f-238">如果您擁有獨立的中繼伺服器池，則每個中繼伺服器都需要下表所列的憑證。</span><span class="sxs-lookup"><span data-stu-id="e411f-238">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table.</span></span> <span data-ttu-id="e411f-239">如果您 collocate 的是前端伺服器的中繼伺服器，在本主題先前的 [前端伺服器中的前端伺服器證書] 表格中所列的憑證就足夠了。</span><span class="sxs-lookup"><span data-stu-id="e411f-239">If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="e411f-240">獨立中繼伺服器的憑證</span><span class="sxs-lookup"><span data-stu-id="e411f-240">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e411f-241">憑證</span><span class="sxs-lookup"><span data-stu-id="e411f-241">Certificate</span></span></th>
<th><span data-ttu-id="e411f-242">消費者名稱/通用名稱</span><span class="sxs-lookup"><span data-stu-id="e411f-242">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="e411f-243">消費者替換名稱</span><span class="sxs-lookup"><span data-stu-id="e411f-243">Subject alternative name</span></span></th>
<th><span data-ttu-id="e411f-244">範例</span><span class="sxs-lookup"><span data-stu-id="e411f-244">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e411f-245">設置</span><span class="sxs-lookup"><span data-stu-id="e411f-245">Default</span></span></p></td>
<td><p><span data-ttu-id="e411f-246">池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="e411f-246">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="e411f-247">池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="e411f-247">FQDN of the pool</span></span></p>
<p><span data-ttu-id="e411f-248">Pool 成員伺服器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="e411f-248">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="e411f-249">SN = medsvr-pool.contoso.net;SAN = medsvr-pool.contoso.net;SAN = medsvr01</span><span class="sxs-lookup"><span data-stu-id="e411f-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="e411f-250">Survivable 分支裝置的憑證</span><span class="sxs-lookup"><span data-stu-id="e411f-250">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e411f-251">憑證</span><span class="sxs-lookup"><span data-stu-id="e411f-251">Certificate</span></span></th>
<th><span data-ttu-id="e411f-252">消費者名稱/通用名稱</span><span class="sxs-lookup"><span data-stu-id="e411f-252">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="e411f-253">消費者替換名稱</span><span class="sxs-lookup"><span data-stu-id="e411f-253">Subject alternative name</span></span></th>
<th><span data-ttu-id="e411f-254">範例</span><span class="sxs-lookup"><span data-stu-id="e411f-254">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e411f-255">設置</span><span class="sxs-lookup"><span data-stu-id="e411f-255">Default</span></span></p></td>
<td><p><span data-ttu-id="e411f-256">裝置的 FQDN</span><span class="sxs-lookup"><span data-stu-id="e411f-256">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="e411f-257">呼吸.&lt;sipdomain&gt; （每個 SIP 網域需要一個專案）</span><span class="sxs-lookup"><span data-stu-id="e411f-257">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="e411f-258">SN = sba01;SAN = sip. .com;SAN = sip. .com</span><span class="sxs-lookup"><span data-stu-id="e411f-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="e411f-259">請參閱</span><span class="sxs-lookup"><span data-stu-id="e411f-259">See Also</span></span>


[<span data-ttu-id="e411f-260">Lync Server 2013 中的萬用字元憑證支援</span><span class="sxs-lookup"><span data-stu-id="e411f-260">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

