---
title: 從內部部署Teams升級商務用 Skype工具
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 從 商務用 Skype 升級至 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 677f642bdb940706079370635a5aa9eec87241fb
ms.sourcegitcommit: e19fdedca6573110d08c7d114e05b84779e36b58
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53437630"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="53fa6-103">適用于 IT 系統管理員的升級Teams &mdash; 工具</span><span class="sxs-lookup"><span data-stu-id="53fa6-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="53fa6-104">本文將說明從 Teams 升級商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="53fa6-104">This article describes tools for upgrading to Teams from Skype for Business.</span></span> 

<span data-ttu-id="53fa6-105">開始升級之前，Microsoft 會建議下列文章說明重要的升級概念和共存行為：</span><span class="sxs-lookup"><span data-stu-id="53fa6-105">Before beginning your upgrade, Microsoft recommends the following articles that describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="53fa6-106">Teams和商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="53fa6-106">Coexistence of Teams and Skype for Business</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="53fa6-107">共存模式 - 參照</span><span class="sxs-lookup"><span data-stu-id="53fa6-107">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="53fa6-108">Teams 用戶端體驗和遵從共存模式</span><span class="sxs-lookup"><span data-stu-id="53fa6-108">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="53fa6-109">管理升級的工具</span><span class="sxs-lookup"><span data-stu-id="53fa6-109">Tools for managing the upgrade</span></span>

<span data-ttu-id="53fa6-110">無論您選擇哪一種升級方法，對於已經有 商務用 Skype Online 的使用者，您都使用 TeamsUpgradePolicy 管理向 TeamsOnly 的轉換，而[TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)會控制使用者的共存模式。</span><span class="sxs-lookup"><span data-stu-id="53fa6-110">Whichever upgrade method you choose, for users that already have Skype for Business Online, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="53fa6-111">對於在 商務用 Skype Server 中擁有內部部署帳戶的使用者，您也可以將它們移至 `Move-CsUser` [雲端](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)。</span><span class="sxs-lookup"><span data-stu-id="53fa6-111">For users with an on-premises account in Skype for Business Server, you also use `Move-CsUser` to [move them to the cloud](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span></span>  <span data-ttu-id="53fa6-112">有關每個模式的資訊，請參閱 [共存模式](migration-interop-guidance-for-teams-with-skype.md)。</span><span class="sxs-lookup"><span data-stu-id="53fa6-112">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>

> [!NOTE]
> <span data-ttu-id="53fa6-113">如果您目前使用 商務用 Skype Online Connector 來管理您的服務，您必須移至 PowerShell 模組Teams並更新現有的 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="53fa6-113">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="53fa6-114">請參閱[從線上連接器商務用 Skype移至 powerShell Teams模組以](teams-powershell-move-from-sfbo.md)瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="53fa6-114">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="53fa6-115">無論您使用不同的模式執行選取功能轉換商務用 Skype或只是從預設群島組態升級至 TeamsOnly 模式，TeamsUpgradePolicy 都是主要工具。就像其他系統Teams一樣，您可以直接將 TeamsUpgradePolicy 指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="53fa6-115">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool.Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="53fa6-116">您也可以將策略設定為租使用者範圍的預設值。</span><span class="sxs-lookup"><span data-stu-id="53fa6-116">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="53fa6-117">任何指派給使用者的優先順序都高於租使用者的預設設定。</span><span class="sxs-lookup"><span data-stu-id="53fa6-117">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="53fa6-118">您可以在系統管理主控台和 PowerShell Teams管理該策略。</span><span class="sxs-lookup"><span data-stu-id="53fa6-118">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="53fa6-119">您可以將 TeamsUpgradePolicy 的任何模式指派給位於內部部署商務用 Skype使用者，但 TeamsOnly 模式除外。</span><span class="sxs-lookup"><span data-stu-id="53fa6-119">You can assign any mode of TeamsUpgradePolicy, except for TeamsOnly mode, to users homed in Skype for Business on-premises.</span></span> <span data-ttu-id="53fa6-120">相反地，雲端使用者只能指派 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="53fa6-120">Conversely, users homed in the cloud can only be assigned TeamsOnly mode.</span></span> <span data-ttu-id="53fa6-121">**TeamsOnly** 模式只能指派給已經位於雲端的使用者，因為只有使用者位於 商務用 Skype Online 中，才能與 商務用 Skype 使用者以及 Microsoft 365 電話系統 功能進行交互操作和聯合。</span><span class="sxs-lookup"><span data-stu-id="53fa6-121">**TeamsOnly mode can only be assigned to a user who is already homed in the cloud** because interop and federation with Skype for Business users as well as Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span>  <span data-ttu-id="53fa6-122">此外，如果您有 商務用 Skype 內部部署 (，則無法將 **TeamsOnly** 模式指派為整個租使用者的預設模式，因為 lyncdiscover DNS 記錄的存在會偵測到 Office 365 外的位置。</span><span class="sxs-lookup"><span data-stu-id="53fa6-122">Further, **you can't assign TeamsOnly mode as the tenant-wide default if you have a Skype for Business on-premises deployment** (which is detected by presence of a lyncdiscover DNS record that points to location other than Office 365.</span></span> <span data-ttu-id="53fa6-123">詳細資料請參閱[停用混合式組Teams移。](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid)</span><span class="sxs-lookup"><span data-stu-id="53fa6-123">For details, see [Disable your hybrid configuration to complete migration to Teams Only](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>

<span data-ttu-id="53fa6-124">擁有商務用 Skype內部部署帳戶的使用者，必須使用內部部署工具Teams[](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)中的 Move-CsUser移至 商務用 Skype 模式。</span><span class="sxs-lookup"><span data-stu-id="53fa6-124">Users with Skype for Business accounts homed on-premises [must be moved online](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) to Teams Only mode using Move-CsUser in the Skype for Business on-premises toolset.</span></span> 

<span data-ttu-id="53fa6-125">與其他政策不同，在系統或系統內無法建立 TeamsUpgradePolicy Microsoft 365 Office 365。</span><span class="sxs-lookup"><span data-stu-id="53fa6-125">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="53fa6-126">所有現有的實例都內建于服務中。</span><span class="sxs-lookup"><span data-stu-id="53fa6-126">All the existing instances are built into the service.</span></span>  <span data-ttu-id="53fa6-127"> (請注意，mode 是 TeamsUpgradePolicy 中的屬性，而不是策略實例的名稱。) 在某些情況下 ，但並非所有的情況中，策略實例的名稱與模式相同。</span><span class="sxs-lookup"><span data-stu-id="53fa6-127">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="53fa6-128">特別是，若要將 TeamsOnly 模式指派給使用者，您將將 TeamsUpgradePolicy 的 「UpgradeToTeams」 實例授予該使用者。</span><span class="sxs-lookup"><span data-stu-id="53fa6-128">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="53fa6-129">若要查看所有實例的清單，您可以執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="53fa6-129">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="53fa6-130">若要將線上使用者升級至 TeamsOnly 模式，請指派「UpgradeToTeams」實例：</span><span class="sxs-lookup"><span data-stu-id="53fa6-130">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="53fa6-131">若要將內部部署使用者商務用 Skype TeamsOnly 模式，請使用Move-CsUser工具集的以下選項：</span><span class="sxs-lookup"><span data-stu-id="53fa6-131">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -credential $cred
```

<span data-ttu-id="53fa6-132">若要變更租使用者中所有使用者的模式，但具有明確每個使用者授權的使用者除外 (優先) ，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="53fa6-132">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="53fa6-133">如果您有任何擁有內部部署帳戶商務用 Skype，您無法在租使用者層級指派 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="53fa6-133">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="53fa6-134">您必須使用 Move-CsUser 將這些使用者個別移至Teams模式。</span><span class="sxs-lookup"><span data-stu-id="53fa6-134">You must move these users individually to Teams Only mode using Move-CsUser.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="53fa6-135">在用戶端商務用 Skype通知</span><span class="sxs-lookup"><span data-stu-id="53fa6-135">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="53fa6-136">系統管理員可以選擇在 商務用 Skype 中提供使用者通知，通知使用者他們即將升級至 Teams，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="53fa6-136">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="53fa6-137">例如，在系統管理員打算將一組使用者升級至 TeamsOnly 模式的一周之前，系統管理員可能會想要針對該使用者群組開啟這些通知。</span><span class="sxs-lookup"><span data-stu-id="53fa6-137">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="53fa6-138">這些通知會使用具有 NotifySfbUsers=true 的 TeamsUpgradePolicy 實例啟用。</span><span class="sxs-lookup"><span data-stu-id="53fa6-138">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="53fa6-139">針對 TeamsOnly 外的所有模式，每個模式實際上有兩個實例，對應到 NotifySfbUsers 的兩個值。</span><span class="sxs-lookup"><span data-stu-id="53fa6-139">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="53fa6-140">針對 TeamsOnly 外的所有模式，每個模式實際上有兩個實例，對應到 NotifySfbUsers 的兩個值。</span><span class="sxs-lookup"><span data-stu-id="53fa6-140">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![顯示通知的圖表](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="53fa6-142">如果您的使用者是使用 商務用 Skype Online，只要指派與使用者模式相同的策略實例，但使用 NotifySfbUsers=true。</span><span class="sxs-lookup"><span data-stu-id="53fa6-142">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="53fa6-143">如果您的使用者位於 商務用 Skype Server 內部部署中，您必須使用內部部署工具集，而 2015 商務用 Skype Server 需要 商務用 Skype Server 2019 或 CU8。</span><span class="sxs-lookup"><span data-stu-id="53fa6-143">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="53fa6-144">對於位於內部商務用 Skype Server中的使用者，會遵守 TeamsUpgradePolicy 線上實例中的 mode 屬性，但 NotifySfbUsers 屬性則沒有。</span><span class="sxs-lookup"><span data-stu-id="53fa6-144">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="53fa6-145">如果需要通知，您必須建立 TeamsUpgradePolicy 的內部部署實例，以控制用戶端行為。</span><span class="sxs-lookup"><span data-stu-id="53fa6-145">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="53fa6-146">在內部部署 PowerShell 視窗中，使用 NotifySfbUsers=true 建立 TeamsUpgradePolicy 的新實例：</span><span class="sxs-lookup"><span data-stu-id="53fa6-146">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="53fa6-147">然後，使用相同的內部部署 PowerShell 視窗，將新策略指派給想要的使用者：</span><span class="sxs-lookup"><span data-stu-id="53fa6-147">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="53fa6-148">會議移移</span><span class="sxs-lookup"><span data-stu-id="53fa6-148">Meeting migration</span></span>

<span data-ttu-id="53fa6-149">當使用者移轉至 TeamsOnly 模式時，根據預設商務用 Skype他們組織的現有會議將會轉換成Teams。</span><span class="sxs-lookup"><span data-stu-id="53fa6-149">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="53fa6-150">您可以選擇將 TeamsOnly 模式指派給使用者時停用預設行為。</span><span class="sxs-lookup"><span data-stu-id="53fa6-150">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="53fa6-151">將使用者從內部部署移轉時，會議必須移轉至雲端，以使用線上使用者帳戶運作，但如果您未指定 -MoveToTeams，會議會移轉為 商務用 Skype 會議，而不是轉換成 Teams。</span><span class="sxs-lookup"><span data-stu-id="53fa6-151">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="53fa6-152">在租使用者層級指派 TeamsOnly 模式時，不會針對任何使用者觸發會議移移。</span><span class="sxs-lookup"><span data-stu-id="53fa6-152">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="53fa6-153">如果您想要在租使用者層級指派 TeamsOnly 模式並移移會議，您可以使用 PowerShell 在租使用者 (中取得使用者清單，例如，在 Get-CsOnlineUser 中使用所需的任何篩選) ，然後迴圈流覽這些使用者，以啟動使用 Start-CsExMeetingMigration 進行會議移入。</span><span class="sxs-lookup"><span data-stu-id="53fa6-153">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="53fa6-154">詳細資料請參閱使用會議移 ([MMS) 。](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="53fa6-154">For details, see [Using the Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="53fa6-155">相關連結</span><span class="sxs-lookup"><span data-stu-id="53fa6-155">Related links</span></span>

[<span data-ttu-id="53fa6-156">共存模式 - 參照</span><span class="sxs-lookup"><span data-stu-id="53fa6-156">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="53fa6-157">設定商務用 Skype Server或Microsoft 365之間的Office 365</span><span class="sxs-lookup"><span data-stu-id="53fa6-157">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="53fa6-158">在內部部署和雲端之間移動使用者</span><span class="sxs-lookup"><span data-stu-id="53fa6-158">Move users between on-premises and cloud</span></span>](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="53fa6-159">設定您的共存和升級設定</span><span class="sxs-lookup"><span data-stu-id="53fa6-159">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="53fa6-160">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="53fa6-160">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="53fa6-161">使用會議移 (MMS) </span><span class="sxs-lookup"><span data-stu-id="53fa6-161">Using the Meeting Migration Service (MMS)</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
