---
title: 設定常設聊天室的增益集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 摘要：瞭解如何在商務用 Skype Server 2015 中設定持久聊天伺服器聊天室的增益集。
ms.openlocfilehash: c7243184f273704335dda3c8709de17e767f6b51
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992108"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>設定常設聊天室的增益集
 
**摘要：** 瞭解如何在商務用 Skype Server 2015 中設定持久聊天伺服器聊天室的增益集。
  
使用增益集，您可以將 Url 與聊天室產生關聯，以延長會議室體驗。 這些 Url 會出現在 [用戶端交談] 的 [擴充性] 窗格中。 典型的增益集可能會包含指向 Silverlight 應用程式的 URL，該應用程式會在將股市代號張貼到聊天室時截獲，並在 [擴充性] 窗格中顯示股票歷程記錄。 其他範例還包括在聊天室中嵌入 OneNote 2013 URL 做為增益集，以包含一些分享內容，例如「第一印象」或「本日熱門話題」。
  
 在使用者可以在用戶端中看到增益集之前，您必須先將增益集新增到已註冊的增益集清單中，而且聊天室管理員或建立者需要將會議室與增益集產生關聯。
  
> [!NOTE]
> 商務用 Skype Server 2015 提供持續聊天，但商務用 Skype Server 2019 已不再支援。 團隊中提供了相同的功能。 如需詳細資訊，請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。 如果您需要使用持續聊天，您可以選擇將需要此功能的使用者遷移至小組，或繼續使用商務用 Skype Server 2015。 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>使用 [控制台] 配置聊天室的增益集

若要使用 [控制] 面板來設定聊天室的增益集：
  
1. 使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。
    
2. 從 [**開始**] 功能表中，選取 [商務用 Skype 伺服器] 控制台或開啟瀏覽器視窗，然後輸入管理員 URL。
    
3. 在左導覽列中，按一下 [常設聊天室]****，然後按一下 [增益集]****。
    
    如果有多個持續聊天伺服器池部署，請從下拉式清單中選取適當的 [資源]。
    
4. 在 [增益集]**** 頁面上，按一下 [新增]****。
    
5. 在 [**選取服務**] 中，選取與您需要建立增益集的持續聊天伺服器池相對應的服務。 增益集不得從一個集區移動到另一個集區，或是在不同集區之間共用。
    
6. 在 [新增增益集]**** 中，執行下列動作：
    
   - 在 [名稱]**** 中，指定新增益集的名稱。
    
   - 在 [URL]**** 中，指定要與增益集建立關聯的 URL。 Url 僅限 HTTP 和 HTTPs 通訊協定。
    
7. 按一下 [認可]****。
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>使用 Windows PowerShell 來設定增益集

您可以使用下列 Windows PowerShell Cmdlet 來設定聊天室的增益集。 如需語法的詳細資料（包括所有可用的參數），請參閱[商務用 Skype Server 2015 管理命令](../management-shell.md)介面。
  

|**Cmdlet**|**描述**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |建立新的增益集  <br/> |
|Set-CsPersistentChatAddin  <br/> |設定現有增益集的設定  <br/> |
|CsPersistentChatAddin  <br/> |取得增益集的相關資訊  <br/> |
|移除-CsPersistentChatAddin  <br/> |移除增益集  <br/> |
   
### <a name="create-a-new-add-in"></a>建立新的增益集

您可以使用**新的 CsPersistentChatAddin** Cmdlet 來建立新的增益集。
  
例如，下列命令會為 pool atl-cs-001.contoso.com 建立新的增益集（名稱為 ITPersistentChatAddin）。 URL 參數和參數值http://atl-cs-001.contoso.com/itchat指定增益集網頁的位置：
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>設定現有增益集的設定

您可以使用**CsPersistentChatAddIn** Cmdlet 設定現有增益集的設定。 例如，下列命令會修改指派給持續聊天增益集 ITPersistentChatAddin 的 URL。 在這種情況下，URL 會變更為http://atl-cs-001.contoso.com/itchat2:
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>取得增益集的相關資訊

您可以使用**CsPersistentChatAddin** Cmdlet 來取得有關增益集的資訊。 例如，下列命令會傳回在組織中設定為使用的所有持久聊天增益集的相關資訊：
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>移除增益集

您可以使用**CsPersistentChatAddIn** Cmdlet 來移除增益集。 例如，下列命令會移除在 [池 atl-cs-001.contoso.com] 中找到的 [永久聊天] 增益集 ITChatAddin：
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


