---
title: 新增常設聊天室規範 SQL Server 存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: 您可以設定規范 SQL Server 儲存區，為 Persistent Chat Server 或 Persistent Chat Server 相容性功能提供資料庫。
ms.openlocfilehash: 748fe7a0798bc8e10d3d10832763d5c3e1f55648
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218684"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a>新增常設聊天室規範 SQL Server 存放區
 
您可以設定規范 SQL Server 儲存區，為 Persistent Chat Server 或 Persistent Chat Server 相容性功能提供資料庫。
  
 **SQL server 儲存區**：選取現有的 SQL Server，並選擇性地選取持久聊天的實例。
  
按一下 [ **新增** ] 可定義新的 SQL Server，並選擇性地定義 Persistent Chat 相容性資料的新實例。
  
選取 [ **啟用 Sql server 儲存區鏡像** ] 核取方塊可設定 sql server 資料庫和選用實例，為持久聊天規範資料提供鏡像資料庫。
  
從 [ **鏡像 Sql server 儲存區** ] 清單中，選取要充當持久聊天規範 sql SERVER 之 sql server 鏡像的 sql server 和選用實例。
  
按一下 [ **新增** ] 可定義新的 SQL server，並選擇性地定義 PERSISTENT Chat SQL server 鏡像的新實例。
  
選取 [使用 SQL Server 鏡像見證啟用自動容錯移轉]**** 清單，此 SQL Server 會在容錯移轉案例中擔任見證伺服器。 見證伺服器不會鏡像或裝載 Persistent 聊天伺服器的資料，但可確保鏡像設定中每次只有一部 SQL Server 成為使用中的 SQL Server。
  
按一下 [ **新增** ] 可定義新的 SQL server 見證，並選擇性地定義 Persistent Chat 相容性 SQL server 鏡像見證的實例。
  
按 [上一步]**** 回到上一個集區定義對話方塊。
  
完成輸入此集區之備份 SQL Server 儲存區設定的選項之後，按 **[下一步]** ，以繼續使用 Persistent Chat Server 集區定義。
  
按一下 [取消]**** 捨棄所有變更，並結束 [定義新的常設聊天室集區精靈]****。
  
按一下 [說明]**** 存取即時線上說明，例如此頁面。
  
## <a name="see-also"></a>請參閱

[在商務用 Skype Server 2015 中規劃 Persistent Chat Server](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[商務用 Skype 2015 Server 中的 Persistent Chat Server 的硬體和軟體需求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[在商務用 Skype Server 2015 中設定 Persistent Chat Server 的合規性服務](../../manage/persistent-chat/configure-compliance.md)
