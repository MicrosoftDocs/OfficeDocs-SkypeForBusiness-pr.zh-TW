---
title: Lync Server 2013： 新的常設聊天室伺服器功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5257490dc63e1626c0cdb6dcf7e6ce1f17e75cd1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a>Lync Server 2013 中的新 Persistent Chat Server 功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-29_

Lync Server 2013，Persistent Chat Server 可讓您參與多方、 主題型保留一段時間的交談。 Persistent Chat Server 可協助組織，執行下列動作：

  - 改進地理位置分散且跨部門之小組間的通訊

  - 擴大資訊傳達和參與範圍

  - 改進大組織的通訊

  - 緩和資訊超載的狀況

  - 改進資訊傳達方式

  - 加強重要知識和資訊的傳播

無法在 Microsoft Office 365 中使用 Lync Server 2013，Persistent Chat Server。 在這個階段中，它是只適用於內部部署 Lync 2013 客戶。

在 Lync 2013 常設聊天室功能整合到 Lync 2013 用戶端。 因此，使用者可以存取所有的 Lync 2013 用戶端 Instant Messaging/目前狀態、 音訊/視訊、 會議及常設聊天室。 如需有關 Lync 2013 用戶端的詳細資訊，請參閱<http://go.microsoft.com/fwlink/p/?linkid=270877>。

本主題說明 Lync Server 2013，Persistent Chat Server 與先前的版本 （Microsoft Lync Server 2010，Group Chat） 的新版本之間的功能變更包括：

  - 提供 Lync Server 控制台] 中的系統管理體驗，並排除 Group Chat Admin Tool

  - 整合拓撲產生器中的 for Persistent Chat Server 的組態設定，藉由消除群組聊天設定工具

  - 輕鬆移轉及升級舊版 Persistent Chat Server

  - 提供高可用性和災害復原解決方案

如其他需 Persistent Chat Server 的最新版本的詳細資訊，請參閱下列各項：

  - 常設聊天室協助在<http://go.microsoft.com/fwlink/p/?linkid=270945>功能，它們的運作方式，以及如何使用它們時執行 Persistent Chat Server 提供常設聊天室的詳細的清單。

  - [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)中規劃文件、 部署文件中的[Deploying Persistent Chat Server 在 Lync Server 2013 中](lync-server-2013-deploying-persistent-chat-server.md)，[從 Lync Server 2010，Group Chat 或 Office Communications Server 2007 R2 Group Chat to Lync Server 2013，Persistent Chat Server 移轉](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)中移轉文件中，並[管理 Lync Server 2013，Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md)的作業文件中所有的指示設定常設聊天室伺服器。

  - 常設聊天室伺服器 Documentation.msi 檔 （Windows Installer 檔案） 可讓使用者存取完整離線文件相關 Persistent Chat Server。

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a>常設聊天室伺服器的主要拓撲變更

Persistent Chat Server 高層級的下列變更包括：

Persistent Chat Server 現在是一個伺服器角色。 在 [Microsoft Lync Server 2010，Group Chat 伺服器已 Microsoft Lync Server 2010 的協力廠商信任應用程式。 使用拓撲產生器時，可加入常設聊天室 Lync Server 2013 拓撲。 在 Lync Server 2013，Persistent Chat Server 功能被實作使用三個新的伺服器角色：

  - **PersistentChatService:** 這是針對常設聊天室前端角色。 在 Standard Edition 部署中，常設聊天室伺服器服務角色組合在像任何其他的 Lync Server 角色部署的器，Standard Edition server。 在 Enterprise Edition 部署中，常設聊天室服務角色被部署在獨立電腦上啟動載入器，像任何其他 Lync 伺服器角色。

  - **PersistentChatStore:** 後端伺服器對應至常設聊天室內容資料庫，儲存所有聊天室的內容。

  - **PersistentChatComplianceStore:** 備份端伺服器角色會對應至常設聊天室規範資料庫，儲存所有的規範事件。

這些 Persistent Chat Server 角色是選擇性的並且會安裝只能由客戶需要完整 Persistent Chat Server 功能。 只有當您選擇部署常設聊天室規範需要**PersistentChatComplianceStore**角色。

**PersistentChatService**角色執行兩項服務：

  - 常設聊天服務

  - 常設聊天室規範服務

在每個 Persistent Chat Server 上執行這些服務能提供這些服務的多重伺服器 Persistent Chat Server 集區中的高可用性。

此外，若要支援的檔案上傳和下載中的常設聊天室，Persistent Chat Server 包括 web 服務。 過去，此服務已組合 Persistent Chat Server、 前端伺服器與需要網際網路資訊服務 (IIS)，若要安裝的必要條件。 在 [Lync Server 2013 常設聊天室伺服器、 檔案上傳/下載 web 服務會與 Lync Server 2013 前端伺服器配置在一起。 副作用，網際網路資訊服務 (IIS) 不再是 Persistent Chat Server 的必要條件。 檔案上傳/下載 web 服務會被識別為**Atl-persistentchat**在網際網路資訊服務 (IIS) 管理員] 中。

<div>


> [!IMPORTANT]  
> <STRONG>PersistentChatService</STRONG>角色可以執行 Lync Server 2013 相同伺服器上的&nbsp;前端伺服器只有在該前端伺服器為 Standard Edition&nbsp;前端伺服器。 <STRONG>PersistentChatService</STRONG>角色不能執行 Lync Server 2013 獨立&nbsp;前端伺服器。 它可以安裝 Lync Server 2013 部署的內容中。



</div>

在 [常設聊天室伺服器排除查閱服務。 在 Lync Server 2010，Group Chat，查閱服務在每個群組聊天伺服器前端伺服器上執行，並執行下列其中一個通道伺服器的路由。 Lync Server 2013 依賴路由使用連絡人物件，其中每個 Persistent Chat Server 集區由以找出並路由傳送要求至適當的 Persistent Chat Server 集區，以及由 Lync Server 前端伺服器的連絡人物件其中一個執行 Persistent Chat Server 集區中的電腦。

在 Lync Server 2013 中，有規範服務修改：

  - Lync Server 2010 的規範服務執行獨立 （非-組合在一起），並只在單一伺服器上。 規範服務現在會執行所有常設聊天室伺服器前端伺服器，以及常設聊天室服務，並藉此提供的多重伺服器 Persistent Chat Server 集區中的高可用性。 單一規範配接器可以設定成從規範資料庫，其中一個其他系統 （XML 檔案、 Exchange 託管封存，依此類推） 擷取資料。 Persistent Chat Server 包含 XML 介面卡。

  - 訊息佇列 (又稱為 MSMQ) 佇列所共用的常設聊天室服務和每個 Persistent Chat Server 前端伺服器上的規範服務現在是僅供這兩項服務共用的私用佇列。 所有的規範服務寫入至相同的規範後端資料庫。 他們也所有從該資料庫讀取，目的將資料傳送到其執行個體的介面卡。 規範後端伺服器是以表示做為新的後端伺服器角色。
    
    <div>
    

    > [!IMPORTANT]  
    > 如同舊版中，所有規範資料都處理一次。 資料可能會由叫用在各種不同的 Lync Server 2013，Persistent Chat Server 電腦所執行的規範服務的配接器執行任何的個體處理。 Persistent Chat Server，在其中一個配接器執行個體無法處理資料。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 安裝訊息佇列的相關資訊，請參閱部署文件中<A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">安裝作業系統和 Lync Server 2013 的伺服器上的必要軟體</A>。

    
    </div>

在 Lync Server 2013 中，有高可用性和災害復原中的改良功能：

  - 高可用性改進： SQL Server 鏡像時用於 Persistent Chat Server 內容資料庫與常設聊天室規範資料庫 （網站） 的資料中心內提供高可用性。

  - 嚴重損壞復原增強功能： Persistent Chat Server 支援延伸集區架構，可讓要跨兩個站台伸展直到佔滿單一 Persistent Chat Server 集區 （也就是單一邏輯集區在拓撲中，集區中的伺服器與實體跨兩個站台位於）。 SQL Server 記錄傳送用於跨網站做為災害復原。

如需高可用性和災害復原的詳細資訊，請參閱部署文件中的[Configuring Persistent Chat Server 的高可用性和 Lync Server 2013 中的災害復原](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)。

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a>金鑰管理和管理變更的常設聊天室伺服器

Lync Server 2013 已進行更輕鬆地管理及管理 Persistent Chat Server 提供：

  - 整合的系統管理與管理。 Lync Server 2013 讓您更容易管理，並使用早已熟悉 Lync 系統管理員的工具來管理 Persistent Chat Server。 Persistent Chat Server 包含整合與 Lync Server Control Panel，地址與舊版群組聊天伺服器的使用者介面的效能問題的系統管理使用者介面體驗。 此外，Persistent Chat Server 包含 Windows PowerShell cmdlet 來管理與管理 Persistent Chat Server 類別、 （包括刪除聊天室和清除過時的內容），Persistent Chat Server 聊天室及增益集的集合。

  - 簡化的管理模型。 Lync Server 2013 已變更，並簡化 Persistent Chat Server 模型來解決下列重要客戶的需求：
    
      - 移除複雜的巢狀的階層的範圍和分類。
    
      - 若要定義支援拒絕目前 MindAlign 客戶規劃移轉至 Persistent Chat Server 清單，以及允許的清單 （範圍）。

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a>從群組聊天伺服器舊版不同之處使用者角色是什麼？

Lync Server 2010，Group Chat 是使用者系統管理員角色、 聊天室系統管理員角色和 Lync Server 系統管理員角色可以管理新增寫 Persistent Chat Server 只會提供 （也就是類似其他 Lync 常設聊天室系統管理員角色伺服器角色型存取控制 (RBAC) 角色）。 任何人都屬於此 RBAC 角色的成員可以管理聊天室、 增益集和類別 （並因此取得這些類別的使用者存取），與 Persistent Chat Server 集區的設定。

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a>從群組聊天伺服器舊版不同之處聊天室類別是什麼？

聊天室類別可以不再巢狀，而不再修改根類別。 AllowedMembers/DeniedMembers 構成 （不同之處在於它不支援指定拒絕清單） 是在舊版的 Group Chat 伺服器版本中使用的範圍。 範圍可能不再是覆寫，因為有無巢狀的類別。 在 Lync Server 2013 常設聊天室系統管理員可以建立及管理聊天室類別。 建立及管理聊天室類別的一部分，常設聊天室管理員可以設定必須是成員/建立者的特定類別的聊天室存取的主體 （Active Directory 群組/容器/使用者）。 A Persistent Chat Administrator 某個類別，也可以新增 DeniedMembers 和這些變得明確排除項目，以允許的清單。 DeniedMembers 覆寫 AllowedMembers 的功能。

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a>從群組聊天伺服器舊版不同之處聊天室屬性是什麼？

Lync Server 2013，Persistent Chat Server 中有開啟的聊天室的新概念。 所有允許的成員可加入聊天室時亦可，沒有獨佔成員資格。

已消除舊版 Persistent Chat Server 中所含的下列聊天室屬性：

  - 主題內容： 會議室現在只有描述。

  - 建立新成員清單： 中 Persistent Chat Server，所有聊天室開頭為空的成員資格 （和成員資格等於允許的成員可以最大化）。

  - 檔案上傳： 用來為每個控制項的聊天室的設定是否允許檔案上傳/下載。 這現在已設定類別層級，並套用至該類別中的所有會議室。

  - 聊天歷程記錄： 用來如果聊天歷程記錄已啟用，但現在已設定只在類別層級，並將套用至該類別中的所有聊天室是每個控制項的聊天室的設定。

  - 邀請： 會議室一律會繼承邀請類別; 設定或者，它可以關閉在會議室。 如果類別先前已設定為邀請 Invite 無法開啟會議室。

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a>從群組聊天伺服器舊版不同之處原則是什麼？

Persistent Chat Server 有新的 Lync 原則啟用常設聊天室]，每個使用者/集區/網站/全域設定。 在 Lync 2013 用戶端的常設聊天室的環境是僅供由原則啟用常設聊天室的使用者 （直接或透過集區/網站/通用設定）。

舊版 Group Chat 伺服器並沒有任何已整合到 Lync Server 原則的原則。 在每次使用者與每個類別/會議室為基礎，使用每個使用者功能，**可以上傳檔案**您無法讓使用者的使用者系統管理員，聊天室管理員，或設定使用者能夠將檔案上傳。 Persistent Chat Server**檔案上傳**功能就只是每個類別。

</div>

<div>

## <a name="logging"></a>記錄

Persistent Chat Server 及 System Center Operations Manager 的記錄已整合至 Lync Server 2013 追蹤記錄。

</div>

<div>

## <a name="see-also"></a>另請參閱


[規劃 Lync Server 2013 中的常設聊天室伺服器](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

