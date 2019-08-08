---
title: 移除後端伺服器上的 SQL Server 實例和資料庫
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 移除依賴這些伺服器的伺服器, 或在您重新設定伺服器以使用其他資料庫之後, 移除 Microsoft SQL Server 資料庫和實例。 當您淘汰目前的 SQL Server, 或以其呈現資料庫過時或無法使用的方式來重新設定目前伺服器時, 您必須執行本主題中的程式。
ms.openlocfilehash: 6c526499e3036c9a10b8dc92ccc519f21ae8bc96
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244433"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>移除後端伺服器上的 SQL Server 實例和資料庫

移除依賴這些伺服器的伺服器, 或在您重新設定伺服器以使用其他資料庫之後, 移除 Microsoft SQL Server 資料庫和實例。 當您淘汰目前的 SQL Server, 或以其呈現資料庫過時或無法使用的方式來重新設定目前伺服器時, 您必須執行本主題中的程式。
  
若要移除存檔伺服器或監視伺服器的資料庫或實例, 您必須先移除伺服器角色。 同樣地, 若要移除前臺端池的實例或資料庫, 您必須先移除或重新設定相依伺服器角色。 這些程式不會區分 collocated 資料庫或伺服器的個別實例。 程式不會受到資料庫 collocation 的影響。
  
## <a name="in-this-section"></a>本節內容

- [移除前端池的 SQL Server 資料庫](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [移除監視伺服器的 SQL Server 資料庫](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [移除存檔伺服器的 SQL Server 資料庫](remove-the-sql-server-database-for-an-archiving-server.md)
    

