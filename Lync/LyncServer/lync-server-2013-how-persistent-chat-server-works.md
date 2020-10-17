---
title: Lync Server 2013： Persistent Chat Server 的運作方式
description: Lync Server 2013： Persistent Chat Server 的運作方式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Persistent Chat Server works
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49684643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c65df6a13305f75a8a25b85a39688fadf64e476c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562959"
---
# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a>在 Lync Server 2013 中，Persistent Chat Server 的運作方式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-21_

Lync Server 2013，Persistent Chat Server 可讓您加入一段時間內的多方、主題型交談。 Persistent Chat Server 可以協助貴組織執行下列作業：

  - 改進地理位置分散且跨部門之小組間的通訊

  - 擴大資訊傳達和參與範圍

  - 改進大組織的通訊

  - 緩和資訊超載的狀況

  - 改進資訊傳達方式

  - 加強重要知識和資訊的傳播

您可以將 Persistent Chat Server 部署為具有 Lync Server 2013 的選用角色。 在專用集區上執行 persistent Chat services，且 Persistent Chat Server 集區取決於 Lync 伺服器集區，以將郵件路由傳送至該伺服器集區。 用戶端將使用 eXtensible Chat Communication Over SIP (XCCOS)。 Lync Server 前端伺服器設定為將流量路由傳送至 Persistent Chat Server 集區。

<div>

## <a name="high-level-architecture"></a>高層架構

下列圖表提供 Persistent Chat Server 架構和服務的高層級。

**Persistent Chat Server 高層架構**

![Persistent Chat Server 架構。](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Persistent Chat Server 架構。")

**Persistent Chat Server 高層服務**

![Persistent Chat Server 元件。](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Persistent Chat Server 元件。")

在 Persistent Chat Server 前端伺服器上執行的兩項服務：

  - 常設聊天室 (通道)

  - 合規性

<div>

## <a name="persistent-chat-channel-service"></a>常設聊天室 (通道) 服務

Persistent Chat (通道) 服務是負責 Persistent Chat Server 的核心服務。 此服務提供下列功能：

  - 接受傳入訊息

  - 在持續聊天室內註冊和列出線上參與者

  - 重新傳輸訊息給其他通道訂閱者

  - 實作通道管理、聊天室邀請、搜尋及新內容通知的邏輯

Persistent Chat (通道) 服務會透過使用 Persistent 聊天存放區，儲存和存取聊天室內容及其他系統中繼資料 (授權規則等) 。 此項服務會將上傳至聊天室的檔案儲存在 Persistent Chat File Store 中。

</div>

<div>

## <a name="compliance-service"></a>規範服務

規範服務是 Persistent Chat Server 的選用元件，負責將聊天內容和事件封存到 Persistent Chat 規範存放區。 如果貴組織的法規要求封存持續聊天活動，您可以部署選用的持續性聊天規範服務。 規範服務是安裝在 Persistent Chat 集區中的每個 Persistent Chat Server 上。 設定後，Persistent Chat Server 相容性會記錄使用者活動，例如加入和離開聊天室，以及張貼和讀取郵件。 規範服務會儲存需要在 Persistent Chat 相容性檔案存放區中封存的檔案。

</div>

<div>

## <a name="persistent-chat-web-services"></a>Persistent Chat Web 服務

在 Lync Server 前端伺服器上，執行的兩個服務會依 Internet Information Services (IIS) 所執行，並以 web 元件的形式執行：

  - 檔案**上傳/下載的持續性聊天 Web 服務**負責在聊天室中張貼及檢索檔案。

  - **聊天室管理的持續性聊天 Web 服務** 負責為使用者提供管理其聊天室的能力，以及建立新的聊天室。

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a>如何開始使用 Persistent Chat Server？

Persistent Chat Server 是 Lync Server 2013 基礎結構中的選用伺服器角色。 如果您安裝 Persistent Chat Server role，系統管理員已透過原則啟用的任何使用者，都可以搭配 Lync 2013 用戶端使用持續性聊天。

如需如何部署 Persistent Chat Server 及如何讓使用者透過原則使用功能的詳細資訊，請參閱 [在 Lync server 2013 中部署 Persistent Chat Server](lync-server-2013-deploying-persistent-chat-server.md)。

如需如何設定持久聊天伺服器部署設定的詳細資訊，請參閱 [部署 Persistent Chat server In Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) 和 [管理 Lync Server 2013，Persistent chat server](managing-lync-server-2013-persistent-chat-server.md)。

如需如何依據原則啟用使用者以在 Lync 2013 用戶端上利用持續性聊天功能的詳細資訊，請參閱 [部署 Persistent Chat server In Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) 和 [管理 Lync Server 2013，Persistent chat server](managing-lync-server-2013-persistent-chat-server.md)。

如果您已部署持續性聊天相容性，請參閱 [管理 Lync server 2013 和 Persistent Chat server](managing-lync-server-2013-persistent-chat-server.md) ，以取得如何設定規范設定的詳細資訊。

</div>

<div>

## <a name="persistent-chat-call-flows"></a>Persistent 聊天通話流程

Persistent Chat 用戶端會使用 XCCOS 與 Persistent Chat service 進行通訊。 下列順序描述登入程序、一般聊天室訂閱以及訊息張貼的情況。

<div>

## <a name="sign-in"></a>登入

下列通話流程圖表和步驟說明登入程式。

**Persistent Chat 用戶端登入通話流程**

![Persistent Chat Server 呼叫流程圖表。](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Persistent Chat Server 呼叫流程圖表。")

1.  Persistent Chat 用戶端會先傳送 SIP 訂閱，以從伺服器中取得帶內布建檔。 這份檔會指出為使用者啟用或停用持續性聊天，以及 Persistent Chat Server 集區的 SIP URIs 清單。

2.  Persistent Chat 用戶端會將 SIP 邀請郵件傳送至在上一個步驟中取得之 Persistent Chat Server 的 SIP URI。 邀請順序後面接著是 200 OK 和 ACK，而且 Persistent Chat 用戶端現在已開啟具有 Persistent Chat Server 端點的 SIP 會話。 因此，Persistent Chat 用戶端會傳送 SIP 資訊郵件（包含聊天訊息或命令要求伺服器以採取動作），以與 Persistent 聊天伺服器進行通訊。 所有這些訊息都會以 200 OK 或「503 服務無法使用」(亦即在伺服器負載過重的情況下) 進行認可。 如果用戶端收到 503 回應，會重試訊息。  (本範例不包含503回應。 ) 如果伺服器接受郵件或命令，並傳送200，則該範例會以個別 SIP 資訊郵件的形式來提供對用戶端的回應。 該回應會包含對原始命令的參考。

3.  Persistent Chat client 會傳送包含 XCCOS **getserverinfo** 命令的 SIP 資訊訊息。 Persistent Chat Server 會使用包含 Persistent Chat service 設定相關資訊的新 SIP 資訊郵件進行回復。

4.  Persistent Chat client 會傳送包含 XCCOS **getassociations** 命令的 SIP 資訊訊息。 Persistent Chat Server 會以新的 SIP 資訊訊息（包含使用者所屬聊天室的清單）進行回復。 Persistent Chat 用戶端會重複執行此命令，以取得使用者為主管的聊天室清單。

5.  Persistent Chat 用戶端會從「目前狀態」檔取得關注的會議室清單，其中每個後續的會議室都會以 "roomSetting" 類別來表示。 所有追蹤聊天室會聯結包含 XCCOS **bjoin** 命令的單一 SIP INFO 訊息，命令中又包含聊天室 URI 的清單。 因為追蹤聊天室的清單保存在伺服器上，在任何電腦上的任何用戶端對於指定的使用者 URI 都有同樣的追蹤聊天室清單。 如果使用者在本機電腦登錄中) 啟用此選項，則持續聊天用戶端也會保留已開啟的 (會議室清單，然後在登入時，傳送包含每個開啟聊天室之 XCCOS **join** 命令的 SIP 資訊訊息，以加入這些會議室。 因為此清單保留在登錄中，所以在不同電腦上執行的兩個 Persistent 聊天用戶端上可能會有不同的狀態。

6.  在每個加入的會議室中，Persistent Chat 用戶端會傳送包含 XCCOS **bccoNtext** 命令的 SIP 資訊訊息。 Persistent Chat Server 會以新的 SIP 資訊訊息回復，該訊息包含會議室中的最近聊天訊息。

7.  Persistent Chat client 會傳送包含 XCCOS **getinv** (的 SIP 資訊郵件，也就是取得「邀請) 」命令，以要求用戶端尚未看到任何新的會議室邀請。 在個別的 SIP 資訊訊息中，Persistent Chat Server 會傳回這些聊天室的清單。

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a>訂閱聊天室及張貼訊息

下列通話流程圖表和步驟說明一般會議室訂閱和郵件發表後的情況。

**Persistent Chat Client 聊天室訂閱和郵件張貼通話流程**

![會議室訂閱和郵件發表後案例。](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "會議室訂閱和郵件發表後案例。")

1.  在 [Persistent Chat] 用戶端中，User1 按一下 [ **加入聊天室**]，按一下 [ **搜尋**]，然後輸入某些搜尋準則。 Persistent Chat client 會傳送包含 XCCOS)  (**chansrch** 的 SIP 資訊郵件，以及搜尋準則。 Persistent Chat Server 會查詢後端資料庫，並在新的 SIP 資訊訊息中回復，其中包含符合搜尋準則的可用會議室清單。

2.  使用者 1 選取要加入的聊天室，然後按一下 **[追蹤此聊天室]**。 Persistent Chat client 會傳送 Persistent Chat Server 包含 XCCOS **join** 命令的 SIP 資訊訊息，以及使用者選取之聊天室的會議室識別碼。 Persistent Chat Server 會回復包含布建資料的 SIP 資訊訊息。

3.  Persistent Chat client 會傳送 Persistent Chat Server 包含 XCCOS **bccoNtext** (backchat coNtext) 命令的 SIP 資訊訊息。 Persistent Chat Server 會檢索聊天記錄，並將它以個別 SIP 資訊訊息傳回給 Persistent Chat 用戶端。 此時，使用者進入聊天室，準備就緒參與。

4.  使用者 1 輸入新訊息，然後按一下 **[傳送]**。 Persistent Chat 用戶端會將郵件傳送至 SIP INFO XCCOS **grpchat** 命令中的聊天室。 Persistent Chat Server 會在 Persistent Chat 後端資料庫中儲存這封新郵件的複本。

5.  Persistent Chat Server 會傳送個別的 SIP 資訊 XCCOS **grpchat** 郵件複本給使用者，他已經輸入聊天室。

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a>Persistent Chat 相容性通話流程

Persistent Chat Server 會使用訊息佇列 (又稱為 MSMQ) ，另一種是規範資料庫 (mgccomp) 來處理規範資料。 下列事件順序描述如何處理訊息張貼事件，用以作為如何處理規範事件的範例。

1.  使用者在聊天室張貼訊息。

2.  Persistent Chat Server 會將相關資訊放入私人訊息佇列佇列中的事件。

3.  Persistent Chat 規範伺服器會從佇列中讀取此事件，並將它放入 mgccomp 資料庫，以備日後處理。

4.  Persistent Chat 規範伺服器會定期處理資料庫中的一組事件，並將其傳送至 Persistent Chat 合規性介面卡以進行處理。

5.  如果介面卡成功處理資料，Persistent Chat server 會刪除 mgccomp 資料庫中的事件。

</div>

</div>

<span> </span>

</div>

</div>

</div>

