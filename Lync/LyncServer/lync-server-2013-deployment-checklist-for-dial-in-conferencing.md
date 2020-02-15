---
title: Lync Server 2013 的電話撥入式會議的部署檢查表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc593e5a40633f98146c4ce94f82b132f15ca6d5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的電話撥入式會議的部署檢查表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-10-03_

當您部署會議工作負載時，會部署電話撥入式會議所需的元件。 您可以設定電話撥入式會議之前，您需要部署企業語音或中繼伺服器與公用交換的電話網路 (PSTN) 閘道。

使用者可以從 PSTN 加入音訊/視訊會議撥入之前，必須執行下表中的所有步驟。

<div>


> [!NOTE]  
> 如果您從 Office Communications Server 2007 R2 移轉，您必須至少將最新更新套用至 Office Communications Server 2007 R2 環境，才能部署電話撥入式會議。



</div>

### <a name="dial-in-conferencing-deployment-process"></a>電話撥入式會議部署程序

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
<th>權限</th>
<th>部署文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>建立包含會議工作負載，包括中繼伺服器和 PSTN 閘道、 拓撲及部署前端集區或 Standard Edition server</strong></p></td>
<td><ol>
<li><p>執行拓撲產生器來設定您的拓撲。 同時設定拓撲，請選取撥入式會議選項。</p></li>
<li><p>發行拓撲並部署前端集區或 Standard Edition server。</p></li>
<li><p>如有必要，建立獨立中繼伺服器，並將它與 PSTN 閘道。</p>
<div>

> [!NOTE]  
> 只有當您未部署 Enterprise Voice 且不組合的中繼伺服器與企業 EditionFront 端伺服器或 Standard Edition 伺服器，則需要此步驟。 如果您部署企業語音時，安裝及設定中繼伺服器和 PSTN 閘道的 Enterprise Voice 部署過程。 如果您在組合的中繼伺服器，安裝及設定中繼伺服器的前端集區或 Standard Edition server 部署的一部分。


</div></li>
</ol></td>
<td><p>Domain Admins</p>
<p>RTCUniversalServerAdmins</p>
<p>系統管理員</p></td>
<td><ul>
<li><p><a href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</a></p></li>
<li><p>若要建立獨立的中繼伺服器集區： <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and Lync Server 2013 中的定義同儕</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>設定撥號對應表</strong></p></td>
<td><p>撥號對應表是一組的電話號碼正規化規則轉譯電話號碼撥打從特定位置的單一標準 (E.164) 格式，以便進行電話授權和來電路由。 從不同位置撥打的電話號碼相同可以根據各自的撥號對應表，解析為不同的 E.164 號碼，視每個位置。 如果您部署企業語音撥號對應表設定為該部署的一部分，您必須先確認撥號對應表也會配合撥入式會議。 如果您不要部署 Enterprise Voice，您需要設定電話撥入式會議的撥號對應表計劃。</p>
<p>使用 Lync Server 2013 控制台] 或 [Lync Server 管理命令介面來設定撥號對應表，如下所示：</p>
<ol>
<li><p>建立一或多個撥號對應表計劃路由傳送撥入存取電話號碼。</p></li>
<li><p>將預設撥號對應表指派給每個集區。 設定<strong>電話撥入式會議地區</strong>為撥號對應表套用到的地理位置。 與撥入存取號碼區域產生關聯的撥號對應表。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Lync Server 2013 中設定撥入式會議的撥號對應表計的劃</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>確定撥號對應表已被指派區域</strong></p></td>
<td><p>執行<strong>Get-csdialplan</strong>和<strong>Set-csdialplan</strong> cmdlet，以確定所有撥號對應表計劃擁有指派的地區。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">確定撥號對應表 Lync Server 2013 已指派區域</a></p></td>
</tr>
<tr class="even">
<td><p><strong>（選用）確認或修改使用者個人識別碼號碼 (PIN) 需求</strong></p></td>
<td><p>使用 Lync Server 2013 控制台] 或 [Lync Server 管理命令介面來檢視或修改會議<strong>的 pin 碼原則</strong>。 您可以指定最小 PIN 長度] 中，登入嘗試，PIN 到期的最大數目以及是否允許共同模式。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-pin-policy-settings.md">（選用）確認 Lync Server 2013 中的 pin 碼原則設定</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>設定會議原則以支援電話撥入式會議</strong></p></td>
<td><p>使用 Lync Server 2013 控制台] 或 [Lync Server 管理命令介面來設定<strong>會議原則</strong>設定。 指定是否：</p>
<ul>
<li><p>PSTN 會議撥號對應表中已啟用。</p></li>
<li><p>使用者可以邀請匿名參與者。</p></li>
<li><p>未驗證的使用者可以使用電話撥出式打電話加入會議。 電話撥出式打電話，會議伺服器會呼叫該使用者與使用者接聽電話加入會議。</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">在 Lync Server 2013 中設定電話撥入式會議的原則</a></p></td>
</tr>
<tr class="even">
<td><p><strong>設定撥入存取號碼</strong></p></td>
<td><p>使用 Lync Server 2013 Control Panel 或 Lync Server 管理命令介面來設定撥入會議，則使用者呼叫的撥入存取號碼，並指定適當的撥號對應表建立關聯的存取號碼的地區。 召集人的撥號對應表所指定的區域的第三個存取號碼會包含在會議邀請。 所有存取號碼都可在 [電話撥入式會議設定] 頁面上。</p>
<div>

> [!NOTE]  
> 在建立撥入存取號碼後，您可以使用<STRONG>Set-csdialinconferencingaccessnumber</STRONG> cmdlet 修改的 Active Directory 連絡人物件的顯示名稱，以便使用者可以更輕鬆識別正確的存取號碼。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">在 Lync Server 2013 中設定電話撥入式會議存取號碼</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>（選用）驗證電話撥入式會議設定</strong></p></td>
<td><p>使用<strong>Get-csdialinconferencingaccessnumber</strong> cmdlet 來搜尋有未由任何存取號碼撥入式會議地區的撥號對應表計劃和未指派區域的存取號碼。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p>
<p>CsHelpDesk</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">（選用）確認 Lync Server 2013 中的撥入式會議設定</a></p></td>
</tr>
<tr class="even">
<td><p><strong>（選用）修改 DTMF 命令的按鍵對應</strong></p></td>
<td><p>使用<strong>Set-csdialinconferencingdtmfconfiguration</strong> cmdlet 來修改複頻式訊號 (DTMF) 命令，供參與者用來控制會議設定所使用的機碼 (例如靜音和取消靜音或鎖定和解除鎖定)。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">（選用）修改 Lync Server 2013 中的 DTMF 命令的按鍵對應</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>（選用）修改會議加入和離開宣告行為</strong></p></td>
<td><p>使用<strong>Set-csdialinconferencingconfiguration</strong>來變更參與者加入和離開會議時，宣告的運作方式。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">（選用）啟用和停用會議加入和離開宣告在 Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>（選用）確認撥入式會議</strong></p></td>
<td><p>使用<strong>Test-csdialinconferencing</strong> cmdlet 來測試指定的集區的存取號碼正確運作。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">（選用）確認 Lync Server 2013 中的電話撥入式會議</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>部署 Online Meeting add-in for Lync 2013</strong></p></td>
<td><p>部署的線上會議增益集 Lync 2013 讓使用者可以排程支援電話撥入式會議的會議。 線上會議增益集 for Lync 2013 會自動安裝當您安裝 Lync 2013。</p></td>
<td><p>系統管理員</p></td>
<td><p><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">部署 Online Meeting add-in for Lync 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>設定使用者帳戶設定</strong></p></td>
<td><p>使用 Lync Server 2013 Control Panel 或 Lync Server 管理命令介面來設定為唯一、 正規化的電話號碼的電話<strong>線路 URI</strong> (例如，tel: + 14255550200)。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsAdministrator</p>
<p>CsUserAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-user-account-settings.md">在 Lync Server 2013 中設定使用者帳戶設定</a></p></td>
</tr>
<tr class="odd">
<td><p>（建議使用）設定會議目錄</p></td>
<td><p>使用<strong>New-csconferencedirectory</strong> cmdlet 來建立一個的每個 999 使用者的會議目錄集區中。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-dial-in-conferencing-requirements.md">電話撥入式會議需求 Lync Server 2013 中的</a><a href="recommended-create-conference-directories.md">建立會議目錄 （建議使用）</a></p></td>
</tr>
<tr class="even">
<td><p><strong>（選用）歡迎使用者加入電話撥入式會議，並設定初始 PIN</strong></p></td>
<td><p>使用<strong>Set-cspinsendcawelcomemail</strong>指令碼來設定使用者的初始 Pin 並傳送歡迎電子郵件內含初始 PIN 和電話撥入式會議設定] 頁面的連結。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">（選用）歡迎使用者使用 Lync Server 2013 中的電話撥入式會議</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

