---
title: 'Lync Server 2013: Capacity planning for Persistent Chat Server'
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
ms.openlocfilehash: f20d297e1d127d167aa8acc059f5b6f89cc96d13
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a>Persistent Chat Server in Lync Server 2013 的容量規劃

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-05_

Persistent Chat Server 可以執行多個使用者可以保存的即時聊天室未來擷取與搜尋。 不同於群組立即訊息 (IM)，會儲存在使用者的信箱如果交談歷程記錄設定，Persistent Chat Server 的工作階段保持開啟更久，且內容儲存在伺服器上，以及郵件、 檔案、 Url 和屬於其他資料進行中的交談。

容量規劃是準備部署 Persistent Chat Server 的重要部分。 本主題提供有關支援的常設聊天室伺服器拓撲和容量規劃表格可用來判斷您的部署的最佳組態的詳細資訊。 它也說明如何以最佳管理 Persistent Chat Server 部署在尖峰時間需要更多的容量。

若要下載 Persistent Chat Server，請參閱 「 Microsoft Lync Server 13 Persistent Chat Server" [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539)。

如需安裝 Persistent Chat Server 的詳細資訊，請參閱部署文件中的[安裝 Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md)和[Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) 。

支援的工具，例如 [Lync Server 規劃工具，可進一步協助您進行容量規劃。 如需規劃工具的詳細資訊，請參閱規劃文件的[開頭 Lync Server 2013 的規劃程序](lync-server-2013-beginning-the-planning-process.md)。

<div>

## <a name="persistent-chat-server-supported-topologies"></a>常設聊天室伺服器支援的拓撲

您可以部署 Persistent Chat Server 在單一伺服器或多部伺服器集區，並與集區的單一或多個集區的拓撲。

我們現在也支援 Persistent Chat Server 的新的 Lync Server 2013 部署的 Standard Edition server 上。 不過，會影響效能和規模，並沒有這個新部署的高可用性選項，因為我們希望您可以使用此功能主要是基於證明概念、 評估，依此類推。

<div>


> [!NOTE]  
> 如需這兩種拓撲的詳細資訊，請參閱<A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A>中此文件組與<A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A>部署文件中。



</div>

<div>

## <a name="single-server-topology"></a>單一伺服器拓撲

最小的設定資料庫和 for Persistent Chat Server 的最簡單部署是單一常設聊天室伺服器前端伺服器的拓撲。 此部署需要執行常設聊天室伺服器 （如果啟用規範，選擇性地執行規範服務，）、 主控這兩個 SQL Server 資料庫伺服器的單一伺服器和合規性是否有需要，要儲存的 SQL Server 資料庫規範資料。

<div>


> [!IMPORTANT]  
> 您無法新增其他伺服器至已啟動拓撲產生器中的單一伺服器部署為 Persistent Chat Server 集區。 我們建議使用多部伺服器集區的拓撲，即使您使用單一伺服器。 這是這樣您就可以新增更多伺服器更新版本中，視需要。 


</div>

下圖顯示內含規範單一常設聊天室伺服器前端伺服器拓撲的所有必要與選用元件。

**單一常設聊天室伺服器**

![具有規範服務的單一伺服器拓撲](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "具有規範服務的單一伺服器拓撲")

</div>

<div>

## <a name="multiple-server-topology"></a>多部伺服器拓撲

若要提供更大的容量及可靠性，您可以部署多部伺服器拓撲，[規劃 Persistent Chat Server in Lync Server 2013 ](lync-server-2013-planning-for-persistent-chat-server.md)中所述。 多部伺服器拓撲可以包含多達四個作用中的電腦執行 Persistent Chat Server （高可用性和災害復原設定會允許最多第八個，但只有四個可以是作用中，其餘四處於待命狀態）。 每個伺服器可支援多達 20000 位並行使用者，總共為 80000 位並行使用者連線到具有 4 部伺服器 Persistent Chat Server 集區。 在多部伺服器拓撲是單一伺服器拓撲相同之處在於多部伺服器主控 Persistent Chat Server，並可將其調整更高版本。 執行 Persistent Chat Server 的多部電腦應該位於相同的 Active Directory 網域服務網域 Lync 伺服器和規範服務。

下圖顯示所有的元件的多部伺服器拓撲與執行 Persistent Chat Server、 選用的 Compliance service 和獨立的規範資料庫的多部電腦。

**多部常設聊天室伺服器**

![多伺服器拓撲](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "多伺服器拓撲")

在有四部伺服器 Persistent Chat Server 部署中，可以 80000 位使用者同時登入，並使用常設聊天室，負載平均分配在每個伺服器 20000 位使用者。 如果一部伺服器變成無法使用，連線至該伺服器的使用者都將遺失其存取至 Persistent Chat Server。 連線遭中斷的使用者會自動被轉接到其餘伺服器，直到無法使用的伺服器還原為止。 在網路上的常設聊天室傳輸量，根據此傳輸可能需要數分鐘或更久。 因為每個剩餘伺服器可能會主控多達 30000 位使用者，我們建議您以避免發生效能問題儘速還原無法使用的伺服器。 否則，您可以提供另一部常設聊天室伺服器使用拓撲產生器或 Windows PowerShell cmdlet， **Set-cspersistentchatactiveserver**。

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a>常設聊天室伺服器容量規劃

下表可協助您使用的容量規劃 Persistent Chat Server。 他們建立模型如何變更各種 Persistent Chat Server 設定會影響容量功能。

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a>規劃常設聊天室伺服器的最大容量

使用下列範例表格，來判斷您可以支援的使用者數目。

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a>Persistent Chat Server 集區最大容量範例

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>作用中的常設聊天室服務執行個體</p></td>
<td><p><em>4</em></p></td>
</tr>
<tr class="even">
<td><p>常設聊天室服務執行個體</p></td>
<td><p><em>8 （4 必須是不在作用中; 只有最大值為 4，可在作用中）</em></p></td>
</tr>
<tr class="odd">
<td><p>作用中的使用者連線</p></td>
<td><p><em>80000</em></p></td>
</tr>
<tr class="even">
<td><p>已佈建的使用者總數</p></td>
<td><p>150000</p></td>
</tr>
<tr class="odd">
<td><p>端點數目</p></td>
<td><p>120000</p></td>
</tr>
</tbody>
</table>


在上述範例中，該計劃是要支援，Persistent Chat Server 可讓使用者的數目上限: （可以有四部執行 Persistent Chat Server 的高可用性和災害復原的多個被動伺服器） 的常設聊天室的服務和 20000 位使用者每個伺服器，80000 位作用中的使用者，總共四個伺服器/執行個體。

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a>管理常設聊天室存取的容量規劃

下列範例表格可協助您管理常設聊天室 Persistent Chat Server 集區中的聊天室存取的計劃。

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
<th>小型聊天室數</th>
<th>中型聊天室數</th>
<th>大型聊天室數</th>
<th>總計</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>大小的聊天室 （已連線的使用者數目）</p></td>
<td><p>每個聊天室 30</p></td>
<td><p>每個聊天室 150</p></td>
<td><p>每個聊天室 16000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>聊天室數</p></td>
<td><p>32000</p></td>
<td><p>1,067</p></td>
<td><p>10 </p></td>
<td><p>33,077</p></td>
</tr>
<tr class="odd">
<td><p>%of 所視聽中心聊天室</p></td>
<td><p>1%</p></td>
<td><p>1%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>%的已開啟的聊天室</p></td>
<td><p>3%</p></td>
<td><p>3%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>開啟的聊天室 （沒有明確的成員資格）</p></td>
<td><p>960</p></td>
<td><p>32</p></td>
<td><p>5 </p></td>
<td><p>997</p></td>
</tr>
<tr class="even">
<td><p>非開啟聊天室 （使用明確的成員資格的一般聊天室）</p></td>
<td><p>31,040</p></td>
<td><p>1.035</p></td>
<td><p>5 </p></td>
<td><p>32,080</p></td>
</tr>
<tr class="odd">
<td><p>視聽中心聊天室 （其他簡報者項目）</p></td>
<td><p>0</p></td>
<td><p>32</p></td>
<td><p>5 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>直接成員資格所管理的聊天室</p></td>
<td><p>50%</p></td>
<td><p>10%</p></td>
<td><p>0%</p></td>
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
<td><p>開啟的聊天室 （未明確指定） 的每個聊天室的成員資格清單中的使用者群組</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>非開啟會議室的每個聊天室的成員資格清單中的使用者</p></td>
<td><p>30</p></td>
<td><p>150</p></td>
<td><p>16000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>非開啟會議室的每個聊天室的成員資格清單中的使用者群組</p></td>
<td><p>3 </p></td>
<td><p>5 </p></td>
<td><p>10 </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>使用者與 （適用於開啟和非開啟的聊天室） 的每個聊天室的管理員清單中的使用者群組</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>使用者和 （適用於開啟和非開啟會議室） 每個視聽中心聊天室的 [主持人] 清單中的使用者群組</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>使用者型成員資格實體數所有非開啟會議室</p></td>
<td><p>465,600</p></td>
<td><p>15,520</p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>使用者群組型成員資格實體數所有非開啟會議室</p></td>
<td><p>46,560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>使用者與使用者群組型實體之間所有視聽中心聊天室</p></td>
<td><p>0</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>使用者和使用者群組為主管理員實體的跨所有聊天室管理員清單</p></td>
<td><p>192,000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>每個聊天室的作用中使用者數</p></td>
<td><p><em>30</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16000</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>每位使用者的聊天室數</p></td>
<td><p><em>12</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>16</em></p></td>
</tr>
<tr class="odd">
<td><p>每個聊天室之成員資格清單中的使用者群組數</p></td>
<td><p><em>10</em></p></td>
<td><p><em>10</em></p></td>
<td><p><em>15</em></p></td>
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
<td><p>155,200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>所有聊天室的使用者型成員資格實體數</p></td>
<td><p>465,600</p></td>
<td><p>77,600</p></td>
<td><p>72,000</p></td>
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
<td><p>使用者與使用者群組，跨所有聊天室的管理員、 簡報者和範圍清單</p></td>
<td><p>192,000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>存取控制項目數</p></td>
<td><p>704,160</p></td>
<td><p>26,768</p></td>
<td><p>160</p></td>
<td><p>731,088</p></td>
</tr>
<tr class="even">
<td><p>最大存取控制項目數</p></td>
<td></td>
<td></td>
<td></td>
<td><p>每 2000000 個</p></td>
</tr>
</tbody>
</table>


在上述範例中，當您部署的建議準則，根據常設聊天室伺服器時所能處理最多 80000 位作用中使用者之間有四部伺服器集區與已啟用的規範。

此範例會示範聊天室分類為 「 小 （30 作用中的使用者在任何指定時間），中型 （150 主動使用者），以及大型 （16000 活躍的使用者）。 特定大小聊天室的數目是依下列項目的總數計算而來：

  - 系統中的作用中使用者

  - 特定大小聊天室中的作用中使用者

  - 單一使用者加入的特定大小聊天室

針對每個聊天室，上述的容量規劃的表格會指定與聊天室，包括直接指派給該聊天室的項目相關聯的存取控制項目數目。 您可以使用存取控制清單 (ACL)，控制對個別聊天室的存取。 您也可以在類別層級控制存取。 在 ACL 中的個別存取控制項目可以是使用者群組 — 例如，[安全性] 群組、 通訊群組清單或單一使用者。 您可以定義聊天室管理員、簡報者和成員的存取控制項目。

<div>


> [!IMPORTANT]  
> 規劃策略管理聊天室，請記住，允許的存取控制項目總數是 2 百萬。 如果計算的存取控制項目超過 2 百萬個，伺服器的效能可能會大幅降低。 若要避免此問題，可能的話，請務必您存取控制項目會而不是個別使用者的使用者群組。



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a>邀請式聊天室存取的容量管理規劃

您可以使用下列的容量規劃的表格以了解邀請 Persistent Chat Server 建立，並將儲存在常設聊天室資料庫時就會設成傳送邀請的數目。 使用 Lync Server 控制台] 中的**聊天室類別設定**] 頁面上或使用 Windows PowerShell cmdlet，**設定 csPersistentChatCategory**，您可以管理類別上的邀請。 使用 Lync 用戶端上，從啟動 「**聊天室管理**」 頁面或使用 Windows PowerShell cmdlet，**設定 csPersistentChatRoom**，您可以管理聊天室時亦可 （內嵌類別的讓） 上的邀請。

下表中的範例資料假設，在所有聊天室的 50%的**聊天室設定**] 頁面上，[**邀請**] 選項設為 **[是]**。

<div>


> [!IMPORTANT]  
> 如果伺服器所產生的邀請數的計算的值超過 1 千萬個，伺服器的效能可能會大幅降低。 若要避免此問題，請務必您最小化設定為傳送邀請] 或 [限制可以加入已設成傳送邀請的聊天室的使用者數目的聊天室數。



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
<th>小型聊天室數</th>
<th>中型聊天室數</th>
<th>大型聊天室數</th>
<th>總計</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>使用者可以存取聊天室</p></td>
<td><p>每個聊天室 30</p></td>
<td><p>每個聊天室 150</p></td>
<td><p>每個聊天室 16000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>具有邀請的聊天室的百分比</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>設成傳送邀請的聊天室數</p></td>
<td><p><em>16000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>5</em></p></td>
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
<td><p>Persistent Chat Server 所產生的邀請</p></td>
<td><p>960,000</p></td>
<td><p>120000</p></td>
<td><p>80000</p></td>
<td><p>1,160,000</p></td>
</tr>
<tr class="even">
<td><p>最大允許的邀請數</p></td>
<td></td>
<td></td>
<td></td>
<td><p>每 2000000 個</p></td>
</tr>
<tr class="odd">
<td><p>模型 1-預期的每個聊天室每日的郵件數目的開頭</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>速率每個聊天室 （每日）</p></td>
<td><p>50</p></td>
<td><p>500</p></td>
<td><p>100</p></td>
<td><p>650</p></td>
</tr>
<tr class="odd">
<td><p>跨所有聊天室的聊天速率 （每秒）</p></td>
<td><p>55.56</p></td>
<td><p>18.52</p></td>
<td><p>0.03</p></td>
<td><p>74</p></td>
</tr>
<tr class="even">
<td><p>模型 2-開頭的每位使用者每天張貼的訊息數目</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>每位使用者每天的聊天速率</p></td>
<td><p>15 </p></td>
<td><p>5 </p></td>
<td><p>0.1</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>每個 （每日） 的聊天室的聊天速率</p></td>
<td><p>38</p></td>
<td><p>375</p></td>
<td><p>800</p></td>
<td><p>1,213</p></td>
</tr>
<tr class="odd">
<td><p>跨所有聊天室的聊天速率 （每秒）</p></td>
<td><p>41.67</p></td>
<td><p>13.89</p></td>
<td><p>0.28</p></td>
<td><p>56</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a>常設聊天室伺服器效能使用者模型

下表說明 for Persistent Chat Server 的使用者模型。 它提供的容量規劃需求之基礎，代表含有四部伺服器上的 80000 位並行使用者的典型組織。

### <a name="persistent-chat-server-performance-user-model"></a>常設聊天室伺服器效能使用者模型

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>連線的作用中使用者數</p></td>
<td><p>80000</p></td>
</tr>
<tr class="even">
<td><p>Persistent Chat Server 服務執行個體數</p></td>
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
<td><p>16000 名使用者</p></td>
</tr>
<tr class="even">
<td><p>聊天室總數</p></td>
<td><p>33,077</p></td>
</tr>
<tr class="odd">
<td><p>小型聊天室數</p></td>
<td><p>32000</p></td>
</tr>
<tr class="even">
<td><p>中型聊天室數</p></td>
<td><p>1,067</p></td>
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
<td><p>12</p></td>
</tr>
<tr class="even">
<td><p>每位使用者的中型聊天室數</p></td>
<td><p>2 </p></td>
</tr>
<tr class="odd">
<td><p>每位使用者的大型聊天室數</p></td>
<td><p>2 </p></td>
</tr>
<tr class="even">
<td><p>每個使用者加入的聊天室數</p></td>
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
<td><p>~0.15/second</p></td>
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
<td><p>在 Active Directory 網域服務中的上階聯盟的平均數目</p></td>
<td><p>100 - 200</p></td>
</tr>
<tr class="even">
<td><p>每位使用者的已訂閱連絡人數</p></td>
<td><p>80</p></td>
</tr>
<tr class="odd">
<td><p>平均每位使用者的端點數目</p></td>
<td><p>1.5</p></td>
</tr>
<tr class="even">
<td><p>每個端點的可見聊天室的平均數目</p></td>
<td><p>1.5</p></td>
</tr>
<tr class="odd">
<td><p>平均每位使用者的可見聊天室數</p></td>
<td><p>2.25 （50 %1 的會議室而 50%為 2 的聊天室）;最多 6 個聊天室開啟時，監視每一個</p></td>
</tr>
<tr class="even">
<td><p>每段間隔輪詢的參與者數</p></td>
<td><p>每個可見聊天室 25</p></td>
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

