---
title: Lync Server 2013： Lync 2013 相容性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync 2013 compatibility
ms:assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412817(v=OCS.15)
ms:contentKeyID: 51541502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e177003efb73cd1e16ae8fd772d579eb222af8bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-2013-compatibility"></a>Lync 2013 相容性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

本節說明 Lync 2013 與各種版本的 Microsoft Office 套件、Microsoft Exchange Server、Windows 作業系統及選取的公用立即訊息（IM）用戶端的相容性。

<div>

## <a name="office-and-lync-2013"></a>Office 和 Lync 2013

下表說明各種 Office 版本支援的 Lync 2013 功能。

### <a name="lync-2013-and-microsoft-office-compatibility"></a>Lync 2013 和 Microsoft Office 相容性

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
<th>功能</th>
<th>Microsoft Office 2003 Service Pack 3 （SP3）（必要）或最新版 service pack （建議使用）</th>
<th>Microsoft Office 2007</th>
<th>Microsoft Office 2010</th>
<th>Microsoft Office 2013</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>自訂 Outlook 會議邀請（新增標誌、說明 URL、免責聲明、頁尾文字）</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>在 Outlook 中，[設定會議] 選項預設會將出席者的音訊和影片設為靜音</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>在 Office 和 Lync 中管理連絡人清單的整合連絡人存放區</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是（需要 Exchange 2013）1</p></td>
</tr>
<tr class="even">
<td><p>高解析度圖片</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是（需要 Exchange 2013）1</p></td>
</tr>
<tr class="odd">
<td><p>與 Office 安裝程式整合的 Lync 2013 設定</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>OneNote 共用筆記</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>PowerPoint 簡報內容</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Outlook [收件者] 和 [抄送] 欄位中的目前狀態</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>從 [可用性] 功能表回復會議通話</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>[是] （從連絡人卡片）</p></td>
<td><p>[是] （從連絡人卡片）</p></td>
</tr>
<tr class="even">
<td><p>[排程小幫手] 索引標籤上會議邀請中的目前狀態</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>在收到的電子郵件訊息中使用 IM 回復，或從工具列或功能區通話</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>Outlook [寄件者] 欄位中的目前狀態</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>從 [IM] 或 [從可用語音] 功能表回復</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>[是] （從連絡人卡片）</p></td>
<td><p>[是] （從連絡人卡片）</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Word 和 Microsoft Excel 檔案中的 IM 和目前狀態（啟用智慧標籤）</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>僅限 Microsoft Word</p></td>
<td><p>僅限 Microsoft Word</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft SharePoint 網站中的 IM 和目前狀態（必須安裝 Outlook）</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
</tbody>
</table>


1如需詳細資訊，請參閱在規劃檔中[整合 Microsoft Lync server 2013 與 Microsoft Exchange Server 2013](lync-server-2013-integrating-with-microsoft-exchange-server-2013.md) 。

下列功能僅適用于 Office 2010 或 Office 2013：

  - 含展開選項的連絡人卡片，例如視頻通話和桌面共用

  - 從 Outlook 中的 [尋找連絡人] 欄位快速搜尋

  - 使用 [郵件]、[行事曆]、[連絡人] 和 [工作] 資料夾中的 Outlook [常用] 功能區中的 IM 或通話回復

  - [我的 Outlook 待辦事項列] 中的 Lync 連絡人清單

  - Office Backstage （[檔案] 索引標籤）目前狀態、程式共用和檔案傳輸

  - Microsoft Office SharePoint Workspace 2010 （舊稱 Microsoft Office Groove 2007）中的 [目前狀態] 功能表

  - 目前狀態功能表擴充性

</div>

<div>

## <a name="exchange-server-and-lync-2013"></a>Exchange Server 和 Lync 2013

下表說明各種 Exchange Server 版本的 Lync 2013 支援。 Outlook 必須安裝在用戶端電腦上，才能處理延伸的 MAPI 呼叫，而某些功能則需要使用 Exchange Web 服務（EWS）。

### <a name="lync-2013-and-exchange-server-compatibility"></a>Lync 2013 與 Exchange Server 相容性

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Exchange Server 版本</th>
<th>Lync 2013 支援</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Exchange Server 2013</p></td>
<td><p>與 Exchange Server 2010 支援相同，其中加入了整合連絡人存放區、高解析度的圖片，以及歸檔整合。</p>
<div>

> [!NOTE]  
> 如需詳細資訊，請參閱<A href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">整合 Microsoft Lync server 2013 和 Microsoft Exchange Server 2013</A>。


</div></td>
</tr>
<tr class="even">
<td><p>Exchange Server 2010</p></td>
<td><p>與 Exchange Server 2007 支援相同，但新增 Exchange 連絡人同步處理。</p></td>
</tr>
<tr class="odd">
<td><p>Exchange Server 2007 Service Pack 1 （SP1）（必要）或最新的 service pack （建議使用）</p></td>
<td><p>下列功能只能透過 EWS 使用：</p>
<ul>
<li><p>讀取或刪除 [交談記錄] 資料夾中的專案</p></li>
<li><p>讀取或刪除語音信箱專案</p></li>
<li><p>顯示延伸的空閒/忙碌資訊及會議主旨和位置</p></li>
</ul>
<p>公用資料夾是 Exchange Server 2007 中的選擇性，包括 Service Pack 1 （SP1）（必要），或是最新的 service pack 或版本（建議使用）。</p></td>
</tr>
<tr class="even">
<td><p>Exchange Server 2003</p></td>
<td><p>僅限 Outlook MAPI。 只提供 EWS 功能（請參閱上一列）。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="windows-and-lync-2013"></a>Windows 和 Lync 2013

如需 Lync 2013 和 Windows 支援服務的相關資訊，請參閱規劃檔中[Lync Server 2013 中的 lync 用戶端軟體支援](lync-server-2013-lync-client-software-support.md)。

</div>

<div>

## <a name="macintosh-and-lync-2013"></a>Macintosh 和 Lync 2013

Lync Server 2013 支援運行 Macintosh 作業系統之電腦上的特定用戶端。 如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的 lync 用戶端軟體支援](lync-server-2013-lync-client-software-support.md)。

</div>

<div>

## <a name="public-instant-messaging-clients-and-lync-2013"></a>公用立即訊息用戶端和 Lync 2013

如果您已將伺服器設定為公用 IM 連線，Lync 支援使用公用 IM 網路的下列功能。 [目前狀態] 會篩選為公用 IM 用戶端支援的那些目前狀態。 如需詳細資訊，請參閱在[Lync server 2013 規劃中的公用立即訊息](lync-server-2013-planning-for-public-instant-messaging-connectivity.md)連線在作業檔中的 [規劃檔] 和 [[管理 lync server 2013 中的外部存取原則](lync-server-2013-manage-external-access-policy-for-your-organization.md)]。

此外，Lync Server 2013 的 XMPP 整合功能可讓使用者與公用 IM 提供者的使用者交換立即訊息和目前狀態資訊，例如 Google 交談。 如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的可擴展訊息和目前狀態通訊協定（XMPP）同盟](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)。

### <a name="lync-2013-and-public-im-clients-compatibility"></a>Lync 2013 和公用 IM 用戶端相容性

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>用戶端</th>
<th>支援的功能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Live Messenger</p></td>
<td><p>IM、基本目前狀態、音訊/視頻（A/V） *</p></td>
</tr>
<tr class="even">
<td><p>Skype</p></td>
<td><p>IM、基本目前狀態、音訊</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>IM 與基本狀態</p></td>
</tr>
<tr class="even">
<td><p>Yahoo</p></td>
<td><p>IM 與基本狀態</p></td>
</tr>
<tr class="odd">
<td><p>Google 交談</p></td>
<td><p>IM 與基本狀態</p></td>
</tr>
</tbody>
</table>


\*最新版本的 Windows Live Messenger 支援 A/V。 如果您是使用 Windows Live Messenger 來實現音訊/視頻（A/V）同盟，您也必須修改伺服器加密層級。 根據預設，加密層級是必要的。 您必須使用 Lync Server 管理命令介面將此設定變更為 [支援]。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。 擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟 信使，直到服務關閉日期為止。 AOL 和 Yahoo！的存留期結束日期為2014年6月 已公佈。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權 名單. Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</P>
> <LI>
> <P>Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。 與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。</P></LI></UL>



</div>

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync 2013 中的用戶端互通性](lync-server-2013-client-interoperability-in-lync-2013.md)  
[Lync Server 2013 中的 lync 用戶端軟體支援](lync-server-2013-lync-client-software-support.md)  
[Lync Web App 支援的 Lync Server 2013 平臺](lync-server-2013-lync-web-app-supported-platforms.md)  
[Lync Server 2013 的 lync Windows Store 應用程式需求](lync-server-2013-lync-windows-store-app-requirements.md)  


[Lync Server 2013 的用戶端系統需求](lync-server-2013-client-system-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

