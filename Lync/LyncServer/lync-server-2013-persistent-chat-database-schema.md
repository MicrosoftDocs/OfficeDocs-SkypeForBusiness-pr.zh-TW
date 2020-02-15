---
title: Lync Server 2013： 常設聊天室資料庫結構描述
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
ms.openlocfilehash: 51ee4506a22d866a5ba0f771db47546a8fa15e6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006911"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a>在 [Lync Server 2013 常設聊天室資料庫結構描述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-18_

本主題記載 Lync Server 2013 通訊軟體常設聊天室資料庫結構的描述。

**PersistentChatStore** （對應至 [mgc] 資料庫） 和**PersistentChatComplianceStore** （對應至 mgccomp 資料庫），常設聊天室資料庫會參照到對應至 Lync Server 2013 後端伺服器角色的資料庫。 發行此結構描述的目標是讓您能夠建立查詢，並深入了解建立關於交談使用方式、作用中聊天室、前幾名的張貼者等實用報告的資訊。

<div>


> [!IMPORTANT]  
> 我們保留發展此結構描述的權利。Microsoft 不保證會維持此發行的結構描述之完整回溯相容性。



</div>

請遵循以下最佳做法：

  - 沒有選取\*/ / 因為欄清單可以擴充支援。

  - 不支援使用者產生的結構描述修改。

  - 不支援寫入作業。

  - 測試您在典型大小之資料庫上建立的任何查詢，以確定查詢可以在符合您需求的層級上執行。

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 常設聊天室伺服器資料表的清單](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Lync Server 2013 中的常設聊天室伺服器規範表格清單](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [在 Lync Server 2013 常設聊天室伺服器資料表詳細資料](lync-server-2013-persistent-chat-server-table-details.md)

  - [常設聊天室資料庫查詢範例針對 Lync Server 2013](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

