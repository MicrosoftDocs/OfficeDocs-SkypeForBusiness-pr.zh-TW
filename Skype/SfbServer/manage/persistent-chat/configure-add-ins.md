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
description: '摘要: 瞭解如何在商務用 Skype Server 2015 中設定持久聊天伺服器聊天室的增益集。'
ms.openlocfilehash: 4614387149eb264d5c59ca7a0642408093312a18
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2019
ms.locfileid: "36193980"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="1d83f-103">設定常設聊天室的增益集</span><span class="sxs-lookup"><span data-stu-id="1d83f-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1d83f-104">**摘要:** 瞭解如何在商務用 Skype Server 2015 中設定持久聊天伺服器聊天室的增益集。</span><span class="sxs-lookup"><span data-stu-id="1d83f-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="1d83f-105">使用增益集, 您可以將 Url 與聊天室產生關聯, 以延長會議室體驗。</span><span class="sxs-lookup"><span data-stu-id="1d83f-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="1d83f-106">這些 Url 會出現在 [用戶端交談] 的 [擴充性] 窗格中。</span><span class="sxs-lookup"><span data-stu-id="1d83f-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="1d83f-107">典型的增益集可能會包含指向 Silverlight 應用程式的 URL, 該應用程式會在將股市代號張貼到聊天室時截獲, 並在 [擴充性] 窗格中顯示股票歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="1d83f-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="1d83f-108">其他範例還包括在聊天室中嵌入 OneNote 2013 URL 做為增益集，以包含一些分享內容，例如「第一印象」或「本日熱門話題」。</span><span class="sxs-lookup"><span data-stu-id="1d83f-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="1d83f-109">在使用者可以在用戶端中看到增益集之前, 您必須先將增益集新增到已註冊的增益集清單中, 而且聊天室管理員或建立者需要將會議室與增益集產生關聯。</span><span class="sxs-lookup"><span data-stu-id="1d83f-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1d83f-110">商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="1d83f-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="1d83f-111">團隊中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="1d83f-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="1d83f-112">如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="1d83f-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="1d83f-113">如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="1d83f-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="1d83f-114">使用 [控制台] 配置聊天室的增益集</span><span class="sxs-lookup"><span data-stu-id="1d83f-114">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="1d83f-115">若要使用 [控制] 面板來設定聊天室的增益集:</span><span class="sxs-lookup"><span data-stu-id="1d83f-115">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="1d83f-116">使用指派給 CsPersistentChatAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任一部電腦。</span><span class="sxs-lookup"><span data-stu-id="1d83f-116">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="1d83f-117">從 [**開始**] 功能表中, 選取 [商務用 Skype 伺服器] 控制台或開啟瀏覽器視窗, 然後輸入管理員 URL。</span><span class="sxs-lookup"><span data-stu-id="1d83f-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="1d83f-118">在左導覽列中，按一下 [常設聊天室]\*\*\*\*，然後按一下 [增益集]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1d83f-118">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="1d83f-119">如果有多個持續聊天伺服器池部署, 請從下拉式清單中選取適當的 [資源]。</span><span class="sxs-lookup"><span data-stu-id="1d83f-119">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="1d83f-120">在 [增益集]\*\*\*\* 頁面上，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1d83f-120">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="1d83f-121">在 [**選取服務**] 中, 選取與您需要建立增益集的持續聊天伺服器池相對應的服務。</span><span class="sxs-lookup"><span data-stu-id="1d83f-121">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="1d83f-122">增益集不得從一個集區移動到另一個集區，或是在不同集區之間共用。</span><span class="sxs-lookup"><span data-stu-id="1d83f-122">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="1d83f-123">在 [新增增益集]\*\*\*\* 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="1d83f-123">In **New Add-in**, do the following:</span></span>
    
   - <span data-ttu-id="1d83f-124">在 [名稱]\*\*\*\* 中，指定新增益集的名稱。</span><span class="sxs-lookup"><span data-stu-id="1d83f-124">In **Name**, specify a name for the new add-in.</span></span>
    
   - <span data-ttu-id="1d83f-125">在 [URL]\*\*\*\* 中，指定要與增益集建立關聯的 URL。</span><span class="sxs-lookup"><span data-stu-id="1d83f-125">In **URL**, specify the URL to be associated with the add-in.</span></span> <span data-ttu-id="1d83f-126">Url 僅限 HTTP 和 HTTPs 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="1d83f-126">URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="1d83f-127">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1d83f-127">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="1d83f-128">使用 Windows PowerShell 來設定增益集</span><span class="sxs-lookup"><span data-stu-id="1d83f-128">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="1d83f-129">您可以使用下列 Windows PowerShell Cmdlet 來設定聊天室的增益集。</span><span class="sxs-lookup"><span data-stu-id="1d83f-129">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets.</span></span> <span data-ttu-id="1d83f-130">如需語法的詳細資料 (包括所有可用的參數), 請參閱[商務用 Skype Server 2015 管理命令](../management-shell.md)介面。</span><span class="sxs-lookup"><span data-stu-id="1d83f-130">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="1d83f-131">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="1d83f-131">**Cmdlet**</span></span>|<span data-ttu-id="1d83f-132">**說明**</span><span class="sxs-lookup"><span data-stu-id="1d83f-132">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1d83f-133">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="1d83f-133">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="1d83f-134">建立新的增益集</span><span class="sxs-lookup"><span data-stu-id="1d83f-134">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="1d83f-135">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="1d83f-135">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="1d83f-136">設定現有增益集的設定</span><span class="sxs-lookup"><span data-stu-id="1d83f-136">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="1d83f-137">CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="1d83f-137">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="1d83f-138">取得增益集的相關資訊</span><span class="sxs-lookup"><span data-stu-id="1d83f-138">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="1d83f-139">移除-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="1d83f-139">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="1d83f-140">移除增益集</span><span class="sxs-lookup"><span data-stu-id="1d83f-140">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="1d83f-141">建立新的增益集</span><span class="sxs-lookup"><span data-stu-id="1d83f-141">Create a new add-in</span></span>

<span data-ttu-id="1d83f-142">您可以使用**新的 CsPersistentChatAddin** Cmdlet 來建立新的增益集。</span><span class="sxs-lookup"><span data-stu-id="1d83f-142">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="1d83f-143">例如, 下列命令會為 pool atl-cs-001.contoso.com 建立新的增益集 (名稱為 ITPersistentChatAddin)。</span><span class="sxs-lookup"><span data-stu-id="1d83f-143">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="1d83f-144">URL 參數和參數值http://atl-cs-001.contoso.com/itchat指定增益集網頁的位置:</span><span class="sxs-lookup"><span data-stu-id="1d83f-144">The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="1d83f-145">設定現有增益集的設定</span><span class="sxs-lookup"><span data-stu-id="1d83f-145">Configure settings for an existing add-in</span></span>

<span data-ttu-id="1d83f-146">您可以使用**CsPersistentChatAddIn** Cmdlet 設定現有增益集的設定。</span><span class="sxs-lookup"><span data-stu-id="1d83f-146">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="1d83f-147">例如, 下列命令會修改指派給持續聊天增益集 ITPersistentChatAddin 的 URL。</span><span class="sxs-lookup"><span data-stu-id="1d83f-147">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="1d83f-148">在這種情況下, URL 會變更為http://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="1d83f-148">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="1d83f-149">取得增益集的相關資訊</span><span class="sxs-lookup"><span data-stu-id="1d83f-149">Retrieve information about add-ins</span></span>

<span data-ttu-id="1d83f-150">您可以使用**CsPersistentChatAddin** Cmdlet 來取得有關增益集的資訊。</span><span class="sxs-lookup"><span data-stu-id="1d83f-150">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet.</span></span> <span data-ttu-id="1d83f-151">例如, 下列命令會傳回在組織中設定為使用的所有持久聊天增益集的相關資訊:</span><span class="sxs-lookup"><span data-stu-id="1d83f-151">For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="1d83f-152">移除增益集</span><span class="sxs-lookup"><span data-stu-id="1d83f-152">Remove an add-in</span></span>

<span data-ttu-id="1d83f-153">您可以使用**CsPersistentChatAddIn** Cmdlet 來移除增益集。</span><span class="sxs-lookup"><span data-stu-id="1d83f-153">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="1d83f-154">例如, 下列命令會移除在 [池 atl-cs-001.contoso.com] 中找到的 [永久聊天] 增益集 ITChatAddin:</span><span class="sxs-lookup"><span data-stu-id="1d83f-154">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


