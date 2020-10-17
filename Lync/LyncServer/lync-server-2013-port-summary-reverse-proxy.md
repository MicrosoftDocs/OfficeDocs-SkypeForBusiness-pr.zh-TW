---
title: Lync Server 2013：埠摘要-反向 proxy
description: Lync Server 2013：埠摘要-反向 proxy。
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
ms.openlocfilehash: bf07800c91f5a28165eb05e14e2d775758460f50
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555249"
---
# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 中的埠摘要-反向 proxy

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-15_

反向 Proxy 對於防火牆和連接埠/通訊協定具有最低需求。

  - 外部防火牆需求為 HTTPS/TCP/443 和選用的 HTTP/TCP/80。 HTTPS 用於透過反向 proxy 進行 SSL 和 TLS 的安全通訊。 如果您選擇允許在修改憑證時存取自動探索服務，可能會證明困難或不會有成本。

  - 用戶端預期會聯繫 HTTPS 上的 Office Web Apps Server。 Office Web Apps Server 期望來自 HTTPS/TCP/443 的內部用戶端進行通訊。 建議的設定是允許 HTTPS/TCP/443 從反向 proxy 到 Office Web Apps Server。

  - 埠8080是用來將流量從反向 proxy 內部介面路由傳送至前端伺服器、前端集區虛擬 IP (VIP) 或選用的 Director 或 Director 集區 VIP。 在需要修改外部 web 服務發行規則憑證的情況下（例如，如果您有大量 SIP 網域) 時，執行 Lync 的行動裝置會需要端口 TCP 8080，以找出自動探索服務 (例如）。 如果您選擇取得含有必要 SAN 項目的新憑證，則不需要使用連接埠 TCP 8080，其為選用項目。

  - 埠4443用於從反向 proxy 內部介面到前端伺服器、前端集區虛擬 IP (VIP) 或選用的 Director 或 Director 集區 VIP 的流量
    
    ![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")  
    
    <div>
    

    > [!WARNING]  
    > 請不要將 4443 over TCP 的反向 proxy 與來自 Standard Edition server 的 TCP 流量和管理中央管理存放區角色的前端集區的內部4443部署混淆。

    
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
<th>通訊協定/TCP 或 UDP/連接埠</th>
<th>來源 IP 位址</th>
<th>目的地 IP 位址</th>
<th>注意事項</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>任何</p></td>
<td><p>反向 Proxy 接聽程式</p></td>
<td><p> (選用) 使用者進入 HTTP://publishedSiteFQDN 時重新導向至 HTTPS &lt; &gt; 。</p>
<p>在組織不想要修改外部 Web 服務發行規則憑證的情況下，如果為執行 Lync 的行動裝置使用 Office Web Apps for 會議和自動探索服務，也是必要的。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>任何</p></td>
<td><p>反向 Proxy 接聽程式</p></td>
<td><p>通訊錄下載、通訊錄 Web 查詢服務、自動探索、用戶端更新、會議內容、裝置更新、群組擴充、Office Web Apps for 會議、電話撥入式會議及會議。</p></td>
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
<th>注意事項</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>內部反向 Proxy 介面</p></td>
<td><p>前端伺服器、前端集區、Director、Director 集區</p></td>
<td><p>在組織不想要修改外部 web 服務發行規則憑證的情況下，如果對執行 Lync 的行動裝置使用自動探索服務，則為必要的。</p>
<p>傳送至反向 Proxy 外部介面之連接埠 80 的流量，會從反向 Proxy 內部介面重新導向至連接埠 8080 上的集區，讓集區 Web 服務能夠將它與內部 Web 流量區分開來。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>內部反向 Proxy 介面</p></td>
<td><p>前端伺服器、前端集區、Director、Director 集區</p></td>
<td><p>傳送至反向 Proxy 外部介面之連接埠 443 上的流量，系統會重新導向至來自反向 Proxy 內部介面之連接埠 4443 上的集區，因此集區 Web 服務可以將它與內部 Web 流量區分開來。</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP/443</p></td>
<td><p>內部反向 Proxy 介面</p></td>
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

