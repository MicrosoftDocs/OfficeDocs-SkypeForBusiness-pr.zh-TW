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
ms.openlocfilehash: c36f8d3ee6e26c00e7686a72e1b68139c1b5ec29
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a>Lync Server 2013 中的行動性部署程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-19_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

本節說明部署 Lync Server 2013 行動功能所需的步驟的順序。

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
<li><p>建立內部 DNS CNAME 或 A (主機，如果 IPv6、 AAAA) 記錄，以解析內部自動探索服務 URL。</p></li>
<li><p>建立外部 DNS CNAME 或 A (主機，如果 IPv6、 AAAA) 記錄，以解析外部自動探索服務 URL。</p></li>
</ul></td>
<td><p>Domain Admins</p>
<p>DnsAdmins</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Lync Server 2013 中的自動探索服務建立 DNS 記錄</a></p></td>
</tr>
<tr class="even">
<td><p>修改憑證</p></td>
<td><p>新增主體替代名稱項目至下列憑證，以支援行動使用者的安全連線：</p>
<ul>
<li><p>Director 憑證</p></li>
<li><p>前端集區憑證結尾</p></li>
<li><p>反向 Proxy 憑證</p></li>
</ul></td>
<td><p>本機系統管理員</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">修改行動性 Lync Server 2013 中的憑證</a></p></td>
</tr>
<tr class="odd">
<td><p>設定反向 Proxy</p></td>
<td><ul>
<li><p>將以主體替代名稱更新的憑證指派給 Secure Sockets Layer (SSL) 接聽程式。</p></li>
<li><p>重新網頁發行規則設定為外部自動探索服務 URL。</p></li>
<li><p>請務必 web 發行規則存在外部 Lync Server 2013 Web 服務 URL 的前端集區上。</p></li>
</ul>
<p>或者</p>
<ul>
<li><p>如果您選擇使用 HTTP 來進行初始自動探索要求，並不會進行更新憑證上的主體替代名稱清單，設定新的 web 發行規則，或重新設定現有的發佈規則，在連接埠 80 HTTP。</p></li>
</ul></td>
<td><p>本機系統管理員</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">在 Lync Server 2013 中設定行動的反向 proxy</a></p></td>
</tr>
<tr class="even">
<td><p>測試行動性部署 Lync 2010 mobile 使用 Mcx Mobility Service</p></td>
<td><p>執行 <strong>Test-CsMcxP2PIM</strong>，以測試從一個人傳送立即訊息給另一個人。</p>
<p>請參閱 Lync Server 管理命令介面指令程式文件<a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-csmcxp2pim</a>如需完整清單的選項。</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">驗證行動部署 Lync Server 2013 中</a></p></td>
</tr>
<tr class="odd">
<td><p>測試行動性部署 Lync 2013 行動用戶端使用 UCWA Web 元件</p></td>
<td><p>使用<strong>Test-csucwaconference</strong>指令程式來測試並確認預先定義的測試使用者或一組的實際使用者可以使用 UCWA 建立並參與會議。</p>
<p>請參閱 Lync Server 管理命令介面指令程式文件<a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-csucwaconference</a>如需完整清單的選項。</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">驗證行動部署 Lync Server 2013 中</a></p></td>
</tr>
<tr class="even">
<td><p>設定推入通知</p></td>
<td><ul>
<li><p>Lync Server 2013 Edge server，新增 Lync Server 線上裝載提供者並設定裝載提供者同盟。</p></li>
<li><p>Lync Server 2010 Edge server，新增 Lync Server 線上裝載提供者並設定裝載提供者同盟。</p></li>
<li><p>針對 Office Communications Server 2007 R2 Edge Server，新增同盟協力廠商。</p></li>
<li><p>如果您要透過 Wi-Fi 網路來支援推入通知，請設定 TCP 連接埠 5223 的防火牆規則輸出。</p></li>
<li><p>使用 <strong>Set-CsPushNotificationConfiguration</strong> Cmdlet 來啟用推入通知至 Apple Push Notification Service (APNS) 及 Microsoft Push Notification Service (MPNS)。 此功能預設為停用。</p></li>
<li><p>使用 <strong>Test-CsFederatedPartner</strong> Cmdlet 來測試同盟設定，並使用 <strong>Test-CsMCXPushNotification</strong> Cmdlet 來測試推入通知。</p>
<div>

> [!NOTE]  
> 推入通知用於在 Apple 裝置和 Windows Phone 上的 Lync 2010 Mobile 用戶端<BR>推播通知是 Lync 2013 行動用戶端的 Windows Phone 上只需要


</div></li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">設定 Lync Server 2013 中的推入通知</a></p></td>
</tr>
<tr class="odd">
<td><p>設定行動原則</p></td>
<td><p>若要允許或不許使用<strong>Set-csmobilitypolicy</strong> cmdlet:</p>
<ul>
<li><p>呼叫從公司撥號</p></li>
<li><p>啟用 IP 音訊及 IP 視訊</p></li>
<li><p>需要 WiFi IP 音訊和/或 IP 視訊</p></li>
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

