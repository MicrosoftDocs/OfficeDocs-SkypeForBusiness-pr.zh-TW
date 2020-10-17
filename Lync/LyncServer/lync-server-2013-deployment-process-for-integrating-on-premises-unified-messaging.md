---
title: 整合內部部署整合通訊的部署程式
description: 整合內部部署整合通訊的部署程式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c1b8f528edb970893198ed06b821535a398f09d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569519"
---
# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>整合內部部署整合通訊和 Lync Server 2013 的部署程式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-17_

如果您想要整合 Exchange 整合通訊 (UM) 與 Lync Server 2013，您必須執行本主題中所述的工作。 此外，請務必查看 [有關整合內部部署整合通訊和 Lync Server 2013 的指導方針](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)中所述的規劃及部署最佳作法。 本主題假設您已部署 Lync Server 2013 與組合轉送伺服器，且已針對 Lync Server 2013 啟用使用者，但不一定已執行所有部署和設定步驟來啟用企業語音，如部署檔中的 [Lync Server 2013 中的部署企業語音](lync-server-2013-deploying-enterprise-voice.md) 所述。

<div>

## <a name="unified-messaging-integration-process"></a>Unified Messaging 整合程序

<div>


> [!IMPORTANT]
> 請務必與組織的 Exchange 系統管理員協調，以確認您將執行的各項工作，以協助確保順利、成功的整合。



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
<th>階段</th>
<th>步驟</th>
<th>所需群組和角色</th>
<th>部署文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>部署下列其中一項：</p>
<ul>
<li><p>Microsoft Exchange Server 2007 Service Pack 1 (SP2) 或最新的 service pack</p></li>
<li><p>Microsoft Exchange Server 2010 或最新的 service pack</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>如果您使用的是 Microsoft Exchange Server 2013，請在相同樹系或不同的樹系中，將下列 Exchange Server 角色安裝為 Lync Server 2013：</p>
<ul>
<li><p>Client Access</p></li>
<li><p>信箱</p></li>
</ul>
<p>如果 Microsoft Exchange Server 2013 和 Exchange 整合通訊 (UM) 安裝在不同的樹系中，請將每個 Exchange 樹系設定為信任 Lync Server 2013 樹系。</p>
<p>如果您使用的是 Exchange 2010，請在相同樹系或不同樹系中，將下列 Exchange 伺服器角色安裝為 Lync Server 2013：</p>
<ul>
<li><p>Unified Messaging</p></li>
<li><p>Hub Transport</p></li>
<li><p>Client Access</p></li>
<li><p>信箱</p></li>
</ul>
<p>如果 Lync Server 2013 和 Exchange 整合通訊 (UM) 安裝在不同的樹系中，請將每個 Exchange 樹系設定為信任 Lync Server 2013 樹系。</p></td>
<td><p>企業的系統管理員 (如果這是組織中的第一部 Exchange Server)</p>
<p>-或-</p>
<p>Exchange 組織系統管理員 (如果這不是組織中的第一部 Exchange Server)</p></td>
<td><p>請參閱您的 Exchange Server 版本所適用的文件：</p>
<dl>
<dt><span></span></dt>
<dd><p>Exchange Server 2007 部署檔，網址為 <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a> 。</p>
</dd>
<dt><span></span></dt>
<dd><p>Exchange Server 2010 或最新的 service pack 部署檔，網址為 <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a> 。</p>
</dd>
<dt><span></span></dt>
<dd><p>Microsoft Exchange Server 2013 規劃和部署于 <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a> 。</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>安裝憑證。</p></td>
<td><p>從受信任的憑證授權單位單位 (CA) 下載並安裝每個 Exchange UM 伺服器的憑證。 在執行 Exchange UM 和 Lync Server 2013 的伺服器之間，相互傳輸層級安全性 (MTLS) 皆需要憑證。</p></td>
<td><p>系統管理員</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">在執行 Microsoft Exchange Server 整合通訊的伺服器上設定憑證</a></p></td>
</tr>
<tr class="odd">
<td><p>建立並設定新的 Exchange UM SIP 撥號對應表。</p></td>
<td><p>在 Exchange UM 伺服器上，根據您組織的特定部署需求建立 SIP 撥號對應表。</p></td>
<td><p>Exchange 組織系統管理員</p></td>
<td><p>如需 Exchange 2007 SP1 或最新的 service pack，請參閱 how &quot; To Create a 整合通訊 SIP URI 撥號對應表的方式 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a> 。</p>
<p>若為 Exchange 2010 或最新的 service pack，請參閱 &quot; Create a UM 撥號對應表 &quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a> 。</p>
<p>若為 Exchange 2013，請參閱整合通訊位置 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> 。</p></td>
</tr>
<tr class="even">
<td><p>設定 Exchange UM SIP 撥號對應表的安全性設定。</p></td>
<td><p>若要加密 Enterprise Voice 流量，請將 Exchange UM SIP 撥號對應表上的安全性設定設定為 [ <strong>SIP 安全</strong> ] 或 [ <strong>安全</strong>]。 如果您已在環境中部署或規劃部署 Lync Phone Edition 裝置，則此為特別重要的步驟。 若要讓 Lync Phone Edition 裝置在具有 Exchange UM 整合的環境中運作，Lync Server 加密設定必須與 Exchange UM 撥號對應表安全性設定對齊。 如需詳細資訊，請參閱＜部署＞文件。</p></td>
<td><p>Exchange 組織系統管理員</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">在 Microsoft Exchange 上設定 Lync Server 2013 的整合通訊</a></p>
<p>針對 Exchange 2007 SP1 或最新的 service pack，另請參閱：</p>
<p>&quot;如何在整合通訊撥號對應表上設定安全性 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a> 。</p>
<p>對於 Exchange 2010 或最新的 Service Pack，另請參閱：</p>
<p>&quot;在 UM 撥號對應表上設定 VoIP 安全性 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a> 。</p>
<p>若為 Exchange 2013，請參閱整合通訊位置 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> 。</p></td>
</tr>
<tr class="odd">
<td><p>將整合通訊伺服器新增至 Exchange UM SIP 撥號對應表。</p></td>
<td><p>若要讓新安裝的 Unified Messaging 伺服器能夠接聽及處理來電，您必須將 Unified Messaging 伺服器新增至 UM 撥號對應表。 在此情況下，請將伺服器新增至 Exchange UM SIP 撥號對應表。</p></td>
<td><p>系統管理員</p>
<p>Exchange Server 系統管理員</p></td>
<td><p>若為 Exchange 2007 SP1 或最新的 service pack，請參閱 how &quot; To Add 整合通訊伺服器至撥號對應表 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a> 。</p>
<p>若為 Exchange 2010 或最新的 service pack，請參閱 &quot; View Or CONFIGURE UM Server 的屬性 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a> 。</p>
<p>若為 Exchange 2013，請參閱整合通訊位置 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> 。</p></td>
</tr>
<tr class="even">
<td><p>以 SIP 位址設定信箱。</p></td>
<td><p>將 SIP 位址指派給將使用 Exchange UM 功能的 Enterprise Voice 使用者信箱。</p></td>
<td><p>Lync Server 2013 系統管理員</p>
<p>Exchange 收件者系統管理員</p></td>
<td><p>針對 Exchange 2007 SP1 或最新的 service pack，請參閱 how &quot; To 新增、移除或修改 UM-Enabled 使用者的 SIP 位址 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a> 。</p>
<p>若為 Exchange 2010 或最新的 service pack，請參閱 &quot; 修改 UM-Enabled 使用者的 SIP 位址 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a> 。</p>
<p>若為 Exchange 2013，請參閱整合通訊位置 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> 。</p></td>
</tr>
<tr class="odd">
<td><p>執行 exchucutil.ps1 指令碼。</p></td>
<td><p>在執行 Exchange UM 服務的伺服器上，開啟 Exchange 管理命令介面，並執行 exchucutil.ps1 腳本，這會執行下列作業：</p>
<ul>
<li><p>授與 Lync Server 2013 讀取 Exchange UM Active Directory 網域服務物件（特別是先前任務中建立的 SIP 撥號對應表）的許可權。</p></li>
<li><p>為主控已啟用 Enterprise Voice 之使用者的每個 Lync Server 2013 Enterprise Edition 集區或 Standard Edition Server 建立 Active Directory 中的整合通訊 IP 閘道物件。</p></li>
<li><p>為每個閘道建立一個 Exchange UM 群組搜尋。 群組搜尋引導識別碼將會是與對應閘道關聯的撥號對應表名稱。 如果有多個撥號對應表，則這些項目必須要一一對應。</p></li>
</ul></td>
<td><p>Exchange 組織系統管理員</p>
<p>Exchange 收件者系統管理員</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">在 Microsoft Exchange 上設定 Lync Server 2013 的整合通訊</a></p></td>
</tr>
<tr class="even">
<td><p>設定 Lync Server 2013 撥號對應表。</p></td>
<td><p>若要與 Exchange 2007 SP1 或最新的 service pack （或 Exchange 2010）整合，請建立新的 Enterprise Voice 撥號對應表，並使其名稱符合 Exchange UM 撥號對應表 (FQDN) 的完整功能變數名稱。</p>



> [!NOTE]
> 您必須為每個 UM 撥號對應表執行這項作業。


<p>若要與 Exchange 2010 SP1 整合，請確定已設定適當的全域/網站層級或集區層級的 Enterprise Voice 撥號對應表。</p>



> [!NOTE]
> 如果您要與 Exchange 2010 SP1 整合，Lync Server 撥號對應表和 Exchange UM SIP 撥號對應表名稱不需要相符。

</td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">在 Lync Server 2013 中設定撥號對應表</a></p></td>
</tr>
<tr class="odd">
<td><p>執行 Exchange UM 整合工具。</p></td>
<td><p>在 Lync Server 2013 上，執行 <strong>ocsumutil.exe</strong>，其：</p>
<ul>
<li><p>建立「訂戶存取」與「自動語音應答」連絡人物件。</p></li>
<li><p>驗證是否有符合 Exchange UM 撥號對應表 FQDN 之名稱的 Enterprise Voice 撥號對應表。 如果您執行的是 Exchange 2010 SP1 或更新版本，撥號對應表名稱不需要比對，您可以忽略此工具對此的警告。</p></li>
</ul>
<p>此工具的運作方式是掃描 Exchange UM 設定的 Active Directory，並讓 Lync Server 2013 系統管理員可以查看、建立及編輯連絡人物件。</p></td>
<td><p>RTCUniversalServerAdmins <em>與</em> RTCUniversalUserAdmins</p>



> [!IMPORTANT]
> 使用者必須同時屬於這兩個群組，ocsumutil.exe 才能順利執行。





> [!NOTE]
> 若要建立連絡人物件，執行 ocsumutil.exe 的使用者對於新連絡人物件存放所在的 Active Directory 組織單位 (OU) 必須具備正確的權限。 您可以執行 <STRONG>Grant-CsOUPermission</STRONG> Cmdlet 來授與此許可權。 如需詳細資料，請參閱＜Lync Server 管理命令介面＞文件。

</td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">設定 Lync Server 2013，以搭配 Microsoft Exchange Server 上的整合通訊使用</a></p></td>
</tr>
<tr class="even">
<td><p>如有必要，請執行其他企業語音設定步驟。</p></td>
<td><p>如果您尚未設定伺服器或使用者的企業語音設定，請執行下列一或多項作業：</p>
<ul>
<li><p>部署和設定</p>
<p>公用交換電話網路 (PSTN) 閘道和轉送伺服器</p></li>
<li><p>定義語音原則、PSTN 使用方式記錄與撥出電話路由。</p></li>
<li><p>啟用使用者的企業語音。</p></li>
<li><p>(選擇性) 設定特定使用者的撥號對應表。</p></li>
</ul>
<p>視您所啟用的企業語音功能之不同，您可能必須執行其他設定步驟。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>請參閱以下幾節中的主題：</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">在 Lync Server 2013 中設定語音原則、PSTN 使用方式記錄和語音路由</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">在 Lync Server 2013 中部署企業語音</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>啟用 Exchange UM 的 Enterprise Voice 使用者。</p></td>
<td><p>在 Exchange UM 伺服器上，確定已建立整合通訊信箱原則，且每位使用者都有唯一的分機號碼指派，然後為使用者啟用整合通訊。</p></td>
<td><p>Exchange 收件者系統管理員</p></td>
<td><p>若為 Exchange 2007 SP1 或最新的 service pack，請參閱 how &quot; To Enable a User for a 整合通訊 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a> 。</p>
<p>針對 Exchange 2010 或最新的 service pack，請參閱 &quot; Enable a User for a 整合通訊 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a> 。</p>
<p>若為 Exchange 2013，請參閱整合通訊位置 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> 。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

