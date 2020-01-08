---
title: Lync Server 2013：前端集區的 DNS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c033d8f1a4167e423d5663b0c9b0b7dbfb2d760
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a>Lync Server 2013 中前端集區的 DNS 需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-07_

若要成功完成此程式，您必須以網域管理員群組或 DnsAdmins 群組成員的身分登入伺服器或網域。

您必須先設定必要的網域名稱系統（DNS）記錄，才能在拓撲建立程式中發佈拓撲。 此外，Lync Server 2013 部署的設定中所用的一些完整功能變數名稱（Fqdn）是邏輯和非物理伺服器 Fqdn，因此在發佈之前，必須先進行額外的 DNS 設定。

<div>


> [!WARNING]  
> Lync Server 2013 不支援單一標示的網域。 例如，支援名為<STRONG>contoso. local</STRONG>的根網域的林，但不支援名為<STRONG>local</STRONG>的根網域。 如需詳細資訊，請參閱 Microsoft 知識庫文章300684：「使用單標籤 DNS 名稱設定 Windows 網域的相關資訊，"at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 300684</A>。



</div>

<div>


> [!IMPORTANT]  
> 您指定的名稱必須與伺服器上設定的電腦名稱相同。 根據預設，未加入網域之電腦的電腦名稱稱是簡稱，不是 FQDN。 拓撲產生器會使用 FQDN，而非簡稱。 在指派執行 Lync Server、Edge 伺服器和池的伺服器 Fqdn 時，<STRONG>只使用標準字元</STRONG>（包括 a-z、A 至 z、0–9和連字號）。 請勿使用 Unicode 字元或底線。 外部 DNS 和公用憑證授權單位（Ca）通常不支援 FQDN 中的非標準字元（當 FQDN 必須指派給憑證中的 SN 時）。



</div>

在部署之後，在執行拓撲之後，請確定已建立下列 Active Directory 和 DNS 記錄（如您對特定功能的需求）：

  - 將存在於拓撲中的每個伺服器角色，都會發佈為 Active Directory 物件（將電腦加入網域即可完成此作業）。

  - 每個伺服器都有一個 DNS A 記錄。

  - 如果您打算針對\_sipinternaltls\_tcp 形式的用戶端使用自動登入，則每個 SIP 網域都存在 DNS SRV 記錄。\<SIP 網域\>。 如果您將使用手動設定用戶端，則不需要此記錄。

  - 針對每個已設定的簡單 URL 的 DNS A 記錄，其中通常有四個： [開會]、[撥入]、[lwa] 和 [排程]。 此外，系統管理員簡單的 URL 是使用 Lync Server 2013 [控制台] 的特殊 URL。

  - 運行 SQL Server 的伺服器必須加入網域，並可由拓撲建立程式發佈的電腦來使用。

下表會遵循 [規劃] 區段中所提供的參考體系結構。 如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)。

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a>前端池所需的 DNS 記錄

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>位置</th>
<th>類型</th>
<th>稱</th>
<th>地圖/批註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>內部 DNS</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 （DNS 負載平衡）。 需要一個 DNS A 記錄，以取得池中每個前端伺服器的 IP 位址，並對應到 [池 FQDN]。</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 （硬體負載平衡器的虛擬 IP （VIP））。</p></td>
</tr>
<tr class="odd">
<td><p>內部 DNS</p></td>
<td><p>A</p></td>
<td><p>fe01.contoso.net</p>
<p>fe02.contoso.net</p>
<p>fe03.contoso.net</p>
<p>…</p></td>
<td><p>Pool01 前端伺服器（節點1）。</p>
<p>Pool01 前端伺服器（節點2）。</p>
<p>Pool01 前端伺服器（節點3）。</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS</p></td>
<td><p>A</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>Pool01 前端伺服器（節點2）。</p></td>
</tr>
<tr class="odd">
<td><p>內部 DNS</p></td>
<td><p>A</p></td>
<td><p>lsweb.contoso.net</p></td>
<td><p>用戶端到伺服器網站流量的 Pool01 （VIP）。</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS</p></td>
<td><p>A</p></td>
<td><p>sqlbe.contoso.net</p></td>
<td><p>Pool01 運行 SQL Server 2008 R2 的後端伺服器。</p></td>
</tr>
<tr class="odd">
<td><p>內部 DNS</p></td>
<td><p>A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>對於 Lync Phone Edition 是必要的，或自動登入不含 DNS SRV 記錄的用戶端，以及嚴格的網域相符。 在任何情況下都不需要。</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>假設第二個 SIP 網域。 Lync Phone Edition 所需、自動登入不含 DNS SRV 記錄的用戶端，以及嚴格的網域相符。 在任何情況下都不需要。</p></td>
</tr>
<tr class="odd">
<td><p>內部 DNS</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>在內部發佈的電話撥入式會議（如果已安裝，則為 Director）回應簡單的 URL 查詢的簡單 URL。</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>在內部發佈的會議的簡單 URL-前端伺服器（或已安裝的控制器）會回應簡單的 URL 查詢。</p></td>
</tr>
<tr class="odd">
<td><p>內部 DNS</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>管理員</p></td>
<td><p>選擇性記錄、Lync Server 2013 [控制台] 的簡單 URL （如果已安裝，則為 [控制器]）回應簡單的 URL 查詢。 建議僅限主機名稱（無功能變數名稱）。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> VIP = 硬體載入平衡器的虛擬 IP 位址



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a>前端池的 DNS SRV 記錄


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>位置</th>
<th>類型</th>
<th>稱</th>
<th>目標 FQDN</th>
<th>通道</th>
<th>地圖/批註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>內部 DNS</p></td>
<td><p>DNS-SRV</p></td>
<td><p>_sipinternaltls. _tcp. .com</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>自動將 Lync 2013 用戶端設定為內部工作所需。</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS</p></td>
<td><p>DNS-SRV</p></td>
<td><p>_sipinternaltls _tcp .com</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>自動將 Lync 2013 用戶端設定為內部工作所需。</p></td>
</tr>
<tr class="odd">
<td><p>內部 DNS</p></td>
<td><p>DNS-SRV</p></td>
<td><p>_ntp. _udp. .com</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>運行 Lync Phone Edition 之裝置所需的網路時間協定（NTP）來源。 在內部，這應該指向網網域控制站。 如果未定義網網域控制站，則會嘗試使用 NTP 伺服器 time.windows.com。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

