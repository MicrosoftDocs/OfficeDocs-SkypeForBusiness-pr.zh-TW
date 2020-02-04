---
title: Lync Server 2013：新常設聊天室伺服器功能
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
ms.openlocfilehash: fe207d2469a36d880e9ed519ff1d47d942ed79aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a>Lync Server 2013 中的新常設聊天室伺服器功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

Lync Server 2013，持續聊天伺服器可讓您參與多方、依時間保留的、以主題為基礎的交談。 持續聊天伺服器可協助您的組織執行下列動作：

  - 改善地理位置分散且跨職能團隊之間的溝通

  - 拓寬資訊意識及參與情況

  - 改善與您的延伸組織的溝通

  - 減少資訊超載

  - 改善資訊意識

  - 增加重要知識與資訊的散佈

Lync Server 2013，在 Microsoft Office 365 中無法使用持續聊天伺服器。 目前，它只能供內部部署的 Lync 2013 客戶使用。

在 Lync 2013 中，持續性聊天功能已整合至 Lync 2013 用戶端。 因此，使用者可以在 Lync 2013 用戶端中存取立即訊息/目前狀態、音訊/視頻、會議和持續聊天。 如需 Lync 2013 用戶端的詳細資訊， <http://go.microsoft.com/fwlink/p/?linkid=270877>請參閱。

本主題描述新版 Lync Server 2013、持續聊天伺服器與舊版（Microsoft Lync Server 2010、群組聊天）之間的功能變更，包括：

  - 在 Lync Server [控制台] 中提供管理體驗，並消除群組聊天系統管理工具

  - 透過去除群組聊天設定工具，將持續聊天伺服器的設定設定整合到拓撲建立器中

  - 輕鬆從舊版的持久性聊天伺服器進行遷移和升級

  - 提供高可用性與災害復原解決方案

如需最新版本持久性聊天伺服器的其他詳細資料，請參閱下列內容：

  - 持續性聊天<http://go.microsoft.com/fwlink/p/?linkid=270945>說明，提供持續聊天功能的詳細清單、運作方式，以及如何在執行持續聊天伺服器時使用它們。

  - 規劃檔中的[Lync server 2013 中的持續聊天伺服器規劃](lync-server-2013-planning-for-persistent-chat-server.md)，在[lync server 2013](lync-server-2013-deploying-persistent-chat-server.md)的 [部署] 檔中部署持續式聊天伺服器[，從 Lync Server 2010 升級，群組聊天或 Office 通訊伺服器 2007 R2 群組聊天至 Lync Server 2013、持續聊天伺服器](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)在作業檔中，以及在操作檔中[管理 lync server 2013 （持續聊天伺服器](managing-lync-server-2013-persistent-chat-server.md)），所有這些都提供有關設定的指示。持續聊天伺服器。

  - 永久聊天伺服器檔（Windows 安裝程式檔案）可讓使用者存取持續聊天伺服器的完整離線檔。

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a>持久聊天伺服器的重要拓撲變更

持續聊天伺服器的下列高層次變更包括：

持續聊天伺服器現在是一個伺服器角色。 在 Microsoft Lync Server 2010 中，群組聊天伺服器是適用于 Microsoft Lync Server 2010 的協力廠商信任應用程式。 您可以使用拓撲結構建立器，將持續式聊天新增至您的 Lync Server 2013 拓撲。 在 Lync Server 2013 中，持續聊天伺服器功能是使用三個新的伺服器角色來實現：

  - **PersistentChatService：** 這是持續聊天的前端角色。 在標準版部署中，Persistent 是由引導程式部署的標準版伺服器（例如任何其他 Lync 伺服器角色）來 collocated 持久聊天伺服器服務角色。 在企業版部署中，系統會在獨立電腦上以引導程式（例如任何其他 Lync 伺服器角色）來部署持久聊天服務角色。

  - **PersistentChatStore：** 與持久聊天內容資料庫對應的後端伺服器，其中所有的聊天內容都儲存在其中。

  - **PersistentChatComplianceStore：** 與持久聊天規範資料庫相對應的後端伺服器角色，所有符合性事件都會儲存在其中。

這些持續聊天伺服器角色是選擇性的，而且只由想要全面持久聊天伺服器功能的客戶所安裝。 只有在您選擇部署持續性聊天規範時，才需要**PersistentChatComplianceStore**角色。

**PersistentChatService**角色會執行兩個服務：

  - 持續聊天服務

  - 持續聊天相容性服務

在每個持續聊天伺服器上執行這些服務，即可在多伺服器持久性聊天伺服器池中提供這些服務的高可用性。

此外，若要支援在持續聊天室中的檔案上傳和下載，持續聊天伺服器會包含 web 服務。 之前，此服務是在持久聊天伺服器、前端伺服器以及必要的網際網路資訊服務（IIS）上 collocated，以作為先決條件來安裝。 在 Lync Server 2013 永久聊天伺服器中，檔案上傳/下載 web 服務是與 Lync Server 2013 前端伺服器 collocated。 如果是副作用，網際網路資訊服務（IIS）已不再是持久聊天伺服器的先決條件。 檔案上傳/下載 web 服務在網際網路資訊服務（IIS）管理員中會被識別為**PersistentChat** 。

<div>


> [!IMPORTANT]  
> 只有當前端伺服器是標準版&nbsp;前端伺服器時， <STRONG>PersistentChatService</STRONG>角色才能&nbsp;在與 Lync server 2013 前端伺服器相同的伺服器上執行。 <STRONG>PersistentChatService</STRONG>角色無法獨立于 Lync server 2013&nbsp;前端伺服器執行。 它只能安裝在 Lync Server 2013 部署的內容中。



</div>

在永久聊天伺服器中，已消除查閱服務。 在 Lync Server 2010 中，[群組聊天] 會在每個群組聊天伺服器前端伺服器上執行查閱服務，並執行路由至其中一個頻道伺服器。 Lync Server 2013 依賴連絡人物件來傳送的方式，其中每個持續聊天伺服器池都是由 Lync Server 前端伺服器所使用的連絡人物件所代表，並將要求傳送到適當的持續聊天伺服器池，以及在池中執行持續聊天伺服器的其中一個電腦。

在 Lync Server 2013 中，有合規性服務修改：

  - 在 Lync Server 2010 中，合規性服務會獨立執行（非 collocated），且僅適用于單一伺服器。 合規性服務現在會在所有持續聊天伺服器前端伺服器上執行，並在持續性聊天服務上執行，因此可在多伺服器持久聊天伺服器池中提供高可用性。 您可以將單一合規性配接器設定為從合規性資料庫和其他其中一個系統（XML 檔案、Exchange 託管的歸檔等）提取資料。 持續聊天伺服器包括 XML 配接器。

  - 持續式聊天服務和每個持續聊天伺服器前端伺服器所共用的 [訊息佇列] （又稱為 MSMQ）佇列現在都是由兩個服務共用的私用佇列。 所有合規性服務將寫入相同的規範後端資料庫。 它們也會從該資料庫讀取，目的是將資料傳送到其配接器的實例。 相容性後端伺服器會以新的後端伺服器角色表示。
    
    <div>
    

    > [!IMPORTANT]  
    > 就像在舊版中一樣，所有合規性資料只會處理一次。 資料可能是由在各種 Lync Server 2013、持續聊天伺服器電腦上執行的規範服務所呼叫的任何配接器實例所處理。 在永久聊天伺服器中，任何一個配接器實例都可以處理資料。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 如需安裝訊息佇列的相關資訊，請參閱部署檔中的<A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Lync Server 2013 的安裝作業系統和必備軟體</A>。

    
    </div>

在 Lync Server 2013 中，在高可用性和災害復原中都有一些改良功能：

  - 高可用性改良：您可以使用 SQL Server 鏡像，在資料中心（網站內）中，為持續性聊天伺服器內容資料庫和持續交談合規性資料庫提供高可用性。

  - 災難復原改良功能：持續性聊天伺服器支援延伸池架構，可讓單一持久聊天伺服器池延伸到兩個網站（也就是拓撲結構中的單一邏輯池），並以物理方式存放在池中的伺服器位於兩個網站上）。 SQL Server 記錄傳送是用於跨網站災害復原。

如需高可用性和災難復原的詳細資訊，請參閱在部署檔中[針對 Lync server 2013 的高可用性和災難復原設定持久聊天伺服器](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)。

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a>持久聊天伺服器的主要管理與管理變更

Lync Server 2013 可讓您更輕鬆地管理和管理持久聊天伺服器，只要提供：

  - 整合管理和管理。 Lync Server 2013 可讓您更輕鬆地使用 Lync 系統管理員熟悉的工具來管理和管理持久聊天伺服器。 持續聊天伺服器包含與 Lync Server 控制台整合的系統管理使用者介面體驗，可解決舊版群組聊天伺服器使用者介面的效能問題。 此外，持續聊天伺服器還包含一組 Windows PowerShell Cmdlet，可用於管理及管理持久聊天伺服器類別、持續聊天伺服器機房（包括刪除聊天室及清除過時的內容）和增益集。

  - 簡化的管理模型。 Lync Server 2013 通過解決下列重要客戶需求，來變更並簡化持續聊天伺服器模型：
    
      - 移除範圍與類別的複雜嵌套層次結構。
    
      - 支援以定義拒絕清單以及目前 MindAlign 客戶的允許清單（範圍），這些客戶正在規劃遷移至持久聊天伺服器。

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a>先前群組聊天伺服器版本中的使用者角色有何不同？

Lync Server 2010，群組聊天擁有使用者系統管理員角色、聊天室管理員角色，以及可管理增益集的 Lync Server 管理員角色。持續聊天伺服器只提供永久性聊天管理員角色（類似其他 Lync）伺服器角色的存取控制（RBAC）角色）。 任何擁有此 RBAC 角色成員的人都可以管理聊天室、增益集及類別（因此，您可以取得這些類別的使用者存取），以及設定持久聊天伺服器池。

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a>從先前的群組聊天伺服器版本，聊天室類別有何不同？

聊天室類別無法再嵌套，且無法再修改根類別。 AllowedMembers/DeniedMembers 包含在舊版群組聊天伺服器版本中使用的範圍（除了不支援指定拒絕清單之外）。 因為沒有嵌套類別，所以不能再重寫範圍。 Lync Server 2013 中的持續聊天系統管理員可以建立和管理聊天室類別。 在建立及管理聊天室類別的過程中，持續性聊天管理員可以設定擁有權的主體（Active Directory 群組/容器/使用者），這些使用者有權存取屬於特定類別之聊天室的成員/提供者。 持續聊天管理員也可以在類別中新增 DeniedMembers，並將它們變成 [允許] 清單的明確排除。 DeniedMembers 會覆寫 AllowedMembers 中的內容。

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a>聊天室屬性與舊版群組聊天伺服器版本有何不同？

Lync Server 2013 （持久聊天伺服器）中存在開啟聊天室的新概念。 所有允許的成員都可以加入聊天室，而不需要獨佔成員資格。

已消除舊版持久性聊天伺服器中所包含的下列聊天室屬性：

  - 主題：聊天室現在只有描述。

  - [建立新成員清單]：在永久聊天伺服器中，所有聊天室都是以空的成員資格開始（並且可以最大化到允許成員 equaling 的成員資格）。

  - 檔案上傳：您可以用來設定每個聊天室的設定，以控制是否允許檔案上傳/下載。 現在，這只會設定類別等級，並套用至該類別中的所有聊天室。

  - 聊天記錄：用來設定每個聊天室的設定，以控制是否已啟用聊天記錄，但現在只會在類別層級設定，並套用到該類別中的所有聊天室。

  - 邀請：會議室永遠會繼承類別的 [邀請] 設定;或者，您可以在聊天室中關閉該檔案。 如果該類別先前已設定為 [邀請]，會議室就無法開啟邀請。

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a>舊版群組聊天伺服器版本中的原則有何不同？

持續聊天伺服器已啟用新的 Lync 原則，且持續聊天、每個使用者/池/網站/全域設定。 在 Lync 2013 用戶端中，只有透過策略來啟用持續聊天（直接或透過 [池/網站/全域設定]）的使用者，才能使用持續式聊天環境。

舊版的群組聊天伺服器沒有任何整合到 Lync 伺服器原則的原則。 在每位使用者和每個類別/房間基礎上，使用 [**可以上傳**檔案的每個使用者] 功能，您就可以讓使用者成為使用者系統管理員、聊天室管理員，或設定使用者上傳檔案的能力。 持續聊天伺服器檔案**上傳**功能只針對每個類別。

</div>

<div>

## <a name="logging"></a>記錄

持續聊天伺服器與 System Center Operations Manager 的記錄功能已整合至 Lync Server 2013 追蹤記錄。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中規劃常設聊天室伺服器](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

