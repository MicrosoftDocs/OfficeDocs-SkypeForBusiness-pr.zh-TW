---
title: Lync Server 2013：內部伺服器的憑證需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c56554a26e5f64089a766300f375039409680578
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526240"
---
# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a>Lync Server 2013 中內部伺服器的憑證需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017-02-17_

執行 Lync Server 且需要憑證的內部伺服器包括 Standard Edition Server、Enterprise Edition 前端伺服器、轉送伺服器及 Director。 下表顯示這些伺服器的憑證需求。 您可以使用 Lync Server 憑證嚮導來要求這些憑證。

<div>


> [!TIP]  
> 針對與前端集區、前端伺服器或 Director 上的簡易 URLs 相關聯的主體替代名稱，支援通配憑證。 如需有關萬用字元憑證支援的詳細資訊，請參閱 <A href="lync-server-2013-wildcard-certificate-support.md">Lync Server 2013 中的通配憑證支援</A>。



</div>

雖然建議內部伺服器使用內部企業憑證授權單位 (CA)，但您也可以使用公用 CA。 如需提供符合整合通訊特定需求之憑證的公用 Ca 清單 (UC) 憑證，並與 Microsoft 合作，以確保其與 Lync Server 憑證嚮導搭配運作，請參閱 Microsoft 知識庫929395：「Exchange Server 和通訊伺服器的整合通訊憑證合作夥伴」; at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) 。

與其他應用程式和伺服器進行通訊，例如 Exchange 2013，需要另一個應用程式和產品所支援的憑證。 針對2013版本，Lync Server 2013 和其他 Microsoft server 產品（包括 Exchange 2013 和 SharePoint 伺服器）都支援「開放授權」 (OAuth 伺服器對伺服器驗證和授權的) 通訊協定。 如需詳細資訊，請參閱部署檔或作業檔中的 [管理 Lync server 2013 中的伺服器對伺服器驗證 (OAuth) 和夥伴應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 。

針對來自執行 Windows 7 作業系統、windows server 2008 作業系統、Windows Server 2008 R2 作業系統、windows Vista 作業系統及 Microsoft Lync Phone Edition 之用戶端的連線，Lync Server 2013 包含對 (的支援，但不需要使用 SHA-256 加密雜湊函數簽署) 憑證。 為了支援使用 SHA-256 的外部存取，外部憑證由公用 CA 使用 SHA-256 發行。

下表依伺服器角色顯示前端集區和 Standard Edition Server 的憑證需求。這些全部都是不可匯出的標準 Web 伺服器憑證、私密金鑰。

請注意，當您使用憑證精靈要求憑證時，會自動設定伺服器增強金鑰使用方法 (EKU)。

<div>


> [!NOTE]  
> 每個憑證好記的名稱在電腦存放區中必須是唯一的。



</div>

<div>


> [!NOTE]  
> 如果您已在 DNS 中設定 sipinternal.contoso.com 或 sipexternal.contoso.com，您必須將其新增至憑證的主體替代名稱。



</div>

### <a name="certificates-for-standard-edition-server"></a>Standard Edition Server 的憑證

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
<th>認證</th>
<th>主體名稱/一般名稱</th>
<th>主體替代名稱</th>
<th>範例</th>
<th>註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>預設</p></td>
<td><p>集區的完整網域名稱 (FQDN)</p></td>
<td><p>集區的 FQDN 和伺服器的 FQDN</p>
<p>如果您擁有多個 SIP 網域，且已啟用用戶端自動設定，則憑證精靈會偵測並新增每個支援的 SIP 網域 FQDN</p>
<p>如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格網域名稱系統 (DNS) 比對，則您也需要 sip.sipdomain (對於您具有的每個 SIP 網域) 的項目。</p></td>
<td><p>SN = se01，SAN = se01</p>
<p>如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 SAN=sip.contoso.com；SAN=sip.fabrikam.com</p></td>
<td><p>在 Standard Edition Server，伺服器 FQDN 與集區 FQDN 相同。</p>
<p>精靈會偵測任何您在安裝期間指定的 SIP 網域，並將之自動新增到主體別名。</p>
<p>您也可以使用此憑證進行 Server-to-Server 驗證。</p></td>
</tr>
<tr class="even">
<td><p>Web 內部</p></td>
<td><p>伺服器的 FQDN</p></td>
<td><p>下列每一項：</p>
<ul>
<li><p>內部 Web FQDN (與伺服器的 FQDN 相同)</p></li>
<li><p>Meet 簡單 URL</p></li>
<li><p>Dial-in 簡單 URL</p></li>
<li><p>Admin 簡單 URL</p></li>
<li><p>或者，簡單 URL 的萬用字元項目</p></li>
</ul></td>
<td><p>SN = se01，SAN = se01;SAN = 符合 .com;SAN = 符合 fabrikam .com;SAN = 撥入 .com;SAN = contoso .com</p>
<p>使用萬用字元憑證：</p>
<p>SN = se01，SAN = se01;SAN = * .com</p></td>
<td><p>您無法在拓撲產生器中覆寫內部 web FQDN。</p>
<p>若有多個 Meet 簡單 URL，則必須包含這些 URL 做為主體別名。</p>
<p>簡單 URL 項目支援萬用字元項目。</p></td>
</tr>
<tr class="odd">
<td><p>Web 外部</p></td>
<td><p>伺服器的 FQDN</p></td>
<td><p>下列每一項：</p>
<ul>
<li><p>外部 Web FQDN</p></li>
<li><p>Dial-in 簡單 URL</p></li>
<li><p>符合每個 SIP 網域的簡易 URLs</p></li>
<li><p>或者，簡單 URL 的萬用字元項目</p></li>
</ul></td>
<td><p>SN = se01，SAN = webcon01;SAN = 符合 .com;SAN = 符合 fabrikam .com;SAN = 撥入 .com</p>
<p>使用萬用字元憑證：</p>
<p>SN = se01，SAN = webcon01;SAN = * .com</p></td>
<td><p>若有多個 Meet 簡單 URL，則必須包含這些 URL 做為主體別名。</p>
<p>簡單 URL 項目支援萬用字元項目。</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a>前端集區中前端伺服器的憑證

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
<th>認證</th>
<th>主體名稱/一般名稱</th>
<th>主體替代名稱</th>
<th>範例</th>
<th>註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>預設</p></td>
<td><p>集區的 FQDN</p></td>
<td><p>集區的 FQDN 和伺服器的 FQDN。</p>
<p>如果您擁有多個 SIP 網域，且已啟用用戶端自動設定，則憑證精靈會偵測並新增每個支援的 SIP 網域 FQDN</p>
<p>如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 sip.sipdomain (對於您具有的每個 SIP 網域) 的項目。</p></td>
<td><p>SN = eepool，SAN = eepool;SAN = ee01</p>
<p>如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 SAN=sip.contoso.com；SAN=sip.fabrikam.com</p></td>
<td><p>精靈會偵測任何您在安裝期間指定的 SIP 網域，並將之自動新增到主體別名。</p>
<p>您也可以使用此憑證進行 Server-to-Server 驗證。</p></td>
</tr>
<tr class="even">
<td><p>Web 內部</p></td>
<td><p>集區的 FQDN</p></td>
<td><p>下列每一項：</p>
<ul>
<li><p>內部 web FQDN (，其與伺服器的 FQDN 不同) </p></li>
<li><p>伺服器 FQDN</p></li>
<li><p>Lync 集區 FQDN</p></li>
<li><p>Meet 簡單 URL</p></li>
<li><p>Dial-in 簡單 URL</p></li>
<li><p>Admin 簡單 URL</p></li>
<li><p>或者，簡單 URL 的萬用字元項目</p></li>
</ul></td>
<td><p>SN = ee01，SAN = ee01;SAN = 符合 .com;SAN = 符合 fabrikam .com;SAN = 撥入 .com;SAN = contoso .com</p>
<p>使用萬用字元憑證：</p>
<p>SN = ee01，SAN = ee01;SAN = * .com</p></td>
<td><p>若有多個 Meet 簡單 URL，則必須包含這些 URL 做為主體別名。</p>
<p>簡單 URL 項目支援萬用字元項目。</p></td>
</tr>
<tr class="odd">
<td><p>Web 外部</p></td>
<td><p>集區的 FQDN</p></td>
<td><p>下列每一項：</p>
<ul>
<li><p>外部 Web FQDN</p></li>
<li><p>Dial-in 簡單 URL</p></li>
<li><p>Admin 簡單 URL</p></li>
<li><p>或者，簡單 URL 的萬用字元項目</p></li>
</ul></td>
<td><p>SN = ee01，SAN = webcon01;SAN = 符合 .com;SAN = 符合 fabrikam .com;SAN = 撥入 .com</p>
<p>使用萬用字元憑證：</p>
<p>SN = ee01，SAN = webcon01;SAN = * .com</p></td>
<td><p>若有多個 Meet 簡單 URL，則必須包含這些 URL 做為主體別名。</p>
<p>簡單 URL 項目支援萬用字元項目。</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a>Director 的憑證

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>認證</th>
<th>主體名稱/一般名稱</th>
<th>主體替代名稱</th>
<th>範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>預設</p></td>
<td><p>Director 集區的 FQDN</p></td>
<td><p>Director 的 FQDN，Director 集區的 FQDN</p>
<p>如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 sip.sipdomain (對於您具有的每個 SIP 網域) 的項目。</p></td>
<td><p>SN = dir-pool.contoso.com;SAN = pool.contoso.com;SAN = dir01</p>
<p>如果此 Director 集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 SAN=sip.contoso.com；SAN=sip.fabrikam.com</p></td>
</tr>
<tr class="even">
<td><p>Web 內部</p></td>
<td><p>伺服器的 FQDN</p></td>
<td><p>下列每一項：</p>
<ul>
<li><p>內部 Web FQDN (與伺服器的 FQDN 相同)</p></li>
<li><p>伺服器 FQDN</p></li>
<li><p>Lync 集區 FQDN</p></li>
<li><p>Meet 簡單 URL</p></li>
<li><p>Dial-in 簡單 URL</p></li>
<li><p>Admin 簡單 URL</p></li>
<li><p>或者，簡單 URL 的萬用字元項目</p></li>
</ul></td>
<td><p>SN = dir01，SAN = dir01;SAN = 符合 .com;SAN = 符合 fabrikam .com;SAN = 撥入 .com;SAN = contoso .com</p>
<p>SN = dir01，SAN = dir01-.com SAN = * .com</p></td>
</tr>
<tr class="odd">
<td><p>Web 外部</p></td>
<td><p>伺服器的 FQDN</p></td>
<td><p>下列每一項：</p>
<ul>
<li><p>外部 Web FQDN</p></li>
<li><p>Dial-in 簡單 URL</p></li>
<li><p>Admin 簡單 URL</p></li>
<li><p>或者，簡單 URL 的萬用字元項目</p></li>
</ul></td>
<td><p>Director 外部 web FQDN 必須不同于前端集區或前端伺服器。</p>
<p>SN = dir01，SAN = directorwebcon01 SAN = "contoso .com"，SAN = 符合 fabrikam .com;SAN = 撥入 .com</p>
<p>SN = dir01，SAN = directorwebcon01-.com SAN = * .com</p></td>
</tr>
</tbody>
</table>


如果您具有獨立中繼伺服器集區，則該集區中的每個中繼伺服器都需要下表所列的憑證。如果您將中繼伺服器與前端伺服器組合在一起，則本主題中前面的「前端集區中前端伺服器的憑證」表格中所列的憑證已足夠。

### <a name="certificates-for-stand-alone-mediation-server"></a>獨立中繼伺服器的憑證

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>認證</th>
<th>主體名稱/一般名稱</th>
<th>主體替代名稱</th>
<th>範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>預設</p></td>
<td><p>集區的 FQDN</p></td>
<td><p>集區的 FQDN</p>
<p>集區成員伺服器的 FQDN</p></td>
<td><p>SN = medsvr-pool.contoso.net;SAN = medsvr-pool.contoso.net;SAN = medsvr01</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a>Survivable Branch Appliance 的憑證

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>認證</th>
<th>主體名稱/一般名稱</th>
<th>主體替代名稱</th>
<th>範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>預設</p></td>
<td><p>Appliance 的 FQDN</p></td>
<td><p>SIP。 &lt;microsoft.rtc.management.xds.sipdomain &gt; (每個 SIP 網域需要一個專案) </p></td>
<td><p>SN = sba01SAN = sip .com;SAN=sip.fabrikam.com</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的萬用字元憑證支援](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

