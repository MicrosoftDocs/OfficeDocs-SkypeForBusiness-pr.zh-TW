---
title: 將使用者從商務用 Skype Server 2019 移至團隊
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
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
description: '摘要: 瞭解如何將使用者設定遷移並將使用者移至團隊。'
ms.openlocfilehash: c655d8ecaa5856a57d7e675676c0ba5e8c2c43d6
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464676"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="e7585-103">將使用者從內部部署移至團隊</span><span class="sxs-lookup"><span data-stu-id="e7585-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="e7585-104">當使用者從內部部署移至 [團隊] 時, 使用者的商務用 Skype 家用版會從 [內部部署] 移至 [線上], 而使用者會獲指派 mode = TeamsOnly 的 TeamsUpgradePolicy。</span><span class="sxs-lookup"><span data-stu-id="e7585-104">When a user is moved from on premises to Teams Only, the user’s Skype for Business home is moved from on premises to online and the user is assigned TeamsUpgradePolicy with mode=TeamsOnly.</span></span>  <span data-ttu-id="e7585-105">使用者從內部部署移至 TeamsOnly 模式後:</span><span class="sxs-lookup"><span data-stu-id="e7585-105">After a user is moved from on-premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="e7585-106">來自其他使用者的所有來電及聊天 (無論是從商務用 Skype 或團隊傳送), 都將居住在使用者的團隊用戶端中。</span><span class="sxs-lookup"><span data-stu-id="e7585-106">All incoming calls and chats from other users (whether sent from Skype for Business or Teams), will land in the user’s Teams client.</span></span>
- <span data-ttu-id="e7585-107">使用者將能夠與其他使用商務用 Skype 的使用者進行交互操作 (無論是線上或內部部署)。</span><span class="sxs-lookup"><span data-stu-id="e7585-107">The user will be able to interoperate with other users who use Skype for Business (whether online or on premises).</span></span>
- <span data-ttu-id="e7585-108">使用者將能夠與同盟組織中的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="e7585-108">The user will be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="e7585-109">由該使用者排程的新會議為 [團隊會議]。</span><span class="sxs-lookup"><span data-stu-id="e7585-109">New meetings scheduled by that user are Teams meetings.</span></span>
- <span data-ttu-id="e7585-110">使用者仍然可以加入任何商務用 Skype 會議。</span><span class="sxs-lookup"><span data-stu-id="e7585-110">User can still join any Skype for Business meetings.</span></span>
- <span data-ttu-id="e7585-111">已排程未來的使用者預先存在的會議將會從內部部署到團隊。</span><span class="sxs-lookup"><span data-stu-id="e7585-111">The user’s pre-existing meetings scheduled for the future will be migrated from on-premises to Teams.</span></span>
- <span data-ttu-id="e7585-112">在使用者第一次登入時, 小組中不久就會提供與內部部署的連絡人。</span><span class="sxs-lookup"><span data-stu-id="e7585-112">Contacts that existed on premises are available in Teams shortly after the user logs on for the first time.</span></span>
- <span data-ttu-id="e7585-113">使用者無法從商務用 Skype 啟動通話或聊天, 也無法在商務用 Skype 中排程新的會議。</span><span class="sxs-lookup"><span data-stu-id="e7585-113">Users cannot initiate calls or chats from Skype for Business, nor can they schedule new meetings in Skype for Business.</span></span> <span data-ttu-id="e7585-114">如果他們嘗試開啟商務用 Skype 用戶端, 就會將它們重新導向為使用團隊, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="e7585-114">If they attempt to open the Skype for Business client, they will be redirected to use Teams as shown below.</span></span> <span data-ttu-id="e7585-115">如果未安裝團隊用戶端, 則會使用瀏覽器將其導向至團隊的網頁版本。</span><span class="sxs-lookup"><span data-stu-id="e7585-115">If the Teams client is not installed, they will be directed to the web version of Teams using their browser.</span></span><br><br>
    <span data-ttu-id="e7585-116">![將使用者重新導向至團隊的郵件](../media/go-to-teams-page.png)</span><span class="sxs-lookup"><span data-stu-id="e7585-116">![Message redirecting a user to Teams](../media/go-to-teams-page.png)</span></span>

<span data-ttu-id="e7585-117">在移動任何使用者之前, 請務必先檢查[先決條件](move-users-between-on-premises-and-cloud.md#prerequisites), 才能將使用者移至雲端。</span><span class="sxs-lookup"><span data-stu-id="e7585-117">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span> <span data-ttu-id="e7585-118">此外, 請務必參閱[與商務用 Skype 搭配使用團隊之組織的遷移與互通性指導](/microsoftteams/migration-interop-guidance-for-teams-with-skype)方針。</span><span class="sxs-lookup"><span data-stu-id="e7585-118">Also be sure to review [Migration and interoperability guidance for organizations using Teams together with Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>


> [!NOTE]
> <span data-ttu-id="e7585-119">必須停用內部部署 SfB 帳戶上的 [整合連絡人存放區], 才能將該連絡人移至 [小組]。</span><span class="sxs-lookup"><span data-stu-id="e7585-119">Unified Contact Store should be disabled on the on-prem SfB account for the contact to be moved to Teams.</span></span>


<span data-ttu-id="e7585-120">有兩種方法可以將使用者從內部部署移至團隊:</span><span class="sxs-lookup"><span data-stu-id="e7585-120">There are two methods to move a user from on premises to Teams:</span></span>

- <span data-ttu-id="e7585-121">如果您使用的是商務用 Skype Server 2015 CU8 之前的版本, 則移動需要兩個步驟 (如果需要, 可以將其腳本化為單一步驟):</span><span class="sxs-lookup"><span data-stu-id="e7585-121">If you are using a version earlier than Skype for Business Server 2015 CU8, the move requires two steps (which can be scripted to be done together as a single step, if desired):</span></span>
  - <span data-ttu-id="e7585-122">[將使用者從商務用 Skype Server (內部部署) 移至商務用 Skype Online](move-users-from-on-premises-to-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="e7585-122">[Move the user from Skype for Business Server (on premises) to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span></span>
  - <span data-ttu-id="e7585-123">當使用者駐留在商務用 Skype Online 中時, 請以 mode = TeamsOnly 指派使用者 TeamsUpgradePolicy。</span><span class="sxs-lookup"><span data-stu-id="e7585-123">Once the user is homed in Skype for Business Online, assign the user TeamsUpgradePolicy with mode= TeamsOnly.</span></span> <span data-ttu-id="e7585-124">若要授與 TeamsOnly 模式, 請從商務用 Skype Online PowerShell 視窗中執行下列 Cmdlet:`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span><span class="sxs-lookup"><span data-stu-id="e7585-124">To grant TeamsOnly mode, run the following cmdlet from a Skype for Business Online PowerShell window: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span></span>
- <span data-ttu-id="e7585-125">如果您有商務用 Skype Server 2015 CU8 或更新版本的系統管理工具, 您可以使用上述方法, 或者您可以按照下文所述, 在一個步驟中移動。</span><span class="sxs-lookup"><span data-stu-id="e7585-125">If you have admin tools from Skype for Business Server 2015 CU8 or later, you can use the method above, or you can do this move in one step as described below.</span></span> <span data-ttu-id="e7585-126">此外, 您可以選擇性地在商務用 Skype 用戶端中提供通知, 然後再將其移至團隊, 以及選擇性地讓商務用 Skype 用戶端自行下載 [團隊用戶端]。</span><span class="sxs-lookup"><span data-stu-id="e7585-126">In addition, you can optionally provide a notification within the Skype for Business client prior to moving them to Teams Only as well as optionally have the Teams client silently downloaded by the Skype for Business client.</span></span>

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="e7585-127">將使用者直接從商務用 Skype 移至團隊</span><span class="sxs-lookup"><span data-stu-id="e7585-127">Move a user directly from Skype for Business on premises to Teams Only</span></span>

<span data-ttu-id="e7585-128">在商務用 Skype Server 2015 中使用 CU8 以及商務用 Skype Server 2019 中的內部部署系統管理工具, 您可以使用 PowerShell 或商務用 Skype Se 中的 Move-csuser Cmdlet, 在單一步驟中, 將使用者從內部部署移至 [僅限團隊模式]rver [控制台], 如下所述。</span><span class="sxs-lookup"><span data-stu-id="e7585-128">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to move users from on premises to Teams Only mode in a single step using either the Move-CsUser cmdlet in PowerShell or the Skype for Business Server Control Panel, as described below.</span></span>

### <a name="move-to-teams-using-move-csuser"></a><span data-ttu-id="e7585-129">使用移動 Move-csuser 移至團隊</span><span class="sxs-lookup"><span data-stu-id="e7585-129">Move to Teams using Move-CsUser</span></span>

<span data-ttu-id="e7585-130">您可以從內部部署商務用 Skype Management Shell PowerShell 視窗中取得 Move-csuser。</span><span class="sxs-lookup"><span data-stu-id="e7585-130">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="e7585-131">下列步驟與需要的許可權與將使用者移至商務用 Skype Online 的方式相同, 除了您必須指定 MoveToTeams 開關之外, 您必須確保使用者也已獲授與其他團隊的授權 (除了商務用 Skype)線上)。</span><span class="sxs-lookup"><span data-stu-id="e7585-131">The steps below and permissions required are the same as moving a user to Skype for Business Online, except that you must also specify the MoveToTeams switch and you must ensure that the user has also been granted a license for Teams (in addition to Skype for Business Online).</span></span>

<span data-ttu-id="e7585-132">在內部部署環境和 Office 365 租使用者中, 您必須具備足夠的許可權, 如[所需的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。</span><span class="sxs-lookup"><span data-stu-id="e7585-132">You must have sufficient privileges in both the on-premises environment and the Office 365 tenant, as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="e7585-133">您可以使用單一帳戶, 在這兩個環境中都有許可權, 或者您可以在內部部署的商務用 Skype Server Management Shell 視窗中, 使用`-Credential`參數指定 Office 365 的認證。具有必要的 Office 365 系統管理角色的帳戶。</span><span class="sxs-lookup"><span data-stu-id="e7585-133">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="e7585-134">若要使用移動 Move-csuser 將使用者移至 [僅限團隊] 模式:</span><span class="sxs-lookup"><span data-stu-id="e7585-134">To move a user to Teams Only mode using Move-CsUser:</span></span>

- <span data-ttu-id="e7585-135">使用`Identity`參數指定要移動的使用者。</span><span class="sxs-lookup"><span data-stu-id="e7585-135">Specify the user to move using the `Identity` parameter.</span></span>
- <span data-ttu-id="e7585-136">指定-Target 參數, 其值為 "sipfed. lync。<span>com "。</span><span class="sxs-lookup"><span data-stu-id="e7585-136">Specify the     -Target     parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="e7585-137">指定`MoveToTeams`開關。</span><span class="sxs-lookup"><span data-stu-id="e7585-137">Specify the `MoveToTeams` switch.</span></span>
- <span data-ttu-id="e7585-138">如果您沒有一個帳戶在內部部署和 Office 365 中都有足夠的許可權, 請使用`-credential`參數, 在 Office 365 中提供擁有足夠許可權的帳戶。</span><span class="sxs-lookup"><span data-stu-id="e7585-138">If you do not have one account with sufficient permissions in both on premises and Office 365, use the `-credential` parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="e7585-139">如果 Office 365 中具有許可權的帳戶不是以 "on." 結尾。<span>com ", 您必須使用正確`-HostedMigrationOverrideUrl`的值來指定參數, 如[所需的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。</span><span class="sxs-lookup"><span data-stu-id="e7585-139">If the account with permissions in Office 365 does not end in “on.microsoft.<span>com”, you must specify the `-HostedMigrationOverrideUrl` parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="e7585-140">下列 Cmdlet 序列可用來將使用者移至 TeamsOnly, 並假設 Office 365 認證是獨立的帳戶, 並提供取得認證提示的輸入。</span><span class="sxs-lookup"><span data-stu-id="e7585-140">The following cmdlet sequence can be used to move a user to TeamsOnly, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

    ```
    $cred=Get-Credential
    $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
    ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a><span data-ttu-id="e7585-141">使用商務用 Skype Server 的 [控制台] 移至 [小組]</span><span class="sxs-lookup"><span data-stu-id="e7585-141">Move to Teams using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e7585-142">開啟商務用 Skype Server 的 [控制台] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="e7585-142">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="e7585-143">在左側導覽中, 選擇 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="e7585-143">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="e7585-144">使用 [**尋找**], 找出您想要移至團隊的使用者。</span><span class="sxs-lookup"><span data-stu-id="e7585-144">Use **Find** to locate the user(s) you would like to move to Teams.</span></span>
4. <span data-ttu-id="e7585-145">選取使用者, 然後從清單上方的 [**動作**] 下拉式清單中, 選擇 [**將選取的使用者移至團隊**]。</span><span class="sxs-lookup"><span data-stu-id="e7585-145">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Teams**.</span></span>
5. <span data-ttu-id="e7585-146">在嚮導中, 按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e7585-146">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="e7585-147">如果出現提示, 請以 onmicrosoft.com 結尾的帳戶登入 Office 365, 且具有足夠的許可權。</span><span class="sxs-lookup"><span data-stu-id="e7585-147">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="e7585-148">按一下 **[下一步**], 然後再按一次, 以移動使用者。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e7585-148">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="e7585-149">請注意, 關於成功或失敗的狀態訊息是在主要控制台 app 的頂端提供, 而不是在嚮導中。</span><span class="sxs-lookup"><span data-stu-id="e7585-149">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a><span data-ttu-id="e7585-150">向小組通知您的商務用 Skype 內部部署使用者</span><span class="sxs-lookup"><span data-stu-id="e7585-150">Notify your Skype for Business on-premises users of the upcoming move to Teams</span></span>

<span data-ttu-id="e7585-151">商務用 Skype Server 2015 的內部部署系統管理工具使用 CU8, 以及商務用 Skype Server 2019, 讓您向小組通知內部部署的商務用 Skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="e7585-151">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to notify on-premises Skype for Business users of their upcoming move to Teams.</span></span> <span data-ttu-id="e7585-152">當您啟用這些通知時, 使用者將會在其商務用 Skype 用戶端 (Win32、Mac、web 和 mobile) 中看到通知, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="e7585-152">When you enable these notifications, users will see a notification in their Skype for Business client (Win32, Mac, web, and mobile) as shown below.</span></span> <span data-ttu-id="e7585-153">如果使用者按一下 [**試用**] 按鈕, 則團隊用戶端會在已安裝時啟動;否則, 使用者會在其瀏覽器中流覽至團隊的網頁版本。</span><span class="sxs-lookup"><span data-stu-id="e7585-153">If users click the **Try it** button, the Teams client will be launched if it is installed; otherwise, users will be navigated to the web version of Teams in their browser.</span></span> <span data-ttu-id="e7585-154">根據預設, 當啟用通知時, Win32 商務用 Skype 用戶端會以無訊息方式下載團隊用戶端, 以便在將使用者移至 [僅限團隊] 模式之前提供豐富的用戶端。不過, 您也可以停用這種行為。</span><span class="sxs-lookup"><span data-stu-id="e7585-154">By default, when notifications are enabled, Win32 Skype for Business clients silently download the Teams client so that the rich client is available prior to moving the user to Teams Only mode; however, you can also disable this behavior.</span></span>  <span data-ttu-id="e7585-155">通知是使用內部部署版本進行設定`TeamsUpgradePolicy`, 而 Win32 用戶端的無提示下載則是透過內部部署`TeamsUpgradeConfiguration` Cmdlet 來控制。</span><span class="sxs-lookup"><span data-stu-id="e7585-155">Notifications are configured using the on-premises version of `TeamsUpgradePolicy`, and silent download for Win32 clients is controlled via the on-premises `TeamsUpgradeConfiguration` cmdlet.</span></span>

> [!TIP]
> <span data-ttu-id="e7585-156">部分伺服器可能需要重新開機, 才能在商務用 Skype 2015 中使用 CU8。</span><span class="sxs-lookup"><span data-stu-id="e7585-156">Some servers may need to reboot for this to work in Skype for Business 2015 with CU8.</span></span>

![即將到來的移至團隊的通知](../media/teams-upgrade-notification.png)

<span data-ttu-id="e7585-158">若要通知內部部署使用者即將升級至團隊, 請使用 NotifySfBUsers = true 建立新的 TeamsUpgradePolicy 實例。</span><span class="sxs-lookup"><span data-stu-id="e7585-158">To notify on-premises users that they will soon be upgraded to Teams, create a new instance of TeamsUpgradePolicy with NotifySfBUsers=true.</span></span> <span data-ttu-id="e7585-159">然後, 將該原則指派給您要通知的使用者, 方法是將原則直接指派給使用者, 或在 [網站]、[池] 或 [全域] 層級設定原則。</span><span class="sxs-lookup"><span data-stu-id="e7585-159">Then assign that policy to the users who you want to notify, either by assigning the policy directly to the user or by setting the policy at the site, pool, or global level.</span></span> <span data-ttu-id="e7585-160">下列 Cmdlet 會建立並授與使用者層級原則:</span><span class="sxs-lookup"><span data-stu-id="e7585-160">The following cmdlets create and grant a user-level policy:</span></span>

```
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

<span data-ttu-id="e7585-161">透過商務用 Skype Win32 用戶端自動下載團隊是透過使用 DownloadTeams 參數的內部部署 TeamsUpgradeConfiguration Cmdlet 來控制。</span><span class="sxs-lookup"><span data-stu-id="e7585-161">Automatic download of Teams via the Skype for Business Win32 client is controlled via the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="e7585-162">您可以在全域、網站和池層級建立此設定。</span><span class="sxs-lookup"><span data-stu-id="e7585-162">You create this configuration on a global, site, and pool level.</span></span> <span data-ttu-id="e7585-163">例如, 下列命令會為 site Redmond1 建立配置:</span><span class="sxs-lookup"><span data-stu-id="e7585-163">For example, the following command creates the configuration for the site Redmond1:</span></span>

`New-CsTeamsUpgradeConfiguration -Identity “site:redmond1”`

<span data-ttu-id="e7585-164">根據預設, DownloadTeams 的值為 True;不過, 只有指定使用者的 NotifySfbUser = True 時,*才能*使用此選項。</span><span class="sxs-lookup"><span data-stu-id="e7585-164">By default, the value of DownloadTeams is True; however, it is *only* honored if NotifySfbUser = True for a given user.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7585-165">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e7585-165">See also</span></span>

[<span data-ttu-id="e7585-166">移動流覽 Move-csuser</span><span class="sxs-lookup"><span data-stu-id="e7585-166">Move-CsUser</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)

[<span data-ttu-id="e7585-167">授與 CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="e7585-167">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy
)

[<span data-ttu-id="e7585-168">與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南</span><span class="sxs-lookup"><span data-stu-id="e7585-168">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="e7585-169">在商務用 Skype 中共存</span><span class="sxs-lookup"><span data-stu-id="e7585-169">Coexistence with Skype for Business</span></span>](/microsoftteams/coexistence-chat-calls-presence)
