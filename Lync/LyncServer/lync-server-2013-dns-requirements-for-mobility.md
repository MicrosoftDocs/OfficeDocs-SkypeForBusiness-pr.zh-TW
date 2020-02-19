---
title: Lync Server 2013： 行動的 DNS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7da4910594581f253db155bfceb85c0dcd78f60
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a>搭配 Lync Server 2013 的行動的 DNS 需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012 年 11 月 13 日_

當您部署 Lync Server 2013 行動功能時，您可以使用新的 Url，可用來搭配 Microsoft Lync Server 2013 自動探索服務，或您可以使用您現有的 Web 服務 Url。 如果您使用您現有的 Url，使用者需要在其行動裝置設定中手動輸入 Url。 此選項通常用於疑難排解。 當您使用新的 Url 時，行動用戶端可以自動探索 Lync Server 2013 的資源。 當您支援自動探索時，您需要新增新的網域名稱系統 (DNS) 記錄。 本節說明所需的自動探索 DNS 記錄。

若要支援自動探索，您需要建立下列 DNS 記錄每個 SIP 網域：

  - 內部 DNS 記錄，以支援從組織網路內部連線的行動使用者

  - 外部 (或公用) DNS 記錄，以支援從網際網路連線的行動使用者

內部自動探索 URL 應該不能從您的網路外部定址。 外部自動探索 URL 應該不能從您的網路內部定址。 不過，如果您不能符合外部 URL 的這項需求，行動用戶端具有相同的作用應該不會受到影響。

DNS 記錄可以是 CNAME 記錄或 A (主機) 記錄。

**內部 DNS 記錄**

您必須建立下列其中一個下列的內部 DNS 記錄：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>記錄類型</th>
<th>主機名稱或 SRV 定義</th>
<th>解析為</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscoverinternal。&lt;sipdomain&gt;</p></td>
<td><p>內部 Web 服務完整網域名稱 (FQDN) 或前端集區的 Director 集區，如果有的話，如果您不具備 Director</p></td>
</tr>
<tr class="even">
<td><p>A (主機)</p></td>
<td><p>lyncdiscoverinternal。&lt;sipdomain&gt;</p></td>
<td><p>內部 Web 服務 IP 位址 （虛擬 IP (VIP) 位址如果您使用負載平衡器） Director 集區，如果您有 director 或前端集區如果您不具備 Director</p></td>
</tr>
</tbody>
</table>


**外部 DNS 記錄**

您需要建立下列其中一項外部 DNS 記錄：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>記錄類型</th>
<th>主機名稱</th>
<th>解析為</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>外部 Web 服務 FQDN，Director 集區，如果您有 director 或前端集區如果您不具備 Director</p></td>
</tr>
<tr class="even">
<td><p>A (主機)</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>外部或公用 IP 位址 （VIP 位址如果您使用負載平衡器） 的反向 proxy</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_sipfederationtls._tcp。 &lt;sipdomain&gt;</p>
<p>會解析為主機 （A 或 AAAA） 記錄的 Access Edge service</p></td>
<td><p>若要支援推入通知服務和 Apple 推播通知服務，您可以建立的每個 SIP 網域具有 Microsoft Lync 行動用戶端的一筆 SRV 記錄。</p>
<div>

> [!IMPORTANT]  
> 這項要求只適用於 Apple 上的 Microsoft Lync 行動用戶端或 Microsoft 型的行動裝置。 Andriod 和 Nokia Symbian 裝置，請勿使用推播通知。


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lyncdiscover，又稱為自動探索、 流量會通過反向 proxy。 SRV 記錄會指向解析透過 Access Edge service 的記錄。



</div>

</div>

<span> </span>

</div>

</div>

</div>

