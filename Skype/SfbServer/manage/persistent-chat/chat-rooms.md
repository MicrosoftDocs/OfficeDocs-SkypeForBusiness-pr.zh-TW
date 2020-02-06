---
title: 管理常設聊天室伺服器中的聊天室
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 摘要：瞭解如何在商務用 Skype Server 2015 中管理持久聊天伺服器聊天室。
ms.openlocfilehash: b19b230aa4b83e9bd1b84b6be50a27cf665de788
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817279"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>管理常設聊天室伺服器中的聊天室
 
**摘要：** 瞭解如何在商務用 Skype Server 2015 中管理持續聊天伺服器聊天室。
  
使用正確的類別，就能更輕鬆地建立及管理聊天室。 類別定義誰可以建立或加入聊天室。 在您嘗試管理聊天室之前，請務必閱讀[商務用 Skype server 2015 中的持續聊天類別、聊天室，以及使用者角色](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)，並在[商務用 skype Server 2015 中管理永久性聊天伺服器的類別](categories.md)。
  
> [!NOTE]
> 商務用 Skype Server 2015 提供持續聊天，但商務用 Skype Server 2019 已不再支援。 團隊中提供了相同的功能。 如需詳細資訊，請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天，您可以選擇將需要此功能的使用者遷移至小組，或繼續使用商務用 Skype Server 2015。 

您可以使用 Windows PowerShell 命令列介面來設定及管理聊天室，或使用商務用 Skype 用戶端（如果您是聊天室的成員）來進行設定和管理聊天室。 本主題說明如何使用 Windows PowerShell 命令列介面管理聊天室。 如果您想要使用商務用 Skype 用戶端管理聊天室，請參閱用戶端說明。 
  
聊天室可以是兩種類型的其中一種： [標準] 和 [Auditorium]。 標準聊天室可讓所有成員張貼及讀取訊息。 Auditorium 是一種在其中只有簡報者可以張貼的聊天室，但所有人都可以閱讀。
  
誰可以存取及管理聊天室，取決於使用者角色，如下所示：
  
- 使用者必須是聊天室的成員，才能張貼及閱讀郵件。
    
- 您可以將簡報者張貼到 Auditorium 會議室。
    
- 系統管理員可以從任何聊天室刪除較舊的內容（例如，在特定日期之前發佈的內容），讓資料庫不會變得太大。 系統管理員也可以移除或取代被視為不適用於特定聊天室的郵件。
    
- 使用者（包括郵件作者）無法刪除任何聊天室中的內容。
    
- 聊天室管理員可以對所有聊天室屬性進行變更，包括停用會議室。 不過，經理不能刪除聊天室，或變更聊天室的類別。 
    
- 只有系統管理員才能在已建立聊天室後刪除聊天室。
    
您可以使用下列 Windows PowerShell Cmdlet 來設定和管理聊天室：
  

|**Cmdlet**|**說明**|
|:-----|:-----|
|新-CsPersistentChatRoom  <br/> |建立新聊天室  <br/> |
|Set-CsPersistentChatRoom  <br/> |設定現有聊天室的設定;將使用者和使用者群組指派給聊天室  <br/> |
|CsPersistentChatRoom  <br/> |取得會議室的相關資訊  <br/> |
|Clear-CsPersistentChatRoom  <br/> |從聊天室中清除聊天室或訊息  <br/> |
|移除-CsPersistentChatRoom  <br/> |移除會議室  <br/> |
|移除-CsPersistentChatMessage  <br/> |移除聊天室中的郵件  <br/> |
   
您可以使用**CsPersistentChatRoom** Cmdlet 來建立聊天室和 CsPersistentChatRoom Cmdlet 來**設定**現有聊天室，包括新增使用者至聊天室。 您可以針對聊天室設定下列參數：
  
- 禁止. 可讓您停用或啟用聊天室。 
    
- 邀請. 可讓您啟用或停用聊天室邀請函，當使用者已新增為聊天室成員時，就會通知使用者。 [繼承] 中邀請函的預設設定，這會造成聊天室採用其所屬類別上設定的邀請設定。 將 [邀請] 設定設定為 [聊天室] 層級的 false，即可覆蓋類別設定。 
    
- 考慮. 可讓您指定聊天室是開啟、關閉或秘密。 任何人都可以搜尋並存取 [開啟聊天室]。 任何人都可以搜尋關閉的聊天室，但只能透過成員存取。 密碼室只能透過聊天室的成員進行搜尋和存取。 根據預設，每個新的聊天室最初都設定為 [關閉]。
    
- 輸入. 可讓您指定聊天室是標準室，也就是接受任何成員張貼的訊息，或是 Auditorium 聊天室，只接受簡報者張貼的訊息。
    
- 增益集. 可讓您將先前設定的增益集與聊天室建立關聯，這可讓成員在參與時查看 URL 內容。
    
除了上述參數之外， **CsPersistentChatRoom** Cmdlet 還可讓您將使用者指派給聊天室，如下所示：
  
- 會員. 配置聊天室的成員資格。 您可以透過指定使用者的 SIP 位址，使用單一 Cmdlet 來新增或移除個別或多個成員。 若要允許大量新增使用者，也可以指定 Active Directory 組織單位或通訊群組。
    
- 主管. 可讓您將主管指派給聊天室。 管理員有權定義聊天室的成員資格，以及其他設定。
    
- 演示. 可讓您將簡報者指派給 Auditorium 聊天室。 
    
  如需語法的詳細資料（包括所有參數），請參閱[商務用 Skype Server 2015 管理命令](../management-shell.md)介面。
  
## <a name="create-a-new-room"></a>建立新聊天室

您可以使用**新的 CsPersistentChatRoom** Cmdlet 來建立新的聊天室。 例如，下列命令會在 [pool atl-cs-001.contoso.com] 上建立一個名為 ITChatRoom 的新聊天室。 在這個範例中，聊天室會新增至 [IT] 類別：
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**注意：** 如果下列其中一項為 true，則不需要 PersistentChatPoolFqdn： 
  
- 只有一個持續聊天伺服器池。
    
- 您可以將池 FQDN 提供給類別。
    
- 您提供一個 [池 FQDN] 來新增聊天室。
    
## <a name="configure-an-existing-room"></a>設定現有的聊天室

您可以使用**CsPersistentChatRoom Cmdlet 設定**現有的聊天室。 例如，下列命令會將 user1 做為成員和簡報者，以及 testCat Auditorium 聊天室的管理員。
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 下一個範例會將 active Directory 中的 NorthAmericaUsers OU 中的所有使用者新增至 [北美] 聊天室：
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

下一個範例會將財務通訊群組中的所有成員新增至相同的聊天室：
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a>停用或啟用聊天室

如果永久聊天室的主題已不再相關，您可以停用聊天室，讓使用者無法使用該聊天室。 停用聊天室時，所有成員都會立即中斷與聊天室的連線。 停用聊天室之後，使用者就無法在聊天室搜尋中重新加入或尋找。
  
如果聊天室的記錄繼續存在，則在停用聊天室時，內容會保留下來。 不過，在聊天室保持在停用狀態時，搜尋中不會顯示該內容。 如果您稍後啟用聊天室，使用者就可以搜尋在停用聊天室之前所張貼的訊息。 如需有關設定聊天室歷程記錄的詳細資訊，請參閱[在商務用 Skype server 2015 的永久聊天伺服器中管理類別](categories.md)。 
  
如果聊天室停用，則會保留其成員資格清單及其他設定。 以管理員身分，您可以啟用已停用的聊天室，而且不需要手動重新建立設定。
  
您可以使用**CsPersistentChatRoom** Cmdlet 來停用聊天室，並將 Disabled 參數設定為 True：
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

若要啟用聊天室，請將 Disabled 參數設定為 False：
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a>取得會議室的相關資訊

若要取得針對貴組織中設定使用的聊天室相關資訊，您可以使用**CsPersistentChatRoom** Cmdlet。
  
下列命令會傳回在組織中設定為使用的所有聊天室的相關資訊：
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a>移除聊天室中的所有內容

您可以使用**Clear CsPersistentChatRoom** Cmdlet 來移除聊天室的內容。 例如，下列命令會移除已在2015年3月1日之前或之前新增到聊天室中的持續聊天室 ITChatRoom 中的所有內容：
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a>移除聊天室中的郵件

您可以在永久聊天資料庫中移除一或多封郵件，並選擇性地使用**CsPersistentChatMessage** Cmdlet，以預設訊息或由系統管理員提供的訊息取代郵件。 例如，下列命令會移除使用者 kenmyer@contoso.com 張貼的 ITChatRoom 聊天室中的所有郵件：
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

下一個範例會將所有已移除的郵件取代為不能再使用的筆記：
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a>移除會議室

您可以使用**CsPersistentChatRoom** Cmdlet 來移除聊天室。
  
例如，下列命令會移除聊天室 RedmondChatRoom：
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a>將會議室從一個類別移到另一個類別

如果聊天室管理員有其他類別的建立**者**許可權，他/她可以將會議室從一個類別移到另一個類別。 不會刪除並重新建立聊天室。 變更是資料庫中的關聯。
  
變更聊天室類別應該很少進行，且需要小心。 類別會決定聊天室的允許成員資格，因此當聊天室移至另一個類別時，新類別不再支援的所有系統存取控制清單（Sacl）都將清除。 例如，如果使用者是聊天室的成員，而且已不再是新類別中的允許成員，就會修改聊天室成員資格，並將該使用者從聊天室中移除。
  

