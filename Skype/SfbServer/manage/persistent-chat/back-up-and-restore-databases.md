---
title: 備份和還原常設聊天室資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 摘要：瞭解如何在商務用 Skype Server 2015 中備份及還原持續聊天伺服器資料庫。
ms.openlocfilehash: a8c407c35b9d864889c26cbea7296dbed86516fa
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991968"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>備份和還原常設聊天室資料庫
 
**摘要：** 瞭解如何在商務用 Skype Server 2015 中備份及還原持續聊天伺服器資料庫。
  
持續聊天伺服器需要 SQL Server 資料庫軟體來儲存聊天室資料，例如記錄與內容、設定、使用者提供及其他相關中繼資料。 此外，如果您的組織有需要封存持久聊天活動的法規，且已啟用 [選用規範服務]，則 SQL Server 資料庫軟體是用來儲存合規性資料，包括聊天內容和事件，例如加入並離開會議室。 聊天室內容會儲存在持續聊天資料庫（mgc）。 合規性資料會儲存在規範資料庫（mgccomp）中。 這是應定期備份的業務關鍵型資料。 
  
> [!NOTE]
> 商務用 Skype Server 2015 提供持續聊天，但商務用 Skype Server 2019 已不再支援。 團隊中提供了相同的功能。 如需詳細資訊，請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天，您可以選擇將需要此功能的使用者遷移至小組，或繼續使用商務用 Skype Server 2015。 

## <a name="back-up-the-databases"></a>備份資料庫

備份持續聊天資料的方式有兩種。 
  
- SQL Server 備份
    
- **匯出 CsPersistentChatData** Cmdlet，可將永久性聊天資料匯出為檔案
    
使用 SQL Server 備份所建立的資料所需的磁碟空間可能會比**Export CsPersistentChatData** Cmdlet 所建立的20倍，但 SQL Server 備份可能是您熟悉的程式。
  
如果您想要使用 SQL Server 備份程式，請參閱 SQL 檔以取得詳細資訊。 
  
如果您想要使用**Export CsPersistentChatData** Cmdlet，您可以指定下列命令：
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

或
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

例如，下列命令會從位於伺服器 atl-sql-001.contoso.com 上的持久聊天資料庫匯出持續聊天資料;匯出的資料會儲存在 [檔案 C:\Logs\PersistentChatData.zip.] 中。 因為未指定 Level 參數，命令會完全匯出持續聊天資訊：
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>還原資料庫

您還原持久聊天資料的方式，取決於您用來備份它的方法。 如果您使用的是 SQL Server 備份程式，您必須使用 SQL Server restore 程式。 如果您使用**Export CsPersistentChatData** Cmdlet 來備份持續聊天資料，您必須使用**Import-CsPersistentChatData** Cmdlet 來還原資料：
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

或
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
