---
title: Lync Server 2013： 連接埠摘要-自動探索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93750418bce8ea98d0cee385232bc09bb0bd63bc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a>連接埠摘要-Lync Server 2013 中的自動探索

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-03-05_

Lync Server 2013 自動探索服務會執行 Director 與前端集區伺服器，以及當 DNS 使用發佈`lyncdiscover.<domain>`和`lyncdiscoverinternal.<domain>`主機記錄，可以用戶端用來尋找 [Lync Server 功能。 為了讓執行 Lync 行動裝置的行動裝置使用自動探索，您可能需要先修改任何 Director 與前端伺服器執行自動探索服務的憑證主體替代名稱清單。 此外，可能還需要針對在反向 Proxy 上用於外部 Web 服務發行規則的憑證，修改主體替代名稱清單。

決定是否要在反向 proxy 上使用主體替代名稱清單根據您是否發佈連接埠 80 或連接埠 443 上的自動探索服務：

  - **在 [連接埠 80 上發佈**   的行動裝置，沒有任何憑證變更所需如果透過連接埠 80，自動探索服務的初始查詢就會發生。 這是因為執行 Lync 的行動裝置會存取外部連接埠 80 上的反向 proxy，然後重新導向至 Director 或前端伺服器上連接埠 8080 內部。

  - **在 [連接埠 443 上發行**   發行規則必須包含外部 web 服務所使用的憑證上的 [主旨替代名稱] 清單`lyncdiscover.<sipdomain>`每個 SIP 網域組織內的項目。
    
    <div>
    

    > [!IMPORTANT]  
    > 對於新的安裝或從您部署行動性的 Lync Server 2010 的升級，您連接埠 80 用於自動探索的 Mobility service，或重新發出憑證的適當的主體名稱和主體替代名稱就地。 檢閱您選擇的憑證上 Director 與前端伺服器，以確認的路徑。

    
    </div>

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
<td><p>（選用）重新導向至 HTTPS 使用者輸入 http://&lt;publishedSiteFQDN&gt;。 如果使用 Office Web Apps 會議] 和 [在組織不想要修改外部 web 服務發行規則憑證的情況中執行 Lync 的行動裝置的自動探索服務，也需要。</p></td>
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
<td><p>前端伺服器上，前端集區、 Director、 Director 集區，Office Web Apps for 會議</p></td>
<td><p>如果在組織不想要修改外部 web 服務發行規則憑證的情況中執行 Lync 的行動裝置使用自動探索服務，需要。 傳送至反向 Proxy 外部介面之連接埠 80 的流量，會從反向 Proxy 內部介面重新導向至連接埠 8080 上的集區，讓集區 Web 服務能夠將它與內部 Web 流量區分開來。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>內部反向 Proxy 介面</p></td>
<td><p>前端伺服器上，前端集區、 Director、 Director 集區，Office Web Apps for 會議</p></td>
<td><p>傳送至反向 Proxy 外部介面之連接埠 443 上的流量，系統會重新導向至來自反向 Proxy 內部介面之連接埠 4443 上的集區，因此集區 Web 服務可以將它與內部 Web 流量區分開來。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

