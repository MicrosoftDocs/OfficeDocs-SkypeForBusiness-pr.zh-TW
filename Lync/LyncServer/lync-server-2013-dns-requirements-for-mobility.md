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
ms.openlocfilehash: bc11c79c291f7db7ad9e9e3228644ee27d42e555
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a>使用 Lync Server 2013 行動的 DNS 需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-13_

當您部署 Lync Server 2013 行動功能功能時，您可以使用 Microsoft Lync Server 2013 自動探索服務中提供的新 Url，或者您可以使用現有的 Web 服務 Url。 如果您使用現有的 Url，使用者必須在其行動裝置設定中手動輸入 Url。 此選項通常用來進行疑難排解。 當您使用新的 Url 時，行動用戶端可以自動探索 Lync Server 2013 資源。 當您支援自動探索時，您必須新增新的網域名稱系統（DNS）記錄。 本節說明自動探索所需的 DNS 記錄。

若要支援自動探索，您需要針對每個 SIP 網域建立下列 DNS 記錄：

  - 支援從貴組織的網路中連線之行動使用者的內部 DNS 記錄

  - 外部或公用的 DNS 記錄，以支援從網際網路連線的行動使用者

內部自動探索 URL 不應該是從您的網路外部定址的。 外部自動探索 URL 不應該是您的網路中的可定址 URL。 不過，如果您無法滿足外部 URL 的這項需求，行動用戶端功能應該不會受到影響。

DNS 記錄可以是 CNAME 記錄或（主機）記錄。

**內部 DNS 記錄**

您需要建立下列其中一個內部 DNS 記錄：


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
<td><p>lyncdiscoverinternal.&lt;sipdomain&gt;</p></td>
<td><p>內部 Web 服務適用于主管池的完整功能變數名稱（FQDN）（如果有的話），如果您沒有控制器，則是適用于您的前端池</p></td>
</tr>
<tr class="even">
<td><p>A （主機）</p></td>
<td><p>lyncdiscoverinternal.&lt;sipdomain&gt;</p></td>
<td><p>如果您沒有控制器，則內部 Web 服務 IP 位址（虛擬 IP （VIP）位址是使用負載平衡器），如果您有一個或多個 [前端] 池</p></td>
</tr>
</tbody>
</table>


**外部 DNS 記錄**

您需要建立下列其中一個外部 DNS 記錄：


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
<td><p>您的控制器池的外部 Web 服務 FQDN （如果有的話），如果您沒有控制器，則是適用于您的前端池</p></td>
</tr>
<tr class="even">
<td><p>A （主機）</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>外部或公用 IP 位址（如果您使用的是負載平衡器，則為 [VIP 位址]）</p></td>
</tr>
<tr class="odd">
<td><p>DNS-SRV</p></td>
<td><p>_sipfederationtls. _tcp。 &lt;sipdomain&gt;</p>
<p>解析為存取邊緣服務的主機（A 或 AAAA）記錄</p></td>
<td><p>若要支援推播通知服務和 Apple 推播通知服務，您可以為擁有 Microsoft Lync 行動用戶端的每個 SIP 網域建立一個 SRV 記錄。</p>
<div>

> [!IMPORTANT]  
> 這個需求只適用于 Apple 或 Microsoft 的行動裝置上的 Microsoft Lync Mobile 用戶端。 Andriod 和 Nokia Symbian 裝置不使用推播通知。


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lyncdiscover （也稱為自動探索）會透過反向 proxy 進行通訊。 SRV 記錄指向透過存取邊緣服務解析的記錄。



</div>

</div>

<span> </span>

</div>

</div>

</div>

