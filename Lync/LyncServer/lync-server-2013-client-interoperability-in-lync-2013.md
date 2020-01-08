---
title: Lync Server 2013：Lync 2013 中的用戶端互通性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8ccc6239ffa0216e36839a7e58b510d8c8c3240
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a>Lync 2013 中的用戶端互通性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-03-04_

本主題討論 Microsoft Lync Server 2013 用戶端與舊版 Lync Server 和 Office 通訊伺服器之間的共存與用戶端互動的能力。

<div>

## <a name="server-and-client-compatibility"></a>伺服器與用戶端相容性

下表顯示用戶端版本和伺服器版本支援的組合。 此表格指示用戶端嘗試連線至所指示的伺服器時，是否支援登入。 Lync Server 2013 支援舊版的用戶端版本。 此外，Lync Server 2010 支援新的 Lync 2013 用戶端，也與舊版版本不同。 這可讓從 Lync Server 2010 升級的組織在獨立于 Lync Server 升級的情況下，推出新的用戶端。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>用戶端</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office 通訊伺服器 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>受</p></td>
<td><p>Supported5</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 基本版</p></td>
<td><p>受</p></td>
<td><p>受</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2013</p></td>
<td><p>受</p></td>
<td><p>不支援</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>受</p></td>
<td><p>受</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 助理</p></td>
<td><p>受</p></td>
<td><p>受</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 群組聊天</p></td>
<td><p>Supported1</p></td>
<td><p>Supported2</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2010</p></td>
<td><p>不支援</p></td>
<td><p>受</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 出席者</p></td>
<td><p>無法 Supported3</p></td>
<td><p>受</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable4</p></td>
<td><p>受</p></td>
<td><p>受</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Office 通訊伺服器 2007 R2 助理</p></td>
<td><p>不支援</p></td>
<td><p>受</p></td>
<td><p>受</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007</p></td>
<td><p>不支援</p></td>
<td><p>受</p></td>
<td><p>受</p></td>
</tr>
<tr class="even">
<td><p>Office Live Meeting 2007</p></td>
<td><p>不支援</p></td>
<td><p>受</p></td>
<td><p>受</p></td>
</tr>
<tr class="odd">
<td><p>Lync Windows Store 應用程式</p></td>
<td><p>受</p></td>
<td><p>受</p></td>
<td><p>不支援</p></td>
</tr>
</tbody>
</table>


1For 詳細資料，請參閱[從 Lync server 2010 遷移、群組聊天或 Office 通訊伺服器 2007 R2 群組聊天至 Lync server 2013、持續聊天伺服器](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)。

2In Microsoft Lync Server 2010，您可以在群組聊天伺服器（即 Lync Server 2010 的協力廠商信任應用程式）中使用群組聊天功能。 Lync 2013 用戶端與 Lync Server 2010 （群組聊天）不相容。

3Lync Web App 2013 現在提供完整的會議體驗，包括電腦音訊和影片，並被視為 Lync 2010 出席者的取代。 只有當您使用不受支援的瀏覽器（Internet Explorer 6 或 Internet Explorer 7）與 Windows XP 時，lync 2010 出席者才會連線至 Lync Server 2013。

Office Communicator 2007 R2 中的4The 目前狀態與 IM 功能與 Lync Server 2013 相容，但會議功能不相容。 從 Office 通訊伺服器 2007 R2 遷移期間，Office Communicator 2007 R2 適用于目前狀態與 IM 互通性，但使用者應該使用 Lync Web App 2013 來加入 Lync Server 2013 會議。

5如需限制，請參閱本主題稍後的「Lync Server 2010 會議中的 Lync 2013 用戶端的會議功能支援」。

</div>

<div>

## <a name="interoperability-among-clients"></a>用戶端之間的互通性

在 Lync Server 2013 版本中，各種用戶端版本都可以在對等與會議案例中順利互動。 本節討論使用者與其他使用不同版本用戶端和伺服器的使用者互動時的功能可用性。

<div>

## <a name="peer-to-peer-feature-support"></a>對等功能支援

針對駐留在不同版本伺服器的使用者，以及使用不同用戶端版本的使用者，都支援對等功能。 最終使用者體驗和可用功能與使用者用戶端的功能和使用者登入的伺服器版本相符。 換句話說：

  - 如果使用者是使用舊版用戶端登入 Lync Server 2013，使用者就會使用自己的體驗。 只有在使用者的用戶端升級之後，才能使用 Lync Server 2013 中引入的任何新功能。 範例包括影片庫視圖、HD 影片、更新的 PowerPoint 共用，以及在會議進入時將所有出席者的音訊和影片設為靜音的選項。 新功能在[Lync server 2013 的新會議功能](lync-server-2013-new-conferencing-features.md)中有說明，以及[lync server 2013 中用戶端的新](lync-server-2013-what-s-new-for-clients.md)功能。

  - 如果使用者是使用 Lync 2013 用戶端登入 Lync Server 2010，則 Lync Server 2010 不支援的任何新功能都將無法使用，除非使用者移至 Lync Server 2013。

下表將用戶端登入 Lync Server 2013 或 Lync Server 2010 的點對點工作階段中的功能可用性進行比較。

<div>


> [!NOTE]  
> Lync Web App 和 Lync 2010 出席者是僅適用于會議的客戶，不會包含在此表格中。



</div>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>用戶端</th>
<th>立即訊息</th>
<th>目前狀態</th>
<th>語音</th>
<th>顯示器</th>
<th>應用程式共用</th>
<th>檔案傳輸</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 基本版</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 助理</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 行動裝置</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是1</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>公用 IM （AOL、Yahoo！）</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>公用 IM （MSN、Windows Live Messenger）</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（PIC USL）已不再提供購買新或續約協定的功能。 擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟 信使，直到服務關閉日期為止。 AOL 和 Yahoo！的存留期結束日期為2014年6月 已公佈。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟所需的每個使用者、每月訂閱授權 名單. Microsoft 提供此服務的能力已因 Yahoo！的支援而定，不會更新的底層合約。</P>
> <LI>
> <P>Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。 與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。 Skype 同盟將會新增到此清單，讓 Lync 使用者能夠透過 IM 和語音來取得成百上千的人員。</P></LI></UL>



</div>

1在 Office Communicator 2007 R2 中，只能使用 [桌面共用] （而非 [程式共用]）。

<div>


> [!NOTE]  
> 在強制執行商務用 Skype 2015 用戶端使用者介面時，無法從較新的用戶端啟動 Office Communicator 2007 R2 與商務用 Skype 2015 之間的桌面共用。



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a>Lync Server 2010 會議中 Lync 2013 用戶端的會議功能支援

當使用者使用 Lync 2013 用戶端加入 Lync Server 2010 會議時，他們可以使用下列例外狀況來存取 Lync 2013 用戶端功能：

  - 在**參與者**管理選項（可透過指向會議視窗中的 [人員] 圖示來存取），[**無會議 IM** ] 選項不起作用。

  - [圖庫] 視圖在視訊會議中不起作用。 使用者只會看到現用喇叭，而不是所有喇叭。 在 [**挑選版面**配置選項] 清單中，[**庫視圖**] 無法使用

  - 「參與者清單」預設會顯示在 [視訊會議] 中。

  - 在參與者清單中以滑鼠右鍵按一下使用者時，無法使用 [**鎖定影片焦點**] 和 [**釘選到圖庫**] 參與者管理選項。

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a>Lync Server 2013 會議中的會議功能支援

Lync Server 2013 提供新的會議功能，在使用者的帳戶移至 Lync Server 2013 並以 Lync 2013 用戶端登入之後，使用者就能使用。 範例包括影片庫視圖、HD 影片、PowerPoint 共用，以及在會議進入時將所有出席者的音訊和影片設為靜音的選項。 新功能在[Lync server 2013 的新會議功能](lync-server-2013-new-conferencing-features.md)中有說明，以及[lync server 2013 中用戶端的新](lync-server-2013-what-s-new-for-clients.md)功能。

在 Lync Server 2013 會議中，對於駐留在不同版本伺服器的使用者，以及使用不同用戶端和用戶端版本的使用者，都支援某些會議功能。 當用戶端加入 Lync Server 2013 會議時，使用者可以使用下表所示的功能和功能。


<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th>用戶端</th>
<th>對等 IM</th>
<th>語音</th>
<th>顯示器</th>
<th>應用程式共用</th>
<th>PowerPoint</th>
<th>檔案傳輸</th>
<th>Whiteboard</th>
<th>投票</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 基本版</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是2</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>Yes3</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2 4</p></td>
<td><p>是</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


1在 Office Communicator 2007 R2 中，只能使用 [桌面共用] （而非 [程式共用]）。

2 Lync Server 2013 使用更新的機制來上傳 PowerPoint 檔案。 加入原先在 Lync Server 2010 上排程之會議的 Lync Web App 使用者可以查看並流覽 PowerPoint 簡報，但無法上傳 PowerPoint 檔案。

3如果會議是在 Lync Server 2013 上排程，且由 Lync 2013 用戶端上傳 PowerPoint 投影片，Lync 2010 使用者只能透過查看方式存取投影片。 相反地，如果您是由 Lync 2010 使用者上傳 PowerPoint 投影片，Lync Server 2013 使用者將能夠查看和投影片，而且如果已設定 Office Web Apps 伺服器，也能存取新功能，例如解析度顯示、動畫、投影片切換效果，以及內嵌的影片。 如需詳細資訊，請參閱設定[與 Office Web Apps server 和 Lync server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

Office Communicator 2007 R2 中的4The 目前狀態與 IM 功能與 Lync Server 2013 相容，但會議功能不相容。 從 Office 通訊伺服器 2007 R2 遷移期間，Office Communicator 2007 R2 適用于目前狀態與 IM 互通性，但使用者應該使用 Lync Web App 2013 來加入 Lync Server 2013 會議。

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a>排程增益集支援

針對各種排程增益集的伺服器支援，與伺服器和用戶端版本相容性一致。 一般來說，Lync Server 2013 支援下列排程增益集。 不過，先前的增益集版本不會提供新的 Lync 2013 增益集功能，例如，將所有出席者的音訊和會議專案設為靜音時的選項。

  - **Lync 2013**   的線上會議增益集提供與 lync 2010 的線上會議增益集相同的功能，以及新增出席者靜音控制項，讓會議召集人預設會將出席者音訊和影片設為靜音的會議。 系統管理員也可以新增自訂標誌、支援 URL、合法免責聲明 URL 或自訂的頁尾文字，來自訂群組織的會議邀請。

  - **Lync 2010**   的線上會議增益集可為 lync 會議提供排程，並移除安排 Office Live Meeting 會議的功能。

  - **Office Communicator 2007 R2 會議增益集**   可為 office Live Meeting 會議與 office Communicator 2007 R2 會議提供排程。 

<div>


> [!NOTE]  
> 在 Lync Server 2013 上無法排程 Live Meeting 會議。



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
<th>排程用戶端</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office 通訊伺服器 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013 的線上會議增益集（可與 Office 2013、Outlook 2010 和 Outlook 2007 搭配使用）</p></td>
<td><p>受</p></td>
<td><p>支援（沒有可用的新增益集功能）</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Web 排程程式</p></td>
<td><p>受</p></td>
<td><p>不支援</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 的線上會議增益集</p></td>
<td><p>受</p></td>
<td><p>受</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2 會議增益集</p></td>
<td><p>不支援</p></td>
<td><p>受</p></td>
<td><p>受</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a>加入會議的支援

Lync Server 2013 支援的所有用戶端都可以加入 Lync 2013 會議。 因為 Lync Web App 是伺服器的網頁元件，所以在使用 Lync Web App 來加入 Lync Server 2013 會議的情況下，會一直使用較新版本的 Lync Web App。

Lync 2013 用戶端可以加入在 Lync 2010 和 Office 通訊伺服器 2007 R2 中託管的會議，並提供上下伸縮功能。 [會議中的功能] 是由託管會議的伺服器版本所限制。

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 的 lync Windows Store 應用程式需求](lync-server-2013-lync-windows-store-app-requirements.md)  
[Lync Server 2013 中的新會議功能](lync-server-2013-new-conferencing-features.md)  
[Lync Server 2013 中的用戶端最新訊息](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

