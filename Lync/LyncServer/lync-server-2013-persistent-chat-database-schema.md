---
title: Lync Server 2013：常設聊天室資料庫結構描述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat database schema
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48184228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73f3b21fe8ea7f9fc71aa5432a601e9fa3ad2425
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a>Lync Server 2013 中的常設聊天室資料庫結構描述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-18_

這會在 Lync Server 2013 通訊軟體中記錄持續聊天資料庫的架構。

Persistent 聊天資料庫指的是與 Lync Server 2013 後端伺服器角色**PersistentChatStore** （對應至 mgc 資料庫）和**PersistentChatComplianceStore** （與 mgccomp 資料庫對應）對應的資料庫。 發佈此架構的目的是讓您建立查詢，並深入瞭解如何在聊天使用、作用中的聊天室、主要海報等上建立有用的報告。

<div>


> [!IMPORTANT]  
> 我們保留要演化此架構的權利。 Microsoft 不會保證維持與此發佈架構完全後相容性的任何保證。



</div>

請遵循下列最佳做法：

  - 因為欄\*清單可能會增加，所以不支援 SELECT//。

  - 不支援使用者產生的架構修改。

  - 不支援寫入作業。

  - 測試您在 representatively 大小的資料庫上建立的任何查詢，以確定查詢可以在某一層級執行，以符合您的需求。

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中的常設聊天室伺服器清單表格](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Lync Server 2013 中常設聊天室伺服器規範表的清單](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [Lync Server 2013 中的常設聊天室伺服器表格詳細資料](lync-server-2013-persistent-chat-server-table-details.md)

  - [Lync Server 2013 的常設聊天室資料庫查詢範例](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

