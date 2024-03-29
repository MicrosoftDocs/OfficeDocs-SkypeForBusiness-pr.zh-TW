---
title: 備份及還原商務用 Skype Server 2015 中的持久聊天資料庫
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 摘要：瞭解如何在商務用 Skype Server 2015 中備份及還原 Persistent Chat Server 資料庫。
---

# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>備份及還原商務用 Skype Server 2015 中的持久聊天資料庫
 
**總結：** 瞭解如何在商務用 Skype Server 2015 中備份及還原 Persistent Chat Server 資料庫。
  
Persistent chat Server 需要 SQL Server 資料庫軟體才能儲存聊天室資料，例如歷史和內容、設定、使用者布建及其他相關的中繼資料。 此外，如果貴組織的法規要求封存持續聊天活動，且已啟用選用規範服務，SQL Server 資料庫軟體是用來儲存規範資料（包括聊天內容和事件，例如加入和離開聊天室）。 聊天室內容會儲存在 Persistent Chat database (mgc) 中。 規範資料儲存在規範資料庫中 (mgccomp) 。 這是應該定期備份的重要業務資料。 
  
> [!NOTE]
> 持續聊天可在商務用 Skype Server 2015 中取得，但在商務用 Skype Server 2019 中已不再支援。 Teams 中提供相同的功能。 如需詳細資訊，請參閱[Microsoft Teams 升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續性聊天，您可以選擇將需要這項功能的使用者遷移至 Teams，或是繼續使用商務用 Skype Server 2015。 

## <a name="back-up-the-databases"></a>備份資料庫

有兩種方式可以備份 Persistent 聊天資料。 
  
- SQL Server 備份
    
- **Export-CsPersistentChatData** Cmdlet，可將 Persistent 聊天資料匯出為檔案
    
使用 SQL Server 備份所建立的資料所需的磁碟空間（可能會比 **Export-CsPersistentChatData** 指令程式所建立的20倍多），但是 SQL Server 備份可能是您熟悉的程式。
  
如果您想要使用 SQL Server 備份程式，請參閱 SQL 檔，以取得詳細資訊。 
  
如果您想要使用 **Export-CsPersistentChatData** Cmdlet，您可以指定下列命令：
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

或
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

例如，下列命令會從位於伺服器 atl-sql-001.contoso.com 上的 Persistent Chat 資料庫匯出 Persistent Chat 資料;匯出的資料會儲存在 C:\Logs\PersistentChatData.zip 的檔案中。 因為未指定 Level 參數，所以命令會完整匯出 Persistent Chat 資訊：
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>還原資料庫

還原持久聊天資料的方式取決於您用來備份它的方法。 如果您使用 SQL Server 備份程式，則必須使用 SQL Server 還原程式。 如果您使用 **Export-CsPersistentChatData** Cmdlet 來備份 Persistent 聊天資料，則必須使用 **Import-CsPersistentChatData** Cmdlet 來還原資料：
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

或
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
