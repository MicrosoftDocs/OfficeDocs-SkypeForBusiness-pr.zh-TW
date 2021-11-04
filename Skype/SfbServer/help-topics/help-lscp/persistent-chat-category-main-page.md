---
title: 常設聊天室類別主頁面
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatCategoryMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: b71c6e6f-681c-4230-954d-3e95ab64ca00
description: 您可以使用 [Persistent Chat] 頁面的 [類別] 區段來設定類別。 Persistent 聊天室類別是用來組織聊天室的邏輯結構。 類別會定義一組預設的存取控制清單 (ACLs)，用於控制可建立或加入聊天室的使用者及使用者群組。 您可以利用類別在組織內不同的子部門之間強制執行道德管束。
ms.openlocfilehash: dd03180802cc8844f2b0a5d43c35f9d78a48bb32
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768951"
---
# <a name="persistent-chat-category-main-page"></a>常設聊天室類別主頁面
 
您可以使用 [ **Persistent Chat** ] 頁面的 [**類別**] 區段來設定類別。 Persistent 聊天室類別是用來組織聊天室的邏輯結構。 類別會定義一組預設的存取控制清單 (ACLs)，用於控制可建立或加入聊天室的使用者及使用者群組。 您可以利用類別在組織內不同的子部門之間強制執行道德管束。
  
聊天室類別可包含聊天室，但不可包含其他類別。 每個類別都會使用中繼資料來描述其內容，例如  _Name_ 及 _Description_。 此外，類別的屬性也可以設定，以控制屬於該類別之聊天室的行為，例如，聊天室允許  _邀請_ 或檔案上 _傳_，或包含  _聊天記錄_。
  
若要建立新的類別，請參閱[在2015商務用 Skype Server 中管理 Persistent Chat Server 中的類別](../../manage/persistent-chat/categories.md)。 如果您是 Persistent Chat Administrator，您可以使用 [控制台] 或 Windows PowerShell Cmdlet 來建立類別。
  
## <a name="tasks-that-you-can-perform"></a>您可以執行的工作

您可以在「類別」頁面上執行下列工作：
  
- 建立或編輯新類別
    
- 將聊天室從某個類別移到另一個類別
    
- 刪除聊天室或類別
    
## <a name="to-configure-categories-for-persistent-chat-rooms"></a>若要設定 Persistent 聊天室的類別

1. 使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。
    
2. 從 [**開始**] 功能表中，選取 [商務用 Skype Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。 .
    
3. 在左導覽列中，按一下 [常設聊天室]，然後按一下 [類別]。
    
    若為多個 Persistent Chat Server 集區部署，請從下拉式清單中選取適當的集區。
    
4. 在 **[類別]** 頁面上，按一下 **[新增]** 或 **[編輯]**。
    
5. 在 [ **選取服務**] 中，選取對應至需要建立類別之 Persistent Chat Server 集區的服務。 服務是 persistent chat Server 集區，Persistent Chat (用戶端) 使用它來識別類別所屬的集區。 類別只能隸屬于一部 Persistent Chat Server 集區，無法移至另一個集區，或與另一個集區共用。
    
6. 在 **[新類別]** 中，執行下列作業：
    
7. 在 **[名稱]** 中，指定新聊天室類別的名稱。
    
8. 在 **[描述]** 中，提供聊天室類別的詳細描述 (例如，Contoso 的聊天室類別)。
    
9. 如果要控制是否可以為屬於此類別的聊天室啟用邀請，請選取或清除 **[啟用邀請]** 核取方塊。 如果選取，此類別中的聊天室即可開啟或關閉邀請；如果清除，則不允許此類別中的聊天室有邀請。 如果會議室已開啟邀請，當新成員新增至聊天室時，他或她會在其 Persistent Chat 用戶端中取得新聊天室的通知。
    
10. 如果要控制屬於此類別的聊天室中的檔案上傳，請選取或清除 **[啟用檔案上傳]** 核取方塊。如果選取，此類別的聊天室就可以啟用或停用檔案上傳；如果清除，則不允許此類別的聊天室有檔案上傳。
    
11. 若要控制聊天記錄，請選取或清除 [ **啟用聊天記錄** ] 核取方塊。 如果選取，聊天內容會持續存在；如果清除，聊天訊息就不會存在。 如果啟用規範，將會依規範儲存聊天內容，但是使用者無法存取較早的訊息。 此選項可用於為不需要保留聊天記錄的即時、點對點共同作業的會議室所指派。
    
12. 在 **[編輯類別]** 中，執行下列作業：
    
    - 在 [ **成員資格**] 的 [ **允許的成員** ] 區段中，新增或移除使用者及其他 Active Directory 網域服務主體 (使用者、通訊群組、組織單位等) ，允許將其新增為屬於類別之聊天室的成員。 類別所允許的主體可以搜尋該類別中的聊天室 (除非該聊天室為隱藏，則只有其成員可以在目錄中搜尋它)。
    
    - 在 [ **成員資格**] 的 [ **拒絕的成員** ] 區段中，新增或移除與被聊天室拒絕的成員有關聯的使用者及其他 Active Directory 主體。
    
    - 在 [ **成員資格**] 的 [建立 **者** ] 區段中，新增或移除與類別建立者相關聯的使用者及其他 Active Directory 主體。 建立者是有權建立聊天室及指派聊天室管理員和成員的使用者。
    
13. 按一下 **[認可]**。
    
## <a name="see-also"></a>另請參閱

如需 Persistent chat server 功能及功能的詳細資訊，請參閱[在商務用 Skype Server 2015 中規劃 persistent chat server](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、[在商務用 Skype Server 2015 中部署 persistent chat](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)server，以及[在商務用 Skype Server 2015 中管理 persistent chat server](../../manage/persistent-chat/persistent-chat.md)。
  

