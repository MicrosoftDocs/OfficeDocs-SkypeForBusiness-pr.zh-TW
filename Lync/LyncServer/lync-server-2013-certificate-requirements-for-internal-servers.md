---
title: Lync Server 2013：內部伺服器的憑證需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4a3f1eb54321c6cac7548d282bd3cea31c3f24a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a>Lync Server 2013 中內部伺服器的憑證需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017-02-17_

執行 Lync Server 且需要證書的內部伺服器包括標準版 Server、Enterprise Edition 前端伺服器、中繼伺服器和控制器。 下表顯示這些伺服器的憑證需求。 您可以使用 [Lync Server 憑證] 嚮導來要求這些憑證。

<div>


> [!TIP]  
> 對於與前端池、前端伺服器或控制器上的簡單 Url 相關聯的主體替換名稱，支援萬用字元憑證。 如需萬用字元憑證支援的詳細資訊，請參閱<A href="lync-server-2013-wildcard-certificate-support.md">Lync Server 2013 中的萬用字元支援</A>。



</div>

雖然建議內部伺服器使用內部企業憑證授權單位（CA），但是您也可以使用公用 CA。 若要在公用 Ca 清單中提供符合整合通訊（UC）憑證之特定需求的憑證，並與 Microsoft 合作，以確保他們能使用 Lync Server 認證嚮導，請參閱 Microsoft 知識庫929395、「Exchange Server 的整合通訊憑證合作夥伴及通訊伺服器」的文章[https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)。

與其他應用程式和伺服器通訊（例如 Exchange 2013）需要其他應用程式和產品所支援的憑證。 針對2013版本，Lync Server 2013 及其他 Microsoft Server 產品（包括 Exchange 2013 和 SharePoint Server）支援開啟授權（OAuth）通訊協定，以進行伺服器對伺服器驗證和授權。 如需詳細資訊，請參閱在部署檔或作業檔中[管理 Lync server 2013 中的伺服器到伺服器驗證（OAuth）和合作夥伴應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。

針對執行 Windows 7 作業系統、windows server 2008 作業系統、Windows Server 2008 R2 作業系統、Windows Vista 作業系統及 Microsoft Lync Phone Edition 的用戶端連線，Lync Server 2013 包含支援（但不需要）使用 SHA-256 加密雜湊函數簽署的憑證。 若要使用 SHA-256 支援外部存取，外部憑證是由使用 SHA-256 的公用 CA 所頒發。

下表顯示前端池和標準版伺服器的伺服器角色的憑證需求。 所有這些都是標準的 web 伺服器憑證、私人金鑰、無法匯出的。

請注意，當您使用 [憑證] 嚮導來要求證書時，系統會自動設定伺服器增強型金鑰用法（EKU）。

<div>


> [!NOTE]  
> 每個證書的易記名稱在電腦存放區中都必須是唯一的。



</div>

<div>


> [!NOTE]  
> 如果您已在 DNS 中設定 sipinternal.contoso.com 或 sipexternal.contoso.com，您將需要在證書的受領人備用名稱中新增它們。



</div>

### <a name="certificates-for-standard-edition-server"></a>標準版伺服器的憑證

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
<th>憑證</th>
<th>消費者名稱/通用名稱</th>
<th>消費者替換名稱</th>
<th>範例</th>
<th>批註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>設置</p></td>
<td><p>池的完整功能變數名稱（FQDN）</p></td>
<td><p>[池] 和 [伺服器的 FQDN] 的 FQDN</p>
<p>如果您有多個 SIP 網域，且已啟用自動用戶端設定，證書嚮導會偵測並新增每個支援的 SIP 網域 Fqdn。</p>
<p>如果此池是用戶端的自動登入伺服器，且在群組原則中需要嚴格的網域名稱系統（DNS）相符，您也需要 sipdomain （適用于您擁有的每個 SIP 網域）中的專案。</p></td>
<td><p>SN = se01;SAN = se01</p>
<p>如果此池是用戶端的自動登入伺服器，且在 [群組原則] 中需要嚴格的 DNS 相符，您也需要 SAN = sip. .com;SAN = sip. .com</p></td>
<td><p>在標準版伺服器上，伺服器 FQDN 與 [池 FQDN] 相同。</p>
<p>此嚮導會偵測您在安裝期間指定的任何 SIP 網域，並自動將其新增到 [使用中] 替換名稱。</p>
<p>您也可以使用此憑證進行伺服器對伺服器驗證。</p></td>
</tr>
<tr class="even">
<td><p>網頁內部</p></td>
<td><p>伺服器的 FQDN</p></td>
<td><p>下列各項：</p>
<ul>
<li><p>內部網路 FQDN （與伺服器的 FQDN 相同）</p></li>
<li><p>符合簡單的 Url</p></li>
<li><p>電話撥入式簡易 URL</p></li>
<li><p>系統管理簡易 URL</p></li>
<li><p>或者，簡單 Url 的萬用字元專案</p></li>
</ul></td>
<td><p>SN = se01;SAN = se01;SAN = 滿足 contoso. .com;SAN = 符合 fabrikam .com;SAN = 撥入. .com;SAN = admin. .com</p>
<p>使用萬用字元憑證：</p>
<p>SN = se01;SAN = se01;SAN = *. .com</p></td>
<td><p>您無法在拓撲建立器中覆寫內部網頁 FQDN。</p>
<p>如果您有多個符合簡單的 Url，您必須將它們全部包含為 subject 替換名稱。</p>
<p>簡單的 URL 專案支援萬用字元專案。</p></td>
</tr>
<tr class="odd">
<td><p>網頁外部</p></td>
<td><p>伺服器的 FQDN</p></td>
<td><p>下列各項：</p>
<ul>
<li><p>外部 web FQDN</p></li>
<li><p>電話撥入式簡易 URL</p></li>
<li><p>符合每個 SIP 網域的簡單 Url</p></li>
<li><p>或者，簡單 Url 的萬用字元專案</p></li>
</ul></td>
<td><p>SN = se01;SAN = webcon01;SAN = 滿足 contoso. .com;SAN = 符合 fabrikam .com;SAN = 撥入. .com</p>
<p>使用萬用字元憑證：</p>
<p>SN = se01;SAN = webcon01;SAN = *. .com</p></td>
<td><p>如果您有多個符合簡單的 Url，您必須將它們全部包含為 subject 替換名稱。</p>
<p>簡單的 URL 專案支援萬用字元專案。</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a>前端伺服器在前端池中的憑證

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
<th>憑證</th>
<th>消費者名稱/通用名稱</th>
<th>消費者替換名稱</th>
<th>範例</th>
<th>批註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>設置</p></td>
<td><p>池的 FQDN</p></td>
<td><p>伺服器的 [pool] 和 [FQDN]。</p>
<p>如果您有多個 SIP 網域，且已啟用自動用戶端設定，證書嚮導會偵測並新增每個支援的 SIP 網域 Fqdn。</p>
<p>如果此池是用戶端的自動登入伺服器，且在 [群組原則] 中需要嚴格的 DNS 相符，您也需要 sipdomain （針對您擁有的每個 SIP 網域）輸入的專案。</p></td>
<td><p>SN = eepool;SAN = eepool;SAN = ee01</p>
<p>如果此池是用戶端的自動登入伺服器，且在 [群組原則] 中需要嚴格的 DNS 相符，您也需要 SAN = sip. .com;SAN = sip. .com</p></td>
<td><p>此嚮導會偵測您在安裝期間指定的任何 SIP 網域，並自動將其新增到 [使用中] 替換名稱。</p>
<p>您也可以使用此憑證進行伺服器對伺服器驗證。</p></td>
</tr>
<tr class="even">
<td><p>網頁內部</p></td>
<td><p>池的 FQDN</p></td>
<td><p>下列各項：</p>
<ul>
<li><p>內部網路 FQDN （與伺服器的 FQDN 不同）</p></li>
<li><p>伺服器 FQDN</p></li>
<li><p>Lync 池 FQDN</p></li>
<li><p>符合簡單的 Url</p></li>
<li><p>電話撥入式簡易 URL</p></li>
<li><p>系統管理簡易 URL</p></li>
<li><p>或者，簡單 Url 的萬用字元專案</p></li>
</ul></td>
<td><p>SN = ee01;SAN = ee01;SAN = 滿足 contoso. .com;SAN = 符合 fabrikam .com;SAN = 撥入. .com;SAN = admin. .com</p>
<p>使用萬用字元憑證：</p>
<p>SN = ee01;SAN = ee01;SAN = *. .com</p></td>
<td><p>如果您有多個符合簡單的 Url，您必須將它們全部包含為 subject 替換名稱。</p>
<p>簡單的 URL 專案支援萬用字元專案。</p></td>
</tr>
<tr class="odd">
<td><p>網頁外部</p></td>
<td><p>池的 FQDN</p></td>
<td><p>下列各項：</p>
<ul>
<li><p>外部 web FQDN</p></li>
<li><p>電話撥入式簡易 URL</p></li>
<li><p>系統管理簡易 URL</p></li>
<li><p>或者，簡單 Url 的萬用字元專案</p></li>
</ul></td>
<td><p>SN = ee01;SAN = webcon01;SAN = 滿足 contoso. .com;SAN = 符合 fabrikam .com;SAN = 撥入. .com</p>
<p>使用萬用字元憑證：</p>
<p>SN = ee01;SAN = webcon01;SAN = *. .com</p></td>
<td><p>如果您有多個符合簡單的 Url，您必須將它們全部包含為 subject 替換名稱。</p>
<p>簡單的 URL 專案支援萬用字元專案。</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a>主管的憑證

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>憑證</th>
<th>消費者名稱/通用名稱</th>
<th>消費者替換名稱</th>
<th>範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>設置</p></td>
<td><p>主管池的 FQDN</p></td>
<td><p>主管的 FQDN，控制器池的 FQDN</p>
<p>如果此池是用戶端的自動登入伺服器，且在 [群組原則] 中需要嚴格的 DNS 相符，您也需要 sipdomain （針對您擁有的每個 SIP 網域）輸入的專案。</p></td>
<td><p>SN = dir-pool.contoso.com;SAN = dir-pool.contoso.com;SAN = dir01</p>
<p>如果此主管池是用戶端的自動登入伺服器，且在 [群組原則] 中需要嚴格的 DNS 相符，您也需要 SAN = sip. .com;SAN = sip. .com</p></td>
</tr>
<tr class="even">
<td><p>網頁內部</p></td>
<td><p>伺服器的 FQDN</p></td>
<td><p>下列各項：</p>
<ul>
<li><p>內部網路 FQDN （與伺服器的 FQDN 相同）</p></li>
<li><p>伺服器 FQDN</p></li>
<li><p>Lync 池 FQDN</p></li>
<li><p>符合簡單的 Url</p></li>
<li><p>電話撥入式簡易 URL</p></li>
<li><p>系統管理簡易 URL</p></li>
<li><p>或者，簡單 Url 的萬用字元專案</p></li>
</ul></td>
<td><p>SN = dir01;SAN = dir01;SAN = 滿足 contoso. .com;SAN = 符合 fabrikam .com;SAN = 撥入. .com;SAN = admin. .com</p>
<p>SN = dir01;SAN = dir01 （contoso. .com） SAN = * .com</p></td>
</tr>
<tr class="odd">
<td><p>網頁外部</p></td>
<td><p>伺服器的 FQDN</p></td>
<td><p>下列各項：</p>
<ul>
<li><p>外部 web FQDN</p></li>
<li><p>電話撥入式簡易 URL</p></li>
<li><p>系統管理簡易 URL</p></li>
<li><p>或者，簡單 Url 的萬用字元專案</p></li>
</ul></td>
<td><p>控制器外部 web FQDN 必須與前端池或前端伺服器不同。</p>
<p>SN = dir01;SAN = directorwebcon01 （contoso .com） SAN = 符合 contoso;SAN = 符合 fabrikam .com;SAN = 撥入. .com</p>
<p>SN = dir01;SAN = directorwebcon01 （contoso. .com） SAN = * .com</p></td>
</tr>
</tbody>
</table>


如果您擁有獨立的中繼伺服器池，則每個中繼伺服器都需要下表所列的憑證。 如果您 collocate 的是前端伺服器的中繼伺服器，在本主題先前的 [前端伺服器中的前端伺服器證書] 表格中所列的憑證就足夠了。

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
<th>憑證</th>
<th>消費者名稱/通用名稱</th>
<th>消費者替換名稱</th>
<th>範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>設置</p></td>
<td><p>池的 FQDN</p></td>
<td><p>池的 FQDN</p>
<p>Pool 成員伺服器的 FQDN</p></td>
<td><p>SN = medsvr-pool.contoso.net;SAN = medsvr-pool.contoso.net;SAN = medsvr01</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a>Survivable 分支裝置的憑證

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>憑證</th>
<th>消費者名稱/通用名稱</th>
<th>消費者替換名稱</th>
<th>範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>設置</p></td>
<td><p>裝置的 FQDN</p></td>
<td><p>呼吸.&lt;sipdomain&gt; （每個 SIP 網域需要一個專案）</p></td>
<td><p>SN = sba01;SAN = sip. .com;SAN = sip. .com</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的萬用字元憑證支援](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

