---
title: Lync Server 2013：持久聊天伺服器的容量規劃
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dde4bcb499e38e729850f06bb08590bf537696e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 中持續聊天伺服器的容量規劃

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

持續聊天伺服器可以執行多使用者即時聊天，以供日後檢索和搜尋。 與儲存在使用者信箱中的群組立即訊息（IM），如果已設定交談歷程記錄，持續聊天伺服器會話會保持開啟，且內容會儲存在伺服器上，以及郵件、檔案、Url 及其他屬於該部分的資料正在進行中的交談。

容量規劃是準備部署持久聊天伺服器的重要部分。 本主題提供支援的持續聊天伺服器拓撲和容量規劃資料表的詳細資料，您可以使用這些表格來判斷部署的最佳配置。 它也說明如何最好地管理在高峰時間需要較大容量的持久聊天伺服器部署。

若要下載持續聊天伺服器，請參閱「Microsoft Lync Server 13 永久聊天伺服器[http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539)」。

如需安裝持久聊天伺服器的詳細資訊，請參閱在[Lync server 2013 中安裝永久性聊天伺服器](lync-server-2013-installing-persistent-chat-server.md)，以及在部署檔中的[lync server 2013 中設定持續聊天伺服器](lync-server-2013-configuring-persistent-chat-server.md)。

支援工具（例如 Lync Server 規劃工具）可以進一步協助您進行容量規劃。 如需規劃工具的詳細資訊，請參閱在規劃檔中[開始進行 Lync Server 2013 的規劃程式](lync-server-2013-beginning-the-planning-process.md)。

<div>

## <a name="persistent-chat-server-supported-topologies"></a>持續聊天伺服器支援的拓撲

您可以在單一伺服器或多重伺服器池中部署持久聊天伺服器，以及使用單一池或多池拓撲。

我們現在還支援適用于新 Lync Server 2013 部署的標準版 server 上的持續聊天伺服器。 不過，效能和規模會受到影響，而且由於這項新的部署沒有高可用性選項，因此我們希望您主要使用這個方法來進行概念驗證、評估等。

<div>


> [!NOTE]  
> 如需這兩個拓朴的其他詳細資料，請參閱本檔中的 [在<A href="lync-server-2013-planning-for-persistent-chat-server.md">lync server 2013 中規劃持久聊天伺服器</A>]，並在 [部署] 檔中設定<A href="lync-server-2013-deploying-persistent-chat-server.md">lync server 2013 中的持續聊天伺服器</A>。



</div>

<div>

## <a name="single-server-topology"></a>單伺服器拓朴

持續聊天伺服器的最小設定和最簡單的部署是單一持續式聊天伺服器前端伺服器拓撲。 此部署需要單一伺服器來執行持續聊天伺服器（如果相容性已啟用，也可選擇執行合規性服務）、託管 SQL Server 資料庫的伺服器，以及如果需要合規性，則是 SQL Server 資料庫來儲存合規性資料。

<div>


> [!IMPORTANT]  
> 您無法將其他伺服器新增至永久聊天伺服器池中，該池是在拓撲建立器中以單一伺服器部署的形式啟動。 我們建議您使用多重伺服器池拓撲結構，即使您使用的是單一伺服器也一樣。 如此一來，您稍後就可以新增更多伺服器（如果需要的話）。 


</div>

下圖顯示單一持續聊天伺服器前端伺服器（符合合規性）的所有必要和選用元件。

**單一持久聊天伺服器**

![安裝有 Compliance Service 的單一伺服器拓撲](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "安裝有 Compliance Service 的單一伺服器拓撲")

</div>

<div>

## <a name="multiple-server-topology"></a>多重伺服器拓朴

若要提供更大的容量及可靠性，您可以部署多伺服器拓朴，如在[Lync server 2013 規劃持續聊天伺服器中](lync-server-2013-planning-for-persistent-chat-server.md)所述。 多重伺服器拓朴可包含多達四個執行持續聊天伺服器的活動電腦（高可用性和災害復原設定允許最多八個，但只有四個作用中的4個作用中，還有四個作用中的四個）。 每個伺服器可支援多達20000並行的使用者，總共是連線到具有4個伺服器的持久聊天伺服器池中的80000個併發使用者。 多重伺服器拓朴與單一伺服器拓朴一樣，只是多個伺服器主機持久的聊天伺服器，而且可以擴大規模。 多台執行持續聊天伺服器的電腦應該位於與 Lync Server 和合規性服務相同的 Active Directory 網域服務網域中。

下圖顯示多伺服器拓朴中的所有元件，其中多台電腦執行持續聊天伺服器、選用規範服務，以及個別的合規性資料庫。

**多個持續聊天伺服器**

![多部伺服器拓撲](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "多部伺服器拓撲")

在四伺服器持續式聊天伺服器部署中，80000使用者可以同時登入並使用持續聊天，在每個伺服器上，都會將負載平均分佈在20000個使用者。 如果一個伺服器無法使用，則連接至該伺服器的使用者將無法存取永久聊天伺服器。 已中斷連線的使用者會自動轉移到其餘的伺服器，直到無法還原無法使用的伺服器為止。 根據網路上持久聊天流量的數量，此傳輸可能需要幾分鐘的時間。 因為其餘的每個伺服器都可能會裝載許多30000的使用者，所以建議您儘快還原無法使用的伺服器，以免發生效能問題。 否則，您可以使用 [拓撲建立器] 或 [Windows PowerShell Cmdlet]，將另一個持久聊天伺服器設為可用，請**CsPersistentChatActiveServer**。

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a>持續聊天伺服器容量規劃

下清單格可協助您使用持續式聊天伺服器的容量規劃。 其模型變更各種持續聊天伺服器設定對容量功能有何影響。

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a>規劃持久聊天伺服器的最大容量

使用下列範例表格來判斷您將能支援的使用者數目。

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a>持續聊天伺服器池最大容量範例

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>活躍持續聊天服務實例</p></td>
<td><p><em>4</em></p></td>
</tr>
<tr class="even">
<td><p>持續聊天服務實例</p></td>
<td><p><em>8（4必須是非使用中，最多隻能啟用4個）</em></p></td>
</tr>
<tr class="odd">
<td><p>已連線的作用中使用者</p></td>
<td><p><em>80000</em></p></td>
</tr>
<tr class="even">
<td><p>已置備的使用者總數</p></td>
<td><p>150000</p></td>
</tr>
<tr class="odd">
<td><p>端點的數目</p></td>
<td><p>120000</p></td>
</tr>
</tbody>
</table>


在前面的範例中，方案是支援持續聊天伺服器允許的使用者數目上限：四個伺服器/每個版本的持續聊天服務（可以有四個待命伺服器執行持久聊天伺服器，以提供高可用性和災難復原），以及每個伺服器的20000使用者（共80000個作用中的使用者）。

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a>管理持續聊天室存取的容量規劃

下列範例表格可協助您規劃如何在持續聊天伺服器池中管理持續性聊天室存取。

### <a name="managing-chat-room-access-sample"></a>管理聊天室存取範例

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
<th></th>
<th>小型聊天室</th>
<th>中型聊天室</th>
<th>大型聊天室</th>
<th>總額</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>聊天室的大小（已連接的使用者數目）</p></td>
<td><p>每個房間30個</p></td>
<td><p>每個房間150</p></td>
<td><p>每個房間16000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>聊天室</p></td>
<td><p>32000</p></td>
<td><p>1067</p></td>
<td><p>第</p></td>
<td><p>33077</p></td>
</tr>
<tr class="odd">
<td><p>auditorium 的會議室%</p></td>
<td><p>sr-1</p></td>
<td><p>sr-1</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>開啟的會議室%</p></td>
<td><p>3</p></td>
<td><p>3</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>開啟會議室（無明確成員資格）</p></td>
<td><p>960</p></td>
<td><p>32</p></td>
<td><p>500</p></td>
<td><p>997</p></td>
</tr>
<tr class="even">
<td><p>未開啟的會議室（具有明確成員資格的一般聊天室）</p></td>
<td><p>31040</p></td>
<td><p>1.035</p></td>
<td><p>500</p></td>
<td><p>32080</p></td>
</tr>
<tr class="odd">
<td><p>Auditorium 會議室（其他簡報者專案）</p></td>
<td><p>0</p></td>
<td><p>32</p></td>
<td><p>500</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>由直接成員資格管理的聊天室</p></td>
<td><p>50%</p></td>
<td><p>第</p></td>
<td><p>0</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>由使用者群組管理的聊天室</p></td>
<td><p>50%</p></td>
<td><p>90%</p></td>
<td><p>100%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>每個聊天室的成員清單中的使用者群組（未明確指定）</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>每個聊天室的每個聊天室的成員資格清單中的使用者</p></td>
<td><p>為期</p></td>
<td><p>150</p></td>
<td><p>16000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>每個聊天室的每個聊天室成員資格清單中的使用者群組（適用于未開啟的會議室）</p></td>
<td><p>3</p></td>
<td><p>500</p></td>
<td><p>第</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>每個聊天室的管理員清單中的使用者和使用者群組（適用于開放和未開啟的會議室）</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>每個 auditorium 聊天室的簡報者清單中的使用者和使用者群組（適用于開放與未開啟的會議室）</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>跨所有非開啟會議室的使用者級成員資格實體</p></td>
<td><p>465600</p></td>
<td><p>15520</p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>跨所有非開啟會議室的使用者群組成員資格實體</p></td>
<td><p>46560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>跨所有 auditorium 聊天室的使用者和使用者群組實體實體</p></td>
<td><p>0</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>在所有聊天室管理員清單中的使用者和使用者群組（以小組為基礎）管理員實體</p></td>
<td><p>192000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>每個聊天室的作用中使用者</p></td>
<td><p><em>為期</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16000</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>每位使用者的聊天室</p></td>
<td><p><em>之間</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>位</em></p></td>
</tr>
<tr class="odd">
<td><p>每個聊天室的成員資格清單中的使用者群組</p></td>
<td><p><em>第</em></p></td>
<td><p><em>第</em></p></td>
<td><p><em>工資</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>由使用者群組管理的聊天室</p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>跨所有聊天室的使用者群組成員資格實體</p></td>
<td><p>155200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>跨所有聊天室的使用者級成員資格實體</p></td>
<td><p>465600</p></td>
<td><p>77600</p></td>
<td><p>72000</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>每個聊天室的管理員、簡報者及範圍清單中的使用者和使用者群組</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>所有聊天室的管理員、簡報者和範圍清單間的使用者和使用者群組</p></td>
<td><p>192000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>存取控制專案</p></td>
<td><p>704160</p></td>
<td><p>26768</p></td>
<td><p>160</p></td>
<td><p>731088</p></td>
</tr>
<tr class="even">
<td><p>最大存取控制專案</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2000000</p></td>
</tr>
</tbody>
</table>


在上述範例中，當您根據建議的準則部署持久聊天伺服器時，他們可以在啟用合規性的四個伺服器池中處理最多80000個作用中的使用者。

此範例顯示分類為小（任何指定時間為30個作用中的使用者）、中型（150作用中使用者）及大型（16000作用中使用者）的聊天室。 根據下列其中一個大小的聊天室數來計算：

  - 系統中的作用中使用者

  - 指定大小的聊天室中的作用中使用者

  - 單一使用者所連接之指定大小的聊天室

針對每個聊天室，先前的容量規劃表格會指定與聊天室相關聯的存取控制專案數目，包括直接指派至聊天室的專案。 您可以使用存取控制清單（Acl）來控制個別聊天室的存取權。 您也可以在類別層級控制存取權。 在 ACL 中，個別的存取控制專案可以是使用者群組，例如安全群組、通訊群組清單或單一使用者。 您可以為聊天室管理員、簡報者和成員定義存取控制專案。

<div>


> [!IMPORTANT]  
> 在規劃管理聊天室的策略時，請記住，允許存取控制專案的總數為2000000。 如果計算出的存取控制專案超過2000000，伺服器效能可能會顯著下降。 若要避免此問題，請確定您的存取控制專案是使用者群組，而不是個別使用者。



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a>透過邀請管理聊天室存取能力的容量規劃

您可以使用下列容量規劃表格，瞭解當它設定為傳送邀請時，持續聊天伺服器在永久聊天資料庫中建立並儲存的邀請數目。 您可以使用 Lync Server [控制台] 中的 [**聊天室類別設定**] 頁面，或使用 Windows PowerShell Cmdlet**設定 csPersistentChatCategory**，來管理類別上的邀請。 您可以使用從 Lync 用戶端啟動的 [**聊天室管理**]**頁面，或**使用 Windows PowerShell Cmdlet，在聊天室（與類別允許的方式）中管理邀請。

下表中的範例資料假設，在 [**聊天室設定**] 頁面上，有50% 的所有聊天室，[**邀請**] 選項會設定為 **[是]**。

<div>


> [!IMPORTANT]  
> 如果伺服器產生的邀請函數計算值超過1000000，伺服器效能可能會顯著下降。 若要避免此問題，請確定您將已設定傳送邀請的聊天室數量減至最少，或限制可以加入已設定傳送邀請之聊天室的使用者數目。



</div>

### <a name="chat-room-access-by-invitation-sample"></a>[透過邀請的聊天室存取] 範例

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
<th></th>
<th>小型聊天室</th>
<th>中型聊天室</th>
<th>大型聊天室</th>
<th>總額</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>可存取聊天室的使用者</p></td>
<td><p>每個房間30個</p></td>
<td><p>每個房間150</p></td>
<td><p>每個房間16000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>有邀請的會議室百分比</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>已設定傳送邀請的聊天室</p></td>
<td><p><em>16000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>500</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>可存取聊天室的使用者</p></td>
<td><p><em>60</em></p></td>
<td><p><em>225</em></p></td>
<td><p><em>16000</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>持續聊天伺服器產生的邀請</p></td>
<td><p>960000</p></td>
<td><p>120000</p></td>
<td><p>80000</p></td>
<td><p>1160000</p></td>
</tr>
<tr class="even">
<td><p>允許的邀請數目上限</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2000000</p></td>
</tr>
<tr class="odd">
<td><p>模型 1-從每個工作日的每個房間取得預期的郵件數目</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>每個會議室的聊天費率（每天）</p></td>
<td><p>50</p></td>
<td><p>500</p></td>
<td><p>100</p></td>
<td><p>650</p></td>
</tr>
<tr class="odd">
<td><p>所有聊天室的聊天比率（每秒）</p></td>
<td><p>55.56</p></td>
<td><p>18.52</p></td>
<td><p>0.03</p></td>
<td><p>74</p></td>
</tr>
<tr class="even">
<td><p>模型 2-從每個使用者每天張貼的訊息數目開始</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>每個使用者每天的聊天費率</p></td>
<td><p>工資</p></td>
<td><p>500</p></td>
<td><p>0.1</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>每個會議室的聊天費率（每天）</p></td>
<td><p>38</p></td>
<td><p>375</p></td>
<td><p>800</p></td>
<td><p>1213</p></td>
</tr>
<tr class="odd">
<td><p>所有聊天室的聊天比率（每秒）</p></td>
<td><p>41.67</p></td>
<td><p>13.89</p></td>
<td><p>0.28</p></td>
<td><p>56</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a>持久聊天伺服器效能使用者模型

下表說明持久聊天伺服器的使用者模型。 它提供容量規劃需求的基礎，並代表在四個伺服器上有80000併發使用者的一般組織。

### <a name="persistent-chat-server-performance-user-model"></a>持久聊天伺服器效能使用者模型

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>已連接的活動使用者數量</p></td>
<td><p>80000</p></td>
</tr>
<tr class="even">
<td><p>持久聊天伺服器服務實例數</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>小型聊天室的大小</p></td>
<td><p>30個使用者</p></td>
</tr>
<tr class="even">
<td><p>中型聊天室的大小</p></td>
<td><p>150使用者</p></td>
</tr>
<tr class="odd">
<td><p>大型聊天室的大小</p></td>
<td><p>16000使用者</p></td>
</tr>
<tr class="even">
<td><p>聊天室的總數量</p></td>
<td><p>33077</p></td>
</tr>
<tr class="odd">
<td><p>小型聊天室的數目</p></td>
<td><p>32000</p></td>
</tr>
<tr class="even">
<td><p>中型聊天室數</p></td>
<td><p>1067</p></td>
</tr>
<tr class="odd">
<td><p>大型聊天室數量</p></td>
<td><p>第</p></td>
</tr>
<tr class="even">
<td><p>每個使用者的聊天室總數</p></td>
<td><p>位</p></td>
</tr>
<tr class="odd">
<td><p>每位使用者的小型聊天室數</p></td>
<td><p>之間</p></td>
</tr>
<tr class="even">
<td><p>每位使用者的中型聊天室數</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>每個使用者的大型聊天室數</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>每位使用者加入的房間數</p></td>
<td><p>24</p></td>
</tr>
<tr class="odd">
<td><p>峰值連接速率</p></td>
<td><p>10/秒</p></td>
</tr>
<tr class="even">
<td><p>研討總匯率</p></td>
<td><p>24/秒</p></td>
</tr>
<tr class="odd">
<td><p>小型聊天室的聊天速度</p></td>
<td><p>22.22/秒</p></td>
</tr>
<tr class="even">
<td><p>中型聊天室的聊天費率</p></td>
<td><p>1.67/秒</p></td>
</tr>
<tr class="odd">
<td><p>大型聊天室的聊天速度</p></td>
<td><p>~ 0.15/秒</p></td>
</tr>
<tr class="even">
<td><p>為邀請設定的聊天室百分比</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>直接成員資格百分比</p></td>
<td><p>50%</p></td>
</tr>
<tr class="even">
<td><p>群組成員資格百分比</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory 網域服務中祖先隸屬關係的平均數目</p></td>
<td><p>100-200</p></td>
</tr>
<tr class="even">
<td><p>每位使用者的已訂閱連絡人數量</p></td>
<td><p>80</p></td>
</tr>
<tr class="odd">
<td><p>每個使用者的平均端點數</p></td>
<td><p>1.5</p></td>
</tr>
<tr class="even">
<td><p>每個端點的可見聊天室的平均數目</p></td>
<td><p>1.5</p></td>
</tr>
<tr class="odd">
<td><p>每位使用者可見聊天室的平均數量</p></td>
<td><p>2.25 （50%），共1個房間和50% （共2個房間）;開啟6個會議室，每個監視器一個</p></td>
</tr>
<tr class="even">
<td><p>每個間隔所輪詢的參與者人數</p></td>
<td><p>每個可見聊天室25個</p></td>
</tr>
<tr class="odd">
<td><p>巡迴檢測間隔長度</p></td>
<td><p>5分鐘</p></td>
</tr>
<tr class="even">
<td><p>每秒輪詢的參與者人數</p></td>
<td><p>15000</p></td>
</tr>
<tr class="odd">
<td><p>每個使用者每小時的狀態變更數量</p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p>每秒的狀態變更數量</p></td>
<td><p>133.33</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

