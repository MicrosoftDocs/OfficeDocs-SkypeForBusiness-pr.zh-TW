---
title: 從商務用 Skype 內部部署升級到 Teams 的工具
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 從商務用 Skype 升級至 Teams 的工具
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c272cdd6eac98b8847b6f915d59b62444d16c97
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460433"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="67bb4-103">適用于 IT 系統管理員升級至 Teams &mdash; 的工具</span><span class="sxs-lookup"><span data-stu-id="67bb4-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="67bb4-104">本文將說明從商務用 Skype 升級到 Teams 的工具。</span><span class="sxs-lookup"><span data-stu-id="67bb4-104">This article describes tools for upgrading to Teams from Skype for Business.</span></span> 

<span data-ttu-id="67bb4-105">在開始升級之前，Microsoft 會建議下列文章說明重要的升級概念和共存行為：</span><span class="sxs-lookup"><span data-stu-id="67bb4-105">Before beginning your upgrade, Microsoft recommends the following articles that describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="67bb4-106">Teams 和商務用 Skype 的共存</span><span class="sxs-lookup"><span data-stu-id="67bb4-106">Coexistence of Teams and Skype for Business</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="67bb4-107">共存模式 - 參照</span><span class="sxs-lookup"><span data-stu-id="67bb4-107">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="67bb4-108">Teams 用戶端體驗和遵從共存模式</span><span class="sxs-lookup"><span data-stu-id="67bb4-108">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="67bb4-109">管理升級的工具</span><span class="sxs-lookup"><span data-stu-id="67bb4-109">Tools for managing the upgrade</span></span>

<span data-ttu-id="67bb4-110">無論您選擇哪一種升級方法，對於已經有商務用 Skype Online 的使用者，您都使用 [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)管理 TeamsOnly 的轉換，該轉換會控制使用者的共存模式。</span><span class="sxs-lookup"><span data-stu-id="67bb4-110">Whichever upgrade method you choose, for users that already have Skype for Business Online, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="67bb4-111">對於在商務用 Skype Server 中擁有內部部署帳戶的使用者，您也可以將它們移到 `Move-CsUser` [雲端](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)。</span><span class="sxs-lookup"><span data-stu-id="67bb4-111">For users with an on-premises account in Skype for Business Server, you also use `Move-CsUser` to [move them to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span></span>  <span data-ttu-id="67bb4-112">有關每個模式的資訊，請參閱 [共存模式](migration-interop-guidance-for-teams-with-skype.md)。</span><span class="sxs-lookup"><span data-stu-id="67bb4-112">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>

> [!NOTE]
> <span data-ttu-id="67bb4-113">如果您目前使用商務用 Skype Online Connector 來管理服務，您必須移至 Teams PowerShell 模組並更新現有的 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="67bb4-113">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="67bb4-114">詳細資訊 [請參閱從商務用 Skype Online Connector](teams-powershell-move-from-sfbo.md) 移至 Teams PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="67bb4-114">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="67bb4-115">無論您是使用商務用 Skype 模式執行選取功能轉換，或只是從預設群島組態升級到 TeamsOnly 模式，TeamsUpgradePolicy 都是擁有商務用 Skype Online 使用者的主要工具。</span><span class="sxs-lookup"><span data-stu-id="67bb4-115">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool for users who already have Skype for Business Online.</span></span> <span data-ttu-id="67bb4-116">就像 Teams 中的其他任何政策一樣，您可以直接將 TeamsUpgradePolicy 指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="67bb4-116">Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="67bb4-117">您也可以將策略設定為全租使用者的預設。</span><span class="sxs-lookup"><span data-stu-id="67bb4-117">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="67bb4-118">任何指派給使用者的作業都優先于租使用者的預設設定。</span><span class="sxs-lookup"><span data-stu-id="67bb4-118">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="67bb4-119">您可以在 Teams 系統管理主控台和 PowerShell 中管理該政策。</span><span class="sxs-lookup"><span data-stu-id="67bb4-119">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="67bb4-120">您也可以將 TeamsOnly 模式以外的任何 TeamsUpgradePolicy 模式指派給位於商務用 Skype 內部部署中的使用者。</span><span class="sxs-lookup"><span data-stu-id="67bb4-120">You can also assign any mode of TeamsUpgradePolicy, except for TeamsOnly mode, to users homed in Skype for Business on-premises.</span></span> <span data-ttu-id="67bb4-121">**TeamsOnly** 模式只能指派給已位於商務用 Skype Online 中的使用者。</span><span class="sxs-lookup"><span data-stu-id="67bb4-121">**TeamsOnly mode can only be assigned to a user who is already homed in Skype for Business Online**.</span></span> <span data-ttu-id="67bb4-122">這是因為只有使用者位於商務用 Skype Online 中，才能與商務用 Skype 使用者和聯盟以及 Microsoft 365 電話系統功能進行互動。</span><span class="sxs-lookup"><span data-stu-id="67bb4-122">This is because interop with Skype for Business users and federation and Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span> <span data-ttu-id="67bb4-123">此外，如果您有商務用 Skype 內部部署 (且 Lyncdiscover DNS 記錄指向 Office 365 之外的位置，您便無法將 **TeamsOnly** 模式指派為全租使用者的預設模式。</span><span class="sxs-lookup"><span data-stu-id="67bb4-123">In addition, **you can't assign TeamsOnly mode as the tenant-wide default if you have a Skype for Business on-premises deployment** (which is detected by presence of a lyncdiscover DNS record that points to location other than Office 365.</span></span>

<span data-ttu-id="67bb4-124">擁有內部部署商務用 Skype 帳戶的使用者必須[](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)移至線上 (或是移至商務用 Skype Online，或直接使用商務用 Skype 內部部署工具集的) Move-CsUser 移至 Teams Move-CsUser。</span><span class="sxs-lookup"><span data-stu-id="67bb4-124">Users with Skype for Business accounts homed on-premises [must be moved online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (either to Skype for Business Online or direct to Teams) using Move-CsUser in the Skype for Business on-premises toolset.</span></span> <span data-ttu-id="67bb4-125">這些使用者可以按照 1 或 2 個步驟移至 TeamsOnly：</span><span class="sxs-lookup"><span data-stu-id="67bb4-125">These users can be moved to TeamsOnly in either 1 or 2 steps:</span></span>

-   <span data-ttu-id="67bb4-126">1 個步驟：在 Move-CsUser 中指定 -MoveToTeams 參數。</span><span class="sxs-lookup"><span data-stu-id="67bb4-126">1 step:  Specify the -MoveToTeams switch in Move-CsUser.</span></span> <span data-ttu-id="67bb4-127">這需要商務用 Skype Server 2019 或商務用 Skype Server 2015 與 CU8 或更新版。</span><span class="sxs-lookup"><span data-stu-id="67bb4-127">This requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span>

-   <span data-ttu-id="67bb4-128">2 個步驟：執行 Move-CsUser 之後，使用 TeamsUpgradePolicy 將 TeamsOnly 模式授予使用者。</span><span class="sxs-lookup"><span data-stu-id="67bb4-128">2 steps: After running Move-CsUser, grant TeamsOnly mode to the user using TeamsUpgradePolicy.</span></span>

<span data-ttu-id="67bb4-129">不同于其他政策，在 Microsoft 365 或 Office 365 中無法建立 TeamsUpgradePolicy 的新實例。</span><span class="sxs-lookup"><span data-stu-id="67bb4-129">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="67bb4-130">所有現有的實例都內建于服務中。</span><span class="sxs-lookup"><span data-stu-id="67bb4-130">All the existing instances are built into the service.</span></span>  <span data-ttu-id="67bb4-131"> (請注意，模式是 TeamsUpgradePolicy 中的屬性，而不是一個策略實例的名稱。) 在某些情況中 ，但並非全部，該策略實例的名稱與模式相同。</span><span class="sxs-lookup"><span data-stu-id="67bb4-131">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="67bb4-132">特別是，若要將 TeamsOnly 模式指派給使用者，您必須將 TeamsUpgradePolicy 的「UpgradeToTeams」實例授予該使用者。</span><span class="sxs-lookup"><span data-stu-id="67bb4-132">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="67bb4-133">若要查看所有實例的清單，您可以執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="67bb4-133">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="67bb4-134">若要將線上使用者升級至 TeamsOnly 模式，請指派「UpgradeToTeams」實例：</span><span class="sxs-lookup"><span data-stu-id="67bb4-134">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="67bb4-135">若要將內部部署商務用 Skype 使用者升級至 TeamsOnly 模式，Move-CsUser內部部署工具集：</span><span class="sxs-lookup"><span data-stu-id="67bb4-135">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

<span data-ttu-id="67bb4-136">若要變更租使用者中所有使用者的模式，但具有明確每個使用者授予許可權的使用者除外 (優先) ，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="67bb4-136">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="67bb4-137">如果您有內部部署商務用 Skype 帳戶的任何使用者，您無法在租使用者層級指派 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="67bb4-137">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="67bb4-138">您必須使用 Move-CsUser，將這些使用者個別移至雲端。</span><span class="sxs-lookup"><span data-stu-id="67bb4-138">You must move these users individually to the cloud using Move-CsUser.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="67bb4-139">在商務用 Skype 用戶端中使用通知</span><span class="sxs-lookup"><span data-stu-id="67bb4-139">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="67bb4-140">系統管理員可選擇在商務用 Skype 用戶端中提供使用者通知，通知使用者即將升級至 Teams，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="67bb4-140">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="67bb4-141">例如，在系統管理員計畫將一組使用者升級至 TeamsOnly 模式的一周之前，系統管理員可能會想要針對該使用者群組開啟這些通知。</span><span class="sxs-lookup"><span data-stu-id="67bb4-141">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="67bb4-142">這些通知是使用 TeamsUpgradePolicy 實例與 NotifySfbUsers=true 啟用。</span><span class="sxs-lookup"><span data-stu-id="67bb4-142">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="67bb4-143">對於 TeamsOnly 外的所有模式，每個模式實際上都有兩個實例，對應到 NotifySfbUsers 的兩個值。</span><span class="sxs-lookup"><span data-stu-id="67bb4-143">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="67bb4-144">對於 TeamsOnly 外的所有模式，每個模式實際上都有兩個實例，對應到 NotifySfbUsers 的兩個值。</span><span class="sxs-lookup"><span data-stu-id="67bb4-144">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![顯示通知的圖表](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="67bb4-146">如果您的使用者是商務用 Skype Online 的首頁，只要指派與使用者模式相同的策略實例，但使用 NotifySfbUsers=true。</span><span class="sxs-lookup"><span data-stu-id="67bb4-146">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="67bb4-147">如果您的使用者位於商務用 Skype Server 內部部署中，您必須使用內部部署工具集，而且您需要商務用 Skype Server 2019 或商務用 Skype Server 2015 的 CU8。</span><span class="sxs-lookup"><span data-stu-id="67bb4-147">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="67bb4-148">對於位於內部部署商務用 Skype Server 的使用者，會使用 TeamsUpgradePolicy 線上實例的 mode 屬性，但不使用 NotifySfbUsers 屬性。</span><span class="sxs-lookup"><span data-stu-id="67bb4-148">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="67bb4-149">如果需要通知，您必須建立 TeamsUpgradePolicy 內部部署實例，以控制用戶端行為。</span><span class="sxs-lookup"><span data-stu-id="67bb4-149">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="67bb4-150">在內部部署 PowerShell 視窗中，使用 NotifySfbUsers=true 建立 TeamsUpgradePolicy 的新實例：</span><span class="sxs-lookup"><span data-stu-id="67bb4-150">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="67bb4-151">然後，使用相同的內部部署 PowerShell 視窗，將新策略指派給所需的使用者：</span><span class="sxs-lookup"><span data-stu-id="67bb4-151">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="67bb4-152">會議移移</span><span class="sxs-lookup"><span data-stu-id="67bb4-152">Meeting migration</span></span>

<span data-ttu-id="67bb4-153">當使用者移轉至 TeamsOnly 模式時，根據預設，他們組織的現有商務用 Skype 會議將會轉換成 Teams。</span><span class="sxs-lookup"><span data-stu-id="67bb4-153">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="67bb4-154">您可以選擇性地停用將 TeamsOnly 模式指派給使用者時的預設行為。</span><span class="sxs-lookup"><span data-stu-id="67bb4-154">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="67bb4-155">將使用者從內部部署移轉時，會議必須移至雲端，以使用線上使用者帳戶運作，但如果您未指定 -MoveToTeams，會議會移轉為商務用 Skype 會議，而不是轉換成 Teams。</span><span class="sxs-lookup"><span data-stu-id="67bb4-155">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="67bb4-156">在租使用者層級指派 TeamsOnly 模式時，不會針對任何使用者觸發會議移移。</span><span class="sxs-lookup"><span data-stu-id="67bb4-156">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="67bb4-157">如果您想要在租使用者層級指派 TeamsOnly 模式並移移會議，您可以使用 PowerShell 在租使用者 (中取得使用者清單 (例如，使用 Get-CsOnlineUser 具有所需的任何篩選準則) 然後迴圈流覽這些使用者，以使用 Start-CsExMeetingMigration 觸發會議移入。</span><span class="sxs-lookup"><span data-stu-id="67bb4-157">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="67bb4-158">有關詳細資料，請參閱使用會議移 ([MMS) 。](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="67bb4-158">For details, see [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="67bb4-159">相關連結</span><span class="sxs-lookup"><span data-stu-id="67bb4-159">Related links</span></span>

[<span data-ttu-id="67bb4-160">共存模式 - 參照</span><span class="sxs-lookup"><span data-stu-id="67bb4-160">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="67bb4-161">設定商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連接</span><span class="sxs-lookup"><span data-stu-id="67bb4-161">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="67bb4-162">在內部部署和雲端之間移動使用者</span><span class="sxs-lookup"><span data-stu-id="67bb4-162">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="67bb4-163">設定您的共存和升級設定</span><span class="sxs-lookup"><span data-stu-id="67bb4-163">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="67bb4-164">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="67bb4-164">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="67bb4-165">使用會議移 (MMS) </span><span class="sxs-lookup"><span data-stu-id="67bb4-165">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

