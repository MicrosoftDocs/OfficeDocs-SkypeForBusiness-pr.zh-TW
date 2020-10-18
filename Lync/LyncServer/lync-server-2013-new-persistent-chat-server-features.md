---
title: Lync Server 2013：新的持久聊天伺服器功能
description: Lync Server 2013：新的持久聊天伺服器功能。
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
ms.openlocfilehash: 549fa43e115467c373fe8df08f8568aa8715c29d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579259"
---
# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a>Lync Server 2013 中的新 Persistent Chat Server 功能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

Lync Server 2013，Persistent Chat Server 可讓您加入一段時間內的多方、主題型交談。 Persistent Chat Server 可以協助貴組織執行下列作業：

  - 改進地理位置分散且跨部門之小組間的通訊

  - 擴大資訊傳達和參與範圍

  - 改進大組織的通訊

  - 緩和資訊超載的狀況

  - 改進資訊傳達方式

  - 加強重要知識和資訊的傳播

Lync Server 2013，在 Microsoft 365 或 Office 365 中無法使用 Persistent Chat Server。 目前只有內部部署 Lync 2013 客戶可以使用此功能。

在 Lync 2013 中，Persistent Chat 功能已整合至 Lync 2013 用戶端。 因此，使用者可以在 Lync 2013 用戶端中存取立即訊息/目前狀態、Audio/Video、會議及持續聊天。 如需 Lync 2013 用戶端的詳細資訊，請參閱 <https://go.microsoft.com/fwlink/p/?linkid=270877> 。

本主題說明新版本的 Lync Server 2013、Persistent Chat Server 和舊版 (Microsoft Lync Server 2010，Group Chat) 之間的功能變更，包括：

  - 在 Lync Server 控制台中提供管理體驗，並消除群組聊天管理工具

  - 透過消除群組聊天設定工具，將 Persistent Chat Server 的設定整合到拓撲產生器中

  - 輕鬆從舊版的持久聊天伺服器遷移和升級

  - 提供高可用性和嚴重損壞修復解決方案

如需最新版本 Persistent Chat Server 的其他詳細資訊，請參閱下列各項：

  - Persistent Chat <https://go.microsoft.com/fwlink/p/?linkid=270945> 說明，提供持續性聊天功能的詳細清單、運作方式，以及如何在執行 Persistent Chat Server 時使用這些功能。

  - 規劃檔中的「Lync Server 2013」中的 [ [持久聊天伺服器規劃](lync-server-2013-planning-for-persistent-chat-server.md) ]，在 [部署檔] 中 [部署 [lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) ] 中的 [Persistent Chat server]， [遷移自 Lync server 2010，群組聊天或 Office 通訊伺服器 2007 R2 Group Chat To Lync Server 2013，persistent chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) in the The The Operations 檔，以及 [管理 Lync Server 2013 （](managing-lync-server-2013-persistent-chat-server.md) 該檔中的 persistent chat Server），其全部都提供設定 Persistent Chat server 的指示。

  - Persistent Chat Server Documentation.msi file (Windows Installer 檔案) 可讓使用者存取有關 Persistent Chat Server 的完整離線檔。

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a>Persistent Chat Server 的重要拓撲變更

Persistent Chat Server 的下列高層級變更包括：

Persistent Chat Server 現在是一個伺服器角色。 在 Microsoft Lync Server 2010 中，Group Chat Server 是協力廠商信任的 Microsoft Lync Server 2010 應用程式。 您可以使用拓撲產生器，將 Persistent 聊天新增至您的 Lync Server 2013 拓撲。 在 Lync Server 2013 中，Persistent Chat Server 功能是使用三個新的伺服器角色來執行：

  - **PersistentChatService：** 這是持續聊天的前端角色。 在 Standard Edition 部署中，在引導程式部署的 Standard Edition 伺服器上組合 Persistent Chat Server 服務角色，如同任何其他 Lync Server 角色。 在 Enterprise Edition 部署中，Persistent 和任何其他 Lync Server 角色一樣，可在獨立電腦上部署 Persistent Chat Service 角色。

  - **PersistentChatStore：** 對應至 Persistent Chat 內容資料庫的後端伺服器，所有的聊天室內容都儲存在此伺服器上。

  - **PersistentChatComplianceStore：** 對應至 Persistent Chat 規範資料庫的後端伺服器角色，所有的相容性事件都儲存在該資料庫中。

這些 Persistent Chat Server role 是選用的，而且只有在需要完整的持久聊天伺服器功能的客戶才能安裝。 只有當您選擇部署持續性聊天相容性時，才需要 **PersistentChatComplianceStore** 角色。

**PersistentChatService**角色會執行兩項服務：

  - Persistent Chat service

  - Persistent Chat 合規性服務

在每個 Persistent Chat Server 上執行這些服務，可在多伺服器 Persistent Chat Server 集區中為這些服務提供高可用性。

此外，若要支援在 Persistent 聊天室中的檔案上傳與下載，Persistent Chat Server 會包含 web 服務。 先前，此服務是在 Persistent Chat Server、前端伺服器及必要的 Internet Information Services 上組合，以安裝成必要條件的方式 (IIS) 。 在 Lync Server 2013 Persistent Chat Server 中，檔案上傳/下載 web 服務是以 Lync Server 2013 前端伺服器組合。 在副作用中，Internet Information Services (IIS) 不再是 Persistent Chat Server 的必要條件。 檔案上傳/下載 web 服務會在網際網路資訊服務 (IIS) 管理員中識別為 **PersistentChat** 。

<div>


> [!IMPORTANT]  
> <STRONG>PersistentChatService</STRONG> &nbsp; 只有當前端伺服器為 Standard Edition 前端伺服器時，PersistentChatService 角色才能與 Lync Server 2013 前端伺服器在同一部伺服器上執行 &nbsp; 。 <STRONG>PersistentChatService</STRONG> role 無法獨立于 Lync server 2013 &nbsp; 前端伺服器上執行。 它只能安裝在 Lync Server 2013 部署的內容中。



</div>

在 Persistent Chat Server 中，查閱服務已經消除。 在 [Lync Server 2010] 中，Group Chat，查閱服務于每個群組聊天伺服器前端伺服器上執行，並已執行路由傳送至其中一個通道伺服器。 Lync Server 2013 依賴使用 contact 物件進行路由傳送，其中每個 Persistent Chat Server 集區都是由 Lync Server 前端伺服器所使用，用來識別及傳送適當 Persistent Chat Server 集區的要求，以及集區中執行 Persistent Chat Server 的電腦之一所代表。

在 Lync Server 2013 中，存在合規性服務修改：

  - 在 Lync Server 2010 中，規範服務執行獨立 (非組合) ，且只能在單一伺服器上執行。 規範服務現在會在所有 Persistent Chat Server 前端伺服器（和 Persistent Chat service）上執行，因此可在多伺服器持久聊天伺服器集區中提供高可用性。 您可以設定單一規範介面卡，將資料從規範資料庫提取，以及將資料放入其中一個其他系統 (XML 檔案、Exchange 主控的封存等等) 。 Persistent Chat Server 包含 XML 介面卡。

  - [！注意] 郵件佇列 (也稱為 Persistent Chat service 共用的 MSMQ) 佇列，而每個 Persistent Chat Server 前端伺服器上的規範服務現在只是兩個服務共用的私人佇列。 所有規範服務都會寫入相同的合規性後端資料庫。 它們也會從該資料庫讀取資料，目的是為了將資料傳送至其配接器的實例。 規範後端伺服器以新的後端伺服器角色表示。
    
    <div>
    

    > [!IMPORTANT]  
    > 就像先前的版本一樣，所有規範資料都只處理一次。 在不同的 Lync Server 2013，Persistent Chat Server 電腦上執行的規範服務所呼叫的任何配接器實例，都可以處理資料。 在 Persistent Chat Server 中，任何一種配接器實例都可以處理資料。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 如需安裝訊息佇列的相關資訊，請參閱部署檔中的在 <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Lync Server 2013 伺服器上安裝作業系統和必要條件軟體</A> 。

    
    </div>

在 Lync Server 2013 中，高可用性和嚴重損壞修復都有增強功能：

  - 高可用性增強功能：使用 SQL Server 鏡像，可在資料中心 (網站內) 中，為持久聊天伺服器內容資料庫及持久聊天規範資料庫提供高可用性。

  - 嚴重損壞修復功能： Persistent Chat Server 支援延伸集區架構，可讓單一持久聊天伺服器集區在兩個網站中 (，也就是拓撲中的單一邏輯集區，而且集區中的伺服器實際位於兩個網站) 上。 SQL Server 記錄傳送可用於跨網站的嚴重損壞修復。

如需高可用性和嚴重損壞修復的詳細資訊，請參閱部署檔中的在 [Lync server 2013 中設定 Persistent Chat Server，以取得高可用性和嚴重損壞修復](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) 。

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a>Persistent Chat Server 的主要管理和管理變更

Lync Server 2013 提供下列功能，讓您更容易管理及管理 Persistent Chat Server：

  - 統一的管理與管理。 Lync Server 2013 利用 Lync 系統管理員所熟悉的工具，讓您更容易管理及管理 Persistent Chat Server。 Persistent Chat Server 包含與 Lync Server 控制台整合的管理使用者介面體驗，其可解決舊版的群組聊天伺服器使用者介面的效能問題。 此外，Persistent Chat Server 包含 Windows PowerShell Cmdlet 的集合，用來管理及管理 Persistent Chat Server 類別、Persistent Chat Server 聊天室 (包括刪除聊天室和清除已過時的內容) 和增益集。

  - 簡化的管理模型。 Lync Server 2013 已透過解決下列主要客戶需求，以變更和簡化了 Persistent Chat Server 模型：
    
      - 移除範圍和類別的複雜嵌套階層。
    
      - 支援若要定義拒絕清單及允許的清單 (目前 MindAlign 客戶的範圍) 以遷移至 Persistent Chat Server。

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a>來自舊版群組聊天伺服器版本的使用者角色有何不同？

Lync Server 2010，群組聊天具有使用者系統管理員角色、聊天室系統管理員角色，以及可管理增益集的 Lync Server 系統管理員角色。Persistent Chat Server 只會提供與其他 Lync Server 角色型存取控制 (RBAC) 角色) 類似的持久聊天系統管理員角色 (。 任何屬於此 RBAC 角色成員的人都可以管理聊天室、增益集和類別 (，因此會取得這些類別的使用者存取權) 以及設定 Persistent Chat Server 集區。

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a>來自舊版群組聊天伺服器版本的聊天室類別有何不同？

聊天室類別可能不再是嵌套的，而且無法再修改根類別。 AllowedMembers/DeniedMembers 會組成舊版 Group Chat Server 版本中所用的範圍 (，但不支援指定拒絕清單) 。 因為沒有嵌套的類別，所以範圍可能不再被覆寫。 Lync Server 2013 中的 Persistent Chat 系統管理員可以建立及管理聊天室類別。 在建立及管理聊天室類別的過程中，Persistent Chat 管理員可以將主體設定 (Active Directory 群組/容器/使用者) ，該使用者有權存取屬於特定類別之聊天室的成員/建立者。 Persistent Chat 系統管理員也可以新增 DeniedMembers 至類別，而這些專案會變成對允許清單的明確排除。 DeniedMembers 覆寫 AllowedMembers 中的內容。

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a>舊群組聊天伺服器版本的聊天室內容有何不同？

Lync Server 2013，Persistent Chat Server 中已存在開放式聊天室的新概念。 所有允許的成員都可以加入聊天室，不需要獨佔成員資格。

已消除舊版 Persistent Chat Server 中包含的下列聊天室屬性：

  - 主題：聊天室現在只有描述。

  - 建立新的成員清單：在 Persistent Chat Server 中，所有聊天室都是以空成員資格 (，可以最大化至允許的成員) 的成員資格 equaling。

  - 檔案上傳：用於設定每個聊天室的設定，以控制是否允許檔案上傳/下載。 這現在只會設定類別層級，並套用至該類別中的所有聊天室。

  - 聊天記錄：用來控制聊天記錄是否已啟用，但現在只會在類別層級設定，並套用至該類別中的所有聊天室。

  - 邀請：會議室永遠繼承類別的 [邀請] 設定。您也可以在會議室上關閉此功能。 若類別以前已設為 [邀請]，會議室便無法開啟邀請。

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a>舊群組聊天伺服器版本的原則有何不同？

Persistent Chat Server 啟用新的 Lync 原則，具有持續聊天、每個使用者/集區/網站/全域設定。 在 Lync 2013 用戶端中，只有透過 (直接或透過「集區/網站/全域) 設定」原則啟用的持久聊天環境使用者才能使用 Persistent 聊天環境。

舊版的群組聊天伺服器沒有任何整合在 Lync Server 原則中的原則。 在每個使用者及每個類別/房間基礎上，使用 [ **可上傳** 每位使用者的檔案] 功能，您可以讓使用者成為使用者管理員、聊天室管理員或設定使用者上傳檔案的能力。 Persistent Chat Server **File 上傳** 功能僅限每個類別。

</div>

<div>

## <a name="logging"></a>記錄

Persistent Chat Server 和 System Center Operations Manager 記錄已整合至 Lync Server 2013 追蹤記錄。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中規劃 Persistent Chat Server](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
