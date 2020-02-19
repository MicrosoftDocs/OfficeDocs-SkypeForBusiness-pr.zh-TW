---
title: Lync Server 2013： 適用於內部伺服器的憑證需求
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
ms.openlocfilehash: a3f9e8f029b4c621d15c17c5af5f7eac3207b832
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a>適用於 Lync Server 2013 中的內部伺服器的憑證需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017年-02-17_

內部伺服器，執行 Lync Server 且需要憑證包含 Standard Edition server、 Enterprise Edition 前端伺服器、 中繼伺服器和 Director。 下表顯示這些伺服器的憑證需求。 您可以使用 [Lync 伺服器憑證] 精靈，以要求這些憑證。

<div>


> [!TIP]  
> 在前端集區、 前端伺服器或 Director 的簡單 Url 相關聯的主體替代名稱支援萬用字元憑證。 如需詳細資訊萬用字元憑證支援，請參閱<A href="lync-server-2013-wildcard-certificate-support.md">Lync Server 2013 中支援的萬用字元憑證</A>。



</div>

雖然建議內部伺服器使用內部企業憑證授權單位 (CA)，但您也可以使用公用 CA。 如需在提供符合特定需求的憑證整合通訊 (UC) 憑證，並已建立合作關係與 Microsoft，以確保可搭配 [Lync 伺服器憑證] 精靈中，請參閱文章 Microsoft 知識庫件 929395 「 整合通訊憑證合作夥伴的 Exchange Server 和 Communications Server，」 的公用 Ca 的清單[https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)。

與其他應用程式和伺服器，例如 Exchange 2013 通訊需要受到其他應用程式和產品的憑證。 2013 版本，Lync Server 2013 與其他 Microsoft server 產品，包括 Exchange 2013 和 SharePoint Server 支援伺服器對伺服器驗證及授權的 Open Authorization (OAuth) 通訊協定。 如需詳細資訊，請參閱部署文件或作業文件中的[管理伺服器對伺服器驗證 (OAuth) 與 Lync Server 2013 中的協力廠商應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。

從執行 Windows 7 作業系統、 Windows Server 2008 作業系統、 Windows Server 2008 R2 作業系統、 Windows Vista 作業系統和 Microsoft Lync Phone Edition 的用戶端連線，Lync Server 2013 包含支援 （但不會需要） 使用 sha-256 密碼編譯雜湊函數簽署的憑證。 為了支援使用 SHA-256 的外部存取，外部憑證由公用 CA 使用 SHA-256 發行。

下表依伺服器角色顯示前端集區和 Standard Edition Server 的憑證需求。這些全部都是不可匯出的標準 Web 伺服器憑證、私密金鑰。

請注意，當您使用憑證精靈要求憑證時，會自動設定伺服器增強金鑰使用方法 (EKU)。

<div>


> [!NOTE]  
> 電腦存放區中，每個憑證好記的名稱必須是唯一的。



</div>

<div>


> [!NOTE]  
> 如果您已設定 sipinternal.contoso.com 或 sipexternal.contoso.com DNS 中，您必須將它們新增中憑證的 Subject Alternative Name。



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
<th>主體名稱 / 一般名稱</th>
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
<td><p>SN=se01.contoso.com;SAN=se01.contoso.com</p>
<p>如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 SAN=sip.contoso.com；SAN=sip.fabrikam.com</p></td>
<td><p>在 Standard Edition Server，伺服器 FQDN 與集區 FQDN 相同。</p>
<p>精靈會偵測任何您在安裝期間指定的 SIP 網域，並將之自動新增到主體別名。</p>
<p>您也可以使用此憑證的伺服器對伺服器驗證。</p></td>
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
<td><p>SN=se01.contoso.com;SAN=se01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com</p>
<p>使用萬用字元憑證：</p>
<p>SN=se01.contoso.com;SAN=se01.contoso.com;SAN = *.contoso.com</p></td>
<td><p>您不能覆寫內部 web FQDN 在拓撲產生器。</p>
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
<li><p>每個 SIP 網域的 meet 簡單 Url</p></li>
<li><p>或是簡單 URL 的萬用字元項目</p></li>
</ul></td>
<td><p>SN=se01.contoso.com;SAN=webcon01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com</p>
<p>使用萬用字元憑證：</p>
<p>SN=se01.contoso.com;SAN=webcon01.contoso.com;SAN = *.contoso.com</p></td>
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
<th>主體名稱 / 一般名稱</th>
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
<td><p>SN=eepool.contoso.com;SAN=eepool.contoso.com;SAN=ee01.contoso.com</p>
<p>如果此集區是用戶端的自動登入伺服器且群組原則中需要嚴格 DNS 比對，則您也需要 SAN=sip.contoso.com；SAN=sip.fabrikam.com</p></td>
<td><p>精靈會偵測任何您在安裝期間指定的 SIP 網域，並將之自動新增到主體別名。</p>
<p>您也可以使用此憑證的伺服器對伺服器驗證。</p></td>
</tr>
<tr class="even">
<td><p>Web 內部</p></td>
<td><p>集區的 FQDN</p></td>
<td><p>下列每一項：</p>
<ul>
<li><p>內部 web FQDN （也就是不之伺服器的 FQDN 相同）</p></li>
<li><p>伺服器 FQDN</p></li>
<li><p>Lync 集區 FQDN</p></li>
<li><p>Meet 簡單 URL</p></li>
<li><p>Dial-in 簡單 URL</p></li>
<li><p>Admin 簡單 URL</p></li>
<li><p>或者，簡單 URL 的萬用字元項目</p></li>
</ul></td>
<td><p>SN=ee01.contoso.com;SAN=ee01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com</p>
<p>使用萬用字元憑證：</p>
<p>SN=ee01.contoso.com;SAN=ee01.contoso.com;SAN = *.contoso.com</p></td>
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
<td><p>SN=ee01.contoso.com;SAN=webcon01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com</p>
<p>使用萬用字元憑證：</p>
<p>SN=ee01.contoso.com;SAN=webcon01.contoso.com;SAN = *.contoso.com</p></td>
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
<th>主體名稱 / 一般名稱</th>
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
<td><p>SN = dir pool.contoso.com;SAN = dir pool.contoso.com;SAN=dir01.contoso.com</p>
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
<td><p>SN=dir01.contoso.com;SAN=dir01.contoso.com;SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com;SAN=admin.contoso.com</p>
<p>SN=dir01.contoso.com;SAN=dir01.contoso.com SAN = *.contoso.com</p></td>
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
<td><p>Director 外部 web FQDN 必須與前端集區或前端伺服器不同。</p>
<p>SN=dir01.contoso.com;SAN=directorwebcon01.contoso.com SAN=meet.contoso.com;SAN=meet.fabrikam.com;SAN=dialin.contoso.com</p>
<p>SN=dir01.contoso.com;SAN=directorwebcon01.contoso.com SAN = *.contoso.com</p></td>
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
<th>主體名稱 / 一般名稱</th>
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
<td><p>SN = medsvr pool.contoso.net;SAN = medsvr pool.contoso.net;SAN=medsvr01.contoso.net</p></td>
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
<th>主體名稱 / 一般名稱</th>
<th>主體替代名稱</th>
<th>範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>預設</p></td>
<td><p>Appliance 的 FQDN</p></td>
<td><p>SIP。&lt;sipdomain&gt; （需要每個 SIP 網域的一個項目）</p></td>
<td><p>SN=sba01.contoso.net;Sip.contoso.com;San = sip.fabrikam.com</p></td>
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

