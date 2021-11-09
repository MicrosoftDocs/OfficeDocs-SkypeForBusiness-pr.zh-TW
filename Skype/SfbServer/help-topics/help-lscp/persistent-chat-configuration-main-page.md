---
title: 常設聊天室組態主要頁面
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatConfigMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 1e75d352-12cf-4548-9301-5d4c0e1c8f46
description: 您的持久聊天伺服器部署可以主控許多併發的持久聊天室。 聊天室可以在伺服器上組織成一組類別。 每個聊天室各屬於一個類別，並繼承該類別的某些設定。 這樣的組織會建立一個有用的結構，可用於根據其商業用途來識別交談，並促進委派管理功能和簡化管理。
ms.openlocfilehash: b0a193fd5b8c56e1f6833328b8670c482bd7a5e7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835521"
---
# <a name="persistent-chat-configuration-main-page"></a>常設聊天室組態主要頁面
 
您的持久聊天伺服器部署可以主控許多併發的持久聊天室。 聊天室可以在伺服器上組織成一組類別。 每個聊天室各屬於一個類別，並繼承該類別的某些設定。 這樣的組織會建立一個有用的結構，可用於根據其商業用途來識別交談，並促進委派管理功能和簡化管理。
  
> [!NOTE]
> 雖然聊天室的許多管理功能是可在使用者執行 Persistent Chat 的電腦上使用，但 **cspersistentchatadministrator** role 中的 Persistent chat Administrators () 必須使用控制台或管理命令介面 Cmdlet 來建立或管理類別。
  
Persistent Chat administrator 使用商務用 Skype Server 控制台或 Windows PowerShell Cmdlet 來建立及管理類別，以及為組織中的使用者設計聊天室的存取。
  
Persistent 聊天室管理員（能夠管理一或多個聊天室）可以使用用戶端啟動聊天室管理 Web 應用程式，以建立及管理會議室 (或客戶可以建立自訂的解決方案和工作流程以) 進行呼叫。 
  
聊天室管理員可以變更所有的聊天室內容，但不能變更聊天室的類別。不能限制聊天室管理員執行下列動作：
  
- 停用聊天室
    
- 變更聊天室名稱
    
- 變更聊天室說明
    
- 變更聊天室類型 (視聽形式或是一般形式)
    
- 變更聊天室的隱私權 (開放、關閉或秘密)
    
- 新增或移除成員
    
- 新增或移除聊天室管理員
    
- 新增或移除增益集
    
- 根據類別所允許的專案變更設定，例如邀請 () 
    
## <a name="tasks-that-you-can-perform"></a>您可以執行的工作

您可以在 [ **Persistent Chat Configuration** ] 頁面上執行下列工作：全域設定或針對特定集區設定持久聊天伺服器選項
  
## <a name="to-configure-persistent-chat-options-globally"></a>若要以全域方式設定持久聊天選項

1. 使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。
    
2. 從 [**開始**] 功能表中，選取 [商務用 Skype Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。
    
3. 在左導覽列中，按一下 [常設聊天室]，然後按一下 [常設聊天室組態]。
    
4. 在 [ **Persistent Chat Configuration** ] 頁面上，按一下 [ **新增]，** 然後按一下 [ **網站** 設定]。
    
    > [!IMPORTANT]
    > 如果您想要將設定套用至網站中部署的所有 Persistent Chat Server 集區，請選擇此選項。 若要將設定套用至特定的 Persistent Chat Server 集區，請按一下 [ **集** 區設定]。
  
5. 在 [ **選取網站**] 中，選取要為 Persistent Chat Server Site configuration 設定的網站。
    
6. 在 [新增常設聊天室組態] 中，執行下列動作：
    
   - 在 [名稱] 中，指定新組態設定的名稱。依預設，網站名稱已存在。
    
   - 在 [預設聊天記錄] 中，定義在第一次要求時，要為每個聊天室處理的聊天訊息數目。此數目預設為 30。這是全域預設值，系統管理員可針對每個類別停用聊天記錄。
    
     > [!IMPORTANT]
     > Persistent Chat Server 會在記憶體中快取這些郵件，因此如果您增加此數目，將會快取更多郵件。 您可以隨時利用搜尋來存取記錄內容。 預設數目只會決定最初連線至聊天室所看到的訊息數目上限。 
  
   - 在 [檔案大小上限 (KB)] 中，選取每個聊天記錄的檔案大小上限。此數目預設為 20 MB (20,000 KB)。這是可以上傳至系統中任何聊天室的檔案大小上限 (依其對應的 [類別] 設定來啟用檔案上傳)。
    
   - 在 [參與者更新限制]，選取參與者更新的限制。 Persistent Chat Server 會傳送名單資訊 (誰連接至聊天室) 給所有參與者，直到連線的使用者數量達到此數目為止。 此數目預設為 75。 此限制指出指定的會議室中的參與者數目上限，在這之後，Persistent Chat Server 會停止將名單更新傳送至會議室中的使用者。
    
   -  (選用。 ) 在 **聊天室管理 Url** 中，選取聊天室管理 url。 這是 web 型自訂聊天室管理的 URL。 如果您不需要自訂聊天室管理，且只要使用預設設定，請將此選項保留空白。 設定 URL 後，它會同時套用至內部及外部聊天室管理 URL。
    
     如果您想要自訂會議室建立體驗，並包含您的特定商務工作流程，您可以使用 Persistent Chat Server 軟體發展套件 (SDK) 建立自訂聊天室管理解決方案，將其主控于某處，然後將 URL 放在這裡。 此 URL 會下傳至用戶端，因此，當使用者嘗試檢視或建立聊天室時，就會將其導向至您的自訂聊天室管理解決方案。
    
7. 按一下 [認可]。
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>設定特定 Persistent Chat Server 集區的持續聊天選項

1. 使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。
    
2. 從 [**開始**] 功能表中，選取 [商務用 Skype Server 控制台]，或開啟瀏覽器視窗，然後輸入管理 URL。
    
3. 在左導覽列中，按一下 [常設聊天室]，然後按一下 [常設聊天室組態]。
    
4. 在「常設聊天室組態」頁面上，按一下 [新增]，然後按一下 [集區組態]。
    
5. 在 [ **選取服務**] 中，選取要設定之持久聊天伺服器集區相關聯的服務。
    
6. 在 [新增常設聊天室組態] 中，執行下列動作：
    
   - 在 [名稱] 中，指定新組態設定的名稱。依預設，網站集區名稱已存在。
    
   - 在 [預設聊天記錄] 中，定義在第一次要求時，要為每個聊天室處理的聊天訊息數目。此數目預設為 30。這是全域預設值，系統管理員可針對每個類別停用聊天記錄。
    
     > [!IMPORTANT]
     > Persistent Chat Server 會在記憶體中快取這些郵件，因此如果您增加此數目，將會快取更多郵件。 您可以隨時利用搜尋來存取記錄內容。 預設數目只會決定最初連線至聊天室所看到的訊息數目上限。 
  
   - 在 [檔案大小上限 (KB)] 中，選取每個聊天記錄的檔案大小上限。此數目預設為 20 MB (20,000 KB)。這是可以上傳至系統中任何聊天室的檔案大小上限 (依其對應的 [類別] 設定來啟用檔案上傳)。
    
   - 在 [參與者更新限制]，選取參與者更新的限制。 Persistent Chat Server 會傳送名單資訊 (誰連接至聊天室) 給所有參與者，直到連線的使用者數量達到此數目為止。 此數目預設為 75。 此限制指出指定的會議室中的參與者數目上限，在這之後，Persistent Chat Server 會停止將名單更新傳送至會議室中的使用者。
    
   - 在 [聊天室管理 URL] 中，選取聊天室管理 URL。 這是 Web 型聊天室管理部署的 URL。 如果您不需要自訂聊天室管理，且只要使用預設設定，請將此選項保留空白。
    
     如果您想要自訂會議室建立體驗，並包含您的特定商務工作流程，您可以使用 Persistent Chat Server 軟體發展套件 (SDK) 建立自訂聊天室管理解決方案，將其主控于某處，然後將 URL 放在這裡。 此 URL 會接著傳送至下游用戶端，因此，當使用者嘗試檢視/建立聊天室時，則會將使用者其導向至您的自訂聊天室管理解決方案。
    
7. 按一下 [認可]。
    
## <a name="see-also"></a>另請參閱

如需 Persistent chat server 功能及功能的詳細資訊，請參閱[在商務用 Skype Server 2015 中規劃 persistent chat server](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、[在商務用 Skype Server 2015 中部署 persistent chat](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)server，以及[在商務用 Skype Server 2015 中管理 persistent chat server](../../manage/persistent-chat/persistent-chat.md)。
  

