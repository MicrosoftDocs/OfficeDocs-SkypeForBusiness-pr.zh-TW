---
title: Lync Server 2013： [認證摘要]-自動探索
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
ms.openlocfilehash: 8956c8a0ed4e149f336e6670aaf5b262f1868748
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a>憑證摘要-Lync Server 2013 中的自動探索

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-14_

Lync Server 2013 自動探索服務會在主管和前端池伺服器上執行，並在 DNS 中發佈時，可供 Lync 用戶端用來尋找伺服器和使用者服務。 如果您是從 Lync Server 2010 升級且沒有部署行動，在用戶端可以使用自動搜尋之前，您必須在執行自動探索服務的任何主管和前端伺服器上修改證書消費者備用名稱清單。 此外，可能還需要針對反向代理伺服器上的外部 web 服務發佈規則，在證書上修改消費者備用名稱清單。

有關是否要在反向代理伺服器上使用 subject 備用名稱清單的決策是依據您是否要在埠80或埠443上發佈自動探索服務而定：

  - **已在埠 80**   上發佈如果自動探索服務的初始查詢是在埠80上進行，則不需要進行憑證變更。 這是因為執行 Lync 的行動裝置會在外部存取埠80上的反向 proxy，然後在內部的埠8080上將其橋接至控制器或前端伺服器。 如需詳細資訊，請參閱[Lync Server 2013 中的行動技術需求](lync-server-2013-technical-requirements-for-mobility.md)（使用埠80的初始自動探索程式）一節。

  - **已在埠 443**   上發佈：外部 web 服務發佈規則所使用的憑證上的使用方式備用名稱清單必須包含*lyncdiscover。\<針對\> *貴組織內的每個 SIP 網域 sipdomain 專案。
    
    <div>
    

    > [!IMPORTANT]  
    > 我們強烈建議您在 HTTP 上使用 HTTPS。 HTTPS 使用憑證來加密流量。 HTTP 不提供加密，且傳送的任何資料都會是純文字。

    
    </div>

使用內部憑證授權單位重新頒發憑證通常是一個簡單的程式。 但針對 web 服務發佈規則所使用的公用憑證，新增多個消費者替換名稱專案可能會變得很昂貴。 若要解決此問題，我們支援經由埠80的初始自動探索連線，然後再重新導向控制器或前端伺服器上的埠8080。

<div>


> [!NOTE]  
> 如果您的 Lync Server 2013 基礎結構使用內部認證機構（CA）頒發的內部憑證，且您打算支援以無線方式連線的行動裝置，則必須安裝內部 CA 的根憑證鏈在行動裝置上，或者您必須在 Lync Server 2013 基礎結構上變更為公用憑證。



</div>

本主題描述的是主管、前端伺服器和反向 proxy 所需的已加入主題替代名稱。 只會參照新增的主體替換名稱（SAN）。 請參閱規劃章節，以取得有關憑證上其他專案的指導方針。 如需詳細資訊，請參閱 lync [server 2013 中的主管案例](lync-server-2013-scenarios-for-the-director.md)、 [lync server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)，以及[lync server 2013 中的反向 proxy](lync-server-2013-scenarios-for-reverse-proxy.md)案例。

下表定義控制器池、前端池及反向 proxy 的自動探索 SAN 專案：

### <a name="director-pool-certificate-requirements"></a>控制器池證書需求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>說明</th>
<th>消費者替換名稱專案</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>內部自動探索服務 URL</p></td>
<td><p>SAN = lyncdiscoverinternal。&lt;內部網功能變數名稱稱&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自動探索服務 URL</p></td>
<td><p>SAN = lyncdiscover。&lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 您可以將新的已更新憑證，以新的 SAN 專案指派給預設憑證。 或者，您也可以使用 SAN = *。&lt;sipdomain&gt;。



</div>

### <a name="front-end-pool-certificate-requirements"></a>前端池憑證需求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>說明</th>
<th>消費者替換名稱專案</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>內部自動探索服務 URL</p></td>
<td><p>SAN = lyncdiscoverinternal。&lt;內部網功能變數名稱稱&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自動探索服務 URL</p></td>
<td><p>SAN = lyncdiscover。&lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 您可以將新的已更新憑證，以新的 SAN 專案指派給預設憑證。 或者，您也可以使用 SAN = *。&lt;sipdomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>反向 Proxy （公用 CA）憑證需求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>說明</th>
<th>消費者替換名稱專案</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部自動探索服務 URL</p></td>
<td><p>SAN = lyncdiscover。&lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 您可以將新的已更新憑證，以新的 SAN 專案指派給反向 proxy 上的 SSL 偵聽程式。



</div>

</div>

<span> </span>

</div>

</div>

</div>

