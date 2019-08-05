---
title: 在商務用 Skype Server 中建立會議配置設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: '摘要: 瞭解如何在商務用 Skype Server 中建立會議配置設定。'
ms.openlocfilehash: 3d4f986b850b309d50967da9126b8b4eea08a166
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192535"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="e00d3-103">在商務用 Skype Server 中建立會議配置設定</span><span class="sxs-lookup"><span data-stu-id="e00d3-103">Create meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="e00d3-104">**摘要:** 瞭解如何在商務用 Skype Server 中建立會議配置設定。</span><span class="sxs-lookup"><span data-stu-id="e00d3-104">**Summary:** Learn how to create meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="e00d3-105">您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server 管理命令介面來建立會議設定設定。</span><span class="sxs-lookup"><span data-stu-id="e00d3-105">You can create meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="e00d3-106">使用商務用 Skype Server [控制台] 建立會議配置設定</span><span class="sxs-lookup"><span data-stu-id="e00d3-106">Create meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e00d3-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e00d3-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="e00d3-108">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="e00d3-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="e00d3-109">在左側導覽列中, 按一下 [**會議**], 然後按一下 [**會議配置**]。</span><span class="sxs-lookup"><span data-stu-id="e00d3-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="e00d3-110">在 [**會議**設定] 頁面上, 按一下 [**新增**], 然後執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="e00d3-110">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
    - <span data-ttu-id="e00d3-111">若要建立網站層級原則, 按一下 [**網站**設定]。</span><span class="sxs-lookup"><span data-stu-id="e00d3-111">To create a site-level policy, click **Site configuration**.</span></span> <span data-ttu-id="e00d3-112">在 [**選取網站**搜尋] 欄位中, 輸入您要定義會議加入設定的網站名稱全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="e00d3-112">In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings.</span></span> <span data-ttu-id="e00d3-113">在產生的網站清單中, 按一下您想要的網站, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e00d3-113">In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
    - <span data-ttu-id="e00d3-114">若要建立池層級原則, 請按一下 [**池**設定]。</span><span class="sxs-lookup"><span data-stu-id="e00d3-114">To create a pool-level policy, click **Pool configuration**.</span></span> <span data-ttu-id="e00d3-115">在 [**選取服務**搜尋] 欄位中, 輸入您要定義會議加入設定的全部或部分的 [池服務] 名稱。</span><span class="sxs-lookup"><span data-stu-id="e00d3-115">In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings.</span></span> <span data-ttu-id="e00d3-116">在產生的服務清單中, 按一下您想要的 [池], 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e00d3-116">In the resulting list of services, click the pool you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="e00d3-117">若要傳送透過大廳從公用交換電話網絡 (PSTN) 撥入的參與者, 請清除**PSTN 呼叫者略過大廳**核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e00d3-117">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box.</span></span> <span data-ttu-id="e00d3-118">根據預設, 從 PSTN 撥入的參與者會直接進入會議。</span><span class="sxs-lookup"><span data-stu-id="e00d3-118">By default, participants dialing in from the PSTN go directly to the meeting.</span></span>
    
6. <span data-ttu-id="e00d3-119">若要設定在會議中可成為簡報者的人員, 請在 [**指定為簡報者**] 中, 執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="e00d3-119">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
   - <span data-ttu-id="e00d3-120">若要不允許召集人以外的任何人成為簡報者, 請按一下 [**無**]。</span><span class="sxs-lookup"><span data-stu-id="e00d3-120">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
   - <span data-ttu-id="e00d3-121">若要只允許作為您組織成員的參與者成為簡報者, 請按一下 [**公司**]。</span><span class="sxs-lookup"><span data-stu-id="e00d3-121">To allow only participants who are members of your organization to be a presenter, click **Company**.</span></span> <span data-ttu-id="e00d3-122">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="e00d3-122">This is the default setting.</span></span>
    
   - <span data-ttu-id="e00d3-123">若要讓任何參與者成為簡報者, 請按一下 [**所有人**]。</span><span class="sxs-lookup"><span data-stu-id="e00d3-123">To allow any participants to be a presenter, click **Everyone**.</span></span>
    
7. <span data-ttu-id="e00d3-124">若要讓召集人在排程會議時選取會議類型, 請清除 [**預設為指派的會議類型**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e00d3-124">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box.</span></span> <span data-ttu-id="e00d3-125">根據預設, 會自動指派會議類型。</span><span class="sxs-lookup"><span data-stu-id="e00d3-125">By default, the conference type is automatically assigned.</span></span>
    
8. <span data-ttu-id="e00d3-126">若要防止匿名 (未經授權) 使用者自動獲准, 請清除 [**預設承認匿名使用者**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e00d3-126">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box.</span></span> <span data-ttu-id="e00d3-127">根據預設, 匿名使用者會自動獲准參加會議。</span><span class="sxs-lookup"><span data-stu-id="e00d3-127">By default, anonymous users are automatically admitted to meetings.</span></span>
    
9. <span data-ttu-id="e00d3-128">若要自訂傳送給參與者的會議邀請, 請執行下列動作。</span><span class="sxs-lookup"><span data-stu-id="e00d3-128">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="e00d3-129">請注意, Url 和自訂頁尾文字的最大長度為1KB。</span><span class="sxs-lookup"><span data-stu-id="e00d3-129">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="e00d3-130">除了說明**URL**之外, 如果您沒有指定自訂專案的值, 就不會包含在會議中。</span><span class="sxs-lookup"><span data-stu-id="e00d3-130">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="e00d3-131">如果您不包含自訂的說明 URL, 則會在邀請中顯示商務用 Skype 的預設說明 URL。</span><span class="sxs-lookup"><span data-stu-id="e00d3-131">If you do not include a custom help URL, the default help URL for Skype for Business will be displayed in the invite.</span></span> 
    
   - <span data-ttu-id="e00d3-132">若要自訂會議邀請中出現的標誌, 請在 [**標誌 URL**] 中輸入標誌的位置。</span><span class="sxs-lookup"><span data-stu-id="e00d3-132">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span> <span data-ttu-id="e00d3-133">標誌必須是一個大小為 188 x 30 圖元的 GIF 或 JPG 影像。</span><span class="sxs-lookup"><span data-stu-id="e00d3-133">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span> 
    
   - <span data-ttu-id="e00d3-134">若要自訂會議邀請中出現的解說文字, 請在 [說明] **URL**中輸入解說文字的位置。</span><span class="sxs-lookup"><span data-stu-id="e00d3-134">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
   - <span data-ttu-id="e00d3-135">若要自訂會議邀請中出現的法律文字, 請在 [**合法文字 URL**] 中輸入法律文字的位置。</span><span class="sxs-lookup"><span data-stu-id="e00d3-135">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
   - <span data-ttu-id="e00d3-136">若要自訂會議邀請中顯示的頁尾文字, 請在 [**自訂頁尾文字**] 中輸入文字。</span><span class="sxs-lookup"><span data-stu-id="e00d3-136">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>
    
10. <span data-ttu-id="e00d3-137">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e00d3-137">Click **Commit**.</span></span>
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="e00d3-138">使用商務用 Skype Server Management Shell 建立會議設定設定</span><span class="sxs-lookup"><span data-stu-id="e00d3-138">Create meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="e00d3-139">若要建立會議設定, 請使用**CsMeetingConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e00d3-139">To create meeting configuration settings, use the **New-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="e00d3-140">下列命令會針對雷德蒙的網站建立一組新的會議配置設定:</span><span class="sxs-lookup"><span data-stu-id="e00d3-140">The following command creates a new set of meeting configuration settings for the Redmond site:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="e00d3-141">因為在上述命令中沒有指定任何參數 (除了是強制身分識別參數), 所以新的會議設定會針對其所有屬性使用預設值。</span><span class="sxs-lookup"><span data-stu-id="e00d3-141">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>
  
<span data-ttu-id="e00d3-142">若要建立使用不同屬性值的設定, 只要包含適當的參數和參數值即可。</span><span class="sxs-lookup"><span data-stu-id="e00d3-142">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="e00d3-143">例如, 若要建立會議設定的集合, 根據預設, 承認所有人都可以以演講者身分參與會議, 請使用如下所示的命令:</span><span class="sxs-lookup"><span data-stu-id="e00d3-143">For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="e00d3-144">您可以透過包含多個參數來設定多個屬性值。</span><span class="sxs-lookup"><span data-stu-id="e00d3-144">Multiple property values can be set by including multiple parameters.</span></span> <span data-ttu-id="e00d3-145">例如, 下列命令會允許所有人作為簡報者加入會議, 同時也會強制 PSTN 使用者在大廳等候, 直到正式獲准取得會議為止:</span><span class="sxs-lookup"><span data-stu-id="e00d3-145">For example, the following command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

<span data-ttu-id="e00d3-146">如需詳細資訊 (包括完整的參數清單), 請參閱[新 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="e00d3-146">For more information, including a complete list of parameters, see [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span></span>
  

