---
title: 移除後端伺服器上的 SQL Server 執行個體與資料庫
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 移除所依賴的伺服器之後，或重新設定伺服器以使用另一個資料庫之後，就會移除 Microsoft SQL Server 的資料庫和實例。 當您淘汰目前的 SQL Server 或重新設定目前的伺服器時，您必須執行本主題中的程式，使其呈現資料庫已過時或無法使用。
ms.openlocfilehash: f9e942f1f5516c0bf3437dd3fc9e2dc25b4cc4236e3cffabbf07ff08dde1e404
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306206"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>移除後端伺服器上的 SQL Server 執行個體與資料庫

移除所依賴的伺服器之後，或重新設定伺服器以使用另一個資料庫之後，就會移除 Microsoft SQL Server 的資料庫和實例。 當您淘汰目前的 SQL Server 或重新設定目前的伺服器時，您必須執行本主題中的程式，使其呈現資料庫已過時或無法使用。
  
若要移除封存伺服器或監控伺服器的資料庫或實例，必須先移除伺服器角色。 同樣地，若要移除前端集區的實例或資料庫，您必須先移除或重新設定從屬伺服器角色。 不論是針對伺服器的組合資料庫或個別執行個體，這些程序都是一樣的。 組合資料庫並不會影響這些程序。
  
## <a name="in-this-section"></a>本節內容

- [移除前端集區的 SQL Server 資料庫](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [移除監控伺服器的 SQL Server 資料庫](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [移除封存伺服器的 SQL Server 資料庫](remove-the-sql-server-database-for-an-archiving-server.md)
    

