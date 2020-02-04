---
title: Lync Server 2013：XMPP 同盟夥伴的交涉設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 995ee34d0a2dcf28ca6aa4f8158d0e08d1533191
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a>Lync Server 2013 中 XMPP 同盟夥伴的交涉設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-21_

XMPP 合作夥伴設定中協商類型的設定有多種可能的組合。 並非所有這些組合都是有效的。 本主題中所述的表格將定義有效和不正確設定。 常見的設定會顯示在第一個資料表中，第二個數據表描述所有可能的組合。 請注意，除非也提供*傳輸層安全性*（TLS），**否則**您不能有*簡單的驗證與安全性層*（SASL）。 SASL 是以未加密（可讀）的格式傳送，除非受到其他方法（例如 TLS）保護，否則切勿傳送。

### <a name="common-xmpp-federation-negotiation-methods"></a>常見的 XMPP 聯盟協商方法

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>傳輸層安全性（TLS）</th>
<th>簡單驗證與安全性層（SASL）</th>
<th>回撥（驗證）</th>
<th>預期的驗證方法</th>
<th>筆記</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>必要</p></td>
<td><p>必要</p></td>
<td><p>虛假</p></td>
<td><p>TLS 之上的 SASL</p></td>
<td><p>TLS 和 SASL 所需的資訊有助於確保 SASL 訊息資料流程是安全的。 如果 XMPP 聯盟合作夥伴未將 TLS 設定為 [必要] 或 [選用]，就無法使用回撥，且無法用於 fallback 方法。</p></td>
</tr>
<tr class="even">
<td><p>必要</p></td>
<td><p>選用</p></td>
<td><p>滿足</p></td>
<td><p>TLS 上的 SASL、TLS 回撥、TCP 回撥</p></td>
<td><p>如果 XMPP 聯盟合作夥伴已將 [SASL] 設定為 [選用] 或 [所需的 SASL]，請使用 TLS。 如果沒有可用的 SASL，將會使用 TLS 上的回撥。</p></td>
</tr>
<tr class="odd">
<td><p>選用</p></td>
<td><p>選用</p></td>
<td><p>滿足</p></td>
<td><p>TLS 上的 SASL、TLS 回撥、TCP 回撥</p></td>
<td><p>在提供的協商方法中非常靈活，這些設定會依賴 XMPP 聯盟夥伴的設定。 如果合作夥伴選用 TLS 選擇性或必要，但不支援 SASL，則可以使用 TLS 回撥。 如果合作夥伴將 TLS 和 SASL 設定為 [選用] 或 [必要]，則會使用在 SASL 上最佳的 TLS 選取。</p></td>
</tr>
<tr class="even">
<td><p>不支援</p></td>
<td><p>不支援</p></td>
<td><p>滿足</p></td>
<td><p>TCP 回撥</p></td>
<td><p>在許多情況下，TCP 回撥是唯一可行的解決方法。 比其他選項更不可取，它會提供一定層面的信任。</p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a>XMPP 同盟協商方法矩陣-完成

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>傳輸層安全性（TLS）</th>
<th>簡單驗證與安全性層（SASL）</th>
<th>回撥（驗證）</th>
<th>預期驗證方法</th>
<th>無法正確設定的記事、警告或錯誤</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>必要</p></td>
<td><p>必要</p></td>
<td><p>滿足</p></td>
<td><p>TLS 之上的 SASL</p></td>
<td><div>

> [!WARNING]  
> 如果需要 SASL 和 TLS，回撥將無法運作。


</div></td>
</tr>
<tr class="even">
<td><p>必要</p></td>
<td><p>必要</p></td>
<td><p>虛假</p></td>
<td><p>TLS 之上的 SASL</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>選用</p></td>
<td><p>必要</p></td>
<td><p>滿足</p></td>
<td><p>TLS 上的 SASL、TLS 回撥、TCP 回撥</p></td>
<td><div>

> [!WARNING]  
> SASL 需要 TLS。 [允許 TLS 為選用] 可能會導致會話協商失敗。


</div></td>
</tr>
<tr class="even">
<td><p>選用</p></td>
<td><p>必要</p></td>
<td><p>虛假</p></td>
<td><p>TLS 之上的 SASL</p></td>
<td><div>

> [!WARNING]  
> SASL 需要 TLS。 [允許 TLS 為選用] 可能會導致會話協商失敗。


</div></td>
</tr>
<tr class="odd">
<td><p>不支援</p></td>
<td><p>必要</p></td>
<td><p>滿足</p></td>
<td><p>TCP 回撥</p></td>
<td><div>

> [!WARNING]  
> SASL 需要 TLS。 [允許 TLS 為選用] 可能會導致會話協商失敗。


</div></td>
</tr>
<tr class="even">
<td><p>不支援</p></td>
<td><p>必要</p></td>
<td><p>虛假</p></td>
<td><div>

> [!WARNING]  
> 不正確設定


</div></td>
<td><div>

> [!WARNING]  
> 因為 SASL 需要 TLS，而且 TLS 無法使用，所以 SASL/TLS 無法成功。 TCP 回撥是設定為 false，而且無法使用。


</div></td>
</tr>
<tr class="odd">
<td><p>必要</p></td>
<td><p>選用</p></td>
<td><p>滿足</p></td>
<td><p>TLS 上的 SASL，TLS 回撥</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>必要</p></td>
<td><p>選用</p></td>
<td><p>虛假</p></td>
<td><p>TLS 之上的 SASL</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>選用</p></td>
<td><p>選用</p></td>
<td><p>滿足</p></td>
<td><p>TLS 上的 SASL、TLS 回撥、TCP 回撥</p></td>
<td><div>

> [!WARNING]  
> SASL 需要 TLS。 [允許 TLS 為選用] 可能會導致會話協商失敗。


</div></td>
</tr>
<tr class="even">
<td><p>選用</p></td>
<td><p>選用</p></td>
<td><p>虛假</p></td>
<td><p>TLS 之上的 SASL</p></td>
<td><div>

> [!WARNING]  
> SASL 需要 TLS。 [允許 TLS 為選用] 可能會導致會話協商失敗。


</div></td>
</tr>
<tr class="odd">
<td><p>不支援</p></td>
<td><p>選用</p></td>
<td><p>滿足</p></td>
<td><p>TCP 回撥</p></td>
<td><div>

> [!WARNING]  
> SASL 需要 TLS。 [允許 TLS 為選用] 可能會導致會話協商失敗。


</div></td>
</tr>
<tr class="even">
<td><p>不支援</p></td>
<td><p>選用</p></td>
<td><p>虛假</p></td>
<td><div>

> [!WARNING]  
> 不正確設定


</div></td>
<td><div>

> [!WARNING]  
> SASL 需要 TLS。 [允許 TLS 為選用] 可能會導致會話協商失敗。


</div></td>
</tr>
<tr class="odd">
<td><p>必要</p></td>
<td><p>不支援</p></td>
<td><p>滿足</p></td>
<td><p>TLS 回撥</p></td>
<td><p>[配置] 允許 TLS 回撥。</p></td>
</tr>
<tr class="even">
<td><p>必要</p></td>
<td><p>不支援</p></td>
<td><p>虛假</p></td>
<td><p>不正確設定</p></td>
<td><div>

> [!WARNING]  
> 必須啟用 SASL 或回撥。


</div></td>
</tr>
<tr class="odd">
<td><p>選用</p></td>
<td><p>不支援</p></td>
<td><p>滿足</p></td>
<td><p>TLS 回撥，TCP 回撥</p></td>
<td><p>根據另一個端點的協商選項，將會接受 TCP 或 TLS 回撥。</p></td>
</tr>
<tr class="even">
<td><p>選用</p></td>
<td><p>不支援</p></td>
<td><p>虛假</p></td>
<td><p>不正確設定</p></td>
<td><div>

> [!WARNING]  
> 必須啟用 SASL 或回撥。


</div></td>
</tr>
<tr class="odd">
<td><p>不支援</p></td>
<td><p>不支援</p></td>
<td><p>滿足</p></td>
<td><p>TCP 回撥</p></td>
<td><p>TCP 回撥是唯一可用的協商方法</p></td>
</tr>
<tr class="even">
<td><p>不支援</p></td>
<td><p>不支援</p></td>
<td><p>虛假</p></td>
<td><p>不正確設定</p></td>
<td><div>

> [!WARNING]  
> 必須啟用 SASL 或回撥。


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

