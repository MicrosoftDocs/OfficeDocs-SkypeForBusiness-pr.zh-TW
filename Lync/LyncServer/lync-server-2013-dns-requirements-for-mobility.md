---
title: Lync Server 2013：行動性的 DNS 需求
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
ms.openlocfilehash: 508e9c8e030de7aeb496a1285ff7b965e43c2a6b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501430"
---
# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a>使用 Lync Server 2013 行動的 DNS 需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-13_

當您部署 Lync Server 2013 行動功能時，您可以使用 Microsoft Lync Server 2013 自動探索服務提供的新 URLs，也可以使用現有的 Web 服務 URLs。 如果您使用現有的 URLs，使用者必須在行動裝置設定中手動輸入 URLs。 此選項通常用於疑難排解。 當您使用新的 URLs 時，行動用戶端可以自動探索 Lync Server 2013 資源。 當您支援自動探索時，您必須新增網域名稱系統 (DNS) 記錄。 本節說明自動探索所需的 DNS 記錄。

若要支援自動探索，您必須為每個 SIP 網域建立下列 DNS 記錄：

  - 內部 DNS 記錄，以支援從組織網路內部連線的行動使用者

  - 外部 (或公用) DNS 記錄，以支援從網際網路連線的行動使用者

內部自動探索 URL 應該不能從您的網路外部定址。 外部自動探索 URL 應該不能從您的網路內部定址。 不過，如果您無法滿足外部 URL 的此需求，行動用戶端功能應該不會受到影響。

DNS 記錄可以是 CNAME 記錄或 A (主機) 記錄。

**內部 DNS 記錄**

您必須建立下列其中一個內部 DNS 記錄：


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
<td><p>lyncdiscoverinternal。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
<td><p>內部 Web 服務完整功能變數名稱 (Director 集區的 FQDN) （如果有的話），或如果您沒有 Director，則為前端集區。</p></td>
</tr>
<tr class="even">
<td><p>A (主機)</p></td>
<td><p>lyncdiscoverinternal。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
<td><p>內部 Web 服務 IP 位址 (虛擬 IP (VIP) 位址如果您擁有 Director 集區的負載平衡器) （如果有的話），或如果您沒有 Director，則使用的前端集區。</p></td>
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
<td><p>lyncdiscover. &lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
<td><p>Director 集區的外部 Web 服務 FQDN （如果有的話），或如果您沒有 Director，則為前端集區。</p></td>
</tr>
<tr class="even">
<td><p>A (主機)</p></td>
<td><p>lyncdiscover. &lt;microsoft.rtc.management.xds.sipdomain&gt;</p></td>
<td><p>當您使用反向 proxy 的負載平衡器) 時，的外部或公用 IP 位址 (VIP 位址</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_sipfederationtls _sipfederationtls._tcp。 &lt;microsoft.rtc.management.xds.sipdomain&gt;</p>
<p>解析為 Access Edge service 的主機 (A 或 AAAA) 記錄</p></td>
<td><p>若要支援推播通知服務和 Apple Push Notification 服務，您可以為每個具有 Microsoft Lync Mobile 用戶端的 SIP 網域建立一個 SRV 記錄。</p>
<div>

> [!IMPORTANT]  
> 這項需求只適用于 Apple 或 Microsoft 移動裝置上的 Microsoft Lync 行動用戶端。 Andriod 和 Nokia Symbian 裝置不使用推播通知。


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lyncdiscover （也稱為自動探索）流量會透過反向 proxy 進行。 SRV 記錄指向透過 Access Edge service 解析的記錄。



</div>

</div>

<span> </span>

</div>

</div>

</div>

