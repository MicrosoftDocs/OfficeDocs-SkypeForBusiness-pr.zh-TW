---
title: Lync Server 2013：憑證摘要-自動探索
description: Lync Server 2013：憑證摘要-自動探索。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae421401421434a4c4069c1d90ee287dfb016997
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574709"
---
# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a>Lync Server 2013 中的憑證摘要-自動探索

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-14_

Lync Server 2013 自動探索服務會在 Director 和前端集區伺服器上執行，當您在 DNS 中發佈時，可供 Lync 用戶端用來尋找伺服器和使用者服務。 若要從 Lync Server 2010 升級，但未部署行動性，用戶端可以使用自動探索之前，必須修改執行自動探索服務之任何 Director 和前端伺服器上的憑證主體替代名稱清單。 此外，可能還需要針對在反向 Proxy 上用於外部 Web 服務發行規則的憑證，修改主體替代名稱清單。

在反向 proxy 上是否要使用主體替代名稱清單的決策，取決於您是在埠80上還是在埠443上發行自動探索服務：

  - **已在埠 80**     上發行如果自動探索服務的初始查詢發生在埠80上，則不需要憑證變更。 這是因為執行 Lync 的行動裝置會在外部存取埠80上的反向 proxy，然後在內部將其橋接至 Director 或前端8080伺服器。 如需詳細資訊，請參閱 [Lync Server 2013 中](lync-server-2013-technical-requirements-for-mobility.md)的「使用埠80的初始自動探索程式」一節行動的技術需求。

  - **已在埠 443**     上發行外部 web 服務發行規則所使用之憑證上的主體替代名稱清單必須包含*lyncdiscover。 \<sipdomain\> * 組織內每個 SIP 網域的專案。
    
    <div>
    

    > [!IMPORTANT]  
    > 強烈建議使用 HTTPS over HTTP。 HTTPS 使用憑證來加密流量。 HTTP 不提供加密，而且傳送的任何資料都會是純文字。

    
    </div>

使用內部憑證授權單位單位重新發起憑證，通常是一種簡單的處理方式。 不過，對於用於 web 服務發行規則的公用憑證，新增多個主體別名專案會變得很昂貴。 若要解決此問題，我們支援經由埠80的初始自動探索連線，然後重新導向 Director 或前端伺服器上的埠8080。

<div>


> [!NOTE]  
> 如果您的 Lync Server 2013 基礎結構使用內部憑證授權單位所發行的內部憑證 (CA) ，且您計畫支援以無線方式連線的行動裝置，則必須在行動裝置上安裝內部 CA 的根憑證鏈，或是必須變更為 Lync Server 2013 基礎結構上的公用憑證。



</div>

本主題說明 Director、前端伺服器及反向 proxy 所需的主體替代名稱。 只會參考 (SAN) 所新增的主體替代名稱。 如需憑證上其他專案的指引，請參閱規劃章節。 如需詳細資訊，請參閱 lync server [2013 中的 Director 案例](lync-server-2013-scenarios-for-the-director.md)、 [lync server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)，以及 [lync server 2013 中的反向 proxy](lync-server-2013-scenarios-for-reverse-proxy.md)案例。

下表定義 Director 集區、前端集區和反向 proxy 的自動探索 SAN 專案：

### <a name="director-pool-certificate-requirements"></a>Director 集區憑證需求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>描述</th>
<th>主體替代名稱項目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>內部自動探索服務 URL</p></td>
<td><p>SAN = lyncdiscoverinternal。 &lt;內部功能變數名稱&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自動探索服務 URL</p></td>
<td><p>SAN = lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 您可以將新的已更新憑證以新的 SAN 專案指派給預設憑證。 或者，您也可以使用 SAN = *。 &lt;microsoft.rtc.management.xds.sipdomain &gt; 。



</div>

### <a name="front-end-pool-certificate-requirements"></a>前端集區憑證需求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>描述</th>
<th>主體替代名稱項目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>內部自動探索服務 URL</p></td>
<td><p>SAN = lyncdiscoverinternal。 &lt;內部功能變數名稱&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自動探索服務 URL</p></td>
<td><p>SAN = lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 您可以將新的已更新憑證以新的 SAN 專案指派給預設憑證。 或者，您也可以使用 SAN = *。 &lt;microsoft.rtc.management.xds.sipdomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>反向 Proxy (公用 CA) 憑證需求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>描述</th>
<th>主體別名項目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部自動探索服務 URL</p></td>
<td><p>SAN = lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 您可以將新的已更新憑證，指派給反向 proxy 上的 SSL 攔截器。



</div>

</div>

<span> </span>

</div>

</div>

</div>

