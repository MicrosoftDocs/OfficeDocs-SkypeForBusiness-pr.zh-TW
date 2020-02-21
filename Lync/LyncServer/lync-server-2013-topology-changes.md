---
title: Lync Server 2013 拓撲變更
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
ms.openlocfilehash: ac7cf9fe1bdabcba4b0b5fc1134f1835407041a5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a>Lync Server 2013 中的拓撲變更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-02_

Lync Server 2013 的拓撲需求及考量是不同於舊版，如本節所述。

<div>

## <a name="new-front-end-pools-architecture"></a>新的前端集區架構

在 [Lync Server 2013 Enterprise Edition 前端集區的架構已變更為分散式的系統架構。

使用此新的架構後, 端資料庫不再是集區中的即時資料存放區。 三個前端伺服器集區中，會保留特定使用者的相關資訊。 每位使用者，一部前端伺服器做為該使用者的資訊之母片及兩個其他前端伺服器做為複本。 前端伺服器停機時，另一個前端伺服器可作為複本是否會自動升級至母片。

發生在幕後這種情況，系統管理員不需要知道哪些前端伺服器是哪一個使用者的母片。 此通訊群組的資料存放區提升效能與延展性內集區，並且消除單一的單一後端伺服器的失敗點。

後端伺服器會擔任使用者與會議資料的備份儲存區，同時也是回應群組資料庫等其他資料庫的主要儲存區。

這些改良功能也表示您如何規劃和維護您的集區中有變更。 我們建議所有 Enterprise Edition 前端集區都包含至少三個前端伺服器，以提供完整的數字的前端集區架構針對所設計的複本。 此外，您必須遵循特定程序將伺服器新增至前端集區時移除伺服器或伺服器升級。 如需詳細資訊，請參閱[前端伺服器、 立即訊息和 Lync Server 2013 中的目前狀態的元件和拓撲](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。

<div>

## <a name="server-role-topology-changes"></a>伺服器角色拓撲變更

先前在個別伺服器執行的某些伺服器角色現在已合併成前端伺服器角色，讓您節省硬體成本

  - 在 Lync Server 2013 中，A / V 會議伺服器一律與前端伺服器組合。

  - 監控和封存的前端現在一律組合與前端伺服器。 監控和封存每個仍需要個別的後端資料庫，其中可以組合在相同的前端集區的後端資料庫伺服器上，或可以架設在不同的後端伺服器上。

  - Persistent Chat Server 現在是一個伺服器角色。 在 [Microsoft Lync Server 2010，Group Chat 伺服器已 Microsoft Lync Server 2010 的協力廠商信任應用程式。 在 Lync Server 2013，Persistent Chat Server 功能被實作使用三個新的伺服器角色：
    
      - **PersistentChatService:** 實作為前端角色的主要 Persistent Chat Server 服務
    
      - **PersistentChatStore:** 後端伺服器角色
    
      - **PersistentChatComplianceStore:** 常設聊天室規範後端伺服器角色

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

