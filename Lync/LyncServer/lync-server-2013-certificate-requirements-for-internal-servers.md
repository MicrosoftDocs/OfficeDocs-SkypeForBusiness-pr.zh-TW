---
title: Lync Server 2013：內部伺服器的憑證需求
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
ms.openlocfilehash: c56554a26e5f64089a766300f375039409680578
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526240"
---
# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="7d0b3-102">Lync Server 2013 中內部伺服器的憑證需求</span><span class="sxs-lookup"><span data-stu-id="7d0b3-102">Certificate requirements for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d0b3-103">_**主題上次修改日期：** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="7d0b3-103">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="7d0b3-104">執行 Lync Server 且需要憑證的內部伺服器包括 Standard Edition Server、Enterprise Edition 前端伺服器、轉送伺服器及 Director。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-104">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="7d0b3-105">下表顯示這些伺服器的憑證需求。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-105">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="7d0b3-106">您可以使用 Lync Server 憑證嚮導來要求這些憑證。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-106">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="7d0b3-107">針對與前端集區、前端伺服器或 Director 上的簡易 URLs 相關聯的主體替代名稱，支援通配憑證。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-107">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="7d0b3-108">如需有關萬用字元憑證支援的詳細資訊，請參閱 <A href="lync-server-2013-wildcard-certificate-support.md">Lync Server 2013 中的通配憑證支援</A>。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-108">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="7d0b3-109">雖然建議內部伺服器使用內部企業憑證授權單位 (CA)，但您也可以使用公用 CA。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-109">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="7d0b3-110">如需提供符合整合通訊特定需求之憑證的公用 Ca 清單 (UC) 憑證，並與 Microsoft 合作，以確保其與 Lync Server 憑證嚮導搭配運作，請參閱 Microsoft 知識庫929395：「Exchange Server 和通訊伺服器的整合通訊憑證合作夥伴」; at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) 。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-110">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="7d0b3-111">與其他應用程式和伺服器進行通訊，例如 Exchange 2013，需要另一個應用程式和產品所支援的憑證。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-111">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="7d0b3-112">針對2013版本，Lync Server 2013 和其他 Microsoft server 產品（包括 Exchange 2013 和 SharePoint 伺服器）都支援「開放授權」 (OAuth 伺服器對伺服器驗證和授權的) 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-112">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="7d0b3-113">如需詳細資訊，請參閱部署檔或作業檔中的 [管理 Lync server 2013 中的伺服器對伺服器驗證 (OAuth) 和夥伴應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-113">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="7d0b3-114">針對來自執行 Windows 7 作業系統、windows server 2008 作業系統、Windows Server 2008 R2 作業系統、windows Vista 作業系統及 Microsoft Lync Phone Edition 之用戶端的連線，Lync Server 2013 包含對 (的支援，但不需要使用 SHA-256 加密雜湊函數簽署) 憑證。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-114">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="7d0b3-115">為了支援使用 SHA-256 的外部存取，外部憑證由公用 CA 使用 SHA-256 發行。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="7d0b3-p106">下表依伺服器角色顯示前端集區和 Standard Edition Server 的憑證需求。這些全部都是不可匯出的標準 Web 伺服器憑證、私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-p106">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers. All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="7d0b3-118">請注意，當您使用憑證精靈要求憑證時，會自動設定伺服器增強金鑰使用方法 (EKU)。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-118">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7d0b3-119">每個憑證好記的名稱在電腦存放區中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-119">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="7d0b3-120">如果您已在 DNS 中設定 sipinternal.contoso.com 或 sipexternal.contoso.com，您必須將其新增至憑證的主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-120">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="7d0b3-121">Standard Edition Server 的憑證</span><span class="sxs-lookup"><span data-stu-id="7d0b3-121">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="7d0b3-122">認證</span><span class="sxs-lookup"><span data-stu-id="7d0b3-122">Certificate</span></span></th>
<th><span data-ttu-id="7d0b3-123">主體名稱/一般名稱</span><span class="sxs-lookup"><span data-stu-id="7d0b3-123">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="7d0b3-124">主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="7d0b3-124">Subject alternative name</span></span></th>
<th><span data-ttu-id="7d0b3-125">範例</span><span class="sxs-lookup"><span data-stu-id="7d0b3-125">Example</span></span></th>
<th><span data-ttu-id="7d0b3-126">註解</span><span class="sxs-lookup"><span data-stu-id="7d0b3-126">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d0b3-127">預設</span><span class="sxs-lookup"><span data-stu-id="7d0b3-127">Default</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-128">集區的完整網域名稱 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="7d0b3-128">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-129">集區的 FQDN 和伺服器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-129">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="7d0b3-130">如果您擁有多個 SIP 網域，且已啟用用戶端自動設定，則憑證精靈會偵測並新增每個支援的 SIP 網域 FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-130">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="7d0b3-131">如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格網域名稱系統 (DNS) 比對，則您也需要 sip.sipdomain (對於您具有的每個 SIP 網域) 的項目。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-131">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-132">SN = se01，SAN = se01</span><span class="sxs-lookup"><span data-stu-id="7d0b3-132">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="7d0b3-133">如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 SAN=sip.contoso.com；SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="7d0b3-133">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-134">在 Standard Edition Server，伺服器 FQDN 與集區 FQDN 相同。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-134">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="7d0b3-135">精靈會偵測任何您在安裝期間指定的 SIP 網域，並將之自動新增到主體別名。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-135">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="7d0b3-136">您也可以使用此憑證進行 Server-to-Server 驗證。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-136">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d0b3-137">Web 內部</span><span class="sxs-lookup"><span data-stu-id="7d0b3-137">Web internal</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-138">伺服器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-138">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-139">下列每一項：</span><span class="sxs-lookup"><span data-stu-id="7d0b3-139">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7d0b3-140">內部 Web FQDN (與伺服器的 FQDN 相同)</span><span class="sxs-lookup"><span data-stu-id="7d0b3-140">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-141">Meet 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="7d0b3-141">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-142">Dial-in 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="7d0b3-142">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-143">Admin 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="7d0b3-143">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-144">或者，簡單 URL 的萬用字元項目</span><span class="sxs-lookup"><span data-stu-id="7d0b3-144">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7d0b3-145">SN = se01，SAN = se01;SAN = 符合 .com;SAN = 符合 fabrikam .com;SAN = 撥入 .com;SAN = contoso .com</span><span class="sxs-lookup"><span data-stu-id="7d0b3-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="7d0b3-146">使用萬用字元憑證：</span><span class="sxs-lookup"><span data-stu-id="7d0b3-146">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="7d0b3-147">SN = se01，SAN = se01;SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="7d0b3-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-148">您無法在拓撲產生器中覆寫內部 web FQDN。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-148">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="7d0b3-149">若有多個 Meet 簡單 URL，則必須包含這些 URL 做為主體別名。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-149">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="7d0b3-150">簡單 URL 項目支援萬用字元項目。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-150">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d0b3-151">Web 外部</span><span class="sxs-lookup"><span data-stu-id="7d0b3-151">Web external</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-152">伺服器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-152">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-153">下列每一項：</span><span class="sxs-lookup"><span data-stu-id="7d0b3-153">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7d0b3-154">外部 Web FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-154">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-155">Dial-in 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="7d0b3-155">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-156">符合每個 SIP 網域的簡易 URLs</span><span class="sxs-lookup"><span data-stu-id="7d0b3-156">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-157">或者，簡單 URL 的萬用字元項目</span><span class="sxs-lookup"><span data-stu-id="7d0b3-157">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7d0b3-158">SN = se01，SAN = webcon01;SAN = 符合 .com;SAN = 符合 fabrikam .com;SAN = 撥入 .com</span><span class="sxs-lookup"><span data-stu-id="7d0b3-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="7d0b3-159">使用萬用字元憑證：</span><span class="sxs-lookup"><span data-stu-id="7d0b3-159">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="7d0b3-160">SN = se01，SAN = webcon01;SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="7d0b3-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-161">若有多個 Meet 簡單 URL，則必須包含這些 URL 做為主體別名。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-161">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="7d0b3-162">簡單 URL 項目支援萬用字元項目。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-162">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="7d0b3-163">前端集區中前端伺服器的憑證</span><span class="sxs-lookup"><span data-stu-id="7d0b3-163">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="7d0b3-164">認證</span><span class="sxs-lookup"><span data-stu-id="7d0b3-164">Certificate</span></span></th>
<th><span data-ttu-id="7d0b3-165">主體名稱/一般名稱</span><span class="sxs-lookup"><span data-stu-id="7d0b3-165">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="7d0b3-166">主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="7d0b3-166">Subject alternative name</span></span></th>
<th><span data-ttu-id="7d0b3-167">範例</span><span class="sxs-lookup"><span data-stu-id="7d0b3-167">Example</span></span></th>
<th><span data-ttu-id="7d0b3-168">註解</span><span class="sxs-lookup"><span data-stu-id="7d0b3-168">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d0b3-169">預設</span><span class="sxs-lookup"><span data-stu-id="7d0b3-169">Default</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-170">集區的 FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-170">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-171">集區的 FQDN 和伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-171">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="7d0b3-172">如果您擁有多個 SIP 網域，且已啟用用戶端自動設定，則憑證精靈會偵測並新增每個支援的 SIP 網域 FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-172">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="7d0b3-173">如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 sip.sipdomain (對於您具有的每個 SIP 網域) 的項目。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-173">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-174">SN = eepool，SAN = eepool;SAN = ee01</span><span class="sxs-lookup"><span data-stu-id="7d0b3-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="7d0b3-175">如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 SAN=sip.contoso.com；SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="7d0b3-175">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-176">精靈會偵測任何您在安裝期間指定的 SIP 網域，並將之自動新增到主體別名。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-176">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="7d0b3-177">您也可以使用此憑證進行 Server-to-Server 驗證。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-177">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d0b3-178">Web 內部</span><span class="sxs-lookup"><span data-stu-id="7d0b3-178">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-179">集區的 FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-179">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-180">下列每一項：</span><span class="sxs-lookup"><span data-stu-id="7d0b3-180">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7d0b3-181">內部 web FQDN (，其與伺服器的 FQDN 不同) </span><span class="sxs-lookup"><span data-stu-id="7d0b3-181">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-182">伺服器 FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-182">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-183">Lync 集區 FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-183">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-184">Meet 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="7d0b3-184">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-185">Dial-in 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="7d0b3-185">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-186">Admin 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="7d0b3-186">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-187">或者，簡單 URL 的萬用字元項目</span><span class="sxs-lookup"><span data-stu-id="7d0b3-187">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7d0b3-188">SN = ee01，SAN = ee01;SAN = 符合 .com;SAN = 符合 fabrikam .com;SAN = 撥入 .com;SAN = contoso .com</span><span class="sxs-lookup"><span data-stu-id="7d0b3-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="7d0b3-189">使用萬用字元憑證：</span><span class="sxs-lookup"><span data-stu-id="7d0b3-189">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="7d0b3-190">SN = ee01，SAN = ee01;SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="7d0b3-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-191">若有多個 Meet 簡單 URL，則必須包含這些 URL 做為主體別名。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-191">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="7d0b3-192">簡單 URL 項目支援萬用字元項目。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-192">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d0b3-193">Web 外部</span><span class="sxs-lookup"><span data-stu-id="7d0b3-193">Web external</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-194">集區的 FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-194">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-195">下列每一項：</span><span class="sxs-lookup"><span data-stu-id="7d0b3-195">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7d0b3-196">外部 Web FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-196">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-197">Dial-in 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="7d0b3-197">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-198">Admin 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="7d0b3-198">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-199">或者，簡單 URL 的萬用字元項目</span><span class="sxs-lookup"><span data-stu-id="7d0b3-199">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7d0b3-200">SN = ee01，SAN = webcon01;SAN = 符合 .com;SAN = 符合 fabrikam .com;SAN = 撥入 .com</span><span class="sxs-lookup"><span data-stu-id="7d0b3-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="7d0b3-201">使用萬用字元憑證：</span><span class="sxs-lookup"><span data-stu-id="7d0b3-201">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="7d0b3-202">SN = ee01，SAN = webcon01;SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="7d0b3-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-203">若有多個 Meet 簡單 URL，則必須包含這些 URL 做為主體別名。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-203">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="7d0b3-204">簡單 URL 項目支援萬用字元項目。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-204">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="7d0b3-205">Director 的憑證</span><span class="sxs-lookup"><span data-stu-id="7d0b3-205">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d0b3-206">認證</span><span class="sxs-lookup"><span data-stu-id="7d0b3-206">Certificate</span></span></th>
<th><span data-ttu-id="7d0b3-207">主體名稱/一般名稱</span><span class="sxs-lookup"><span data-stu-id="7d0b3-207">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="7d0b3-208">主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="7d0b3-208">Subject alternative name</span></span></th>
<th><span data-ttu-id="7d0b3-209">範例</span><span class="sxs-lookup"><span data-stu-id="7d0b3-209">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d0b3-210">預設</span><span class="sxs-lookup"><span data-stu-id="7d0b3-210">Default</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-211">Director 集區的 FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-211">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-212">Director 的 FQDN，Director 集區的 FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-212">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="7d0b3-213">如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 sip.sipdomain (對於您具有的每個 SIP 網域) 的項目。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-213">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-214">SN = dir-pool.contoso.com;SAN = pool.contoso.com;SAN = dir01</span><span class="sxs-lookup"><span data-stu-id="7d0b3-214">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="7d0b3-215">如果此 Director 集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 SAN=sip.contoso.com；SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="7d0b3-215">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d0b3-216">Web 內部</span><span class="sxs-lookup"><span data-stu-id="7d0b3-216">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-217">伺服器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-217">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-218">下列每一項：</span><span class="sxs-lookup"><span data-stu-id="7d0b3-218">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7d0b3-219">內部 Web FQDN (與伺服器的 FQDN 相同)</span><span class="sxs-lookup"><span data-stu-id="7d0b3-219">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-220">伺服器 FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-220">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-221">Lync 集區 FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-221">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-222">Meet 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="7d0b3-222">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-223">Dial-in 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="7d0b3-223">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-224">Admin 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="7d0b3-224">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-225">或者，簡單 URL 的萬用字元項目</span><span class="sxs-lookup"><span data-stu-id="7d0b3-225">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7d0b3-226">SN = dir01，SAN = dir01;SAN = 符合 .com;SAN = 符合 fabrikam .com;SAN = 撥入 .com;SAN = contoso .com</span><span class="sxs-lookup"><span data-stu-id="7d0b3-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="7d0b3-227">SN = dir01，SAN = dir01-.com SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="7d0b3-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d0b3-228">Web 外部</span><span class="sxs-lookup"><span data-stu-id="7d0b3-228">Web external</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-229">伺服器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-229">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-230">下列每一項：</span><span class="sxs-lookup"><span data-stu-id="7d0b3-230">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7d0b3-231">外部 Web FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-231">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-232">Dial-in 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="7d0b3-232">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-233">Admin 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="7d0b3-233">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="7d0b3-234">或者，簡單 URL 的萬用字元項目</span><span class="sxs-lookup"><span data-stu-id="7d0b3-234">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7d0b3-235">Director 外部 web FQDN 必須不同于前端集區或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-235">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="7d0b3-236">SN = dir01，SAN = directorwebcon01 SAN = "contoso .com"，SAN = 符合 fabrikam .com;SAN = 撥入 .com</span><span class="sxs-lookup"><span data-stu-id="7d0b3-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="7d0b3-237">SN = dir01，SAN = directorwebcon01-.com SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="7d0b3-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7d0b3-p107">如果您具有獨立中繼伺服器集區，則該集區中的每個中繼伺服器都需要下表所列的憑證。如果您將中繼伺服器與前端伺服器組合在一起，則本主題中前面的「前端集區中前端伺服器的憑證」表格中所列的憑證已足夠。</span><span class="sxs-lookup"><span data-stu-id="7d0b3-p107">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table. If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="7d0b3-240">獨立中繼伺服器的憑證</span><span class="sxs-lookup"><span data-stu-id="7d0b3-240">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d0b3-241">認證</span><span class="sxs-lookup"><span data-stu-id="7d0b3-241">Certificate</span></span></th>
<th><span data-ttu-id="7d0b3-242">主體名稱/一般名稱</span><span class="sxs-lookup"><span data-stu-id="7d0b3-242">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="7d0b3-243">主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="7d0b3-243">Subject alternative name</span></span></th>
<th><span data-ttu-id="7d0b3-244">範例</span><span class="sxs-lookup"><span data-stu-id="7d0b3-244">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d0b3-245">預設</span><span class="sxs-lookup"><span data-stu-id="7d0b3-245">Default</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-246">集區的 FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-246">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-247">集區的 FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-247">FQDN of the pool</span></span></p>
<p><span data-ttu-id="7d0b3-248">集區成員伺服器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-248">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-249">SN = medsvr-pool.contoso.net;SAN = medsvr-pool.contoso.net;SAN = medsvr01</span><span class="sxs-lookup"><span data-stu-id="7d0b3-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="7d0b3-250">Survivable Branch Appliance 的憑證</span><span class="sxs-lookup"><span data-stu-id="7d0b3-250">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d0b3-251">認證</span><span class="sxs-lookup"><span data-stu-id="7d0b3-251">Certificate</span></span></th>
<th><span data-ttu-id="7d0b3-252">主體名稱/一般名稱</span><span class="sxs-lookup"><span data-stu-id="7d0b3-252">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="7d0b3-253">主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="7d0b3-253">Subject alternative name</span></span></th>
<th><span data-ttu-id="7d0b3-254">範例</span><span class="sxs-lookup"><span data-stu-id="7d0b3-254">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d0b3-255">預設</span><span class="sxs-lookup"><span data-stu-id="7d0b3-255">Default</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-256">Appliance 的 FQDN</span><span class="sxs-lookup"><span data-stu-id="7d0b3-256">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-257">SIP。 &lt;microsoft.rtc.management.xds.sipdomain &gt; (每個 SIP 網域需要一個專案) </span><span class="sxs-lookup"><span data-stu-id="7d0b3-257">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="7d0b3-258">SN = sba01SAN = sip .com;SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="7d0b3-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="7d0b3-259">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7d0b3-259">See Also</span></span>


[<span data-ttu-id="7d0b3-260">Lync Server 2013 中的萬用字元憑證支援</span><span class="sxs-lookup"><span data-stu-id="7d0b3-260">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

