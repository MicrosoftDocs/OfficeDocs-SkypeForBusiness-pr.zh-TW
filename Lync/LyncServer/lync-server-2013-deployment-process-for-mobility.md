---
title: Lync Server 2013：行動的部署程式
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
ms.openlocfilehash: f7d0e78cd4a8705178b3704a716846755d5c46f3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514480"
---
# <a name="deployment-process-for-mobility-in-lync-server-2013"></a>Lync Server 2013 中行動的部署程式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-19_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

本節說明部署 Lync Server 2013 行動功能所需的步驟順序。

### <a name="mobility-deployment-process"></a>行動性部署程序

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>階段</th>
<th>步驟</th>
<th>權限</th>
<th>部署文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>建立網域名稱系統 (DNS) 記錄</p></td>
<td><ul>
<li><p>建立內部 DNS CNAME 或 (主機，如果 IPv6，AAAA) 記錄來解析內部自動探索服務 URL。</p></li>
<li><p>建立外部 DNS CNAME 或 (主機，如果 IPv6，AAAA) 記錄來解析外部自動探索服務 URL。</p></li>
</ul></td>
<td><p>Domain Admins</p>
<p>DnsAdmins</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">在 Lync Server 2013 中建立自動探索服務的 DNS 記錄</a></p></td>
</tr>
<tr class="even">
<td><p>修改憑證</p></td>
<td><p>新增主體替代名稱項目至下列憑證，以支援行動使用者的安全連線：</p>
<ul>
<li><p>Director 憑證</p></li>
<li><p>前端集區憑證</p></li>
<li><p>反向 Proxy 憑證</p></li>
</ul></td>
<td><p>本機系統管理員</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">在 Lync Server 2013 中修改行動憑證</a></p></td>
</tr>
<tr class="odd">
<td><p>設定反向 Proxy</p></td>
<td><ul>
<li><p>將以主體替代名稱更新的憑證指派給 Secure Sockets Layer (SSL) 接聽程式。</p></li>
<li><p>重新設定外部自動探索服務 URL 的 web 發行規則。</p></li>
<li><p>請確定前端集區上的外部 Lync Server 2013 Web 服務 URL 已存在 web 發佈規則。</p></li>
</ul>
<p>或者</p>
<ul>
<li><p>如果您選擇使用 HTTP 來進行初始自動探索要求，但沒有更新憑證上的主體替代名稱清單，請為埠 80 HTTP 設定新的 web 發行規則或重新設定現有的發行規則。</p></li>
</ul></td>
<td><p>本機系統管理員</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">在 Lync Server 2013 中設定行動的反向 proxy</a></p></td>
</tr>
<tr class="even">
<td><p>使用 Mcx 行動性服務，針對 Lync 2010 Mobile 測試行動性部署</p></td>
<td><p>執行 <strong>Test-CsMcxP2PIM</strong>，以測試從一個人傳送立即訊息給另一個人。</p>
<p>如需完整的選項清單，請參閱 Lync Server Management Shell Cmdlet 檔，以取得 <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> 。</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">在 Lync Server 2013 中驗證行動性部署</a></p></td>
</tr>
<tr class="odd">
<td><p>使用 UCWA Web 元件測試您的 Lync 2013 行動用戶端行動性部署</p></td>
<td><p>使用 <strong>Test-CsUcwaConference</strong> Cmdlet 來測試及驗證預先定義的測試使用者或一組實際的使用者可以使用 UCWA 來建立及參與會議。</p>
<p>如需完整的選項清單，請參閱 Lync Server Management Shell Cmdlet 檔，以取得 <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> 。</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">在 Lync Server 2013 中驗證行動性部署</a></p></td>
</tr>
<tr class="even">
<td><p>設定推入通知</p></td>
<td><ul>
<li><p>針對 Lync Server 2013 Edge server，新增 Lync Server online 主機服務提供者，並設定裝載提供者同盟。</p></li>
<li><p>針對 Lync Server 2010 Edge server，新增 Lync Server online 主機服務提供者，並設定裝載提供者同盟。</p></li>
<li><p>若為 Office 通訊伺服器 2007 R2 Edge Server，請新增同盟協力廠商。</p></li>
<li><p>如果您要透過 Wi-Fi 網路來支援推入通知，請設定 TCP 連接埠 5223 的防火牆規則輸出。</p></li>
<li><p>使用 <strong>Set-CsPushNotificationConfiguration</strong> Cmdlet 來啟用推入通知至 Apple Push Notification Service (APNS) 及 Microsoft Push Notification Service (MPNS)。 此功能預設為停用。</p></li>
<li><p>使用 <strong>Test-CsFederatedPartner</strong> Cmdlet 來測試同盟設定，並使用 <strong>Test-CsMCXPushNotification</strong> Cmdlet 來測試推入通知。</p>
<div>

> [!NOTE]  
> 用於 Apple 裝置和 Windows Phone 上的 Lync 2010 行動用戶端的推播通知<BR>僅限 Windows Phone 上的 Lync 2013 行動用戶端要求推播通知


</div></li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">在 Lync Server 2013 中設定推播通知</a></p></td>
</tr>
<tr class="odd">
<td><p>設定行動原則</p></td>
<td><p>使用 <strong>Set-CsMobilityPolicy</strong> Cmdlet 可允許或禁止：</p>
<ul>
<li><p>從公司通話</p></li>
<li><p>啟用 IP 音訊和 IP 影片</p></li>
<li><p>需要 IP 音訊和/或 IP 影片的 WiFi</p></li>
</ul></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-mobility-policy.md">在 Lync Server 2013 中設定行動性原則</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

