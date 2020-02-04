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
ms.openlocfilehash: 1e1aa407fbb1d7d8a006698d30545165352386b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a><span data-ttu-id="46640-102">透過商務用 Skype 設定用戶端體驗</span><span class="sxs-lookup"><span data-stu-id="46640-102">Configure the client experience with Skype for Business</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46640-103">_**主題上次修改日期：** 2015-09-17_</span><span class="sxs-lookup"><span data-stu-id="46640-103">_**Topic Last Modified:** 2015-09-17_</span></span>

<span data-ttu-id="46640-104">**摘要：** 本主題說明如何針對 Lync Server 2013 環境中的商務用 Skype 用戶端使用者設定用戶端體驗。</span><span class="sxs-lookup"><span data-stu-id="46640-104">**Summary:** This topic describes how to configure the client experience for Skype for Business client users in a Lync Server 2013 environment.</span></span> <span data-ttu-id="46640-105">只有當您在使用2014年12月累積更新（5.0.8308.857）或更新版本的情況下執行 Lync Server 2013 時，才能設定用戶端體驗。</span><span class="sxs-lookup"><span data-stu-id="46640-105">You can configure the client experience only if you are running Lync Server 2013 with the December 2014 Cumulative Update (5.0.8308.857) or later installed.</span></span> <span data-ttu-id="46640-106">如需更新 Lync Server 2013 的相關資訊，請參閱[Lync server 2013 的更新](http://go.microsoft.com/fwlink/p/?linkid=532651)。</span><span class="sxs-lookup"><span data-stu-id="46640-106">For information about updating Lync Server 2013, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532651).</span></span>

<span data-ttu-id="46640-107">商務用 skype 提供以 Skype 消費者產品體驗為基礎的新使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="46640-107">Skype for Business provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="46640-108">除了 Lync 的所有功能之外，商務用 Skype 也會以簡化的控制項和熟悉的圖示來提供新功能。</span><span class="sxs-lookup"><span data-stu-id="46640-108">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="46640-109">如需新用戶端體驗的詳細資訊，請參閱[Lync 現在已開始商務用 Skype--查看新功能](http://go.microsoft.com/fwlink/?linkid=529022)。</span><span class="sxs-lookup"><span data-stu-id="46640-109">For detailed information about the new client experience, see [Lync is now Skype for Business -- see what's new](http://go.microsoft.com/fwlink/?linkid=529022).</span></span>

<span data-ttu-id="46640-110">Lync Server 2013 支援新的商務用 Skype 用戶端體驗，以及 Lync 用戶端體驗。</span><span class="sxs-lookup"><span data-stu-id="46640-110">Lync Server 2013 supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="46640-111">作為系統管理員，您可以為使用者選擇首選的用戶端體驗。</span><span class="sxs-lookup"><span data-stu-id="46640-111">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="46640-112">例如，您可能會想要部署 Lync 用戶端體驗，直到貴組織中的使用者在新的商務用 Skype 體驗中受到全面訓練為止。</span><span class="sxs-lookup"><span data-stu-id="46640-112">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="46640-113">或者，如果您尚未將所有使用者升級到商務用 Skype Server 2015，您可能會希望所有使用者都能使用相同的用戶端體驗，直到全部都升級到新的伺服器為止。</span><span class="sxs-lookup"><span data-stu-id="46640-113">Or, if you have not yet upgraded all users to Skype for Business Server 2015, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="46640-114">如果您的組織已部署商務用 Skype Server 2015 和 Lync Server 2013，則預設的用戶端體驗會依伺服器版本和 UI 設定而有所不同。</span><span class="sxs-lookup"><span data-stu-id="46640-114">If your organization has both Skype for Business Server 2015 and Lync Server 2013 deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="46640-115">當使用者第一次啟動商務用 Skype 時，他們將永遠會看到商務用 Skype 使用者介面，即使您已選取 Lync 使用者介面也一樣。</span><span class="sxs-lookup"><span data-stu-id="46640-115">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync user interface.</span></span> <span data-ttu-id="46640-116">幾分鐘之後，系統會要求使用者切換到 Lync 模式。</span><span class="sxs-lookup"><span data-stu-id="46640-116">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="46640-117">如需詳細資訊，請參閱本主題稍後的<STRONG>第一次啟動用戶端行為</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="46640-117">For more information, see <STRONG>First launch client behavior</STRONG> later in this topic.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="46640-118">Lync 2013 用戶端體驗不是商務用 Skype 2016 用戶端版本的選項。</span><span class="sxs-lookup"><span data-stu-id="46640-118">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="46640-119">在您嘗試將用戶端環境設定為使用 Lync 2013 用戶端之前，請先檢查用戶端版本，以確保它不是以數位16開頭;例如： x.x.x。</span><span class="sxs-lookup"><span data-stu-id="46640-119">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span>



</div>

<div>

## <a name="configure-the-client-experience"></a><span data-ttu-id="46640-120">設定用戶端體驗</span><span class="sxs-lookup"><span data-stu-id="46640-120">Configure the client experience</span></span>

<span data-ttu-id="46640-121">您可以使用**CSClientPolicy** Cmdlet 及 EnableSkypeUI 參數，指定貴組織中的使用者所能看到的用戶端體驗。</span><span class="sxs-lookup"><span data-stu-id="46640-121">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter.</span></span> <span data-ttu-id="46640-122">下列命令會針對貴組織中受全域原則影響的所有使用者，選取商務用 Skype 用戶端體驗（請記住，網站或使用者專用原則會覆寫全域原則）：</span><span class="sxs-lookup"><span data-stu-id="46640-122">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

<span data-ttu-id="46640-123">[下一步] 命令會針對貴組織中的所有使用者選取由全域原則影響的 Lync 用戶端體驗：</span><span class="sxs-lookup"><span data-stu-id="46640-123">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

<span data-ttu-id="46640-124">[下一步] 命令會針對雷德蒙網站中的所有使用者選取商務用 Skype 用戶端體驗：</span><span class="sxs-lookup"><span data-stu-id="46640-124">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

<span data-ttu-id="46640-125">如果您想要針對貴組織內的特定使用者設定用戶端體驗，您可以使用 CsClientPolicy Cmdlet 建立新**的**使用者策略，然後使用**授與 CsClientPolicy** Cmdlet，將原則指派給特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="46640-125">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>

<span data-ttu-id="46640-126">例如，下列命令會建立新的用戶端原則 SalesClientUI，以選取商務用 Skype 用戶端體驗：</span><span class="sxs-lookup"><span data-stu-id="46640-126">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

<span data-ttu-id="46640-127">下一個命令會將原則（SalesClientUI）指派給銷售部門的所有成員：</span><span class="sxs-lookup"><span data-stu-id="46640-127">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="46640-128">第一次啟動用戶端行為</span><span class="sxs-lookup"><span data-stu-id="46640-128">First launch client behaviors</span></span>

<span data-ttu-id="46640-129">根據預設，當使用者第一次啟動商務用 Skype 時，他們將永遠會看到商務用 Skype 的使用者介面，即使您已選取 Lync 用戶端體驗，只要將 EnableSkypeUI 參數的值設定為 $False （如先前所述）。.</span><span class="sxs-lookup"><span data-stu-id="46640-129">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="46640-130">幾分鐘之後，系統會要求使用者切換到 Lync 模式。</span><span class="sxs-lookup"><span data-stu-id="46640-130">After several minutes, users will then be asked to switch to Lync mode.</span></span>

<span data-ttu-id="46640-131">如果您想要在使用者第一次啟動商務用 Skype 用戶端時顯示 Lync 使用者介面，請在用戶端第一次更新之後，按照下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="46640-131">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>

1.  <span data-ttu-id="46640-132">確認您使用的原則`EnableSkypeUI`中的值設定為 $False，如先前所述。</span><span class="sxs-lookup"><span data-stu-id="46640-132">Confirm that the value of `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>

2.  <span data-ttu-id="46640-133">更新使用者電腦上的系統登錄。</span><span class="sxs-lookup"><span data-stu-id="46640-133">Update the system registry on the user's computer.</span></span> <span data-ttu-id="46640-134">您應該在使用者第一次啟動商務用 Skype 用戶端之前執行此動作，而您只能執行此動作一次。</span><span class="sxs-lookup"><span data-stu-id="46640-134">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="46640-135">如需如何建立群組原則物件以更新加入網域的電腦上的登錄的相關資訊，請參閱主題稍後的章節。</span><span class="sxs-lookup"><span data-stu-id="46640-135">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="46640-136">在 [ \*\* \[HKEY\_目前\_的\\使用者\\軟體\\Microsoft\\Office\] Lync**金鑰] 中，建立新的**二進位\*\*值。</span><span class="sxs-lookup"><span data-stu-id="46640-136">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="46640-137">**值名稱**必須是**EnableSkypeUI**，而**值資料**必須設定為**00 00 00 00**。</span><span class="sxs-lookup"><span data-stu-id="46640-137">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="46640-138">此索引鍵看起來應該像以下這樣：</span><span class="sxs-lookup"><span data-stu-id="46640-138">The key should look like the following:</span></span>
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

<span data-ttu-id="46640-139">Lync 使用者介面現在會在使用者第一次啟動商務用 Skype 用戶端時顯示。</span><span class="sxs-lookup"><span data-stu-id="46640-139">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="46640-140">控制歡迎畫面教學課程的顯示</span><span class="sxs-lookup"><span data-stu-id="46640-140">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="46640-141">當使用者開啟商務用 Skype 用戶端時，預設行為是顯示 [歡迎] 畫面，其中包含*大部分人要求的7個快速秘訣*。</span><span class="sxs-lookup"><span data-stu-id="46640-141">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="46640-142">您可以在用戶端電腦上新增下列登錄值，以關閉歡迎畫面的顯示，但仍允許使用者存取教學課程：</span><span class="sxs-lookup"><span data-stu-id="46640-142">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>

<span data-ttu-id="46640-143">在 [ \*\* \[HKEY\_目前\_的\\使用者\\軟體\\Microsoft\\Office\\15.0\] Lync**金鑰] 中，建立新的**DWORD （32位）值\*\*。</span><span class="sxs-lookup"><span data-stu-id="46640-143">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="46640-144">**值名稱**必須是**IsBasicTutorialSeenByUser**，而**值資料**必須設定為**1**。</span><span class="sxs-lookup"><span data-stu-id="46640-144">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>

<span data-ttu-id="46640-145">此索引鍵看起來應該像以下這樣：</span><span class="sxs-lookup"><span data-stu-id="46640-145">The key should look like the following:</span></span>

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="46640-146">關閉用戶端教學課程</span><span class="sxs-lookup"><span data-stu-id="46640-146">Turn off the client tutorial</span></span>

<span data-ttu-id="46640-147">如果您不想讓使用者存取教學課程，您可以使用下列登錄值來關閉用戶端教學課程：</span><span class="sxs-lookup"><span data-stu-id="46640-147">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>

<span data-ttu-id="46640-148">在 [ \*\* \[HKEY\_目前\_的\\使用者\\軟體\\Microsoft\\Office\\15.0\] Lync**金鑰] 中，建立新的**DWORD （32位）值\*\*。</span><span class="sxs-lookup"><span data-stu-id="46640-148">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="46640-149">**值名稱**必須是**TutorialFeatureEnabled**，而**值資料**必須設定為**0**。</span><span class="sxs-lookup"><span data-stu-id="46640-149">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>

    "TutorialFeatureEnabled"=dword:00000000

<span data-ttu-id="46640-150">您可以將**值資料**設定為**1**，將教學課程改回開啟。</span><span class="sxs-lookup"><span data-stu-id="46640-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>

</div>

</div>

<div>

## <a name="default-client-experiences"></a><span data-ttu-id="46640-151">預設用戶端體驗</span><span class="sxs-lookup"><span data-stu-id="46640-151">Default client experiences</span></span>

<span data-ttu-id="46640-152">如果您的組織同時已部署商務用 Skype Server 2015 和 Lync Server，則用戶端體驗會隨著伺服器版本和 Skype UI 設定而有所不同。</span><span class="sxs-lookup"><span data-stu-id="46640-152">If your organization has both Skype for Business Server 2015 and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="46640-153">下表顯示以伺服器版本和 UI 設定為基礎的初始用戶端體驗：</span><span class="sxs-lookup"><span data-stu-id="46640-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="46640-154">伺服器版本</span><span class="sxs-lookup"><span data-stu-id="46640-154">Server version</span></span></p></th>
<th><p><span data-ttu-id="46640-155">EnableSkypeUI 設定</span><span class="sxs-lookup"><span data-stu-id="46640-155">EnableSkypeUI setting</span></span></p></th>
<th><p><span data-ttu-id="46640-156">用戶端體驗</span><span class="sxs-lookup"><span data-stu-id="46640-156">Client experience</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46640-157">商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="46640-157">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="46640-158">設置</span><span class="sxs-lookup"><span data-stu-id="46640-158">Default</span></span></p></td>
<td><p><span data-ttu-id="46640-159">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="46640-159">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46640-160">商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="46640-160">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="46640-161">滿足</span><span class="sxs-lookup"><span data-stu-id="46640-161">True</span></span></p></td>
<td><p><span data-ttu-id="46640-162">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="46640-162">Skype for Business</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46640-163">商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="46640-163">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="46640-164">虛假</span><span class="sxs-lookup"><span data-stu-id="46640-164">False</span></span></p></td>
<td><p><span data-ttu-id="46640-165">使用者要求切換至 Lync 模式（如果您將 UI 設定變更為 $true，使用者就可以在稍後切換到商務用 Skype）</span><span class="sxs-lookup"><span data-stu-id="46640-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46640-166">Lync Server 2010 或 Lync Server 2013 （含正確的修補程式）</span><span class="sxs-lookup"><span data-stu-id="46640-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="46640-167">設置</span><span class="sxs-lookup"><span data-stu-id="46640-167">Default</span></span></p></td>
<td><p><span data-ttu-id="46640-168">使用者要求切換至 Lync 模式（如果您將 UI 設定變更為 $true，使用者就可以在稍後切換到商務用 Skype）</span><span class="sxs-lookup"><span data-stu-id="46640-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46640-169">Lync Server 2010 或 Lync Server 2013 （含正確的修補程式）</span><span class="sxs-lookup"><span data-stu-id="46640-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="46640-170">滿足</span><span class="sxs-lookup"><span data-stu-id="46640-170">True</span></span></p></td>
<td><p><span data-ttu-id="46640-171">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="46640-171">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46640-172">Lync Server 2010 或 Lync Server 2013 （含正確的修補程式）</span><span class="sxs-lookup"><span data-stu-id="46640-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="46640-173">虛假</span><span class="sxs-lookup"><span data-stu-id="46640-173">False</span></span></p></td>
<td><p><span data-ttu-id="46640-174">使用者要求切換至 Lync 模式（如果您將 UI 設定變更為 $true，使用者就可以在稍後切換到商務用 Skype）</span><span class="sxs-lookup"><span data-stu-id="46640-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46640-175">Lync Server 2010 或 Lync Server 2013 （不含補丁程式）</span><span class="sxs-lookup"><span data-stu-id="46640-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="46640-176">設置</span><span class="sxs-lookup"><span data-stu-id="46640-176">Default</span></span></p></td>
<td><p><span data-ttu-id="46640-177">使用者要求切換至 Lync 用戶端體驗（使用者稍後無法切換到商務用 Skype）</span><span class="sxs-lookup"><span data-stu-id="46640-177">User asked to switch to Lync client experience (user cannot switch to Skype for Business later)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="46640-178">下表顯示管理員變更 Skype UI 體驗的初始設定時的用戶端體驗：</span><span class="sxs-lookup"><span data-stu-id="46640-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="46640-179">伺服器版本</span><span class="sxs-lookup"><span data-stu-id="46640-179">Server version</span></span></p></th>
<th><p><span data-ttu-id="46640-180">Skype UI 設定</span><span class="sxs-lookup"><span data-stu-id="46640-180">Skype UI setting</span></span></p></th>
<th><p><span data-ttu-id="46640-181">用戶端 UI = Lync</span><span class="sxs-lookup"><span data-stu-id="46640-181">Client UI = Lync</span></span></p></th>
<th><p><span data-ttu-id="46640-182">用戶端 UI = 商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="46640-182">Client UI = Skype for Business</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46640-183">商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="46640-183">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="46640-184">滿足</span><span class="sxs-lookup"><span data-stu-id="46640-184">True</span></span></p></td>
<td><p><span data-ttu-id="46640-185">使用者要求切換到商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="46640-185">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="46640-186">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="46640-186">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46640-187">商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="46640-187">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="46640-188">虛假</span><span class="sxs-lookup"><span data-stu-id="46640-188">False</span></span></p></td>
<td><p><span data-ttu-id="46640-189">Lync UI</span><span class="sxs-lookup"><span data-stu-id="46640-189">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="46640-190">使用者要求切換至 Lync UI</span><span class="sxs-lookup"><span data-stu-id="46640-190">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46640-191">Lync Server 2010 或 Lync Server 2013 （含正確的修補程式）</span><span class="sxs-lookup"><span data-stu-id="46640-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="46640-192">滿足</span><span class="sxs-lookup"><span data-stu-id="46640-192">True</span></span></p></td>
<td><p><span data-ttu-id="46640-193">使用者要求切換到商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="46640-193">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="46640-194">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="46640-194">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46640-195">Lync Server 2010 或 Lync Server 2013 （含正確的修補程式）</span><span class="sxs-lookup"><span data-stu-id="46640-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="46640-196">虛假</span><span class="sxs-lookup"><span data-stu-id="46640-196">False</span></span></p></td>
<td><p><span data-ttu-id="46640-197">Lync UI</span><span class="sxs-lookup"><span data-stu-id="46640-197">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="46640-198">使用者要求切換至 Lync UI</span><span class="sxs-lookup"><span data-stu-id="46640-198">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46640-199">Lync Server 2010 或 Lync Server 2013 （不含補丁程式）</span><span class="sxs-lookup"><span data-stu-id="46640-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="46640-200">設置</span><span class="sxs-lookup"><span data-stu-id="46640-200">Default</span></span></p></td>
<td><p><span data-ttu-id="46640-201">Lync 模式（無法切換到商務用 Skype）</span><span class="sxs-lookup"><span data-stu-id="46640-201">Lync mode (cannot switch to Skype for Business)</span></span></p></td>
<td><p><span data-ttu-id="46640-202">Lync UI （無法切換到商務用 Skype）</span><span class="sxs-lookup"><span data-stu-id="46640-202">Lync UI (cannot switch to Skype for Business)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="46640-203">管理商務用 Skype 用戶端設定所需的修補程式版本如下：</span><span class="sxs-lookup"><span data-stu-id="46640-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>

  - <span data-ttu-id="46640-204">Lync Server 2010-Lync Server 2010 的2015年2月累計更新（4.0.7577.710）。</span><span class="sxs-lookup"><span data-stu-id="46640-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="46640-205">如需詳細資訊，請參閱[Lync Server 2010 更新](http://go.microsoft.com/fwlink/p/?linkid=532771)</span><span class="sxs-lookup"><span data-stu-id="46640-205">For information, see [Updates for Lync Server 2010](http://go.microsoft.com/fwlink/p/?linkid=532771)</span></span>

  - <span data-ttu-id="46640-206">Lync Server 2013-Lync Server 2013 的2014年12月累計更新（5.0.8308.857）。</span><span class="sxs-lookup"><span data-stu-id="46640-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="46640-207">如需詳細資訊，請參閱[Lync Server 2013 更新](http://go.microsoft.com/fwlink/p/?linkid=532772)。</span><span class="sxs-lookup"><span data-stu-id="46640-207">For information, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532772).</span></span>

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="46640-208">建立群組原則物件來修改加入網域的電腦上的登錄</span><span class="sxs-lookup"><span data-stu-id="46640-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="46640-209">在使用者第一次啟動商務用 Skype 用戶端時，若要顯示 Lync 用戶端體驗的登錄更新，則必須只進行一次。</span><span class="sxs-lookup"><span data-stu-id="46640-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once.</span></span> <span data-ttu-id="46640-210">如果您使用群組原則物件（GPO）來更新註冊表，您需要定義物件來建立新的值，而不是更新值資料。</span><span class="sxs-lookup"><span data-stu-id="46640-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="46640-211">當套用 GPO 時，如果新值不存在，GPO 將會建立它，並將值資料設定為0。</span><span class="sxs-lookup"><span data-stu-id="46640-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>

<span data-ttu-id="46640-212">下列程式說明如何修改註冊表，以便在使用者第一次啟動商務用 Skype 時顯示 Lync 用戶端體驗。</span><span class="sxs-lookup"><span data-stu-id="46640-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business.</span></span> <span data-ttu-id="46640-213">您也可以使用此程式來更新註冊表，如前文所述，停用歡迎畫面教學課程。</span><span class="sxs-lookup"><span data-stu-id="46640-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>

<span data-ttu-id="46640-214">**建立 GPO**</span><span class="sxs-lookup"><span data-stu-id="46640-214">**To create the GPO**</span></span>

1.  <span data-ttu-id="46640-215">啟動**群組原則管理主控台**。</span><span class="sxs-lookup"><span data-stu-id="46640-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="46640-216">如需如何使用群組原則管理主控台的相關資訊，請參閱[群群組原則管理主控台](http://go.microsoft.com/fwlink/?linkid=532759)。</span><span class="sxs-lookup"><span data-stu-id="46640-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](http://go.microsoft.com/fwlink/?linkid=532759).</span></span>

2.  <span data-ttu-id="46640-217">以滑鼠右鍵按一下 [**群群組原則物件**] 節點，然後在功能表上選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="46640-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>

3.  <span data-ttu-id="46640-218">在 [**新增 gpo** ] 對話方塊中，輸入 GPO 的名稱，例如 [ **MakeLyncDefaultUI**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="46640-218">In the **New GPO** dialog, enter a name for the GPO, for example, **MakeLyncDefaultUI**, and then click **OK**.</span></span>

4.  <span data-ttu-id="46640-219">以滑鼠右鍵按一下您剛建立的新 GPO，然後從功能表中選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="46640-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>

5.  <span data-ttu-id="46640-220">在 [**群組原則管理編輯器**] 中，展開 [**使用者**設定]，展開 [**喜好**設定]，展開 [ **Windows 設定**]，然後**選取 [登錄**] 節點。</span><span class="sxs-lookup"><span data-stu-id="46640-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>

6.  <span data-ttu-id="46640-221">以滑鼠右鍵**按一下 [登錄**] 節點，然後選取 [**新增** \> **註冊專案**]。</span><span class="sxs-lookup"><span data-stu-id="46640-221">Right-click on the **Registry** node, and then select **New** \> **Registry Item**.</span></span>

7.  <span data-ttu-id="46640-222">在 [**新增登錄屬性**] 對話方塊中，更新下列專案：</span><span class="sxs-lookup"><span data-stu-id="46640-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="46640-223">域</span><span class="sxs-lookup"><span data-stu-id="46640-223">Field</span></span></th>
    <th><span data-ttu-id="46640-224">要選取或輸入的值</span><span class="sxs-lookup"><span data-stu-id="46640-224">Value to select or enter</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="46640-225"><strong>動作</strong></span><span class="sxs-lookup"><span data-stu-id="46640-225"><strong>Action</strong></span></span></p></td>
    <td><p><span data-ttu-id="46640-226"><strong>建立</strong></span><span class="sxs-lookup"><span data-stu-id="46640-226"><strong>Create</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="46640-227"><strong>一兩</strong></span><span class="sxs-lookup"><span data-stu-id="46640-227"><strong>Hive</strong></span></span></p></td>
    <td><p><span data-ttu-id="46640-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="46640-228">HKEY_CURRENT_USER</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="46640-229"><strong>索引鍵路徑</strong></span><span class="sxs-lookup"><span data-stu-id="46640-229"><strong>Key Path</strong></span></span></p></td>
    <td><p><span data-ttu-id="46640-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="46640-230">Software\Microsoft\Office\Lync</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="46640-231"><strong>值名稱</strong></span><span class="sxs-lookup"><span data-stu-id="46640-231"><strong>Value name</strong></span></span></p></td>
    <td><p><span data-ttu-id="46640-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="46640-232">EnableSkypeUI</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="46640-233"><strong>數值型別</strong></span><span class="sxs-lookup"><span data-stu-id="46640-233"><strong>Value type</strong></span></span></p></td>
    <td><p><span data-ttu-id="46640-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="46640-234">REG_BINARY</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="46640-235"><strong>值資料</strong></span><span class="sxs-lookup"><span data-stu-id="46640-235"><strong>Value data</strong></span></span></p></td>
    <td><p><span data-ttu-id="46640-236">00000000</span><span class="sxs-lookup"><span data-stu-id="46640-236">00000000</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="46640-237">按一下 **[確定]** 儲存變更，然後關閉該 GPO。</span><span class="sxs-lookup"><span data-stu-id="46640-237">Click **OK** to save your changes, and then close the GPO.</span></span>

<span data-ttu-id="46640-238">接著，您必須將您所建立的 GPO 連結至您要指派原則的使用者群組（例如 OU）。</span><span class="sxs-lookup"><span data-stu-id="46640-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>

<span data-ttu-id="46640-239">**使用 GPO 指派原則**</span><span class="sxs-lookup"><span data-stu-id="46640-239">**To use the GPO to assign the policy**</span></span>

1.  <span data-ttu-id="46640-240">在 [群組原則管理主控台] 中，以滑鼠右鍵按一下您要指派原則的 OU，然後選取 [**連結到現有的 GPO**]。</span><span class="sxs-lookup"><span data-stu-id="46640-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>

2.  <span data-ttu-id="46640-241">在 [**選取 gpo** ] 對話方塊中，選取您所建立的 GPO，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="46640-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>

3.  <span data-ttu-id="46640-242">在目標使用者的電腦上，開啟命令提示字元，然後輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="46640-242">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="46640-243">**gpupdate/target： user**</span><span class="sxs-lookup"><span data-stu-id="46640-243">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="46640-244">訊息「正在更新原則 ...」會在應用 GPO 時顯示。</span><span class="sxs-lookup"><span data-stu-id="46640-244">The message "Updating policy..." is displayed while the GPO is applied.</span></span> <span data-ttu-id="46640-245">完成後，就會顯示「使用者原則更新已成功完成」訊息。</span><span class="sxs-lookup"><span data-stu-id="46640-245">When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>

4.  <span data-ttu-id="46640-246">在命令提示字元中，輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="46640-246">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="46640-247">**gpresult/r**</span><span class="sxs-lookup"><span data-stu-id="46640-247">**gpresult /r**</span></span>
    
    <span data-ttu-id="46640-248">您應該會看到「指派的群群組原則物件」與您所建立之 GPO 的名稱，如下所示。</span><span class="sxs-lookup"><span data-stu-id="46640-248">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>

<span data-ttu-id="46640-249">您也可以檢查登錄，以驗證 GPO 是否已在使用者的電腦上成功更新登錄。</span><span class="sxs-lookup"><span data-stu-id="46640-249">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="46640-250">開啟 [登錄編輯程式]，然後流覽至\*\* \[ \_HKEY\\[\\目前\\\_的\\使用者\]軟體 Microsoft Office Lync\*\*金鑰]。</span><span class="sxs-lookup"><span data-stu-id="46640-250">Open Registry Editor and navigate to the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key.</span></span> <span data-ttu-id="46640-251">如果 GPO 成功更新了註冊表，您會看到一個名為 EnableSkypeUI 的值，其值為0。</span><span class="sxs-lookup"><span data-stu-id="46640-251">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

