---
title: 常設聊天室類別主要頁面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatCategoryMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b71c6e6f-681c-4230-954d-3e95ab64ca00
description: 您可以使用 [常設聊天室] 頁面的 [類別] 區段來設定類別。 持續聊天室類別是組織聊天室的邏輯結構。 類別定義一組預設的存取控制清單 (ACL)，以控制可能建立或加入聊天室的使用者和使用者群組。 您可以使用類別，在不同的組織部門間強制執行道德管束。
ms.openlocfilehash: f080a71c7949d32fa3e72e902113be0d5dc88455
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193448"
---
# <a name="persistent-chat-category-main-page"></a>常設聊天室類別主要頁面
 
您可以使用 [常設聊天室]**** 頁面的 [類別]**** 區段來設定類別。 持續聊天室類別是組織聊天室的邏輯結構。 類別定義一組預設的存取控制清單 (ACL)，以控制可能建立或加入聊天室的使用者和使用者群組。 您可以使用類別，在不同的組織部門間強制執行道德管束。
  
聊天室類別可包含聊天室，但不可包含其他類別。 每個類別都說明其內容與中繼資料, 例如 [_名稱_] 和 [_描述_]。 此外, 該類別具有可設定以控制其所屬聊天室行為的屬性, 例如, 聊天室允許_邀請_或檔案上_傳_, 或包含_聊天記錄_。
  
若要建立新類別, 請參閱[在商務用 Skype server 2015 的 [永久聊天伺服器] 中管理類別](../../manage/persistent-chat/categories.md)。 如果您是永久性聊天管理員, 您可以使用 [控制台] 或 [Windows PowerShell Cmdlet] 來建立類別。
  
## <a name="tasks-that-you-can-perform"></a>您可以執行的工作

您可以在「類別」**** 頁面上執行下列工作：
  
- 建立或編輯新類別
    
- 將聊天室從某個類別移到另一個類別
    
- 刪除聊天室或類別
    
## <a name="to-configure-categories-for-persistent-chat-rooms"></a>設定持久聊天室的類別

1. 使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。
    
2. 從 [**開始**] 功能表中, 選取 [商務用 Skype 伺服器] 控制台或開啟瀏覽器視窗, 然後輸入管理員 URL。 .
    
3. 在左導覽列中，按一下 [常設聊天室]****，然後按一下 [類別]****。
    
    如果有多個持續聊天伺服器池部署, 請從下拉式清單中選取適當的 [資源]。
    
4. 在 [類別]**** 頁面上，按一下 [新增]**** 或 [編輯]****。
    
5. 在 [**選取服務**] 中, 選取與需要建立類別之持久聊天伺服器池相對應的服務。 此服務是永久聊天伺服器池, 持續聊天 (用戶端) 用來識別該類別屬於哪個池。 類別只能屬於一個持久聊天伺服器池, 而且不能移動到另一個, 或與另一個池共用。
    
6. 在 [新類別]**** 中，執行下列作業：
    
7. 在 [名稱]**** 中，指定新聊天室類別的名稱。
    
8. 在 [描述]**** 中，提供聊天室類別的詳細描述 (例如，Contoso 的聊天室類別)。
    
9. 如果要控制是否可以為屬於此類別的聊天室啟用邀請，請選取或清除 [啟用邀請]**** 核取方塊。 如果選取，此類別中的聊天室即可開啟或關閉邀請；如果清除，則不允許此類別中的聊天室有邀請。 如果會議室有邀請, 新成員新增至聊天室時, 他/她會在其持續聊天用戶端中收到新聊天室的通知。
    
10. 如果要控制屬於此類別的聊天室中的檔案上傳，請選取或清除 [啟用檔案上傳]**** 核取方塊。如果選取，此類別的聊天室就可以啟用或停用檔案上傳；如果清除，則不允許此類別的聊天室有檔案上傳。
    
11. 若要控制聊天記錄, 請選取或清除 [**啟用聊天記錄**] 核取方塊。 如果選取，聊天內容會持續存在；如果清除，聊天訊息就不會存在。 如果啟用規範，將會依規範儲存聊天內容，但是使用者無法存取較早的訊息。 此選項可用於為即時、不需要保留聊天記錄的會議室指派。
    
12. 在 [編輯類別]**** 中，執行下列作業：
    
    - 在 [**成員資格**] 的 [**允許的成員**] 區段中, 新增或移除使用者及其他 Active Directory 網域服務主體 (使用者、通訊群組、組織單位等), 這些都可以新增為聊天室的成員屬於類別。 類別所允許的主體可以搜尋該類別中的聊天室 (除非該聊天室為隱藏，則只有其成員可以在目錄中搜尋它)。
    
    - 在 [**成員資格**] 的 [**拒絕的成員**] 區段中, 新增或移除與從聊天室拒絕的成員相關聯的使用者及其他 Active Directory 主體。
    
    - 在 [**成員資格**] **** 的 [建立人] 區段中, 新增或移除與類別的建立者相關聯的使用者及其他 Active Directory 主體。 建立者是有權建立聊天室及指派聊天室管理員和成員的使用者。
    
13. 按一下 [認可]****。
    
## <a name="see-also"></a>另請參閱

如需持續聊天伺服器功能與功能的詳細資訊, 請參閱[在商務用 Skype server 2015 中規劃持續聊天伺服器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、[在商務用 skype server 2015 中部署持續聊天伺服器](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), 以及[管理持久聊天伺服器在商務用 Skype Server 2015 中](../../manage/persistent-chat/persistent-chat.md)。
  

