---
title: Lync Server 2013：行動憑證需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f62b05fd77151250e352c62cad7084d1bb90926
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a>Lync Server 2013 中的行動憑證需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-24_

如果您部署行動裝置功能，且支援行動用戶端的自動探索，您必須在憑證上包含特定的消費者替換名稱專案，以支援行動用戶端的安全連線。

您必須在下列憑證上包含消費者備用名稱專案，才能自動探索：

  - 主管池

  - 前端集區

  - 反向 proxy

本節說明您在自動探索的憑證上所需的主題替換名稱專案。

<div>


> [!NOTE]  
> 使用內部憑證授權單位重新頒發憑證通常是一個簡單的程式，但新增多個 subject 替換名稱專案到反向 proxy 使用的公用憑證可能會很昂貴。 如果您有多個 SIP 網域，增加消費者備用名稱的費用非常昂貴，您可以將反向 proxy 設定為使用 HTTP 取得初始自動探索服務要求，而不是使用 HTTPS （預設設定）。 如需詳細資訊，請參閱<A href="lync-server-2013-technical-requirements-for-mobility.md">Lync Server 2013 中行動的技術需求</A>。



</div>

### <a name="director-pool-certificate-requirements"></a>控制器池證書需求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>描述</th>
<th>消費者替換名稱專案</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>內部自動探索服務 URL</p></td>
<td><p>SAN = lyncdiscoverinternal。&lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自動探索服務 URL</p></td>
<td><p>SAN = lyncdiscover。&lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 或者，您也可以使用 SAN = *。&lt;sipdomain&gt;



</div>

### <a name="front-end-pool-certificate-requirements"></a>前端池憑證需求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>描述</th>
<th>消費者替換名稱專案</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>內部自動探索服務 URL</p></td>
<td><p>SAN = lyncdiscoverinternal。&lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自動探索服務 URL</p></td>
<td><p>SAN = lyncdiscover。&lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 或者，您也可以使用 SAN = *。&lt;sipdomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>反向 Proxy （公用 CA）憑證需求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>描述</th>
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
> 您可以將這個 SAN 指派給在反向 proxy 上指派給 SSL 監聽程式的憑證。



</div>

<div>


> [!NOTE]  
> 您的反向 proxy 偵聽程式將會針對您的外部 Web 服務 URL （例如 SAN = lyncwebextpool01 .com）及 dirwebexternal.contoso.com （如果您已部署選用的控制器），提供消費者替換名稱。



</div>

</div>

<span> </span>

</div>

</div>

</div>

