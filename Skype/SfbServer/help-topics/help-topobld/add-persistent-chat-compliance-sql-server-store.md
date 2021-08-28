---
title: 新增常設聊天室規範 SQL Server 存放區
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
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: 您可以設定規范 SQL Server 儲存區，將會為 persistent chat server 或 persistent chat server 相容性功能提供資料庫。
ms.openlocfilehash: 09138c2e6a5fb23b6745a5594c231d29c13b911b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615759"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a>新增常設聊天室規範 SQL Server 存放區
 
您可以設定規范 SQL Server 儲存區，將會為 persistent chat server 或 persistent chat server 相容性功能提供資料庫。
  
 **SQL Server 儲存區**：選取現有 SQL Server，並選擇性地為持久聊天的實例。
  
按一下 [**新增**] 可定義新的 SQL Server，並選擇性地定義 Persistent Chat 相容性資料的新實例。
  
選取 [**啟用 SQL Server 儲存區鏡像**] 核取方塊，以設定 SQL Server 資料庫和選用實例，將會為持久聊天規範資料提供鏡像資料庫。
  
從 [鏡像] 清單中選取 [**鏡像] SQL Server 儲存** SQL Server 和選用實例，以充當持久聊天規範 SQL Server 的 SQL Server 鏡像。
  
按一下 [**新增**] 可定義新的 SQL Server，並選擇性地定義持久聊天 SQL Server 鏡像的新實例。
  
選取 [使用 SQL Server 鏡像見證啟用自動容錯移轉] 清單，此 SQL Server 會在容錯移轉案例中擔任見證伺服器。 見證伺服器不會鏡像或裝載 Persistent 聊天伺服器的資料，但可確保在任何時間，鏡像設定中只有一個 SQL Server 使用中 SQL Server。
  
按一下 [**新增**] 可定義新的 SQL Server 見證，並選擇性地定義 Persistent Chat 規章 SQL Server 鏡像見證的實例。
  
按 [上一步] 回到上一個集區定義對話方塊。
  
完成輸入此集區之備份的選項後，請按 **[下一步]** SQL Server 儲存設定，然後繼續使用 Persistent Chat Server 集區定義。
  
按一下 [取消] 捨棄所有變更，並結束 [定義新的常設聊天室集區精靈]。
  
按一下 [說明] 存取即時線上說明，例如此頁面。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 2015 中規劃 Persistent Chat Server](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[商務用 Skype Server 2015 中的 Persistent Chat Server 的硬體和軟體需求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[在商務用 Skype Server 2015 中設定 Persistent Chat Server 的規範服務](../../manage/persistent-chat/configure-compliance.md)
