---
title: 在商務用 Skype Server 2015 中管理 Persistent chat Server 中的聊天室
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 摘要：瞭解如何在商務用 Skype Server 2015 中管理 Persistent chat Server 聊天室。
ms.openlocfilehash: 5eb69b3f852ce8e093947cdd04cc00b6bfdc19e3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746879"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中管理 Persistent chat Server 中的聊天室
 
**摘要：** 瞭解如何在商務用 Skype Server 2015 中管理 Persistent 聊天室伺服器聊天室。
  
正確使用類別時，建立及管理聊天室的工作會更容易。 類別定義誰可以建立或加入聊天室。 在您嘗試管理聊天室之前，請務必閱讀[商務用 Skype Server 2015 中的持續聊天類別、聊天室和使用者角色](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)，並在[商務用 Skype Server 2015 中管理 persistent chat Server](categories.md)中的類別。
  
> [!NOTE]
> 持續聊天可在商務用 Skype Server 2015 中取得，但在商務用 Skype Server 2019 中已不再支援。 Teams 中提供相同的功能。 如需詳細資訊，請參閱[Microsoft Teams 升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續性聊天，您可以選擇將需要這項功能的使用者遷移至 Teams，或是繼續使用商務用 Skype Server 2015。 

您可以使用 Windows PowerShell 命令列介面，或使用商務用 Skype 用戶端（如果您是聊天室的成員）來設定及管理聊天室。 本主題說明如何使用 Windows PowerShell 命令列介面來管理聊天室。 如果您想要使用商務用 Skype 用戶端來管理聊天室，請參閱 client help。 
  
聊天室可以是兩種類型之一： Normal 和視聽中心。 一般聊天室允許所有成員張貼和讀取郵件。 視聽中心是一種聊天室，只有簡報者可以張貼，但每個人都可以讀取。
  
神秘可以存取及管理聊天室取決於使用者角色，如下所示：
  
- 使用者必須是聊天室的成員，才能張貼和閱讀郵件。
    
- 可以將簡報者張貼至視聽中心聊天室。
    
- 管理員可以刪除舊版內容 (例如，在特定日期之前發佈的內容) 從任何聊天室，以防止資料庫變得太大。 管理員也可以移除或取代視為不適用於特定聊天室的郵件。
    
- 使用者（包括郵件作者）無法刪除任何聊天室中的內容。
    
- 聊天室管理員可對所有聊天室內容進行變更，包括停用會議室。 不過，管理員無法刪除聊天室，或變更聊天室的類別。 
    
- 只有管理員可以在建立聊天室之後刪除聊天室。
    
您可以使用下列 Windows PowerShell Cmdlet 來設定及管理聊天室：
  

|**指令程式**|**描述**|
|:-----|:-----|
|New-CsPersistentChatRoom  <br/> |建立新聊天室  <br/> |
|Set-CsPersistentChatRoom  <br/> |設定現有聊天室的設定;將使用者和使用者群組指派給會議室  <br/> |
|Get-CsPersistentChatRoom  <br/> |取得會議室的相關資訊  <br/> |
|Clear-CsPersistentChatRoom  <br/> |清除會議室或郵件  <br/> |
|Remove-CsPersistentChatRoom  <br/> |移除會議室  <br/> |
|Remove-CsPersistentChatMessage  <br/> |移除聊天室中的郵件  <br/> |
   
您可以使用 **New-CsPersistentChatRoom** Cmdlet 來建立聊天室和 **Set-CsPersistentChatRoom** Cmdlet，以設定現有聊天室，包括將使用者新增至聊天室。 您可以為聊天室設定下列參數：
  
- 禁用。 可讓您停用或啟用聊天室。 
    
- 邀請。 可讓您啟用或停用聊天室邀請，用來在使用者已新增為聊天室成員時通知使用者。 Inherit 中邀請函的預設設定，這會導致聊天室採用其所屬類別上設定的邀請設定。 在聊天室層級設定邀請設定為 false，可允許覆寫類別設定。 
    
- 隱私。 可讓您指定聊天室為開啟、關閉或機密。 任何人皆可搜尋並存取開啟的聊天室。 任何人皆可搜尋關閉的會議室，但只能透過成員存取。 只有會議室的成員可以搜尋並存取機密聊天室。 根據預設，每個新的會議室最初都會設定為 [已關閉]。
    
- 類型。 可讓您指定聊天室是否為一般聊天室，可接受任何成員張貼的郵件，或視聽中心聊天室，它只接受簡報者張貼的郵件。
    
- 外掛程式. 可讓您將先前設定的增益集與聊天室產生關聯，讓成員可以在參與時透過成員查看 URL 內容。
    
除了上述參數之外， **Set-CsPersistentChatRoom** Cmdlet 也可讓您將使用者指派至聊天室，如下所示：
  
- 成員 。 設定聊天室的成員資格。 您可以指定使用者的 SIP 位址，使用單一 Cmdlet 來新增或移除個別或多個成員。 若要允許大量新增使用者，也可以指定 Active Directory 組織單位或通訊群組。
    
- 經理。 可讓您將管理員指派給聊天室。 管理員有權定義聊天室的成員資格，以及其他設定。
    
- 主持人。 可讓您將簡報者指派至視聽中心聊天室。 
    
  如需語法（包括所有參數）的詳細資訊，請參閱[商務用 Skype Server 2015 管理命令](../management-shell.md)介面。
  
## <a name="create-a-new-room"></a>建立新聊天室

您可以使用 **New-CsPersistentChatRoom** Cmdlet 來建立新的聊天室。 例如，下列命令會在集區 atl-cs-001.contoso.com 上建立名為 ITChatRoom 的新聊天室。 在此範例中，聊天室會新增至 IT 類別：
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**附注：** 如果下列其中一個為 true，則不需要 PersistentChatPoolFqdn： 
  
- 只有一個持續性聊天伺服器集區。
    
- 您為類別提供集區 FQDN。
    
- 您提供集區 FQDN 以加入會議室。
    
## <a name="configure-an-existing-room"></a>設定現有聊天室

您可以使用 **Set-CsPersistentChatRoom** Cmdlet 來設定現有的聊天室。 例如，下列命令會將 user1 當做成員和簡報者，及使用者2指派為 testCat 視聽中心聊天室的管理員：
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 下一個範例會將 active Directory 中的 NorthAmericaUsers OU 中的所有使用者新增至 NorthAmerica 聊天室：
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

下一個範例會將財務通訊群組中的所有成員新增至相同的聊天室：
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a>停用或啟用聊天室

如果已不再相關的持久聊天室主題，您可以停用聊天室，讓使用者無法使用它。 停用聊天室時，所有成員都會立即中斷與聊天室的連線。 停用聊天室之後，使用者就無法在聊天室搜尋中重新加入或尋找。
  
如果聊天室的記錄依然存在，則會在停用聊天室時保留內容。 不過，在聊天室保持停用狀態時，搜尋中不會顯示該內容。 如果您稍後啟用聊天室，使用者可以搜尋停用聊天室之前所張貼的郵件。 如需設定聊天室記錄的詳細資訊，請參閱[在商務用 Skype Server 2015 中的 Persistent chat Server 中管理類別](categories.md)。 
  
停用聊天室時，其中的成員資格清單與其他設定仍會保留。 您可以以系統管理員身分啟用已停用的會議室，而且不需要手動重新建立設定。
  
您可以使用 **Set-CsPersistentChatRoom** Cmdlet 來停用聊天室，並將 Disabled 參數設定為 True：
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

若要啟用聊天室，請將 Disabled 參數設定為 False：
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a>取得會議室的相關資訊

若要取得設定供組織使用之聊天室的相關資訊，您可以使用 **Get-CsPersistentChatRoom** Cmdlet。
  
下列命令會傳回設定供組織使用之所有聊天室的相關資訊：
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a>移除聊天室中的所有內容

您可以使用 **Clear-CsPersistentChatRoom** Cmdlet 來移除聊天室中的內容。 例如，下列命令會從2015年3月1日或之前的會議室中移除所有來自 Persistent 聊天室 ITChatRoom 的內容：
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a>移除聊天室中的郵件

您可以使用 **test-cspersistentchatmessage** 指令程式，在 Persistent Chat 資料庫中移除一或多封郵件，並選擇性地將郵件取代為預設郵件或使用系統管理員所提供的郵件。 例如，下列命令會從使用者 kenmyer@contoso.com 張貼的 ITChatRoom 聊天室中移除所有郵件：
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

下一個範例會取代所有已移除的郵件，請注意，該郵件已不再可用：
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a>移除會議室

您可以使用 **Remove-CsPersistentChatRoom** Cmdlet 來移除聊天室。
  
例如，下列命令會移除聊天室 RedmondChatRoom：
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a>將會議室從一個類別移到另一個類別

如果聊天室管理員在其他類別中有建立 **者** 許可權，則可以將會議室從某個類別移到另一個類別。 未刪除或重新建立聊天室。 這是與資料庫的關聯出現變更。
  
變更聊天室類別時，應很少和小心。 類別會決定允許的聊天室成員資格，因此，將聊天室移到另一個類別時，將清除新類別不再支援的所有系統存取控制清單 (SACL)。 例如，如果使用者是會議室的成員，而且不再是新類別中的允許成員，則會修改該會議室成員資格，並且會從聊天室中移除該使用者。
  

