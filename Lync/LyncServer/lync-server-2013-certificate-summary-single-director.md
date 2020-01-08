---
title: Lync Server 2013：憑證摘要 - 單一 Director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Single Director
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48183546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e44be0ca76a1926a1515657a9d7d5646a49390c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-director-in-lync-server-2013"></a>Lync Server 2013 中的憑證摘要 - 單一 Director

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

單一控制器的憑證需求是由控制器可以接收之服務的主體名稱和消費者替代名稱所組成的預設憑證所組成。 此外，有一個用於伺服器驗證的 OAuth 權杖憑證。

### <a name="certificates-for-director"></a>主管的憑證

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>元件</th>
<th>消費者名稱（SN）</th>
<th>消費者備用名稱（SAN）</th>
<th>批註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>設置</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>（選擇性） *. contoso.com</p></td>
<td><p>您可以從內部管理的憑證授權單位（CA）或公用 CA 來要求控制器證書。</p>
<p>控制器會回應來自週邊或從邊緣伺服器的反向 proxy 要求。 內部用戶端不會使用控制器。</p>
<p>或者，簡單 Url 的萬用字元專案</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>無專案</p></td>
<td><div>

> [!IMPORTANT]  
> 請注意，最小金鑰長度是1024，但是您可能會收到「建議」金鑰長度最小的警告（2048位）。


</div>
<p>OAuthTokenIssuer 憑證是單一用途的憑證，目的在於驗證大型環境中的伺服器，而且可以從內部 CA 或公用 CA 進行申請。 需要證書。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

