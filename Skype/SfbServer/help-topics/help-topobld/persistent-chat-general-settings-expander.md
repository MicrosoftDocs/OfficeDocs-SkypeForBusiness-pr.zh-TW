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
- CSH
ms.custom:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 您可以透過設定或定義下列內容，來編輯 Persistent Chat Server 或 Persistent Chat Server 集區的一般設定：
ms.openlocfilehash: aae63b2d736f02b717b47aeff5fccb9b676daf99
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215994"
---
# <a name="persistent-chat-general-settings-expander"></a>常設聊天室一般設定展開工具
 
您可以透過設定或定義下列內容，來編輯 Persistent Chat Server 或 Persistent Chat Server 集區的 **一般** 設定：
  
 **一般**
  
- **FQDN**：編輯此設定以定義 Persistent chat Server 或 Persistent chat server 集區的完整功能變數名稱
    
- **常設聊天室集區的顯示名稱**：定義此設定可為伺服器或集區提供使用者易記及易於讀取的設定。 這項設定可讓您的使用者更輕鬆地依顯示名稱關聯指定的持續聊天伺服器或 Persistent Chat Server 集區，而不是更難於瞭解完整功能變數名稱。
    
- **常設聊天室連接埠**：指定用於常設聊天室的連接埠。
    
您可以透過設定或定義下列內容，來編輯 Persistent Chat Server 或 Persistent Chat Server 集區的 **關聯** 性設定：
  
 **協會**
  
- **Sql server 儲存區**：從清單中選取 SQL server 儲存區和選用的命名實例。
    
    按一下 [新增]**** 定義新的 SQL Server 儲存區和選用執行個體。
    
- 如果您想啟用主要 SQL Server 儲存區的鏡像，請選取 [ **啟用 SQL Server 儲存區鏡像** ] 核取方塊。
    
    如果您選擇啟用 SQL Server 儲存區鏡像，請從 [ **鏡像 SQL Server 儲存區**] 清單中選取儲存區和實例。
    
    按一下 [新增]**** 定義新的 SQL Server 儲存區和選用執行個體。
    
- 如果您想自動容錯移轉主要 SQL Server 儲存區，請選取 [ **使用 SQL Server 鏡像見證啟用自動容錯移轉** ] 核取方塊。
    
    如果您選擇啟用 SQL Server 儲存區鏡像見證以啟用自動容錯移轉，請從清單中選取儲存區和實例。
    
    按一下 [新增]**** 定義見證儲存區的新 SQL Server 儲存區和選用執行個體。
    
- 如果您想要啟用 SQL Server 嚴重損壞修復，請選取 [ **使用備份 SQL Server 儲存區來啟用** 嚴重損壞修復] 核取方塊。
    
    如果選擇啟用嚴重損壞修復，請從 [備份 SQL Server 儲存區]**** 清單中選取儲存區和執行個體。
    
    按一下 [新增]**** 定義新的 SQL Server 儲存區和選用執行個體。
    
- 如果您想啟用備份 SQL Server 鏡像儲存區的鏡像，請選取 [ **啟用 SQL Server 儲存區鏡像** ] 核取方塊。
    
    如果您選擇啟用備份 SQL Server 儲存區鏡像，請從 [ **備份 Sql server 儲存區鏡像**] 清單中選取儲存區和實例。
    
    按一下 [新增]**** 定義新的 SQL Server 儲存區和選用執行個體。
    
- 如果您想自動容錯移轉備份 SQL Server 儲存區，請選取 [ **使用 SQL Server 鏡像見證啟用自動容錯移轉** ] 核取方塊。
    
    如果您選擇啟用 SQL Server 儲存區鏡像見證以啟用自動容錯移轉，請從清單中選取儲存區和實例。
    
    按一下 [新增]**** 定義見證儲存區的新 SQL Server 儲存區和選用執行個體。
    
- 如果您想啟用規範資料庫，請選取 [啟用規範]**** 核取方塊。
    
    如果選擇啟用規範，請從 [規範 SQL Server 儲存區]**** 清單中選取儲存區和執行個體。
    
    按一下 [新增]**** 定義新的 SQL Server 儲存區和選用執行個體。
    
- 如果您想啟用規範 SQL Server 儲存區的鏡像，請選取 [ **啟用 SQL server 儲存區鏡像** ] 核取方塊。
    
    如果您選擇啟用規範 SQL Server 儲存區鏡像，請從 [ **規範 Sql server 儲存區鏡像**] 清單中選取儲存區和實例。
    
    按一下 [新增]**** 定義新的 SQL Server 儲存區和選用執行個體。
    
- 如果您想自動容錯移轉規範 SQL Server 儲存區，請選取 [ **使用 SQL Server 鏡像見證啟用自動容錯移轉** ] 核取方塊。
    
    如果您選擇啟用 SQL Server 儲存區鏡像見證以啟用自動容錯移轉，請從清單中選取儲存區和實例。
    
    按一下 [新增]**** 定義見證儲存區的新 SQL Server 儲存區和選用執行個體。
    
- 如果選擇啟用規範，請從 [備份規範 SQL Server 儲存區]**** 清單中選取儲存區和執行個體。
    
    按一下 [新增]**** 定義新的 SQL Server 儲存區和選用執行個體。
    
- 如果您想啟用規範 SQL Server 儲存區的鏡像，請選取 [ **啟用 SQL server 儲存區鏡像** ] 核取方塊。
    
    如果您選擇啟用規範 SQL Server 儲存區鏡像，請從 [ **備份規範 Sql server 儲存區鏡像**] 清單中選取儲存區和實例。
    
    按一下 [新增]**** 定義新的 SQL Server 儲存區和選用執行個體。
    
- 如果您想自動容錯移轉備份規範 SQL Server 儲存區，請選取 [ **使用 SQL Server 鏡像見證啟用自動容錯移轉** ] 核取方塊。
    
    如果您選擇啟用 SQL Server 儲存區鏡像見證以啟用自動容錯移轉，請從清單中選取儲存區和實例。
    
    按一下 [新增]**** 定義見證儲存區的新 SQL Server 儲存區和選用執行個體。
    
- **檔存放區** 從清單中選取檔案存放區位置，或按一下 [ **新增** ] 建立新的檔案存放區。
    
  **確定**：接受並認可對話方塊的變更。
  
  **取消**：捨棄變更，並關閉對話方塊。
  
  **說明**：顯示此說明畫面。
  
## <a name="see-also"></a>請參閱

[在商務用 Skype Server 2015 中規劃 Persistent Chat Server](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[將 Persistent Chat Server 新增至您的商務用 Skype Server 2015 拓撲](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[在商務用 Skype Server 2015 中設定 Persistent Chat Server 的高可用性和嚴重損壞修復](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
