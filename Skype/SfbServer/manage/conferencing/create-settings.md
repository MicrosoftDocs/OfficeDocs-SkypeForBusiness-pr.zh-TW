---
title: 在商務用 Skype Server 中建立會議配置設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 摘要：瞭解如何在商務用 Skype Server 中建立會議配置設定。
ms.openlocfilehash: 862ffc56fd14c446a747a490daa0655e410e01d9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119512"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="04074-103">在商務用 Skype Server 中建立會議配置設定</span><span class="sxs-lookup"><span data-stu-id="04074-103">Create meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="04074-104">**摘要：** 瞭解如何在商務用 Skype Server 中建立會議配置設定。</span><span class="sxs-lookup"><span data-stu-id="04074-104">**Summary:** Learn how to create meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="04074-105">您可以使用商務用 Skype Server 控制台或使用商務用 Skype Server 管理命令介面來建立會議設定設定。</span><span class="sxs-lookup"><span data-stu-id="04074-105">You can create meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="04074-106">使用商務用 Skype Server 控制台建立會議配置設定</span><span class="sxs-lookup"><span data-stu-id="04074-106">Create meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="04074-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="04074-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="04074-108">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="04074-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="04074-109">在左導覽列中，按一下 [ **會議**]，然後按一下 [ **會議** 設定]。</span><span class="sxs-lookup"><span data-stu-id="04074-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="04074-110">在 [ **會議** 設定] 頁面上，按一下 [ **新增**]，然後執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="04074-110">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
    - <span data-ttu-id="04074-111">若要建立網站層級原則，請按一下 [ **網站** 設定]。</span><span class="sxs-lookup"><span data-stu-id="04074-111">To create a site-level policy, click **Site configuration**.</span></span> <span data-ttu-id="04074-112">在 [ **選取網站** ] 搜尋欄位中，輸入您要定義會議加入設定之網站的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="04074-112">In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings.</span></span> <span data-ttu-id="04074-113">在產生的網站清單中，按一下您想要的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="04074-113">In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
    - <span data-ttu-id="04074-114">若要建立集區層級原則，請按一下 [ **集** 區設定]。</span><span class="sxs-lookup"><span data-stu-id="04074-114">To create a pool-level policy, click **Pool configuration**.</span></span> <span data-ttu-id="04074-115">在 [ **選取服務** ] 搜尋欄位中，輸入您要定義會議加入設定之集區服務的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="04074-115">In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings.</span></span> <span data-ttu-id="04074-116">在產生的服務清單中，按一下您想要的集區，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="04074-116">In the resulting list of services, click the pool you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="04074-117">若要透過會議廳從公用交換電話網路 (PSTN) 傳送從公用交換電話網路撥號的參與者，請清除 [ **PSTN 來電者旁路會議廳** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="04074-117">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box.</span></span> <span data-ttu-id="04074-118">根據預設，從 PSTN 撥入的參與者會直接進入會議。</span><span class="sxs-lookup"><span data-stu-id="04074-118">By default, participants dialing in from the PSTN go directly to the meeting.</span></span>
    
6. <span data-ttu-id="04074-119">若要設定在會議中誰可以是簡報者，請在 [ **指定為簡報者**] 中，執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="04074-119">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
   - <span data-ttu-id="04074-120">若不允許召集人以外的任何人員成為簡報者，請按一下 [ **無**]。</span><span class="sxs-lookup"><span data-stu-id="04074-120">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
   - <span data-ttu-id="04074-121">若只要允許屬於組織成員的參與者成為簡報者，請按一下 [ **公司**]。</span><span class="sxs-lookup"><span data-stu-id="04074-121">To allow only participants who are members of your organization to be a presenter, click **Company**.</span></span> <span data-ttu-id="04074-122">這是預設設定。</span><span class="sxs-lookup"><span data-stu-id="04074-122">This is the default setting.</span></span>
    
   - <span data-ttu-id="04074-123">若要允許任何參與者成為簡報者，請按一下 [ **所有人**]。</span><span class="sxs-lookup"><span data-stu-id="04074-123">To allow any participants to be a presenter, click **Everyone**.</span></span>
    
7. <span data-ttu-id="04074-124">若要讓召集人在排程會議時選取會議類型，請清除 [ **依預設指派會議類型** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="04074-124">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box.</span></span> <span data-ttu-id="04074-125">依預設，會自動指派會議類型。</span><span class="sxs-lookup"><span data-stu-id="04074-125">By default, the conference type is automatically assigned.</span></span>
    
8. <span data-ttu-id="04074-126">若要防止匿名 (未驗證的使用者自動獲准) 使用者，請清除 [ **預設會承認匿名使用者** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="04074-126">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box.</span></span> <span data-ttu-id="04074-127">根據預設，匿名使用者會自動獲准參加會議。</span><span class="sxs-lookup"><span data-stu-id="04074-127">By default, anonymous users are automatically admitted to meetings.</span></span>
    
9. <span data-ttu-id="04074-128">若要自訂傳送給參與者的會議邀請，請執行下列動作。</span><span class="sxs-lookup"><span data-stu-id="04074-128">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="04074-129">請注意，URLs 和自訂頁腳文字的最大長度為1KB。</span><span class="sxs-lookup"><span data-stu-id="04074-129">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="04074-130">除了 [說明 **URL**] 之外，如果您沒有指定自訂專案的值，這些自訂專案不會包含在會議中。</span><span class="sxs-lookup"><span data-stu-id="04074-130">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="04074-131">如果不包含自訂的 [說明] URL，則會在邀請中顯示商務用 Skype 的預設「說明」 URL。</span><span class="sxs-lookup"><span data-stu-id="04074-131">If you do not include a custom help URL, the default help URL for Skype for Business will be displayed in the invite.</span></span> 
    
   - <span data-ttu-id="04074-132">若要自訂出現在會議邀請中的標誌，請在 [ **標誌 URL**] 中輸入標誌的位置。</span><span class="sxs-lookup"><span data-stu-id="04074-132">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span> <span data-ttu-id="04074-133">此徽標必須是大小為 188 x 30 圖元的 GIF 或 JPG 影像。</span><span class="sxs-lookup"><span data-stu-id="04074-133">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span> 
    
   - <span data-ttu-id="04074-134">若要自訂出現在會議邀請中的解說文字，請在 [說明 **URL**] 中輸入説明文字的位置。</span><span class="sxs-lookup"><span data-stu-id="04074-134">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
   - <span data-ttu-id="04074-135">若要自訂出現在會議邀請中的法律文字，請在 [ **合法文字 URL**] 中輸入法律文字的位置。</span><span class="sxs-lookup"><span data-stu-id="04074-135">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
   - <span data-ttu-id="04074-136">若要自訂出現在會議邀請中的頁腳文字，請在 [ **自訂頁腳文字**] 中輸入文字。</span><span class="sxs-lookup"><span data-stu-id="04074-136">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>
    
10. <span data-ttu-id="04074-137">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="04074-137">Click **Commit**.</span></span>
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="04074-138">使用商務用 Skype Server 管理命令介面建立會議設定設定</span><span class="sxs-lookup"><span data-stu-id="04074-138">Create meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="04074-139">若要建立會議配置設定，請使用 **New-CsMeetingConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="04074-139">To create meeting configuration settings, use the **New-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="04074-140">下列命令會為 Redmond 網站建立一組新的會議配置設定：</span><span class="sxs-lookup"><span data-stu-id="04074-140">The following command creates a new set of meeting configuration settings for the Redmond site:</span></span>
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="04074-141">由於上述命令中未指定任何 (必要 Identity 參數) 以外的參數，因此新的會議設定會使用其所有屬性的預設值。</span><span class="sxs-lookup"><span data-stu-id="04074-141">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>
  
<span data-ttu-id="04074-142">若要建立使用不同屬性質的設定，只需要加入適當的參數和參數值即可。</span><span class="sxs-lookup"><span data-stu-id="04074-142">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="04074-143">例如，若要建立會議設定的集合，根據預設，承認所有人都可以加入會議，以供簡報者使用類似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="04074-143">For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="04074-144">您可以透過包含多個參數來設定多個屬性值。</span><span class="sxs-lookup"><span data-stu-id="04074-144">Multiple property values can be set by including multiple parameters.</span></span> <span data-ttu-id="04074-145">例如，下列命令會 admits 每個人參加會議的簡報者，也會強制 PSTN 使用者在大廳等候，直到他們正式獲准參加會議為止：</span><span class="sxs-lookup"><span data-stu-id="04074-145">For example, the following command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

<span data-ttu-id="04074-146">如需詳細資訊，包括完整的參數清單，請參閱 [New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="04074-146">For more information, including a complete list of parameters, see [New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span></span>
