---
title: Lync Server 2013 拓撲變更
description: Lync Server 2013 拓撲變更。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 562766eae939e4510a0d3af20e40b4731c361040
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549099"
---
# <a name="topology-changes-in-lync-server-2013"></a>Lync Server 2013 中的拓撲變更

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

Lync Server 2013 的拓撲需求和考慮，與舊版版本不同，如本節所述。

<div>

## <a name="new-front-end-pools-architecture"></a>新的前端集區架構

在 Lync Server 2013 中，Enterprise Edition 前端集區的架構已變更為分散式系統架構。

在這個新的架構中，後端資料庫不再是集區中的即時資料存放區。 特定使用者的資訊會保存在集區中的三部前端伺服器上。 針對每位使用者，一部前端伺服器充當該使用者資訊的主圖形，其他兩部前端伺服器充當複本。 如果前端伺服器宕機，另一部充當複本的前端伺服器會自動升級為主伺服器。

這種情況會發生在幕後，管理員不需要知道哪些前端伺服器是其主圖形的使用者。 這種資料儲存的散佈可改善集區中的效能與擴充性，並消除單一後端伺服器的單一失敗點。

後端伺服器充當使用者和會議資料的備份儲存區，也是其他資料庫（如回應群組資料庫）的主要儲存區。

這些改進也表示您規劃及維護集區的方式有所變更。 建議您的所有 Enterprise Edition 前端集區至少都包含三部前端伺服器，以提供為其設計前端集區架構的完整複本數目。 此外，您必須在將伺服器新增至前端集區、移除伺服器或升級伺服器時，遵循某些程式。 如需詳細資訊，請參閱 [Lync Server 2013 中的前端伺服器、立即訊息及顯示狀態的拓撲和元件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。

<div>

## <a name="server-role-topology-changes"></a>伺服器角色拓撲變更

先前在個別伺服器上執行的一些伺服器角色現在已合併成前端伺服器角色，可讓您儲存硬體成本。

  - 在 Lync Server 2013 中，A/V 會議伺服器永遠會與前端伺服器組合。

  - 監視與封存的前端現在永遠都是與前端伺服器組合。 監視和封存每個仍然需要個別的 Back-End 資料庫，此資料庫可以與前端集區的後端資料庫在同一部伺服器上組合，也可以位於不同的 Back-End 伺服器上。

  - Persistent Chat Server 現在是一個伺服器角色。 在 Microsoft Lync Server 2010 中，Group Chat Server 是協力廠商信任的 Microsoft Lync Server 2010 應用程式。 在 Lync Server 2013 中，Persistent Chat Server 功能是使用三種新的伺服器角色來執行：
    
      - **PersistentChatService：** 以前端角色形式實現的主要 Persistent Chat Server 服務
    
      - **PersistentChatStore：** 後端伺服器角色
    
      - **PersistentChatComplianceStore：** 持久聊天相容性的後端伺服器角色

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

