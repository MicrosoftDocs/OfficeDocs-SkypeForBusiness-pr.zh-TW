---
title: Lync Server 2013：行動的部署程式
description: Lync Server 2013：行動的部署程式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for mobility
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690023(v=OCS.15)
ms:contentKeyID: 48184220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b49d69af899f6d9f2ac1db5040d017a9d62ce9eb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551039"
---
# <a name="deployment-process-for-mobility-in-lync-server-2013"></a><span data-ttu-id="ec314-103">Lync Server 2013 中行動的部署程式</span><span class="sxs-lookup"><span data-stu-id="ec314-103">Deployment process for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec314-104">_**主題上次修改日期：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="ec314-104">_**Topic Last Modified:** 2013-02-19_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

<span data-ttu-id="ec314-105">本節說明部署 Lync Server 2013 行動功能所需的步驟順序。</span><span class="sxs-lookup"><span data-stu-id="ec314-105">This section describes the sequence of steps required to deploy the Lync Server 2013 mobility feature.</span></span>

### <a name="mobility-deployment-process"></a><span data-ttu-id="ec314-106">行動性部署程序</span><span class="sxs-lookup"><span data-stu-id="ec314-106">Mobility Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ec314-107">階段</span><span class="sxs-lookup"><span data-stu-id="ec314-107">Phase</span></span></th>
<th><span data-ttu-id="ec314-108">步驟</span><span class="sxs-lookup"><span data-stu-id="ec314-108">Steps</span></span></th>
<th><span data-ttu-id="ec314-109">權限</span><span class="sxs-lookup"><span data-stu-id="ec314-109">Permissions</span></span></th>
<th><span data-ttu-id="ec314-110">部署文件</span><span class="sxs-lookup"><span data-stu-id="ec314-110">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec314-111">建立網域名稱系統 (DNS) 記錄</span><span class="sxs-lookup"><span data-stu-id="ec314-111">Create Domain Name System (DNS) records</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ec314-112">建立內部 DNS CNAME 或 (主機，如果 IPv6，AAAA) 記錄來解析內部自動探索服務 URL。</span><span class="sxs-lookup"><span data-stu-id="ec314-112">Create an internal DNS CNAME or A (host, if IPv6, AAAA) record to resolve the internal Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="ec314-113">建立外部 DNS CNAME 或 (主機，如果 IPv6，AAAA) 記錄來解析外部自動探索服務 URL。</span><span class="sxs-lookup"><span data-stu-id="ec314-113">Create an external DNS CNAME or A (host, if IPv6, AAAA) record to resolve the external Autodiscover Service URL.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ec314-114">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="ec314-114">Domain Admins</span></span></p>
<p><span data-ttu-id="ec314-115">DnsAdmins</span><span class="sxs-lookup"><span data-stu-id="ec314-115">DnsAdmins</span></span></p></td>
<td><p><span data-ttu-id="ec314-116"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">在 Lync Server 2013 中建立自動探索服務的 DNS 記錄</a></span><span class="sxs-lookup"><span data-stu-id="ec314-116"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creating DNS records for the Autodiscover Service in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec314-117">修改憑證</span><span class="sxs-lookup"><span data-stu-id="ec314-117">Modify certificates</span></span></p></td>
<td><p><span data-ttu-id="ec314-118">新增主體替代名稱項目至下列憑證，以支援行動使用者的安全連線：</span><span class="sxs-lookup"><span data-stu-id="ec314-118">Add subject alternative name entries to the following certificates to support secure connections for mobile users:</span></span></p>
<ul>
<li><p><span data-ttu-id="ec314-119">Director 憑證</span><span class="sxs-lookup"><span data-stu-id="ec314-119">Director certificate</span></span></p></li>
<li><p><span data-ttu-id="ec314-120">前端集區憑證</span><span class="sxs-lookup"><span data-stu-id="ec314-120">Front End pool certificate</span></span></p></li>
<li><p><span data-ttu-id="ec314-121">反向 Proxy 憑證</span><span class="sxs-lookup"><span data-stu-id="ec314-121">Reverse proxy certificate</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ec314-122">本機系統管理員</span><span class="sxs-lookup"><span data-stu-id="ec314-122">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="ec314-123"><a href="lync-server-2013-modifying-certificates-for-mobility.md">在 Lync Server 2013 中修改行動憑證</a></span><span class="sxs-lookup"><span data-stu-id="ec314-123"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifying certificates for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec314-124">設定反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="ec314-124">Configure the reverse proxy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ec314-125">將以主體替代名稱更新的憑證指派給 Secure Sockets Layer (SSL) 接聽程式。</span><span class="sxs-lookup"><span data-stu-id="ec314-125">Assign certificates updated with subject alternative names to the Secure Sockets Layer (SSL) Listener.</span></span></p></li>
<li><p><span data-ttu-id="ec314-126">重新設定外部自動探索服務 URL 的 web 發行規則。</span><span class="sxs-lookup"><span data-stu-id="ec314-126">Reconfigure the web publishing rule for the external Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="ec314-127">請確定前端集區上的外部 Lync Server 2013 Web 服務 URL 已存在 web 發佈規則。</span><span class="sxs-lookup"><span data-stu-id="ec314-127">Be sure that a web publishing rule exists for the external Lync Server 2013 Web Services URL on your Front End pool.</span></span></p></li>
</ul>
<p><span data-ttu-id="ec314-128">或者</span><span class="sxs-lookup"><span data-stu-id="ec314-128">Or</span></span></p>
<ul>
<li><p><span data-ttu-id="ec314-129">如果您選擇使用 HTTP 來進行初始自動探索要求，但沒有更新憑證上的主體替代名稱清單，請為埠 80 HTTP 設定新的 web 發行規則或重新設定現有的發行規則。</span><span class="sxs-lookup"><span data-stu-id="ec314-129">If you choose to use HTTP for the initial Autodiscover request and do not update subject alternative name lists on the certificates, configure a new web publishing rule or reconfigure an existing publishing rule for port 80 HTTP.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ec314-130">本機系統管理員</span><span class="sxs-lookup"><span data-stu-id="ec314-130">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="ec314-131"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">在 Lync Server 2013 中設定行動的反向 proxy</a></span><span class="sxs-lookup"><span data-stu-id="ec314-131"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec314-132">使用 Mcx 行動性服務，針對 Lync 2010 Mobile 測試行動性部署</span><span class="sxs-lookup"><span data-stu-id="ec314-132">Test your mobility deployment for Lync 2010 Mobile using the Mcx Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="ec314-133">執行 <strong>Test-CsMcxP2PIM</strong>，以測試從一個人傳送立即訊息給另一個人。</span><span class="sxs-lookup"><span data-stu-id="ec314-133">Run <strong>Test-CsMcxP2PIM</strong> to test sending an instant message from one person to another.</span></span></p>
<p><span data-ttu-id="ec314-134">如需完整的選項清單，請參閱 Lync Server Management Shell Cmdlet 檔，以取得 <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> 。</span><span class="sxs-lookup"><span data-stu-id="ec314-134">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="ec314-135">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ec314-135">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ec314-136"><a href="lync-server-2013-verifying-your-mobility-deployment.md">在 Lync Server 2013 中驗證行動性部署</a></span><span class="sxs-lookup"><span data-stu-id="ec314-136"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec314-137">使用 UCWA Web 元件測試您的 Lync 2013 行動用戶端行動性部署</span><span class="sxs-lookup"><span data-stu-id="ec314-137">Test your mobility deployment for Lync 2013 Mobile clients using the UCWA Web components</span></span></p></td>
<td><p><span data-ttu-id="ec314-138">使用 <strong>Test-CsUcwaConference</strong> Cmdlet 來測試及驗證預先定義的測試使用者或一組實際的使用者可以使用 UCWA 來建立及參與會議。</span><span class="sxs-lookup"><span data-stu-id="ec314-138">Use the <strong>Test-CsUcwaConference</strong> cmdlet to test and verify that pre-defined test users or a pair of actual users can use UCWA to create and participate in a conference.</span></span></p>
<p><span data-ttu-id="ec314-139">如需完整的選項清單，請參閱 Lync Server Management Shell Cmdlet 檔，以取得 <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> 。</span><span class="sxs-lookup"><span data-stu-id="ec314-139">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="ec314-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ec314-140">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ec314-141"><a href="lync-server-2013-verifying-your-mobility-deployment.md">在 Lync Server 2013 中驗證行動性部署</a></span><span class="sxs-lookup"><span data-stu-id="ec314-141"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec314-142">設定推入通知</span><span class="sxs-lookup"><span data-stu-id="ec314-142">Configure for push notifications</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ec314-143">針對 Lync Server 2013 Edge server，新增 Lync Server online 主機服務提供者，並設定裝載提供者同盟。</span><span class="sxs-lookup"><span data-stu-id="ec314-143">For Lync Server 2013 Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="ec314-144">針對 Lync Server 2010 Edge server，新增 Lync Server online 主機服務提供者，並設定裝載提供者同盟。</span><span class="sxs-lookup"><span data-stu-id="ec314-144">For Lync Server 2010  Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="ec314-145">若為 Office 通訊伺服器 2007 R2 Edge Server，請新增同盟協力廠商。</span><span class="sxs-lookup"><span data-stu-id="ec314-145">For Office Communications Server 2007 R2 Edge Servers, add a federated partner.</span></span></p></li>
<li><p><span data-ttu-id="ec314-146">如果您要透過 Wi-Fi 網路來支援推入通知，請設定 TCP 連接埠 5223 的防火牆規則輸出。</span><span class="sxs-lookup"><span data-stu-id="ec314-146">If you want to support push notifications over a Wi-Fi network, configure a firewall rule outbound for TCP port 5223.</span></span></p></li>
<li><p><span data-ttu-id="ec314-147">使用 <strong>Set-CsPushNotificationConfiguration</strong> Cmdlet 來啟用推入通知至 Apple Push Notification Service (APNS) 及 Microsoft Push Notification Service (MPNS)。</span><span class="sxs-lookup"><span data-stu-id="ec314-147">Use the <strong>Set-CsPushNotificationConfiguration</strong> cmdlet to enable push notifications to the Apple Push Notification Service (APNS) and Microsoft Push Notification Service (MPNS).</span></span> <span data-ttu-id="ec314-148">此功能預設為停用。</span><span class="sxs-lookup"><span data-stu-id="ec314-148">This feature is disabled by default.</span></span></p></li>
<li><p><span data-ttu-id="ec314-149">使用 <strong>Test-CsFederatedPartner</strong> Cmdlet 來測試同盟設定，並使用 <strong>Test-CsMCXPushNotification</strong> Cmdlet 來測試推入通知。</span><span class="sxs-lookup"><span data-stu-id="ec314-149">Use the <strong>Test-CsFederatedPartner</strong> cmdlet to test the federation configuration and the <strong>Test-CsMCXPushNotification</strong> cmdlet to test push notifications.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="ec314-150">用於 Apple 裝置和 Windows Phone 上的 Lync 2010 行動用戶端的推播通知</span><span class="sxs-lookup"><span data-stu-id="ec314-150">Push notifications are used for Lync 2010 Mobile clients on Apple devices and Windows Phone</span></span><BR><span data-ttu-id="ec314-151">僅限 Windows Phone 上的 Lync 2013 行動用戶端要求推播通知</span><span class="sxs-lookup"><span data-stu-id="ec314-151">Push notification is required for Lync 2013 Mobile clients on Windows Phone only</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="ec314-152">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ec314-152">RtcUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="ec314-153"><a href="lync-server-2013-configuring-for-push-notifications.md">在 Lync Server 2013 中設定推播通知</a></span><span class="sxs-lookup"><span data-stu-id="ec314-153"><a href="lync-server-2013-configuring-for-push-notifications.md">Configuring for push notifications in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec314-154">設定行動原則</span><span class="sxs-lookup"><span data-stu-id="ec314-154">Configure mobility policy</span></span></p></td>
<td><p><span data-ttu-id="ec314-155">使用 <strong>Set-CsMobilityPolicy</strong> Cmdlet 可允許或禁止：</span><span class="sxs-lookup"><span data-stu-id="ec314-155">Use the <strong>Set-CsMobilityPolicy</strong> cmdlet to allow or disallow:</span></span></p>
<ul>
<li><p><span data-ttu-id="ec314-156">從公司通話</span><span class="sxs-lookup"><span data-stu-id="ec314-156">Call via Work</span></span></p></li>
<li><p><span data-ttu-id="ec314-157">啟用 IP 音訊和 IP 影片</span><span class="sxs-lookup"><span data-stu-id="ec314-157">Enable IP Audio and IP Video</span></span></p></li>
<li><p><span data-ttu-id="ec314-158">需要 IP 音訊和/或 IP 影片的 WiFi</span><span class="sxs-lookup"><span data-stu-id="ec314-158">Require WiFi for IP Audio and/or IP Video</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ec314-159">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ec314-159">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ec314-160"><a href="lync-server-2013-configuring-mobility-policy.md">在 Lync Server 2013 中設定行動性原則</a></span><span class="sxs-lookup"><span data-stu-id="ec314-160"><a href="lync-server-2013-configuring-mobility-policy.md">Configuring mobility policy in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

