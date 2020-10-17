---
title: Lync Server 2013： Lync 2013 中的用戶端互通性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e00071edd4a3d65e9db763914577983306491fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502670"
---
# <a name="client-interoperability-in-lync-2013"></a>Lync 2013 中的用戶端互通性

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-03-04_

本主題討論 Microsoft Lync Server 2013 用戶端與舊版 Lync Server 和 Office 通訊伺服器上的用戶端共存及互動的能力。

<div>

## <a name="server-and-client-compatibility"></a>伺服器與用戶端相容性

下表顯示支援的用戶端版本和伺服器版本組合。 此表格指出當用戶端嘗試連線至指出的伺服器時，是否支援登入。 Lync Server 2013 支援舊版的用戶端版本。 此外，與舊版不同的是，Lync Server 2010 支援新的 Lync 2013 用戶端。 這可讓從 Lync Server 2010 升級的組織，將新的用戶端與 Lync Server 升級獨立。


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
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>支援</p></td>
<td><p>Supported5</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>支援</p></td>
<td><p>支援</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2013</p></td>
<td><p>支援</p></td>
<td><p>不支援</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>支援</p></td>
<td><p>支援</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendant</p></td>
<td><p>支援</p></td>
<td><p>支援</p></td>
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
<td><p>支援</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendee</p></td>
<td><p>非 Supported3</p></td>
<td><p>支援</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable4</p></td>
<td><p>支援</p></td>
<td><p>支援</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Office Communications Server 2007 R2 Attendant</p></td>
<td><p>不支援</p></td>
<td><p>支援</p></td>
<td><p>支援</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007</p></td>
<td><p>不支援</p></td>
<td><p>支援</p></td>
<td><p>支援</p></td>
</tr>
<tr class="even">
<td><p>Office Live Meeting 2007</p></td>
<td><p>不支援</p></td>
<td><p>支援</p></td>
<td><p>支援</p></td>
</tr>
<tr class="odd">
<td><p>Lync Windows Store 應用程式</p></td>
<td><p>支援</p></td>
<td><p>支援</p></td>
<td><p>不支援</p></td>
</tr>
</tbody>
</table>


1For 詳細資料，請參閱 [從 Lync server 2010，Group chat 或 Office 通訊伺服器 2007 R2 群組聊天至 Lync server 2013，Persistent Chat server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)。

2In Microsoft Lync Server 2010，群組聊天伺服器會提供群組聊天功能，這是 Lync Server 2010 的協力廠商信任應用程式。 Lync 2013 用戶端與 Lync Server 2010 （群組聊天）不相容。

3Lync Web App 2013 現在提供完整的會議體驗，包括電腦音訊和影片，且被視為 Lync 2010 出席者的取代。 只有當您使用不受支援的瀏覽器 (Internet Explorer 6 或 Internet Explorer 7) 與 Windows XP 時，lync 2010 出席者才會連線至 Lync Server 2013。

Office Communicator 2007 R2 中的4The 目前狀態和 IM 功能與 Lync Server 2013 相容，但會議功能卻不相容。 從 Office 通訊伺服器 2007 R2 進行遷移時，Office Communicator 2007 R2 適用于目前狀態和 IM 互通性，但是使用者應使用 Lync Web App 2013 加入 Lync Server 的 [2013] 會議。

5如需限制，請參閱本主題稍後的「Lync Server 2010 會議中2013的 ' 會議功能支援」。

</div>

<div>

## <a name="interoperability-among-clients"></a>用戶端間的互通性

在 Lync Server 2013 版本中，各種用戶端版本可以在對等與會議案例中順利互動。 本節討論使用者與其他使用不同版本用戶端和伺服器的使用者進行互動時的功能可用性。

<div>

## <a name="peer-to-peer-feature-support"></a>Peer-to-Peer 功能支援

對等功能可支援位於不同伺服器版本的使用者，以及使用不同用戶端版本的使用者。 使用者經驗和可用的功能，與使用者的用戶端功能和使用者登入之伺服器的版本一致。 換句話說：

  - 若使用者已使用舊版用戶端登入 Lync Server 2013，使用者就會使用自己的經驗。 在升級使用者的用戶端之前，不會提供 Lync Server 2013 中引入的任何新功能。 範例包括影片庫視圖、HD 影片、更新 PowerPoint 共用，以及在會議輸入時靜音所有出席者音訊和影片的選項。 [Lync server 2013 中的新會議功能](lync-server-2013-new-conferencing-features.md)會列出新功能，以及[lync server 2013 中用戶端的新](lync-server-2013-what-s-new-for-clients.md)功能。

  - 如果使用者登入 Lync Server 2010 與 Lync 2013 用戶端，則在使用者移至 Lync Server 2013 之前，Lync Server 2010 不支援的任何新功能將無法使用。

下表比較用戶端登入 Lync Server 2013 或 Lync Server 2010 的點對點工作階段中的功能可用性。

<div>


> [!NOTE]  
> Lync Web App 和 Lync 2010 出席者是僅供會議的用戶端，不會包含在此表格中。



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
<th>影片</th>
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
<td><p>Lync 2013 Basic</p></td>
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
<td><p>Lync 2010 Attendant</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Mobile</p></td>
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
<td><p>公用 IM (AOL，Yahoo！ ) </p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>公用 IM (MSN、Windows Live Messenger) </p></td>
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
> <P>從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 (PIC USL) 已不再提供購買新的或更新的協定。 具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟 信使直到服務關閉日期。 AOL 和 Yahoo！的循環結束日期為2014年6月 已宣告。 如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的每一使用者、每月訂閱授權。 信使。 Microsoft 提供此服務的能力已因 Yahoo！的支援而產生，不會更新的基準合約。</P>
> <LI>
> <P>Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。 與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。 隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以透過 IM 和語音來抵達數百個人的人員。</P></LI></UL>



</div>

1在 Office Communicator 2007 R2 中，僅有桌面共用 (與程式共用) 皆可供使用。

<div>


> [!NOTE]  
> 當商務用 Skype 2015 用戶端使用者介面強制執行時，Office Communicator 2007 R2 和商務用 Skype 2015 之間的桌面共用無法從較新的用戶端啟動。



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a>Lync Server 2010 會議中 Lync 2013 用戶端的會議功能支援

當使用者使用 Lync 2013 用戶端加入 Lync Server 2010 會議時，他們可以存取 Lync 2013 用戶端功能，但有下列例外：

  - 在 [ **參與者** 管理] 選項中，透過指向會議視窗中的 [人員] 圖示可供存取，[ **無會議 IM** ] 選項不會正常運作。

  - 圖庫 View 在影片會議中無法運作。 使用者只會看到使用中的音箱，而不是所有的揚聲器。 在 [ **選擇版面** 配置選項] 清單中，無法使用 **圖庫 View** 功能

  - 在 [影片會議] 中，預設會顯示參與者清單。

  - 以滑鼠右鍵按一下參與者清單中的使用者時，會無法使用 [影片] [影片] 和 [**固定至圖庫**]**的 [工作**表參與者管理] 選項。

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a>Lync Server 2013 會議中的會議功能支援

Lync Server 2013 提供新的會議功能，當使用者的帳戶移至 Lync Server 2013 並以 Lync 2013 用戶端登入時，這些功能就可供使用者使用。 範例包括影片庫視圖、HD 影片、PowerPoint 共用，以及在會議輸入時靜音所有出席者音訊和影片的選項。 [Lync server 2013 中的新會議功能](lync-server-2013-new-conferencing-features.md)會列出新功能，以及[lync server 2013 中用戶端的新](lync-server-2013-what-s-new-for-clients.md)功能。

在 Lync Server 2013 會議中，特定的會議功能可供位於不同伺服器版本的使用者和使用不同用戶端和用戶端版本的使用者使用。 當用戶端加入 Lync Server 2013 會議時，使用者可以存取此表格中所示的功能和功能。


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
<th>影片</th>
<th>應用程式共用</th>
<th>PowerPoint</th>
<th>檔案傳輸</th>
<th>Whiteboard</th>
<th>輪詢</th>
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
<td><p>Lync 2013 Basic</p></td>
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
<td><p>是3</p></td>
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


1在 Office Communicator 2007 R2 中，僅有桌面共用 (與程式共用) 皆可供使用。

2 Lync Server 2013 使用更新的機制來上傳 PowerPoint 檔案。 加入最初排定在 Lync Server 2010 上之會議的 Lync Web App 使用者可以查看和流覽 PowerPoint 簡報，但無法上傳 PowerPoint 檔案。

3如果會議已排定在 Lync Server 2013 上，且 PowerPoint 的投影片是由 Lync 2013 用戶端上傳，則 Lync 2010 使用者可以查看投影片的許可權。 相反地，如果 Lync 2010 使用者上傳 PowerPoint 投影片，Lync Server 2013 使用者將可以查看和投影片，如果已設定 Office Web Apps Server，就會存取新的功能，例如更高的解析度顯示、動畫、投影片切換效果及內嵌的影片。 如需詳細資訊，請參閱設定 [Office Web Apps Server 和 Lync server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

Office Communicator 2007 R2 中的4The 目前狀態和 IM 功能與 Lync Server 2013 相容，但會議功能卻不相容。 從 Office 通訊伺服器 2007 R2 進行遷移時，Office Communicator 2007 R2 適用于目前狀態和 IM 互通性，但是使用者應使用 Lync Web App 2013 加入 Lync Server 的 [2013] 會議。

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a>排程增益集支援

不同排程增益集的伺服器支援與伺服器及用戶端版本相容性一致。 一般來說，Lync Server 2013 上支援下列排程增益集。 不過，舊版的增益集不會提供新的 Lync 2013 增益集功能，例如，將所有出席者的音訊和影片輸入到會議輸入時的選項。

  - **Lync 2013**     的線上會議增益集提供與 Lync 2010 的線上會議增益集相同的功能，加入出席者的靜音控制項，讓會議召集人可以排定預設會靜音和影片的會議。 管理員也可以新增自訂標誌、支援 URL、法律免責聲明 URL 或自訂頁腳文字，以自訂群組織的會議邀請。

  - **Lync 2010**     的線上會議增益集提供 Lync 會議的排程，並移除安排 Office Live Meeting 會議的功能。

  - **Office Communicator 2007 R2 會議增益集**    提供 Office Live Meeting 會議和 Office Communicator 2007 R2 會議的排程。 

<div>


> [!NOTE]  
> 無法在 Lync Server 2013 上排定 Live Meeting 會議。



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
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013 (的線上會議增益集可以搭配 Office 2013、Outlook 2010 和 Outlook 2007) 使用</p></td>
<td><p>支援</p></td>
<td><p>支援 (無法使用的新增益集功能) </p></td>
<td><p>不支援</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Web 排程器</p></td>
<td><p>支援</p></td>
<td><p>不支援</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 線上會議增益集</p></td>
<td><p>支援</p></td>
<td><p>支援</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2 會議增益集</p></td>
<td><p>不支援</p></td>
<td><p>支援</p></td>
<td><p>支援</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a>加入會議的支援

所有 Lync Server 2013 支援的用戶端都可以加入 Lync 2013 會議。 因為 Lync Web App 是伺服器的網頁元件，所以在使用 Lync Web App 來加入 Lync Server 2013 會議時，永遠會使用較新版本的 Lync Web App。

Lync 2013 用戶端可以加入以向外擴充功能之 Lync 2010 和 Office 通訊伺服器 2007 R2 主控的會議。 「會議中功能」是由主控會議所在的伺服器版本所限制。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 的 lync Windows 應用程式需求](lync-server-2013-lync-windows-store-app-requirements.md)  
[Lync Server 2013 中的新會議功能](lync-server-2013-new-conferencing-features.md)  
[Lync Server 2013 中用戶端的新功能](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

