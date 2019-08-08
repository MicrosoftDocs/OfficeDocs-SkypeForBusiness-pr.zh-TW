---
title: 使用商務用 Skype 2015 設定用戶端體驗
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: '摘要: 請閱讀本主題, 以瞭解如何設定商務用 Skype 使用者的用戶端體驗。'
ms.openlocfilehash: ea1d38693291ebfa7d7cc4f8893b0aa6ec1c0d83
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234450"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a><span data-ttu-id="aec12-103">使用商務用 Skype 2015 設定用戶端體驗</span><span class="sxs-lookup"><span data-stu-id="aec12-103">Configure the client experience with Skype for Business 2015</span></span>
 
<span data-ttu-id="aec12-104">**摘要:** 若要瞭解如何設定商務用 Skype 2015 使用者的用戶端體驗, 請閱讀本主題。</span><span class="sxs-lookup"><span data-stu-id="aec12-104">**Summary:** Read this topic to learn how to configure the client experience for Skype for Business 2015 users.</span></span>
  
<span data-ttu-id="aec12-105">商務用 skype 2015 提供以 Skype 消費者產品體驗為基礎的新使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="aec12-105">Skype for Business 2015 provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="aec12-106">除了 Lync 的所有功能之外, 商務用 Skype 也會以簡化的控制項和熟悉的圖示來提供新功能。</span><span class="sxs-lookup"><span data-stu-id="aec12-106">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="aec12-107">如需新用戶端體驗的詳細資訊, 請參閱[探索商務用 Skype](https://go.microsoft.com/fwlink/?LinkId=529022)。</span><span class="sxs-lookup"><span data-stu-id="aec12-107">For detailed information about the new client experience, see [Explore Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).</span></span>
  
<span data-ttu-id="aec12-108">商務用 skype 伺服器支援新的商務用 Skype 用戶端體驗, 以及 Lync 用戶端體驗。</span><span class="sxs-lookup"><span data-stu-id="aec12-108">Skype for Business Server supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="aec12-109">作為系統管理員, 您可以為使用者選擇首選的用戶端體驗。</span><span class="sxs-lookup"><span data-stu-id="aec12-109">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="aec12-110">例如, 您可能會想要部署 Lync 用戶端體驗, 直到貴組織中的使用者在新的商務用 Skype 體驗中受到全面訓練為止。</span><span class="sxs-lookup"><span data-stu-id="aec12-110">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="aec12-111">或者, 如果您尚未將所有使用者升級到商務用 Skype Server, 您可能會希望所有使用者都能使用相同的用戶端體驗, 直到全部都升級到新的伺服器為止。</span><span class="sxs-lookup"><span data-stu-id="aec12-111">Or, if you have not yet upgraded all users to Skype for Business Server, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="aec12-112">如果貴組織已部署商務用 Skype Server 和 Lync Server, 則預設的用戶端體驗會依伺服器版本和 UI 設定而有所不同。</span><span class="sxs-lookup"><span data-stu-id="aec12-112">If your organization has both Skype for Business Server and Lync Server deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="aec12-113">當使用者第一次啟動商務用 Skype 時, 他們將永遠會看到商務用 Skype 使用者介面, 即使您已選取 Lync 用戶端體驗也一樣。</span><span class="sxs-lookup"><span data-stu-id="aec12-113">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience.</span></span> <span data-ttu-id="aec12-114">幾分鐘之後, 系統會要求使用者切換到 Lync 模式。</span><span class="sxs-lookup"><span data-stu-id="aec12-114">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="aec12-115">如需詳細資訊, 請參閱本主題稍後的**第一次啟動用戶端行為**。</span><span class="sxs-lookup"><span data-stu-id="aec12-115">For more information, see **First launch client behavior** later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aec12-116">Lync 2013 用戶端體驗不是商務用 Skype 2016 用戶端版本或更新版本的選項。</span><span class="sxs-lookup"><span data-stu-id="aec12-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions or later.</span></span> <span data-ttu-id="aec12-117">在您嘗試將用戶端環境設定為使用 Lync 2013 用戶端之前, 請先檢查用戶端版本, 以確保它不是以數位16開頭;例如: x.x.x。</span><span class="sxs-lookup"><span data-stu-id="aec12-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="configure-the-client-experience"></a><span data-ttu-id="aec12-118">設定用戶端體驗</span><span class="sxs-lookup"><span data-stu-id="aec12-118">Configure the client experience</span></span>

<span data-ttu-id="aec12-119">您可以透過使用**CSClientPolicy** Cmdlet 與 EnableSkypeUI 參數, 來指定貴組織中的使用者所能看到的用戶端體驗:</span><span class="sxs-lookup"><span data-stu-id="aec12-119">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter:</span></span>
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

<span data-ttu-id="aec12-120">其中 XdsIdentity 指的是全域原則或命名網站原則。</span><span class="sxs-lookup"><span data-stu-id="aec12-120">where XdsIdentity refers to the Global policy or a named site policy.</span></span>
  
<span data-ttu-id="aec12-121">下列命令會針對貴組織中受全域原則影響的所有使用者, 選取商務用 Skype 用戶端體驗 (請記住, 網站或使用者專用原則會覆寫全域原則):</span><span class="sxs-lookup"><span data-stu-id="aec12-121">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span> 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

<span data-ttu-id="aec12-122">[下一步] 命令會針對貴組織中的所有使用者選取由全域原則影響的 Lync 用戶端體驗:</span><span class="sxs-lookup"><span data-stu-id="aec12-122">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

<span data-ttu-id="aec12-123">[下一步] 命令會針對雷德蒙網站中的所有使用者選取商務用 Skype 用戶端體驗:</span><span class="sxs-lookup"><span data-stu-id="aec12-123">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

<span data-ttu-id="aec12-124">如果您想要針對貴組織內的特定使用者設定用戶端體驗, 您可以使用 CsClientPolicy Cmdlet 建立新**的**使用者策略, 然後使用**授與 CsClientPolicy**將原則指派給特定使用者。Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="aec12-124">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>
  
<span data-ttu-id="aec12-125">例如, 下列命令會建立新的用戶端原則 SalesClientUI, 以選取商務用 Skype 用戶端體驗:</span><span class="sxs-lookup"><span data-stu-id="aec12-125">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

<span data-ttu-id="aec12-126">下一個命令會將原則 (SalesClientUI) 指派給銷售部門的所有成員:</span><span class="sxs-lookup"><span data-stu-id="aec12-126">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="aec12-127">第一次啟動用戶端行為</span><span class="sxs-lookup"><span data-stu-id="aec12-127">First launch client behaviors</span></span>

<span data-ttu-id="aec12-128">根據預設, 當使用者第一次啟動商務用 Skype 2015 時, 他們將永遠會看到商務用 Skype 的使用者介面, 即使您已選取 Lync 用戶端體驗, 只要將 EnableSkypeUI 參數的值設定為 $False (如下所述)。先前.</span><span class="sxs-lookup"><span data-stu-id="aec12-128">By default, when users launch Skype for Business 2015 for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="aec12-129">幾分鐘之後, 系統會要求使用者切換到 Lync 模式。</span><span class="sxs-lookup"><span data-stu-id="aec12-129">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="aec12-130">如果您想要在使用者第一次啟動商務用 Skype 用戶端時顯示 Lync 使用者介面, 請在用戶端第一次更新之後, 按照下列步驟進行:</span><span class="sxs-lookup"><span data-stu-id="aec12-130">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="aec12-131">確認您使用的原則`EnableSkypeUI`中的值設定為 $False, 如先前所述。</span><span class="sxs-lookup"><span data-stu-id="aec12-131">Confirm that the value of  `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>
    
2. <span data-ttu-id="aec12-132">更新使用者電腦上的系統登錄。</span><span class="sxs-lookup"><span data-stu-id="aec12-132">Update the system registry on the user's computer.</span></span> <span data-ttu-id="aec12-133">您應該在使用者第一次啟動商務用 Skype 用戶端之前執行此動作, 而您只能執行此動作一次。</span><span class="sxs-lookup"><span data-stu-id="aec12-133">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="aec12-134">如需如何建立群組原則物件以更新加入網域的電腦上的登錄的相關資訊, 請參閱主題稍後的章節。</span><span class="sxs-lookup"><span data-stu-id="aec12-134">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="aec12-135">在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** 索引鍵中, 建立新的**二進位**值。</span><span class="sxs-lookup"><span data-stu-id="aec12-135">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="aec12-136">**值名稱**必須是**EnableSkypeUI**, 而**值資料**必須設定為**00 00 00 00**。</span><span class="sxs-lookup"><span data-stu-id="aec12-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="aec12-137">此索引鍵看起來應該像以下這樣:</span><span class="sxs-lookup"><span data-stu-id="aec12-137">The key should look like the following:</span></span>
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

<span data-ttu-id="aec12-138">Lync 使用者介面現在會在使用者第一次啟動商務用 Skype 用戶端時顯示。</span><span class="sxs-lookup"><span data-stu-id="aec12-138">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="aec12-139">控制歡迎畫面教學課程的顯示</span><span class="sxs-lookup"><span data-stu-id="aec12-139">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="aec12-140">當使用者開啟商務用 Skype 用戶端時, 預設行為是顯示 [歡迎] 畫面, 其中包含*大部分人要求的7個快速秘訣*。</span><span class="sxs-lookup"><span data-stu-id="aec12-140">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes  *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="aec12-141">您可以在用戶端電腦上新增下列登錄值, 以關閉歡迎畫面的顯示, 但仍允許使用者存取教學課程:</span><span class="sxs-lookup"><span data-stu-id="aec12-141">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="aec12-142">在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 索引鍵中, 建立新的**DWORD (32 位) 值**。</span><span class="sxs-lookup"><span data-stu-id="aec12-142">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="aec12-143">**值名稱**必須是**IsBasicTutorialSeenByUser**, 而**值資料**必須設定為**1**。</span><span class="sxs-lookup"><span data-stu-id="aec12-143">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="aec12-144">此索引鍵看起來應該像以下這樣:</span><span class="sxs-lookup"><span data-stu-id="aec12-144">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="aec12-145">關閉用戶端教學課程</span><span class="sxs-lookup"><span data-stu-id="aec12-145">Turn off the client tutorial</span></span>

<span data-ttu-id="aec12-146">如果您不想讓使用者存取教學課程, 您可以使用下列登錄值來關閉用戶端教學課程:</span><span class="sxs-lookup"><span data-stu-id="aec12-146">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="aec12-147">在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 索引鍵中, 建立新的**DWORD (32 位) 值**。</span><span class="sxs-lookup"><span data-stu-id="aec12-147">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="aec12-148">**值名稱**必須是**TutorialFeatureEnabled**, 而**值資料**必須設定為**0**。</span><span class="sxs-lookup"><span data-stu-id="aec12-148">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
<span data-ttu-id="aec12-149">Lync</span><span class="sxs-lookup"><span data-stu-id="aec12-149">Lync</span></span>
  
```
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="aec12-150">您可以將**值資料**設定為**1**, 將教學課程改回開啟。</span><span class="sxs-lookup"><span data-stu-id="aec12-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="default-client-behaviors"></a><span data-ttu-id="aec12-151">預設用戶端行為</span><span class="sxs-lookup"><span data-stu-id="aec12-151">Default client behaviors</span></span>

<span data-ttu-id="aec12-152">如果貴組織已部署商務用 Skype Server 和 Lync Server, 則用戶端體驗會隨著伺服器版本和 Skype UI 設定而有所不同。</span><span class="sxs-lookup"><span data-stu-id="aec12-152">If your organization has both Skype for Business Server and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="aec12-153">下表顯示以伺服器版本和 UI 設定為基礎的初始用戶端體驗:</span><span class="sxs-lookup"><span data-stu-id="aec12-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>
  

|<span data-ttu-id="aec12-154">**伺服器版本**</span><span class="sxs-lookup"><span data-stu-id="aec12-154">**Server version**</span></span>|<span data-ttu-id="aec12-155">**EnableSkypeUI 設定**</span><span class="sxs-lookup"><span data-stu-id="aec12-155">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="aec12-156">**用戶端體驗**</span><span class="sxs-lookup"><span data-stu-id="aec12-156">**Client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aec12-157">商務用 Skype 伺服器</span><span class="sxs-lookup"><span data-stu-id="aec12-157">Skype for Business Server</span></span> |<span data-ttu-id="aec12-158">設置</span><span class="sxs-lookup"><span data-stu-id="aec12-158">Default</span></span>  <br/> |<span data-ttu-id="aec12-159">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="aec12-159">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="aec12-160">商務用 Skype 伺服器</span><span class="sxs-lookup"><span data-stu-id="aec12-160">Skype for Business Server</span></span>  |<span data-ttu-id="aec12-161">滿足</span><span class="sxs-lookup"><span data-stu-id="aec12-161">True</span></span>  <br/> |<span data-ttu-id="aec12-162">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="aec12-162">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="aec12-163">商務用 Skype 伺服器</span><span class="sxs-lookup"><span data-stu-id="aec12-163">Skype for Business Server</span></span>  |<span data-ttu-id="aec12-164">虛假</span><span class="sxs-lookup"><span data-stu-id="aec12-164">False</span></span>  <br/> |<span data-ttu-id="aec12-165">使用者要求切換至 Lync 模式 (如果您將 UI 設定變更為 $true, 使用者就可以在稍後切換到商務用 Skype)</span><span class="sxs-lookup"><span data-stu-id="aec12-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="aec12-166">Lync Server 2010 或 Lync Server 2013 (含正確的修補程式)</span><span class="sxs-lookup"><span data-stu-id="aec12-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="aec12-167">設置</span><span class="sxs-lookup"><span data-stu-id="aec12-167">Default</span></span>  <br/> |<span data-ttu-id="aec12-168">使用者要求切換至 Lync 模式 (如果您將 UI 設定變更為 $true, 使用者就可以在稍後切換到商務用 Skype)</span><span class="sxs-lookup"><span data-stu-id="aec12-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="aec12-169">Lync Server 2010 或 Lync Server 2013 (含正確的修補程式)</span><span class="sxs-lookup"><span data-stu-id="aec12-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="aec12-170">滿足</span><span class="sxs-lookup"><span data-stu-id="aec12-170">True</span></span>  <br/> |<span data-ttu-id="aec12-171">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="aec12-171">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="aec12-172">Lync Server 2010 或 Lync Server 2013 (含正確的修補程式)</span><span class="sxs-lookup"><span data-stu-id="aec12-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="aec12-173">虛假</span><span class="sxs-lookup"><span data-stu-id="aec12-173">False</span></span>  <br/> |<span data-ttu-id="aec12-174">使用者要求切換至 Lync 模式 (如果您將 UI 設定變更為 $true, 使用者就可以在稍後切換到商務用 Skype)</span><span class="sxs-lookup"><span data-stu-id="aec12-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="aec12-175">Lync Server 2010 或 Lync Server 2013 (不含補丁程式)</span><span class="sxs-lookup"><span data-stu-id="aec12-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="aec12-176">設置</span><span class="sxs-lookup"><span data-stu-id="aec12-176">Default</span></span>  <br/> |<span data-ttu-id="aec12-177">使用者要求切換至 Lync 模式 (使用者稍後無法切換到商務用 Skype)</span><span class="sxs-lookup"><span data-stu-id="aec12-177">User asked to switch to Lync mode (user cannot switch to Skype for Business later)</span></span>  <br/> |
   
<span data-ttu-id="aec12-178">下表顯示管理員變更 Skype UI 體驗的初始設定時的用戶端體驗:</span><span class="sxs-lookup"><span data-stu-id="aec12-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>
  

|<span data-ttu-id="aec12-179">**伺服器版本**</span><span class="sxs-lookup"><span data-stu-id="aec12-179">**Server version**</span></span>|<span data-ttu-id="aec12-180">**EnableSkypeUI 設定**</span><span class="sxs-lookup"><span data-stu-id="aec12-180">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="aec12-181">**用戶端 UI = Lync**</span><span class="sxs-lookup"><span data-stu-id="aec12-181">**Client UI = Lync**</span></span>|<span data-ttu-id="aec12-182">**用戶端 UI = 商務用 Skype**</span><span class="sxs-lookup"><span data-stu-id="aec12-182">**Client UI = Skype for Business**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="aec12-183">商務用 Skype 伺服器</span><span class="sxs-lookup"><span data-stu-id="aec12-183">Skype for Business Server</span></span> |<span data-ttu-id="aec12-184">滿足</span><span class="sxs-lookup"><span data-stu-id="aec12-184">True</span></span>  <br/> |<span data-ttu-id="aec12-185">使用者要求切換到商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="aec12-185">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="aec12-186">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="aec12-186">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="aec12-187">商務用 Skype 伺服器</span><span class="sxs-lookup"><span data-stu-id="aec12-187">Skype for Business Server</span></span> |<span data-ttu-id="aec12-188">虛假</span><span class="sxs-lookup"><span data-stu-id="aec12-188">False</span></span>  <br/> |<span data-ttu-id="aec12-189">Lync 模式</span><span class="sxs-lookup"><span data-stu-id="aec12-189">Lync mode</span></span>  <br/> |<span data-ttu-id="aec12-190">使用者要求切換至 Lync 模式</span><span class="sxs-lookup"><span data-stu-id="aec12-190">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="aec12-191">Lync Server 2010 或 Lync Server 2013 (含正確的修補程式)</span><span class="sxs-lookup"><span data-stu-id="aec12-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="aec12-192">滿足</span><span class="sxs-lookup"><span data-stu-id="aec12-192">True</span></span>  <br/> |<span data-ttu-id="aec12-193">使用者要求切換到商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="aec12-193">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="aec12-194">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="aec12-194">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="aec12-195">Lync Server 2010 或 Lync Server 2013 (含正確的修補程式)</span><span class="sxs-lookup"><span data-stu-id="aec12-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="aec12-196">虛假</span><span class="sxs-lookup"><span data-stu-id="aec12-196">False</span></span>  <br/> |<span data-ttu-id="aec12-197">Lync 模式</span><span class="sxs-lookup"><span data-stu-id="aec12-197">Lync mode</span></span>  <br/> |<span data-ttu-id="aec12-198">使用者要求切換至 Lync 模式</span><span class="sxs-lookup"><span data-stu-id="aec12-198">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="aec12-199">Lync Server 2010 或 Lync Server 2013 (不含補丁程式)</span><span class="sxs-lookup"><span data-stu-id="aec12-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="aec12-200">設置</span><span class="sxs-lookup"><span data-stu-id="aec12-200">Default</span></span>  <br/> |<span data-ttu-id="aec12-201">Lync 模式 (無法切換到商務用 Skype)</span><span class="sxs-lookup"><span data-stu-id="aec12-201">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |<span data-ttu-id="aec12-202">Lync 模式 (無法切換到商務用 Skype)</span><span class="sxs-lookup"><span data-stu-id="aec12-202">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |
   
<span data-ttu-id="aec12-203">管理商務用 Skype 用戶端設定所需的修補程式版本如下:</span><span class="sxs-lookup"><span data-stu-id="aec12-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>
  
- <span data-ttu-id="aec12-204">Lync Server 2010-Lync Server 2010 的2015年2月累計更新 (4.0.7577.710)。</span><span class="sxs-lookup"><span data-stu-id="aec12-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="aec12-205">如需詳細資訊, 請參閱[Lync Server 2010 更新](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span><span class="sxs-lookup"><span data-stu-id="aec12-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span></span>
    
- <span data-ttu-id="aec12-206">Lync Server 2013-Lync Server 2013 的2014年12月累計更新 (5.0.8308.857)。</span><span class="sxs-lookup"><span data-stu-id="aec12-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="aec12-207">如需詳細資訊, 請參閱[Lync Server 2013 更新](https://go.microsoft.com/fwlink/p/?LinkId=532772)。</span><span class="sxs-lookup"><span data-stu-id="aec12-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="aec12-208">建立群組原則物件來修改加入網域的電腦上的登錄</span><span class="sxs-lookup"><span data-stu-id="aec12-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="aec12-209">[登錄更新] 會在使用者第一次啟動商務用 Skype 2015 用戶端時, 顯示 Lync 用戶端體驗一次。</span><span class="sxs-lookup"><span data-stu-id="aec12-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business 2015 client should be done only once.</span></span> <span data-ttu-id="aec12-210">如果您使用群組原則物件 (GPO) 來更新註冊表, 您需要定義物件來建立新的值, 而不是更新值資料。</span><span class="sxs-lookup"><span data-stu-id="aec12-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="aec12-211">當套用 GPO 時, 如果新值不存在, GPO 將會建立它, 並將值資料設定為0。</span><span class="sxs-lookup"><span data-stu-id="aec12-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span> 
  
<span data-ttu-id="aec12-212">下列程式說明如何修改註冊表, 以便在使用者第一次啟動商務用 Skype 2015 用戶端時顯示 Lync 用戶端體驗。</span><span class="sxs-lookup"><span data-stu-id="aec12-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business 2015 client.</span></span> <span data-ttu-id="aec12-213">您也可以使用此程式來更新註冊表, 如前文所述, 停用歡迎畫面教學課程。</span><span class="sxs-lookup"><span data-stu-id="aec12-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
### <a name="to-create-the-gpo"></a><span data-ttu-id="aec12-214">建立 GPO</span><span class="sxs-lookup"><span data-stu-id="aec12-214">To create the GPO</span></span>

1. <span data-ttu-id="aec12-215">啟動**群組原則管理主控台**。</span><span class="sxs-lookup"><span data-stu-id="aec12-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="aec12-216">如需如何使用群組原則管理主控台的相關資訊, 請參閱[群群組原則管理主控台](https://go.microsoft.com/fwlink/?LinkId=532759)。</span><span class="sxs-lookup"><span data-stu-id="aec12-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="aec12-217">以滑鼠右鍵按一下 [**群群組原則物件**] 節點, 然後在功能表上選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="aec12-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="aec12-218">在 [**新增 gpo** ] 對話方塊中, 輸入 GPO 的名稱, 例如 [MakeLyncDefaultUI], 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="aec12-218">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="aec12-219">以滑鼠右鍵按一下您剛建立的新 GPO, 然後從功能表中選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="aec12-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="aec12-220">在 [**群組原則管理編輯器**] 中, 展開 [**使用者**設定], 展開 [**喜好**設定], 展開\*\*\*\* [ **Windows 設定**], 然後選取 [登錄] 節點。</span><span class="sxs-lookup"><span data-stu-id="aec12-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="aec12-221">以滑鼠右鍵按一下 [ \*\*\*\* 登錄] 節點, 然後選取 [**新增** > **註冊專案**]。</span><span class="sxs-lookup"><span data-stu-id="aec12-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="aec12-222">在 [**新增登錄屬性**] 對話方塊中, 更新下列專案:</span><span class="sxs-lookup"><span data-stu-id="aec12-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
   |<span data-ttu-id="aec12-223">**域**</span><span class="sxs-lookup"><span data-stu-id="aec12-223">**Field**</span></span>|<span data-ttu-id="aec12-224">**要選取或輸入的值**</span><span class="sxs-lookup"><span data-stu-id="aec12-224">**Value to select or enter**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="aec12-225">**執行**</span><span class="sxs-lookup"><span data-stu-id="aec12-225">**Action**</span></span> <br/> |<span data-ttu-id="aec12-226">**建立**</span><span class="sxs-lookup"><span data-stu-id="aec12-226">**Create**</span></span> <br/> |
   |<span data-ttu-id="aec12-227">**一兩**</span><span class="sxs-lookup"><span data-stu-id="aec12-227">**Hive**</span></span> <br/> | <span data-ttu-id="aec12-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="aec12-228">HKEY_CURRENT_USER</span></span> <br/> |
   |<span data-ttu-id="aec12-229">**索引鍵路徑**</span><span class="sxs-lookup"><span data-stu-id="aec12-229">**Key Path**</span></span> <br/> |<span data-ttu-id="aec12-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="aec12-230">Software\Microsoft\Office\Lync</span></span>  <br/> |
   |<span data-ttu-id="aec12-231">**值名稱**</span><span class="sxs-lookup"><span data-stu-id="aec12-231">**Value name**</span></span> <br/> |<span data-ttu-id="aec12-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="aec12-232">EnableSkypeUI</span></span>  <br/> |
   |<span data-ttu-id="aec12-233">**數值型別**</span><span class="sxs-lookup"><span data-stu-id="aec12-233">**Value type**</span></span> <br/> |<span data-ttu-id="aec12-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="aec12-234">REG_BINARY</span></span>  <br/> |
   |<span data-ttu-id="aec12-235">**值資料**</span><span class="sxs-lookup"><span data-stu-id="aec12-235">**Value data**</span></span> <br/> |<span data-ttu-id="aec12-236">00000000</span><span class="sxs-lookup"><span data-stu-id="aec12-236">00000000</span></span>  <br/> |
   
8. <span data-ttu-id="aec12-237">按一下 **[確定]** 儲存變更, 然後關閉該 GPO。</span><span class="sxs-lookup"><span data-stu-id="aec12-237">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="aec12-238">接著, 您必須將您所建立的 GPO 連結至您要指派原則的使用者群組 (例如 OU)。</span><span class="sxs-lookup"><span data-stu-id="aec12-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a><span data-ttu-id="aec12-239">使用 GPO 指派原則</span><span class="sxs-lookup"><span data-stu-id="aec12-239">To use the GPO to assign the policy</span></span>

1. <span data-ttu-id="aec12-240">在 [群組原則管理主控台] 中, 以滑鼠右鍵按一下您要指派原則的 OU, 然後選取 [**連結到現有的 GPO**]。</span><span class="sxs-lookup"><span data-stu-id="aec12-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="aec12-241">在 [**選取 gpo** ] 對話方塊中, 選取您所建立的 GPO, 然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="aec12-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="aec12-242">在目標使用者的電腦上, 開啟命令提示字元, 然後輸入下列命令:</span><span class="sxs-lookup"><span data-stu-id="aec12-242">On the target user's computer, open a command prompt and type the following command:</span></span>
       
```
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. <span data-ttu-id="aec12-243">在命令提示字元中, 輸入下列命令:</span><span class="sxs-lookup"><span data-stu-id="aec12-243">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="aec12-244">**gpresult/r**</span><span class="sxs-lookup"><span data-stu-id="aec12-244">**gpresult /r**</span></span>
    
    <span data-ttu-id="aec12-245">您應該會看到「指派的群群組原則物件」與您所建立之 GPO 的名稱, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="aec12-245">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="aec12-246">您也可以檢查登錄, 以驗證 GPO 是否已在使用者的電腦上成功更新登錄。</span><span class="sxs-lookup"><span data-stu-id="aec12-246">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="aec12-247">開啟 [登錄編輯程式], 然後流覽至 **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** 索引鍵。</span><span class="sxs-lookup"><span data-stu-id="aec12-247">Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key.</span></span> <span data-ttu-id="aec12-248">如果 GPO 成功更新了註冊表, 您會看到一個名為 EnableSkypeUI 的值, 其值為0。</span><span class="sxs-lookup"><span data-stu-id="aec12-248">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  

