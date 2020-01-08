---
title: 憑證摘要 - 調整式 Director 集區 (硬體負載平衡器)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21b1688641d09e00c82ea952d57bd2a9547ac0dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a>Lync Server 2013 中的憑證摘要 - 調整式 Director 集區 (硬體負載平衡器)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-20_

具有硬體負載平衡器之主管的憑證需求將會使用預設認證，該預設憑證具有 [受領人名稱] 和 [消費者名稱] 的預設憑證，且可供控制器擁有者接收。 針對池中的每個主管要求憑證。 此外，在每個伺服器上安裝的伺服器到伺服器驗證目的都有 OAuth 權杖憑證。

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a>使用硬體負載平衡器的縮放控制器憑證

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
<td><p>dirpool01.contoso.net</p></td>
<td><p>dirpool01.contoso.net</p>
<p>dir01.contoso.net</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>lyncdiscoverinternal.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>（選擇性） *. contoso.com</p></td>
<td><p>您可以從內部管理的憑證授權單位（CA）或公用 CA 來要求控制器證書。</p>
<p>控制器會回應來自週邊或從邊緣伺服器的反向 proxy 要求。</p>
<p>或者，簡單 Url 的萬用字元專案</p></td>
</tr>
<tr class="even">
<td><p>OAuthTokenIssuer</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>無專案</p></td>
<td>


> [!IMPORTANT]
> 請注意，最小金鑰長度是1024，但是您可能會收到「建議」金鑰長度最小的警告（2048位）。


<p>OAuthTokenIssuer 憑證是單一用途的憑證，目的在於驗證大型環境中的伺服器，而且可以從內部 CA 或公用 CA 進行申請。 需要證書。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

