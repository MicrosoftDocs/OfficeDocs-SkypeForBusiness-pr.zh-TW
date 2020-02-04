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
ms.openlocfilehash: 945e3ed9d532f27676e250c29ab415646bd967ec
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a>埠摘要-Lync Server 2013 中的自動探索

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-05_

Lync Server 2013 自動探索服務會在主管和前端池伺服器上執行，當您使用`lyncdiscover.<domain>`與`lyncdiscoverinternal.<domain>`主機記錄在 DNS 中發佈時，可供用戶端用來尋找 Lync Server 功能。 若要在執行 Lync Mobile 的行動裝置上使用自動探索功能，您可能必須先在執行自動探索服務的任何主管和前端伺服器上修改證書受領人備用名稱清單。 此外，可能還需要針對反向代理伺服器上的外部 web 服務發佈規則，在證書上修改消費者備用名稱清單。

有關是否要在反向代理伺服器上使用 subject 備用名稱清單的決策是依據您是否要在埠80或埠443上發佈自動探索服務而定：

  - **在**   適用于行動裝置的埠80上發佈，如果自動探索服務的初始查詢是在埠80上進行，則不需要進行任何憑證變更。 這是因為執行 Lync 的行動裝置會在外部存取埠80上的反向 proxy，然後在內部將埠8080重新導向到控制器或前端伺服器。

  - **已在埠 443**   上發佈對於外部 web 服務發佈規則所使用的憑證，您必須為貴組織`lyncdiscover.<sipdomain>`內的每個 SIP 網域包含一個專案。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您是從已部署行動性的 Lync Server 2010 進行全新安裝或升級，您可以使用埠80來自動探索行動服務，或以適當的受領人名稱和 subject 替代名稱來重新頒發憑證。 查看主管和前端伺服器上的憑證，確認您選擇的是哪個路徑。

    
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
<td><p>可選如果使用者進入 HTTP://&lt;publishedSiteFQDN&gt;，則重定向至 HTTPS。 如果您在組織不想要修改外部 Web 服務發佈規則憑證的情況下，使用 Office Web Apps for 會議，以及執行 Lync 之行動裝置的自動探索服務，也需要。</p></td>
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
<td><p>[前端伺服器]、[前端] 池、[主管]、[控制器] 池、[會議的 Office Web Apps]</p></td>
<td><p>如果組織不想要修改外部 web 服務發佈規則憑證的情況下，在執行 Lync 的行動裝置上使用自動探索服務，則是必要的。 在反向 proxy 外部介面上傳送到埠80的流量，會從反向 proxy 內部介面重新導向到埠8080上的 pool，讓 pool Web 服務可以區別內部網路流量。</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>內部反向 proxy 介面</p></td>
<td><p>[前端伺服器]、[前端] 池、[主管]、[控制器] 池、[會議的 Office Web Apps]</p></td>
<td><p>在反向 proxy 外部介面上傳送到埠443的流量，會從反向 proxy 內部介面重新導向到埠4443上的 pool，讓 pool web 服務可以區別內部網路流量。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

