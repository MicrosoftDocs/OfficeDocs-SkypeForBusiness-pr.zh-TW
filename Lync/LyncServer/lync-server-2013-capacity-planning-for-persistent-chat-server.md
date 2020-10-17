---
title: Lync Server 2013： Persistent Chat Server 的容量規劃
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
ms.openlocfilehash: 5c6bb3c7dcd8d03ffb0a57fb165fe1dba4ee933d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512800"
---
# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 中的持久聊天伺服器容量規劃

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

Persistent Chat Server 可以執行多使用者即時聊天，可保留以供未來檢索及搜尋。 與群組立即訊息 (IM) 會儲存在使用者的信箱中如果已設定交談記錄，則 Persistent Chat Server 會話會保持開啟的狀態，而且內容會儲存在伺服器上，以及郵件、檔案、URLs 和其他屬於進行中交談的資料。

容量規劃是準備部署 Persistent Chat Server 的重要部分。 本主題提供支援的持續性聊天伺服器拓撲及容量規劃表格的詳細資料，您可以用來判斷部署的最佳設定。 此外，本文也說明如何在高峰時進行需要較高容量的持久聊天伺服器部署的最佳管理。

若要下載 Persistent Chat Server，請參閱《 Microsoft Lync Server 13 Persistent Chat Server 》，網址為 [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539) 。

如需安裝 Persistent Chat Server 的詳細資訊，請參閱部署檔中的在 lync server [2013 中安裝 Persistent Chat server](lync-server-2013-installing-persistent-chat-server.md) 和設定 [persistent chat server 2013](lync-server-2013-configuring-persistent-chat-server.md) 中的功能。

支援工具（例如 Lync Server 規劃工具）可進一步協助您進行容量規劃。 如需規劃工具的詳細資訊，請參閱規劃檔中的 [開始進行 Lync Server 2013 的規劃程式](lync-server-2013-beginning-the-planning-process.md) 。

<div>

## <a name="persistent-chat-server-supported-topologies"></a>Persistent Chat Server 支援的拓撲

您可以在單一伺服器或多部伺服器集區中部署 Persistent Chat Server，並使用單一集區或多集區拓撲。

現在，我們也會在 Standard Edition server 上為新的 Lync Server 2013 部署支援 Persistent Chat Server。 不過，效能及規模會受到影響，而且由於這項新的部署沒有高可用性選項，因此我們預計您主要是用來進行概念證明、評估等等的目的。

<div>


> [!NOTE]  
> 如需這兩種拓撲的詳細資訊，請參閱部署檔中的 [在 lync Server <A href="lync-server-2013-planning-for-persistent-chat-server.md">2013 中規劃 Persistent Chat server</A> ] 和 [在 <A href="lync-server-2013-deploying-persistent-chat-server.md">lync Server 2013 中部署 persistent chat server</A> ]。



</div>

<div>

## <a name="single-server-topology"></a>單一伺服器拓撲

Persistent Chat Server 的最小設定和最簡單部署是單一持久聊天伺服器前端伺服器拓撲。 此部署需要執行 Persistent Chat Server (的單一伺服器，如果符合性已啟用) 、主控 SQL Server 資料庫的伺服器及相容性（若有必要），則會執行該程式，以儲存相容性資料。

<div>


> [!IMPORTANT]  
> 您無法將其他伺服器新增至 Persistent Chat Server 集區，此集區在拓撲產生器中以單一伺服器部署的方式啟動。 我們建議使用多伺服器集區拓撲，即使您使用單一伺服器也是一樣。 如此一來，您就可以在必要時新增更多的伺服器。 


</div>

下圖顯示單一 Persistent Chat Server 前端伺服器及規範的拓撲的所有必要和選用元件。

**單一常設聊天室伺服器**

![具有規範服務的單一伺服器拓撲](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "具有規範服務的單一伺服器拓撲")

</div>

<div>

## <a name="multiple-server-topology"></a>多部伺服器拓撲

若要提供更大的容量與可靠性，您可以部署多伺服器拓撲，如在 [Lync server 2013 中規劃 Persistent Chat server](lync-server-2013-planning-for-persistent-chat-server.md)所述。 多重伺服器拓撲可包含多達四部使用中持久聊天伺服器的使用中電腦 (高可用性和嚴重損壞修復設定允許最多八個，但只有四個可以使用中，而在待機) 仍可使用。 每一部伺服器最多可支援20000並行使用者，共連接至具有4部伺服器的持久聊天伺服器集區的併發使用者總數為80000。 多伺服器拓撲與單一伺服器拓撲相同，只是多部伺服器主控 Persistent Chat Server，而且可以擴充更高。 多部執行 Persistent Chat Server 的電腦應該位於與 Lync Server 和合規性服務相同的 Active Directory 網域服務網域中。

下圖顯示多部伺服器拓撲的所有元件，包含多部執行 Persistent Chat Server 的電腦、選用的規範服務和個別的規範資料庫。

**多部常設聊天室伺服器**

![多部伺服器拓撲](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "多部伺服器拓撲")

在四部伺服器的持續聊天伺服器部署中，80000使用者可以同時登入和使用持續性聊天，在每個伺服器的20000使用者之間平均分配負載。 如果一部伺服器無法使用，連接至該伺服器的使用者將無法存取其 Persistent Chat Server。 連線遭中斷的使用者會自動被轉接到其餘伺服器，直到無法使用的伺服器還原為止。 根據網路上的持續性聊天流量數量，此傳輸可能需要數分鐘或更長的時間。 因為剩下的每一部伺服器都可能裝載為30000個使用者，所以建議您儘快還原無法使用的伺服器，以避免效能問題。 否則，您可以使用拓撲產生器或 Windows PowerShell Cmdlet，將另一部 Persistent 聊天伺服器設定為可用， **CsPersistentChatActiveServer**。

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a>持久聊天伺服器容量規劃

下表可協助您使用 Persistent Chat Server 的容量規劃。 其模型變更各種持久聊天伺服器設定對容量功能的影響。

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a>規劃 Persistent Chat Server 的最大容量

使用下列範例表格，來判斷您可以支援的使用者數目。

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a>Persistent Chat Server 集區的最大容量範例

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>主動 Persistent Chat service 實例</p></td>
<td><p><em>dmx-4</em></p></td>
</tr>
<tr class="even">
<td><p>Persistent Chat service 實例</p></td>
<td><p><em>8 (4 必須是非使用中的;最多隻能使用4個作用中) </em></p></td>
</tr>
<tr class="odd">
<td><p>已連線的作用中使用者</p></td>
<td><p><em>80000</em></p></td>
</tr>
<tr class="even">
<td><p>布建使用者總數</p></td>
<td><p>150000</p></td>
</tr>
<tr class="odd">
<td><p>端點數目</p></td>
<td><p>120000</p></td>
</tr>
</tbody>
</table>


在上述範例中，方案是支援 Persistent Chat Server 所允許的最大使用者數目：「持久聊天」服務 (四個伺服器/實例可以有四個以上的被動式伺服器執行 Persistent Chat Server，以進行高可用性) 和嚴重損壞復原，以及每一部伺服器的20000使用者，共80000個作用中的使用者。

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a>管理持續聊天室存取的容量規劃

下列範例表可協助您規劃如何在 Persistent Chat Server 集區中管理持續性聊天室存取。

### <a name="managing-chat-room-access-sample"></a>聊天室存取管理範例

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
<th>大聊天室</th>
<th>總計</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>聊天室大小 (連接的使用者人數) </p></td>
<td><p>每個會議室30個</p></td>
<td><p>每個會議室150</p></td>
<td><p>每個會議室16000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>聊天室數</p></td>
<td><p>32000</p></td>
<td><p>1067</p></td>
<td><p>10 </p></td>
<td><p>33077</p></td>
</tr>
<tr class="odd">
<td><p>視聽中心的會議室%</p></td>
<td><p>1</p></td>
<td><p>1</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>開啟的會議室%</p></td>
<td><p>個</p></td>
<td><p>個</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>開啟會議室 (沒有明確的成員資格) </p></td>
<td><p>960</p></td>
<td><p>32</p></td>
<td><p>5 </p></td>
<td><p>997</p></td>
</tr>
<tr class="even">
<td><p>使用明確成員資格的非開啟聊天室 (一般會議室) </p></td>
<td><p>31040</p></td>
<td><p>1.035</p></td>
<td><p>5 </p></td>
<td><p>32080</p></td>
</tr>
<tr class="odd">
<td><p>視聽中心聊天室 (其他簡報者專案) </p></td>
<td><p>0</p></td>
<td><p>32</p></td>
<td><p>5 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>由直接成員資格管理的聊天室</p></td>
<td><p>50%</p></td>
<td><p>十進位</p></td>
<td><p>0</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>以使用者群組管理的聊天室數</p></td>
<td><p>50%</p></td>
<td><p>90%</p></td>
<td><p>100%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>開啟之聊天室之每個聊天室的成員資格清單中的使用者群組 (未明確指定) </p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>非開啟會議室之每個聊天室成員資格清單中的使用者</p></td>
<td><p>大約</p></td>
<td><p>150</p></td>
<td><p>16000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>非開啟會議室之每個聊天室成員資格清單中的使用者群組</p></td>
<td><p>個</p></td>
<td><p>5 </p></td>
<td><p>10 </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>每個聊天室的管理員清單中的使用者與使用者群組 (開放和非開啟的會議室) </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>每個視聽中心聊天室的簡報者清單中的使用者與使用者群組 (開啟和非開啟的會議室) </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>跨所有非開啟聊天室的使用者型成員資格實體</p></td>
<td><p>465600</p></td>
<td><p>15520</p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>跨所有非開啟會議室的使用者群組型成員資格實體</p></td>
<td><p>46560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>所有視聽中心聊天室中的使用者和使用者群組基礎實體</p></td>
<td><p>0</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>所有聊天室管理員清單中的使用者與使用者群組管理員實體</p></td>
<td><p>192000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>每個聊天室的作用中使用者數</p></td>
<td><p><em>大約</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16000</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>每位使用者的聊天室數</p></td>
<td><p><em>英寸</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>16</em></p></td>
</tr>
<tr class="odd">
<td><p>每個聊天室之成員資格清單中的使用者群組數</p></td>
<td><p><em>十進位</em></p></td>
<td><p><em>十進位</em></p></td>
<td><p><em>8</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>以使用者群組管理的聊天室數</p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>所有聊天室的使用者群組型成員資格實體數</p></td>
<td><p>155200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>所有聊天室的使用者型成員資格實體數</p></td>
<td><p>465600</p></td>
<td><p>77600</p></td>
<td><p>72000</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>每個聊天室的管理員、簡報者和範圍清單中的使用者與使用者群組數</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>所有聊天室的管理員、簡報者和範圍清單之間的使用者和使用者群組</p></td>
<td><p>192000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>存取控制項目數</p></td>
<td><p>704160</p></td>
<td><p>26768</p></td>
<td><p>160</p></td>
<td><p>731088</p></td>
</tr>
<tr class="even">
<td><p>最大存取控制項目數</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2000000</p></td>
</tr>
</tbody>
</table>


在上述範例中，當您根據建議的指導方針來部署 Persistent Chat server 時，可在啟用規範的情況下，處理跨越四個伺服器集區的最多80000個活躍使用者。

這個範例會顯示在任何指定時間) 、中型 (150 作用中使用者) 及大型 (16000 作用中使用者) ，歸類為小型 (30 作用中使用者的聊天室。 特定大小聊天室的數目是依下列項目的總數計算而來：

  - 系統中的作用中使用者

  - 特定大小聊天室中的作用中使用者

  - 單一使用者加入的特定大小聊天室

針對每個聊天室，先前的容量規劃表格會指定與聊天室相關聯的存取控制專案數目（包括直接指派給聊天室的專案）。 您可以使用存取控制清單 (ACL)，控制對個別聊天室的存取。 您也可以在類別層級控制存取。 在 ACL 中，個別的存取控制專案可以是使用者群組（例如，安全性群組、通訊群組清單或單一使用者）。 您可以定義聊天室管理員、簡報者和成員的存取控制項目。

<div>


> [!IMPORTANT]  
> 在規劃管理聊天室的策略時，請記住允許的存取控制專案總數為2000000。 如果計算出的存取控制專案超過2000000，伺服器效能可能會大幅降低。 若要避免此問題，請盡可能確定您的存取控制專案是使用者群組，而非個別使用者。



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a>邀請式聊天室存取的容量管理規劃

您可以使用下列容量規劃表格來瞭解 Persistent Chat Server 在設定成傳送邀請時，在 Persistent Chat 資料庫中建立及儲存的邀請數目。 您可以使用 Lync Server 控制台中的 **聊天室類別設定** 頁面或使用 Windows PowerShell Cmdlet **CsPersistentChatCategory**，管理類別上的邀請。 您可以使用 Lync 用戶端（或使用 Windows PowerShell Cmdlet）從 Lync 用戶端（ **clear-cspersistentchatroom**）中所) 提供的「**會議室管理**」頁面來管理聊天室上的邀請函 (線上。

下表中的範例資料假設，在 [ **聊天室設定** ] 頁面上的50% 的所有聊天室中，[ **邀請** ] 選項會設定為 **[是]**。

<div>


> [!IMPORTANT]  
> 如果伺服器所產生之邀請數目的計算值超過1000000，伺服器效能可能會大幅降低。 若要避免此問題，請確定您將設定為傳送邀請的聊天室數目降至最低，或限制可加入已設定為傳送邀請之聊天室的使用者人數。



</div>

### <a name="chat-room-access-by-invitation-sample"></a>邀請式聊天室存取範例

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
<th>大聊天室</th>
<th>總計</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>可以存取聊天室的使用者</p></td>
<td><p>每個會議室30個</p></td>
<td><p>每個會議室150</p></td>
<td><p>每個會議室16000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>具有邀請的會議室百分比</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>設成傳送邀請的聊天室數</p></td>
<td><p><em>16000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>位</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>可以存取該聊天室的使用者</p></td>
<td><p><em>60</em></p></td>
<td><p><em>225</em></p></td>
<td><p><em>16000</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Persistent Chat Server 產生的邀請</p></td>
<td><p>960000</p></td>
<td><p>120000</p></td>
<td><p>80000</p></td>
<td><p>1160000</p></td>
</tr>
<tr class="even">
<td><p>最大允許的邀請數</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2000000</p></td>
</tr>
<tr class="odd">
<td><p>模型 1-以預期的每天每個會議室的郵件數目為起始單位</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>每個會議室 (每日聊天速度) </p></td>
<td><p>50</p></td>
<td><p>500</p></td>
<td><p>100</p></td>
<td><p>650</p></td>
</tr>
<tr class="odd">
<td><p>所有會議室每秒 (的交談率) </p></td>
<td><p>55.56</p></td>
<td><p>18.52</p></td>
<td><p>0.03</p></td>
<td><p>74</p></td>
</tr>
<tr class="even">
<td><p>模型 2-從每位使用者每天發佈的郵件數目開始</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>每天每位使用者的聊天室速度</p></td>
<td><p>15 </p></td>
<td><p>5 </p></td>
<td><p>0.1</p></td>
<td><p>共</p></td>
</tr>
<tr class="even">
<td><p>每個會議室 (每日聊天速度) </p></td>
<td><p>38</p></td>
<td><p>375</p></td>
<td><p>800</p></td>
<td><p>1213</p></td>
</tr>
<tr class="odd">
<td><p>所有會議室每秒 (的交談率) </p></td>
<td><p>41.67</p></td>
<td><p>13.89</p></td>
<td><p>0.28</p></td>
<td><p>56</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a>Persistent Chat Server 效能使用者模型

下表說明 Persistent Chat Server 的使用者模型。 它會提供容量規劃需求的基礎，並代表四部伺服器上具有80000並行使用者的一般組織。

### <a name="persistent-chat-server-performance-user-model"></a>Persistent Chat Server 效能使用者模型

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>連接的使用中使用者數目</p></td>
<td><p>80000</p></td>
</tr>
<tr class="even">
<td><p>Persistent Chat Server 服務實例數目</p></td>
<td><p>4 </p></td>
</tr>
<tr class="odd">
<td><p>小型聊天室大小</p></td>
<td><p>30 位使用者</p></td>
</tr>
<tr class="even">
<td><p>中型聊天室大小</p></td>
<td><p>150 位使用者</p></td>
</tr>
<tr class="odd">
<td><p>大型聊天室大小</p></td>
<td><p>16000使用者</p></td>
</tr>
<tr class="even">
<td><p>聊天室總數</p></td>
<td><p>33077</p></td>
</tr>
<tr class="odd">
<td><p>小型聊天室數</p></td>
<td><p>32000</p></td>
</tr>
<tr class="even">
<td><p>中型聊天室數</p></td>
<td><p>1067</p></td>
</tr>
<tr class="odd">
<td><p>大型聊天室數</p></td>
<td><p>10 </p></td>
</tr>
<tr class="even">
<td><p>每位使用者的聊天室總數</p></td>
<td><p>16 </p></td>
</tr>
<tr class="odd">
<td><p>每位使用者的小型聊天室數</p></td>
<td><p>12 </p></td>
</tr>
<tr class="even">
<td><p>每位使用者的中型聊天室數</p></td>
<td><p>第</p></td>
</tr>
<tr class="odd">
<td><p>每位使用者的大型聊天室數</p></td>
<td><p>第</p></td>
</tr>
<tr class="even">
<td><p>每位使用者加入的會議室數目</p></td>
<td><p>24</p></td>
</tr>
<tr class="odd">
<td><p>尖峰加入速率</p></td>
<td><p>10/秒</p></td>
</tr>
<tr class="even">
<td><p>總聊天速率</p></td>
<td><p>24/秒</p></td>
</tr>
<tr class="odd">
<td><p>小型聊天室的聊天速率</p></td>
<td><p>22.22/秒</p></td>
</tr>
<tr class="even">
<td><p>中型聊天室的聊天速率</p></td>
<td><p>1.67/秒</p></td>
</tr>
<tr class="odd">
<td><p>大型聊天室的聊天速率</p></td>
<td><p>大約 0.15/秒</p></td>
</tr>
<tr class="even">
<td><p>設成傳送邀請的聊天室百分比</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>直接成員資格的百分比</p></td>
<td><p>50%</p></td>
</tr>
<tr class="even">
<td><p>群組成員資格的百分比</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory 網域服務中的平均祖先隸屬關係數目</p></td>
<td><p>100 - 200</p></td>
</tr>
<tr class="even">
<td><p>每位使用者的已訂閱連絡人數</p></td>
<td><p>80</p></td>
</tr>
<tr class="odd">
<td><p>每位使用者的平均端點數目</p></td>
<td><p>1.5</p></td>
</tr>
<tr class="even">
<td><p>每個端點的可見聊天室平均數目</p></td>
<td><p>1.5</p></td>
</tr>
<tr class="odd">
<td><p>每位使用者的可見聊天室平均數目</p></td>
<td><p>2.25 (50% 的1個會議室和50% 的2個會議室) ;開啟6個會議室，每個監視器一個</p></td>
</tr>
<tr class="even">
<td><p>每段間隔輪詢的參與者數</p></td>
<td><p>每個可見聊天室25個</p></td>
</tr>
<tr class="odd">
<td><p>輪詢間隔的長度</p></td>
<td><p>5 分鐘</p></td>
</tr>
<tr class="even">
<td><p>每秒輪詢的參與者數</p></td>
<td><p>15,000</p></td>
</tr>
<tr class="odd">
<td><p>每位使用者每小時的目前狀態變更次數</p></td>
<td><p>6 </p></td>
</tr>
<tr class="even">
<td><p>每秒的目前狀態變更次數</p></td>
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

