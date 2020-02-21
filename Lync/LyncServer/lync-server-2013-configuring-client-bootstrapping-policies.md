---
title: Lync Server 2013： 設定用戶端啟動載入原則
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
ms.openlocfilehash: c0a917364c31da4a944f41da586b53bc6a59b6ef
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-client-bootstrapping-policies-in-lync-server-2013"></a><span data-ttu-id="39915-102">設定用戶端啟動載入 Lync Server 2013 中的原則</span><span class="sxs-lookup"><span data-stu-id="39915-102">Configuring client bootstrapping policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39915-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="39915-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="39915-104">群組原則管理主控台 (GPMC) 和群組原則物件編輯器是您用來管理群組原則工具。</span><span class="sxs-lookup"><span data-stu-id="39915-104">The Group Policy Management Console (GPMC) and the Group Policy Object Editor are tools that you use to manage Group Policy.</span></span> <span data-ttu-id="39915-105">隨附於 Office 群組原則系統管理範本是 Lync 2013.admx (ADMX) 以及.adml (ADML) 系統管理範本，其中包含您的網域中的群組原則物件的登錄型原則設定。</span><span class="sxs-lookup"><span data-stu-id="39915-105">Included with the Office Group Policy Administrative Template are Lync 2013.admx (ADMX) and .adml (ADML) Administrative Templates, which contain the registry-based policy settings that you configure for Group Policy objects in the domain.</span></span> <span data-ttu-id="39915-106">ADML 檔案都是特定語言的互補 ADMX 檔案。</span><span class="sxs-lookup"><span data-stu-id="39915-106">ADML files are language-specific complements to ADMX files.</span></span> <span data-ttu-id="39915-107">每個 ADMX 和 ADML 檔案包含單一 Office 應用程式的原則設定。</span><span class="sxs-lookup"><span data-stu-id="39915-107">Each ADMX and ADML file contains the policy settings for a single Office application.</span></span> <span data-ttu-id="39915-108">如需詳細資訊，請參閱 「 Office 2013 Administrative Template files （ADMX，ADML） 」 中的 Office 2013 文件<https://go.microsoft.com/fwlink/p/?linkid=267516>。</span><span class="sxs-lookup"><span data-stu-id="39915-108">For more information, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <https://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<span data-ttu-id="39915-109">Lync 2013 的有幾個用戶端啟動載入原則，您應該考慮設定之前使用者登入伺服器第一次。</span><span class="sxs-lookup"><span data-stu-id="39915-109">For Lync 2013, there are several client bootstrapping policies that you should consider configuring before users sign in to the server for the first time.</span></span> <span data-ttu-id="39915-110">如範例、 預設伺服器和用戶端應該使用直到登入的安全性模式已完成。</span><span class="sxs-lookup"><span data-stu-id="39915-110">For example, the default servers and security mode that the client should use until sign-in is complete.</span></span> <span data-ttu-id="39915-111">您可以使用群組原則來建立使用者的電腦登錄中的這些設定之前他們登入，並開始接收來自伺服器的頻內佈建設定。</span><span class="sxs-lookup"><span data-stu-id="39915-111">You can use Group Policy to establish these settings in users’ computer registries before they sign in and begin receiving in-band provisioning settings from the server.</span></span> <span data-ttu-id="39915-112">下表列出可供 Lync 2013 的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="39915-112">The following table lists the Group Policy settings that are available for Lync 2013.</span></span>

### <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="39915-113">Lync 2013 的群組原則設定</span><span class="sxs-lookup"><span data-stu-id="39915-113">Group Policy Settings for Lync 2013</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39915-114">群組原則設定</span><span class="sxs-lookup"><span data-stu-id="39915-114">Group Policy setting</span></span></th>
<th><span data-ttu-id="39915-115">說明</span><span class="sxs-lookup"><span data-stu-id="39915-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39915-116">指定伺服器</span><span class="sxs-lookup"><span data-stu-id="39915-116">Specify Server</span></span><br />
<span data-ttu-id="39915-117">(ConfigurationMode)</span><span class="sxs-lookup"><span data-stu-id="39915-117">(ConfigurationMode)</span></span></p></td>
<td><p><span data-ttu-id="39915-118">會指定如何 Lync 2013 識別 「 傳輸 」 和 「 登入期間所要使用的伺服器。</span><span class="sxs-lookup"><span data-stu-id="39915-118">Specifies how Lync 2013 identifies the transport and server to use during sign-in.</span></span> <span data-ttu-id="39915-119">此設定，在您指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="39915-119">Within this setting, you specify the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="39915-120">ServerAddressExternal： 指定伺服器名稱或 IP 位址供用戶端及同盟連絡人從外部防火牆連線時。</span><span class="sxs-lookup"><span data-stu-id="39915-120">ServerAddressExternal: Specifies the server name or IP address used by clients and federated contacts when connecting from outside the external firewall.</span></span></p></li>
<li><p><span data-ttu-id="39915-121">ServerAddressInternal： 指定伺服器名稱或用戶端從組織防火牆內部連線時所使用的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="39915-121">ServerAddressInternal: Specifies the server name or IP address used when clients connect from inside the organization’s firewall.</span></span></p></li>
<li><p><span data-ttu-id="39915-122">Transport： 指定傳輸控制通訊協定 (TCP) 或傳輸層安全性 (TLS)。</span><span class="sxs-lookup"><span data-stu-id="39915-122">Transport: Specifies either Transmission Control Protocol (TCP) or Transport Layer Security (TLS).</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39915-123">支援的其他伺服器版本</span><span class="sxs-lookup"><span data-stu-id="39915-123">Additional server versions supported</span></span><br />
<span data-ttu-id="39915-124">(ConfiguredServerCheckValues)</span><span class="sxs-lookup"><span data-stu-id="39915-124">(ConfiguredServerCheckValues)</span></span></p></td>
<td><p><span data-ttu-id="39915-125">會指定以 Lync Server 2013 將登入，此外預設所支援的伺服器版本的分號分隔的伺服器版本名稱的清單。</span><span class="sxs-lookup"><span data-stu-id="39915-125">Specifies a list of server version names separated by semi-colons that Lync Server 2013 will log on to, in addition to the server versions that are supported by default.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39915-126">停用自動上傳的登入失敗記錄 (DisableAutomaticSendTracing)</span><span class="sxs-lookup"><span data-stu-id="39915-126">Disable automatic upload of sign-in failure logs (DisableAutomaticSendTracing)</span></span></p></td>
<td><p><span data-ttu-id="39915-127">自動上傳登入失敗記錄至 Lync Server 進行分析。</span><span class="sxs-lookup"><span data-stu-id="39915-127">Automatically uploads sign-in failure logs to Lync Server for analysis.</span></span> <span data-ttu-id="39915-128">如果登入成功自動上傳沒有記錄檔。</span><span class="sxs-lookup"><span data-stu-id="39915-128">No logs are automatically uploaded if sign-in is successful.</span></span> <span data-ttu-id="39915-129">如果未設定此原則，會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="39915-129">If this policy is not configured, the following happens:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="39915-130">Lync Online 使用者： 登入失敗記錄會自動上傳。</span><span class="sxs-lookup"><span data-stu-id="39915-130">For Lync Online users: Sign-in failure logs are automatically uploaded.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="39915-131">針對 Lync 內部部署使用者： 上載之前對使用者顯示的確認對話方塊中，該資料。</span><span class="sxs-lookup"><span data-stu-id="39915-131">For Lync on-premises users: A confirmation dialog box is shown to the user before upload.</span></span></p>
</dd>
</dl>
<p><span data-ttu-id="39915-132">停用此設定時，登入記錄檔會自動上傳到 Lync 內部部署和 Lync Online 使用者在 Lync 伺服器。</span><span class="sxs-lookup"><span data-stu-id="39915-132">When this setting is disabled, sign-in logs are automatically uploaded to the Lync Server for both Lync on-premises and Lync Online users.</span></span> <span data-ttu-id="39915-133">啟用此設定時，登入記錄檔會永遠不會自動上載。</span><span class="sxs-lookup"><span data-stu-id="39915-133">When this setting is enabled, sign-in logs are never uploaded automatically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39915-134">停用 HTTP 後援 SIP 連線</span><span class="sxs-lookup"><span data-stu-id="39915-134">Disable HTTP fallback for SIP connection</span></span><br />
<span data-ttu-id="39915-135">(DisableHttpConnect)</span><span class="sxs-lookup"><span data-stu-id="39915-135">(DisableHttpConnect)</span></span></p></td>
<td><p><span data-ttu-id="39915-136">Lync Server 可防止嘗試如果無法使用 TLS 或 TCP 使用 HTTP 連線至伺服器。</span><span class="sxs-lookup"><span data-stu-id="39915-136">Prevents Lync Server from trying to connect to the server by using HTTP, if TLS or TCP are unavailable.</span></span> <span data-ttu-id="39915-137">根據預設，Lync 第一次嘗試使用 TLS 或 TCP 連線至伺服器，然後 Lync 如果這些傳輸方法皆未成功，嘗試使用 HTTP 連線。</span><span class="sxs-lookup"><span data-stu-id="39915-137">By default, Lync first attempts to connect to the server by using TLS or TCP and, if neither of these transport methods is successful, Lync tries to connect by using HTTP.</span></span> <span data-ttu-id="39915-138">使用此原則可停用後援 HTTP 連線嘗試。</span><span class="sxs-lookup"><span data-stu-id="39915-138">Use this policy to disable the fallback HTTP connection attempt.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39915-139">需要登入認證</span><span class="sxs-lookup"><span data-stu-id="39915-139">Require logon credentials</span></span><br />
<span data-ttu-id="39915-140">(DisableNTCredentials)</span><span class="sxs-lookup"><span data-stu-id="39915-140">(DisableNTCredentials)</span></span></p></td>
<td><p><span data-ttu-id="39915-141">需要使用者以提供 Lync，而不是使用期間登入 SIP 伺服器的 Windows 認證自動登入認證。</span><span class="sxs-lookup"><span data-stu-id="39915-141">Requires the user to provide logon credentials for Lync rather than automatically using Windows credentials during sign-in to a SIP server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39915-142">停用伺服器版本檢查</span><span class="sxs-lookup"><span data-stu-id="39915-142">Disable server version check</span></span><br />
<span data-ttu-id="39915-143">(DisableServerCheck)</span><span class="sxs-lookup"><span data-stu-id="39915-143">(DisableServerCheck)</span></span></p></td>
<td><p><span data-ttu-id="39915-144">如果您將此原則設定為 1 時，可防止 Lync 登入前先檢查的伺服器名稱和版本。</span><span class="sxs-lookup"><span data-stu-id="39915-144">If you set this policy to 1, prevents Lync from checking the server name and version before signing in.</span></span> <span data-ttu-id="39915-145">根據預設，Lync 進行之前登入這類檢查。</span><span class="sxs-lookup"><span data-stu-id="39915-145">By default, Lync makes these checks before signing in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39915-146">啟用使用位元下載通訊錄服務檔案</span><span class="sxs-lookup"><span data-stu-id="39915-146">Enable using BITS to download Address Book Service files</span></span><br />
<span data-ttu-id="39915-147">(EnableBitsForGalDownload)</span><span class="sxs-lookup"><span data-stu-id="39915-147">(EnableBitsForGalDownload)</span></span></p></td>
<td><p><span data-ttu-id="39915-148">可讓 Lync 使用背景智慧型傳送服務 (BITS) 下載通訊錄服務檔案。</span><span class="sxs-lookup"><span data-stu-id="39915-148">Enables Lync to use Background Intelligent Transfer Service (BITS) to download the Address Book Services files.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39915-149">設定 SIP 安全性模式</span><span class="sxs-lookup"><span data-stu-id="39915-149">Configure SIP security mode</span></span><br />
<span data-ttu-id="39915-150">(EnableSIPHighSecurityMode)</span><span class="sxs-lookup"><span data-stu-id="39915-150">(EnableSIPHighSecurityMode)</span></span></p></td>
<td><p><span data-ttu-id="39915-151">可讓 Lync 傳送和接收立即訊息更安全的方式。</span><span class="sxs-lookup"><span data-stu-id="39915-151">Enables Lync to send and receive instant messages more securely.</span></span> <span data-ttu-id="39915-152">此原則具有不會影響 Windows.NET 或 Microsoft Exchange Server 服務。</span><span class="sxs-lookup"><span data-stu-id="39915-152">This policy has no effect on Windows .NET or Microsoft Exchange Server services.</span></span></p>
<p><span data-ttu-id="39915-153">如果您未設定此原則，Lync 可以使用任何傳輸。</span><span class="sxs-lookup"><span data-stu-id="39915-153">If you do not configure this policy setting, Lync can use any transport.</span></span> <span data-ttu-id="39915-154">但如果它不會使用 TLS 和 Lync server 進行驗證的使用者，如果必須使用 NTLM 或 Kerberos 驗證。</span><span class="sxs-lookup"><span data-stu-id="39915-154">But if it does not use TLS and if the server authenticates users, Lync must use either NTLM or Kerberos authentication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39915-155">全域通訊錄下載初始延遲</span><span class="sxs-lookup"><span data-stu-id="39915-155">Global Address Book Download Initial Delay</span></span><br />
<span data-ttu-id="39915-156">(GalDownloadInitialDelay)</span><span class="sxs-lookup"><span data-stu-id="39915-156">(GalDownloadInitialDelay)</span></span></p></td>
<td><p><span data-ttu-id="39915-157">指定的時間之前的全域通訊清單 (GAL) 下載，就會發生。</span><span class="sxs-lookup"><span data-stu-id="39915-157">Specifies the time period before a download of the global address list (GAL) occurs.</span></span> <span data-ttu-id="39915-158">預設值為 60 分鐘，這表示伺服器延遲介於 0 到 60 分鐘的隨機期間 GAL 檔案下載。</span><span class="sxs-lookup"><span data-stu-id="39915-158">The default value is 60 minutes, which means the server delays the download of GAL file for a random period of between 0 and 60 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39915-159">防止使用者執行 Microsoft Lync</span><span class="sxs-lookup"><span data-stu-id="39915-159">Prevent users from running Microsoft Lync</span></span><br />
<span data-ttu-id="39915-160">(PreventRun)</span><span class="sxs-lookup"><span data-stu-id="39915-160">(PreventRun)</span></span></p></td>
<td><p><span data-ttu-id="39915-161">防止使用者執行 Lync。</span><span class="sxs-lookup"><span data-stu-id="39915-161">Prevents users from running Lync.</span></span> <span data-ttu-id="39915-162">您可在「電腦設定」和「使用者設定」中設定此原則設定，但系統會優先使用「電腦設定」中的原則設定。</span><span class="sxs-lookup"><span data-stu-id="39915-162">You can configure this policy setting under both Computer Configuration and User Configuration, but the policy setting under Computer Configuration takes precedence.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39915-163">允許儲存使用者密碼</span><span class="sxs-lookup"><span data-stu-id="39915-163">Allow storage of user passwords</span></span><br />
<span data-ttu-id="39915-164">(SavePassword)</span><span class="sxs-lookup"><span data-stu-id="39915-164">(SavePassword)</span></span></p></td>
<td><p><span data-ttu-id="39915-165">可讓 Lync 儲存密碼。</span><span class="sxs-lookup"><span data-stu-id="39915-165">Enables Lync to store passwords.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39915-166">設定 SIP 壓縮模式</span><span class="sxs-lookup"><span data-stu-id="39915-166">Configure SIP compression mode</span></span><br />
<span data-ttu-id="39915-167">(SipCompression)</span><span class="sxs-lookup"><span data-stu-id="39915-167">(SipCompression)</span></span></p></td>
<td><p><span data-ttu-id="39915-168">指定何時要開啟 [SIP 壓縮。</span><span class="sxs-lookup"><span data-stu-id="39915-168">Specifies when to turn on SIP compression.</span></span> <span data-ttu-id="39915-169">根據預設，會根據介面卡速度啟用 SIP 壓縮。</span><span class="sxs-lookup"><span data-stu-id="39915-169">By default, SIP compression is enabled based on the adapter speed.</span></span> <span data-ttu-id="39915-170">請注意，設定此原則可能導致登入時間變長。</span><span class="sxs-lookup"><span data-stu-id="39915-170">Note that setting this policy might cause an increase in sign-in time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39915-171">受信任的網域清單</span><span class="sxs-lookup"><span data-stu-id="39915-171">Trusted Domain List</span></span><br />
<span data-ttu-id="39915-172">(TrustModelData)</span><span class="sxs-lookup"><span data-stu-id="39915-172">(TrustModelData)</span></span></p></td>
<td><p><span data-ttu-id="39915-173">列出受信任的網域，不會符合客戶 SIP 網域的前置詞。</span><span class="sxs-lookup"><span data-stu-id="39915-173">Lists the trusted domains that do not match the prefix of the customer SIP domain.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="39915-p113">在伺服器上設定的原則優先於群組原則設定和使用者設定的用戶端選項。下表摘要列出當衝突發生時，設定的優先順序。</span><span class="sxs-lookup"><span data-stu-id="39915-p113">Policies configured on the server take precedence over Group Policy settings and client options configured by the user. The following table summarizes the order in which settings take precedence when a conflict occurs.</span></span>

### <a name="group-policy-precedence"></a><span data-ttu-id="39915-176">群組原則優先順序</span><span class="sxs-lookup"><span data-stu-id="39915-176">Group Policy Precedence</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39915-177">Precedence</span><span class="sxs-lookup"><span data-stu-id="39915-177">Precedence</span></span></th>
<th><span data-ttu-id="39915-178">設定的位置或方法</span><span class="sxs-lookup"><span data-stu-id="39915-178">Location or Method of Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39915-179">1</span><span class="sxs-lookup"><span data-stu-id="39915-179">1</span></span></p></td>
<td><p><span data-ttu-id="39915-180">Lync Server 2013 頻內佈建</span><span class="sxs-lookup"><span data-stu-id="39915-180">Lync Server 2013 in-band provisioning</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39915-181">2</span><span class="sxs-lookup"><span data-stu-id="39915-181">2</span></span></p></td>
<td><p><span data-ttu-id="39915-182">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="39915-182">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39915-183">3</span><span class="sxs-lookup"><span data-stu-id="39915-183">3</span></span></p></td>
<td><p><span data-ttu-id="39915-184">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span><span class="sxs-lookup"><span data-stu-id="39915-184">HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\15.0\Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39915-185">4</span><span class="sxs-lookup"><span data-stu-id="39915-185">4</span></span></p></td>
<td><p><span data-ttu-id="39915-186">[Lync-Lync 2013 中的 [選項] 對話方塊</span><span class="sxs-lookup"><span data-stu-id="39915-186">The Lync - Options dialog box in Lync 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-define-group-policy-settings-by-using-the-lync-2013-administrative-template-files"></a><span data-ttu-id="39915-187">若要使用 Lync 2013 系統管理範本檔案定義群組原則設定</span><span class="sxs-lookup"><span data-stu-id="39915-187">To define Group Policy settings by using the Lync 2013 administrative template files</span></span>

1.  <span data-ttu-id="39915-188">建立包含所有的非語言相關 ADMX 檔案的根層級資料夾。</span><span class="sxs-lookup"><span data-stu-id="39915-188">Create a root-level folder to contain all language-neutral ADMX files.</span></span> <span data-ttu-id="39915-189">例如，您的網域控制站，這個位置上建立集中存放區的根資料夾：</span><span class="sxs-lookup"><span data-stu-id="39915-189">For example, create the root folder for the central store on your domain controller at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="39915-190">此程序假設您想要管理您網域中的多部電腦。</span><span class="sxs-lookup"><span data-stu-id="39915-190">This procedure assumes that you want to manage multiple computers in your domain.</span></span> <span data-ttu-id="39915-191">在此情況下，您可以儲存範本集中存放區中的主要網域控制站的 Sysvol 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="39915-191">In this case, you store the templates in a central store in the Sysvol folder on the primary domain controller.</span></span> <span data-ttu-id="39915-192">此網域系統管理範本提供複製的中央儲存位置。</span><span class="sxs-lookup"><span data-stu-id="39915-192">This provides a replicated central storage location for domain Administrative Templates.</span></span>

    
    </div>

2.  <span data-ttu-id="39915-193">建立您要使用的每種語言的子資料夾。</span><span class="sxs-lookup"><span data-stu-id="39915-193">Create a subfolder for each language that you’ll use.</span></span> <span data-ttu-id="39915-194">這些子資料夾會包含語言專屬 ADML 資源檔案。</span><span class="sxs-lookup"><span data-stu-id="39915-194">These subfolders will contain the language-specific ADML resource files.</span></span> <span data-ttu-id="39915-195">例如，在此位置建立美國英文 (EN-US) 的子資料夾：</span><span class="sxs-lookup"><span data-stu-id="39915-195">For example, create a subfolder for United States English (EN-US) at this location:</span></span>
    
    `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`

</div>

</div>

<span> </span>

</div>

</div>

</div>

