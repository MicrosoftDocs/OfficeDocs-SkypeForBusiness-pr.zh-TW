---
title: 新增常設聊天室備份 SQL Server 儲存區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: 您可以設定備份 SQL Server 存放區，以提供持久聊天伺服器或持久聊天伺服器池的備份資料庫。
ms.openlocfilehash: 0f8fe19d95adff9e2ac538600f3dcf5153c25afd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820705"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a>新增常設聊天室備份 SQL Server 儲存區
 
您可以設定備份 SQL Server 存放區，以提供持久聊天伺服器或持久聊天伺服器池的備份資料庫。
  
 **SQL server store**：選取現有的 SQL Server，並選擇性地使用持久聊天的實例。
  
按一下 [**新增**] 以定義新的 SQL Server，以及可選擇的持續聊天備份資料的新實例。
  
選取 [**啟用 SQL server store 鏡像**] 核取方塊，以設定 sql Server 資料庫及選用的實例，該範例會提供持續聊天備份資料的鏡像資料庫。
  
從清單中選取 [**鏡像 Sql server** ]，將 sql server 和選用實例當作持續聊天備份 sql SERVER 的 sql server 鏡像。
  
按一下 [**新增**] 來定義新的 SQL server，也可以選擇使用持久聊天 SQL server 鏡像的新實例。
  
選取 [使用 SQL Server 鏡像見證啟用自動容錯移轉]**** 清單，此 SQL Server 會在容錯移轉案例中擔任見證伺服器。 見證伺服器不會針對持久聊天伺服器進行鏡像或主機資料，但可確保鏡像配置中只有一個 SQL Server 在任何時候都是作用中的 SQL 伺服器。
  
按一下 [**新增**] 以定義新的 SQL Server 見證（可選擇永久聊天備份 sql server 鏡像見證的實例）。
  
按 [上一步] **** 回到上一個集區定義對話方塊。
  
當您完成輸入此池子的 [備份 SQL Server store 設定] 選項，然後繼續進行持續聊天伺服器池定義時，請按 **[下一步]** 。
  
按一下 [取消]**** 捨棄所有變更，並結束 [定義新的常設聊天室集區精靈]****。
  
按一下 [說明]**** 存取即時線上說明，例如此頁面。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 2015 中規劃常設聊天室伺服器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[常設聊天室伺服器的硬體與軟體需求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[設定常設聊天室伺服器的高可用性和災害復原](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
