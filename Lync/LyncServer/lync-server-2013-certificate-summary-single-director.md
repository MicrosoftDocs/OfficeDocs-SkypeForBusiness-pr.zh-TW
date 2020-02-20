---
title: Lync Server 2013： 憑證摘要-單一 Director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single Director
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48183546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 677f9cf6e7cc9d260846598023435f33d2ebd2fc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-director-in-lync-server-2013"></a>憑證摘要-Lync Server 2013 中的單一 Director

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-08_

單一 Director 的憑證需求所組成的預設憑證，有一個主旨名稱和主體替代名稱 Director 可接收的服務。 此外，還包含用於伺服器對伺服器驗證所需的 OAuth Token 憑證。

### <a name="certificates-for-director"></a>Director 憑證

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
<th>主體名稱 (SN)</th>
<th>主體替代名稱 (SAN)</th>
<th>註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>預設</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(選用) *.contoso.com</p></td>
<td><p>可向內部管理的憑證授權單位 (CA) 或公用 ca 要求 director 的憑證。</p>
<p>Director 回應要求從周邊網路中的反向 proxy 或 Edge Server。 內部用戶端不會使用 Director。</p>
<p>或是簡單 URL 的萬用字元項目</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>無項目</p></td>
<td><div>

> [!IMPORTANT]  
> 請注意，雖然最小金鑰長度是 1024，但是您可能會收到警告表示建議最小金鑰長度為 2048 位元。


</div>
<p>OAuthTokenIssuer 憑證是單一目的憑證，用於驗證大規模環境中的伺服器，且可向內部 CA 或公用 CA 要求。此憑證為必要。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

