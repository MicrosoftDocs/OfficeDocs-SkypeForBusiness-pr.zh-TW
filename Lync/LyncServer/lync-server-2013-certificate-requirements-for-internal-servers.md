---
title: Lync Server 2013： 適用於內部伺服器的憑證需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5b3da640ca4aa9f7b53c072802a2f7f727759dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="9b32d-102">適用於 Lync Server 2013 中的內部伺服器的憑證需求</span><span class="sxs-lookup"><span data-stu-id="9b32d-102">Certificate requirements for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b32d-103">_**主題上次修改日期：** 2017年-02-17_</span><span class="sxs-lookup"><span data-stu-id="9b32d-103">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="9b32d-104">內部伺服器，執行 Lync Server 且需要憑證包含 Standard Edition server、 Enterprise Edition 前端伺服器、 中繼伺服器和 Director。</span><span class="sxs-lookup"><span data-stu-id="9b32d-104">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="9b32d-105">下表顯示這些伺服器的憑證需求。</span><span class="sxs-lookup"><span data-stu-id="9b32d-105">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="9b32d-106">您可以使用 [Lync 伺服器憑證] 精靈，以要求這些憑證。</span><span class="sxs-lookup"><span data-stu-id="9b32d-106">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="9b32d-107">在前端集區、 前端伺服器或 Director 的簡單 Url 相關聯的主體替代名稱支援萬用字元憑證。</span><span class="sxs-lookup"><span data-stu-id="9b32d-107">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="9b32d-108">如需詳細資訊萬用字元憑證支援，請參閱<A href="lync-server-2013-wildcard-certificate-support.md">Lync Server 2013 中支援的萬用字元憑證</A>。</span><span class="sxs-lookup"><span data-stu-id="9b32d-108">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="9b32d-109">雖然建議內部伺服器使用內部企業憑證授權單位 (CA)，但您也可以使用公用 CA。</span><span class="sxs-lookup"><span data-stu-id="9b32d-109">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="9b32d-110">如需在提供符合特定需求的憑證整合通訊 (UC) 憑證，並已建立合作關係與 Microsoft，以確保可搭配 [Lync 伺服器憑證] 精靈中，請參閱文章 Microsoft 知識庫件 929395 「 整合通訊憑證合作夥伴的 Exchange Server 和 Communications Server，」 的公用 Ca 的清單[https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)。</span><span class="sxs-lookup"><span data-stu-id="9b32d-110">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="9b32d-111">與其他應用程式和伺服器，例如 Exchange 2013 通訊需要受到其他應用程式和產品的憑證。</span><span class="sxs-lookup"><span data-stu-id="9b32d-111">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="9b32d-112">2013 版本，Lync Server 2013 與其他 Microsoft server 產品，包括 Exchange 2013 和 SharePoint Server 支援伺服器對伺服器驗證及授權的 Open Authorization (OAuth) 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="9b32d-112">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="9b32d-113">如需詳細資訊，請參閱部署文件或作業文件中的[管理伺服器對伺服器驗證 (OAuth) 與 Lync Server 2013 中的協力廠商應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="9b32d-113">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="9b32d-114">從執行 Windows 7 作業系統、 Windows Server 2008 作業系統、 Windows Server 2008 R2 作業系統、 Windows Vista 作業系統和 Microsoft Lync Phone Edition 的用戶端連線，Lync Server 2013 包含支援 （但不會需要） 使用 sha-256 密碼編譯雜湊函數簽署的憑證。</span><span class="sxs-lookup"><span data-stu-id="9b32d-114">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="9b32d-115">為了支援使用 SHA-256 的外部存取，外部憑證由公用 CA 使用 SHA-256 發行。</span><span class="sxs-lookup"><span data-stu-id="9b32d-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="9b32d-p106">下表依伺服器角色顯示前端集區和 Standard Edition Server 的憑證需求。這些全部都是不可匯出的標準 Web 伺服器憑證、私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="9b32d-p106">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers. All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="9b32d-118">請注意，當您使用憑證精靈要求憑證時，會自動設定伺服器增強金鑰使用方法 (EKU)。</span><span class="sxs-lookup"><span data-stu-id="9b32d-118">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9b32d-119">電腦存放區中，每個憑證好記的名稱必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="9b32d-119">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="9b32d-120">如果您已設定 sipinternal.contoso.com 或 sipexternal.contoso.com DNS 中，您必須將它們新增中憑證的 Subject Alternative Name。</span><span class="sxs-lookup"><span data-stu-id="9b32d-120">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="9b32d-121">Standard Edition Server 的憑證</span><span class="sxs-lookup"><span data-stu-id="9b32d-121">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="9b32d-122">認證</span><span class="sxs-lookup"><span data-stu-id="9b32d-122">Certificate</span></span></th>
<th><span data-ttu-id="9b32d-123">主體名稱 / 一般名稱</span><span class="sxs-lookup"><span data-stu-id="9b32d-123">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="9b32d-124">主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="9b32d-124">Subject alternative name</span></span></th>
<th><span data-ttu-id="9b32d-125">範例</span><span class="sxs-lookup"><span data-stu-id="9b32d-125">Example</span></span></th>
<th><span data-ttu-id="9b32d-126">註解</span><span class="sxs-lookup"><span data-stu-id="9b32d-126">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b32d-127">預設</span><span class="sxs-lookup"><span data-stu-id="9b32d-127">Default</span></span></p></td>
<td><p><span data-ttu-id="9b32d-128">集區的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="9b32d-128">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="9b32d-129">集區的 FQDN 和伺服器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-129">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="9b32d-130">如果您擁有多個 SIP 網域，且已啟用用戶端自動設定，則憑證精靈會偵測並新增每個支援的 SIP 網域 FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-130">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="9b32d-131">如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格網域名稱系統 (DNS) 比對，則您也需要 sip.sipdomain (對於您具有的每個 SIP 網域) 的項目。</span><span class="sxs-lookup"><span data-stu-id="9b32d-131">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="9b32d-132">SN=se01.contoso.com;SAN=se01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b32d-132">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="9b32d-133">如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 SAN=sip.contoso.com；SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9b32d-133">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="9b32d-134">在 Standard Edition Server，伺服器 FQDN 與集區 FQDN 相同。</span><span class="sxs-lookup"><span data-stu-id="9b32d-134">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="9b32d-135">精靈會偵測任何您在安裝期間指定的 SIP 網域，並將之自動新增到主體別名。</span><span class="sxs-lookup"><span data-stu-id="9b32d-135">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="9b32d-136">您也可以使用此憑證的伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="9b32d-136">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b32d-137">Web 內部</span><span class="sxs-lookup"><span data-stu-id="9b32d-137">Web internal</span></span></p></td>
<td><p><span data-ttu-id="9b32d-138">伺服器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-138">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="9b32d-139">下列每一項：</span><span class="sxs-lookup"><span data-stu-id="9b32d-139">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9b32d-140">內部 Web FQDN (與伺服器的 FQDN 相同)</span><span class="sxs-lookup"><span data-stu-id="9b32d-140">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="9b32d-141">Meet 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="9b32d-141">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="9b32d-142">Dial-in 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="9b32d-142">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="9b32d-143">Admin 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="9b32d-143">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="9b32d-144">或者，簡單 URL 的萬用字元項目</span><span class="sxs-lookup"><span data-stu-id="9b32d-144">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9b32d-145">SN=se01.contoso.com;SAN=se01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b32d-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="9b32d-146">使用萬用字元憑證：</span><span class="sxs-lookup"><span data-stu-id="9b32d-146">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="9b32d-147">SN=se01.contoso.com;SAN=se01.contoso.com;SAN = \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b32d-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9b32d-148">您不能覆寫內部 web FQDN 在拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="9b32d-148">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="9b32d-149">若有多個 Meet 簡單 URL，則必須包含這些 URL 做為主體別名。</span><span class="sxs-lookup"><span data-stu-id="9b32d-149">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="9b32d-150">簡單 URL 項目支援萬用字元項目。</span><span class="sxs-lookup"><span data-stu-id="9b32d-150">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b32d-151">Web 外部</span><span class="sxs-lookup"><span data-stu-id="9b32d-151">Web external</span></span></p></td>
<td><p><span data-ttu-id="9b32d-152">伺服器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-152">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="9b32d-153">下列每一項：</span><span class="sxs-lookup"><span data-stu-id="9b32d-153">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9b32d-154">外部 Web FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-154">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="9b32d-155">Dial-in 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="9b32d-155">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="9b32d-156">每個 SIP 網域的 meet 簡單 Url</span><span class="sxs-lookup"><span data-stu-id="9b32d-156">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="9b32d-157">或是簡單 URL 的萬用字元項目</span><span class="sxs-lookup"><span data-stu-id="9b32d-157">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9b32d-158">SN=se01.contoso.com;SAN=webcon01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b32d-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="9b32d-159">使用萬用字元憑證：</span><span class="sxs-lookup"><span data-stu-id="9b32d-159">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="9b32d-160">SN=se01.contoso.com;SAN=webcon01.contoso.com;SAN = \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b32d-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9b32d-161">若有多個 Meet 簡單 URL，則必須包含這些 URL 做為主體別名。</span><span class="sxs-lookup"><span data-stu-id="9b32d-161">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="9b32d-162">簡單 URL 項目支援萬用字元項目。</span><span class="sxs-lookup"><span data-stu-id="9b32d-162">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="9b32d-163">前端集區中前端伺服器的憑證</span><span class="sxs-lookup"><span data-stu-id="9b32d-163">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="9b32d-164">認證</span><span class="sxs-lookup"><span data-stu-id="9b32d-164">Certificate</span></span></th>
<th><span data-ttu-id="9b32d-165">主體名稱 / 一般名稱</span><span class="sxs-lookup"><span data-stu-id="9b32d-165">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="9b32d-166">主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="9b32d-166">Subject alternative name</span></span></th>
<th><span data-ttu-id="9b32d-167">範例</span><span class="sxs-lookup"><span data-stu-id="9b32d-167">Example</span></span></th>
<th><span data-ttu-id="9b32d-168">註解</span><span class="sxs-lookup"><span data-stu-id="9b32d-168">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b32d-169">預設</span><span class="sxs-lookup"><span data-stu-id="9b32d-169">Default</span></span></p></td>
<td><p><span data-ttu-id="9b32d-170">集區的 FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-170">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="9b32d-171">集區的 FQDN 和伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9b32d-171">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="9b32d-172">如果您擁有多個 SIP 網域，且已啟用用戶端自動設定，則憑證精靈會偵測並新增每個支援的 SIP 網域 FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-172">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="9b32d-173">如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 sip.sipdomain (對於您具有的每個 SIP 網域) 的項目。</span><span class="sxs-lookup"><span data-stu-id="9b32d-173">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="9b32d-174">SN=eepool.contoso.com;SAN=eepool.contoso.com;SAN=ee01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b32d-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="9b32d-175">如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 SAN=sip.contoso.com；SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9b32d-175">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="9b32d-176">精靈會偵測任何您在安裝期間指定的 SIP 網域，並將之自動新增到主體別名。</span><span class="sxs-lookup"><span data-stu-id="9b32d-176">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="9b32d-177">您也可以使用此憑證的伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="9b32d-177">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b32d-178">Web 內部</span><span class="sxs-lookup"><span data-stu-id="9b32d-178">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="9b32d-179">集區的 FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-179">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="9b32d-180">下列每一項：</span><span class="sxs-lookup"><span data-stu-id="9b32d-180">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9b32d-181">內部 web FQDN （也就是不之伺服器的 FQDN 相同）</span><span class="sxs-lookup"><span data-stu-id="9b32d-181">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="9b32d-182">伺服器 FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-182">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="9b32d-183">Lync 集區 FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-183">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="9b32d-184">Meet 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="9b32d-184">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="9b32d-185">Dial-in 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="9b32d-185">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="9b32d-186">Admin 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="9b32d-186">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="9b32d-187">或者，簡單 URL 的萬用字元項目</span><span class="sxs-lookup"><span data-stu-id="9b32d-187">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9b32d-188">SN=ee01.contoso.com;SAN=ee01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b32d-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="9b32d-189">使用萬用字元憑證：</span><span class="sxs-lookup"><span data-stu-id="9b32d-189">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="9b32d-190">SN=ee01.contoso.com;SAN=ee01.contoso.com;SAN = \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b32d-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9b32d-191">若有多個 Meet 簡單 URL，則必須包含這些 URL 做為主體別名。</span><span class="sxs-lookup"><span data-stu-id="9b32d-191">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="9b32d-192">簡單 URL 項目支援萬用字元項目。</span><span class="sxs-lookup"><span data-stu-id="9b32d-192">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b32d-193">Web 外部</span><span class="sxs-lookup"><span data-stu-id="9b32d-193">Web external</span></span></p></td>
<td><p><span data-ttu-id="9b32d-194">集區的 FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-194">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="9b32d-195">下列每一項：</span><span class="sxs-lookup"><span data-stu-id="9b32d-195">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9b32d-196">外部 Web FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-196">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="9b32d-197">Dial-in 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="9b32d-197">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="9b32d-198">Admin 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="9b32d-198">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="9b32d-199">或者，簡單 URL 的萬用字元項目</span><span class="sxs-lookup"><span data-stu-id="9b32d-199">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9b32d-200">SN=ee01.contoso.com;SAN=webcon01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b32d-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="9b32d-201">使用萬用字元憑證：</span><span class="sxs-lookup"><span data-stu-id="9b32d-201">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="9b32d-202">SN=ee01.contoso.com;SAN=webcon01.contoso.com;SAN = \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b32d-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9b32d-203">若有多個 Meet 簡單 URL，則必須包含這些 URL 做為主體別名。</span><span class="sxs-lookup"><span data-stu-id="9b32d-203">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="9b32d-204">簡單 URL 項目支援萬用字元項目。</span><span class="sxs-lookup"><span data-stu-id="9b32d-204">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="9b32d-205">Director 的憑證</span><span class="sxs-lookup"><span data-stu-id="9b32d-205">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b32d-206">認證</span><span class="sxs-lookup"><span data-stu-id="9b32d-206">Certificate</span></span></th>
<th><span data-ttu-id="9b32d-207">主體名稱 / 一般名稱</span><span class="sxs-lookup"><span data-stu-id="9b32d-207">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="9b32d-208">主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="9b32d-208">Subject alternative name</span></span></th>
<th><span data-ttu-id="9b32d-209">範例</span><span class="sxs-lookup"><span data-stu-id="9b32d-209">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b32d-210">預設</span><span class="sxs-lookup"><span data-stu-id="9b32d-210">Default</span></span></p></td>
<td><p><span data-ttu-id="9b32d-211">Director 集區的 FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-211">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="9b32d-212">Director 的 FQDN，Director 集區的 FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-212">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="9b32d-213">如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 sip.sipdomain (對於您具有的每個 SIP 網域) 的項目。</span><span class="sxs-lookup"><span data-stu-id="9b32d-213">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="9b32d-214">SN = dir pool.contoso.com;SAN = dir pool.contoso.com;SAN=dir01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b32d-214">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="9b32d-215">如果此 Director 集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 SAN=sip.contoso.com；SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9b32d-215">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b32d-216">Web 內部</span><span class="sxs-lookup"><span data-stu-id="9b32d-216">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="9b32d-217">伺服器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-217">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="9b32d-218">下列每一項：</span><span class="sxs-lookup"><span data-stu-id="9b32d-218">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9b32d-219">內部 Web FQDN (與伺服器的 FQDN 相同)</span><span class="sxs-lookup"><span data-stu-id="9b32d-219">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="9b32d-220">伺服器 FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-220">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="9b32d-221">Lync 集區 FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-221">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="9b32d-222">Meet 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="9b32d-222">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="9b32d-223">Dial-in 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="9b32d-223">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="9b32d-224">Admin 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="9b32d-224">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="9b32d-225">或者，簡單 URL 的萬用字元項目</span><span class="sxs-lookup"><span data-stu-id="9b32d-225">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9b32d-226">SN=dir01.contoso.com;SAN=dir01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b32d-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="9b32d-227">SN=dir01.contoso.com;SAN=dir01.contoso.com SAN = \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b32d-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b32d-228">Web 外部</span><span class="sxs-lookup"><span data-stu-id="9b32d-228">Web external</span></span></p></td>
<td><p><span data-ttu-id="9b32d-229">伺服器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-229">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="9b32d-230">下列每一項：</span><span class="sxs-lookup"><span data-stu-id="9b32d-230">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9b32d-231">外部 Web FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-231">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="9b32d-232">Dial-in 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="9b32d-232">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="9b32d-233">Admin 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="9b32d-233">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="9b32d-234">或者，簡單 URL 的萬用字元項目</span><span class="sxs-lookup"><span data-stu-id="9b32d-234">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="9b32d-235">Director 外部 web FQDN 必須與前端集區或前端伺服器不同。</span><span class="sxs-lookup"><span data-stu-id="9b32d-235">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="9b32d-236">SN=dir01.contoso.com;SAN=directorwebcon01.contoso.com SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b32d-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="9b32d-237">SN=dir01.contoso.com;SAN=directorwebcon01.contoso.com SAN = \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9b32d-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9b32d-p107">如果您具有獨立中繼伺服器集區，則該集區中的每個中繼伺服器都需要下表所列的憑證。如果您將中繼伺服器與前端伺服器組合在一起，則本主題中前面的「前端集區中前端伺服器的憑證」表格中所列的憑證已足夠。</span><span class="sxs-lookup"><span data-stu-id="9b32d-p107">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table. If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="9b32d-240">獨立中繼伺服器的憑證</span><span class="sxs-lookup"><span data-stu-id="9b32d-240">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b32d-241">認證</span><span class="sxs-lookup"><span data-stu-id="9b32d-241">Certificate</span></span></th>
<th><span data-ttu-id="9b32d-242">主體名稱 / 一般名稱</span><span class="sxs-lookup"><span data-stu-id="9b32d-242">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="9b32d-243">主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="9b32d-243">Subject alternative name</span></span></th>
<th><span data-ttu-id="9b32d-244">範例</span><span class="sxs-lookup"><span data-stu-id="9b32d-244">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b32d-245">預設</span><span class="sxs-lookup"><span data-stu-id="9b32d-245">Default</span></span></p></td>
<td><p><span data-ttu-id="9b32d-246">集區的 FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-246">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="9b32d-247">集區的 FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-247">FQDN of the pool</span></span></p>
<p><span data-ttu-id="9b32d-248">集區成員伺服器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-248">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="9b32d-249">SN = medsvr pool.contoso.net;SAN = medsvr pool.contoso.net;SAN=medsvr01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="9b32d-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="9b32d-250">Survivable Branch Appliance 的憑證</span><span class="sxs-lookup"><span data-stu-id="9b32d-250">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b32d-251">認證</span><span class="sxs-lookup"><span data-stu-id="9b32d-251">Certificate</span></span></th>
<th><span data-ttu-id="9b32d-252">主體名稱 / 一般名稱</span><span class="sxs-lookup"><span data-stu-id="9b32d-252">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="9b32d-253">主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="9b32d-253">Subject alternative name</span></span></th>
<th><span data-ttu-id="9b32d-254">範例</span><span class="sxs-lookup"><span data-stu-id="9b32d-254">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b32d-255">預設</span><span class="sxs-lookup"><span data-stu-id="9b32d-255">Default</span></span></p></td>
<td><p><span data-ttu-id="9b32d-256">Appliance 的 FQDN</span><span class="sxs-lookup"><span data-stu-id="9b32d-256">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="9b32d-257">SIP。&lt;sipdomain&gt; （需要每個 SIP 網域的一個項目）</span><span class="sxs-lookup"><span data-stu-id="9b32d-257">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="9b32d-258">SN=sba01.contoso.net;Sip.contoso.com;San = sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9b32d-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="9b32d-259">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9b32d-259">See Also</span></span>


[<span data-ttu-id="9b32d-260">Lync Server 2013 中的萬用字元憑證支援</span><span class="sxs-lookup"><span data-stu-id="9b32d-260">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

