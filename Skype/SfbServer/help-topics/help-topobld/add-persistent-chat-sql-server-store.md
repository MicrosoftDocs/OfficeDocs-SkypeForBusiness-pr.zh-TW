---
title: 新增常設聊天室 SQL Server 存放區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: 設定會為 Persistent Chat Server 或 Persistent Chat Server 集區提供資料庫的 SQL Server 存放區。
ms.openlocfilehash: e93705e0646f1115994a61c936a5c0cb16149dfa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818653"
---
# <a name="add-persistent-chat-sql-server-store"></a>新增常設聊天室 SQL Server 存放區
 
設定會為 Persistent Chat Server 或 Persistent Chat Server 集區提供資料庫的 SQL Server 存放區。
  
 **SQL server 儲存區**：選取現有的 SQL Server，並選擇性地選取持久聊天的實例。
  
按一下 [ **新增** ] 可定義新的 SQL Server，並選擇性地定義持久聊天資料的新實例。
  
選取 [ **啟用 SQL server 儲存區鏡像** ] 核取方塊可設定 sql server 資料庫和選用實例，為持久聊天資料提供鏡像資料庫。
  
從 [ **鏡像 Sql server 儲存區** ] 清單中，選取要充當 PERSISTENT Chat sql SERVER 之 sql server 鏡像的 sql server 和選用實例。
  
按一下 [ **新增** ] 可定義新的 SQL server，並選擇性地定義 PERSISTENT Chat SQL server 鏡像的新實例。
  
選取 [使用 SQL Server 鏡像見證啟用自動容錯移轉] 清單，此 SQL Server 會在容錯移轉案例中擔任見證伺服器。 見證伺服器不會鏡像或裝載 Persistent 聊天伺服器的資料，但可確保鏡像設定中每次只有一部 SQL Server 成為使用中的 SQL Server。
  
按一下 [ **新增** ] 可定義新的 SQL server 見證，並選擇性地定義 PERSISTENT Chat SQL server 鏡像見證的實例。
  
按 [上一步] 回到上一個集區定義對話方塊。
  
完成輸入集區之 SQL Server 儲存區設定的選項之後，按 **[下一步]** ，繼續執行 Persistent Chat Server 集區定義。
  
按一下 [取消] 捨棄所有變更，並結束 [定義新的常設聊天室集區精靈]。
  
按一下 [說明] 存取即時線上說明，例如此頁面。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 2015 中規劃 Persistent Chat Server](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[將 Persistent Chat Server 新增至您的商務用 Skype Server 2015 拓撲](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[商務用 Skype 2015 Server 中的 Persistent Chat Server 的硬體和軟體需求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[商務用 Skype Server 2015 的拓撲基礎](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[在商務用 Skype Server 2015 中設定 Persistent Chat Server 的高可用性和嚴重損壞修復](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
