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
ms.openlocfilehash: c4453a9b5b8a5fcd60eaad1e437fd4800caddfba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a>Lync Server 2013 中的拓撲變更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

Lync Server 2013 的拓撲需求和考慮與舊版版本不同，如本節所述。

<div>

## <a name="new-front-end-pools-architecture"></a>新的前端池架構

在 Lync Server 2013 中，企業版前端池的架構已變更為分散式系統架構。

使用這個新的架構，後端資料庫就不再是池中的即時資料存放區。 特定使用者的相關資訊會保留在池中的三個前端伺服器上。 針對每位使用者，一個前端伺服器充當該使用者資訊的主版，而其他兩個前端伺服器則充當複本。 如果前端伺服器發生故障，另一個作為複本的前端伺服器會自動升級至 [主版]。

這會在幕後發生，而系統管理員不需要知道哪些前端伺服器是使用者的主機。 這種資料儲存的發佈可改善池中的效能和可伸縮性，並消除單一後端伺服器的單一故障點。

後端伺服器充當使用者與會議資料的備份儲存空間，也是其他資料庫（例如回應群組資料庫）的主要儲存空間。

這些改良也表示您規劃及維護您的池的方式有何變更。 我們建議您所有的企業版前端池都包含至少三個前端伺服器，以提供最多可供設計的最大複本數。 此外，您必須遵循將伺服器新增到前端池、移除伺服器或升級伺服器的特定程式。 如需詳細資訊，請參閱[Lync Server 2013 中前端伺服器、立即訊息和目前狀態的拓撲與元件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。

<div>

## <a name="server-role-topology-changes"></a>伺服器角色拓朴變更

先前在個別伺服器上執行的一些伺服器角色現在已整合至前端伺服器角色，可讓您儲存硬體成本

  - 在 Lync Server 2013 中，A/V 會議伺服器總是與前端伺服器 collocated。

  - 監視和封存的前端現在總是與前端伺服器 collocated。 監視及封存每個仍需要個別的後端資料庫，這可以在與前端池的後端資料庫相同的伺服器上 collocated，也可以裝載在不同的後端伺服器上。

  - 持續聊天伺服器現在是一個伺服器角色。 在 Microsoft Lync Server 2010 中，群組聊天伺服器是適用于 Microsoft Lync Server 2010 的協力廠商信任應用程式。 在 Lync Server 2013 中，持續聊天伺服器功能是使用三個新的伺服器角色來實現：
    
      - **PersistentChatService：** 以前端角色形式實現的主要持久聊天伺服器服務
    
      - **PersistentChatStore：** 後端伺服器角色
    
      - **PersistentChatComplianceStore：** 持久的聊天合規性的後端伺服器角色

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

