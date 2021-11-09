---
title: 在商務用 Skype Server 2015 中管理 Persistent Chat Server 中的類別
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: 摘要：瞭解如何在商務用 Skype Server 2015 中管理 Persistent Chat Server 類別。
ms.openlocfilehash: 86a90143bad43f4bb8a96434885eec741c01f4a4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853007"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中管理 Persistent Chat Server 中的類別
 
**摘要：** 瞭解如何在商務用 Skype Server 2015 中管理 Persistent Chat Server 類別。
  
類別是用來組織聊天室的邏輯結構。 類別會定義一組預設的存取控制清單 (ACLs) ，以控制可建立或加入聊天室的使用者和使用者群組。 聊天室類別包含聊天室，但不包含其他類別。 每個類別分別說明其內容與中繼資料，例如「名稱」與「描述」。 類別的屬性可以設定，以控制屬於該類別的聊天室行為。例如，聊天室是否允許邀請或檔案上傳，或包含聊天記錄。 
  
正確使用類別時，建立及管理聊天室的工作會更容易。 身為 Persistent Chat Server 系統管理員，您可以為每個類別定義 AllowedMembers 及建立者，也可以定義將套用到所有在類別中建立之聊天室的預設聊天室設定和行為。 例如，如果您將類別的 AllowedMembers 設定為 contoso.com，您可以將 Contoso 中的任何群組或使用者新增至該類別中的聊天室的成員。 如果您將類別上的允許成員設定為 Sales，則只有此通訊群組清單中的群組和使用者可以新增為該類別中聊天室的成員。 建立者屬性可讓您控制誰可以在該類別建立聊天室。 在建立聊天室之後，可以將 AllowedMembers 群組中的任何人指派為該會議室上的日常管理作業的管理員 (例如，成員資格變更和核准) 。
  
定義類別的 AllowedMembers 和建立者具有下列優點：
  
- 此類別中的所有聊天室都受限於在類別層級設定的限制。 您可以使用此功能，根據業務需求和存取原則隔離聊天室。
    
- 建立者清單中的使用者可以在該類別中建立新聊天室。 如果您想要執行的系統中，組織內的人員人數限制可以建立聊天室，此控制項可用於符合該需求。 
    
使用者、組織單位 (Ou) ，以及識別為類別建立者的使用者群組，都是唯一可以在類別中建立聊天室的個人和群組。 在建立類別之後，您可以從類別的 AllowedMembers 清單中選擇使用者、Ou 和使用者群組做為聊天室管理員和成員，以管理及參與會議室。 
  
在您設定類別之前，請務必閱讀[商務用 Skype Server 2015 中的持續聊天類別、聊天室和使用者角色](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)。
  
您可以使用 [控制台] 或使用 Windows PowerShell Cmdlet 來設定及管理類別。

> [!NOTE]
> 持續聊天可在商務用 Skype Server 2015 中取得，但在商務用 Skype Server 2019 中已不再支援。 Teams 中提供相同的功能。 如需詳細資訊，請參閱[Microsoft Teams 升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續性聊天，您可以選擇將需要這項功能的使用者遷移至 Teams，或是繼續使用商務用 Skype Server 2015。 
  
## <a name="configure-categories-by-using-the-control-panel"></a>使用控制台設定類別

1. 使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。
    
2. 從 [**開始**] 功能表中，選取 [商務用 Skype Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。
    
3. 在左導覽列中，按一下 [常設聊天室]，然後按一下 [類別]。
    
    若為多個 Persistent Chat Server 集區部署，請從下拉式清單中選取適當的集區。
    
4. 在 **[類別]** 頁面上，按一下 **[新增]** 或 **[編輯]**。
    
5. 在 [ **選取服務**] 中，選取對應至需要建立類別之 Persistent Chat Server 集區的服務。 服務是 persistent chat Server 集區，Persistent Chat 用戶端會使用它來識別類別所屬的集區。 類別只能隸屬于一個 Persistent Chat Server 集區，無法移至另一個集區或與其共用。
    
6. 在 **[新類別]** 中，執行下列作業：
    
   - 在 **[名稱]** 中，指定新聊天室類別的名稱。
    
   - 在 **[描述]** 中，提供聊天室類別的詳細描述 (例如，Contoso 的聊天室類別)。
    
   - 如果要控制是否可以為屬於此類別的聊天室啟用邀請，請選取或清除 **[啟用邀請]** 核取方塊。 如果選取，此類別中的聊天室即可開啟或關閉邀請；如果清除，則不允許此類別中的聊天室有邀請。 如果會議室已開啟邀請，當新成員新增至聊天室時，他或她會在其 Persistent Chat 用戶端中取得新聊天室的通知。
    
   - 如果要控制屬於此類別的聊天室中的檔案上傳，請選取或清除 **[啟用檔案上傳]** 核取方塊。如果選取，此類別的聊天室就可以啟用或停用檔案上傳；如果清除，則不允許此類別的聊天室有檔案上傳。
    
   - 若要控制聊天記錄，請選取或清除 [ **啟用聊天記錄** ] 核取方塊。 如果選取，聊天內容會持續存在；如果清除，聊天訊息就不會存在。 如果啟用規範，將會依規範儲存聊天內容，但是使用者無法存取較早的訊息。 此選項可用於為不需要保留聊天記錄的即時、點對點共同作業的會議室所指派。
    
7. 在 **[編輯類別]** 中，執行下列作業：
    
   - 在 [ **成員資格**] 的 [ **允許的成員** ] 區段中，新增或移除使用者及其他 Active Directory 網域服務主體 (使用者、通訊群組、組織單位等) ，允許將其新增為屬於類別之聊天室的成員。 類別所允許的主體可以搜尋該類別中的聊天室 (除非該聊天室為隱藏，則只有其成員可以在目錄中搜尋它)。
    
   - 在 [ **成員資格**] 的 [ **拒絕的成員** ] 區段中，新增或移除與被聊天室拒絕的成員有關聯的使用者及其他 Active Directory 主體。
    
   - 在 [ **成員資格**] 的 [建立 **者** ] 區段中，新增或移除與類別建立者相關聯的使用者及其他 Active Directory 主體。 建立者是有權建立聊天室及指派聊天室管理員和成員的使用者。
    
8. 按一下 **[認可]**。
    
## <a name="configure-categories-by-using-windows-powershell"></a>使用 Windows PowerShell 設定類別

您可以使用下列 Windows PowerShell Cmdlet 來設定類別：
  

|**指令程式**|**描述**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |建立新類別  <br/> |
|Set-CsPersistentChatCategory  <br/> |設定現有類別的設定  <br/> |
|Get-CsPersistentChatCategory  <br/> |檢索類別的相關資訊  <br/> |
|Remove-CsPersistentChatCategory  <br/> |移除類別  <br/> |
   
您可以為類別設定下列參數：
  
- EnableFileUpload. 允許檔上傳至類別中的聊天室。
    
- EnableInvitations. 啟用類別的邀請。 [AllowedMembers] 清單中的使用者會在建立新的聊天室時，自動接收加入新聊天室的邀請。
    
- ChatHistory. 啟用或停用聊天記錄功能。
    
- 創造者。 指定允許在類別中建立聊天室的使用者。
    
- AllowedMembers。 指定允許存取類別中聊天室的使用者。
    
- DeniedMembers。 列出不允許存取該類別中之聊天室的使用者。
    
如需 Cmdlet 語法（包括所有參數）的完整資訊，請參閱[商務用 Skype Server 2015 管理命令](../management-shell.md)介面。
  
### <a name="create-a-new-category"></a>建立新類別

您可以使用 **New-CsPersistentChatCategory** Cmdlet 來建立新的類別。 例如，下列命令會在集區 atl-cs-001.contoso.com 上建立名為 HelpDesk 的新類別。 在此範例中，會啟用檔案上傳：
  
```PowerShell
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>設定現有類別

您可以使用 **CsPersistentCategory** 指令程式來設定現有的類別。
  
例如，下列命令會指定 user1 是 AllowedMember 和建立者，而使用者2卻拒絕存取類別中的聊天室：
  
```PowerShell
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>取得類別的相關資訊

您可以使用 **Get-CsPersistentChatCategory** Cmdlet 取得類別的相關資訊。 例如，下列命令會傳回組織中所有 Persistent Chat 類別的資訊：
  
```PowerShell
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>移除類別

您可以使用 **CsPersistentChatCategory** Cmdlet 來移除類別。 移除類別之前，您必須先刪除其底下的所有聊天室，或將聊天室移至新的類別。 例如，下列命令會移除 Identity 為 "atl-ws-01-001 com\helpdesk" 的類別：
  
```PowerShell
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
