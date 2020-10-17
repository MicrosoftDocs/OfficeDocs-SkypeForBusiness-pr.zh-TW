---
title: Lync Server 2013： XMPP 同盟合作夥伴的協商設定
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
ms.openlocfilehash: bdb09d52970b5fd97395acda6a2e4fbc824a378d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505590"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a>Lync Server 2013 中 XMPP 同盟合作夥伴的協商設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-21_

XMPP 合作夥伴設定中的協商類型設定具有多種可能的組合。 並非所有的組合都是有效的。 本主題所述的表格會定義有效且不正確設定。 通用設定會顯示在第一個表格中，第二個表格會詳細說明所有可能的組合。 請注意，除非也可以使用「*傳輸層安全性* (TLS) ，**否則**不能讓*簡單驗證及安全性層* (SASL) 。 SASL 會以未加密的 (可讀取的) 格式傳送，除非受到另一種方式（如 TLS）保護，否則決不會傳送。

### <a name="common-xmpp-federation-negotiation-methods"></a>一般 XMPP 同盟協商方法

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
<th>傳輸層安全性 (TLS)</th>
<th>簡單驗證及安全性層 (SASL) </th>
<th>回撥驗證</th>
<th>預期的驗證方法 (s) </th>
<th>注意事項</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>必要</p></td>
<td><p>必要</p></td>
<td><p>False</p></td>
<td><p>SASL over TLS</p></td>
<td><p>需要 TLS 和 SASL，有助於確保 SASL 郵件資料流程安全。 如果 XMPP 同盟協力廠商未將 TLS 設定為 [必要] 或 [選用]，則無法使用回撥方法。</p></td>
</tr>
<tr class="even">
<td><p>必要</p></td>
<td><p>選用</p></td>
<td><p>是</p></td>
<td><p>SASL over TLS、TLS 回撥、TCP 回撥</p></td>
<td><p>在需要 TLS 的情況下，如果 XMPP 同盟協力廠商已將 SASL 設定為選用或必要的 SASL。 如果無法使用 SASL，將會使用以 TLS 進行回撥。</p></td>
</tr>
<tr class="odd">
<td><p>選用</p></td>
<td><p>選用</p></td>
<td><p>是</p></td>
<td><p>SASL over TLS、TLS 回撥、TCP 回撥</p></td>
<td><p>在提供的協商方法中非常靈活，這些設定會依賴 XMPP 同盟協力廠商的設定。 如果合作夥伴具有 TLS 選用或必要，但不支援 SASL，則 TLS 回撥將可供使用。 如果夥伴的 TLS 和 SASL 設定為 [選用] 或 [必要]，則會使用在 SASL 上的最佳選取 TLS。</p></td>
</tr>
<tr class="even">
<td><p>不支援</p></td>
<td><p>不支援</p></td>
<td><p>是</p></td>
<td><p>TCP 回撥</p></td>
<td><p>在許多情況下，TCP 回撥是唯一可行的解決方案。 比其他選項還不可取，它提供一定層級的信任。</p></td>
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
<th>傳輸層安全性 (TLS)</th>
<th>簡單驗證及安全性層 (SASL) </th>
<th>回撥驗證</th>
<th>預期的驗證方法</th>
<th>無效設定的附注、警告或錯誤</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>必要</p></td>
<td><p>必要</p></td>
<td><p>是</p></td>
<td><p>SASL over TLS</p></td>
<td><div>

> [!WARNING]  
> 如果需要 SASL 和 TLS，則回撥不會運作。


</div></td>
</tr>
<tr class="even">
<td><p>必要</p></td>
<td><p>必要</p></td>
<td><p>False</p></td>
<td><p>SASL over TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>選用</p></td>
<td><p>必要</p></td>
<td><p>是</p></td>
<td><p>SASL over TLS、TLS 回撥、TCP 回撥</p></td>
<td><div>

> [!WARNING]  
> SASL 要求 TLS。 允許 TLS 為選用可能會導致會話協商失敗。


</div></td>
</tr>
<tr class="even">
<td><p>選用</p></td>
<td><p>必要</p></td>
<td><p>False</p></td>
<td><p>SASL over TLS</p></td>
<td><div>

> [!WARNING]  
> SASL 要求 TLS。 允許 TLS 為選用可能會導致會話協商失敗。


</div></td>
</tr>
<tr class="odd">
<td><p>不支援</p></td>
<td><p>必要</p></td>
<td><p>是</p></td>
<td><p>TCP 回撥</p></td>
<td><div>

> [!WARNING]  
> SASL 要求 TLS。 允許 TLS 為選用可能會導致會話協商失敗。


</div></td>
</tr>
<tr class="even">
<td><p>不支援</p></td>
<td><p>必要</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> 無效設定


</div></td>
<td><div>

> [!WARNING]  
> 因為 SASL 需要 TLS，而 TLS 無法使用，所以 SASL/TLS 無法成功。 TCP 回撥是設定為 false，且無法使用。


</div></td>
</tr>
<tr class="odd">
<td><p>必要</p></td>
<td><p>選用</p></td>
<td><p>是</p></td>
<td><p>SASL over TLS，TLS 回撥</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>必要</p></td>
<td><p>選用</p></td>
<td><p>False</p></td>
<td><p>SASL over TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>選用</p></td>
<td><p>選用</p></td>
<td><p>是</p></td>
<td><p>SASL over TLS、TLS 回撥、TCP 回撥</p></td>
<td><div>

> [!WARNING]  
> SASL 要求 TLS。 允許 TLS 為選用可能會導致會話協商失敗。


</div></td>
</tr>
<tr class="even">
<td><p>選用</p></td>
<td><p>選用</p></td>
<td><p>False</p></td>
<td><p>SASL over TLS</p></td>
<td><div>

> [!WARNING]  
> SASL 要求 TLS。 允許 TLS 為選用可能會導致會話協商失敗。


</div></td>
</tr>
<tr class="odd">
<td><p>不支援</p></td>
<td><p>選用</p></td>
<td><p>是</p></td>
<td><p>TCP 回撥</p></td>
<td><div>

> [!WARNING]  
> SASL 要求 TLS。 允許 TLS 為選用可能會導致會話協商失敗。


</div></td>
</tr>
<tr class="even">
<td><p>不支援</p></td>
<td><p>選用</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> 無效設定


</div></td>
<td><div>

> [!WARNING]  
> SASL 要求 TLS。 允許 TLS 為選用可能會導致會話協商失敗。


</div></td>
</tr>
<tr class="odd">
<td><p>必要</p></td>
<td><p>不支援</p></td>
<td><p>是</p></td>
<td><p>TLS 回撥</p></td>
<td><p>設定允許 TLS 回撥。</p></td>
</tr>
<tr class="even">
<td><p>必要</p></td>
<td><p>不支援</p></td>
<td><p>False</p></td>
<td><p>無效設定</p></td>
<td><div>

> [!WARNING]  
> 必須啟用 SASL 或回撥。


</div></td>
</tr>
<tr class="odd">
<td><p>選用</p></td>
<td><p>不支援</p></td>
<td><p>是</p></td>
<td><p>TLS 回撥，TCP 回撥</p></td>
<td><p>根據其他端點的協商選擇，會接受 TCP 或 TLS 回撥。</p></td>
</tr>
<tr class="even">
<td><p>選用</p></td>
<td><p>不支援</p></td>
<td><p>False</p></td>
<td><p>無效設定</p></td>
<td><div>

> [!WARNING]  
> 必須啟用 SASL 或回撥。


</div></td>
</tr>
<tr class="odd">
<td><p>不支援</p></td>
<td><p>不支援</p></td>
<td><p>是</p></td>
<td><p>TCP 回撥</p></td>
<td><p>TCP 回撥是唯一可用的協商方法</p></td>
</tr>
<tr class="even">
<td><p>不支援</p></td>
<td><p>不支援</p></td>
<td><p>False</p></td>
<td><p>無效設定</p></td>
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

