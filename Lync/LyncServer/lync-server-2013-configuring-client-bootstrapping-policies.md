---
title: Lync Server 2013：設定用戶端引導原則
description: Lync Server 2013：設定用戶端引導原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c03a9f7954d42f128dd6ae96296069ae5a515e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545629"
---
# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a><span data-ttu-id="6b4e4-103">在 Lync Server 2013 中設定用戶端引導原則</span><span class="sxs-lookup"><span data-stu-id="6b4e4-103">Configuring client bootstrapping policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b4e4-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="6b4e4-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="6b4e4-105">群組原則管理主控台 (GPMC) ，而群組原則物件編輯器是您用來管理群組原則的工具。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-105">The Group Policy Management Console (GPMC) and the Group Policy Object Editor are tools that you use to manage Group Policy.</span></span> <span data-ttu-id="6b4e4-106">隨附于 Office 群組原則系統管理範本（Lync)  (2013）和 adml (ADML) 系統管理範本，其中包含您為網域中的 [群組原則] 物件所設定的登錄型原則設定。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-106">Included with the Office Group Policy Administrative Template are Lync 2013.admx (ADMX) and .adml (ADML) Administrative Templates, which contain the registry-based policy settings that you configure for Group Policy objects in the domain.</span></span> <span data-ttu-id="6b4e4-107">ADML 檔案是特定語言對 ADMX 檔案的補充。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-107">ADML files are language-specific complements to ADMX files.</span></span> <span data-ttu-id="6b4e4-108">每個 ADMX 和 ADML 檔案都包含單一 Office 應用程式的原則設定。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-108">Each ADMX and ADML file contains the policy settings for a single Office application.</span></span> <span data-ttu-id="6b4e4-109">如需詳細資訊，請參閱 Office 2013 檔中的「Office 2013 系統管理範本檔案 (ADMX，ADML) 」 <https://go.microsoft.com/fwlink/p/?linkid=267516> 。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-109">For more information, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <https://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<span data-ttu-id="6b4e4-110">對於 Lync 2013，您應該考慮在使用者第一次登入伺服器之前，先考慮一些用戶端引導原則。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-110">For Lync 2013, there are several client bootstrapping policies that you should consider configuring before users sign in to the server for the first time.</span></span> <span data-ttu-id="6b4e4-111">例如，用戶端應使用的預設伺服器及安全性模式，直到登入完成為止。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-111">For example, the default servers and security mode that the client should use until sign-in is complete.</span></span> <span data-ttu-id="6b4e4-112">您可以使用群組原則在使用者的電腦登錄中建立這些設定，然後再登入，並開始從伺服器接收帶內布建設定。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-112">You can use Group Policy to establish these settings in users’ computer registries before they sign in and begin receiving in-band provisioning settings from the server.</span></span> <span data-ttu-id="6b4e4-113">下表列出 Lync 2013 可使用的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-113">The following table lists the Group Policy settings that are available for Lync 2013.</span></span>

### <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="6b4e4-114">Lync 2013 的群組原則設定</span><span class="sxs-lookup"><span data-stu-id="6b4e4-114">Group Policy Settings for Lync 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b4e4-115">群組原則設定</span><span class="sxs-lookup"><span data-stu-id="6b4e4-115">Group Policy setting</span></span></th>
<th><span data-ttu-id="6b4e4-116">描述</span><span class="sxs-lookup"><span data-stu-id="6b4e4-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b4e4-117">指定伺服器</span><span class="sxs-lookup"><span data-stu-id="6b4e4-117">Specify Server</span></span><br />
<span data-ttu-id="6b4e4-118"> (ConfigurationMode) </span><span class="sxs-lookup"><span data-stu-id="6b4e4-118">(ConfigurationMode)</span></span></p></td>
<td><p><span data-ttu-id="6b4e4-119">指定 Lync 2013 如何識別登入期間使用的傳輸和伺服器。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-119">Specifies how Lync 2013 identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="6b4e4-120">在此設定中，您可以指定下列專案：</span><span class="sxs-lookup"><span data-stu-id="6b4e4-120">Within this setting, you specify the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6b4e4-121">ServerAddressExternal：指定從外部防火牆外部連線時，用戶端和同盟連絡人所使用的伺服器名稱或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-121">ServerAddressExternal: Specifies the server name or IP address used by clients and federated contacts when connecting from outside the external firewall.</span></span></p></li>
<li><p><span data-ttu-id="6b4e4-122">ServerAddressInternal：指定用戶端從組織防火牆內部連線時所使用的伺服器名稱或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-122">ServerAddressInternal: Specifies the server name or IP address used when clients connect from inside the organization’s firewall.</span></span></p></li>
<li><p><span data-ttu-id="6b4e4-123">Transport：指定傳輸控制通訊協定 (TCP) 或傳輸層安全性 (TLS) 。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-123">Transport: Specifies either Transmission Control Protocol (TCP) or Transport Layer Security (TLS).</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b4e4-124">其他支援的伺服器版本</span><span class="sxs-lookup"><span data-stu-id="6b4e4-124">Additional server versions supported</span></span><br />
<span data-ttu-id="6b4e4-125"> (ConfiguredServerCheckValues) </span><span class="sxs-lookup"><span data-stu-id="6b4e4-125">(ConfiguredServerCheckValues)</span></span></p></td>
<td><p><span data-ttu-id="6b4e4-126">指定除了預設所支援的伺服器版本之外，Lync Server 2013 會登入的伺服器版本名稱清單，並以分號分隔。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-126">Specifies a list of server version names separated by semi-colons that Lync Server 2013 will log on to, in addition to the server versions that are supported by default.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b4e4-127">停用自動上傳失敗記錄 (DisableAutomaticSendTracing) </span><span class="sxs-lookup"><span data-stu-id="6b4e4-127">Disable automatic upload of sign-in failure logs (DisableAutomaticSendTracing)</span></span></p></td>
<td><p><span data-ttu-id="6b4e4-128">自動將登入失敗記錄上傳至 Lync Server 進行分析。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-128">Automatically uploads sign-in failure logs to Lync Server for analysis.</span></span> <span data-ttu-id="6b4e4-129">登入成功時，不會自動上傳記錄。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-129">No logs are automatically uploaded if sign-in is successful.</span></span> <span data-ttu-id="6b4e4-130">若未設定此原則，則會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="6b4e4-130">If this policy is not configured, the following happens:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="6b4e4-131">對於 Lync Online 使用者：可自動上傳登錄失敗記錄。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-131">For Lync Online users: Sign-in failure logs are automatically uploaded.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="6b4e4-132">對於 Lync 內部部署使用者：上傳之前向使用者顯示確認對話方塊。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-132">For Lync on-premises users: A confirmation dialog box is shown to the user before upload.</span></span></p>
</dd>
</dl>
<p><span data-ttu-id="6b4e4-133">停用此設定時，會自動將 Lync 內部部署和 Lync Online 使用者的登入記錄上傳至 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-133">When this setting is disabled, sign-in logs are automatically uploaded to the Lync Server for both Lync on-premises and Lync Online users.</span></span> <span data-ttu-id="6b4e4-134">啟用此設定時，將不會自動上傳登入記錄。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-134">When this setting is enabled, sign-in logs are never uploaded automatically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b4e4-135">停用 SIP 連線的 HTTP 回退</span><span class="sxs-lookup"><span data-stu-id="6b4e4-135">Disable HTTP fallback for SIP connection</span></span><br />
<span data-ttu-id="6b4e4-136"> (DisableHttpConnect) </span><span class="sxs-lookup"><span data-stu-id="6b4e4-136">(DisableHttpConnect)</span></span></p></td>
<td><p><span data-ttu-id="6b4e4-137">當 TLS 或 TCP 無法使用時，禁止 Lync 伺服器嘗試使用 HTTP 連線到伺服器。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-137">Prevents Lync Server from trying to connect to the server by using HTTP, if TLS or TCP are unavailable.</span></span> <span data-ttu-id="6b4e4-138">依預設，Lync 會先使用 TLS 或 TCP 嘗試連線至伺服器，如果兩個傳輸方法都沒有成功，Lync 會嘗試使用 HTTP 進行連線。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-138">By default, Lync first attempts to connect to the server by using TLS or TCP and, if neither of these transport methods is successful, Lync tries to connect by using HTTP.</span></span> <span data-ttu-id="6b4e4-139">使用此原則可停用後援 HTTP 連線嘗試。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-139">Use this policy to disable the fallback HTTP connection attempt.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b4e4-140">需要登入認證</span><span class="sxs-lookup"><span data-stu-id="6b4e4-140">Require logon credentials</span></span><br />
<span data-ttu-id="6b4e4-141"> (DisableNTCredentials) </span><span class="sxs-lookup"><span data-stu-id="6b4e4-141">(DisableNTCredentials)</span></span></p></td>
<td><p><span data-ttu-id="6b4e4-142">需要使用者提供 Lync 的登入認證，而不會在登入 SIP 伺服器期間自動使用 Windows 認證。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-142">Requires the user to provide logon credentials for Lync rather than automatically using Windows credentials during sign-in to a SIP server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b4e4-143">停用伺服器版本檢查</span><span class="sxs-lookup"><span data-stu-id="6b4e4-143">Disable server version check</span></span><br />
<span data-ttu-id="6b4e4-144"> (DisableServerCheck) </span><span class="sxs-lookup"><span data-stu-id="6b4e4-144">(DisableServerCheck)</span></span></p></td>
<td><p><span data-ttu-id="6b4e4-145">如果您將此原則設為1，請在登入前，禁止 Lync 檢查伺服器名稱及版本。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-145">If you set this policy to 1, prevents Lync from checking the server name and version before signing in.</span></span> <span data-ttu-id="6b4e4-146">根據預設，Lync 會在登入前進行這些檢查。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-146">By default, Lync makes these checks before signing in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b4e4-147">啟用使用 BITS 下載通訊錄服務檔案</span><span class="sxs-lookup"><span data-stu-id="6b4e4-147">Enable using BITS to download Address Book Service files</span></span><br />
<span data-ttu-id="6b4e4-148"> (EnableBitsForGalDownload) </span><span class="sxs-lookup"><span data-stu-id="6b4e4-148">(EnableBitsForGalDownload)</span></span></p></td>
<td><p><span data-ttu-id="6b4e4-149">可讓 Lync 使用後臺智慧傳輸服務 (BITS) 下載通訊錄服務檔案。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-149">Enables Lync to use Background Intelligent Transfer Service (BITS) to download the Address Book Services files.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b4e4-150">設定 SIP 安全性模式</span><span class="sxs-lookup"><span data-stu-id="6b4e4-150">Configure SIP security mode</span></span><br />
<span data-ttu-id="6b4e4-151"> (EnableSIPHighSecurityMode) </span><span class="sxs-lookup"><span data-stu-id="6b4e4-151">(EnableSIPHighSecurityMode)</span></span></p></td>
<td><p><span data-ttu-id="6b4e4-152">可讓 Lync 更安全地傳送和接收立即訊息。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-152">Enables Lync to send and receive instant messages more securely.</span></span> <span data-ttu-id="6b4e4-153">這個原則對 Windows .NET 或 Microsoft Exchange Server 服務沒有任何作用。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-153">This policy has no effect on Windows .NET or Microsoft Exchange Server services.</span></span></p>
<p><span data-ttu-id="6b4e4-154">如果您未設定此原則設定，Lync 可以使用任何傳輸。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-154">If you do not configure this policy setting, Lync can use any transport.</span></span> <span data-ttu-id="6b4e4-155">不過，如果它不使用 TLS，而且伺服器驗證使用者，Lync 必須使用 NTLM 或 Kerberos 驗證。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-155">But if it does not use TLS and if the server authenticates users, Lync must use either NTLM or Kerberos authentication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b4e4-156">全域通訊錄下載初始延遲</span><span class="sxs-lookup"><span data-stu-id="6b4e4-156">Global Address Book Download Initial Delay</span></span><br />
<span data-ttu-id="6b4e4-157"> (GalDownloadInitialDelay) </span><span class="sxs-lookup"><span data-stu-id="6b4e4-157">(GalDownloadInitialDelay)</span></span></p></td>
<td><p><span data-ttu-id="6b4e4-158">會指定在 (GAL) 中下載全域通訊清單之前的時間週期。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-158">Specifies the time period before a download of the global address list (GAL) occurs.</span></span> <span data-ttu-id="6b4e4-159">預設值為60分鐘，這表示伺服器會延遲下載 GAL 檔案，其隨機期限介於0到60分鐘之間。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-159">The default value is 60 minutes, which means the server delays the download of GAL file for a random period of between 0 and 60 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b4e4-160">防止使用者執行 Microsoft Lync</span><span class="sxs-lookup"><span data-stu-id="6b4e4-160">Prevent users from running Microsoft Lync</span></span><br />
<span data-ttu-id="6b4e4-161"> (PreventRun) </span><span class="sxs-lookup"><span data-stu-id="6b4e4-161">(PreventRun)</span></span></p></td>
<td><p><span data-ttu-id="6b4e4-162">防止使用者執行 Lync。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-162">Prevents users from running Lync.</span></span> <span data-ttu-id="6b4e4-163">您可在「電腦設定」和「使用者設定」中設定此原則設定，但系統會優先使用「電腦設定」中的原則設定。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-163">You can configure this policy setting under both Computer Configuration and User Configuration, but the policy setting under Computer Configuration takes precedence.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b4e4-164">允許儲存使用者密碼</span><span class="sxs-lookup"><span data-stu-id="6b4e4-164">Allow storage of user passwords</span></span><br />
<span data-ttu-id="6b4e4-165"> (SavePassword) </span><span class="sxs-lookup"><span data-stu-id="6b4e4-165">(SavePassword)</span></span></p></td>
<td><p><span data-ttu-id="6b4e4-166">可讓 Lync 儲存密碼。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-166">Enables Lync to store passwords.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b4e4-167">設定 SIP 壓縮模式</span><span class="sxs-lookup"><span data-stu-id="6b4e4-167">Configure SIP compression mode</span></span><br />
<span data-ttu-id="6b4e4-168"> (SipCompression) </span><span class="sxs-lookup"><span data-stu-id="6b4e4-168">(SipCompression)</span></span></p></td>
<td><p><span data-ttu-id="6b4e4-169">指定何時開啟 SIP 壓縮。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-169">Specifies when to turn on SIP compression.</span></span> <span data-ttu-id="6b4e4-170">根據預設，以配接器速度啟用 SIP 壓縮。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-170">By default, SIP compression is enabled based on the adapter speed.</span></span> <span data-ttu-id="6b4e4-171">請注意，設定此原則可能導致登入時間變長。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-171">Note that setting this policy might cause an increase in sign-in time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b4e4-172">受信任的網域清單</span><span class="sxs-lookup"><span data-stu-id="6b4e4-172">Trusted Domain List</span></span><br />
<span data-ttu-id="6b4e4-173"> (TrustModelData) </span><span class="sxs-lookup"><span data-stu-id="6b4e4-173">(TrustModelData)</span></span></p></td>
<td><p><span data-ttu-id="6b4e4-174">列出不符合客戶 SIP 網域首碼的信任網域。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-174">Lists the trusted domains that do not match the prefix of the customer SIP domain.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6b4e4-p113">在伺服器上設定的原則優先於群組原則設定和使用者設定的用戶端選項。下表摘要列出當衝突發生時，設定的優先順序。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-p113">Policies configured on the server take precedence over Group Policy settings and client options configured by the user. The following table summarizes the order in which settings take precedence when a conflict occurs.</span></span>

### <a name="group-policy-precedence"></a><span data-ttu-id="6b4e4-177">群組原則優先順序</span><span class="sxs-lookup"><span data-stu-id="6b4e4-177">Group Policy Precedence</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b4e4-178">Precedence</span><span class="sxs-lookup"><span data-stu-id="6b4e4-178">Precedence</span></span></th>
<th><span data-ttu-id="6b4e4-179">設定的位置或方法</span><span class="sxs-lookup"><span data-stu-id="6b4e4-179">Location or Method of Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b4e4-180">1 </span><span class="sxs-lookup"><span data-stu-id="6b4e4-180">1</span></span></p></td>
<td><p><span data-ttu-id="6b4e4-181">Lync Server 2013 頻帶內布建</span><span class="sxs-lookup"><span data-stu-id="6b4e4-181">Lync Server 2013 in-band provisioning</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b4e4-182">第</span><span class="sxs-lookup"><span data-stu-id="6b4e4-182">2</span></span></p></td>
<td><p><span data-ttu-id="6b4e4-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="6b4e4-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b4e4-184">個</span><span class="sxs-lookup"><span data-stu-id="6b4e4-184">3</span></span></p></td>
<td><p><span data-ttu-id="6b4e4-185">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="6b4e4-185">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b4e4-186">4 </span><span class="sxs-lookup"><span data-stu-id="6b4e4-186">4</span></span></p></td>
<td><p><span data-ttu-id="6b4e4-187">Lync 2013 中的 [Lync-選項] 對話方塊</span><span class="sxs-lookup"><span data-stu-id="6b4e4-187">The Lync - Options dialog box in Lync 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a><span data-ttu-id="6b4e4-188">使用 Lync 2013 系統管理範本檔案定義群組原則設定</span><span class="sxs-lookup"><span data-stu-id="6b4e4-188">To define Group Policy settings by using the Lync 2013 administrative template files</span></span>

1.  <span data-ttu-id="6b4e4-189">建立根層級的資料夾，以包含所有語言中立的 ADMX 檔案。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-189">Create a root-level folder to contain all language-neutral ADMX files.</span></span> <span data-ttu-id="6b4e4-190">例如，在此位置的網域控制站上建立中央存放區的根資料夾：</span><span class="sxs-lookup"><span data-stu-id="6b4e4-190">For example, create the root folder for the central store on your domain controller at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6b4e4-191">此程式假設您要管理網域中的多部電腦。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-191">This procedure assumes that you want to manage multiple computers in your domain.</span></span> <span data-ttu-id="6b4e4-192">在此情況下，您可以將範本儲存在網域主控站的 Sysvol 資料夾中的中央存放區。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-192">In this case, you store the templates in a central store in the Sysvol folder on the primary domain controller.</span></span> <span data-ttu-id="6b4e4-193">這會為網域系統管理範本提供複製的中央儲存位置。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-193">This provides a replicated central storage location for domain Administrative Templates.</span></span>

    
    </div>

2.  <span data-ttu-id="6b4e4-194">為您要使用的每一種語言建立子資料夾。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-194">Create a subfolder for each language that you’ll use.</span></span> <span data-ttu-id="6b4e4-195">這些子資料夾將會包含特定語言的 ADML 資源檔。</span><span class="sxs-lookup"><span data-stu-id="6b4e4-195">These subfolders will contain the language-specific ADML resource files.</span></span> <span data-ttu-id="6b4e4-196">例如，在此位置，為美國英文 (EN-US) 建立子資料夾：</span><span class="sxs-lookup"><span data-stu-id="6b4e4-196">For example, create a subfolder for United States English (EN-US) at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

