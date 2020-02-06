---
title: 常設聊天室一般設定展開工具
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
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 您可以透過設定或定義這些屬性來編輯持續聊天伺服器或持續聊天伺服器池的一般設定：
ms.openlocfilehash: d44818efa1909e0fd90e4c80fcd88b3d11a616ea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819475"
---
# <a name="persistent-chat-general-settings-expander"></a>常設聊天室一般設定展開工具
 
您可以透過設定或定義這些屬性來編輯持續聊天伺服器或持續聊天伺服器池的**一般**設定：
  
 **一般**
  
- **FQDN**：編輯此設定以定義持續聊天伺服器或持久聊天伺服器池的完整功能變數名稱
    
- **常設聊天室集區的顯示名稱**：定義此設定可為伺服器或集區提供使用者易記及易於讀取的設定。 這項設定可讓您的使用者更輕鬆地根據顯示名稱與指定的持續聊天伺服器或持續聊天伺服器池建立關聯，而不是更難瞭解完整的功能變數名稱。
    
- **常設聊天室連接埠**：指定用於常設聊天室的連接埠。
    
您可以透過設定或定義這些屬性來編輯持續聊天伺服器或持續聊天伺服器池的**關聯**設定：
  
 **關聯**
  
- **SQL Server 儲存區**：從清單中選取 SQL Server 儲存區和選用具名執行個體。
    
    按一下 [新增] **** 定義新的 SQL Server 儲存區和選用執行個體。
    
- 如果您想要為主要的 SQL Server 存放區啟用鏡像，請選取 [**啟用 SQL Server store 鏡像**] 核取方塊。
    
    如果您選擇啟用 [SQL Server store 鏡像]，請從清單**鏡像 SQL Server store**選取 store 和 instance。
    
    按一下 [新增] **** 定義新的 SQL Server 儲存區和選用執行個體。
    
- 如果您想要自動容錯移轉主要的 SQL Server store，請選取 [**使用 SQL Server 鏡像見證來啟用自動容錯移轉**] 核取方塊。
    
    如果您選擇啟用 [SQL Server store 鏡像見證] 來啟用自動容錯移轉，請從清單中選取 [store] 和 [instance]。
    
    按一下 [新增] **** 定義見證儲存區的新 SQL Server 儲存區和選用執行個體。
    
- 如果您想要啟用 SQL Server 災害復原，請選取 [**使用備份 SQL Server 存儲區來啟用災難**復原] 核取方塊。
    
    如果選擇啟用災害復原，請從 [備份 SQL Server 儲存區] **** 清單中選取儲存區和執行個體。
    
    按一下 [新增] **** 定義新的 SQL Server 儲存區和選用執行個體。
    
- 如果您想要針對備份 SQL Server 鏡像存放區啟用鏡像，請選取 [**啟用 SQL Server store 鏡像**] 核取方塊。
    
    如果您選擇啟用 [備份 SQL Server store 鏡像]，請從清單**備份 Sql server store mirror**選取 store 和 instance。
    
    按一下 [新增] **** 定義新的 SQL Server 儲存區和選用執行個體。
    
- 如果您想要自動容錯移轉備份 SQL Server 存放區，請選取 [**使用 SQL Server 鏡像見證來啟用自動容錯移轉**] 核取方塊。
    
    如果您選擇啟用 [SQL Server store 鏡像見證] 來啟用自動容錯移轉，請從清單中選取 [store] 和 [instance]。
    
    按一下 [新增] **** 定義見證儲存區的新 SQL Server 儲存區和選用執行個體。
    
- 如果您想啟用規範資料庫，請選取 [啟用規範]**** 核取方塊。
    
    如果選擇啟用規範，請從 [規範 SQL Server 儲存區] **** 清單中選取儲存區和執行個體。
    
    按一下 [新增] **** 定義新的 SQL Server 儲存區和選用執行個體。
    
- 如果您想要針對合規性 SQL Server store 啟用鏡像，請選取 [**啟用 SQL Server store 鏡像**] 核取方塊。
    
    如果您選擇啟用合規性 SQL Server store 鏡像，請從清單**相容性 Sql Server store mirror**選取 store 和 instance。
    
    按一下 [新增] **** 定義新的 SQL Server 儲存區和選用執行個體。
    
- 如果您想要自動容錯移轉 SQL Server store，請選取 [**使用 SQL Server 鏡像見證來啟用自動容錯移轉**] 核取方塊。
    
    如果您選擇啟用 [SQL Server store 鏡像見證] 來啟用自動容錯移轉，請從清單中選取 [store] 和 [instance]。
    
    按一下 [新增] **** 定義見證儲存區的新 SQL Server 儲存區和選用執行個體。
    
- 如果選擇啟用規範，請從 [備份規範 SQL Server 儲存區] **** 清單中選取儲存區和執行個體。
    
    按一下 [新增] **** 定義新的 SQL Server 儲存區和選用執行個體。
    
- 如果您想要針對合規性 SQL Server store 啟用鏡像，請選取 [**啟用 SQL Server store 鏡像**] 核取方塊。
    
    如果您選擇 [啟用合規性 SQL Server store 鏡像]，請從清單**備份相容性 Sql Server store mirror**中選取 store 和 instance。
    
    按一下 [新增] **** 定義新的 SQL Server 儲存區和選用執行個體。
    
- 如果您想要自動容錯移轉 [備份規範] SQL Server 存放區，請選取 [**使用 SQL Server 鏡像見證來啟用自動容錯移轉**] 核取方塊。
    
    如果您選擇啟用 [SQL Server store 鏡像見證] 來啟用自動容錯移轉，請從清單中選取 [store] 和 [instance]。
    
    按一下 [新增] **** 定義見證儲存區的新 SQL Server 儲存區和選用執行個體。
    
- 檔案**存放區**從清單中選取檔案存放位置，或按一下 [**新增**]，建立新的檔案存放區。
    
  **確定**：接受並認可對話方塊的變更。
  
  **取消**：捨棄變更，並關閉對話方塊。
  
  **說明**：顯示此說明畫面。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 2015 中規劃常設聊天室伺服器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[在商務用 Skype Server 2015 拓撲中新增持久聊天伺服器](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[設定常設聊天室伺服器的高可用性和災害復原](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
