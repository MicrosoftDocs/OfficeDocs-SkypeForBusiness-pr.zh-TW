---
title: Lync Server 2013：持久聊天伺服器的運作方式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: How Persistent Chat Server works
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49684643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bf6179e1ce24264c2079b3096fa9bb8c539ca1c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a>在 Lync Server 2013 中，持久聊天伺服器的運作方式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-21_

Lync Server 2013，持續聊天伺服器可讓您參與多方、依時間保留的、以主題為基礎的交談。 持續聊天伺服器可協助您的組織執行下列動作：

  - 改善地理位置分散且跨職能團隊之間的溝通

  - 拓寬資訊意識及參與情況

  - 改善與您的延伸組織的溝通

  - 減少資訊超載

  - 改善資訊意識

  - 增加重要知識與資訊的散佈

您可以使用 Lync Server 2013 來部署持久聊天伺服器作為選用角色。 持久性聊天服務在專用的池中執行，而持續聊天伺服器池則依賴 Lync 伺服器池來傳送郵件給它。 用戶端透過 SIP （XCCOS）使用可擴展聊天通訊。 Lync Server 前端伺服器已設定為將流量路由到持續聊天伺服器池。

<div>

## <a name="high-level-architecture"></a>高層次架構

下列圖表提供持續聊天伺服器架構與服務的高層觀點。

**持續聊天伺服器的高層次架構**

![持續聊天伺服器架構。](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "持續聊天伺服器架構。")

**持續聊天伺服器高層級服務**

![持續聊天伺服器元件。](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "持續聊天伺服器元件。")

在永久聊天伺服器前端伺服器上執行兩項服務：

  - 持續聊天（頻道）

  - 從屬

<div>

## <a name="persistent-chat-channel-service"></a>持續聊天（通道）服務

持續聊天（通道）服務是負責持久聊天伺服器的核心服務。 此服務提供下列功能：

  - 接受接收的郵件

  - 在持續聊天室中註冊並列出線上參與者

  - 將郵件重新傳送至其他通道訂閱者

  - 針對通道管理、聊天室邀請、搜尋及新的內容通知實現邏輯

永久聊天（通道）服務會使用 [永久聊天] 存放區，儲存及存取聊天室內容和其他系統中繼資料（授權規則等）。 此服務會儲存已上傳到 [永久聊天] 檔案存放區中的聊天室的檔案。

</div>

<div>

## <a name="compliance-service"></a>合規性服務

合規性服務是永久性聊天伺服器的選擇性元件，負責將聊天內容和事件封存到持續性聊天合規性存放區。 如果您的組織有需要永久聊天活動進行封存的規章，您可以部署選用的持續聊天合規性服務。 相容性服務已安裝在持續聊天池中的每個持續聊天伺服器上。 設定後，持久的聊天伺服器規範會記錄使用者活動，例如加入和離開聊天室，以及張貼及讀取訊息。 合規性服務儲存需要封存在持續聊天相容性檔案存放區中的檔案。

</div>

<div>

## <a name="persistent-chat-web-services"></a>持續聊天 Web 服務

在 Lync Server 前端伺服器上，執行兩個依存于網際網路資訊服務（IIS）的服務，並以網頁元件的形式實現：

  - 檔案**上傳/下載的持續聊天 Web 服務**負責從聊天室張貼及檢索檔案。

  - **聊天室管理的持續聊天 Web 服務**負責為使用者提供管理其聊天室的功能，並建立新的聊天室。

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a>我要如何開始使用持續聊天伺服器？

Persistent 聊天伺服器是 Lync Server 2013 基礎結構中的選擇性伺服器角色。 如果您安裝持久聊天伺服器角色，由系統管理員提供的任何已透過策略啟用的使用者都可以使用與 Lync 2013 用戶端的持續交談。

如需有關如何部署持續聊天伺服器並讓使用者能夠利用策略的詳細資料，請參閱[在 Lync server 2013 中部署持久聊天伺服器](lync-server-2013-deploying-persistent-chat-server.md)。

如需如何在持續聊天伺服器部署上設定設定的詳細資料，請參閱[在 Lync server 2013 中部署持久聊天伺服器](lync-server-2013-deploying-persistent-chat-server.md)，以及[管理 lync Server 2013、持續聊天伺服器](managing-lync-server-2013-persistent-chat-server.md)。

如需如何根據原則啟用使用者以使用 Lync 2013 用戶端中的持續聊天功能的詳細資料，請參閱[在 Lync server 2013 中部署持續聊天伺服器](lync-server-2013-deploying-persistent-chat-server.md)以及[管理 lync Server 2013、持續聊天伺服器](managing-lync-server-2013-persistent-chat-server.md)。

如果您已部署持久的聊天合規性，請參閱[管理 Lync server 2013、持續聊天伺服器，](managing-lync-server-2013-persistent-chat-server.md)以取得如何設定合規性設定的詳細資料。

</div>

<div>

## <a name="persistent-chat-call-flows"></a>持續聊天通話流程

持續聊天用戶端會使用 XCCOS 與持續聊天服務進行通訊。 下列順序描述登入程式，以及典型的聊天室訂閱和訊息發佈情況。

<div>

## <a name="sign-in"></a>登入

下列通話流程圖和步驟說明登入程式。

**持續聊天用戶端登入通話流程**

![持續聊天伺服器通話流程圖表。](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "持續聊天伺服器通話流程圖表。")

1.  持續性聊天用戶端會先傳送 SIP 訂閱，以從伺服器取得帶外的提供檔。 這份檔會指出使用者是否已啟用或停用持續聊天，以及持續聊天伺服器池中的 SIP Uri 清單。

2.  持續聊天用戶端會將 SIP 邀請訊息傳送到在上一個步驟中取得的持續聊天伺服器的 SIP URI。 邀請順序後面接著200的 [確定] 和 [ACK]，持續聊天用戶端現在已開啟與持續聊天伺服器端點的 SIP 會話。 因此，持續聊天用戶端會傳送 SIP 資訊訊息，其中包含聊天訊息或命令要求伺服器採取動作的命令，來與持久聊天伺服器進行通訊。 所有這些訊息都是透過 200 OK 或503服務無法使用（也就是伺服器負載繁重的事件）來確認。 如果用戶端收到503回應，將會重試訊息。 （這個範例不包含503回應）。如果伺服器接受該訊息或命令，並傳送 200 [確定]，就會以個別 SIP 資訊訊息的形式提供對用戶端的回應。 此回應包括對原始命令的參照。

3.  持續聊天用戶端會傳送包含 XCCOS **getserverinfo**命令的 SIP 資訊訊息。 持續聊天伺服器會以新的 SIP 資訊訊息回復，其中包含持續聊天服務設定的相關資訊。

4.  持續聊天用戶端會傳送包含 XCCOS **getassociations**命令的 SIP 資訊訊息。 持續聊天伺服器會以新的 SIP 資訊訊息回復，其中包含使用者所屬的聊天室清單。 持續性聊天用戶端會重複命令，以取得使用者為管理員的聊天室清單。

5.  持續聊天用戶端會從「目前狀態」檔中取得已追蹤的聊天室清單，其中每個聊天室都是以「roomSetting」類別表示。 所有追蹤的聊天室都是由單一 SIP 資訊訊息所聯接，其中包含包含聊天室 Uri 清單的 XCCOS **bjoin**命令。 因為已追蹤的聊天室清單會保留在伺服器上，所以任何電腦上的任何用戶端都有與指定使用者 URI 相同的已追蹤會議室清單。 持續聊天用戶端也會在本機電腦登錄中保留開啟的會議室（如果使用者已啟用此選項）清單，並在登入時，傳送包含每個開啟的聊天室的 XCCOS **join**命令的 SIP 資訊訊息，以加入該會議室。 由於此清單會保留在登錄中，因此在不同電腦上執行的兩個持續聊天用戶端可能會有不同的變化。

6.  針對每個加入的聊天室，持續性聊天用戶端會傳送包含 XCCOS **bccoNtext**命令的 SIP 資訊訊息。 持續聊天伺服器會以新的 SIP 資訊訊息回復，其中包含聊天室中最近的聊天訊息。

7.  持續性聊天用戶端會傳送一個 SIP 資訊訊息，其中包含 XCCOS **getinv** （也就是 [取得邀請]）命令，以要求用戶端尚未看到任何新的聊天室邀請。 在個別的 SIP 資訊訊息中，持續聊天伺服器會傳回這些聊天室的清單。

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a>訂閱聊天室並張貼訊息

下列通話流程圖和步驟描述典型的房間訂閱和訊息文章案例。

**持續聊天用戶端房間訂閱和郵件張貼通話流程**

![會議室訂閱與訊息文章中的案例。](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "會議室訂閱與訊息文章中的案例。")

1.  從持久性聊天用戶端，User1 按一下 [**加入聊天室**]，按一下 [**搜尋**]，然後輸入一些搜尋準則。 持續聊天用戶端會傳送包含 XCCOS **chansrch** （聊天室搜尋）命令的 SIP 資訊訊息，以及搜尋準則。 持續聊天伺服器會查詢後端資料庫，並在新的 SIP 資訊訊息中包含符合搜尋準則之可用聊天室清單的回復。

2.  [User1] 會選取他或她想要加入的聊天室，然後按一下 [**追蹤此聊天室**]。 持續聊天用戶端會傳送持續聊天伺服器的 SIP 資訊訊息，其中包含 XCCOS **join**命令，以及使用者選取的聊天室的聊天室識別碼。 持續聊天伺服器會以包含預配資料之 SIP 資訊訊息回復。

3.  持續聊天用戶端會傳送持久聊天伺服器，其中包含 XCCOS **bccoNtext** （backchat 內容）命令的 SIP 資訊訊息。 持續聊天伺服器會檢索聊天記錄，並將其傳回獨立 SIP 資訊訊息中的持續聊天用戶端。 此時，使用者會進入聊天室並準備參與。

4.  [User1] 會輸入新郵件，然後按一下 [**傳送**]。 持續聊天用戶端會將訊息張貼到 SIP 資訊 XCCOS **grpchat**命令中的聊天室。 持續聊天伺服器會將此新郵件的複本儲存在持久的聊天后端資料庫中。

5.  持續聊天伺服器會將 SIP**資訊 XCCOS 的**個別複本傳送給使用者，他們已進入聊天室。

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a>持續交談合規性通話流程

Persistent 聊天伺服器使用訊息佇列（也稱為 MSMQ）和額外的規範資料庫（mgccomp）來處理合規性資料。 如需處理合規性事件的方式範例，下列事件順序說明如何處理訊息張貼事件。

1.  使用者將訊息張貼到聊天室。

2.  持續聊天伺服器會將與事件相關的資訊放在私人訊息佇列佇列中。

3.  Persistent 聊天合規性伺服器會從佇列中讀取這個事件，並將它放在 mgccomp 資料庫中供日後進行處理。

4.  持續性聊天規範伺服器會定期處理資料庫中的一組事件，並將其傳送至持久聊天合規性配接器以進行處理。

5.  如果配接器成功處理資料，持久的聊天合規性伺服器會從 mgccomp 資料庫中刪除事件。

</div>

</div>

<span> </span>

</div>

</div>

</div>

