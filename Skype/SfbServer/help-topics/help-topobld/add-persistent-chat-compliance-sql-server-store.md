---
title: 新增常設聊天室規範 SQL Server 儲存區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: 您可以設定規范 SQL Server 存放區，以提供持久聊天伺服器或持久聊天伺服器合規性功能的資料庫。
ms.openlocfilehash: 64697fbe9783bbdf356a28882f7cf53e7e96ef94
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698068"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a>新增常設聊天室規範 SQL Server 儲存區
 
您可以設定規范 SQL Server 存放區，以提供持久聊天伺服器或持久聊天伺服器合規性功能的資料庫。
  
 **SQL server store**：選取現有的 SQL Server，並選擇性地使用持久聊天的實例。
  
按一下 [**新增**] 以定義新的 SQL Server，並選擇新的持久聊天合規性資料實例。
  
選取 [**啟用 SQL server store 鏡像**] 核取方塊，以設定 sql Server 資料庫及選用的實例，該範例會為持續性聊天規範資料提供鏡像資料庫。
  
從清單中選取 [**鏡像 Sql server** ]，將 sql server 和選用實例當作持久的聊天相容性 sql SERVER 的 sql server 鏡像。
  
按一下 [**新增**] 來定義新的 SQL server，也可以選擇使用持久聊天 SQL server 鏡像的新實例。
  
選取 [使用 SQL Server 鏡像見證啟用自動容錯移轉]**** 清單，此 SQL Server 會在容錯移轉案例中擔任見證伺服器。 見證伺服器不會針對持久聊天伺服器進行鏡像或主機資料，但可確保鏡像配置中只有一個 SQL Server 在任何時候都是作用中的 SQL 伺服器。
  
按一下 [**新增**] 以定義新的 SQL Server 見證（可選擇永久聊天相容性 sql server 鏡像見證的實例）。
  
按 [上一步] **** 回到上一個集區定義對話方塊。
  
當您完成輸入此池子的 [備份 SQL Server store 設定] 選項，然後繼續進行持續聊天伺服器池定義時，請按 **[下一步]** 。
  
按一下 [取消]**** 捨棄所有變更，並結束 [定義新的常設聊天室集區精靈]****。
  
按一下 [說明]**** 存取即時線上說明，例如此頁面。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 2015 中規劃常設聊天室伺服器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[常設聊天室伺服器的硬體與軟體需求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[設定常設聊天室伺服器的規範服務](../../manage/persistent-chat/configure-compliance.md)
