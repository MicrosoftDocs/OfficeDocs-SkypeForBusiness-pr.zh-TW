---
title: Lync Server 2013： 連接埠摘要-反向 proxy
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
ms.openlocfilehash: aedd0552377861c686667eadd88d190a03799cce
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a>連接埠摘要-Lync Server 2013 中的反向 proxy

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-15_

反向 Proxy 對於防火牆和連接埠/通訊協定具有最低需求。

  - 外部防火牆需求是 HTTPS/TCP/443 和選擇性 HTTP/TCP/80。 HTTPS 用於透過反向 proxy 的 SSL 和 TLS 安全通訊。 如果您選擇允許存取自動探索服務時修改憑證可能證明難以或成本的左右，則會使用 HTTP。

  - 用戶端預期連絡 HTTPS 上的 Office Web Apps 伺服器。 Office Web Apps Server 預期在 HTTPS/TCP/443 上內部用戶端通訊。 建議的組態設定是允許來自反向 proxy 的 HTTPS/TCP/443 至 Office Web Apps Server。

  - 反向 proxy 內部介面的流量路由傳送至前端伺服器，前端集區虛擬 IP (VIP) 或選用的 Director 或 Director 集區 VIP 使用連接埠 8080。 需要執行 Lync 來尋找自動探索服務時 （例如，如果您有大量的 SIP 網域） 不需要修改外部 web 服務發行規則憑證的情況中的行動裝置的連接埠 TCP 8080。 如果您選擇取得含有必要 SAN 項目的新憑證，則不需要使用連接埠 TCP 8080，其為選用項目。

  - 連接埠 4443 用於從反向 proxy 內部介面到前端伺服器，前端集區虛擬 IP (VIP) 或選用的 Director 或 Director 集區 VIP 的流量
    
    ![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")  
    
    <div>
    

    > [!WARNING]  
    > 請勿將 4443 over TCP 來自反向 proxy over TCP 流量的連接埠 4443 從 Standard Edition server 或管理 [中央管理存放區角色的前端集區的內部部署。

    
    </div>

<div>

## <a name="port-and-protocol-details"></a>連接埠和通訊協定詳細資料

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
<th>通訊協定/TCP 或 UDP/連接埠</th>
<th>來源 IP 位址</th>
<th>目的地 IP 位址</th>
<th>附註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>任何</p></td>
<td><p>反向 Proxy 接聽程式</p></td>
<td><p>（選用）重新導向至 HTTPS 使用者輸入 http://&lt;publishedSiteFQDN&gt;。</p>
<p>如果使用 Office Web Apps 會議] 和 [在組織不想要修改外部 web 服務發行規則憑證的情況中執行 Lync 的行動裝置的自動探索服務，也需要。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>任何</p></td>
<td><p>反向 Proxy 接聽程式</p></td>
<td><p>通訊錄下載、 通訊錄 Web 查詢服務、 自動探索、 用戶端更新、 會議內容、 裝置更新、 群組擴充，Office Web Apps for 會議、 電話撥入式會議及會議。</p></td>
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
<th>通訊協定/TCP 或 UDP/連接埠</th>
<th>來源 IP 位址</th>
<th>目的地 IP 位址</th>
<th>附註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>內部反向 Proxy 介面</p></td>
<td><p>前端伺服器，前端集區、 Director、 Director 集區</p></td>
<td><p>如果在組織不想要修改外部 web 服務發行規則憑證的情況中執行 Lync 的行動裝置使用自動探索服務，需要。</p>
<p>傳送至反向 Proxy 外部介面之連接埠 80 的流量，會從反向 Proxy 內部介面重新導向至連接埠 8080 上的集區，讓集區 Web 服務能夠將它與內部 Web 流量區分開來。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>內部反向 Proxy 介面</p></td>
<td><p>前端伺服器，前端集區、 Director、 Director 集區</p></td>
<td><p>傳送至反向 Proxy 外部介面之連接埠 443 上的流量，系統會重新導向至來自反向 Proxy 內部介面之連接埠 4443 上的集區，因此集區 Web 服務可以將它與內部 Web 流量區分開來。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP/443</p></td>
<td><p>內部反向 Proxy 介面</p></td>
<td><p>電話撥入會議的 office Web Apps</p></td>
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

