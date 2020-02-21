---
title: Lync Server 2013： 憑證摘要-DNS 與 HLB 負載平衡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 055f1eea81f67281384e6a6124b5c72cee6d823f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a>憑證摘要-DNS 與 HLB 負載平衡 Lync Server 2013 中

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-22_

搭配 DNS Director 的憑證需求的負載平衡與硬體負載平衡器會使用預設的憑證具有主旨名稱和主體替代名稱 Director 可接收的服務。 憑證要求的每個 Director 集區中。 必須注意的是，硬體負載平衡器僅對於來自反向 Proxy 的流量進行負載平衡。 此外，各個伺服器上安裝的 OAuth 語彙基元憑證可用於伺服器對伺服器驗證用途。

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
<td><p>dirpool01.contoso.net</p></td>
<td><p>dirpool01.contoso.net</p>
<p>dir01.contoso.net</p>
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

