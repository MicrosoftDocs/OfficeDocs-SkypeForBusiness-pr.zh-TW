---
title: 電話撥入式會議的 Lync Server 2013 部署檢查清單
description: 電話撥入式會議的 Lync Server 2013 部署檢查清單。
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
ms.openlocfilehash: 743b5120bf011ab8467679bea9869a46231b0835
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568355"
---
# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的電話撥入式會議部署檢查清單

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-10-03_

當您部署會議工作負載時，會部署電話撥入式會議所需的元件。 在設定電話撥入式會議之前，您需要部署 Enterprise Voice 或轉送伺服器，以及公用交換電話網路 (PSTN) 閘道。

在使用者可以從 PSTN 撥入以加入音訊/視訊會議之前，必須先執行下表中的所有步驟。

<div>


> [!NOTE]  
> 如果您是從 Office 通訊伺服器 2007 R2 進行遷移，您必須在部署電話撥入式會議之前，將最新的更新套用至 Office 通訊伺服器 2007 R2 環境。



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
<th>階段</th>
<th>步驟</th>
<th>權限</th>
<th>部署文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>建立包含會議工作負載的拓撲，包括轉送伺服器和 PSTN 閘道，以及部署前端集區或 Standard Edition Server</strong></p></td>
<td><ol>
<li><p>執行拓撲產生器以設定拓撲。 設定拓撲時，請選取 [電話撥入式會議] 選項。</p></li>
<li><p>發行拓撲及部署前端集區或 Standard Edition server。</p></li>
<li><p>如有必要，請建立獨立的轉送伺服器，並將它與 PSTN 閘道建立關聯。</p>
<div>

> [!NOTE]  
> 只有在您未部署 Enterprise Voice，而且不會組合具有 Enterprise EditionFront server 或 Standard Edition Server 的轉送伺服器時，才需要執行此步驟。 如果您部署企業語音，請在企業語音部署中安裝及設定轉送伺服器和 PSTN 閘道。 如果您組合轉送伺服器，請在前端集區或 Standard Edition Server 部署的一部分中安裝及設定轉送伺服器。


</div></li>
</ol></td>
<td><p>Domain Admins</p>
<p>RTCUniversalServerAdmins</p>
<p>系統管理員</p></td>
<td><ul>
<li><p><a href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</a></p></li>
<li><p>若要建立獨立的轉送伺服器集區，請執行下列作業：<a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">部署轉送伺服器並定義 Lync server 2013 中的對等</a>專案</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>設定撥號對應表</strong></p></td>
<td><p>撥號對應表是一組電話號碼正規化規則，可將從特定位置撥打的電話號碼，轉譯成單一標準 () 格式，以進行電話授權和呼叫路由的目的。 從不同位置撥打的相同電話號碼可以根據各自的撥號對應表，視各自的位置而定，解析為不同的 e.164 號碼。 如果您部署企業語音，您可以將撥號對應表設定為該部署的一部分，而且您必須確定撥號對應表也能容納電話撥入式會議。 如果您未部署企業語音，您必須設定電話撥入式會議的撥號對應表。</p>
<p>使用 Lync Server 2013 控制台或 Lync Server 管理命令介面來設定撥號對應表，如下所示：</p>
<ol>
<li><p>建立一或多個用於路由撥入存取電話號碼的撥號對應表。</p></li>
<li><p>將預設的撥號對應表指派給每個集區。 將 <strong>電話撥入式會議地區</strong> 設定為套用撥號對應表的地理位置。 地區會將撥號對應表與電話撥入存取號碼產生關聯。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">在 Lync Server 2013 中設定電話撥入式會議的撥號對應表</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>請確定已將撥號對應表指派給地區</strong></p></td>
<td><p>請執行 <strong>Get-CsDialPlan</strong> 和 <strong>Set-CsDialPlan</strong> Cmdlet，以確定所有撥號對應表均已指派地區。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">確定撥號對應表 Lync Server 2013 具有指派的區域</a></p></td>
</tr>
<tr class="even">
<td><p><strong> (選用) 驗證或修改使用者個人身分識別號碼 (PIN) 需求</strong></p></td>
<td><p>使用 Lync Server 2013 控制台或 Lync Server 管理命令介面來查看或修改會議 <strong>PIN 原則</strong>。 您可以指定最小 PIN 碼長度、登入嘗試次數上限、PIN 碼到期，以及是否允許通用模式。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-pin-policy-settings.md"> (選用) 驗證 Lync Server 2013 中的 PIN 原則設定</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>設定會議原則以支援電話撥入式會議</strong></p></td>
<td><p>使用 Lync Server 2013 控制台或 Lync Server 管理命令介面來設定 <strong>會議原則</strong> 設定。 指定：</p>
<ul>
<li><p>已啟用 PSTN 會議撥入功能。</p></li>
<li><p>使用者可以邀請匿名參與者。</p></li>
<li><p>未驗證的使用者可以使用撥出 phoning 加入會議。 透過撥出 phoning，會議服務器呼叫使用者，而使用者接聽電話以加入會議。</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">在 Lync Server 2013 中設定電話撥入式會議原則</a></p></td>
</tr>
<tr class="even">
<td><p><strong>設定撥入存取號碼</strong></p></td>
<td><p>使用 Lync Server 2013 控制台或 Lync Server 管理命令介面來設定使用者撥打至會議的撥入存取號碼，並指定與適當撥號對應表相關聯之存取號碼的地區。 召集人的撥號對應表所指定之區域的前三個存取號碼會包含在會議邀請中。 [電話撥入式會議設定] 頁面上提供所有的存取號碼。</p>
<div>

> [!NOTE]  
> 建立撥入存取號碼之後，您可以使用 <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> Cmdlet 來修改 Active Directory 連絡人物件的顯示名稱，這樣使用者就能更輕鬆地識別正確的存取號碼。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">在 Lync Server 2013 中設定電話撥入式會議存取號碼</a></p></td>
</tr>
<tr class="odd">
<td><p><strong> (選用) 驗證電話撥入式會議設定</strong></p></td>
<td><p>使用 <strong>Get-CsDialinConferencingAccessNumber</strong> 指令程式來搜尋撥號對應表，其中含有未獲任何存取號碼及未指派任何區域之電話撥入式會議區域的撥號對應表。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p>
<p>CsHelpDesk</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md"> (選用) 驗證 Lync Server 2013 中的電話撥入式會議設定</a></p></td>
</tr>
<tr class="even">
<td><p><strong> (選用) Modify DTMF 命令的按鍵對應</strong></p></td>
<td><p>您可以使用 <strong>Set-CsDialinConferencingDtmfConfiguration</strong> Cmdlet，修改雙音訊式訊號 (DTMF) 命令所用的按鍵，以供參與者用來控制會議設定 (例如靜音和取消靜音或鎖定和解除鎖定) 。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md"> (選用) 在 Lync Server 2013 中修改 DTMF 命令的按鍵對應</a></p></td>
</tr>
<tr class="odd">
<td><p><strong> (選用) Modify 會議加入和離開宣告行為</strong></p></td>
<td><p>使用 <strong>Set-CsDialinConferencingConfiguration</strong> 變更參與者加入和離開會議時的宣告運作方式。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md"> (選用) 在 Lync Server 2013 中啟用和停用會議加入和離開宣告</a></p></td>
</tr>
<tr class="even">
<td><p><strong> (選用) 驗證電話撥入式會議</strong></p></td>
<td><p>使用 <strong>Test-CsDialInConferencing</strong> Cmdlet 來測試指定集區的存取號碼是否運作正常。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing.md"> (選用) 驗證 Lync Server 2013 中的電話撥入式會議</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>部署 Lync 2013 的線上會議增益集</strong></p></td>
<td><p>部署 Lync 2013 的線上會議增益集，讓使用者可以排程支援電話撥入式會議的會議。 當您安裝 Lync 2013 時，會自動安裝 Lync 2013 的線上會議增益集。</p></td>
<td><p>系統管理員</p></td>
<td><p><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">部署 Lync 2013 的線上會議增益集</a></p></td>
</tr>
<tr class="even">
<td><p><strong>設定使用者帳戶設定</strong></p></td>
<td><p>使用 Lync Server 2013 控制台或 Lync Server 管理命令介面，將電話語音列 <strong>URI</strong> 設定為唯一且正規化的電話號碼 (例如電話： + 14255550200) 。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsAdministrator</p>
<p>CsUserAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-user-account-settings.md">在 Lync Server 2013 中設定使用者帳戶設定</a></p></td>
</tr>
<tr class="odd">
<td><p> (建議) 設定會議目錄</p></td>
<td><p>使用 <strong>New-CsConferenceDirectory</strong> Cmdlet 為集區中的每個999使用者建立一個會議目錄。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013 中的電話撥入式會議需求</a> <a href="recommended-create-conference-directories.md"> (建議) 建立會議目錄</a></p></td>
</tr>
<tr class="even">
<td><p><strong> (選用) 歡迎使用者的電話撥入式會議和設定初始 PIN 碼</strong></p></td>
<td><p>使用 <strong>Set-CsPinSendCAWelcomeMail</strong> 腳本來設定使用者的初始 pin，並傳送包含初始 PIN 的歡迎使用電子郵件，以及電話撥入式會議設定頁面的連結。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md"> 在 Lync Server 2013 中 (選用) 歡迎使用者撥入式會議</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

