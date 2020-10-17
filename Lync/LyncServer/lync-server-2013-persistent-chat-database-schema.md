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
# <a name="persistent-chat-database-schema-in-lync-server-2013"></a><span data-ttu-id="9a084-102">Lync Server 2013 中的持久聊天資料庫架構</span><span class="sxs-lookup"><span data-stu-id="9a084-102">Persistent Chat database schema in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a084-103">_**主題上次修改日期：** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="9a084-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="9a084-104">這會在 Lync Server 2013 通訊軟體中記錄 Persistent Chat 資料庫的架構。</span><span class="sxs-lookup"><span data-stu-id="9a084-104">This documents the schema of the Persistent Chat database in Lync Server 2013 communications software.</span></span>

<span data-ttu-id="9a084-105">Persistent Chat 資料庫是指對應至 Lync Server 2013 後端伺服器角色的資料庫 **PersistentChatStore** (對應至 mgc 資料庫) 和 **PersistentChatComplianceStore** (對應于 mgccomp 資料庫) 。</span><span class="sxs-lookup"><span data-stu-id="9a084-105">The Persistent Chat database refers to the database corresponding to the Lync Server 2013 Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="9a084-106">發行此結構描述的目標是讓您能夠建立查詢，並深入了解建立關於交談使用方式、作用中聊天室、前幾名的張貼者等實用報告的資訊。</span><span class="sxs-lookup"><span data-stu-id="9a084-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9a084-p102">我們保留發展此結構描述的權利。Microsoft 不保證會維持此發行的結構描述之完整回溯相容性。</span><span class="sxs-lookup"><span data-stu-id="9a084-p102">We reserve the right to evolve this schema. Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span>



</div>

<span data-ttu-id="9a084-109">請遵循以下最佳做法：</span><span class="sxs-lookup"><span data-stu-id="9a084-109">Follow these best practices:</span></span>

  - <span data-ttu-id="9a084-110">\*因為 column 清單可能會成長，所以不支援 SELECT//。</span><span class="sxs-lookup"><span data-stu-id="9a084-110">No SELECT\* // is supported because the column list can grow.</span></span>

  - <span data-ttu-id="9a084-111">不支援使用者產生的結構描述修改。</span><span class="sxs-lookup"><span data-stu-id="9a084-111">No user-generated schema modifications are supported.</span></span>

  - <span data-ttu-id="9a084-112">不支援寫入作業。</span><span class="sxs-lookup"><span data-stu-id="9a084-112">No write operations are supported.</span></span>

  - <span data-ttu-id="9a084-113">測試您在典型大小之資料庫上建立的任何查詢，以確定查詢可以在符合您需求的層級上執行。</span><span class="sxs-lookup"><span data-stu-id="9a084-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9a084-114">本章節內容</span><span class="sxs-lookup"><span data-stu-id="9a084-114">In This Section</span></span>

  - [<span data-ttu-id="9a084-115">Lync Server 2013 中的 Persistent Chat Server 表格清單</span><span class="sxs-lookup"><span data-stu-id="9a084-115">List of Persistent Chat Server tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [<span data-ttu-id="9a084-116">Lync Server 2013 中的 Persistent Chat Server 相容性資料表清單</span><span class="sxs-lookup"><span data-stu-id="9a084-116">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [<span data-ttu-id="9a084-117">Lync Server 2013 中的持久聊天伺服器表格詳細資料</span><span class="sxs-lookup"><span data-stu-id="9a084-117">Persistent Chat Server table details in Lync Server 2013</span></span>](lync-server-2013-persistent-chat-server-table-details.md)

  - [<span data-ttu-id="9a084-118">Lync Server 2013 的持久聊天資料庫查詢範例</span><span class="sxs-lookup"><span data-stu-id="9a084-118">Sample Persistent Chat database queries for Lync Server 2013</span></span>](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

