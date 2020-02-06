---
title: 常設聊天室資料庫結構描述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: 這會在商務用 Skype Server 中記錄持續聊天資料庫的架構。
ms.openlocfilehash: b042f4490648760f4750e45fa1e35e032a8bf8b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814741"
---
# <a name="persistent-chat-database-schema"></a><span data-ttu-id="6ef54-103">常設聊天室資料庫結構描述</span><span class="sxs-lookup"><span data-stu-id="6ef54-103">Persistent Chat database schema</span></span>
 
<span data-ttu-id="6ef54-104">這會在商務用 Skype Server 中記錄持續聊天資料庫的架構。</span><span class="sxs-lookup"><span data-stu-id="6ef54-104">This documents the schema of the Persistent Chat database in Skype for Business Server.</span></span>
  
<span data-ttu-id="6ef54-105">Persistent 聊天資料庫指的是對應到商務用 Skype Server 後端伺服器角色**PersistentChatStore** （對應于 mgc 資料庫）和**PersistentChatComplianceStore** （對應至 mgccomp 資料庫）的資料庫。</span><span class="sxs-lookup"><span data-stu-id="6ef54-105">The Persistent Chat database refers to the database corresponding to the Skype for Business Server Back End Server roles **PersistentChatStore** (corresponding to the mgc database) and **PersistentChatComplianceStore** (corresponding to the mgccomp database).</span></span> <span data-ttu-id="6ef54-106">發佈此架構的目的是讓您建立查詢，並深入瞭解如何在聊天使用、作用中的聊天室、主要海報等上建立有用的報告。</span><span class="sxs-lookup"><span data-stu-id="6ef54-106">The goal of publishing this schema is to enable you to build queries and gain some insights into building useful reporting around chat usage, active rooms, top posters, and so on.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6ef54-107">我們保留要演化此架構的權利。</span><span class="sxs-lookup"><span data-stu-id="6ef54-107">We reserve the right to evolve this schema.</span></span> <span data-ttu-id="6ef54-108">Microsoft 不會保證維持與此發佈架構完全後相容性的任何保證。</span><span class="sxs-lookup"><span data-stu-id="6ef54-108">Microsoft does not make any guarantees to maintain full backward compatibility with this published schema.</span></span> 
  
<span data-ttu-id="6ef54-109">請遵循下列最佳做法：</span><span class="sxs-lookup"><span data-stu-id="6ef54-109">Follow these best practices:</span></span>
  
- <span data-ttu-id="6ef54-110">因為欄\*清單可能會增加，所以不支援 SELECT//。</span><span class="sxs-lookup"><span data-stu-id="6ef54-110">No SELECT\* // is supported because the column list can grow.</span></span>
    
- <span data-ttu-id="6ef54-111">不支援使用者產生的架構修改。</span><span class="sxs-lookup"><span data-stu-id="6ef54-111">No user-generated schema modifications are supported.</span></span>
    
- <span data-ttu-id="6ef54-112">不支援寫入作業。</span><span class="sxs-lookup"><span data-stu-id="6ef54-112">No write operations are supported.</span></span>
    
- <span data-ttu-id="6ef54-113">測試您在 representatively 大小的資料庫上建立的任何查詢，以確定查詢可以在某一層級執行，以符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="6ef54-113">Test any queries that you build on representatively-sized databases to be sure that the queries can perform at a level to meet your needs.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="6ef54-114">本節內容</span><span class="sxs-lookup"><span data-stu-id="6ef54-114">In this section</span></span>

- [<span data-ttu-id="6ef54-115">常設聊天室伺服器表格清單</span><span class="sxs-lookup"><span data-stu-id="6ef54-115">List of Persistent Chat Server tables</span></span>](list-of-persistent-chat-server-tables.md)
    
- [<span data-ttu-id="6ef54-116">商務用 Skype Server 中的持續聊天伺服器合規性表格清單</span><span class="sxs-lookup"><span data-stu-id="6ef54-116">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>](list-of-persistent-chat-server-compliance-tables.md)
    
- [<span data-ttu-id="6ef54-117">常設聊天室伺服器表格詳細資料</span><span class="sxs-lookup"><span data-stu-id="6ef54-117">Persistent Chat Server table details</span></span>](persistent-chat-server-table-details.md)
    
- [<span data-ttu-id="6ef54-118">範例常設聊天室資料庫查詢</span><span class="sxs-lookup"><span data-stu-id="6ef54-118">Sample Persistent Chat database queries</span></span>](sample-persistent-chat-database-queries.md)
    

