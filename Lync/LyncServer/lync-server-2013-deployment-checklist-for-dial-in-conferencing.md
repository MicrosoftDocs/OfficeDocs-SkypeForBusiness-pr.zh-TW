---
title: Lync Server 2013 電話撥入式會議的部署檢查清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44591676d69b5fb4ac3d66ce0e18718389a0c189
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的電話撥入式會議的部署檢查清單

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-10-03_

當您部署會議工作負載時，會部署電話撥入式會議所需的元件。 在您可以設定電話撥入式會議之前，您必須先部署企業語音或中繼伺服器以及公用交換電話網絡（PSTN）閘道。

您必須先執行下表中的所有步驟，才能讓使用者從 PSTN 撥入以加入音訊/視訊會議。

<div>


> [!NOTE]  
> 如果您是從 Office 通訊伺服器 2007 R2 進行遷移，您必須在部署電話撥入式會議之前，將最新的更新套用到您的 Office 通訊伺服器 2007 R2 環境。



</div>

### <a name="dial-in-conferencing-deployment-process"></a>電話撥入式會議部署程式

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
<th>許可權</th>
<th>部署檔</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>建立包含會議工作負載的拓撲，包括轉送伺服器和 PSTN 閘道，以及部署前端池或標準版伺服器</strong></p></td>
<td><ol>
<li><p>執行拓撲產生器以設定您的拓撲。 配置拓撲時，請選取 [電話撥入式會議] 選項。</p></li>
<li><p>發佈拓撲並部署前端池或標準版伺服器。</p></li>
<li><p>如有需要，請建立獨立的中繼伺服器，並將它與 PSTN 閘道建立關聯。</p>
<div>

> [!NOTE]  
> 只有在您不部署企業語音且沒有 collocate 企業 EditionFront 端伺服器或標準版伺服器的中繼伺服器時，才需要執行此步驟。 如果您要部署企業語音，您必須安裝並設定轉送伺服器和 PSTN 閘道，做為企業語音部署的一部分。 如果您 collocate 的是中繼伺服器，您可以在前端池或標準版伺服器部署中安裝並設定中繼伺服器。


</div></li>
</ol></td>
<td><p>網域管理員</p>
<p>RTCUniversalServerAdmins</p>
<p>許可權</p></td>
<td><ul>
<li><p><a href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</a></p></li>
<li><p>若要建立獨立的中繼伺服器池：<a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">在 Lync server 2013 中部署轉送伺服器和定義對等</a>專案</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>設定撥號方案</strong></p></td>
<td><p>撥號方案是一組電話號碼正規化規則，可將從特定位置撥打電話的電話號碼轉換為單一標準（e. 164）格式，以用於手機授權及呼叫路由。 根據各自的撥號方案，從不同位置撥打電話的電話號碼，視每個地點適當地解析成不同的 e. 164 號碼。 如果您要部署企業語音，請將撥號方案設定為該部署的一部分，而且您必須確認撥號方案也能容納電話撥入式會議。 如果您沒有部署企業語音，您必須為電話撥入式會議設定撥號方案。</p>
<p>使用 Lync Server 2013 的 [控制台] 或 [Lync Server 管理命令介面] 來設定撥號方案，如下所示：</p>
<ol>
<li><p>建立一或多個用來傳送撥入存取電話號碼的撥號方案。</p></li>
<li><p>將預設的撥號方案指派給每個文件庫。 將<strong>電話撥入式會議區域</strong>設定為要套用撥號計畫的地理位置。 該區域會將撥號方案與撥入存取號碼進行關聯。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">在 Lync Server 2013 中設定電話撥入式會議的撥號對應表</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>確定撥號方案是指派的區域</strong></p></td>
<td><p>執行<strong>CsDialPlan</strong>和<strong>CsDialPlan</strong> Cmdlet，以確定所有撥號方案都已指派區域。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">確認 Lync Server 2013 已指派地區的撥號方案</a></p></td>
</tr>
<tr class="even">
<td><p><strong>可選驗證或修改使用者個人識別碼（PIN）需求</strong></p></td>
<td><p>使用 Lync Server 2013 的 [控制台] 或 [Lync Server 管理命令介面] 來查看或修改會議<strong>PIN 原則</strong>。 您可以指定最小 PIN 長度、最大登入嘗試次數、PIN 到期日，以及是否允許通用模式。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(選用) 在 Lync Server 2013 中驗證 PIN 原則設定</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>設定會議原則以支援電話撥入式會議</strong></p></td>
<td><p>使用 Lync Server 2013 [控制台] 或 [Lync Server 管理命令介面] 來設定<strong>會議原則</strong>設定。 指定是否：</p>
<ul>
<li><p>已啟用 PSTN 會議撥入。</p></li>
<li><p>使用者可以邀請匿名參與者。</p></li>
<li><p>未經驗證的使用者可以使用撥出 phoning 加入會議。 使用撥出 phoning，會議服務器就會呼叫使用者，而使用者會接聽電話加入會議。</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">在 Lync Server 2013 中設定電話撥入式會議的會議原則</a></p></td>
</tr>
<tr class="even">
<td><p><strong>設定撥入存取號碼</strong></p></td>
<td><p>使用 Lync Server 2013 [控制台] 或 [Lync Server 管理命令介面] 來設定使用者撥入會議所撥打的撥入號碼，並指定將存取號碼與適當的撥號方案相關聯的地區。 召集人撥號計畫所指定之區域的前三個存取號碼包含在會議邀請中。 [電話撥入式會議設定] 頁面上提供所有存取號碼。</p>
<div>

> [!NOTE]  
> 在您建立撥入存取號碼之後，您可以使用<STRONG>CsDialInConferencingAccessNumber</STRONG> Cmdlet 來修改 Active Directory 連絡人物件的顯示名稱，讓使用者能更輕鬆地識別正確的存取號碼。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">在 Lync Server 2013 中設定電話撥入式會議存取號碼</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>(選用) 驗證電話撥入式會議設定</strong></p></td>
<td><p>使用<strong>CsDialinConferencingAccessNumber</strong> Cmdlet 來搜尋具有電話撥入式會議區域的撥號方案，這些方案不是由任何存取號碼和沒有指派區域的存取號碼所使用。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p>
<p>CsHelpDesk</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(選用) 在 Lync Server 2013 中驗證電話撥入式會議設定</a></p></td>
</tr>
<tr class="even">
<td><p><strong>可選修改 DTMF 命令的金鑰組應</strong></p></td>
<td><p>使用<strong>CsDialinConferencingDtmfConfiguration</strong> Cmdlet 來修改雙色調 MULTIFREQUENCY （DTMF）命令使用的金鑰，這些參與者可以用來控制會議設定（例如靜音和取消靜音，或鎖定與解除鎖定）。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(選用) 在 Lync Server 2013 中修改 DTMF 命令的按鍵對應</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>可選修改會議加入並離開宣告行為</strong></p></td>
<td><p>使用<strong>CsDialinConferencingConfiguration</strong>變更參與者加入與離開會議時的宣告運作方式。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(選用) 在 Lync Server 2013 中啟用和停用會議加入和離開宣告</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(選用) 驗證電話撥入式會議</strong></p></td>
<td><p>使用<strong>CsDialInConferencing</strong> Cmdlet 來測試指定池的存取號碼是否正常運作。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">Lync Server 2013 中的 (選用) 驗證電話撥入式會議</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>部署 Lync 2013 的線上會議增益集</strong></p></td>
<td><p>部署 Lync 2013 的線上會議增益集，讓使用者能夠排程支援電話撥入式會議的會議。 當您安裝 Lync 2013 時，系統會自動安裝 Lync 2013 的線上會議增益集。</p></td>
<td><p>人員</p></td>
<td><p><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">部署 Lync 2013 的線上會議增益集</a></p></td>
</tr>
<tr class="even">
<td><p><strong>設定使用者帳戶設定</strong></p></td>
<td><p>使用 Lync Server 2013 的 [控制台] 或 [Lync Server 管理命令介面]，將電話<strong>線路 URI</strong>設定為唯一、標準化的電話號碼（例如電話： + 14255550200）。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsAdministrator</p>
<p>CsUserAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-user-account-settings.md">在 Lync Server 2013 中設定使用者帳戶設定</a></p></td>
</tr>
<tr class="odd">
<td><p>採用設定會議目錄</p></td>
<td><p>使用<strong>CsConferenceDirectory</strong> Cmdlet 為池中的每個999使用者建立一個會議目錄。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013 中的電話撥入式會議需求</a> <a href="recommended-create-conference-directories.md">（建議使用）建立會議目錄</a></p></td>
</tr>
<tr class="even">
<td><p><strong>可選歡迎使用者撥入式會議及設定初始 PIN</strong></p></td>
<td><p>使用<strong>CsPinSendCAWelcomeMail</strong>腳本來設定使用者的初始 pin，並傳送包含初始 PIN 的歡迎電子郵件，以及 [電話撥入式會議設定] 頁面的連結。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(選用) 在 Lync Server 2013 中歡迎使用者使用電話撥入式會議</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

