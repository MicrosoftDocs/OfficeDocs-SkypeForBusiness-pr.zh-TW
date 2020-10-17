---
title: 在 Lync Server 2013 中設定商務用 Skype 用戶端
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20980f0f0b6697eada6c237aa8d2297b0fd227d9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503300"
---
# <a name="configure-the-client-experience-with-skype-for-business"></a><span data-ttu-id="31fed-102">使用商務用 Skype 設定用戶端經驗</span><span class="sxs-lookup"><span data-stu-id="31fed-102">Configure the client experience with Skype for Business</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31fed-103">_**主題上次修改日期：** 2015-09-17_</span><span class="sxs-lookup"><span data-stu-id="31fed-103">_**Topic Last Modified:** 2015-09-17_</span></span>

<span data-ttu-id="31fed-104">**摘要：** 本主題說明如何在 Lync Server 2013 環境中為商務用 Skype 用戶端使用者設定用戶端經驗。</span><span class="sxs-lookup"><span data-stu-id="31fed-104">**Summary:** This topic describes how to configure the client experience for Skype for Business client users in a Lync Server 2013 environment.</span></span> <span data-ttu-id="31fed-105">您可以設定用戶端體驗，只有在您執行 Lync Server 2013 時已安裝12月2014累積更新 (5.0.8308.857) 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="31fed-105">You can configure the client experience only if you are running Lync Server 2013 with the December 2014 Cumulative Update (5.0.8308.857) or later installed.</span></span> <span data-ttu-id="31fed-106">如需更新 Lync Server 2013 的詳細資訊，請參閱 [Lync server 2013 的更新](https://go.microsoft.com/fwlink/p/?linkid=532651)。</span><span class="sxs-lookup"><span data-stu-id="31fed-106">For information about updating Lync Server 2013, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532651).</span></span>

<span data-ttu-id="31fed-107">商務用 skype 提供以 Skype 消費者產品經驗為基礎的新使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="31fed-107">Skype for Business provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="31fed-108">除了 Lync 的所有功能之外，商務用 Skype 也會透過簡化的控制項及熟悉的圖示來提供新功能。</span><span class="sxs-lookup"><span data-stu-id="31fed-108">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="31fed-109">如需有關新用戶端體驗的詳細資訊，請參閱 [Lync 現在是商務用 Skype--查看](https://go.microsoft.com/fwlink/?linkid=529022)最近更新。</span><span class="sxs-lookup"><span data-stu-id="31fed-109">For detailed information about the new client experience, see [Lync is now Skype for Business -- see what's new](https://go.microsoft.com/fwlink/?linkid=529022).</span></span>

<span data-ttu-id="31fed-110">Lync Server 2013 支援新的商務用 Skype 用戶端體驗和 Lync 用戶端經驗。</span><span class="sxs-lookup"><span data-stu-id="31fed-110">Lync Server 2013 supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="31fed-111">身為管理員，您可以為使用者選擇喜歡的用戶端體驗。</span><span class="sxs-lookup"><span data-stu-id="31fed-111">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="31fed-112">例如，您可能想要部署 Lync 用戶端體驗，直到貴組織中的使用者已完全訓練新的商務用 Skype 體驗。</span><span class="sxs-lookup"><span data-stu-id="31fed-112">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="31fed-113">或者，如果您尚未將所有使用者升級至商務用 Skype Server 2015，您可能想要在所有使用者都升級至新伺服器之前，都有相同的用戶端經驗。</span><span class="sxs-lookup"><span data-stu-id="31fed-113">Or, if you have not yet upgraded all users to Skype for Business Server 2015, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="31fed-114">如果您的組織已部署商務用 Skype Server 2015 和 Lync Server 2013，則預設用戶端體驗會因伺服器版本和 UI 設定而異。</span><span class="sxs-lookup"><span data-stu-id="31fed-114">If your organization has both Skype for Business Server 2015 and Lync Server 2013 deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="31fed-115">當使用者第一次啟動商務用 Skype 時，他們會永遠看到商務用 Skype 使用者介面--即使您已選取 Lync 使用者介面也是一樣。</span><span class="sxs-lookup"><span data-stu-id="31fed-115">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync user interface.</span></span> <span data-ttu-id="31fed-116">幾分鐘後，系統會要求使用者切換至 Lync 模式。</span><span class="sxs-lookup"><span data-stu-id="31fed-116">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="31fed-117">如需詳細資訊，請參閱本主題稍後的 <STRONG>第一次啟動用戶端行為</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="31fed-117">For more information, see <STRONG>First launch client behavior</STRONG> later in this topic.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="31fed-118">Lync 2013 用戶端體驗不是商務用 Skype 2016 用戶端版本的選項。</span><span class="sxs-lookup"><span data-stu-id="31fed-118">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="31fed-119">在您嘗試設定用戶端環境以使用 Lync 2013 用戶端之前，請檢查用戶端版本，以確保其不是以數位16開頭;例如： x.x.x。</span><span class="sxs-lookup"><span data-stu-id="31fed-119">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span>



</div>

<div>

## <a name="configure-the-client-experience"></a><span data-ttu-id="31fed-120">設定用戶端體驗</span><span class="sxs-lookup"><span data-stu-id="31fed-120">Configure the client experience</span></span>

<span data-ttu-id="31fed-121">您可以使用 **Set-CSClientPolicy** Cmdlet 搭配 EnableSkypeUI 參數，指定組織中的使用者所看到的用戶端經驗。</span><span class="sxs-lookup"><span data-stu-id="31fed-121">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter.</span></span> <span data-ttu-id="31fed-122">下列命令會為組織中受全域原則影響的所有使用者選取商務用 Skype 用戶端體驗 (請記住，網站或使用者特定原則會覆寫全域原則) ：</span><span class="sxs-lookup"><span data-stu-id="31fed-122">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

<span data-ttu-id="31fed-123">下一個命令會為組織中的所有使用者選取受全域原則影響的 Lync 用戶端體驗：</span><span class="sxs-lookup"><span data-stu-id="31fed-123">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

<span data-ttu-id="31fed-124">下一個命令會為 Redmond 網站內的所有使用者選取商務用 Skype 用戶端體驗：</span><span class="sxs-lookup"><span data-stu-id="31fed-124">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

<span data-ttu-id="31fed-125">如果您想要為組織內的特定使用者設定用戶端經驗，您可以使用 **New-CsClientPolicy** Cmdlet 來建立新的使用者原則，然後使用 **Grant-CsClientPolicy** Cmdlet 將原則指派給特定使用者。</span><span class="sxs-lookup"><span data-stu-id="31fed-125">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>

<span data-ttu-id="31fed-126">例如，下列命令會建立新的用戶端原則 SalesClientUI，以選取商務用 Skype 用戶端體驗：</span><span class="sxs-lookup"><span data-stu-id="31fed-126">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

<span data-ttu-id="31fed-127">下一個命令會將原則 SalesClientUI 指派給銷售部門的所有成員：</span><span class="sxs-lookup"><span data-stu-id="31fed-127">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="31fed-128">第一次啟動用戶端行為</span><span class="sxs-lookup"><span data-stu-id="31fed-128">First launch client behaviors</span></span>

<span data-ttu-id="31fed-129">根據預設，當使用者第一次啟動商務用 Skype 時，他們會永遠看到商務用 Skype 使用者介面--即使您已透過將 EnableSkypeUI 參數的值設為 $False，如先前所述，您已選取 Lync 用戶端經驗。</span><span class="sxs-lookup"><span data-stu-id="31fed-129">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="31fed-130">幾分鐘後，系統會要求使用者切換至 Lync 模式。</span><span class="sxs-lookup"><span data-stu-id="31fed-130">After several minutes, users will then be asked to switch to Lync mode.</span></span>

<span data-ttu-id="31fed-131">當使用者第一次啟動商務用 Skype 用戶端時，如果您想要顯示 Lync 使用者介面，請在更新後第一次啟動用戶端之前，先執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="31fed-131">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>

1.  <span data-ttu-id="31fed-132">確認的值 `EnableSkypeUI` 已設定為在您使用的原則中 $False，如先前所述。</span><span class="sxs-lookup"><span data-stu-id="31fed-132">Confirm that the value of `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>

2.  <span data-ttu-id="31fed-133">更新使用者電腦上的系統登錄。</span><span class="sxs-lookup"><span data-stu-id="31fed-133">Update the system registry on the user's computer.</span></span> <span data-ttu-id="31fed-134">您應該在使用者第一次啟動商務用 Skype 用戶端之前執行此作業，而且您應該只執行一次。</span><span class="sxs-lookup"><span data-stu-id="31fed-134">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="31fed-135">如需如何建立群組原則物件以更新加入網域之電腦上之登錄的詳細資訊，請參閱本主題稍後的章節。</span><span class="sxs-lookup"><span data-stu-id="31fed-135">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="31fed-136">在 [ \*\* \[ HKEY \_ 目前的 \_ 使用者 \\ 軟體] \\ Microsoft \\ Office \\ \] Lync**金鑰中，建立新的**二進位\*\*值。</span><span class="sxs-lookup"><span data-stu-id="31fed-136">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="31fed-137">**值名稱**必須是**EnableSkypeUI**，且**數值資料**必須設定為**00 00 00 00**。</span><span class="sxs-lookup"><span data-stu-id="31fed-137">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="31fed-138">索引鍵應該如下所示：</span><span class="sxs-lookup"><span data-stu-id="31fed-138">The key should look like the following:</span></span>
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

<span data-ttu-id="31fed-139">當使用者第一次啟動商務用 Skype 用戶端時，即會顯示 Lync 使用者介面。</span><span class="sxs-lookup"><span data-stu-id="31fed-139">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="31fed-140">控制歡迎使用畫面教學課程的顯示</span><span class="sxs-lookup"><span data-stu-id="31fed-140">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="31fed-141">當使用者開啟商務用 Skype 用戶端時，預設行為是顯示歡迎畫面，其中包含 *大多數人員所要求的7個快速秘訣*。</span><span class="sxs-lookup"><span data-stu-id="31fed-141">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="31fed-142">您可以在用戶端電腦上新增下列登錄值，關閉 [歡迎] 畫面，但仍允許使用者存取教學課程：</span><span class="sxs-lookup"><span data-stu-id="31fed-142">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>

<span data-ttu-id="31fed-143">在 [ \*\* \[ HKEY \_ 目前的 \_ 使用者 \\ 軟體] \\ Microsoft \\ Office \\ 15.0 \\ Lync \] **機碼中，建立新的**DWORD (32 位) 值\*\*。</span><span class="sxs-lookup"><span data-stu-id="31fed-143">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="31fed-144">**值名稱**必須是**IsBasicTutorialSeenByUser**，且**數值資料**必須設定為**1**。</span><span class="sxs-lookup"><span data-stu-id="31fed-144">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>

<span data-ttu-id="31fed-145">索引鍵應該如下所示：</span><span class="sxs-lookup"><span data-stu-id="31fed-145">The key should look like the following:</span></span>

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="31fed-146">關閉用戶端教學課程</span><span class="sxs-lookup"><span data-stu-id="31fed-146">Turn off the client tutorial</span></span>

<span data-ttu-id="31fed-147">如果您不想讓使用者能夠存取教學課程，您可以使用下列登錄值來關閉用戶端教學課程：</span><span class="sxs-lookup"><span data-stu-id="31fed-147">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>

<span data-ttu-id="31fed-148">在 [ \*\* \[ HKEY \_ 目前的 \_ 使用者 \\ 軟體] \\ Microsoft \\ Office \\ 15.0 \\ Lync \] **機碼中，建立新的**DWORD (32 位) 值\*\*。</span><span class="sxs-lookup"><span data-stu-id="31fed-148">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="31fed-149">**值名稱**必須是**TutorialFeatureEnabled**，且**數值資料**必須設定為**0**。</span><span class="sxs-lookup"><span data-stu-id="31fed-149">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>

    "TutorialFeatureEnabled"=dword:00000000

<span data-ttu-id="31fed-150">您可以將 **數值資料** 設為 **1**，以重新開啟教學課程。</span><span class="sxs-lookup"><span data-stu-id="31fed-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>

</div>

</div>

<div>

## <a name="default-client-experiences"></a><span data-ttu-id="31fed-151">預設用戶端體驗</span><span class="sxs-lookup"><span data-stu-id="31fed-151">Default client experiences</span></span>

<span data-ttu-id="31fed-152">如果您的組織同時已部署商務用 Skype Server 2015 和 Lync Server，用戶端經驗會因伺服器版本和 Skype UI 設定而有所不同。</span><span class="sxs-lookup"><span data-stu-id="31fed-152">If your organization has both Skype for Business Server 2015 and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="31fed-153">下表顯示以伺服器版本及 UI 設定為基礎的初始用戶端體驗：</span><span class="sxs-lookup"><span data-stu-id="31fed-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="31fed-154">伺服器版本</span><span class="sxs-lookup"><span data-stu-id="31fed-154">Server version</span></span></p></th>
<th><p><span data-ttu-id="31fed-155">EnableSkypeUI 設定</span><span class="sxs-lookup"><span data-stu-id="31fed-155">EnableSkypeUI setting</span></span></p></th>
<th><p><span data-ttu-id="31fed-156">用戶端經驗</span><span class="sxs-lookup"><span data-stu-id="31fed-156">Client experience</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31fed-157">商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="31fed-157">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="31fed-158">預設</span><span class="sxs-lookup"><span data-stu-id="31fed-158">Default</span></span></p></td>
<td><p><span data-ttu-id="31fed-159">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="31fed-159">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31fed-160">商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="31fed-160">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="31fed-161">是</span><span class="sxs-lookup"><span data-stu-id="31fed-161">True</span></span></p></td>
<td><p><span data-ttu-id="31fed-162">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="31fed-162">Skype for Business</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31fed-163">商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="31fed-163">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="31fed-164">False</span><span class="sxs-lookup"><span data-stu-id="31fed-164">False</span></span></p></td>
<td><p><span data-ttu-id="31fed-165">使用者要求切換至 Lync 模式 (使用者可以在稍後將 UI 設定變更為 $true，以切換至商務用 Skype。) </span><span class="sxs-lookup"><span data-stu-id="31fed-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31fed-166">使用正確修補程式的 lync Server 2010 或 Lync Server 2013 () </span><span class="sxs-lookup"><span data-stu-id="31fed-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="31fed-167">預設</span><span class="sxs-lookup"><span data-stu-id="31fed-167">Default</span></span></p></td>
<td><p><span data-ttu-id="31fed-168">使用者要求切換至 Lync 模式 (使用者可以在稍後將 UI 設定變更為 $true，以切換至商務用 Skype。) </span><span class="sxs-lookup"><span data-stu-id="31fed-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31fed-169">使用正確修補程式的 lync Server 2010 或 Lync Server 2013 () </span><span class="sxs-lookup"><span data-stu-id="31fed-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="31fed-170">是</span><span class="sxs-lookup"><span data-stu-id="31fed-170">True</span></span></p></td>
<td><p><span data-ttu-id="31fed-171">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="31fed-171">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31fed-172">使用正確修補程式的 lync Server 2010 或 Lync Server 2013 () </span><span class="sxs-lookup"><span data-stu-id="31fed-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="31fed-173">False</span><span class="sxs-lookup"><span data-stu-id="31fed-173">False</span></span></p></td>
<td><p><span data-ttu-id="31fed-174">使用者要求切換至 Lync 模式 (使用者可以在稍後將 UI 設定變更為 $true，以切換至商務用 Skype。) </span><span class="sxs-lookup"><span data-stu-id="31fed-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31fed-175">不含修補程式的 lync Server 2010 或 Lync Server 2013 () </span><span class="sxs-lookup"><span data-stu-id="31fed-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="31fed-176">預設</span><span class="sxs-lookup"><span data-stu-id="31fed-176">Default</span></span></p></td>
<td><p><span data-ttu-id="31fed-177">使用者要求切換至 Lync 用戶端體驗 (使用者無法切換至商務用 Skype) </span><span class="sxs-lookup"><span data-stu-id="31fed-177">User asked to switch to Lync client experience (user cannot switch to Skype for Business later)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="31fed-178">下表顯示管理員變更 Skype 使用者介面體驗的初始設定時，用戶端的經驗。</span><span class="sxs-lookup"><span data-stu-id="31fed-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="31fed-179">伺服器版本</span><span class="sxs-lookup"><span data-stu-id="31fed-179">Server version</span></span></p></th>
<th><p><span data-ttu-id="31fed-180">Skype 使用者介面設定</span><span class="sxs-lookup"><span data-stu-id="31fed-180">Skype UI setting</span></span></p></th>
<th><p><span data-ttu-id="31fed-181">用戶端 UI = Lync</span><span class="sxs-lookup"><span data-stu-id="31fed-181">Client UI = Lync</span></span></p></th>
<th><p><span data-ttu-id="31fed-182">用戶端 UI = 商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="31fed-182">Client UI = Skype for Business</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31fed-183">商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="31fed-183">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="31fed-184">是</span><span class="sxs-lookup"><span data-stu-id="31fed-184">True</span></span></p></td>
<td><p><span data-ttu-id="31fed-185">使用者要求切換至商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="31fed-185">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="31fed-186">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="31fed-186">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31fed-187">商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="31fed-187">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="31fed-188">False</span><span class="sxs-lookup"><span data-stu-id="31fed-188">False</span></span></p></td>
<td><p><span data-ttu-id="31fed-189">Lync 使用者介面</span><span class="sxs-lookup"><span data-stu-id="31fed-189">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="31fed-190">使用者要求切換至 Lync UI</span><span class="sxs-lookup"><span data-stu-id="31fed-190">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31fed-191">使用正確修補程式的 lync Server 2010 或 Lync Server 2013 () </span><span class="sxs-lookup"><span data-stu-id="31fed-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="31fed-192">是</span><span class="sxs-lookup"><span data-stu-id="31fed-192">True</span></span></p></td>
<td><p><span data-ttu-id="31fed-193">使用者要求切換至商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="31fed-193">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="31fed-194">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="31fed-194">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31fed-195">使用正確修補程式的 lync Server 2010 或 Lync Server 2013 () </span><span class="sxs-lookup"><span data-stu-id="31fed-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="31fed-196">False</span><span class="sxs-lookup"><span data-stu-id="31fed-196">False</span></span></p></td>
<td><p><span data-ttu-id="31fed-197">Lync 使用者介面</span><span class="sxs-lookup"><span data-stu-id="31fed-197">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="31fed-198">使用者要求切換至 Lync UI</span><span class="sxs-lookup"><span data-stu-id="31fed-198">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31fed-199">不含修補程式的 lync Server 2010 或 Lync Server 2013 () </span><span class="sxs-lookup"><span data-stu-id="31fed-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="31fed-200">預設</span><span class="sxs-lookup"><span data-stu-id="31fed-200">Default</span></span></p></td>
<td><p><span data-ttu-id="31fed-201">Lync 模式 (無法切換至商務用 Skype) </span><span class="sxs-lookup"><span data-stu-id="31fed-201">Lync mode (cannot switch to Skype for Business)</span></span></p></td>
<td><p><span data-ttu-id="31fed-202">Lync UI (無法切換至商務用 Skype) </span><span class="sxs-lookup"><span data-stu-id="31fed-202">Lync UI (cannot switch to Skype for Business)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="31fed-203">管理商務用 Skype 用戶端設定所需的修補程式版本如下：</span><span class="sxs-lookup"><span data-stu-id="31fed-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>

  - <span data-ttu-id="31fed-204">Lync Server 2010-2 月2015累積更新 (4.0.7577.710) 的 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="31fed-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="31fed-205">如需詳細資訊，請參閱 [Lync Server 2010 的更新](https://go.microsoft.com/fwlink/p/?linkid=532771)</span><span class="sxs-lookup"><span data-stu-id="31fed-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkid=532771)</span></span>

  - <span data-ttu-id="31fed-206">Lync Server 2013-Lync Server 2013 的2014累計更新 (5.0.8308.857) 。</span><span class="sxs-lookup"><span data-stu-id="31fed-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="31fed-207">如需詳細資訊，請參閱 [Lync Server 2013 的更新](https://go.microsoft.com/fwlink/p/?linkid=532772)。</span><span class="sxs-lookup"><span data-stu-id="31fed-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532772).</span></span>

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="31fed-208">建立群組原則物件以在加入網域的電腦上修改登錄</span><span class="sxs-lookup"><span data-stu-id="31fed-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="31fed-209">當使用者第一次啟動商務用 Skype 用戶端時，要顯示 Lync 用戶端經驗的登錄更新，應只執行一次。</span><span class="sxs-lookup"><span data-stu-id="31fed-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once.</span></span> <span data-ttu-id="31fed-210">如果您使用群組原則物件 (GPO) 來更新登錄，您必須定義物件來建立新的值，而不是更新值資料。</span><span class="sxs-lookup"><span data-stu-id="31fed-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="31fed-211">套用 GPO 時，如果新值不存在，GPO 將會建立它，並將數值資料設定為0。</span><span class="sxs-lookup"><span data-stu-id="31fed-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>

<span data-ttu-id="31fed-212">下列程式說明如何修改登錄，讓使用者第一次啟動商務用 Skype 時，才會顯示 Lync 用戶端經驗。</span><span class="sxs-lookup"><span data-stu-id="31fed-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business.</span></span> <span data-ttu-id="31fed-213">您也可以使用此程式來更新登錄，以停用先前所述的歡迎畫面教學課程。</span><span class="sxs-lookup"><span data-stu-id="31fed-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>

<span data-ttu-id="31fed-214">**建立 GPO**</span><span class="sxs-lookup"><span data-stu-id="31fed-214">**To create the GPO**</span></span>

1.  <span data-ttu-id="31fed-215">啟動 [ **群組原則管理主控台**]。</span><span class="sxs-lookup"><span data-stu-id="31fed-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="31fed-216">如需如何使用「群組原則管理主控台」的詳細資訊，請參閱 [群組原則管理主控台](https://go.microsoft.com/fwlink/?linkid=532759)。</span><span class="sxs-lookup"><span data-stu-id="31fed-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?linkid=532759).</span></span>

2.  <span data-ttu-id="31fed-217">在 [ **群組原則物件** ] 節點上按一下滑鼠右鍵，然後在功能表上選取 [ **新增** ]。</span><span class="sxs-lookup"><span data-stu-id="31fed-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>

3.  <span data-ttu-id="31fed-218">在 [ **新增 gpo** ] 對話方塊中，輸入 GPO 的名稱，例如 [ **MakeLyncDefaultUI**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="31fed-218">In the **New GPO** dialog, enter a name for the GPO, for example, **MakeLyncDefaultUI**, and then click **OK**.</span></span>

4.  <span data-ttu-id="31fed-219">在您剛才建立的新 GPO 上按一下滑鼠右鍵，然後從功能表中選取 [ **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="31fed-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>

5.  <span data-ttu-id="31fed-220">在 [**群組原則管理編輯器**] 中，展開 [**使用者**設定]，展開 [**喜好**設定]，展開 [ **Windows 設定**]，然後選取**登錄節點。**</span><span class="sxs-lookup"><span data-stu-id="31fed-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>

6.  <span data-ttu-id="31fed-221">**在 [登錄**] 節點上按一下滑鼠右鍵，然後選取 [**新增**登錄 \> **專案**]。</span><span class="sxs-lookup"><span data-stu-id="31fed-221">Right-click on the **Registry** node, and then select **New** \> **Registry Item**.</span></span>

7.  <span data-ttu-id="31fed-222">在 [ **新增註冊表屬性** ] 對話方塊中，更新下列專案：</span><span class="sxs-lookup"><span data-stu-id="31fed-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="31fed-223">欄位</span><span class="sxs-lookup"><span data-stu-id="31fed-223">Field</span></span></th>
    <th><span data-ttu-id="31fed-224">要選取或輸入的值</span><span class="sxs-lookup"><span data-stu-id="31fed-224">Value to select or enter</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="31fed-225"><strong>Action</strong></span><span class="sxs-lookup"><span data-stu-id="31fed-225"><strong>Action</strong></span></span></p></td>
    <td><p><span data-ttu-id="31fed-226"><strong>Create</strong></span><span class="sxs-lookup"><span data-stu-id="31fed-226"><strong>Create</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="31fed-227"><strong>蜂巢</strong></span><span class="sxs-lookup"><span data-stu-id="31fed-227"><strong>Hive</strong></span></span></p></td>
    <td><p><span data-ttu-id="31fed-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="31fed-228">HKEY_CURRENT_USER</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="31fed-229"><strong>機碼路徑</strong></span><span class="sxs-lookup"><span data-stu-id="31fed-229"><strong>Key Path</strong></span></span></p></td>
    <td><p><span data-ttu-id="31fed-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="31fed-230">Software\Microsoft\Office\Lync</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="31fed-231"><strong>Value name</strong></span><span class="sxs-lookup"><span data-stu-id="31fed-231"><strong>Value name</strong></span></span></p></td>
    <td><p><span data-ttu-id="31fed-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="31fed-232">EnableSkypeUI</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="31fed-233"><strong>Value type</strong></span><span class="sxs-lookup"><span data-stu-id="31fed-233"><strong>Value type</strong></span></span></p></td>
    <td><p><span data-ttu-id="31fed-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="31fed-234">REG_BINARY</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="31fed-235"><strong>值資料</strong></span><span class="sxs-lookup"><span data-stu-id="31fed-235"><strong>Value data</strong></span></span></p></td>
    <td><p><span data-ttu-id="31fed-236">00000000</span><span class="sxs-lookup"><span data-stu-id="31fed-236">00000000</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="31fed-237">按一下 **[確定]** 以儲存變更，然後關閉 GPO。</span><span class="sxs-lookup"><span data-stu-id="31fed-237">Click **OK** to save your changes, and then close the GPO.</span></span>

<span data-ttu-id="31fed-238">接下來，您必須將您建立的 GPO 連結至您要指派原則的使用者群組，例如 OU。</span><span class="sxs-lookup"><span data-stu-id="31fed-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>

<span data-ttu-id="31fed-239">**若要使用 GPO 指派原則**</span><span class="sxs-lookup"><span data-stu-id="31fed-239">**To use the GPO to assign the policy**</span></span>

1.  <span data-ttu-id="31fed-240">在 [群組原則管理主控台] 中，以滑鼠右鍵按一下您要指派原則的 OU，然後選取 [ **連結到現有的 GPO**]。</span><span class="sxs-lookup"><span data-stu-id="31fed-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>

2.  <span data-ttu-id="31fed-241">在 [ **選取 gpo** ] 對話方塊中，選取您建立的 GPO，然後選取 **[確定**]。</span><span class="sxs-lookup"><span data-stu-id="31fed-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>

3.  <span data-ttu-id="31fed-242">在目標使用者的電腦上，開啟命令提示字元，並輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="31fed-242">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="31fed-243">**gpupdate/target： user**</span><span class="sxs-lookup"><span data-stu-id="31fed-243">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="31fed-244">郵件「更新原則 ...」會在應用 GPO 時顯示。</span><span class="sxs-lookup"><span data-stu-id="31fed-244">The message "Updating policy..." is displayed while the GPO is applied.</span></span> <span data-ttu-id="31fed-245">完成後，就會顯示「已成功完成使用者原則更新」郵件。</span><span class="sxs-lookup"><span data-stu-id="31fed-245">When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>

4.  <span data-ttu-id="31fed-246">在命令提示字元處，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="31fed-246">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="31fed-247">**gpresult/r**</span><span class="sxs-lookup"><span data-stu-id="31fed-247">**gpresult /r**</span></span>
    
    <span data-ttu-id="31fed-248">您應該會看到 "指派的群組原則物件"，具有您在下方所建立的 GPO 名稱。</span><span class="sxs-lookup"><span data-stu-id="31fed-248">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>

<span data-ttu-id="31fed-249">您也可以檢查登錄，以確認 GPO 是否已成功更新使用者電腦上的登錄。</span><span class="sxs-lookup"><span data-stu-id="31fed-249">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="31fed-250">開啟登錄編輯程式，並流覽至\*\* \[ HKEY \_ 目前的 \_ 使用者 \\ 軟體 \\ Microsoft \\ Office \\ Lync \] \*\*金鑰。</span><span class="sxs-lookup"><span data-stu-id="31fed-250">Open Registry Editor and navigate to the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key.</span></span> <span data-ttu-id="31fed-251">如果 GPO 成功更新登錄，您將會看到名為 EnableSkypeUI 的值，其值為0。</span><span class="sxs-lookup"><span data-stu-id="31fed-251">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

