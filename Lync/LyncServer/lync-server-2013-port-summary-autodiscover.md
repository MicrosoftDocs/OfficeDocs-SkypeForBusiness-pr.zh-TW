---
title: Lync Server 2013：埠摘要-自動探索
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
ms.openlocfilehash: 57397d3c2629c0f3f69ebb616c3d933c8312f7b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527950"
---
# <a name="port-summary---autodiscover-in-lync-server-2013"></a>Lync Server 2013 中的埠摘要-自動探索

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-05_

Lync Server 2013 自動探索服務會在 Director 和前端集區伺服器上執行，並會在使用和主控記錄的 DNS 中發佈時，供 `lyncdiscover.<domain>` `lyncdiscoverinternal.<domain>` 用戶端用來找出 lync server 功能。 為了讓執行 Lync Mobile 的行動裝置使用自動探索，您可能需要先修改執行自動探索服務之任何 Director 和前端伺服器上的憑證主體替代名稱清單。 此外，可能還需要針對在反向 Proxy 上用於外部 Web 服務發行規則的憑證，修改主體替代名稱清單。

在反向 proxy 上是否要使用主體替代名稱清單的決策，取決於您是在埠80上還是在埠443上發行自動探索服務：

  - **已在埠 80**     上發行若為行動裝置，當自動探索服務的初始查詢在埠80上發生時，不需要憑證變更。 這是因為執行 Lync 的行動裝置會在外部存取埠80上的反向 proxy，然後再重新導向埠8080上的 Director 或前端伺服器。

  - **已在埠 443**     上發行外部 web 服務發行規則所使用之憑證上的主體替代名稱清單必須包含 `lyncdiscover.<sipdomain>` 組織內每個 SIP 網域的專案。
    
    <div>
    

    > [!IMPORTANT]  
    > 若要在您部署行動性的 Lync Server 2010 中進行全新安裝或升級，您可以使用埠80來自動探索行動性服務，或使用適當的主體名稱和主體替代名稱重新頒發憑證。 檢查 Director 和前端伺服器上的憑證，以確認您選擇的是哪一個路徑。

    
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
<th>注意事項</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>任何</p></td>
<td><p>反向 Proxy 接聽程式</p></td>
<td><p> (選用) 使用者進入 HTTP://publishedSiteFQDN 時重新導向至 HTTPS &lt; &gt; 。 在組織不想要修改外部 Web 服務發行規則憑證的情況下，如果為執行 Lync 的行動裝置使用 Office Web Apps for 會議和自動探索服務，也是必要的。</p></td>
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
<td><p>前端伺服器、前端集區、Director、Director 集區、Office Web Apps for 會議</p></td>
<td><p>在組織不想要修改外部 web 服務發行規則憑證的情況下，如果對執行 Lync 的行動裝置使用自動探索服務，則為必要的。 傳送至反向 Proxy 外部介面之連接埠 80 的流量，會從反向 Proxy 內部介面重新導向至連接埠 8080 上的集區，讓集區 Web 服務能夠將它與內部 Web 流量區分開來。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>內部反向 Proxy 介面</p></td>
<td><p>前端伺服器、前端集區、Director、Director 集區、Office Web Apps for 會議</p></td>
<td><p>傳送至反向 Proxy 外部介面之連接埠 443 上的流量，系統會重新導向至來自反向 Proxy 內部介面之連接埠 4443 上的集區，因此集區 Web 服務可以將它與內部 Web 流量區分開來。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

