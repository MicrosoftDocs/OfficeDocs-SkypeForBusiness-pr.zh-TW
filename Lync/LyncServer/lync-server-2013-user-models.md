---
title: Lync Server 2013：使用者模型
description: Lync Server 2013：使用者模型。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 user models
ms:assetid: c551371c-d740-4372-bada-f0d713ec0d33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398811(v=OCS.15)
ms:contentKeyID: 49733811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15be3f4c002de6cfb9ade4f13d80aedb59d76a82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569759"
---
# <a name="user-models-in-lync-server-2013"></a>Lync Server 2013 中的使用者模型

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

本文所述的使用者模型為 [使用使用者模型的 Lync Server 2013 容量規劃](lync-server-2013-capacity-planning-using-the-user-models.md)中所述的容量規劃測量和建議提供基礎。

<div>

## <a name="lync-server-2013-user-models"></a>Lync Server 2013 使用者模型

下表說明 Lync Server 2013 的註冊、連絡人、立即訊息 (IM) 及顯示狀態的使用者模型。

### <a name="environment-and-registration-user-model"></a>環境和註冊使用者模型

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
<td><p>部署規模及分配</p></td>
<td><p>我們會使用三個中央網站來建立大型部署模型，每個網站各有一個前端集區。</p></td>
</tr>
<tr class="even">
<td><p>Active Directory 使用者的百分比</p></td>
<td><p>我們假設組織中所有 Active Directory 使用者的70% 皆已啟用 Lync Server。 80% 的已啟用使用者每天會登入 Lync Server (80% concurrency) 。 並行使用者是此區段其餘部分之數位的基礎。</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory 變更</p></td>
<td><p>我們假設每週在 Active Directory 中為 Lync 建立和啟用使用者總數的0.5%，且每週會從 Active Directory 和 Lync 停用總使用者的0.5%。 5% 的使用者每週至少有一個 Active Directory 屬性已變更。</p></td>
</tr>
<tr class="even">
<td><p>Active Directory 通訊群組</p></td>
<td><p>我們假設組織中的 Active Directory 通訊群組數目等於 Active Directory 中所有使用者數目的三倍。 通訊群組具有下列大小：</p>
<ul>
<li><p>64% 具有2-30 使用者</p></li>
<li><p>13% 具有31-50 使用者</p></li>
<li><p>10% 具有51-100 使用者</p></li>
<li><p>13% 具有101-500 使用者</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>) 使用者 VoIP 的語音 over IP (</p></td>
<td><p>60% 的 Lync Server 使用者已啟用整合通訊 (UC)  (也就是說，其電話號碼會歸 Lync Server) 所有。</p></td>
</tr>
<tr class="even">
<td><p>已註冊的用戶端分配</p></td>
<td><p>65% 的用戶端執行 Lync 2013 軟體，包括 Lync 和 Lync Phone Edition。</p>
<p>30% 的用戶端執行先前版本的 Lync 用戶端軟體。</p>
<p>使用 Lync Web App 的用戶端人數為5%。</p>
<p>如果已啟用行動性，我們會假設40% 的使用者正在與其他先前提及的註冊用戶端選項一起同時使用行動。 在此情況下，用戶端多重顯示點 (MPOP) 比率為1：1.9。 如果行動已停用，MPOP 比值為1：1.5。</p></td>
</tr>
<tr class="odd">
<td><p>遠端使用者分配</p></td>
<td><p>70% 的使用者內部連線。</p>
<p>30% 的使用者透過 Edge Server 和 Director 進行連線。</p></td>
</tr>
<tr class="even">
<td><p>連絡人散佈</p></td>
<td><p>使用者人數上限為1000。 小於1% 的使用者有1000連絡人。 少於25% 的使用者有100或以上的連絡人。</p>
<p>使用公用雲端連線的使用者的平均80連絡人。 下列使用者：</p>
<ul>
<li><p>50% 的連絡人位於組織內。 10% 的使用者為遠端使用者，從防火牆外部連線。</p></li>
<li><p>40% 的連絡人是公用雲端使用者 (例如 AOL、Yahoo！、MSN 或 Google 交談) 的使用者。</p></li>
<li><p>10% 的連絡人來自同盟合作夥伴。</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 ( 「PIC USL」 ) 不再提供購買新的或更新的協定。 具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟 信使直到服務關閉日期。 AOL 和 Yahoo！的循環結束日期為2014年6月 已宣告。 如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權 信使。 Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</P>
> <LI>
> <P>Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。 與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。 隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</P></LI></UL>


</div></li>
</ul>
<p>在沒有公用雲端連線的情況下，為使用者平均50連絡人。 下列使用者：</p>
<ul>
<li><p>80% 的連絡人位於組織內。 10% 的使用者為遠端使用者，從防火牆外部連線。</p></li>
<li><p>20% 的連絡人來自同盟合作夥伴。</p>
<p>每個使用者的連絡人清單中有1個通訊群組。 針對效能測試，我們假設通訊群組永遠展開。</p></li>
</ul>
<p>25% 的使用者的連絡人使用 XMPP。</p></td>
</tr>
<tr class="odd">
<td><p>會話時間</p></td>
<td><p>平均使用者登入會話會持續12小時。 所有使用者在會話開始的120分鐘內登入。</p></td>
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
<td><p>每位使用者每天平均六個對等 IM 會話。</p>
<p>每個會話10個立即訊息。</p>
<p>每封郵件會以兩個 SIP 資訊訊息和2個 SIP 200 確定郵件 (，以供狀態指標（如 " &lt; Name the Name &gt; "） ) </p></td>
</tr>
<tr class="even">
<td><p>目前狀態輪詢</p></td>
<td><p>總而言之，我們每位使用者每小時平均60輪詢的平均狀態輪詢。 針對每個使用者，假設平均：</p>
<ul>
<li><p>在使用者的 [組織] 索引標籤中，每一天一個輪詢使用者的狀態 (但不是連絡人清單) 。 在使用者的 [組織] 索引標籤中，平均非連絡人數目為15位使用者。 每天的兩個連絡人卡片查看作業。</p></li>
<li><p>一個目前狀態輪詢每當使用者按一下另一個使用者來開始交談時，預估每小時預估一次。</p></li>
<li><p>每小時六個使用者搜尋。 每次執行搜尋時，都會針對搜尋結果清單中的每個人傳送批次投票。 我們假設搜尋結果的平均大小為20。 如果搜尋結果停留在螢幕上，批次輪詢會每5分鐘刷新一次。我們假設每小時會有兩種重新整理。</p></li>
<li><p>當使用者開啟或預覽 Outlook 中的電子郵件時，會在電子郵件的 [收件者：] 和 [副本：] 欄位中輪詢使用者的狀態，每小時預估5封電子郵件，每封電子郵件四位使用者。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>目前狀態訂閱</p></td>
<td><p>當一個使用者將另一個使用者新增為連絡人時，第一個使用者會 <em>訂閱</em> 第二個使用者的五種資訊類別。 這些資訊類別的更新會自動傳送給第一個使用者。</p>
<p>針對每個用戶端，會傳送單一批次訂閱要求，以取得平均40連絡人的目前狀態，另外還有其他40對話方塊，可取得同盟連絡人的狀態資訊。</p>
<p>展開的通訊群組成員的目前狀態會透過持續存在性訂閱來找到，而非輪詢，而且會為每位使用者每2個小時以1個擴充模式進行類比。</p>
<p><em>短訂閱</em> 會在使用者登入時發生，所有使用者的連絡人都有一個批次訂閱，然後使用者便會立即登出。 我們為每位使用者每小時假設6個短訂閱，每個訂閱會持續10分鐘。</p></td>
</tr>
<tr class="even">
<td><p>目前狀態出版物</p></td>
<td><p>每位使用者每小時平均發佈一個顯示狀態的狀態，每位使用者每小時最多6個出版物。</p></td>
</tr>
<tr class="odd">
<td><p>目前狀態檔案大小</p></td>
<td><p>完整顯示狀態檔的平均大小假設為4K，最大值為25K。</p></td>
</tr>
</tbody>
</table>


下表說明通訊錄使用的使用者模型。

### <a name="address-book-usage-user-model"></a>通訊錄使用狀況使用者模型

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>通訊錄搜尋模式</th>
<th>Usage</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>通訊錄 Web 查詢僅 (通訊錄 Web 查詢服務執行的所有查詢) </p></td>
<td><p>每位使用者每天四個首碼查詢。</p>
<p>60每天每位使用者的確切搜尋查詢。 40% 的批次，每個查詢平均有20個連絡人。 其他60% 的查詢是針對單一連絡人。</p>
<p>每位使用者每天25張照片查詢。 24是針對單一相片，另一個是具有平均20個連絡人的批次查詢。</p>
<p>每位使用者每天一個組織搜尋查詢總數。</p></td>
</tr>
<tr class="even">
<td><p>混合模式，使用通訊錄檔案和 web 查詢。 這是預設模式。</p></td>
<td><p>只有兩種類型的查詢會進入網路、相片和組織總搜尋查詢。</p>
<p>每位使用者每天25張照片查詢。 24是針對單一相片，另一個是具有平均20個連絡人的批次查詢。</p>
<p>每位使用者每天一個組織搜尋查詢總數。</p></td>
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
<td><p>排定的會議與「 &quot; 立即開會」的 &quot; 會議</p></td>
<td><p>已排程60%，40% 未計畫。</p>
<p>在排程的會議中，我們假設80% 指派為會議，也就是週期性會議的出現;10% 是一次開啟的會議;8% 是一次性匿名會議，2% 是一次關閉會議。</p></td>
</tr>
<tr class="even">
<td><p>會議用戶端分配</p></td>
<td><p>對於排程的會議：</p>
<ul>
<li><p>65% 的會議使用者使用 Lync 2013。</p></li>
<li><p>5% 的會議使用者使用 Microsoft Lync Web App。</p></li>
<li><p>30% 的會議使用者使用舊版用戶端，包括 Microsoft Lync 2010、Office Communicator 2007 R2、Office Communicator 2007 和 Microsoft Office Communicator Web Access (2007 版本) 。</p></li>
</ul>
<p>針對排程的會議：</p>
<ul>
<li><p>70% 的會議使用者使用 Lync 2013。</p></li>
<li><p>30% 的會議使用者使用舊版用戶端，包括 Microsoft Lync 2010、Office Communicator 2007 R2、Office Communicator 2007 和 Microsoft Office Communicator Web Access (2007 版本) 。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>會議並行</p></td>
<td><p>5% 的使用者將在工作時間內的會議。 因此，在80000使用者集區中，最多可以有4000個使用者在會議中有一次。</p></td>
</tr>
<tr class="even">
<td><p>會議音訊分配</p></td>
<td><p>40% 混合 VoIP 音訊和電話撥入式會議，具有 VoIP 使用者的3:1 比率為撥入使用者。</p>
<p>35% 僅 VoIP 音訊。</p>
<p>15% 僅限電話撥入式會議音訊。</p>
<p>10% 無音訊 (僅限 IM 會議，每位使用者平均傳送五封郵件) 。</p></td>
</tr>
<tr class="odd">
<td><p>會議的媒體組合</p></td>
<td><p>75% 的會議是網路會議，包含音訊及其他一些共同作業形式。</p>
<p>對於這些會議，其他共同作業方法如下：</p>
<div>

> [!NOTE]  
> 這些數目的增加超過100%，因為一部會議可以有多個共同作業方法。


</div>
<ul>
<li><p>50% 新增應用程式共用。 我們假設一位使用者以每秒峰值 1.1 MB 的速率傳送資料。</p></li>
<li><p>50% 新增立即訊息 (，每位使用者) 平均有2封郵件。</p></li>
<li><p>20% 新增資料共同作業（包括 PowerPoint 或白板），平均每次會議所呈現的2個 PowerPoint 檔案，平均 PowerPoint 的檔案大小為 10 MB (，但沒有內嵌影片) 或 30 MB (使用內嵌的影片) 。 每個白板的平均20個批註。</p></li>
<li><p>20% 新增影片。 在這些使用者中，70% 位於啟用多種顯示顯示的會議中，每個使用者都會收到2-3 的視頻資料流程。</p></li>
<li><p>15% 新增共用筆記。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>會議參與者分配</p></td>
<td><p>50% 已驗證的內部使用者。</p>
<p>25% 遠端存取，已驗證的使用者。</p>
<p>15% 匿名使用者。</p>
<p>10% 同盟使用者。</p></td>
</tr>
<tr class="odd">
<td><p>會議加入分配</p></td>
<td><p>使用者在前5分鐘內模擬為加入會議。</p></td>
</tr>
</tbody>
</table>


在一般前端集區中，Lync Server 2013 的支援會議大小上限為250使用者。 每個集區一次可裝載 1 250 使用者會議。 在此大型會議發生時，集區也可以主控其他較小的會議。 此外，您可以設定專用集區來主控這些會議，以支援最多1000使用者的會議。 如需詳細資訊，請參閱 [在 Lync Server 2013 中支援大型會議](lync-server-2013-support-for-large-meetings.md)。

會議的模擬方式如下：

  - 85% 的會議有四位參與者。

  - 10% 的會議有6位參與者。

  - 5% 的會議有11位參與者。

  - 一個大型的250使用者會議。

下表提供使用者模型的詳細資訊，包括撥入使用者的會議。

### <a name="dial-in-conferencing-user-model"></a>會議使用者模型 Dial-In

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
<td><p>70% 的呼叫者會以匿名方式加入，並提示您輸入錄製的名稱。 30% 加入為已驗證的使用者。</p></td>
</tr>
<tr class="even">
<td><p>通話持續時間和等候音樂</p></td>
<td><p>平均通話持續時間，未等候音樂：50秒。</p>
<p>50% 的來電使用者在平均5分鐘內聽到等候音樂。</p></td>
</tr>
<tr class="odd">
<td><p>雙音訊式訊號 (DTMF) </p></td>
<td><p>15% 的電話會議只有電話領導者。 包含撥入式使用者的混合式會議中，有10% 的混合會議也有電話領導者。</p>
<p>20% 的電話領導者使用每個會議的2個 DTMF 命令。</p></td>
</tr>
<tr class="even">
<td><p>宣告語言</p></td>
<td><p>模擬使用英文做為宣告語言。</p></td>
</tr>
</tbody>
</table>


下表提供有關會議大廳之使用者模型的詳細資料。

### <a name="conference-lobby-user-model"></a>會議會議廳使用者模型

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
<td><p>會議廳中的使用者人數</p></td>
<td><p>5% 的撥入使用者會流覽會議廳，25% 的其他使用者會進入會議廳。</p></td>
</tr>
<tr class="even">
<td><p>從會議廳准許</p></td>
<td><p>在模擬中，所有使用者在用戶端超時之前都已由簡報者所承認。</p></td>
</tr>
</tbody>
</table>


下表說明其他點對點工作階段的使用者模型。

### <a name="peer-to-peer-sessions-user-model"></a>Peer-to-Peer 會話使用者模型

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
<td><p>每一位使用者每月加入5對等應用程式共用會話，平均每天0.25 個會話。</p></td>
</tr>
<tr class="even">
<td><p>檔案傳輸</p></td>
<td><p>每個使用者都會每月加入一部對等檔案傳輸會話 (成為 IM 會話) ，平均每天0.05 個會話。 傳輸的平均會話檔案大小為 1 MB。</p></td>
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
<td><p>會議、目前狀態及封存原則</p></td>
<td><p>我們假設有一個全域原則、10個標記會議原則、4個封存原則及10個標記顯示狀態原則。</p></td>
</tr>
<tr class="even">
<td><p>語音原則</p></td>
<td><p>我們假設每個網站都有一個全域原則和2個標記原則。 100% 的網站有網站原則，30% 的使用者已指派個別使用者原則。 我們假設每個網站有一個撥號對應表，每個網站都有兩個路由。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="busy-hour"></a>忙碌小時

點對點工作階段，峰值負載是使用繁忙的小時嘗試 (BHCA) 進行計算。 這個語音行業條款假設一天的50% 會在20% 的時間內完成。 它會使用下列公式計算：

`BHCA=(total calls * 0.5) / 1.6`

執行 VoIP 及其他點對點工作階段時，效能測試會以每小時至少每日至少1.6 小時的速度來執行。

會議峰值負載假設一天的75% 的所有會議都會以4個峰時段的時間進行。 這兩個峰時段的平均會議負載是1.5 倍。

</div>

<div>

## <a name="enterprise-voice-to-pstn-calls"></a>Enterprise Voice to PSTN 通話

下列假設適用于 Enterprise Voice 呼叫：

  - 50% 的使用者已啟用 Enterprise Voice，而這些使用者的60% 已啟用 PSTN 通話。

  - 每個為 PSTN 通話啟用的使用者，在忙碌小時內撥打4個 PSTN 通話。 每個通話持續時間為3分鐘。

  - 65% 的這些 PSTN 語音通話使用媒體旁路。

</div>

<div>

## <a name="mobility"></a>行動性

40% 的註冊使用者會被視為啟用行動性。 針對每個已啟用行動裝置的使用者，我們假設行動用戶端的活動已附加到該使用者的其他 MPOP 實例，但會議互動例外，其行動用戶端只是另一種可用於參與會議的用戶端類型。

</div>

<div>

## <a name="persistent-chat"></a>常設聊天室

我們假設25% 的註冊使用者會參與持續聊天會話，具有下列特性：

  - 每位使用者的平均1.5 聊天室

  - 每個聊天室都會每小時產生12個輪詢要求，每個目標平均平均為10位使用者。

</div>

<div>

## <a name="response-group-and-call-park"></a>回應群組和通話駐留

我們假設已註冊使用者的0.15% 屬於回應群組。 我們假設已註冊使用者的0.02% 已在任何指定的時間點寄存通話。

</div>

</div>

<span> </span>

</div>

</div>

</div>

