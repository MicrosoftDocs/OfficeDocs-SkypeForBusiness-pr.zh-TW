---
title: 在商務用 Skype Server 2015 中設定 Persistent 聊天室的增益集
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 摘要：瞭解如何在商務用 Skype Server 2015 中設定 Persistent 聊天室伺服器聊天室的增益集。
ms.openlocfilehash: f6ff42e57f72a6fa875e8123af91caa7f4e3efc0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599978"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中設定 Persistent 聊天室的增益集
 
**摘要：** 瞭解如何在商務用 Skype Server 2015 中設定 Persistent 聊天室伺服器聊天室的增益集。
  
增益集是用來將 URLs 與聊天室產生關聯，以擴充會議室體驗。 這些 URLs 會出現在用戶端交談擴充窗格中。 一般增益集可能會包含指向 Silverlight 應用程式的 URL，該應用程式會在將股市代號傳送至聊天室時進行截獲，並在 [擴充性] 窗格中顯示 stock 記錄。 其他範例還包括在聊天室中嵌入 OneNote 2013 URL 做為增益集，以包含一些分享內容，例如「第一印象」或「本日熱門話題」。
  
 在使用者可以在用戶端中看到增益集之前，您必須將增益集新增至已註冊的增益集清單，而聊天室管理員或建立者必須與增益集產生關聯。
  
> [!NOTE]
> 持續聊天可在商務用 Skype Server 2015 中取得，但在商務用 Skype Server 2019 中已不再支援。 Teams 中提供相同的功能。 如需詳細資訊，請參閱[Microsoft Teams 升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續性聊天，您可以選擇將需要這項功能的使用者遷移至 Teams，或是繼續使用商務用 Skype Server 2015。 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>使用控制台設定聊天室的增益集

若要使用 [控制台] 設定聊天室的增益集，請執行下列動作：
  
1. 使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。
    
2. 從 [**開始**] 功能表中，選取 [商務用 Skype Server 控制台] 或開啟瀏覽器視窗，然後輸入管理 URL。
    
3. 在左導覽列中，按一下 [常設聊天室]，然後按一下 [增益集]。
    
    若為多個 Persistent Chat Server 集區部署，請從下拉式清單中選取適當的集區。
    
4. 在 **[增益集]** 頁面上，按一下 **[新增]**。
    
5. 在 [ **選取服務**] 中，選取對應至您需要建立增益集之 Persistent Chat Server 集區的服務。 增益集不得從一個集區移動到另一個集區，或是在不同集區之間共用。
    
6. 在 **[新增增益集]** 中，執行下列動作：
    
   - 在 **[名稱]** 中，指定新增益集的名稱。
    
   - 在 **[URL]** 中，指定要與增益集建立關聯的 URL。 URLs 會限制在 HTTP 和 HTTPs 通訊協定中。
    
7. 按一下 **[認可]**。
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>使用 Windows PowerShell 設定增益集

您可以使用下列 Windows PowerShell Cmdlet 來設定聊天室的增益集。 如需語法的詳細資訊（包括所有可用參數），請參閱[商務用 Skype Server 2015 管理命令](../management-shell.md)介面。
  

|**指令程式**|**描述**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |建立新的增益集  <br/> |
|Set-CsPersistentChatAddin  <br/> |設定現有增益集的設定  <br/> |
|Get-CsPersistentChatAddin  <br/> |取得增益集的相關資訊  <br/> |
|Remove-CsPersistentChatAddin  <br/> |移除增益集  <br/> |
   
### <a name="create-a-new-add-in"></a>建立新的增益集

您可以使用 **New-CsPersistentChatAddin** Cmdlet 來建立新的增益集。
  
例如，下列命令會使用集區 atl-cs-001.contoso.com 的 name ITPersistentChatAddin) 來建立新的增益集 (。 URL 參數和參數值會 http://atl-cs-001.contoso.com/itchat 指定增益集網頁的位置：
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>設定現有增益集的設定

您可以使用 **get-cspersistentchataddin** 指令程式，設定現有增益集的設定。 例如，下列命令會修改指派給持久聊天增益集 ITPersistentChatAddin 的 URL。 在此情況下，URL 會變更為 http://atl-cs-001.contoso.com/itchat2:
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>取得增益集的相關資訊

您可以使用 **Get-CsPersistentChatAddin** Cmdlet 取得增益集的相關資訊。 例如，下列命令會傳回設定供組織使用之所有 Persistent Chat 增益集的相關資訊：
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>移除增益集

您可以使用 **get-cspersistentchataddin** Cmdlet 來移除增益集。 例如，下列命令會移除集區 atl-cs-001.contoso.com 上所找到的 Persistent Chat 增益集 ITChatAddin：
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


