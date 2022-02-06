---
title: 常設聊天室資料庫結構描述
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: 這會在商務用 Skype Server 中記錄 Persistent Chat 資料庫的架構。
---

# <a name="persistent-chat-database-schema"></a>常設聊天室資料庫結構描述
 
這會在商務用 Skype Server 中記錄 Persistent Chat 資料庫的架構。
  
Persistent Chat 資料庫是指對應于商務用 Skype Server 後端伺服器角色 **PersistentChatStore** (相對於 mgccomp 資料庫) 的 mgc 資料庫) 和 **PersistentChatComplianceStore** (的資料庫。 發行此結構描述的目標是讓您能夠建立查詢，並深入了解建立關於交談使用方式、作用中聊天室、前幾名的張貼者等實用報告的資訊。
  
> [!IMPORTANT]
> 我們保留發展此結構描述的權利。Microsoft 不保證會維持此發行的結構描述之完整回溯相容性。 
  
請遵循以下最佳做法：
  
- 因為 column 清單可能會成長，所以不支援 SELECT \* //。
    
- 不支援使用者產生的結構描述修改。
    
- 不支援寫入作業。
    
- 測試您在典型大小之資料庫上建立的任何查詢，以確定查詢可以在符合您需求的層級上執行。
    
## <a name="in-this-section"></a>本節內容

- [常設聊天室伺服器表格清單](list-of-persistent-chat-server-tables.md)
    
- [商務用 Skype Server 中的 Persistent Chat Server 相容性資料表清單](list-of-persistent-chat-server-compliance-tables.md)
    
- [常設聊天室伺服器表格詳細資料](persistent-chat-server-table-details.md)
    
- [範例常設聊天室資料庫查詢](sample-persistent-chat-database-queries.md)
    

