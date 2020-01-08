---
title: Lync Server 2013：行動的部署程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for mobility
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690023(v=OCS.15)
ms:contentKeyID: 48184220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dec6f1e089a9418db3d8ece1f390615226687cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a>Lync Server 2013 中行動的部署程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-19_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

本節說明部署 Lync Server 2013 行動功能所需的步驟順序。

### <a name="mobility-deployment-process"></a>行動部署流程

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>分</th>
<th>步驟</th>
<th>許可權</th>
<th>部署檔</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>建立網域名稱系統（DNS）記錄</p></td>
<td><ul>
<li><p>建立內部 DNS CNAME 或 A （如果是 IPv6、AAAA）記錄，以解析內部自動探索服務 URL。</p></li>
<li><p>建立外部 DNS CNAME 或 A （如果是 IPv6、AAAA）記錄，以解析外部自動探索服務 URL。</p></li>
</ul></td>
<td><p>網域管理員</p>
<p>DnsAdmins</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">在 Lync Server 2013 中建立自動探索服務的 DNS 記錄</a></p></td>
</tr>
<tr class="even">
<td><p>修改憑證</p></td>
<td><p>將消費者備用名稱專案新增至下列憑證，以支援行動使用者的安全連線：</p>
<ul>
<li><p>導演憑證</p></li>
<li><p>前端池憑證</p></li>
<li><p>反向 proxy 憑證</p></li>
</ul></td>
<td><p>本機系統管理員</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">在 Lync Server 2013 中修改行動憑證</a></p></td>
</tr>
<tr class="odd">
<td><p>設定反向 proxy</p></td>
<td><ul>
<li><p>使用 [安全通訊端層（SSL）] 監聽程式，以消費者替換名稱來指派更新的憑證。</p></li>
<li><p>重新設定外部自動探索服務 URL 的 web 發佈規則。</p></li>
<li><p>請確定您前端池中的外部 Lync Server 2013 Web 服務 URL 存在 web 發佈規則。</p></li>
</ul>
<p>或</p>
<ul>
<li><p>如果您選擇在初始自動探索要求中使用 HTTP，且不更新憑證上的消費者備用名稱清單，請設定新的 web 發佈規則，或針對埠 80 HTTP 重新設定現有的發佈規則。</p></li>
</ul></td>
<td><p>本機系統管理員</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">在 Lync Server 2013 中設定行動的反向 Proxy</a></p></td>
</tr>
<tr class="even">
<td><p>使用 Mcx 行動服務測試 Lync 2010 Mobile 行動裝置部署</p></td>
<td><p>執行<strong>測試-CsMcxP2PIM</strong> ，測試將即時消息從某個人傳送給另一個人。</p>
<p>如需選項的完整清單，請參閱 Lync Server Management Shell Cmdlet 檔以進行<a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">測試 CsMcxP2PIM</a> 。</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">在 Lync Server 2013 中驗證行動性部署</a></p></td>
</tr>
<tr class="odd">
<td><p>使用 UCWA 網頁元件測試 Lync 2013 行動用戶端的行動裝置部署</p></td>
<td><p>使用<strong>CsUcwaConference</strong> Cmdlet 來測試並驗證預先定義的測試使用者或一組實際的使用者可以使用 UCWA 來建立及參與會議。</p>
<p>如需選項的完整清單，請參閱 Lync Server Management Shell Cmdlet 檔以進行<a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">測試 CsUcwaConference</a> 。</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">在 Lync Server 2013 中驗證行動性部署</a></p></td>
</tr>
<tr class="even">
<td><p>針對推播通知進行設定</p></td>
<td><ul>
<li><p>針對 Lync Server 2013 Edge 伺服器，請新增 Lync Server online 主機主機服務提供者，並設定主機服務提供者同盟。</p></li>
<li><p>針對 Lync Server 2010 Edge 伺服器，請新增 Lync Server online 主機主機服務提供者，並設定主機服務提供者同盟。</p></li>
<li><p>針對 Office 通訊伺服器 2007 R2 Edge 伺服器，請新增聯盟夥伴。</p></li>
<li><p>如果您想要在 Wi-fi 網路上支援推播通知，請設定 TCP 埠5223的出站防火牆規則。</p></li>
<li><p>使用<strong>CsPushNotificationConfiguration</strong> Cmdlet 來啟用 Apple 推播通知服務（APNS）和 Microsoft 推播通知服務（MPNS）的推播通知。 此功能預設為停用。</p></li>
<li><p>使用<strong>CsFederatedPartner</strong> Cmdlet 來測試同盟設定和<strong>CsMCXPushNotification</strong> Cmdlet，以測試推播通知。</p>
<div>

> [!NOTE]  
> [推播通知] 用於 Apple 裝置和 Windows Phone 上的 Lync 2010 行動用戶端<BR>只有 Windows Phone 上的 Lync 2013 行動用戶端需要推播通知


</div></li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">在 Lync Server 2013 中設定推播通知</a></p></td>
</tr>
<tr class="odd">
<td><p>設定行動原則</p></td>
<td><p>使用<strong>CsMobilityPolicy</strong> Cmdlet 來允許或禁止：</p>
<ul>
<li><p>透過公司通話</p></li>
<li><p>啟用 IP 音訊與 IP 影片</p></li>
<li><p>IP 音訊和/或 IP 視頻需要 WiFi</p></li>
</ul></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-mobility-policy.md">在 Lync Server 2013 中設定行動原則</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

