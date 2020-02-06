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
# <a name="persistent-chat-database-schema"></a>常設聊天室資料庫結構描述
 
這會在商務用 Skype Server 中記錄持續聊天資料庫的架構。
  
Persistent 聊天資料庫指的是對應到商務用 Skype Server 後端伺服器角色**PersistentChatStore** （對應于 mgc 資料庫）和**PersistentChatComplianceStore** （對應至 mgccomp 資料庫）的資料庫。 發佈此架構的目的是讓您建立查詢，並深入瞭解如何在聊天使用、作用中的聊天室、主要海報等上建立有用的報告。
  
> [!IMPORTANT]
> 我們保留要演化此架構的權利。 Microsoft 不會保證維持與此發佈架構完全後相容性的任何保證。 
  
請遵循下列最佳做法：
  
- 因為欄\*清單可能會增加，所以不支援 SELECT//。
    
- 不支援使用者產生的架構修改。
    
- 不支援寫入作業。
    
- 測試您在 representatively 大小的資料庫上建立的任何查詢，以確定查詢可以在某一層級執行，以符合您的需求。
    
## <a name="in-this-section"></a>本節內容

- [常設聊天室伺服器表格清單](list-of-persistent-chat-server-tables.md)
    
- [商務用 Skype Server 中的持續聊天伺服器合規性表格清單](list-of-persistent-chat-server-compliance-tables.md)
    
- [常設聊天室伺服器表格詳細資料](persistent-chat-server-table-details.md)
    
- [範例常設聊天室資料庫查詢](sample-persistent-chat-database-queries.md)
    

