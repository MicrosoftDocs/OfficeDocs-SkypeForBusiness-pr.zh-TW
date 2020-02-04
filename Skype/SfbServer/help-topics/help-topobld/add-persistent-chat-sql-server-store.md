---
title: 新增常設聊天室 SQL Server 儲存區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: 您設定的 SQL Server 存儲將提供持久聊天伺服器或持久聊天伺服器池的資料庫。
ms.openlocfilehash: 794ad4a1b5427fab7a8409fbbbd76448c33e918e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685056"
---
# <a name="add-persistent-chat-sql-server-store"></a>新增常設聊天室 SQL Server 儲存區
 
您設定的 SQL Server 存儲將提供持久聊天伺服器或持久聊天伺服器池的資料庫。
  
 **SQL server store**：選取現有的 SQL Server，並選擇性地使用持久聊天的實例。
  
按一下 [**新增**] 以定義新的 SQL Server，以及可選擇的持續聊天資料的新實例。
  
選取 [**啟用 SQL server store 鏡像**] 核取方塊，以設定 sql Server 資料庫及可為持續聊天資料提供鏡像資料庫的選用實例。
  
從清單中選取 [**鏡像 Sql server** ]，將 sql server 和選用實例當作持久聊天 sql SERVER 的 sql server 鏡像。
  
按一下 [**新增**] 來定義新的 SQL server，也可以選擇使用持久聊天 SQL server 鏡像的新實例。
  
選取 [使用 SQL Server 鏡像見證啟用自動容錯移轉]**** 清單，此 SQL Server 會在容錯移轉案例中擔任見證伺服器。 見證伺服器不會針對持久聊天伺服器進行鏡像或主機資料，但可確保鏡像配置中只有一個 SQL Server 在任何時候都是作用中的 SQL 伺服器。
  
按一下 [**新增**] 以定義新的 SQL Server 見證（可選擇永久聊天 sql server 鏡像見證的實例）。
  
按 [上一步] **** 回到上一個集區定義對話方塊。
  
當您完成輸入此池之 SQL Server store 設定的選項並繼續進行持續聊天伺服器池定義時，請按 **[下一步]** 。
  
按一下 [取消]**** 捨棄所有變更，並結束 [定義新的常設聊天室集區精靈]****。
  
按一下 [說明]**** 存取即時線上說明，例如此頁面。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 2015 中規劃常設聊天室伺服器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[在商務用 Skype Server 2015 拓撲中新增持久聊天伺服器](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[常設聊天室伺服器的硬體與軟體需求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[商務用 Skype Server 2015 的拓撲基本知識](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[設定常設聊天室伺服器的高可用性和災害復原](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
