---
title: 新增常設聊天室備份 SQL Server 儲存區
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: 您可以設定備份 SQL Server 儲存區，將會為 persistent chat server 或 persistent chat server 集區提供備份資料庫。
ms.openlocfilehash: 447e1005cc2ac5cc4783a38094e5de8b84a53cc3
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395715"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a>新增常設聊天室備份 SQL Server 儲存區
 
您可以設定備份 SQL Server 儲存區，將會為 persistent chat server 或 persistent chat server 集區提供備份資料庫。
  
 **SQL Server 儲存區**：選取現有 SQL Server，並選擇性地為持久聊天的實例。
  
按一下 [**新增**] 可定義新的 SQL Server，並選擇性地定義持久聊天備份資料的新實例。
  
選取 [**啟用 SQL Server 儲存區鏡像**] 核取方塊，以設定 SQL Server 資料庫和選用實例，將會為持久聊天備份資料提供鏡像資料庫。
  
從 [鏡像] 清單中選取 [**鏡像] SQL Server 儲存** SQL Server 和選用實例做為持久聊天備份 SQL Server 的 SQL Server 鏡像。
  
按一下 [**新增**] 可定義新的 SQL Server，並選擇性地定義持久聊天 SQL Server 鏡像的新實例。
  
選取 [使用 SQL Server 鏡像見證啟用自動容錯移轉] 清單，此 SQL Server 會在容錯移轉案例中擔任見證伺服器。 見證伺服器不會鏡像或裝載 Persistent 聊天伺服器的資料，但可確保在任何時間，鏡像設定中只有一個 SQL Server 使用中 SQL Server。
  
按一下 [**新增**] 可定義新的 SQL Server 見證，並選擇性地定義 Persistent Chat backup SQL Server 鏡像見證的實例。
  
按 [上一步] 回到上一個集區定義對話方塊。
  
完成輸入此集區之備份的選項後，請按 **[下一步]** SQL Server 儲存設定，然後繼續使用 Persistent Chat Server 集區定義。
  
按一下 [取消] 捨棄所有變更，並結束 [定義新的常設聊天室集區精靈]。
  
按一下 [說明] 存取即時線上說明，例如此頁面。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 2015 中規劃 Persistent Chat Server](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[商務用 Skype Server 2015 中的 Persistent Chat Server 的硬體和軟體需求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[在商務用 Skype Server 2015 中設定 Persistent Chat Server 的高可用性和嚴重損壞修復](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
