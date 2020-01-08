---
title: 整合內部部署整合訊息的部署程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7147a83bad1ed8b5cacc369d8d64e71fcaac32b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>整合內部部署 Unified Messaging 和 Lync Server 2013 的部署程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-17_

如果您想要將 Exchange 整合通訊（UM）與 Lync Server 2013 整合，您必須執行本主題中所述的工作。 此外，請務必參閱[整合內部部署整合訊息和 Lync Server 2013 指南](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)中所述的規劃與部署最佳做法。 本主題假設您已將 Lync Server 2013 與 collocated 中繼伺服器一起部署，且您已為 Lync Server 2013 啟用使用者，但不一定已執行所有部署和設定步驟來啟用企業語音，如在部署檔中的[Lync Server 2013 中部署企業語音中](lync-server-2013-deploying-enterprise-voice.md)所述。

<div>

## <a name="unified-messaging-integration-process"></a>整合通訊流程整合程式

<div>


> [!IMPORTANT]
> 請務必與貴組織的 Exchange 管理員共同作業，以確認您要執行的工作，以協助確保順利、成功的整合。



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>分</th>
<th>步驟</th>
<th>必要的群組和角色</th>
<th>部署檔</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>部署下列其中一項：</p>
<ul>
<li><p>Microsoft Exchange Server 2007 Service Pack 1 （SP2）或最新 Service pack</p></li>
<li><p>Microsoft Exchange Server 2010 或最新 service pack</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>如果您使用的是 Microsoft Exchange Server 2013，請在與 Lync Server 2013 相同的林中或不同的林中，安裝下列 Exchange Server 角色：</p>
<ul>
<li><p>用戶端存取</p></li>
<li><p>控制</p></li>
</ul>
<p>如果 Microsoft Exchange Server 2013 與 Exchange 整合通訊（UM）安裝在不同的林中，請將每個 Exchange 林設定為信任 Lync Server 2013 林。</p>
<p>如果您使用的是 Exchange 2010，請在與 Lync Server 2013 相同的林中或不同的林中，安裝下列 Exchange 伺服器角色：</p>
<ul>
<li><p>整合通訊</p></li>
<li><p>中樞傳輸</p></li>
<li><p>用戶端存取</p></li>
<li><p>控制</p></li>
</ul>
<p>如果 Lync Server 2013 與 Exchange 整合通訊（UM）安裝在不同的林中，請將每個 Exchange 林設定為信任 Lync Server 2013 林。</p></td>
<td><p>企業系統管理員（如果這是組織中的第一個 Exchange 伺服器）</p>
<p>或</p>
<p>Exchange 組織管理員（如果這不是組織中的第一個 Exchange 伺服器）</p></td>
<td><p>請參閱適用于您 Exchange 伺服器版本的相關檔：</p>
<dl>
<dt><span></span></dt>
<dd><p>Exchange Server 2007 部署檔位於<a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>。</p>
</dd>
<dt><span></span></dt>
<dd><p>Exchange Server 2010 或最新的 service pack 部署<a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>檔在。</p>
</dd>
<dt><span></span></dt>
<dd><p>Microsoft Exchange Server 2013 規劃和部署<a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>。</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>安裝憑證。</p></td>
<td><p>從信任的根憑證授權單位（CA）下載並安裝每個 Exchange UM 伺服器的憑證。 在執行 Exchange UM 和 Lync Server 2013 的伺服器之間，雙方傳輸層級安全性（MTLS）都需要有證書。</p></td>
<td><p>人員</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">在運行 Microsoft Exchange Server 整合通訊的伺服器上設定憑證</a></p></td>
</tr>
<tr class="odd">
<td><p>建立及設定新的 Exchange UM SIP 撥號計畫。</p></td>
<td><p>在 Exchange UM 伺服器上，根據貴組織的特定部署需求來建立 SIP 撥號方案。</p></td>
<td><p>Exchange 組織管理員</p></td>
<td><p>若為 Exchange 2007 SP1 或最新的 service &quot;pack，請參閱如何在<a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>建立整合通訊 SIP&quot; URI 撥號計畫。</p>
<p>若為 Exchange 2010 或最新的 service &quot;pack，請參閱在&quot;上<a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>建立 UM 撥號方案。</p>
<p>若為 Exchange 2013，請參閱的<a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>[整合訊息]。</p></td>
</tr>
<tr class="even">
<td><p>設定 Exchange UM SIP 撥號方案的安全性設定。</p></td>
<td><p>若要加密企業語音流量，請將 Exchange UM SIP 撥號方案的安全性設定設定為 [ <strong>SIP 安全</strong>] 或 [<strong>安全</strong>的]。 如果您已在您的環境中部署或規劃部署 Lync Phone Edition 裝置，這是一個特別重要的步驟。 若要讓 Lync Phone Edition 裝置在使用 Exchange UM 整合的環境中運作，Lync Server 加密設定必須與 Exchange UM 撥號方案安全性設定一致。 如需詳細資訊，請參閱部署檔。</p></td>
<td><p>Exchange 組織管理員</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">在 Microsoft Exchange for Lync Server 2013 中設定整合通訊</a></p>
<p>若是 Exchange 2007 SP1 或最新的 service pack，請參閱：</p>
<p>&quot;如何在&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>整合的郵件撥號方案上設定安全性。</p>
<p>若是 Exchange 2010 或最新的 service pack，請參閱：</p>
<p>&quot;在 UM 撥號方案&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>上設定 VoIP 安全性。</p>
<p>若為 Exchange 2013，請參閱的<a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>[整合訊息]。</p></td>
</tr>
<tr class="odd">
<td><p>將整合郵件伺服器新增至 Exchange UM SIP 撥號計畫。</p></td>
<td><p>若要讓新安裝的整合通訊伺服器應答並處理來電，您必須將統一訊息伺服器新增到 UM 撥號方案。 在這種情況下，請將伺服器新增到 Exchange UM SIP 撥號方案。</p></td>
<td><p>人員</p>
<p>Exchange Server 系統管理員</p></td>
<td><p>針對 Exchange 2007 SP1 或最新的 service pack &quot;，請參閱如何將整合郵件伺服器新增至&quot;撥號<a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>計畫。</p>
<p>若為 Exchange 2010 或最新的 service &quot;pack，請參閱在上<a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>查看或設定&quot; UM 伺服器的屬性。</p>
<p>若為 Exchange 2013，請參閱的<a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>[整合訊息]。</p></td>
</tr>
<tr class="even">
<td><p>使用 SIP 位址設定信箱。</p></td>
<td><p>將 SIP 位址指派給將使用 Exchange UM 功能之企業語音使用者的信箱。</p></td>
<td><p>Lync Server 2013 系統管理員</p>
<p>Exchange 收件者管理員</p></td>
<td><p>若為 Exchange 2007 SP1 或最新的 service &quot;pack，請參閱如何在上&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>新增、移除或修改啟用 UM 的使用者的 SIP 位址。</p>
<p>若為 Exchange 2010 或最新的 service &quot;pack，請參閱在上<a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>修改啟用 UM 的&quot;使用者的 SIP 位址。</p>
<p>若為 Exchange 2013，請參閱的<a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>[整合訊息]。</p></td>
</tr>
<tr class="odd">
<td><p>執行 exchucutil. ps1 腳本。</p></td>
<td><p>在執行 Exchange UM 服務的伺服器上，開啟 Exchange 管理命令介面，並執行 exchucutil. ps1 腳本，此腳本會執行下列動作：</p>
<ul>
<li><p>授予 Lync Server 2013 讀取 Exchange UM Active Directory 網域服務物件的許可權，特別是在前一個工作中建立的 SIP 撥號方案。</p></li>
<li><p>在 Active Directory 中針對每一個 Lync Server 2013 企業版文件庫或標準版伺服器（宿主已啟用企業語音的使用者）建立統一通訊 IP 閘道物件。</p></li>
<li><p>針對每個閘道建立 Exchange UM 查尋群組。 [查尋] 群組試點識別碼將是與對應的閘道相關聯的撥號方案名稱。 如果有一個以上的撥號方案，則需要將這些專案對應至1:1。</p></li>
</ul></td>
<td><p>Exchange 組織管理員</p>
<p>Exchange 收件者管理員</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">在 Microsoft Exchange for Lync Server 2013 中設定整合通訊</a></p></td>
</tr>
<tr class="even">
<td><p>設定 Lync Server 2013 撥號方案。</p></td>
<td><p>如果您要與 Exchange 2007 SP1 或最新的 service pack （或 Exchange 2010）整合，請建立新的企業語音撥號方案，其名稱必須符合 Exchange UM 撥號方案的完整功能變數名稱（FQDN）。</p>



> [!NOTE]
> 您將需要針對每個 UM 撥號方案進行這項作業。


<p>如果您要與 Exchange 2010 SP1 整合，請確定已設定適當的全域/網站層級或池層級的企業語音撥號方案。</p>



> [!NOTE]
> 如果您要與 Exchange 2010 SP1 整合，Lync Server 撥號方案與 Exchange UM SIP 撥號方案名稱不需相符。

</td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">在 Lync Server 2013 中設定撥號對應表</a></p></td>
</tr>
<tr class="odd">
<td><p>執行 Exchange UM 整合工具。</p></td>
<td><p>在 Lync Server 2013 上，執行<strong>ocsumutil</strong>，這是：</p>
<ul>
<li><p>建立訂閱者存取權及自動語音應答連絡人物件。</p></li>
<li><p>驗證是否有符合 Exchange UM 撥號方案 FQDN 之名稱的企業語音撥號方案。 如果您執行的是 Exchange 2010 SP1 或更新版本，撥號方案名稱不需要符合，而且您可以略過工具對此所做的警告。</p></li>
</ul>
<p>此工具的運作方式是掃描 Exchange UM 設定的 Active Directory，並允許 Lync Server 2013 系統管理員來查看、建立及編輯連絡人物件。</p></td>
<td><p>RTCUniversalServerAdmins<em>和</em>RTCUniversalUserAdmins</p>



> [!IMPORTANT]
> 若要成功執行 ocsumutil，使用者必須屬於這兩個群組。





> [!NOTE]
> 若要建立連絡人物件，執行 ocsumutil 的使用者必須擁有儲存新連絡人物件之 Active Directory 組織單位（OU）的正確許可權。 您可以執行<STRONG>授與 CsOUPermission</STRONG> Cmdlet 來授與此許可權。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔。

</td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">設定 Lync Server 2013 以搭配 Microsoft Exchange Server 上的 Unified Messaging 使用</a></p></td>
</tr>
<tr class="even">
<td><p>如有需要，請執行其他企業語音設定步驟。</p></td>
<td><p>如果您尚未在伺服器或使用者上設定 [企業語音設定]，請執行下列其中一項或多項操作：</p>
<ul>
<li><p>部署和設定</p>
<p>公用交換式電話網絡（PSTN）閘道和轉送伺服器</p></li>
<li><p>定義語音原則、PSTN 使用方式記錄，以及傳出通話路由。</p></li>
<li><p>允許使用者使用企業語音。</p></li>
<li><p>您也可以選擇使用撥號方案設定特定的使用者。</p></li>
</ul>
<p>根據您所啟用的企業語音功能，可能需要其他配置步驟。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>請參閱下列各節中的主題：</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">在 Lync Server 2013 中設定語音原則、PSTN 使用方式記錄及語音路由</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">在 Lync Server 2013 中部署企業版語音</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>針對 Exchange UM 啟用企業語音使用者。</p></td>
<td><p>在 Exchange UM 伺服器上，確定已建立統一訊息信箱原則，且每位使用者都有唯一的分機號碼指派，然後讓使用者使用統一訊息。</p></td>
<td><p>Exchange 收件者管理員</p></td>
<td><p>若為 Exchange 2007 SP1 或最新的 service &quot;pack，請參閱如何為使用者啟用&quot;整合<a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>訊息。</p>
<p>若為 Exchange 2010 或最新的 service &quot;pack，請參閱在<a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>下列&quot;啟用整合通訊的使用者。</p>
<p>若為 Exchange 2013，請參閱的<a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>[整合訊息]。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

