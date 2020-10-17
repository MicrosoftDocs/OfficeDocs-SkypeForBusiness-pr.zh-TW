---
title: Lync Server 2013： Persistent Chat 資料庫架構
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
ms.openlocfilehash: 0b393f9281c1bb1fc1072a541b33bbab2656dafb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524250"
---
# <a name="persistent-chat-database-schema-in-lync-server-2013"></a>Lync Server 2013 中的持久聊天資料庫架構

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-18_

這會在 Lync Server 2013 通訊軟體中記錄 Persistent Chat 資料庫的架構。

Persistent Chat 資料庫是指對應至 Lync Server 2013 後端伺服器角色的資料庫 **PersistentChatStore** (對應至 mgc 資料庫) 和 **PersistentChatComplianceStore** (對應于 mgccomp 資料庫) 。 發行此結構描述的目標是讓您能夠建立查詢，並深入了解建立關於交談使用方式、作用中聊天室、前幾名的張貼者等實用報告的資訊。

<div>


> [!IMPORTANT]  
> 我們保留發展此結構描述的權利。Microsoft 不保證會維持此發行的結構描述之完整回溯相容性。



</div>

請遵循以下最佳做法：

  - \*因為 column 清單可能會成長，所以不支援 SELECT//。

  - 不支援使用者產生的結構描述修改。

  - 不支援寫入作業。

  - 測試您在典型大小之資料庫上建立的任何查詢，以確定查詢可以在符合您需求的層級上執行。

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中的 Persistent Chat Server 表格清單](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Lync Server 2013 中的 Persistent Chat Server 相容性資料表清單](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [Lync Server 2013 中的持久聊天伺服器表格詳細資料](lync-server-2013-persistent-chat-server-table-details.md)

  - [Lync Server 2013 的持久聊天資料庫查詢範例](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

