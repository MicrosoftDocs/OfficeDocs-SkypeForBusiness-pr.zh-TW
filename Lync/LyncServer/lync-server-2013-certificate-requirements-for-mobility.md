---
title: Lync Server 2013：行動的憑證需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e1267710405cb9b6c4e64d9cf2e31fb63feddaa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a>Lync Server 2013 中行動的憑證需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-24_

如果您部署行動性功能並支援行動用戶端的自動探索，您需要在憑證上加入特定主體替代名稱專案，以支援行動用戶端的安全連線。

您必須在下列憑證中包含主體替代名稱專案，以進行自動探索：

  - Director pool

  - 前端集區

  - 反向 Proxy

本節說明自動探索憑證所需的主體替代名稱專案。

<div>


> [!NOTE]  
> 使用內部憑證授權單位重新發出憑證通常是很簡單的程序，但是新增多個主體替代名稱項目至反向 Proxy 所使用的公用憑證會很昂貴。 如果您有多個 SIP 網域，增加主體別名的加入是非常昂貴的，您可以設定反向 proxy 使用 HTTP 來進行初始自動探索服務要求，而不是使用 HTTPS (預設設定) 。 如需詳細資訊，請參閱<A href="lync-server-2013-technical-requirements-for-mobility.md">Lync Server 2013 中行動的技術需求</A>。



</div>

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
<td><p>SAN = lyncdiscoverinternal。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自動探索服務 URL</p></td>
<td><p>SAN = lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 或者，您也可以使用 SAN = *。 &lt;microsoft.rtc.management.xds.sipdomain&gt;



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
<td><p>SAN = lyncdiscoverinternal。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自動探索服務 URL</p></td>
<td><p>SAN = lyncdiscover。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 或者，您也可以使用 SAN = *。 &lt;microsoft.rtc.management.xds.sipdomain&gt;



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
> 您將此 SAN 指派給反向 proxy 上的 SSL 接聽程式所指派的憑證。



</div>

<div>


> [!NOTE]  
> 如果您已部署選用的 Director) ，您的反向 proxy 攔截器將會有您的外部 Web 服務 URL 的主體替代名稱 (s)  (例如 SAN=lyncwebextpool01.contoso.com 及 dirwebexternal.contoso.com。



</div>

</div>

<span> </span>

</div>

</div>

</div>

