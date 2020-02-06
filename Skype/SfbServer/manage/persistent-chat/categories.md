---
title: 管理常設聊天室伺服器中的類別
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
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: 摘要：瞭解如何在商務用 Skype Server 2015 中管理持久聊天伺服器類別。
ms.openlocfilehash: 03e01e6221cdb32e4a2c77314e256a195b9ea4d3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817329"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>管理常設聊天室伺服器中的類別
 
**摘要：** 瞭解如何在商務用 Skype Server 2015 中管理持久聊天伺服器類別。
  
類別是組織聊天室的邏輯結構。 類別會定義一組預設的存取控制清單（Acl），以控制可建立或加入聊天室的使用者和使用者群組。 聊天室類別含有聊天室，但不包含其他類別。 每個類別分別說明其內容與中繼資料，例如Name與Description。 該類別具有可設定以控制其所屬聊天室行為的屬性。例如，聊天室是否允許邀請或檔案上傳，或包含聊天歷程記錄。 
  
使用正確的類別，就能更輕鬆地建立及管理聊天室。 就像是永久性聊天伺服器管理員，您可以為每個類別定義 AllowedMembers 和創意者，也可以定義預設聊天室設定和將套用到在類別中建立的所有聊天室的行為。 例如，如果您將類別的 AllowedMembers 設定為 contoso.com，您可以在 Contoso 中新增任何群組或使用者作為該類別中的聊天室。 如果您將類別中允許的成員設定為 [銷售]，則只有此通訊群組清單中的群組和使用者可以新增為該類別中的聊天聊天室成員。 [創意者] 屬性可讓您控制誰可以在該類別中建立聊天室。 在您建立聊天室之後，您可以將來自 AllowedMembers 群組的任何人指派為系統管理員，以便在會議室上進行持續的管理作業（例如，成員資格變更與核准）。
  
定義類別的 AllowedMembers 和創意者具有下列優點：
  
- 此類別中的所有聊天室都是由在類別層級設定的限制來系結。 您可以根據業務需求與存取原則，使用這個功能來隔離聊天室。
    
- [製作者清單] 中的使用者可以在該類別中建立新的聊天室。 如果您想要實現組織中受限制的人員可建立聊天室的系統，可以使用此控制項來符合該需求。 
    
使用者、組織單位（Ou），以及識別為類別創意者的使用者群組，都是唯一可在類別中建立聊天室的個人和群組。 建立類別之後，您可以從類別的 [AllowedMembers] 清單中選擇 [使用者]、[Ou] 和 [使用者群組] 做為聊天室管理員與管理並參與聊天室的成員。 
  
在您設定類別之前，請務必閱讀[商務用 Skype Server 2015 中的持續聊天類別、聊天室及使用者角色](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)。
  
您可以使用 [控制台] 或使用 Windows PowerShell Cmdlet 來設定及管理類別。

> [!NOTE]
> 商務用 Skype Server 2015 提供持續聊天，但商務用 Skype Server 2019 已不再支援。 團隊中提供了相同的功能。 如需詳細資訊，請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天，您可以選擇將需要此功能的使用者遷移至小組，或繼續使用商務用 Skype Server 2015。 
  
## <a name="configure-categories-by-using-the-control-panel"></a>使用 [控制台] 設定類別

1. 使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。
    
2. 從 [**開始**] 功能表中，選取 [商務用 Skype 伺服器] 控制台或開啟瀏覽器視窗，然後輸入管理員 URL。
    
3. 在左導覽列中，按一下 [常設聊天室]****，然後按一下 [類別]****。
    
    如果有多個持續聊天伺服器池部署，請從下拉式清單中選取適當的 [資源]。
    
4. 在 [類別]**** 頁面上，按一下 [新增]**** 或 [編輯]****。
    
5. 在 [**選取服務**] 中，選取與需要建立類別之持久聊天伺服器池相對應的服務。 服務是永久聊天伺服器池，持續聊天用戶端會用來識別該類別屬於哪個池。 類別只能屬於一個持續聊天伺服器池，而且不能移動到另一個池或與其他池共用。
    
6. 在 [新類別]**** 中，執行下列作業：
    
   - 在 [名稱]**** 中，指定新聊天室類別的名稱。
    
   - 在 [描述]**** 中，提供聊天室類別的詳細描述 (例如，Contoso 的聊天室類別)。
    
   - 如果要控制是否可以為屬於此類別的聊天室啟用邀請，請選取或清除 [啟用邀請]**** 核取方塊。 如果選取，此類別中的聊天室即可開啟或關閉邀請；如果清除，則不允許此類別中的聊天室有邀請。 如果會議室有邀請，新成員新增至聊天室時，他/她會在其持續聊天用戶端中收到新聊天室的通知。
    
   - 如果要控制屬於此類別的聊天室中的檔案上傳，請選取或清除 [啟用檔案上傳]**** 核取方塊。如果選取，此類別的聊天室就可以啟用或停用檔案上傳；如果清除，則不允許此類別的聊天室有檔案上傳。
    
   - 若要控制聊天記錄，請選取或清除 [**啟用聊天記錄**] 核取方塊。 如果選取，聊天內容會持續存在；如果清除，聊天訊息就不會存在。 如果啟用規範，將會依規範儲存聊天內容，但是使用者無法存取較早的訊息。 此選項可用於為即時、不需要保留聊天記錄的會議室指派。
    
7. 在 [編輯類別]**** 中，執行下列作業：
    
   - 在 [**成員資格**] 的 [**允許的成員**] 區段中，新增或移除使用者及其他 Active Directory 網域服務主體（使用者、通訊群組、組織單位等），允許將其新增為屬於該類別之聊天室的成員。 類別所允許的主體可以搜尋該類別中的聊天室 (除非該聊天室為隱藏，則只有其成員可以在目錄中搜尋它)。
    
   - 在 [**成員資格**] 的 [**拒絕的成員**] 區段中，新增或移除與從聊天室拒絕的成員相關聯的使用者及其他 Active Directory 主體。
    
   - 在 [**成員資格**] **** 的 [建立人] 區段中，新增或移除與類別的建立者相關聯的使用者及其他 Active Directory 主體。 建立者是有權建立聊天室及指派聊天室管理員和成員的使用者。
    
8. 按一下 [認可]****。
    
## <a name="configure-categories-by-using-windows-powershell"></a>使用 Windows PowerShell 來設定類別

您可以使用下列 Windows PowerShell Cmdlet 來設定類別：
  

|**Cmdlet**|**說明**|
|:-----|:-----|
|新-CsPersistentChatCategory  <br/> |建立新類別  <br/> |
|Set-CsPersistentChatCategory  <br/> |設定現有類別的設定  <br/> |
|CsPersistentChatCategory  <br/> |取得類別的相關資訊  <br/> |
|移除-CsPersistentChatCategory  <br/> |移除類別  <br/> |
   
您可以針對類別設定下列參數：
  
- EnableFileUpload. 允許檔案上傳到類別中的聊天室。
    
- EnableInvitations. 啟用類別的邀請。 [AllowedMembers] 清單中的使用者會在建立新的聊天室時，自動收到加入新聊天室的邀請。
    
- ChatHistory. 啟用或停用聊天記錄功能。
    
- 編寫. 指定允許在類別內建立聊天室的使用者。
    
- AllowedMembers. 指定允許存取類別中聊天室的使用者。
    
- DeniedMembers. 列出不允許存取該類別中聊天室的使用者。
    
如需有關 Cmdlet 語法（包括所有參數）的完整資訊，請參閱[商務用 Skype Server 2015 管理命令](../management-shell.md)介面。
  
### <a name="create-a-new-category"></a>建立新類別

您可以使用 CsPersistentChatCategory Cmdlet 來建立新**的**類別。 例如，下列命令會在 [pool atl-cs-001.contoso.com] 上建立名為 [支援人員] 的新類別。 在這個範例中，會啟用 [檔案上傳]：
  
```PowerShell
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>設定現有類別

您可以使用**CsPersistentCategory Cmdlet 設定**現有的類別。
  
例如，下列命令指定 user1 是 AllowedMember 及建立者，而是禁止使用程式對類別中的聊天室進行存取：
  
```PowerShell
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>取得類別的相關資訊

您可以使用**CsPersistentChatCategory** Cmdlet 來取得類別的相關資訊。 例如，下列命令會傳回組織中所有持續聊天類別的資訊：
  
```PowerShell
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>移除類別

您可以使用**CsPersistentChatCategory** Cmdlet 來移除類別。 在移除類別之前，您必須先刪除其底下的所有聊天室，或將聊天室移至新的類別。 例如，下列命令會移除 [atl-cs-001. com\helpdesk] 身分識別的類別：
  
```PowerShell
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
