---
title: Lync Server 2013： 憑證摘要-自動探索
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
ms.openlocfilehash: c7d45183b3dac5d96d65d771bf1425546f861c38
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a>憑證摘要-Lync Server 2013 中的自動探索

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-14_

Lync Server 2013 自動探索服務執行 Director 與前端集區伺服器，而且當發佈在 DNS 中，可以用於 Lync 用戶端所尋找伺服器和使用者的服務。 如果您從 Lync Server 2010 升級，並沒有不部署行動性，才能用戶端可以使用自動探索，您必須修改任何 Director 與前端伺服器執行自動探索服務的憑證主體替代名稱清單。 此外，可能還需要針對在反向 Proxy 上用於外部 Web 服務發行規則的憑證，修改主體替代名稱清單。

決定是否要在反向 proxy 上使用主體替代名稱清單根據您是否發佈連接埠 80 或連接埠 443 上的自動探索服務：

  - **在 [連接埠 80 上發佈**   如果自動探索服務的初始查詢發生透過連接埠 80，不需要任何憑證變更。 這是因為執行 Lync 的行動裝置會存取外部連接埠 80 上的反向 proxy，然後橋接至 Director 或前端伺服器上連接埠 8080 內部。 如需詳細資訊，請參閱 「 初始自動探索程序使用連接埠 80 」 一節[的 Technical requirements for Lync Server 2013 中的行動性](lync-server-2013-technical-requirements-for-mobility.md)。

  - **在 [連接埠 443 上發行**   上使用的外部 web 服務發行規則憑證的主體替代名稱清單必須包含*lyncdiscover。\<sipdomain\>* 每個 SIP 網域組織內的項目。
    
    <div>
    

    > [!IMPORTANT]  
    > 我們強烈建議使用 HTTPS over HTTP。 HTTPS 使用憑證來加密的流量。 HTTP 不提供加密，並傳送任何資料都將純文字。

    
    </div>

使用內部憑證授權單位作為憑證，通常是簡單的程序。 但對於使用 web 服務發行規則的公用憑證，新增多個主體替代名稱項目可能會變得昂貴。 若要解決此問題，我們可以支援的初始自動探索連線通訊埠 80，然後重新導向至 Director 或前端伺服器上的連接埠 8080。

<div>


> [!NOTE]  
> 如果您的 Lync Server 2013 基礎結構使用從內部憑證授權單位 (CA) 發出的內部憑證，且想要支援行動裝置以無線方式連線，則必須先安裝來自內部 CA 的任一根憑證鏈結在行動裝置或您必須變更為使用公用憑證上您的 Lync Server 2013 基礎結構。



</div>

本主題說明 Director、 前端伺服器和反向 proxy 所需的新增的主體替代名稱。 僅新增的主體替代名稱 (SAN) 參照。 請參閱規劃的區段在憑證上的其他項目上的指引。 如需詳細資訊，請參閱[Lync Server 2013 中 Director 的案例](lync-server-2013-scenarios-for-the-director.md)、 [Lync Server 2013 中的外部使用者存取的案例](lync-server-2013-scenarios-for-external-user-access.md)和[Lync Server 2013 中的反向 proxy 案例](lync-server-2013-scenarios-for-reverse-proxy.md)。

下表定義 Director 集區、 前端集區]，和反向 proxy 的自動探索 SAN 項目：

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
<td><p>SAN = lyncdiscoverinternal。&lt;內部網域名稱&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自動探索服務 URL</p></td>
<td><p>SAN = lyncdiscover。&lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 您將與新的 SAN 項目最近更新的憑證指派給預設憑證時。 或者，您可以使用 SAN = *。&lt;sipdomain&gt;。



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
<td><p>SAN = lyncdiscoverinternal。&lt;內部網域名稱&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自動探索服務 URL</p></td>
<td><p>SAN = lyncdiscover。&lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 您將與新的 SAN 項目最近更新的憑證指派給預設憑證時。 或者，您可以使用 SAN = *。&lt;sipdomain&gt;



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
<td><p>SAN = lyncdiscover。&lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 您將與新的 SAN 項目最近更新的憑證指派給反向 proxy 上的 SSL 接聽程式時。



</div>

</div>

<span> </span>

</div>

</div>

</div>

