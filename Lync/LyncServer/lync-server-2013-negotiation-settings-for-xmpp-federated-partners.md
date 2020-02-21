---
title: Lync Server 2013： 交涉設定為 XMPP 同盟協力廠商
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
ms.openlocfilehash: ab897bf5bc9d959089090ebeaaddc4d766549401
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a>交涉設定為 XMPP 同盟協力廠商在 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-21_

設定中的 XMPP 協力廠商的交涉類型的設定有各種可能的組合。 並非所有的這些組合都有效。 本主題中詳述的表格會定義有效及無效的設定。 一般設定一文中所述的第一個表格，其中所有可能組合第二個表格。 請注意，您不能有*簡單驗證及安全性階層*(SASL)**除非***傳輸層安全性*(TLS) 也是可用的。 SASL 傳送以未加密 （讀取） 的格式，且應該永遠不容許傳輸除非由另一個方法，例如 TLS 保護。

### <a name="common-xmpp-federation-negotiation-methods"></a>常見的 XMPP 同盟交涉方法

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
<th>簡單驗證及安全性階層 (SASL)</th>
<th>回撥驗證</th>
<th>預期的驗證方法</th>
<th>附註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>必要</p></td>
<td><p>必要</p></td>
<td><p>False</p></td>
<td><p>SASL 優於 TLS</p></td>
<td><p>需要協助確保 SASL 郵件資料流是安全的 TLS 和 SASL。 回撥不提供，如果 XMPP 同盟協力廠商不必要或選用設定 TLS 無法用於後援方法。</p></td>
</tr>
<tr class="even">
<td><p>必要</p></td>
<td><p>選擇性</p></td>
<td><p>True</p></td>
<td><p>SASL 優於 TLS、 TLS 回撥、 TCP 回撥</p></td>
<td><p>依需要 TLS，會使用 XMPP 同盟協力廠商已將 SASL 設定為選用或必要 SASL。 如果無法使用 SASL，則會使用透過 TLS 的回撥。</p></td>
</tr>
<tr class="odd">
<td><p>選用</p></td>
<td><p>選用</p></td>
<td><p>True</p></td>
<td><p>SASL 優於 TLS、 TLS 回撥、 TCP 回撥</p></td>
<td><p>雖然很有彈性中提供的交涉方法，這些設定會依賴 XMPP 同盟協力廠商的設定。 如果協力廠商 TLS 選用或必要，但不是支援 SASL，則可使用 TLS 回撥。 如果協力廠商 TLS 和 SASL 設為選用或必要，會使用 TLS over SASL 最佳選擇。</p></td>
</tr>
<tr class="even">
<td><p>不支援</p></td>
<td><p>不支援</p></td>
<td><p>True</p></td>
<td><p>TCP 回撥</p></td>
<td><p>在許多情況下，TCP 回撥是唯一可能的解決方案。 較不建議比其他選項，但是它提供某種程度的信任。</p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a>XMPP 同盟交涉方法矩陣： 完成

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
<th>簡單驗證及安全性階層 (SASL)</th>
<th>回撥驗證</th>
<th>預期的驗證方法</th>
<th>備忘稿、 警告或錯誤不正確的設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>必要</p></td>
<td><p>必要</p></td>
<td><p>True</p></td>
<td><p>SASL 優於 TLS</p></td>
<td><div>

> [!WARNING]  
> 如果需要 SASL 與 TLS 的回撥將無法運作。


</div></td>
</tr>
<tr class="even">
<td><p>必要</p></td>
<td><p>必要</p></td>
<td><p>False</p></td>
<td><p>SASL 優於 TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>選用</p></td>
<td><p>必要</p></td>
<td><p>True</p></td>
<td><p>SASL 優於 TLS、 TLS 回撥、 TCP 回撥</p></td>
<td><div>

> [!WARNING]  
> SASL 要求 TLS。 允許為選用的 TLS，可能會造成失敗的工作階段交涉。


</div></td>
</tr>
<tr class="even">
<td><p>選用</p></td>
<td><p>必要</p></td>
<td><p>False</p></td>
<td><p>SASL 優於 TLS</p></td>
<td><div>

> [!WARNING]  
> SASL 要求 TLS。 允許為選用的 TLS，可能會造成失敗的工作階段交涉。


</div></td>
</tr>
<tr class="odd">
<td><p>不支援</p></td>
<td><p>必要</p></td>
<td><p>True</p></td>
<td><p>TCP 回撥</p></td>
<td><div>

> [!WARNING]  
> SASL 要求 TLS。 允許為選用的 TLS，可能會造成失敗的工作階段交涉。


</div></td>
</tr>
<tr class="even">
<td><p>不支援</p></td>
<td><p>必要</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> 無效組態


</div></td>
<td><div>

> [!WARNING]  
> 因為 SASL 需要 TLS、 TLS 不提供，SASL/TLS 無法成功。 TCP 回撥設定為 false，並無法使用。


</div></td>
</tr>
<tr class="odd">
<td><p>必要</p></td>
<td><p>選擇性</p></td>
<td><p>True</p></td>
<td><p>SASL 優於 TLS、 TLS 回撥</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>必要</p></td>
<td><p>選擇性</p></td>
<td><p>False</p></td>
<td><p>SASL 優於 TLS</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>選用</p></td>
<td><p>選用</p></td>
<td><p>True</p></td>
<td><p>SASL 優於 TLS、 TLS 回撥、 TCP 回撥</p></td>
<td><div>

> [!WARNING]  
> SASL 要求 TLS。 允許為選用的 TLS，可能會造成失敗的工作階段交涉。


</div></td>
</tr>
<tr class="even">
<td><p>選用</p></td>
<td><p>選用</p></td>
<td><p>False</p></td>
<td><p>SASL 優於 TLS</p></td>
<td><div>

> [!WARNING]  
> SASL 要求 TLS。 允許為選用的 TLS，可能會造成失敗的工作階段交涉。


</div></td>
</tr>
<tr class="odd">
<td><p>不支援</p></td>
<td><p>選用</p></td>
<td><p>True</p></td>
<td><p>TCP 回撥</p></td>
<td><div>

> [!WARNING]  
> SASL 要求 TLS。 允許為選用的 TLS，可能會造成失敗的工作階段交涉。


</div></td>
</tr>
<tr class="even">
<td><p>不支援</p></td>
<td><p>選用</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> 無效組態


</div></td>
<td><div>

> [!WARNING]  
> SASL 要求 TLS。 允許為選用的 TLS，可能會造成失敗的工作階段交涉。


</div></td>
</tr>
<tr class="odd">
<td><p>必要</p></td>
<td><p>不支援</p></td>
<td><p>True</p></td>
<td><p>TLS 回撥</p></td>
<td><p>組態可用於 TLS 回撥。</p></td>
</tr>
<tr class="even">
<td><p>必要</p></td>
<td><p>不支援</p></td>
<td><p>False</p></td>
<td><p>無效組態</p></td>
<td><div>

> [!WARNING]  
> SASL 或回撥必須啟用。


</div></td>
</tr>
<tr class="odd">
<td><p>選用</p></td>
<td><p>不支援</p></td>
<td><p>True</p></td>
<td><p>TLS 回撥、 TCP 回撥</p></td>
<td><p>根據其他端點的交涉選擇，TCP 或 TLS 回撥將被接受。</p></td>
</tr>
<tr class="even">
<td><p>選用</p></td>
<td><p>不支援</p></td>
<td><p>False</p></td>
<td><p>無效組態</p></td>
<td><div>

> [!WARNING]  
> SASL 或回撥必須啟用。


</div></td>
</tr>
<tr class="odd">
<td><p>不支援</p></td>
<td><p>不支援</p></td>
<td><p>True</p></td>
<td><p>TCP 回撥</p></td>
<td><p>TCP 回撥是可用的唯一的交涉方法</p></td>
</tr>
<tr class="even">
<td><p>不支援</p></td>
<td><p>不支援</p></td>
<td><p>False</p></td>
<td><p>無效組態</p></td>
<td><div>

> [!WARNING]  
> SASL 或回撥必須啟用。


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

