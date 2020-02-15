---
title: Lync Server 2013： 行動性部署程序
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
ms.openlocfilehash: 337e85520cb2a285f4e4743837aafa4136c89f27
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a><span data-ttu-id="6ba20-102">Lync Server 2013 中的行動性部署程序</span><span class="sxs-lookup"><span data-stu-id="6ba20-102">Deployment process for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ba20-103">_**上次修改主題：** 2013年-02-19_</span><span class="sxs-lookup"><span data-stu-id="6ba20-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

<span data-ttu-id="6ba20-104">本節說明部署 Lync Server 2013 行動功能所需的步驟的順序。</span><span class="sxs-lookup"><span data-stu-id="6ba20-104">This section describes the sequence of steps required to deploy the Lync Server 2013 mobility feature.</span></span>

### <a name="mobility-deployment-process"></a><span data-ttu-id="6ba20-105">行動性部署程序</span><span class="sxs-lookup"><span data-stu-id="6ba20-105">Mobility Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ba20-106">階段</span><span class="sxs-lookup"><span data-stu-id="6ba20-106">Phase</span></span></th>
<th><span data-ttu-id="6ba20-107">步驟</span><span class="sxs-lookup"><span data-stu-id="6ba20-107">Steps</span></span></th>
<th><span data-ttu-id="6ba20-108">權限</span><span class="sxs-lookup"><span data-stu-id="6ba20-108">Permissions</span></span></th>
<th><span data-ttu-id="6ba20-109">部署文件</span><span class="sxs-lookup"><span data-stu-id="6ba20-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ba20-110">建立網域名稱系統 (DNS) 記錄</span><span class="sxs-lookup"><span data-stu-id="6ba20-110">Create Domain Name System (DNS) records</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6ba20-111">建立內部 DNS CNAME 或 A (主機，如果 IPv6、 AAAA) 記錄，以解析內部自動探索服務 URL。</span><span class="sxs-lookup"><span data-stu-id="6ba20-111">Create an internal DNS CNAME or A (host, if IPv6, AAAA) record to resolve the internal Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="6ba20-112">建立外部 DNS CNAME 或 A (主機，如果 IPv6、 AAAA) 記錄，以解析外部自動探索服務 URL。</span><span class="sxs-lookup"><span data-stu-id="6ba20-112">Create an external DNS CNAME or A (host, if IPv6, AAAA) record to resolve the external Autodiscover Service URL.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6ba20-113">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="6ba20-113">Domain Admins</span></span></p>
<p><span data-ttu-id="6ba20-114">DnsAdmins</span><span class="sxs-lookup"><span data-stu-id="6ba20-114">DnsAdmins</span></span></p></td>
<td><p><span data-ttu-id="6ba20-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Lync Server 2013 中的自動探索服務建立 DNS 記錄</a></span><span class="sxs-lookup"><span data-stu-id="6ba20-115"><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Creating DNS records for the Autodiscover Service in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ba20-116">修改憑證</span><span class="sxs-lookup"><span data-stu-id="6ba20-116">Modify certificates</span></span></p></td>
<td><p><span data-ttu-id="6ba20-117">新增主體替代名稱項目至下列憑證，以支援行動使用者的安全連線：</span><span class="sxs-lookup"><span data-stu-id="6ba20-117">Add subject alternative name entries to the following certificates to support secure connections for mobile users:</span></span></p>
<ul>
<li><p><span data-ttu-id="6ba20-118">Director 憑證</span><span class="sxs-lookup"><span data-stu-id="6ba20-118">Director certificate</span></span></p></li>
<li><p><span data-ttu-id="6ba20-119">前端集區憑證結尾</span><span class="sxs-lookup"><span data-stu-id="6ba20-119">Front End pool certificate</span></span></p></li>
<li><p><span data-ttu-id="6ba20-120">反向 Proxy 憑證</span><span class="sxs-lookup"><span data-stu-id="6ba20-120">Reverse proxy certificate</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6ba20-121">本機系統管理員</span><span class="sxs-lookup"><span data-stu-id="6ba20-121">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="6ba20-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">修改行動性 Lync Server 2013 中的憑證</a></span><span class="sxs-lookup"><span data-stu-id="6ba20-122"><a href="lync-server-2013-modifying-certificates-for-mobility.md">Modifying certificates for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ba20-123">設定反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="6ba20-123">Configure the reverse proxy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6ba20-124">將以主體替代名稱更新的憑證指派給 Secure Sockets Layer (SSL) 接聽程式。</span><span class="sxs-lookup"><span data-stu-id="6ba20-124">Assign certificates updated with subject alternative names to the Secure Sockets Layer (SSL) Listener.</span></span></p></li>
<li><p><span data-ttu-id="6ba20-125">重新網頁發行規則設定為外部自動探索服務 URL。</span><span class="sxs-lookup"><span data-stu-id="6ba20-125">Reconfigure the web publishing rule for the external Autodiscover Service URL.</span></span></p></li>
<li><p><span data-ttu-id="6ba20-126">請務必 web 發行規則存在外部 Lync Server 2013 Web 服務 URL 的前端集區上。</span><span class="sxs-lookup"><span data-stu-id="6ba20-126">Be sure that a web publishing rule exists for the external Lync Server 2013 Web Services URL on your Front End pool.</span></span></p></li>
</ul>
<p><span data-ttu-id="6ba20-127">或</span><span class="sxs-lookup"><span data-stu-id="6ba20-127">Or</span></span></p>
<ul>
<li><p><span data-ttu-id="6ba20-128">如果您選擇使用 HTTP 來進行初始自動探索要求，並不會進行更新憑證上的主體替代名稱清單，設定新的 web 發行規則，或重新設定現有的發佈規則，在連接埠 80 HTTP。</span><span class="sxs-lookup"><span data-stu-id="6ba20-128">If you choose to use HTTP for the initial Autodiscover request and do not update subject alternative name lists on the certificates, configure a new web publishing rule or reconfigure an existing publishing rule for port 80 HTTP.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6ba20-129">本機系統管理員</span><span class="sxs-lookup"><span data-stu-id="6ba20-129">Local administrator</span></span></p></td>
<td><p><span data-ttu-id="6ba20-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">在 Lync Server 2013 中設定行動的反向 proxy</a></span><span class="sxs-lookup"><span data-stu-id="6ba20-130"><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ba20-131">測試行動性部署 Lync 2010 mobile 使用 Mcx Mobility Service</span><span class="sxs-lookup"><span data-stu-id="6ba20-131">Test your mobility deployment for Lync 2010 Mobile using the Mcx Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="6ba20-132">執行 <strong>Test-CsMcxP2PIM</strong>，以測試從一個人傳送立即訊息給另一個人。</span><span class="sxs-lookup"><span data-stu-id="6ba20-132">Run <strong>Test-CsMcxP2PIM</strong> to test sending an instant message from one person to another.</span></span></p>
<p><span data-ttu-id="6ba20-133">請參閱 Lync Server 管理命令介面指令程式文件<a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-csmcxp2pim</a>如需完整清單的選項。</span><span class="sxs-lookup"><span data-stu-id="6ba20-133">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="6ba20-134">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="6ba20-134">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="6ba20-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">驗證行動部署 Lync Server 2013 中</a></span><span class="sxs-lookup"><span data-stu-id="6ba20-135"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ba20-136">測試行動性部署 Lync 2013 行動用戶端使用 UCWA Web 元件</span><span class="sxs-lookup"><span data-stu-id="6ba20-136">Test your mobility deployment for Lync 2013 Mobile clients using the UCWA Web components</span></span></p></td>
<td><p><span data-ttu-id="6ba20-137">使用<strong>Test-csucwaconference</strong>指令程式來測試並確認預先定義的測試使用者或一組的實際使用者可以使用 UCWA 建立並參與會議。</span><span class="sxs-lookup"><span data-stu-id="6ba20-137">Use the <strong>Test-CsUcwaConference</strong> cmdlet to test and verify that pre-defined test users or a pair of actual users can use UCWA to create and participate in a conference.</span></span></p>
<p><span data-ttu-id="6ba20-138">請參閱 Lync Server 管理命令介面指令程式文件<a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-csucwaconference</a>如需完整清單的選項。</span><span class="sxs-lookup"><span data-stu-id="6ba20-138">See the Lync Server Management Shell cmdlet documentation for <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> for a complete list of options.</span></span></p></td>
<td><p><span data-ttu-id="6ba20-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="6ba20-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="6ba20-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">驗證行動部署 Lync Server 2013 中</a></span><span class="sxs-lookup"><span data-stu-id="6ba20-140"><a href="lync-server-2013-verifying-your-mobility-deployment.md">Verifying your mobility deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ba20-141">設定推入通知</span><span class="sxs-lookup"><span data-stu-id="6ba20-141">Configure for push notifications</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6ba20-142">Lync Server 2013 Edge server，新增 Lync Server 線上裝載提供者並設定裝載提供者同盟。</span><span class="sxs-lookup"><span data-stu-id="6ba20-142">For Lync Server 2013 Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="6ba20-143">Lync Server 2010 Edge server，新增 Lync Server 線上裝載提供者並設定裝載提供者同盟。</span><span class="sxs-lookup"><span data-stu-id="6ba20-143">For Lync Server 2010  Edge Servers, add a Lync Server online hosting provider and configure hosting provider federation.</span></span></p></li>
<li><p><span data-ttu-id="6ba20-144">針對 Office Communications Server 2007 R2 Edge Server，新增同盟協力廠商。</span><span class="sxs-lookup"><span data-stu-id="6ba20-144">For Office Communications Server 2007 R2 Edge Servers, add a federated partner.</span></span></p></li>
<li><p><span data-ttu-id="6ba20-145">如果您要透過 Wi-Fi 網路來支援推入通知，請設定 TCP 連接埠 5223 的防火牆規則輸出。</span><span class="sxs-lookup"><span data-stu-id="6ba20-145">If you want to support push notifications over a Wi-Fi network, configure a firewall rule outbound for TCP port 5223.</span></span></p></li>
<li><p><span data-ttu-id="6ba20-146">使用 <strong>Set-CsPushNotificationConfiguration</strong> Cmdlet 來啟用推入通知至 Apple Push Notification Service (APNS) 及 Microsoft Push Notification Service (MPNS)。</span><span class="sxs-lookup"><span data-stu-id="6ba20-146">Use the <strong>Set-CsPushNotificationConfiguration</strong> cmdlet to enable push notifications to the Apple Push Notification Service (APNS) and Microsoft Push Notification Service (MPNS).</span></span> <span data-ttu-id="6ba20-147">此功能預設為停用。</span><span class="sxs-lookup"><span data-stu-id="6ba20-147">This feature is disabled by default.</span></span></p></li>
<li><p><span data-ttu-id="6ba20-148">使用 <strong>Test-CsFederatedPartner</strong> Cmdlet 來測試同盟設定，並使用 <strong>Test-CsMCXPushNotification</strong> Cmdlet 來測試推入通知。</span><span class="sxs-lookup"><span data-stu-id="6ba20-148">Use the <strong>Test-CsFederatedPartner</strong> cmdlet to test the federation configuration and the <strong>Test-CsMCXPushNotification</strong> cmdlet to test push notifications.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6ba20-149">推入通知用於在 Apple 裝置和 Windows Phone 上的 Lync 2010 Mobile 用戶端</span><span class="sxs-lookup"><span data-stu-id="6ba20-149">Push notifications are used for Lync 2010 Mobile clients on Apple devices and Windows Phone</span></span><BR><span data-ttu-id="6ba20-150">推播通知是 Lync 2013 行動用戶端的 Windows Phone 上只需要</span><span class="sxs-lookup"><span data-stu-id="6ba20-150">Push notification is required for Lync 2013 Mobile clients on Windows Phone only</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="6ba20-151">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6ba20-151">RtcUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="6ba20-152"><a href="lync-server-2013-configuring-for-push-notifications.md">設定 Lync Server 2013 中的推入通知</a></span><span class="sxs-lookup"><span data-stu-id="6ba20-152"><a href="lync-server-2013-configuring-for-push-notifications.md">Configuring for push notifications in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ba20-153">設定行動原則</span><span class="sxs-lookup"><span data-stu-id="6ba20-153">Configure mobility policy</span></span></p></td>
<td><p><span data-ttu-id="6ba20-154">若要允許或不許使用<strong>Set-csmobilitypolicy</strong> cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6ba20-154">Use the <strong>Set-CsMobilityPolicy</strong> cmdlet to allow or disallow:</span></span></p>
<ul>
<li><p><span data-ttu-id="6ba20-155">呼叫從公司撥號</span><span class="sxs-lookup"><span data-stu-id="6ba20-155">Call via Work</span></span></p></li>
<li><p><span data-ttu-id="6ba20-156">啟用 IP 音訊及 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="6ba20-156">Enable IP Audio and IP Video</span></span></p></li>
<li><p><span data-ttu-id="6ba20-157">需要 WiFi IP 音訊和/或 IP 視訊</span><span class="sxs-lookup"><span data-stu-id="6ba20-157">Require WiFi for IP Audio and/or IP Video</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6ba20-158">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="6ba20-158">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="6ba20-159"><a href="lync-server-2013-configuring-mobility-policy.md">在 Lync Server 2013 中設定行動性原則</a></span><span class="sxs-lookup"><span data-stu-id="6ba20-159"><a href="lync-server-2013-configuring-mobility-policy.md">Configuring mobility policy in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

