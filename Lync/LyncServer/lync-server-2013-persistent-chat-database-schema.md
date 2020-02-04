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

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a><span data-ttu-id="a1869-102">Lync Server 2013 中的常設聊天室資料庫結構描述</span><span class="sxs-lookup"><span data-stu-id="a1869-102">Persistent Chat database schema in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1869-103">_**主題上次修改日期：** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="a1869-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="a1869-104">這會在 Lync Server 2013 通訊軟體中記錄持續聊天資料庫的架構。</span><span class="sxs-lookup"><span data-stu-id="a1869-104">This documents the schema of the Persistent Chat database in Lync Server 2013 communications software.</span></span>

<span data-ttu-id="a1869-105">Persistent 聊天資料庫指的是與 Lync Server 2013 後端伺服器角色**PersistentChatStore** （對應至 mgc 資料庫）和**PersistentChatComplianceStore** （與 mgccomp 資料庫對應）對應的資料庫。</span><span class="sxs-lookup"><span data-stu-id="a1869-105">The Persistent Chat database refers to the database corresponding to the Lync Server 2013 Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="a1869-106">發佈此架構的目的是讓您建立查詢，並深入瞭解如何在聊天使用、作用中的聊天室、主要海報等上建立有用的報告。</span><span class="sxs-lookup"><span data-stu-id="a1869-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a1869-107">我們保留要演化此架構的權利。</span><span class="sxs-lookup"><span data-stu-id="a1869-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="a1869-108">Microsoft 不會保證維持與此發佈架構完全後相容性的任何保證。</span><span class="sxs-lookup"><span data-stu-id="a1869-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span>



</div>

<span data-ttu-id="a1869-109">請遵循下列最佳做法：</span><span class="sxs-lookup"><span data-stu-id="a1869-109">Follow these best practices:</span></span>

  - <span data-ttu-id="a1869-110">因為欄\*清單可能會增加，所以不支援 SELECT//。</span><span class="sxs-lookup"><span data-stu-id="a1869-110">No SELECT\* // is supported because the column list can grow.</span></span>

  - <span data-ttu-id="a1869-111">不支援使用者產生的架構修改。</span><span class="sxs-lookup"><span data-stu-id="a1869-111">No user-generated schema modifications are supported.</span></span>

  - <span data-ttu-id="a1869-112">不支援寫入作業。</span><span class="sxs-lookup"><span data-stu-id="a1869-112">No write operations are supported.</span></span>

  - <span data-ttu-id="a1869-113">測試您在 representatively 大小的資料庫上建立的任何查詢，以確定查詢可以在某一層級執行，以符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="a1869-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a1869-114">本節內容</span><span class="sxs-lookup"><span data-stu-id="a1869-114">In This Section</span></span>

  - [<span data-ttu-id="a1869-115">Lync Server 2013 中的常設聊天室伺服器清單表格</span><span class="sxs-lookup"><span data-stu-id="a1869-115">List of Persistent Chat Server tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [<span data-ttu-id="a1869-116">Lync Server 2013 中常設聊天室伺服器規範表的清單</span><span class="sxs-lookup"><span data-stu-id="a1869-116">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [<span data-ttu-id="a1869-117">Lync Server 2013 中的常設聊天室伺服器表格詳細資料</span><span class="sxs-lookup"><span data-stu-id="a1869-117">Persistent Chat Server table details in Lync Server 2013</span></span>](lync-server-2013-persistent-chat-server-table-details.md)

  - [<span data-ttu-id="a1869-118">Lync Server 2013 的常設聊天室資料庫查詢範例</span><span class="sxs-lookup"><span data-stu-id="a1869-118">Sample Persistent Chat database queries for Lync Server 2013</span></span>](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

