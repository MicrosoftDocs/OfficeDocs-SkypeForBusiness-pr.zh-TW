---
title: Lync Server 2013：行動的部署程序
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
ms.openlocfilehash: c6f9f7994981a860aaa02d4674d6a3248c3593d6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a><span data-ttu-id="0e02c-102">Lync Server 2013 中行動的部署程序</span><span class="sxs-lookup"><span data-stu-id="0e02c-102">Deployment process for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e02c-103">_**主題上次修改日期：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="0e02c-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

<span data-ttu-id="0e02c-104">本節說明部署 Lync Server 2013 行動功能所需的步驟順序。</span><span class="sxs-lookup"><span data-stu-id="0e02c-104">This section describes the sequence of steps required to deploy the Lync Server 2013 mobility feature.</span></span>

### <a name="mobility-deployment-process"></a><span data-ttu-id="0e02c-105">行動部署流程</span><span class="sxs-lookup"><span data-stu-id="0e02c-105">Mobility Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e02c-106">分</span><span class="sxs-lookup"><span data-stu-id="0e02c-106">Phase</span></span></th>
<th><span data-ttu-id="0e02c-107">步驟</span><span class="sxs-lookup"><span data-stu-id="0e02c-107">Steps</span></span></th>
<th><span data-ttu-id="0e02c-108">許可權</span><span class="sxs-lookup"><span data-stu-id="0e02c-108">Permissions</span></span></th>
<th><span data-ttu-id="0e02c-109">部署檔</span><span class="sxs-lookup"><span data-stu-id="0e02c-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e02c-110">建立網域名稱系統（DNS）記錄</span><span class="sxs-lookup"><span data-stu-id="0e02c-110">Create Domain Name System (DNS) records</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0e02c-111">建立內部 DNS CNAME 或 A （如果是 IPv6、AAAA）記錄，以解析內部自動探索服務 URL。</span><span class="sxs-lookup"><span data-stu-id="0e02c-111">Create an internal DNS CNAME or A (host, if IPv6, AAAA) record to resolve the internal Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="0e02c-112">建立外部 DNS CNAME 或 A （如果是 IPv6、AAAA）記錄，以解析外部自動探索服務 URL。</span><span class="sxs-lookup"><span data-stu-id="0e02c-112">Create an external DNS CNAME or A (host, if IPv6, AAAA) record to resolve the external Autodiscover Service URL.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0e02c-113">網域管理員</span><span class="sxs-lookup"><span data-stu-id="0e02c-113">Domain Admins</span></span></p>
<p><span data-ttu-id="0e02c-114">DnsAdmins</span><span class="sxs-lookup"><span data-stu-id="0e02c-114">DnsAdmins</span></span></p></td>
<td><p><span data-ttu-id="0e02c-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">在 Lync Server 2013 中建立自動探索服務的 DNS 記錄</a></span><span class="sxs-lookup"><span data-stu-id="0e02c-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creating DNS records for the Autodiscover Service in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e02c-116">修改憑證</span><span class="sxs-lookup"><span data-stu-id="0e02c-116">Modify certificates</span></span></p></td>
<td><p><span data-ttu-id="0e02c-117">將消費者備用名稱專案新增至下列憑證，以支援行動使用者的安全連線：</span><span class="sxs-lookup"><span data-stu-id="0e02c-117">Add subject alternative name entries to the following certificates to support secure connections for mobile users:</span></span></p>
<ul>
<li><p><span data-ttu-id="0e02c-118">導演憑證</span><span class="sxs-lookup"><span data-stu-id="0e02c-118">Director certificate</span></span></p></li>
<li><p><span data-ttu-id="0e02c-119">前端池憑證</span><span class="sxs-lookup"><span data-stu-id="0e02c-119">Front End pool certificate</span></span></p></li>
<li><p><span data-ttu-id="0e02c-120">反向 proxy 憑證</span><span class="sxs-lookup"><span data-stu-id="0e02c-120">Reverse proxy certificate</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0e02c-121">本機系統管理員</span><span class="sxs-lookup"><span data-stu-id="0e02c-121">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="0e02c-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">在 Lync Server 2013 中修改行動憑證</a></span><span class="sxs-lookup"><span data-stu-id="0e02c-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifying certificates for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e02c-123">設定反向 proxy</span><span class="sxs-lookup"><span data-stu-id="0e02c-123">Configure the reverse proxy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0e02c-124">使用 [安全通訊端層（SSL）] 監聽程式，以消費者替換名稱來指派更新的憑證。</span><span class="sxs-lookup"><span data-stu-id="0e02c-124">Assign certificates updated with subject alternative names to the Secure Sockets Layer (SSL) Listener.</span></span></p></li>
<li><p><span data-ttu-id="0e02c-125">重新設定外部自動探索服務 URL 的 web 發佈規則。</span><span class="sxs-lookup"><span data-stu-id="0e02c-125">Reconfigure the web publishing rule for the external Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="0e02c-126">請確定您前端池中的外部 Lync Server 2013 Web 服務 URL 存在 web 發佈規則。</span><span class="sxs-lookup"><span data-stu-id="0e02c-126">Be sure that a web publishing rule exists for the external Lync Server 2013 Web Services URL on your Front End pool.</span></span></p></li>
</ul>
<p><span data-ttu-id="0e02c-127">或</span><span class="sxs-lookup"><span data-stu-id="0e02c-127">Or</span></span></p>
<ul>
<li><p><span data-ttu-id="0e02c-128">如果您選擇在初始自動探索要求中使用 HTTP，且不更新憑證上的消費者備用名稱清單，請設定新的 web 發佈規則，或針對埠 80 HTTP 重新設定現有的發佈規則。</span><span class="sxs-lookup"><span data-stu-id="0e02c-128">If you choose to use HTTP for the initial Autodiscover request and do not update subject alternative name lists on the certificates, configure a new web publishing rule or reconfigure an existing publishing rule for port 80 HTTP.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0e02c-129">本機系統管理員</span><span class="sxs-lookup"><span data-stu-id="0e02c-129">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="0e02c-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">在 Lync Server 2013 中設定行動的反向 Proxy</a></span><span class="sxs-lookup"><span data-stu-id="0e02c-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e02c-131">使用 Mcx 行動服務測試 Lync 2010 Mobile 行動裝置部署</span><span class="sxs-lookup"><span data-stu-id="0e02c-131">Test your mobility deployment for Lync 2010 Mobile using the Mcx Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="0e02c-132">執行<strong>測試-CsMcxP2PIM</strong> ，測試將即時消息從某個人傳送給另一個人。</span><span class="sxs-lookup"><span data-stu-id="0e02c-132">Run <strong>Test-CsMcxP2PIM</strong> to test sending an instant message from one person to another.</span></span></p>
<p><span data-ttu-id="0e02c-133">如需選項的完整清單，請參閱 Lync Server Management Shell Cmdlet 檔以進行<a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">測試 CsMcxP2PIM</a> 。</span><span class="sxs-lookup"><span data-stu-id="0e02c-133">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="0e02c-134">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0e02c-134">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0e02c-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">在 Lync Server 2013 中驗證行動性部署</a></span><span class="sxs-lookup"><span data-stu-id="0e02c-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e02c-136">使用 UCWA 網頁元件測試 Lync 2013 行動用戶端的行動裝置部署</span><span class="sxs-lookup"><span data-stu-id="0e02c-136">Test your mobility deployment for Lync 2013 Mobile clients using the UCWA Web components</span></span></p></td>
<td><p><span data-ttu-id="0e02c-137">使用<strong>CsUcwaConference</strong> Cmdlet 來測試並驗證預先定義的測試使用者或一組實際的使用者可以使用 UCWA 來建立及參與會議。</span><span class="sxs-lookup"><span data-stu-id="0e02c-137">Use the <strong>Test-CsUcwaConference</strong> cmdlet to test and verify that pre-defined test users or a pair of actual users can use UCWA to create and participate in a conference.</span></span></p>
<p><span data-ttu-id="0e02c-138">如需選項的完整清單，請參閱 Lync Server Management Shell Cmdlet 檔以進行<a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">測試 CsUcwaConference</a> 。</span><span class="sxs-lookup"><span data-stu-id="0e02c-138">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="0e02c-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0e02c-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0e02c-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">在 Lync Server 2013 中驗證行動性部署</a></span><span class="sxs-lookup"><span data-stu-id="0e02c-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e02c-141">針對推播通知進行設定</span><span class="sxs-lookup"><span data-stu-id="0e02c-141">Configure for push notifications</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0e02c-142">針對 Lync Server 2013 Edge 伺服器，請新增 Lync Server online 主機主機服務提供者，並設定主機服務提供者同盟。</span><span class="sxs-lookup"><span data-stu-id="0e02c-142">For Lync Server 2013 Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="0e02c-143">針對 Lync Server 2010 Edge 伺服器，請新增 Lync Server online 主機主機服務提供者，並設定主機服務提供者同盟。</span><span class="sxs-lookup"><span data-stu-id="0e02c-143">For Lync Server 2010  Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="0e02c-144">針對 Office 通訊伺服器 2007 R2 Edge 伺服器，請新增聯盟夥伴。</span><span class="sxs-lookup"><span data-stu-id="0e02c-144">For Office Communications Server 2007 R2 Edge Servers, add a federated partner.</span></span></p></li>
<li><p><span data-ttu-id="0e02c-145">如果您想要在 Wi-fi 網路上支援推播通知，請設定 TCP 埠5223的出站防火牆規則。</span><span class="sxs-lookup"><span data-stu-id="0e02c-145">If you want to support push notifications over a Wi-Fi network, configure a firewall rule outbound for TCP port 5223.</span></span></p></li>
<li><p><span data-ttu-id="0e02c-146">使用<strong>CsPushNotificationConfiguration</strong> Cmdlet 來啟用 Apple 推播通知服務（APNS）和 Microsoft 推播通知服務（MPNS）的推播通知。</span><span class="sxs-lookup"><span data-stu-id="0e02c-146">Use the <strong>Set-CsPushNotificationConfiguration</strong> cmdlet to enable push notifications to the Apple Push Notification Service (APNS) and Microsoft Push Notification Service (MPNS).</span></span> <span data-ttu-id="0e02c-147">此功能預設為停用。</span><span class="sxs-lookup"><span data-stu-id="0e02c-147">This feature is disabled by default.</span></span></p></li>
<li><p><span data-ttu-id="0e02c-148">使用<strong>CsFederatedPartner</strong> Cmdlet 來測試同盟設定和<strong>CsMCXPushNotification</strong> Cmdlet，以測試推播通知。</span><span class="sxs-lookup"><span data-stu-id="0e02c-148">Use the <strong>Test-CsFederatedPartner</strong> cmdlet to test the federation configuration and the <strong>Test-CsMCXPushNotification</strong> cmdlet to test push notifications.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="0e02c-149">[推播通知] 用於 Apple 裝置和 Windows Phone 上的 Lync 2010 行動用戶端</span><span class="sxs-lookup"><span data-stu-id="0e02c-149">Push notifications are used for Lync 2010 Mobile clients on Apple devices and Windows Phone</span></span><BR><span data-ttu-id="0e02c-150">只有 Windows Phone 上的 Lync 2013 行動用戶端需要推播通知</span><span class="sxs-lookup"><span data-stu-id="0e02c-150">Push notification is required for Lync 2013 Mobile clients on Windows Phone only</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="0e02c-151">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0e02c-151">RtcUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="0e02c-152"><a href="lync-server-2013-configuring-for-push-notifications.md">在 Lync Server 2013 中設定推播通知</a></span><span class="sxs-lookup"><span data-stu-id="0e02c-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Configuring for push notifications in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e02c-153">設定行動原則</span><span class="sxs-lookup"><span data-stu-id="0e02c-153">Configure mobility policy</span></span></p></td>
<td><p><span data-ttu-id="0e02c-154">使用<strong>CsMobilityPolicy</strong> Cmdlet 來允許或禁止：</span><span class="sxs-lookup"><span data-stu-id="0e02c-154">Use the <strong>Set-CsMobilityPolicy</strong> cmdlet to allow or disallow:</span></span></p>
<ul>
<li><p><span data-ttu-id="0e02c-155">透過公司通話</span><span class="sxs-lookup"><span data-stu-id="0e02c-155">Call via Work</span></span></p></li>
<li><p><span data-ttu-id="0e02c-156">啟用 IP 音訊與 IP 影片</span><span class="sxs-lookup"><span data-stu-id="0e02c-156">Enable IP Audio and IP Video</span></span></p></li>
<li><p><span data-ttu-id="0e02c-157">IP 音訊和/或 IP 視頻需要 WiFi</span><span class="sxs-lookup"><span data-stu-id="0e02c-157">Require WiFi for IP Audio and/or IP Video</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0e02c-158">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0e02c-158">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="0e02c-159"><a href="lync-server-2013-configuring-mobility-policy.md">在 Lync Server 2013 中設定行動原則</a></span><span class="sxs-lookup"><span data-stu-id="0e02c-159"><a href="lync-server-2013-configuring-mobility-policy.md">Configuring mobility policy in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

