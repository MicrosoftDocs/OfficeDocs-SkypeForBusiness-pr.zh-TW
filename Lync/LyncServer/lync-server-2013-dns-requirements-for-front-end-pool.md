---
title: Lync Server 2013： 的前端集區的 DNS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0ace2b05b506b5bbf73177282747a66d212b38f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a>Lync Server 2013 中的前端集區的 DNS 需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-07_

若要順利完成此程序，您至少應該以 Domain Admins 群組成員或 DnsAdmins 群組成員的身分登入伺服器或網域。

您要設定在拓撲產生器中發行拓撲之前所需的網域名稱系統 (DNS) 記錄。 此外，Lync Server 2013 部署的組態中使用完整的網域名稱 (Fqdn) 部分是邏輯並不是實體伺服器 Fqdn] 中，因此額外的 DNS 設定已發佈前需先。

<div>


> [!WARNING]  
> Lync Server 2013 不支援單一標示的網域。 例如，根網域名稱為 <STRONG>contoso.local</STRONG> 的樹系是受支援的，名為 <STRONG>local</STRONG> 的根網域則不受支援。 如需詳細資訊，請參閱 Microsoft 知識庫文章 300684，「 具有單一標籤 DNS 名稱的網域設定 Windows 的相關資訊 」 <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp; 3052&kbid = 300684</A>。



</div>

<div>


> [!IMPORTANT]  
> 您指定的名稱必須與伺服器上設定的電腦名稱一模一樣。 根據預設，未加入網域的電腦，其電腦名稱是簡稱，而不是 FQDN。 拓撲產生器會使用 Fqdn，不短檔名。 <STRONG>使用唯一標準字元</STRONG>（包括 A – Z、 a – z、 0 – 9、 連字號） 分派執行 Lync Server、 Edge Server 以及集區的伺服器的 Fqdn 時。 請勿使用 Unicode 字元或底線。 當 FQDN 必須指派給憑證的 SN 時，外部 DNS 與公用憑證授權單位 (CA) 通常不支援在 FQDN 中使用非標準字元。



</div>

之前之後已部署作業系統拓樸，確保下列 Active Directory 和 DNS 記錄所建立 （做為您的特定功能規定需求）：

  - 將存在於拓撲中每個伺服器角色發佈為 Active Directory 物件 （將電腦加入至網域將會完成這項作業）。

  - 每個伺服器都存在 DNS A 記錄。

  - DNS SRV 記錄存在，每個 SIP 網域如果您打算使用的表單中的用戶端自動登入\_sipinternaltls\_tcp。\<SIP 網域\>。 如果您將對用戶端使用手動設定，則不需要此記錄。

  - 每個已設定簡單 URL 的 DNS A 記錄通常有四種：meet、dialin、lwa 及 scheduler。 此外，沒有這是特殊的 URL 來存取 Lync Server 2013 控制台 admin 簡單 URL。

  - 發行拓撲產生器的電腦必須加入至網域，並且可以存取執行 SQL Server 的伺服器。

下表追蹤規劃章節中呈現的參考架構。 如需詳細資訊，請參閱規劃文件中的[Lync Server 2013 中的外部使用者存取的案例](lync-server-2013-scenarios-for-external-user-access.md)。

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a>前端集區所需的 DNS 記錄

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
<th>Type</th>
<th>FQDN</th>
<th>對應至/註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>內部 DNS</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (DNS 負載平衡)。 需要每部前端伺服器集區，在對應至集區 FQDN 的 IP 位址的 DNS A 記錄。</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS</p></td>
<td><p>A</p></td>
<td><p>pool01.contoso.net</p></td>
<td><p>Pool01 (硬體負載平衡器的虛擬 IP (VIP))。</p></td>
</tr>
<tr class="odd">
<td><p>內部 DNS</p></td>
<td><p>A</p></td>
<td><p>fe01.contoso.net</p>
<p>fe02.contoso.net</p>
<p>fe03.contoso.net</p>
<p>…</p></td>
<td><p>Pool01 前端伺服器 （節點 1）。</p>
<p>Pool01 前端伺服器 （節點 2）。</p>
<p>Pool01 前端伺服器 （節點 3）。</p>
<p>…</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS</p></td>
<td><p>A</p></td>
<td><p>fe02.contoso.net</p></td>
<td><p>Pool01 前端伺服器 （節點 2）。</p></td>
</tr>
<tr class="odd">
<td><p>內部 DNS</p></td>
<td><p>A</p></td>
<td><p>lsweb.contoso.net</p></td>
<td><p>用戶端到伺服器 Web 流量的 Pool01 (VIP)。</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS</p></td>
<td><p>A</p></td>
<td><p>sqlbe.contoso.net</p></td>
<td><p>Pool01 後端伺服器執行 SQL Server 2008 R2。</p></td>
</tr>
<tr class="odd">
<td><p>內部 DNS</p></td>
<td><p>A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>所需的 Lync Phone Edition，或是沒有 DNS SRV 記錄，用戶端的自動登入，以及嚴格網域相符。 並非所有情況下都需要此種記錄。</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS</p></td>
<td><p>A</p></td>
<td><p>sip.fabrikam.com</p></td>
<td><p>假設第二個 SIP 網域。 Lync Phone Edition，沒有 DNS SRV 記錄，用戶端的自動登入及嚴格網域比對所需。 並非所有情況下都需要此種記錄。</p></td>
</tr>
<tr class="odd">
<td><p>內部 DNS</p></td>
<td><p>A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>內部發行電話撥入式會議的簡單 URL-前端伺服器 （或 Director，如果安裝） 回應簡單 URL 查詢。</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS</p></td>
<td><p>A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>內部發行會議的簡單 URL-前端伺服器 （或 Director，如果安裝） 回應簡單 URL 查詢。</p></td>
</tr>
<tr class="odd">
<td><p>內部 DNS</p></td>
<td><p>A</p></td>
<td><p>admin.contoso.com</p>
<p>系統管理員</p></td>
<td><p>選用的記錄，Lync Server 2013 控制台的內部發行簡單 URL-前端伺服器 （或 Director，如果安裝） 回應簡單 URL 查詢。 建議僅使用主機名稱 (沒有網域名稱)。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> VIP = 硬體負載平衡器的虛擬 IP 位址



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a>前端集區的 DNS SRV 記錄


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
<th>Type</th>
<th>FQDN</th>
<th>目標 FQDN</th>
<th>連接埠</th>
<th>對應至/註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>內部 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls._tcp.contoso.com</p></td>
<td><p>pool01.contoso.com</p></td>
<td><p>5061</p></td>
<td><p>所需的 Lync 2013 用戶端的自動設定內部運作。</p></td>
</tr>
<tr class="even">
<td><p>內部 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_sipinternaltls._tcp.fabrikam.com</p></td>
<td><p>pool01.fabrikam.com</p></td>
<td><p>5061</p></td>
<td><p>所需的 Lync 2013 用戶端的自動設定內部運作。</p></td>
</tr>
<tr class="odd">
<td><p>內部 DNS</p></td>
<td><p>SRV</p></td>
<td><p>_ntp._udp.contoso.com</p></td>
<td><p>dc01.contoso.com</p></td>
<td><p>123</p></td>
<td><p>執行 Lync Phone Edition 裝置所需的網路時間通訊協定 (NTP) 來源。 在內部，此記錄應指向網域控制站。 如果未定義網域控制站，則會嘗試使用 NTP 伺服器 time.windows.com。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

