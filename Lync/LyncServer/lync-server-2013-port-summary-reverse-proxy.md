---
title: Lync Server 2013：連接埠摘要 - 反向 Proxy
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2944cde932413f00b5a4dcb75cd4a37bd5b3a3a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 中的連接埠摘要 - 反向 Proxy

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-15_

反向 proxy 對防火牆和埠/通訊協定的需求最低。

  - 外部防火牆需求是 HTTPS/TCP/443 以及選用的 HTTP/TCP/80。 HTTPS 是透過反向 proxy 使用 SSL 和 TLS 安全通訊。 如果您選擇在修改憑證時允許存取自動探索服務，可能會證明困難或不是成本。

  - 用戶端預期要與 HTTPS 上的 Office Web Apps 伺服器取得聯繫。 Office Web Apps 伺服器預期從 HTTPS/TCP/443 上的內部用戶端進行通訊。 建議的設定是允許從反向 proxy 的 HTTPS/TCP/443 到 Office Web Apps 伺服器。

  - Port 8080 是用來將流量從反向 proxy 內部介面路由到前端伺服器、前端池虛擬 IP （VIP），或是選用控制器或控制器池 VIP。 在執行 Lync 的行動裝置上，如果您需要修改外部 web 服務發佈規則憑證的情況（例如，如果您有大量 SIP 網域），則必須使用埠 TCP 8080 來尋找自動探索服務。 如果您選擇要用所需的 SAN 專案來取得新憑證，則不需要端口 TCP 8080，且是選擇性的。

  - 埠4443用於從反向 proxy 內部介面到前端伺服器、前端池虛擬 IP （VIP）或選用控制器或控制器池 VIP 的流量
    
    ![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")  
    
    <div>
    

    > [!WARNING]  
    > 請不要將4443的 TCP 從反向 proxy 與來自標準版 server 的內部4443部署，或是管理中央管理儲存角色的前端池。

    
    </div>

<div>

## <a name="port-and-protocol-details"></a>埠與通訊協定詳細資料

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a>反向 Proxy 伺服器的防火牆詳細資料：外部介面

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>通訊協定/TCP 或 UDP/埠</th>
<th>來源 IP 位址</th>
<th>目的地 IP 位址</th>
<th>筆記</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>每</p></td>
<td><p>反向 proxy 偵聽程式</p></td>
<td><p>可選如果使用者進入 HTTP://&lt;publishedSiteFQDN&gt;，則重定向至 HTTPS。</p>
<p>如果您在組織不想要修改外部 Web 服務發佈規則憑證的情況下，使用 Office Web Apps for 會議，以及執行 Lync 之行動裝置的自動探索服務，也需要。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>每</p></td>
<td><p>反向 proxy 偵聽程式</p></td>
<td><p>通訊錄下載、通訊錄網頁查詢服務、自動探索、用戶端更新、會議內容、裝置更新、群組延伸、Office Web Apps for 會議、電話撥入式會議及會議。</p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a>反向 Proxy 伺服器的防火牆詳細資料：內部介面

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>通訊協定/TCP 或 UDP/埠</th>
<th>來源 IP 位址</th>
<th>目的地 IP 位址</th>
<th>筆記</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>內部反向 proxy 介面</p></td>
<td><p>前端伺服器、前端池、導演、控制器池</p></td>
<td><p>如果組織不想要修改外部 web 服務發佈規則憑證的情況下，在執行 Lync 的行動裝置上使用自動探索服務，則是必要的。</p>
<p>在反向 proxy 外部介面上傳送到埠80的流量，會從反向 proxy 內部介面重新導向到埠8080上的 pool，讓 pool Web 服務可以區別內部網路流量。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>內部反向 proxy 介面</p></td>
<td><p>前端伺服器、前端池、導演、控制器池</p></td>
<td><p>在反向 proxy 外部介面上傳送到埠443的流量，會從反向 proxy 內部介面重新導向到埠4443上的 pool，讓 pool web 服務可以區別內部網路流量。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP/443</p></td>
<td><p>內部反向 proxy 介面</p></td>
<td><p>適用于會議的 Office Web Apps</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

