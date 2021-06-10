---
title: 將使用者從商務用 Skype Server 2019 移至 Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 摘要：瞭解如何遷移使用者設定，以及將使用者移至 Teams。
ms.openlocfilehash: b9b21dafc2290dfff5522f5d54c0872121294dd9
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856302"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="21160-103">將使用者從內部部署移動至 Teams</span><span class="sxs-lookup"><span data-stu-id="21160-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="21160-104">當使用者從內部部署移至 Teams 時，使用者的商務用 Skype home 會從內部部署移至線上，且會為使用者指派 mode = TeamsOnly 的 TeamsUpgradePolicy。</span><span class="sxs-lookup"><span data-stu-id="21160-104">When a user is moved from on premises to Teams Only, the user’s Skype for Business home is moved from on premises to online and the user is assigned TeamsUpgradePolicy with mode=TeamsOnly.</span></span>  <span data-ttu-id="21160-105">使用者從內部部署移至 TeamsOnly 模式後：</span><span class="sxs-lookup"><span data-stu-id="21160-105">After a user is moved from on-premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="21160-106">所有來自其他使用者的來電和聊天 (不論是從商務用 Skype 或 Teams) 傳送，都將會在使用者的 Teams 用戶端中土地。</span><span class="sxs-lookup"><span data-stu-id="21160-106">All incoming calls and chats from other users (whether sent from Skype for Business or Teams), will land in the user’s Teams client.</span></span>
- <span data-ttu-id="21160-107">使用者將能夠與使用商務用 Skype (線上或內部部署) 的其他使用者互動。</span><span class="sxs-lookup"><span data-stu-id="21160-107">The user will be able to interoperate with other users who use Skype for Business (whether online or on premises).</span></span>
- <span data-ttu-id="21160-108">使用者將能夠與同盟組織中的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="21160-108">The user will be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="21160-109">由該使用者排程的新會議 Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="21160-109">New meetings scheduled by that user are Teams meetings.</span></span>
- <span data-ttu-id="21160-110">使用者仍然可以加入任何商務用 Skype 會議。</span><span class="sxs-lookup"><span data-stu-id="21160-110">User can still join any Skype for Business meetings.</span></span>
- <span data-ttu-id="21160-111">預定未來的使用者預先存在的會議會從內部部署遷移至 Teams。</span><span class="sxs-lookup"><span data-stu-id="21160-111">The user’s pre-existing meetings scheduled for the future will be migrated from on-premises to Teams.</span></span>
- <span data-ttu-id="21160-112">在使用者第一次登入之後，就可以在 Teams 中取得已存在內部部署的連絡人。</span><span class="sxs-lookup"><span data-stu-id="21160-112">Contacts that existed on-premises are available in Teams shortly after the user logs on for the first time.</span></span>
- <span data-ttu-id="21160-113">使用者無法從商務用 Skype 發起通話或交談，也無法在商務用 Skype 中排程新的會議。</span><span class="sxs-lookup"><span data-stu-id="21160-113">Users cannot initiate calls or chats from Skype for Business, nor can they schedule new meetings in Skype for Business.</span></span> <span data-ttu-id="21160-114">如果他們嘗試開啟商務用 Skype 用戶端，將會重新導向為使用 Teams，如下所示。</span><span class="sxs-lookup"><span data-stu-id="21160-114">If they attempt to open the Skype for Business client, they will be redirected to use Teams as shown below.</span></span> <span data-ttu-id="21160-115">若未安裝 Teams 用戶端，將會使用瀏覽器將其導向 Teams 的網頁版本。</span><span class="sxs-lookup"><span data-stu-id="21160-115">If the Teams client is not installed, they will be directed to the web version of Teams using their browser.</span></span><br><br>
    <span data-ttu-id="21160-116">![將使用者重新導向至 Teams 的郵件](../media/go-to-teams-page.png)</span><span class="sxs-lookup"><span data-stu-id="21160-116">![Message redirecting a user to Teams](../media/go-to-teams-page.png)</span></span>

<span data-ttu-id="21160-117">移動任何使用者之前，請務必先檢查 [必要條件](move-users-between-on-premises-and-cloud.md#prerequisites) ，將使用者移至雲端。</span><span class="sxs-lookup"><span data-stu-id="21160-117">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span> <span data-ttu-id="21160-118">此外，請務必查看[使用 Teams 搭配商務用 Skype 組織的遷移和互通性指導](/microsoftteams/migration-interop-guidance-for-teams-with-skype)方針。</span><span class="sxs-lookup"><span data-stu-id="21160-118">Also be sure to review [Migration and interoperability guidance for organizations using Teams together with Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>


> [!NOTE]
> <span data-ttu-id="21160-119">應停用部署 SfB 帳戶的整合連絡人存放區，以將連絡人移至 Teams。</span><span class="sxs-lookup"><span data-stu-id="21160-119">Unified Contact Store should be disabled on the on-prem SfB account for the contact to be moved to Teams.</span></span>

> [!IMPORTANT]
><span data-ttu-id="21160-120">當您使用 Move-CsUser 將使用者從內部部署移至雲端時，使用者現在會自動被指派 TeamsOnly 模式，而且來自內部部署的會議會自動轉換為 Teams 會議，不論該 `-MoveToTeams` 參數是否實際指定。</span><span class="sxs-lookup"><span data-stu-id="21160-120">When moving a user from on-premises to the cloud with Move-CsUser, users are now automatically assigned TeamsOnly mode and their meetings from on-premises are automatically converted to Teams meetings, regardless of whether the `-MoveToTeams` switch is actually specified.</span></span> <span data-ttu-id="21160-121"> (這包括從 Lync Server 2013 進行遷移，其絕對不會有 `-MoveToTeams` 此參數。 ) 先前若未指定此參數，則會將使用者轉換為位於商務用 Skype Server 內部部署中以商務用 Skype 線上，而且其模式仍保持不變。</span><span class="sxs-lookup"><span data-stu-id="21160-121">(This includes migrations from Lync Server 2013, which never had the `-MoveToTeams` switch.)  Previously if this switch was not specified, users transitioned from being homed in Skype for Business Server on-premises to Skype for Business Online, and their mode remained unchanged.</span></span> <span data-ttu-id="21160-122">這項功能最近已變更，準備退休的商務用 Skype 線上。</span><span class="sxs-lookup"><span data-stu-id="21160-122">This has recently been changed in preparation for retirement of Skype for Business Online.</span></span>


## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="21160-123">將使用者直接從商務用 Skype 內部部署移至 Teams</span><span class="sxs-lookup"><span data-stu-id="21160-123">Move a user directly from Skype for Business on premises to Teams Only</span></span>

<span data-ttu-id="21160-124">商務用 Skype Server 和 Lync Server 2013 中的內部部署系統管理工具可讓您在單一步驟中使用 PowerShell 或商務用 Skype Server 控制台中的 Move-CsUser Cmdlet，將使用者移至 TeamsOnly 模式，如下所述。</span><span class="sxs-lookup"><span data-stu-id="21160-124">The on-premises admin tools in Skype for Business Server and Lync Server 2013 enable you to move users from on premises to TeamsOnly mode in a single step using either the Move-CsUser cmdlet in PowerShell or the Skype for Business Server Control Panel, as described below.</span></span> <span data-ttu-id="21160-125">`-MoveToTeams`不論使用的是哪個版本的商務用 Skype Server 或 Lync Server，都不再需要指定參數的參數和從內部部署直接移至 Teams 的行為。</span><span class="sxs-lookup"><span data-stu-id="21160-125">It is no longer required to specify the `-MoveToTeams` switch and the behavior to move directly from on premises to Teams Only is now automatic, regardless of which version of Skype for Business Server or Lync Server is used.</span></span> 

<span data-ttu-id="21160-126">在內部部署環境和雲端服務 (都必須具備足夠的許可權，Microsoft 365 或 Office 365) ，如[必要的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)所述。</span><span class="sxs-lookup"><span data-stu-id="21160-126">You must have sufficient privileges in both the on-premises environment and the cloud service (Microsoft 365 or Office 365), as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="21160-127">您可以在兩個環境中使用具有許可權的單一帳戶，也可以使用內部部署認證來啟動內部部署商務用 Skype Server 管理命令介面視窗，並使用 `-Credential` 參數指定具有必要系統管理角色之 Microsoft 365 的認證。</span><span class="sxs-lookup"><span data-stu-id="21160-127">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 with the necessary administrative role.</span></span>

<span data-ttu-id="21160-128">此外，除了商務用 Skype 線上) 之外，還必須確定已授與使用者 Teams (的授權。</span><span class="sxs-lookup"><span data-stu-id="21160-128">In addition, you must ensure the user has been granted a license for Teams (in addition to Skype for Business Online).</span></span> <span data-ttu-id="21160-129">請勿停用商務用 Skype 線上授權。</span><span class="sxs-lookup"><span data-stu-id="21160-129">Do not disable the Skype for Business Online license.</span></span>

### <a name="move-to-teams-using-move-csuser"></a><span data-ttu-id="21160-130">使用 Move-CsUser 移至 Teams</span><span class="sxs-lookup"><span data-stu-id="21160-130">Move to Teams using Move-CsUser</span></span>

<span data-ttu-id="21160-131">您可以從內部部署商務用 Skype Server 管理命令介面 PowerShell] 視窗或從 Lync Server 管理命令介面 PowerShell 視窗中取得 Move-CsUser。</span><span class="sxs-lookup"><span data-stu-id="21160-131">Move-CsUser is available from an on-premises Skype for Business Server Management Shell PowerShell window or from a Lync Server Management Shell PowerShell window.</span></span> <span data-ttu-id="21160-132">若要使用 Move-CsUser 將使用者移至 TeamsOnly 模式：</span><span class="sxs-lookup"><span data-stu-id="21160-132">To move a user to TeamsOnly mode using Move-CsUser:</span></span>
- <span data-ttu-id="21160-133">使用參數指定要移動的使用者 `Identity` 。</span><span class="sxs-lookup"><span data-stu-id="21160-133">Specify the user to move using the `Identity` parameter.</span></span>
- <span data-ttu-id="21160-134">指定 `-Target` 值為 "sipfed <span> " 的參數。com "。</span><span class="sxs-lookup"><span data-stu-id="21160-134">Specify the `-Target` parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="21160-135">如果您在內部部署和雲端服務 (Microsoft 365) 中沒有一個帳戶具有足夠的許可權，請使用 `-credential` 參數提供 Microsoft 365 中具有足夠許可權的帳戶。</span><span class="sxs-lookup"><span data-stu-id="21160-135">If you do not have one account with sufficient permissions in both on premises and the cloud service (Microsoft 365), use the `-credential` parameter to supply an account with sufficient permissions in Microsoft 365.</span></span>
- <span data-ttu-id="21160-136">如果 Microsoft 365 中具有許可權的帳戶不會以 "name.onmicrosoft.com17" 結尾。 <span>com "，您必須指定 `-HostedMigrationOverrideUrl` 參數，並在[必要的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述的值正確。</span><span class="sxs-lookup"><span data-stu-id="21160-136">If the account with permissions in Microsoft 365 does not end in “onmicrosoft.<span>com”, you must specify the `-HostedMigrationOverrideUrl` parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="21160-137">下列指令程式順序可用來將使用者移至 TeamsOnly，並假設 Microsoft 365 認證是個別帳戶，並提供給 Get-Credential 提示的輸入。</span><span class="sxs-lookup"><span data-stu-id="21160-137">The following cmdlet sequence can be used to move a user to TeamsOnly, and assumes the Microsoft 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span> <span data-ttu-id="21160-138">不論是否指定參數，行為都相同 `-MoveToTeams` 。</span><span class="sxs-lookup"><span data-stu-id="21160-138">The behavior is the same whether `-MoveToTeams` switch is specified or not.</span></span>

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> <span data-ttu-id="21160-139">在不同的情況下，需要不同的參數，大多數案例的預設命令為：</span><span class="sxs-lookup"><span data-stu-id="21160-139">As there are different circumstances requiring different parameters, the default command for most cases is:</span></span>

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a><span data-ttu-id="21160-140">使用商務用 Skype Server 控制台移至 Teams</span><span class="sxs-lookup"><span data-stu-id="21160-140">Move to Teams using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="21160-141">開啟商務用 Skype Server 的 [控制台] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="21160-141">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="21160-142">在左側導覽中，選擇 [ **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="21160-142">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="21160-143">使用 [**尋找**] 來找出要移至 Teams 的使用者 (s) 。</span><span class="sxs-lookup"><span data-stu-id="21160-143">Use **Find** to locate the user(s) you would like to move to Teams.</span></span>
4. <span data-ttu-id="21160-144">選取 [使用者 (s) ]，然後從清單上方的 [**動作**] 下拉式功能表中，選擇 [**將選取的使用者移至**]，Teams 或 **將選取的使用者移動到商務用 Skype 線上**。</span><span class="sxs-lookup"><span data-stu-id="21160-144">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Teams** or **Move selected users to Skype for Business Online**.</span></span>   <span data-ttu-id="21160-145">這兩個選項現在都會直接將使用者直接移至 TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="21160-145">Either option now moves users directly to TeamsOnly.</span></span>
5. <span data-ttu-id="21160-146">在精靈中，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="21160-146">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="21160-147">如果出現提示，請以 onmicrosoft.com 結尾的帳戶登入 Microsoft 365，且具有足夠的許可權。</span><span class="sxs-lookup"><span data-stu-id="21160-147">If prompted, sign in to Microsoft 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="21160-148">按 **[下一步** **]，然後再一** 次移動使用者。</span><span class="sxs-lookup"><span data-stu-id="21160-148">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="21160-149">請注意，關於成功或失敗的狀態訊息是在主要控制台應用程式的頂端，而不是在嚮導中提供。</span><span class="sxs-lookup"><span data-stu-id="21160-149">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>
    
    
## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a><span data-ttu-id="21160-150">將即將進行的商務用 Skype 內部部署使用者通報 Teams</span><span class="sxs-lookup"><span data-stu-id="21160-150">Notify your Skype for Business on-premises users of the upcoming move to Teams</span></span>

<span data-ttu-id="21160-151">使用 CU8 商務用 Skype Server 2015 中的內部部署系統管理工具，以及商務用 Skype Server 2019，可讓您通知內部部署商務用 Skype 使用者的即將到來移至 Teams。</span><span class="sxs-lookup"><span data-stu-id="21160-151">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to notify on-premises Skype for Business users of their upcoming move to Teams.</span></span> <span data-ttu-id="21160-152">當您啟用這些通知時，使用者會在其商務用 Skype 用戶端 (Win32、Mac、web 及行動) 中看到通知，如下所示。</span><span class="sxs-lookup"><span data-stu-id="21160-152">When you enable these notifications, users will see a notification in their Skype for Business client (Win32, Mac, web, and mobile) as shown below.</span></span> <span data-ttu-id="21160-153">如果使用者按一下 [ **Try it** ] 按鈕，將會在安裝 Teams 用戶端時將其啟動;否則，使用者會在其瀏覽器中流覽至 Teams 的 web 版本。</span><span class="sxs-lookup"><span data-stu-id="21160-153">If users click the **Try it** button, the Teams client will be launched if it is installed; otherwise, users will be navigated to the web version of Teams in their browser.</span></span> <span data-ttu-id="21160-154">根據預設，當啟用通知時，Win32 商務用 Skype 用戶端會無訊息地下載 Teams 用戶端，以便在將使用者移至 TeamsOnly 模式之前能夠使用豐富型用戶端;不過，您也可以停用此行為。</span><span class="sxs-lookup"><span data-stu-id="21160-154">By default, when notifications are enabled, Win32 Skype for Business clients silently download the Teams client so that the rich client is available prior to moving the user to TeamsOnly mode; however, you can also disable this behavior.</span></span>  <span data-ttu-id="21160-155">使用內部部署版本設定通知 `TeamsUpgradePolicy` ，且 Win32 用戶端的無訊息下載是透過內部部署 Cmdlet 來控制的 `TeamsUpgradeConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="21160-155">Notifications are configured using the on-premises version of `TeamsUpgradePolicy`, and silent download for Win32 clients is controlled via the on-premises `TeamsUpgradeConfiguration` cmdlet.</span></span>

> [!TIP]
> <span data-ttu-id="21160-156">部分伺服器可能需要重新開機，以使用 CU8 商務用 Skype 2015。</span><span class="sxs-lookup"><span data-stu-id="21160-156">Some servers may need to reboot for this to work in Skype for Business 2015 with CU8.</span></span>

![即將到來移至 Teams 的通知](../media/teams-upgrade-notification.png)

<span data-ttu-id="21160-158">若要通知內部部署使用者即將升級為 Teams，請使用 NotifySfBUsers = true 建立 TeamsUpgradePolicy 的新實例。</span><span class="sxs-lookup"><span data-stu-id="21160-158">To notify on-premises users that they will soon be upgraded to Teams, create a new instance of TeamsUpgradePolicy with NotifySfBUsers=true.</span></span> <span data-ttu-id="21160-159">然後，您可以將原則直接指派給使用者，或透過設定網站、集區或全域層級的原則，將該原則指派給您想要通知的使用者。</span><span class="sxs-lookup"><span data-stu-id="21160-159">Then assign that policy to the users who you want to notify, either by assigning the policy directly to the user or by setting the policy at the site, pool, or global level.</span></span> <span data-ttu-id="21160-160">下列 Cmdlet 會建立並授與使用者層級原則：</span><span class="sxs-lookup"><span data-stu-id="21160-160">The following cmdlets create and grant a user-level policy:</span></span>

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

<span data-ttu-id="21160-161">透過 TeamsUpgradeConfiguration 商務用 Skype Win32 用戶端，可透過使用 DownloadTeams 參數的內部部署 Cmdlet 來控制自動下載 Teams。</span><span class="sxs-lookup"><span data-stu-id="21160-161">Automatic download of Teams via the Skype for Business Win32 client is controlled via the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="21160-162">您可以在全域、網站及集區層級建立此設定。</span><span class="sxs-lookup"><span data-stu-id="21160-162">You create this configuration on a global, site, and pool level.</span></span> <span data-ttu-id="21160-163">例如，下列命令會建立網站 Redmond1 的設定：</span><span class="sxs-lookup"><span data-stu-id="21160-163">For example, the following command creates the configuration for the site Redmond1:</span></span>

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

<span data-ttu-id="21160-164">DownloadTeams 的值預設為 True;不過，只有在指定的使用者 NotifySfbUser = True 時， *才* 會使用此參數。</span><span class="sxs-lookup"><span data-stu-id="21160-164">By default, the value of DownloadTeams is True; however, it is *only* honored if NotifySfbUser = True for a given user.</span></span>

## <a name="see-also"></a><span data-ttu-id="21160-165">另請參閱</span><span class="sxs-lookup"><span data-stu-id="21160-165">See also</span></span>

[<span data-ttu-id="21160-166">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="21160-166">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)

[<span data-ttu-id="21160-167">授與 CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="21160-167">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy
)

[<span data-ttu-id="21160-168">搭配使用 Teams 與商務用 Skype 之組織的移轉和互通性指引</span><span class="sxs-lookup"><span data-stu-id="21160-168">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="21160-169">與商務用 Skype 共存</span><span class="sxs-lookup"><span data-stu-id="21160-169">Coexistence with Skype for Business</span></span>](/microsoftteams/coexistence-chat-calls-presence)
