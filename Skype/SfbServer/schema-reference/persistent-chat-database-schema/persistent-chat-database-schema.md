---
title: 常設聊天室資料庫結構描述
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: 這會在商務用 Skype Server 中記錄 Persistent Chat 資料庫的架構。
ms.openlocfilehash: ba50f4391ce35d8a938318e96e1483bbfe0e3dfa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809873"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="bda48-103">常設聊天室資料庫結構描述</span><span class="sxs-lookup"><span data-stu-id="bda48-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="bda48-104">這會在商務用 Skype Server 中記錄 Persistent Chat 資料庫的架構。</span><span class="sxs-lookup"><span data-stu-id="bda48-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="bda48-105">Persistent Chat 資料庫是指對應于商務用 Skype Server 後端伺服器角色的資料庫 **PersistentChatStore** (，該資料庫對應于與 mgccomp 資料庫) 相對應的 mgc 資料庫) 和 **PersistentChatComplianceStore** (。</span><span class="sxs-lookup"><span data-stu-id="bda48-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="bda48-106">發行此結構描述的目標是讓您能夠建立查詢，並深入了解建立關於交談使用方式、作用中聊天室、前幾名的張貼者等實用報告的資訊。</span><span class="sxs-lookup"><span data-stu-id="bda48-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bda48-p102">我們保留發展此結構描述的權利。Microsoft 不保證會維持此發行的結構描述之完整回溯相容性。</span><span class="sxs-lookup"><span data-stu-id="bda48-p102">We reserve the right to evolve this schema. Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="bda48-109">請遵循以下最佳做法：</span><span class="sxs-lookup"><span data-stu-id="bda48-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="bda48-110">\*因為 column 清單可能會成長，所以不支援 SELECT//。</span><span class="sxs-lookup"><span data-stu-id="bda48-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="bda48-111">不支援使用者產生的結構描述修改。</span><span class="sxs-lookup"><span data-stu-id="bda48-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="bda48-112">不支援寫入作業。</span><span class="sxs-lookup"><span data-stu-id="bda48-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="bda48-113">測試您在典型大小之資料庫上建立的任何查詢，以確定查詢可以在符合您需求的層級上執行。</span><span class="sxs-lookup"><span data-stu-id="bda48-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="bda48-114">本節內容</span><span class="sxs-lookup"><span data-stu-id="bda48-114">In this section</span></span>

- [<span data-ttu-id="bda48-115">常設聊天室伺服器表格清單</span><span class="sxs-lookup"><span data-stu-id="bda48-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="bda48-116">商務用 Skype Server 中的 Persistent Chat Server 相容性資料表清單</span><span class="sxs-lookup"><span data-stu-id="bda48-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="bda48-117">常設聊天室伺服器表格詳細資料</span><span class="sxs-lookup"><span data-stu-id="bda48-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="bda48-118">範例常設聊天室資料庫查詢</span><span class="sxs-lookup"><span data-stu-id="bda48-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

