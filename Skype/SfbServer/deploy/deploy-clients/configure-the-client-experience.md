---
title: 使用商務用 Skype 2015 設定用戶端體驗
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 摘要：閱讀此主題以瞭解如何設定商務用 Skype 使用者的用戶端經驗。
ms.openlocfilehash: 2125f911927bfe1aa8898c89c6ad70439186a8c0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805953"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a><span data-ttu-id="b2b9b-103">使用商務用 Skype 2015 設定用戶端體驗</span><span class="sxs-lookup"><span data-stu-id="b2b9b-103">Configure the client experience with Skype for Business 2015</span></span>
 
<span data-ttu-id="b2b9b-104">**摘要：** 閱讀此主題以瞭解如何設定商務用 Skype 2015 使用者的用戶端經驗。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-104">**Summary:** Read this topic to learn how to configure the client experience for Skype for Business 2015 users.</span></span>
  
<span data-ttu-id="b2b9b-105">商務用 skype 2015 提供以 Skype 消費者產品經驗為基礎的新使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-105">Skype for Business 2015 provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="b2b9b-106">除了 Lync 的所有功能之外，商務用 Skype 也會透過簡化的控制項及熟悉的圖示來提供新功能。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-106">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="b2b9b-107">如需有關新用戶端體驗的詳細資訊，請參閱 [探索商務用 Skype](https://go.microsoft.com/fwlink/?LinkId=529022)。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-107">For detailed information about the new client experience, see [Explore Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).</span></span>
  
<span data-ttu-id="b2b9b-108">商務用 skype 伺服器支援新的商務用 Skype 用戶端體驗和 Lync 用戶端經驗。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-108">Skype for Business Server supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="b2b9b-109">身為管理員，您可以為使用者選擇喜歡的用戶端體驗。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-109">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="b2b9b-110">例如，您可能想要部署 Lync 用戶端體驗，直到貴組織中的使用者已完全訓練新的商務用 Skype 體驗。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-110">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="b2b9b-111">或者，如果您尚未將所有使用者升級至商務用 Skype Server，您可能會希望所有使用者都能使用相同的用戶端體驗，直到全部使用者都升級至新伺服器為止。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-111">Or, if you have not yet upgraded all users to Skype for Business Server, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b2b9b-112">如果您的組織同時已部署商務用 Skype Server 和 Lync Server，則預設的用戶端體驗會因伺服器版本和使用者介面設定而異。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-112">If your organization has both Skype for Business Server and Lync Server deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="b2b9b-113">當使用者第一次啟動商務用 Skype 時，他們會永遠看到商務用 Skype 使用者介面，即使您已選取 Lync 用戶端經驗也是一樣。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-113">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience.</span></span> <span data-ttu-id="b2b9b-114">幾分鐘後，系統會要求使用者切換至 Lync 模式。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-114">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="b2b9b-115">如需詳細資訊，請參閱本主題稍後的 **第一次啟動用戶端行為** 。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-115">For more information, see **First launch client behavior** later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b2b9b-116">Lync 2013 用戶端體驗不是商務用 Skype 2016 用戶端版本或更新版本的選項。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions or later.</span></span> <span data-ttu-id="b2b9b-117">在您嘗試設定用戶端環境以使用 Lync 2013 用戶端之前，請檢查用戶端版本，以確保其不是以數位16開頭;例如： x.x.x。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="configure-the-client-experience"></a><span data-ttu-id="b2b9b-118">設定用戶端體驗</span><span class="sxs-lookup"><span data-stu-id="b2b9b-118">Configure the client experience</span></span>

<span data-ttu-id="b2b9b-119">您可以使用 **Set-CSClientPolicy** Cmdlet 搭配 EnableSkypeUI 參數，指定您組織中的使用者所看到的用戶端體驗：</span><span class="sxs-lookup"><span data-stu-id="b2b9b-119">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter:</span></span>
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

<span data-ttu-id="b2b9b-120">其中 Microsoft.rtc.management.xds.xdsidentity 指的是全域原則或已命名的網站原則。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-120">where XdsIdentity refers to the Global policy or a named site policy.</span></span>
  
<span data-ttu-id="b2b9b-121">下列命令會為組織中受全域原則影響的所有使用者選取商務用 Skype 用戶端體驗 (請記住，網站或使用者特定原則會覆寫全域原則) ：</span><span class="sxs-lookup"><span data-stu-id="b2b9b-121">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span> 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

<span data-ttu-id="b2b9b-122">下一個命令會為組織中的所有使用者選取受全域原則影響的 Lync 用戶端體驗：</span><span class="sxs-lookup"><span data-stu-id="b2b9b-122">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

<span data-ttu-id="b2b9b-123">下一個命令會為 Redmond 網站內的所有使用者選取商務用 Skype 用戶端體驗：</span><span class="sxs-lookup"><span data-stu-id="b2b9b-123">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

<span data-ttu-id="b2b9b-124">如果您想要為組織內的特定使用者設定用戶端經驗，您可以使用 **New-CsClientPolicy** Cmdlet 來建立新的使用者原則，然後使用 **Grant-CsClientPolicy** Cmdlet 將原則指派給特定使用者。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-124">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>
  
<span data-ttu-id="b2b9b-125">例如，下列命令會建立新的用戶端原則 SalesClientUI，以選取商務用 Skype 用戶端體驗：</span><span class="sxs-lookup"><span data-stu-id="b2b9b-125">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

<span data-ttu-id="b2b9b-126">下一個命令會將原則 SalesClientUI 指派給銷售部門的所有成員：</span><span class="sxs-lookup"><span data-stu-id="b2b9b-126">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="b2b9b-127">第一次啟動用戶端行為</span><span class="sxs-lookup"><span data-stu-id="b2b9b-127">First launch client behaviors</span></span>

<span data-ttu-id="b2b9b-128">根據預設，當使用者第一次啟動商務用 Skype 2015 時，他們會永遠看到商務用 Skype 使用者介面--即使您已透過將 EnableSkypeUI 參數的值設為 $False，如先前所述，您已選取 Lync 用戶端經驗。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-128">By default, when users launch Skype for Business 2015 for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="b2b9b-129">幾分鐘後，系統會要求使用者切換至 Lync 模式。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-129">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="b2b9b-130">當使用者第一次啟動商務用 Skype 用戶端時，如果您想要顯示 Lync 使用者介面，請在更新後第一次啟動用戶端之前，先執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="b2b9b-130">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="b2b9b-131">確認的值  `EnableSkypeUI` 已設定為在您使用的原則中 $False，如先前所述。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-131">Confirm that the value of  `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>
    
2. <span data-ttu-id="b2b9b-132">更新使用者電腦上的系統登錄。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-132">Update the system registry on the user's computer.</span></span> <span data-ttu-id="b2b9b-133">您應該在使用者第一次啟動商務用 Skype 用戶端之前執行此作業，而且您應該只執行一次。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-133">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="b2b9b-134">如需如何建立群組原則物件以更新加入網域之電腦上之登錄的詳細資訊，請參閱本主題稍後的章節。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-134">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="b2b9b-135">在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** 機碼中，建立新的 **二進位** 值。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-135">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="b2b9b-136">**值名稱** 必須是 **EnableSkypeUI**，且 **數值資料** 必須設定為 **00 00 00 00**。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="b2b9b-137">索引鍵應該如下所示：</span><span class="sxs-lookup"><span data-stu-id="b2b9b-137">The key should look like the following:</span></span>
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

<span data-ttu-id="b2b9b-138">當使用者第一次啟動商務用 Skype 用戶端時，即會顯示 Lync 使用者介面。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-138">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="b2b9b-139">控制歡迎使用畫面教學課程的顯示</span><span class="sxs-lookup"><span data-stu-id="b2b9b-139">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="b2b9b-140">當使用者開啟商務用 Skype 用戶端時，預設行為是顯示歡迎畫面，其中包含  *大多數人員所要求的7個快速秘訣*。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-140">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes  *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="b2b9b-141">您可以在用戶端電腦上新增下列登錄值，關閉 [歡迎] 畫面，但仍允許使用者存取教學課程：</span><span class="sxs-lookup"><span data-stu-id="b2b9b-141">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="b2b9b-142">在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 機碼中，建立新的 **DWORD (32-bit) 值**。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-142">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="b2b9b-143">**值名稱** 必須是 **IsBasicTutorialSeenByUser**，且 **數值資料** 必須設定為 **1**。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-143">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="b2b9b-144">索引鍵應該如下所示：</span><span class="sxs-lookup"><span data-stu-id="b2b9b-144">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="b2b9b-145">關閉用戶端教學課程</span><span class="sxs-lookup"><span data-stu-id="b2b9b-145">Turn off the client tutorial</span></span>

<span data-ttu-id="b2b9b-146">如果您不想讓使用者能夠存取教學課程，您可以使用下列登錄值來關閉用戶端教學課程：</span><span class="sxs-lookup"><span data-stu-id="b2b9b-146">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="b2b9b-147">在 **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 機碼中，建立新的 **DWORD (32-bit) 值**。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-147">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="b2b9b-148">**值名稱** 必須是 **TutorialFeatureEnabled**，且 **數值資料** 必須設定為 **0**。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-148">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
<span data-ttu-id="b2b9b-149">Lync</span><span class="sxs-lookup"><span data-stu-id="b2b9b-149">Lync</span></span>
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="b2b9b-150">您可以將 **數值資料** 設為 **1**，以重新開啟教學課程。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="default-client-behaviors"></a><span data-ttu-id="b2b9b-151">預設用戶端行為</span><span class="sxs-lookup"><span data-stu-id="b2b9b-151">Default client behaviors</span></span>

<span data-ttu-id="b2b9b-152">如果您的組織同時已部署商務用 Skype Server 和 Lync Server，則用戶端經驗會因伺服器版本和 Skype UI 設定而有所不同。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-152">If your organization has both Skype for Business Server and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="b2b9b-153">下表顯示以伺服器版本及 UI 設定為基礎的初始用戶端體驗：</span><span class="sxs-lookup"><span data-stu-id="b2b9b-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>
  

|<span data-ttu-id="b2b9b-154">**伺服器版本**</span><span class="sxs-lookup"><span data-stu-id="b2b9b-154">**Server version**</span></span>|<span data-ttu-id="b2b9b-155">**EnableSkypeUI 設定**</span><span class="sxs-lookup"><span data-stu-id="b2b9b-155">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="b2b9b-156">**用戶端經驗**</span><span class="sxs-lookup"><span data-stu-id="b2b9b-156">**Client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b2b9b-157">商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="b2b9b-157">Skype for Business Server</span></span> |<span data-ttu-id="b2b9b-158">預設</span><span class="sxs-lookup"><span data-stu-id="b2b9b-158">Default</span></span>  <br/> |<span data-ttu-id="b2b9b-159">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="b2b9b-159">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="b2b9b-160">商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="b2b9b-160">Skype for Business Server</span></span>  |<span data-ttu-id="b2b9b-161">是</span><span class="sxs-lookup"><span data-stu-id="b2b9b-161">True</span></span>  <br/> |<span data-ttu-id="b2b9b-162">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="b2b9b-162">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="b2b9b-163">商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="b2b9b-163">Skype for Business Server</span></span>  |<span data-ttu-id="b2b9b-164">False</span><span class="sxs-lookup"><span data-stu-id="b2b9b-164">False</span></span>  <br/> |<span data-ttu-id="b2b9b-165">使用者要求切換至 Lync 模式 (使用者可以在稍後將 UI 設定變更為 $true，以切換至商務用 Skype。) </span><span class="sxs-lookup"><span data-stu-id="b2b9b-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="b2b9b-166">使用正確修補程式的 lync Server 2010 或 Lync Server 2013 () </span><span class="sxs-lookup"><span data-stu-id="b2b9b-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="b2b9b-167">預設</span><span class="sxs-lookup"><span data-stu-id="b2b9b-167">Default</span></span>  <br/> |<span data-ttu-id="b2b9b-168">使用者要求切換至 Lync 模式 (使用者可以在稍後將 UI 設定變更為 $true，以切換至商務用 Skype。) </span><span class="sxs-lookup"><span data-stu-id="b2b9b-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="b2b9b-169">使用正確修補程式的 lync Server 2010 或 Lync Server 2013 () </span><span class="sxs-lookup"><span data-stu-id="b2b9b-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="b2b9b-170">是</span><span class="sxs-lookup"><span data-stu-id="b2b9b-170">True</span></span>  <br/> |<span data-ttu-id="b2b9b-171">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="b2b9b-171">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="b2b9b-172">使用正確修補程式的 lync Server 2010 或 Lync Server 2013 () </span><span class="sxs-lookup"><span data-stu-id="b2b9b-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="b2b9b-173">False</span><span class="sxs-lookup"><span data-stu-id="b2b9b-173">False</span></span>  <br/> |<span data-ttu-id="b2b9b-174">使用者要求切換至 Lync 模式 (使用者可以在稍後將 UI 設定變更為 $true，以切換至商務用 Skype。) </span><span class="sxs-lookup"><span data-stu-id="b2b9b-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="b2b9b-175">不含修補程式的 lync Server 2010 或 Lync Server 2013 () </span><span class="sxs-lookup"><span data-stu-id="b2b9b-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="b2b9b-176">預設</span><span class="sxs-lookup"><span data-stu-id="b2b9b-176">Default</span></span>  <br/> |<span data-ttu-id="b2b9b-177">使用者要求切換至 Lync 模式 (使用者無法切換至商務用 Skype) </span><span class="sxs-lookup"><span data-stu-id="b2b9b-177">User asked to switch to Lync mode (user cannot switch to Skype for Business later)</span></span>  <br/> |
   
<span data-ttu-id="b2b9b-178">下表顯示管理員變更 Skype 使用者介面體驗的初始設定時，用戶端的經驗。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>
  

|<span data-ttu-id="b2b9b-179">**伺服器版本**</span><span class="sxs-lookup"><span data-stu-id="b2b9b-179">**Server version**</span></span>|<span data-ttu-id="b2b9b-180">**EnableSkypeUI 設定**</span><span class="sxs-lookup"><span data-stu-id="b2b9b-180">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="b2b9b-181">**用戶端 UI = Lync**</span><span class="sxs-lookup"><span data-stu-id="b2b9b-181">**Client UI = Lync**</span></span>|<span data-ttu-id="b2b9b-182">**用戶端 UI = 商務用 Skype**</span><span class="sxs-lookup"><span data-stu-id="b2b9b-182">**Client UI = Skype for Business**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b2b9b-183">商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="b2b9b-183">Skype for Business Server</span></span> |<span data-ttu-id="b2b9b-184">是</span><span class="sxs-lookup"><span data-stu-id="b2b9b-184">True</span></span>  <br/> |<span data-ttu-id="b2b9b-185">使用者要求切換至商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="b2b9b-185">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="b2b9b-186">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="b2b9b-186">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="b2b9b-187">商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="b2b9b-187">Skype for Business Server</span></span> |<span data-ttu-id="b2b9b-188">False</span><span class="sxs-lookup"><span data-stu-id="b2b9b-188">False</span></span>  <br/> |<span data-ttu-id="b2b9b-189">Lync 模式</span><span class="sxs-lookup"><span data-stu-id="b2b9b-189">Lync mode</span></span>  <br/> |<span data-ttu-id="b2b9b-190">使用者要求切換至 Lync 模式</span><span class="sxs-lookup"><span data-stu-id="b2b9b-190">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="b2b9b-191">使用正確修補程式的 lync Server 2010 或 Lync Server 2013 () </span><span class="sxs-lookup"><span data-stu-id="b2b9b-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="b2b9b-192">是</span><span class="sxs-lookup"><span data-stu-id="b2b9b-192">True</span></span>  <br/> |<span data-ttu-id="b2b9b-193">使用者要求切換至商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="b2b9b-193">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="b2b9b-194">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="b2b9b-194">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="b2b9b-195">使用正確修補程式的 lync Server 2010 或 Lync Server 2013 () </span><span class="sxs-lookup"><span data-stu-id="b2b9b-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="b2b9b-196">False</span><span class="sxs-lookup"><span data-stu-id="b2b9b-196">False</span></span>  <br/> |<span data-ttu-id="b2b9b-197">Lync 模式</span><span class="sxs-lookup"><span data-stu-id="b2b9b-197">Lync mode</span></span>  <br/> |<span data-ttu-id="b2b9b-198">使用者要求切換至 Lync 模式</span><span class="sxs-lookup"><span data-stu-id="b2b9b-198">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="b2b9b-199">不含修補程式的 lync Server 2010 或 Lync Server 2013 () </span><span class="sxs-lookup"><span data-stu-id="b2b9b-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="b2b9b-200">預設</span><span class="sxs-lookup"><span data-stu-id="b2b9b-200">Default</span></span>  <br/> |<span data-ttu-id="b2b9b-201">Lync 模式 (無法切換至商務用 Skype) </span><span class="sxs-lookup"><span data-stu-id="b2b9b-201">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |<span data-ttu-id="b2b9b-202">Lync 模式 (無法切換至商務用 Skype) </span><span class="sxs-lookup"><span data-stu-id="b2b9b-202">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |
   
<span data-ttu-id="b2b9b-203">管理商務用 Skype 用戶端設定所需的修補程式版本如下：</span><span class="sxs-lookup"><span data-stu-id="b2b9b-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>
  
- <span data-ttu-id="b2b9b-204">Lync Server 2010-2 月2015累積更新 (4.0.7577.710) 的 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="b2b9b-205">如需詳細資訊，請參閱 [Lync Server 2010 的更新](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span><span class="sxs-lookup"><span data-stu-id="b2b9b-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span></span>
    
- <span data-ttu-id="b2b9b-206">Lync Server 2013-Lync Server 2013 的2014累計更新 (5.0.8308.857) 。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="b2b9b-207">如需詳細資訊，請參閱 [Lync Server 2013 的更新](https://go.microsoft.com/fwlink/p/?LinkId=532772)。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="b2b9b-208">建立群組原則物件以在加入網域的電腦上修改登錄</span><span class="sxs-lookup"><span data-stu-id="b2b9b-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="b2b9b-209">當使用者第一次啟動商務用 Skype 2015 用戶端時，要顯示 Lync 用戶端經驗的登錄更新，應只執行一次。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business 2015 client should be done only once.</span></span> <span data-ttu-id="b2b9b-210">如果您使用群組原則物件 (GPO) 來更新登錄，您必須定義物件來建立新的值，而不是更新值資料。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="b2b9b-211">套用 GPO 時，如果新值不存在，GPO 將會建立它，並將數值資料設定為0。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span> 
  
<span data-ttu-id="b2b9b-212">下列程式說明如何修改登錄，讓使用者第一次啟動商務用 Skype 2015 用戶端時，會顯示 Lync 用戶端體驗。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business 2015 client.</span></span> <span data-ttu-id="b2b9b-213">您也可以使用此程式來更新登錄，以停用先前所述的歡迎畫面教學課程。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
### <a name="to-create-the-gpo"></a><span data-ttu-id="b2b9b-214">建立 GPO</span><span class="sxs-lookup"><span data-stu-id="b2b9b-214">To create the GPO</span></span>

1. <span data-ttu-id="b2b9b-215">啟動 [ **群組原則管理主控台**]。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="b2b9b-216">如需如何使用「群組原則管理主控台」的詳細資訊，請參閱 [群組原則管理主控台](https://go.microsoft.com/fwlink/?LinkId=532759)。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="b2b9b-217">在 [ **群組原則物件** ] 節點上按一下滑鼠右鍵，然後在功能表上選取 [ **新增** ]。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="b2b9b-218">在 [ **新增 gpo** ] 對話方塊中，輸入 GPO 的名稱，例如 [MakeLyncDefaultUI]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-218">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="b2b9b-219">在您剛才建立的新 GPO 上按一下滑鼠右鍵，然後從功能表中選取 [ **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="b2b9b-220">在 [**群組原則管理編輯器**] 中，展開 [**使用者** 設定]，展開 [**喜好** 設定]，展開 [ **Windows 設定**]，然後選取 **登錄節點。**</span><span class="sxs-lookup"><span data-stu-id="b2b9b-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="b2b9b-221">**在 [登錄**] 節點上按一下滑鼠右鍵，然後選取 [**新增** 登錄  >  **專案**]。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="b2b9b-222">在 [ **新增註冊表屬性** ] 對話方塊中，更新下列專案：</span><span class="sxs-lookup"><span data-stu-id="b2b9b-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
   |<span data-ttu-id="b2b9b-223">**Field**</span><span class="sxs-lookup"><span data-stu-id="b2b9b-223">**Field**</span></span>|<span data-ttu-id="b2b9b-224">**要選取或輸入的值**</span><span class="sxs-lookup"><span data-stu-id="b2b9b-224">**Value to select or enter**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="b2b9b-225">**動作**</span><span class="sxs-lookup"><span data-stu-id="b2b9b-225">**Action**</span></span> <br/> |<span data-ttu-id="b2b9b-226">**Create**</span><span class="sxs-lookup"><span data-stu-id="b2b9b-226">**Create**</span></span> <br/> |
   |<span data-ttu-id="b2b9b-227">**蜂巢**</span><span class="sxs-lookup"><span data-stu-id="b2b9b-227">**Hive**</span></span> <br/> | <span data-ttu-id="b2b9b-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="b2b9b-228">HKEY_CURRENT_USER</span></span> <br/> |
   |<span data-ttu-id="b2b9b-229">**機碼路徑**</span><span class="sxs-lookup"><span data-stu-id="b2b9b-229">**Key Path**</span></span> <br/> |<span data-ttu-id="b2b9b-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="b2b9b-230">Software\Microsoft\Office\Lync</span></span>  <br/> |
   |<span data-ttu-id="b2b9b-231">**Value name**</span><span class="sxs-lookup"><span data-stu-id="b2b9b-231">**Value name**</span></span> <br/> |<span data-ttu-id="b2b9b-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="b2b9b-232">EnableSkypeUI</span></span>  <br/> |
   |<span data-ttu-id="b2b9b-233">**Value type**</span><span class="sxs-lookup"><span data-stu-id="b2b9b-233">**Value type**</span></span> <br/> |<span data-ttu-id="b2b9b-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="b2b9b-234">REG_BINARY</span></span>  <br/> |
   |<span data-ttu-id="b2b9b-235">**值資料**</span><span class="sxs-lookup"><span data-stu-id="b2b9b-235">**Value data**</span></span> <br/> |<span data-ttu-id="b2b9b-236">00000000</span><span class="sxs-lookup"><span data-stu-id="b2b9b-236">00000000</span></span>  <br/> |
   
8. <span data-ttu-id="b2b9b-237">按一下 **[確定]** 以儲存變更，然後關閉 GPO。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-237">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="b2b9b-238">接下來，您必須將您建立的 GPO 連結至您要指派原則的使用者群組，例如 OU。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a><span data-ttu-id="b2b9b-239">若要使用 GPO 指派原則</span><span class="sxs-lookup"><span data-stu-id="b2b9b-239">To use the GPO to assign the policy</span></span>

1. <span data-ttu-id="b2b9b-240">在 [群組原則管理主控台] 中，以滑鼠右鍵按一下您要指派原則的 OU，然後選取 [ **連結到現有的 GPO**]。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="b2b9b-241">在 [ **選取 gpo** ] 對話方塊中，選取您建立的 GPO，然後選取 **[確定**]。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="b2b9b-242">在目標使用者的電腦上，開啟命令提示字元，並輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="b2b9b-242">On the target user's computer, open a command prompt and type the following command:</span></span>
       
```console
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. <span data-ttu-id="b2b9b-243">在命令提示字元處，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="b2b9b-243">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="b2b9b-244">**gpresult/r**</span><span class="sxs-lookup"><span data-stu-id="b2b9b-244">**gpresult /r**</span></span>
    
    <span data-ttu-id="b2b9b-245">您應該會看到 "指派的群組原則物件"，具有您在下方所建立的 GPO 名稱。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-245">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="b2b9b-246">您也可以檢查登錄，以確認 GPO 是否已成功更新使用者電腦上的登錄。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-246">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="b2b9b-247">開啟 [登錄編輯程式]，然後流覽至 **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** 機碼。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-247">Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key.</span></span> <span data-ttu-id="b2b9b-248">如果 GPO 成功更新登錄，您將會看到名為 EnableSkypeUI 的值，其值為0。</span><span class="sxs-lookup"><span data-stu-id="b2b9b-248">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  

