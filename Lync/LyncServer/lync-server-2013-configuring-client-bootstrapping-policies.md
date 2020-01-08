---
title: Lync Server 2013：設定用戶端引導原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring client bootstrapping policies
ms:assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425941(v=OCS.15)
ms:contentKeyID: 48184031
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06119d5488b47adfe01a934aca9a55581feaf33e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976970"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a><span data-ttu-id="322d0-102">在 Lync Server 2013 中設定用戶端引導原則</span><span class="sxs-lookup"><span data-stu-id="322d0-102">Configuring client bootstrapping policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="322d0-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="322d0-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="322d0-104">群組原則管理主控台（GPMC）和群組原則物件編輯器是您用來管理群組原則的工具。</span><span class="sxs-lookup"><span data-stu-id="322d0-104">The Group Policy Management Console (GPMC) and the Group Policy Object Editor are tools that you use to manage Group Policy.</span></span> <span data-ttu-id="322d0-105">Office 群組原則管理範本隨附于 Lync 2013 與 adml （ADML）系統管理範本，其中包含您針對網域中的 [群組原則] 物件所設定的登錄型原則設定。</span><span class="sxs-lookup"><span data-stu-id="322d0-105">Included with the Office Group Policy Administrative Template are Lync 2013.admx (ADMX) and .adml (ADML) Administrative Templates, which contain the registry-based policy settings that you configure for Group Policy objects in the domain.</span></span> <span data-ttu-id="322d0-106">ADML 檔案是對 ADMX 檔案的語言特定補充。</span><span class="sxs-lookup"><span data-stu-id="322d0-106">ADML files are language-specific complements to ADMX files.</span></span> <span data-ttu-id="322d0-107">每個 ADMX 與 ADML 檔案都包含單一 Office 應用程式的原則設定。</span><span class="sxs-lookup"><span data-stu-id="322d0-107">Each ADMX and ADML file contains the policy settings for a single Office application.</span></span> <span data-ttu-id="322d0-108">如需詳細資訊，請參閱 Office 2013 檔中的「Office 2013 管理範本檔案（ADMX、ADML） <http://go.microsoft.com/fwlink/p/?linkid=267516>」。</span><span class="sxs-lookup"><span data-stu-id="322d0-108">For more information, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<span data-ttu-id="322d0-109">在 Lync 2013 中，有數個用戶端的引導原則，您必須先考慮在使用者第一次登入伺服器前進行設定。</span><span class="sxs-lookup"><span data-stu-id="322d0-109">For Lync 2013, there are several client bootstrapping policies that you should consider configuring before users sign in to the server for the first time.</span></span> <span data-ttu-id="322d0-110">例如，用戶端在登入完成之前應該要使用的預設伺服器和安全模式。</span><span class="sxs-lookup"><span data-stu-id="322d0-110">For example, the default servers and security mode that the client should use until sign-in is complete.</span></span> <span data-ttu-id="322d0-111">您可以使用群組原則在使用者的電腦註冊表中建立這些設定，然後再登入並開始從伺服器接收帶外的提供設定設定。</span><span class="sxs-lookup"><span data-stu-id="322d0-111">You can use Group Policy to establish these settings in users’ computer registries before they sign in and begin receiving in-band provisioning settings from the server.</span></span> <span data-ttu-id="322d0-112">下表列出 Lync 2013 可用的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="322d0-112">The following table lists the Group Policy settings that are available for Lync 2013.</span></span>

### <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="322d0-113">Lync 2013 的群組原則設定</span><span class="sxs-lookup"><span data-stu-id="322d0-113">Group Policy Settings for Lync 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="322d0-114">群組原則設定</span><span class="sxs-lookup"><span data-stu-id="322d0-114">Group Policy setting</span></span></th>
<th><span data-ttu-id="322d0-115">描述</span><span class="sxs-lookup"><span data-stu-id="322d0-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="322d0-116">指定伺服器</span><span class="sxs-lookup"><span data-stu-id="322d0-116">Specify Server</span></span><br />
<span data-ttu-id="322d0-117">(ConfigurationMode)</span><span class="sxs-lookup"><span data-stu-id="322d0-117">(ConfigurationMode)</span></span></p></td>
<td><p><span data-ttu-id="322d0-118">指定 Lync 2013 如何識別登入期間要使用的傳輸與伺服器。</span><span class="sxs-lookup"><span data-stu-id="322d0-118">Specifies how Lync 2013 identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="322d0-119">在此設定中，您指定下列各項：</span><span class="sxs-lookup"><span data-stu-id="322d0-119">Within this setting, you specify the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="322d0-120">ServerAddressExternal：指定從外部防火牆外部連線時，用戶端和同盟連絡人所使用的伺服器名稱或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="322d0-120">ServerAddressExternal: Specifies the server name or IP address used by clients and federated contacts when connecting from outside the external firewall.</span></span></p></li>
<li><p><span data-ttu-id="322d0-121">ServerAddressInternal：指定用戶端從組織的防火牆內連線時所使用的伺服器名稱或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="322d0-121">ServerAddressInternal: Specifies the server name or IP address used when clients connect from inside the organization’s firewall.</span></span></p></li>
<li><p><span data-ttu-id="322d0-122">傳輸：指定傳輸控制通訊協定（TCP）或傳輸層安全性（TLS）。</span><span class="sxs-lookup"><span data-stu-id="322d0-122">Transport: Specifies either Transmission Control Protocol (TCP) or Transport Layer Security (TLS).</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322d0-123">支援的其他伺服器版本</span><span class="sxs-lookup"><span data-stu-id="322d0-123">Additional server versions supported</span></span><br />
<span data-ttu-id="322d0-124">(ConfiguredServerCheckValues)</span><span class="sxs-lookup"><span data-stu-id="322d0-124">(ConfiguredServerCheckValues)</span></span></p></td>
<td><p><span data-ttu-id="322d0-125">指定伺服器版本名稱的清單，除了預設支援的伺服器版本之外，還會使用 Lync Server 2013 將登入的分號來分隔。</span><span class="sxs-lookup"><span data-stu-id="322d0-125">Specifies a list of server version names separated by semi-colons that Lync Server 2013 will log on to, in addition to the server versions that are supported by default.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322d0-126">停用登入失敗記錄的自動上傳（DisableAutomaticSendTracing）</span><span class="sxs-lookup"><span data-stu-id="322d0-126">Disable automatic upload of sign-in failure logs (DisableAutomaticSendTracing)</span></span></p></td>
<td><p><span data-ttu-id="322d0-127">自動將登入失敗記錄上傳到 Lync Server 進行分析。</span><span class="sxs-lookup"><span data-stu-id="322d0-127">Automatically uploads sign-in failure logs to Lync Server for analysis.</span></span> <span data-ttu-id="322d0-128">如果登入成功，則不會自動上傳任何記錄。</span><span class="sxs-lookup"><span data-stu-id="322d0-128">No logs are automatically uploaded if sign-in is successful.</span></span> <span data-ttu-id="322d0-129">如果未設定此原則，就會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="322d0-129">If this policy is not configured, the following happens:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="322d0-130">Lync Online 使用者：系統會自動上傳登入失敗記錄。</span><span class="sxs-lookup"><span data-stu-id="322d0-130">For Lync Online users: Sign-in failure logs are automatically uploaded.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="322d0-131">對於 Lync 內部部署使用者： [上傳] 之前，會向使用者顯示確認對話方塊。</span><span class="sxs-lookup"><span data-stu-id="322d0-131">For Lync on-premises users: A confirmation dialog box is shown to the user before upload.</span></span></p>
</dd>
</dl>
<p><span data-ttu-id="322d0-132">停用此設定時，系統會針對 Lync 內部部署和 Lync Online 使用者自動將登入記錄上傳到 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="322d0-132">When this setting is disabled, sign-in logs are automatically uploaded to the Lync Server for both Lync on-premises and Lync Online users.</span></span> <span data-ttu-id="322d0-133">啟用此設定時，不會自動上傳登入記錄。</span><span class="sxs-lookup"><span data-stu-id="322d0-133">When this setting is enabled, sign-in logs are never uploaded automatically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322d0-134">停用 SIP 連線的 HTTP 回退</span><span class="sxs-lookup"><span data-stu-id="322d0-134">Disable HTTP fallback for SIP connection</span></span><br />
<span data-ttu-id="322d0-135">(DisableHttpConnect)</span><span class="sxs-lookup"><span data-stu-id="322d0-135">(DisableHttpConnect)</span></span></p></td>
<td><p><span data-ttu-id="322d0-136">如果 TLS 或 TCP 無法使用，則禁止 Lync Server 嘗試使用 HTTP 連線到伺服器。</span><span class="sxs-lookup"><span data-stu-id="322d0-136">Prevents Lync Server from trying to connect to the server by using HTTP, if TLS or TCP are unavailable.</span></span> <span data-ttu-id="322d0-137">根據預設，Lync 會先嘗試使用 TLS 或 TCP 連線到伺服器，如果這些傳輸方法都沒有成功，Lync 會嘗試使用 HTTP 進行連線。</span><span class="sxs-lookup"><span data-stu-id="322d0-137">By default, Lync first attempts to connect to the server by using TLS or TCP and, if neither of these transport methods is successful, Lync tries to connect by using HTTP.</span></span> <span data-ttu-id="322d0-138">使用此原則來停用回退 HTTP 連線嘗試。</span><span class="sxs-lookup"><span data-stu-id="322d0-138">Use this policy to disable the fallback HTTP connection attempt.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322d0-139">需要登入認證</span><span class="sxs-lookup"><span data-stu-id="322d0-139">Require logon credentials</span></span><br />
<span data-ttu-id="322d0-140">(DisableNTCredentials)</span><span class="sxs-lookup"><span data-stu-id="322d0-140">(DisableNTCredentials)</span></span></p></td>
<td><p><span data-ttu-id="322d0-141">要求使用者為 Lync 提供登入認證，而不是在登入 SIP 伺服器期間自動使用 Windows 認證。</span><span class="sxs-lookup"><span data-stu-id="322d0-141">Requires the user to provide logon credentials for Lync rather than automatically using Windows credentials during sign-in to a SIP server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322d0-142">停用伺服器版本檢查</span><span class="sxs-lookup"><span data-stu-id="322d0-142">Disable server version check</span></span><br />
<span data-ttu-id="322d0-143">(DisableServerCheck)</span><span class="sxs-lookup"><span data-stu-id="322d0-143">(DisableServerCheck)</span></span></p></td>
<td><p><span data-ttu-id="322d0-144">如果您將此原則設定為1，則會在登入前，避免 Lync 檢查伺服器名稱和版本。</span><span class="sxs-lookup"><span data-stu-id="322d0-144">If you set this policy to 1, prevents Lync from checking the server name and version before signing in.</span></span> <span data-ttu-id="322d0-145">根據預設，Lync 會先進行這些檢查，然後才能登入。</span><span class="sxs-lookup"><span data-stu-id="322d0-145">By default, Lync makes these checks before signing in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322d0-146">啟用 BITS 以下載通訊錄服務檔</span><span class="sxs-lookup"><span data-stu-id="322d0-146">Enable using BITS to download Address Book Service files</span></span><br />
<span data-ttu-id="322d0-147">(EnableBitsForGalDownload)</span><span class="sxs-lookup"><span data-stu-id="322d0-147">(EnableBitsForGalDownload)</span></span></p></td>
<td><p><span data-ttu-id="322d0-148">讓 Lync 使用背景智慧傳輸服務（BITS）下載通訊錄服務檔案。</span><span class="sxs-lookup"><span data-stu-id="322d0-148">Enables Lync to use Background Intelligent Transfer Service (BITS) to download the Address Book Services files.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322d0-149">設定 SIP 安全模式</span><span class="sxs-lookup"><span data-stu-id="322d0-149">Configure SIP security mode</span></span><br />
<span data-ttu-id="322d0-150">(EnableSIPHighSecurityMode)</span><span class="sxs-lookup"><span data-stu-id="322d0-150">(EnableSIPHighSecurityMode)</span></span></p></td>
<td><p><span data-ttu-id="322d0-151">讓 Lync 能更安全地傳送及接收立即訊息。</span><span class="sxs-lookup"><span data-stu-id="322d0-151">Enables Lync to send and receive instant messages more securely.</span></span> <span data-ttu-id="322d0-152">此原則對 Windows .NET 或 Microsoft Exchange Server 服務沒有任何影響。</span><span class="sxs-lookup"><span data-stu-id="322d0-152">This policy has no effect on Windows .NET or Microsoft Exchange Server services.</span></span></p>
<p><span data-ttu-id="322d0-153">如果您未設定此原則設定，Lync 可以使用任何傳輸。</span><span class="sxs-lookup"><span data-stu-id="322d0-153">If you do not configure this policy setting, Lync can use any transport.</span></span> <span data-ttu-id="322d0-154">但如果它不使用 TLS，且伺服器驗證使用者的身份，Lync 必須使用 NTLM 或 Kerberos 驗證。</span><span class="sxs-lookup"><span data-stu-id="322d0-154">But if it does not use TLS and if the server authenticates users, Lync must use either NTLM or Kerberos authentication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322d0-155">全域通訊錄下載初始延遲</span><span class="sxs-lookup"><span data-stu-id="322d0-155">Global Address Book Download Initial Delay</span></span><br />
<span data-ttu-id="322d0-156">(GalDownloadInitialDelay)</span><span class="sxs-lookup"><span data-stu-id="322d0-156">(GalDownloadInitialDelay)</span></span></p></td>
<td><p><span data-ttu-id="322d0-157">指定在下載全域通訊清單（GAL）之前的時間週期。</span><span class="sxs-lookup"><span data-stu-id="322d0-157">Specifies the time period before a download of the global address list (GAL) occurs.</span></span> <span data-ttu-id="322d0-158">預設值為60分鐘，表示伺服器會延遲下載 GAL 檔案，且隨機期間為0到60分鐘。</span><span class="sxs-lookup"><span data-stu-id="322d0-158">The default value is 60 minutes, which means the server delays the download of GAL file for a random period of between 0 and 60 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322d0-159">防止使用者執行 Microsoft Lync</span><span class="sxs-lookup"><span data-stu-id="322d0-159">Prevent users from running Microsoft Lync</span></span><br />
<span data-ttu-id="322d0-160">(PreventRun)</span><span class="sxs-lookup"><span data-stu-id="322d0-160">(PreventRun)</span></span></p></td>
<td><p><span data-ttu-id="322d0-161">防止使用者執行 Lync。</span><span class="sxs-lookup"><span data-stu-id="322d0-161">Prevents users from running Lync.</span></span> <span data-ttu-id="322d0-162">您可以在 [電腦設定] 和 [使用者設定] 底下設定此原則設定，但 [電腦設定] 底下的原則設定優先。</span><span class="sxs-lookup"><span data-stu-id="322d0-162">You can configure this policy setting under both Computer Configuration and User Configuration, but the policy setting under Computer Configuration takes precedence.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322d0-163">允許儲存使用者密碼</span><span class="sxs-lookup"><span data-stu-id="322d0-163">Allow storage of user passwords</span></span><br />
<span data-ttu-id="322d0-164">(SavePassword)</span><span class="sxs-lookup"><span data-stu-id="322d0-164">(SavePassword)</span></span></p></td>
<td><p><span data-ttu-id="322d0-165">啟用 Lync 來儲存密碼。</span><span class="sxs-lookup"><span data-stu-id="322d0-165">Enables Lync to store passwords.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322d0-166">設定 SIP 壓縮模式</span><span class="sxs-lookup"><span data-stu-id="322d0-166">Configure SIP compression mode</span></span><br />
<span data-ttu-id="322d0-167">(SipCompression)</span><span class="sxs-lookup"><span data-stu-id="322d0-167">(SipCompression)</span></span></p></td>
<td><p><span data-ttu-id="322d0-168">指定何時開啟 SIP 壓縮。</span><span class="sxs-lookup"><span data-stu-id="322d0-168">Specifies when to turn on SIP compression.</span></span> <span data-ttu-id="322d0-169">根據預設，SIP 壓縮會根據配接器速度而啟用。</span><span class="sxs-lookup"><span data-stu-id="322d0-169">By default, SIP compression is enabled based on the adapter speed.</span></span> <span data-ttu-id="322d0-170">請注意，設定此原則可能會增加登入時間。</span><span class="sxs-lookup"><span data-stu-id="322d0-170">Note that setting this policy might cause an increase in sign-in time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322d0-171">受信任的網域清單</span><span class="sxs-lookup"><span data-stu-id="322d0-171">Trusted Domain List</span></span><br />
<span data-ttu-id="322d0-172">TrustModelData</span><span class="sxs-lookup"><span data-stu-id="322d0-172">(TrustModelData)</span></span></p></td>
<td><p><span data-ttu-id="322d0-173">列出與客戶 SIP 網域的首碼不相符的信任網域。</span><span class="sxs-lookup"><span data-stu-id="322d0-173">Lists the trusted domains that do not match the prefix of the customer SIP domain.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="322d0-174">在伺服器上設定的原則會優先于使用者設定的群組原則設定和用戶端選項。</span><span class="sxs-lookup"><span data-stu-id="322d0-174">Policies configured on the server take precedence over Group Policy settings and client options configured by the user.</span></span> <span data-ttu-id="322d0-175">下表摘要列出發生衝突時設定的優先順序順序。</span><span class="sxs-lookup"><span data-stu-id="322d0-175">The following table summarizes the order in which settings take precedence when a conflict occurs.</span></span>

### <a name="group-policy-precedence"></a><span data-ttu-id="322d0-176">群組原則優先順序</span><span class="sxs-lookup"><span data-stu-id="322d0-176">Group Policy Precedence</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="322d0-177">高於</span><span class="sxs-lookup"><span data-stu-id="322d0-177">Precedence</span></span></th>
<th><span data-ttu-id="322d0-178">設定的位置或方法</span><span class="sxs-lookup"><span data-stu-id="322d0-178">Location or Method of Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="322d0-179">1</span><span class="sxs-lookup"><span data-stu-id="322d0-179">1</span></span></p></td>
<td><p><span data-ttu-id="322d0-180">Lync Server 2013 內布配</span><span class="sxs-lookup"><span data-stu-id="322d0-180">Lync Server 2013 in-band provisioning</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322d0-181">pplx-2</span><span class="sxs-lookup"><span data-stu-id="322d0-181">2</span></span></p></td>
<td><p><span data-ttu-id="322d0-182">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="322d0-182">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="322d0-183">3</span><span class="sxs-lookup"><span data-stu-id="322d0-183">3</span></span></p></td>
<td><p><span data-ttu-id="322d0-184">HKEY_CURRENT_USER \SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="322d0-184">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="322d0-185">4</span><span class="sxs-lookup"><span data-stu-id="322d0-185">4</span></span></p></td>
<td><p><span data-ttu-id="322d0-186">Lync 2013 中的 [Lync-選項] 對話方塊</span><span class="sxs-lookup"><span data-stu-id="322d0-186">The Lync - Options dialog box in Lync 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a><span data-ttu-id="322d0-187">使用 Lync 2013 系統管理範本檔案來定義群組原則設定</span><span class="sxs-lookup"><span data-stu-id="322d0-187">To define Group Policy settings by using the Lync 2013 administrative template files</span></span>

1.  <span data-ttu-id="322d0-188">建立根層級資料夾，以包含所有語言中立的 ADMX 檔案。</span><span class="sxs-lookup"><span data-stu-id="322d0-188">Create a root-level folder to contain all language-neutral ADMX files.</span></span> <span data-ttu-id="322d0-189">例如，在以下位置為網網域控制站上的中央存放區建立根資料夾：</span><span class="sxs-lookup"><span data-stu-id="322d0-189">For example, create the root folder for the central store on your domain controller at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="322d0-190">這個程式假設您想要管理網域中的多部電腦。</span><span class="sxs-lookup"><span data-stu-id="322d0-190">This procedure assumes that you want to manage multiple computers in your domain.</span></span> <span data-ttu-id="322d0-191">在這種情況下，您會將範本儲存在主要網網域控制站上 Sysvol 資料夾中的中央存放區。</span><span class="sxs-lookup"><span data-stu-id="322d0-191">In this case, you store the templates in a central store in the Sysvol folder on the primary domain controller.</span></span> <span data-ttu-id="322d0-192">這會提供網域系統管理範本的複製中央儲存位置。</span><span class="sxs-lookup"><span data-stu-id="322d0-192">This provides a replicated central storage location for domain Administrative Templates.</span></span>

    
    </div>

2.  <span data-ttu-id="322d0-193">針對您要使用的每個語言建立子資料夾。</span><span class="sxs-lookup"><span data-stu-id="322d0-193">Create a subfolder for each language that you’ll use.</span></span> <span data-ttu-id="322d0-194">這些子資料夾將包含特定語言的 ADML 資源檔案。</span><span class="sxs-lookup"><span data-stu-id="322d0-194">These subfolders will contain the language-specific ADML resource files.</span></span> <span data-ttu-id="322d0-195">例如，在此位置為美國英文（ZH-CN）建立子資料夾：</span><span class="sxs-lookup"><span data-stu-id="322d0-195">For example, create a subfolder for United States English (EN-US) at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

