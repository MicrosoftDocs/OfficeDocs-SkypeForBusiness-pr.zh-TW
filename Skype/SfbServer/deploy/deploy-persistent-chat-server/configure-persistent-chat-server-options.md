---
title: 在商務用 Skype Server 2015 中設定 Persistent Chat Server 選項
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: 摘要：瞭解如何在商務用 Skype Server 2015 的全域、網站或集區層級設定 Persistent Chat Server 選項。
---

# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中設定 Persistent Chat Server 選項
 
**總結：** 瞭解如何在商務用 Skype Server 2015 的全域、網站或集區層級設定 Persistent Chat Server 選項。
  
您可以為持久聊天伺服器指定數個選項，這些選項可全域套用到網站中的所有集區或網站中的特定集區。 Persistent Chat server 選項包括下列各項： 
  
- 預設聊天記錄。 在第一次要求時可用於每個聊天室的聊天訊息數目。 全域預設值為30個聊天訊息。 
    
- 檔案大小上限。 可上傳或從聊天室中下載的檔案大小上限。 全域預設值為20MB。
    
- 參與者更新限制。 在特定聊天室中，Persistent 聊天會傳送名單更新的參與者人數上限。 全域預設值為75。
    
- 聊天室管理 URL。 自訂聊天室管理所用的 URL。 設定允許使用自訂聊天室管理解決方案。 
   
> [!NOTE] 
> 持續聊天可在商務用 Skype Server 2015 中取得，但在商務用 Skype Server 2019 中已不再支援。 Teams 中提供相同的功能。 如需詳細資訊，請參閱[Microsoft Teams 升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續性聊天，您可以選擇將需要這項功能的使用者遷移至 Teams，或是繼續使用商務用 Skype Server 2015。
 
## <a name="configure-persistent-chat-server-global-options"></a>設定 Persistent Chat Server 全域選項

若要設定 Persistent Chat Server 通用選項：
  
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
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a>設定特定 Persistent Chat Server 集區的選項

設定特定 Persistent Chat Server 集區的選項。
  
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
    

