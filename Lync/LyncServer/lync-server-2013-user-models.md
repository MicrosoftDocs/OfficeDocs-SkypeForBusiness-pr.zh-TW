---
title: Lync Server 2013：使用者模型
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 user models
ms:assetid: c551371c-d740-4372-bada-f0d713ec0d33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398811(v=OCS.15)
ms:contentKeyID: 49733811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8185fc2fdb92f907eb013349b8a202df2b7b62bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-models-in-lync-server-2013"></a>Lync Server 2013 中的使用者模型

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

此處所述的使用者模型提供[使用使用者模型的 Lync Server 2013 容量規劃](lync-server-2013-capacity-planning-using-the-user-models.md)中所述的容量規劃測量與建議的基礎。

<div>

## <a name="lync-server-2013-user-models"></a>Lync Server 2013 使用者模型

下表說明 Lync Server 2013 註冊、連絡人、立即訊息（IM）和目前狀態的使用者模型。

### <a name="environment-and-registration-user-model"></a>環境與註冊使用者模型

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>類別</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>部署大小與發佈</p></td>
<td><p>我們會針對具有三個中心網站的大型部署建模，每個網站都有一個前端池。</p></td>
</tr>
<tr class="even">
<td><p>Active Directory 使用者的百分比</p></td>
<td><p>我們假設組織中所有 Active Directory 使用者的70% 都已啟用 Lync Server。 80% 的使用者每天都會登入 Lync Server （80% concurrency）。 併發使用者是本節其餘部分中的數位的基礎。</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory 變更</p></td>
<td><p>我們假設每週為 Active Directory 中的 Lync 建立並啟用總使用者數的0.5%，而使用者每週從 Active Directory 和 Lync 停用總使用者數的0.5%。 5% 的使用者每週至少有一個 Active Directory 屬性已變更。</p></td>
</tr>
<tr class="even">
<td><p>Active Directory 通訊群組</p></td>
<td><p>我們假設組織中的 Active Directory 通訊群組數目等於 Active Directory 中所有使用者數的三倍。 通訊群組具有下列大小：</p>
<ul>
<li><p>64% 有2-30 使用者</p></li>
<li><p>13% 有31-50 使用者</p></li>
<li><p>10% 有51-100 使用者</p></li>
<li><p>13% 有101-500 使用者</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>[語音 over IP （VoIP）] 使用者</p></td>
<td><p>60% 的 Lync Server 使用者已啟用整合通訊（UC）（也就是他們的電話號碼是由 Lync Server 所擁有）。</p></td>
</tr>
<tr class="even">
<td><p>已註冊的用戶端分配</p></td>
<td><p>65% 的用戶端執行 Lync 2013 軟體，包括 Lync 和 Lync Phone Edition。</p>
<p>從舊版 Lync 執行用戶端軟體之客戶的30%。</p>
<p>5% 的用戶端使用 Lync Web App。</p>
<p>如果行動已啟用，我們會假設40% 的使用者正在與其他先前提及的註冊用戶端選項同時使用行動。 在這種情況下，用戶端的多重狀態點（MPOP）比率為1：1.9。 如果行動已停用，則 MPOP 比率為1：1.5。</p></td>
</tr>
<tr class="odd">
<td><p>遠端使用者發佈</p></td>
<td><p>內部連接的使用者70%。</p>
<p>透過邊緣伺服器和主管連線的使用者的30%。</p></td>
</tr>
<tr class="even">
<td><p>連絡人分配</p></td>
<td><p>使用者擁有的連絡人數目上限為1000。 少於1% 的使用者有1000連絡人。 少於25% 的使用者有100或更多連絡人。</p>
<p>使用公用雲端連線的使用者的80連絡人平均值。 下列使用者：</p>
<ul>
<li><p>50% 的連絡人都在組織內。 這些使用者的10% 是遠端使用者，從防火牆外部連線。</p></li>
<li><p>40% 的連絡人是公用雲端使用者（例如 AOL、Yahoo！、MSN 或 Google 交談的使用者）。</p></li>
<li><p>連絡人的10% 是來自聯盟合作夥伴。</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。 擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟 信使，直到服務關閉日期為止。 AOL 和 Yahoo！的存留期結束日期為2014年6月 已公佈。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權 名單. Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</P>
> <LI>
> <P>Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。 與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。 您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</P></LI></UL>


</div></li>
</ul>
<p>不含公用雲端連線的使用者的50連絡人平均值。 下列使用者：</p>
<ul>
<li><p>80% 的連絡人都在組織內。 這些使用者的10% 是遠端使用者，從防火牆外部連線。</p></li>
<li><p>此連絡人的20% 是來自聯盟合作夥伴。</p>
<p>每個使用者的連絡人清單中都有一個通訊群組。 針對效能測試，我們假設通訊群組總是展開。</p></li>
</ul>
<p>使用者的連絡人的25% 使用 XMPP。</p></td>
</tr>
<tr class="odd">
<td><p>會話時間</p></td>
<td><p>一般的使用者登入會話持續12小時。 所有使用者都會在會話開始的120分鐘內登入。</p></td>
</tr>
</tbody>
</table>


### <a name="im-and-presence-user-model"></a>IM 和目前狀態使用者模型

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>類別</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>對等 IM 會話</p></td>
<td><p>每個使用者每天平均六個對等 IM 會話。</p>
<p>每個會話10個即時消息。</p>
<p>每封郵件都是由兩個 SIP 資訊訊息和2個 SIP 200 的 [確定] 訊息（例如&lt;"&gt; Name is Name" 之類的狀態指標）來相符。</p></td>
</tr>
<tr class="even">
<td><p>目前狀態輪詢</p></td>
<td><p>總的來說，我們假設每個使用者每小時的目前狀態輪詢平均為60輪詢。 針對每個使用者，假設平均值：</p>
<ul>
<li><p>在使用者的 [組織] 索引標籤（但不是 [連絡人] 清單）中，每一天輪詢一天。 在使用者的 [組織] 索引標籤中，第15位使用者的非連絡人平均數。 每日兩個連絡人卡片查看作業。</p></li>
<li><p>每次使用者按一下另一個使用者以開始交談時，每小時估計一次，即會有一個目前狀態輪詢。</p></li>
<li><p>每小時六個使用者搜尋。 每次執行搜尋時，都會針對搜尋結果清單中的每個人傳送批次投票。 我們假設搜尋結果的平均大小為20。 如果搜尋結果停留在螢幕上，批次輪詢會每隔5分鐘更新一次;我們假設每小時會有兩個此類更新。</p></li>
<li><p>當使用者在 Outlook 中開啟或預覽電子郵件時，會在電子郵件的 [收件者：] 和 [抄送：] 欄位中的目前狀態，在每個電子郵件上估計5封電子郵件，以及每個電子郵件的四個使用者。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>目前狀態訂閱</p></td>
<td><p>當使用者將另一個使用者新增為連絡人時，第一個使用者會<em>訂閱</em>五個有關第二個使用者的資訊類別。 這些資訊類別的更新會自動傳送給第一個使用者。</p>
<p>針對每個用戶端，會傳送單一批次訂閱要求，以取得平均40連絡人的目前狀態，還有額外的40對話方塊來取得同盟連絡人的目前狀態。</p>
<p>展開的通訊群組成員的「目前狀態」是透過持久的目前狀態訂閱（不是輪詢）找到，且每個使用者每兩個小時都是以1個延伸的方式進行。</p>
<p><em>較短的訂閱</em>會在使用者登入時發生，所有使用者的連絡人都有一個批次訂閱，然後使用者就會立即登入。 我們假設每個使用者的每小時只有6個短訂閱，每個訂閱的持續時間為10分鐘。</p></td>
</tr>
<tr class="even">
<td><p>目前狀態發佈</p></td>
<td><p>[目前狀態] 是以每個使用者每小時4個發佈的平均發佈，每個使用者最多每小時6份。</p></td>
</tr>
<tr class="odd">
<td><p>目前狀態檔案大小</p></td>
<td><p>完整目前狀態檔的平均大小假設是4K，且最大25K。</p></td>
</tr>
</tbody>
</table>


下表說明通訊錄使用的使用者模型。

### <a name="address-book-usage-user-model"></a>[通訊錄使用方式] 使用者模型

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>通訊錄搜尋模式</th>
<th>用法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>[通訊錄網頁查詢] （由通訊錄網頁查詢服務所執行的所有查詢）</p></td>
<td><p>每位使用者一天四個首碼查詢。</p>
<p>60每位使用者每天精確搜尋查詢。 其中的40% 是批次，平均每個查詢20個連絡人。 其他60% 的查詢是針對單一連絡人。</p>
<p>每個使用者每天有25個相片查詢。 24是針對單一相片，另一個是平均為20個連絡人的批次查詢。</p>
<p>每個使用者每天一個組織搜尋查詢的總數。</p></td>
</tr>
<tr class="even">
<td><p>混合模式，使用通訊錄檔案和網路查詢。 這是預設模式。</p></td>
<td><p>只有兩種類型的查詢會移至網路、相片與整個組織的搜尋查詢。</p>
<p>每個使用者每天有25個相片查詢。 24是針對單一相片，另一個是平均為20個連絡人的批次查詢。</p>
<p>每個使用者每天一個組織搜尋查詢的總數。</p></td>
</tr>
</tbody>
</table>


下表說明會議模型。

### <a name="conferencing-model"></a>會議模型

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>類別</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>排定的會議&quot;與 [&quot;立即開會] 會議</p></td>
<td><p>已排程60%，40% 未排程。</p>
<p>在已排定的會議中，我們假設80% 是指派的會議，這是週期性會議的出現次數;10% 是一次開啟的會議;8% 是一次性的匿名會議，2% 是一次性關閉的會議。</p></td>
</tr>
<tr class="even">
<td><p>會議用戶端發佈</p></td>
<td><p>針對排程的會議：</p>
<ul>
<li><p>65% 的會議使用者使用 Lync 2013。</p></li>
<li><p>5% 的會議使用者使用 Microsoft Lync Web App。</p></li>
<li><p>30% 的會議使用者使用較舊的用戶端，包括 Microsoft Lync 2010、Office Communicator 2007 R2、Office Communicator 2007，以及 Microsoft Office Communicator Web Access （2007發行版本）。</p></li>
</ul>
<p>針對未排程的會議：</p>
<ul>
<li><p>70% 的會議使用者使用 Lync 2013。</p></li>
<li><p>30% 的會議使用者使用較舊的用戶端，包括 Microsoft Lync 2010、Office Communicator 2007 R2、Office Communicator 2007，以及 Microsoft Office Communicator Web Access （2007發行版本）。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>會議併發性</p></td>
<td><p>在工作時間內，5% 的使用者就會參與會議。 因此，在 80000-使用者池中，4000許多使用者可能都會在會議中進行任何一次的會議。</p></td>
</tr>
<tr class="even">
<td><p>會議音訊發佈</p></td>
<td><p>40% 混合式 VoIP 音訊和撥入式會議，且 VoIP 使用者的3:1 比率為撥入使用者。</p>
<p>僅35% 的 VoIP 音訊。</p>
<p>只有15% 的電話撥入式會議音訊。</p>
<p>10% 無音訊（僅限 IM 會議，平均每位使用者傳送五個郵件）。</p></td>
</tr>
<tr class="odd">
<td><p>適用于會議的媒體組合</p></td>
<td><p>75% 的會議是網路會議，其中包含音訊加上其他一些共同作業形式。</p>
<p>針對這些會議，其他共同作業方法如下所示：</p>
<div>

> [!NOTE]  
> 因為一個會議可以有多個共同作業方法，所以這些數位會加總超過100%。


</div>
<ul>
<li><p>50% 新增應用程式共用。 我們假設一位使用者以每秒 1.1 MB 的峰值傳送資料。</p></li>
<li><p>50% 新增立即訊息（每位使用者平均為2封郵件）。</p></li>
<li><p>20% 新增資料共同作業，包括 PowerPoint 或白板，這兩個是每個會議所提供的兩個 PowerPoint 檔案，一般的 PowerPoint 檔案大小為 10 MB （沒有內嵌影片）或 30 MB （內嵌的影片）。 每個白板的平均20個批註。</p></li>
<li><p>20% [新增影片]。 在這些使用者中，70% 是針對多畫面影片啟用的會議，每個使用者都會收到2-3 視頻串流。</p></li>
<li><p>15% 新增共用筆記。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>會議參與者發佈</p></td>
<td><p>50% 內部、經過驗證的使用者。</p>
<p>25% 的遠端存取，經過驗證的使用者。</p>
<p>15% 匿名使用者。</p>
<p>10% 聯盟使用者。</p></td>
</tr>
<tr class="odd">
<td><p>會議加入發佈</p></td>
<td><p>使用者會在前5分鐘內模擬為加入會議。</p></td>
</tr>
</tbody>
</table>


在一般的前端池中，Lync Server 2013 的最大支援會議大小為250個使用者。 每個池都可以一次主持 1 250-使用者會議。 在進行這個大型會議時，該池子也可以主持其他較小的會議。 此外，您可以設定專用的池子來主持這些會議，以支援最多1000個使用者的會議。 如需詳細資訊，請參閱[Lync Server 2013 中的大型會議支援](lync-server-2013-support-for-large-meetings.md)。

會議的類比方式如下：

  - 85% 的會議有四個參與者。

  - 10% 的會議有六個參與者。

  - 5% 的會議有11個參與者。

  - 一個大型的250使用者會議。

下表提供涉及撥入使用者之會議之使用者模型的詳細資料。

### <a name="dial-in-conferencing-user-model"></a>電話撥入式會議使用者模型

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>類別</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>已驗證/匿名</p></td>
<td><p>70% 的呼叫者以匿名方式加入，且系統會提示您輸入錄製的名稱。 30% 以已驗證的使用者身分加入。</p></td>
</tr>
<tr class="even">
<td><p>保留通話持續時間和音樂</p></td>
<td><p>保留期間不含音樂的平均通話持續時間：50秒。</p>
<p>50% 的撥入使用者會聽到 [暫停音樂]，平均為5分鐘。</p></td>
</tr>
<tr class="odd">
<td><p>雙音調 multifrequency （DTMF）</p></td>
<td><p>在撥入的會議中，15% 只有手機領導人。 包含撥入使用者的混合會議中有10% 的混合會議也有電話領導人。</p>
<p>20% 的手機領袖會針對每個會議使用2個 DTMF 命令。</p></td>
</tr>
<tr class="even">
<td><p>宣告語言</p></td>
<td><p>模擬使用英文做為宣告語言。</p></td>
</tr>
</tbody>
</table>


下表提供有關 [會議大廳] 使用者模型的詳細資料。

### <a name="conference-lobby-user-model"></a>會議廳使用者模型

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>類別</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>大廳中的使用者數目</p></td>
<td><p>5% 的撥入使用者會透過大廳進行，而25% 的其他使用者則會透過大廳進行</p></td>
</tr>
<tr class="even">
<td><p>從大廳 Admitting</p></td>
<td><p>在模擬中，所有使用者都是在用戶端超時前由簡報者承認。</p></td>
</tr>
</tbody>
</table>


下表說明其他點對點工作階段的使用者模型。

### <a name="peer-to-peer-sessions-user-model"></a>點對點工作階段使用者模型

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>類別</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>應用程式共用</p></td>
<td><p>每個使用者每個月都參與5對等應用程式共用會話，平均每日0.25 個會話。</p></td>
</tr>
<tr class="even">
<td><p>檔案傳輸</p></td>
<td><p>每個使用者每個月都參與1對等檔案傳輸會話（作為 IM 會話的一部分），平均每日0.05 個會話。 傳輸的平均會話檔案大小為 1 MB。</p></td>
</tr>
</tbody>
</table>


下表說明原則的使用者模型。

### <a name="policies-user-model"></a>原則使用者模型

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>類別</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>會議、目前狀態及歸檔原則</p></td>
<td><p>我們假設您有一個全域原則、10個標記會議原則、4個封存原則，以及10個標籤的目前狀態原則。</p></td>
</tr>
<tr class="even">
<td><p>語音原則</p></td>
<td><p>我們假設每個網站都有一個全域原則和2個標記原則。 100% 的網站有網站原則，30% 的使用者已指派每使用者原則。 我們假設每個網站都有一個撥號方案，每個網站都有兩個路由。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="busy-hour"></a>Busy 小時

對於點對點工作階段，峰值負載是使用繁忙時間的呼叫企圖（BHCA）來計算。 這個語音產業字假設當天所有通話的50% 將在20% 的時間內完成。 它是使用下列公式來計算：

`BHCA=(total calls * 0.5) / 1.6`

在執行 VoIP 及其他點對點工作階段時，請在24小時內的每日至少1.6 小時負載中執行 VoIP 及其他點對點工作階段，以進行效能測試。

「會議峰值負載」假設所有會議的75% 是在4個小時的時間內完成。 這些尖峰時間的平均會議負載是1.5。

</div>

<div>

## <a name="enterprise-voice-to-pstn-calls"></a>企業語音到 PSTN 通話

下列假設適用于企業語音通話：

  - 50% 的使用者已啟用企業語音功能，而這些使用者的60% 已啟用 PSTN 通話。

  - 每個啟用 PSTN 通話的使用者都會在繁忙時間內撥打4個 PSTN 通話。 每個通話持續時間為3分鐘。

  - 這些 PSTN 語音通話的65% 使用媒體旁路。

</div>

<div>

## <a name="mobility"></a>行動性

系統會假設已登錄使用者的40% 是啟用行動。 針對已啟用行動裝置的每位使用者，我們假設行動用戶端的活動會累加至該使用者的其他 MPOP 實例，除了會議互動以外，其行動用戶端只是另一個用戶端類型，可以用來參與會議。

</div>

<div>

## <a name="persistent-chat"></a>常設聊天室

我們假設有25% 的註冊使用者將參與持續聊天會話，且具有下列特性：

  - 每位使用者1.5 聊天室的平均值

  - 每個聊天室會每小時產生12個輪詢要求，平均目標為10個使用者

</div>

<div>

## <a name="response-group-and-call-park"></a>回應群組和通話駐留

我們假設已註冊的使用者0.15% 是屬於回應群組。 我們假設0.02% 的已註冊使用者已在任何指定時間點停用通話。

</div>

</div>

<span> </span>

</div>

</div>

</div>

