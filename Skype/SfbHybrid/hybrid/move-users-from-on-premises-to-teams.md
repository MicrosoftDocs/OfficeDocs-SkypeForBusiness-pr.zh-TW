---
title: 將使用者從商務用 Skype Server 2019 移至團隊
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
description: 摘要：瞭解如何遷移使用者設定，以及將使用者移至團隊。
ms.openlocfilehash: 07d0657017d24acbbd3961c3528056debb927a5a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779679"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="54e70-103">將使用者從內部部署移動至 Teams</span><span class="sxs-lookup"><span data-stu-id="54e70-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="54e70-104">當使用者從內部部署移至團隊時，使用者的商務用 Skype 首頁會從內部部署移至線上，且會為使用者指派 TeamsUpgradePolicy with mode = TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="54e70-104">When a user is moved from on premises to Teams Only, the user’s Skype for Business home is moved from on premises to online and the user is assigned TeamsUpgradePolicy with mode=TeamsOnly.</span></span>  <span data-ttu-id="54e70-105">使用者從內部部署移至 TeamsOnly 模式後：</span><span class="sxs-lookup"><span data-stu-id="54e70-105">After a user is moved from on-premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="54e70-106">所有來自其他使用者的來電和聊天（不論是從商務用 Skype 或小組傳送）都會在使用者的團隊用戶端中土地。</span><span class="sxs-lookup"><span data-stu-id="54e70-106">All incoming calls and chats from other users (whether sent from Skype for Business or Teams), will land in the user’s Teams client.</span></span>
- <span data-ttu-id="54e70-107">使用者將能夠與使用商務用 Skype 的其他使用者互動（不論是線上或內部部署）。</span><span class="sxs-lookup"><span data-stu-id="54e70-107">The user will be able to interoperate with other users who use Skype for Business (whether online or on premises).</span></span>
- <span data-ttu-id="54e70-108">使用者將能夠與同盟組織中的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="54e70-108">The user will be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="54e70-109">由該使用者排程的新會議為小組會議。</span><span class="sxs-lookup"><span data-stu-id="54e70-109">New meetings scheduled by that user are Teams meetings.</span></span>
- <span data-ttu-id="54e70-110">使用者仍可加入任何商務用 Skype 會議。</span><span class="sxs-lookup"><span data-stu-id="54e70-110">User can still join any Skype for Business meetings.</span></span>
- <span data-ttu-id="54e70-111">預定未來的使用者預先存在的會議會從內部部署遷移至團隊。</span><span class="sxs-lookup"><span data-stu-id="54e70-111">The user’s pre-existing meetings scheduled for the future will be migrated from on-premises to Teams.</span></span>
- <span data-ttu-id="54e70-112">在使用者第一次登入之後，就可以在內部部署的連絡人。</span><span class="sxs-lookup"><span data-stu-id="54e70-112">Contacts that existed on premises are available in Teams shortly after the user logs on for the first time.</span></span>
- <span data-ttu-id="54e70-113">使用者無法從商務用 Skype 發起通話或交談，也不能在商務用 Skype 中排程新的會議。</span><span class="sxs-lookup"><span data-stu-id="54e70-113">Users cannot initiate calls or chats from Skype for Business, nor can they schedule new meetings in Skype for Business.</span></span> <span data-ttu-id="54e70-114">如果他們嘗試開啟商務用 Skype 用戶端，他們將會重新導向為使用小組，如下所示。</span><span class="sxs-lookup"><span data-stu-id="54e70-114">If they attempt to open the Skype for Business client, they will be redirected to use Teams as shown below.</span></span> <span data-ttu-id="54e70-115">若未安裝團隊用戶端，將會使用瀏覽器將其導向至小組的 web 版本。</span><span class="sxs-lookup"><span data-stu-id="54e70-115">If the Teams client is not installed, they will be directed to the web version of Teams using their browser.</span></span><br><br>
    <span data-ttu-id="54e70-116">![將使用者重新導向至小組的郵件](../media/go-to-teams-page.png)</span><span class="sxs-lookup"><span data-stu-id="54e70-116">![Message redirecting a user to Teams](../media/go-to-teams-page.png)</span></span>

<span data-ttu-id="54e70-117">移動任何使用者之前，請務必先檢查[必要條件](move-users-between-on-premises-and-cloud.md#prerequisites)，將使用者移至雲端。</span><span class="sxs-lookup"><span data-stu-id="54e70-117">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span> <span data-ttu-id="54e70-118">此外，請務必查看[使用團隊搭配商務用 Skype 的組織遷移和互通性指導](/microsoftteams/migration-interop-guidance-for-teams-with-skype)方針。</span><span class="sxs-lookup"><span data-stu-id="54e70-118">Also be sure to review [Migration and interoperability guidance for organizations using Teams together with Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>


> [!NOTE]
> <span data-ttu-id="54e70-119">應停用部署 SfB 帳戶的整合連絡人存放區，以將連絡人移至小組。</span><span class="sxs-lookup"><span data-stu-id="54e70-119">Unified Contact Store should be disabled on the on-prem SfB account for the contact to be moved to Teams.</span></span>


<span data-ttu-id="54e70-120">有兩種方法可以將使用者從內部部署移至小組：</span><span class="sxs-lookup"><span data-stu-id="54e70-120">There are two methods to move a user from on premises to Teams:</span></span>

- <span data-ttu-id="54e70-121">如果您使用的是商務用 Skype Server 2015 CU8 之前的版本，移動需要兩個步驟（如有需要，可以將其腳本編寫成單一步驟）：</span><span class="sxs-lookup"><span data-stu-id="54e70-121">If you are using a version earlier than Skype for Business Server 2015 CU8, the move requires two steps (which can be scripted to be done together as a single step, if desired):</span></span>
  - <span data-ttu-id="54e70-122">[將使用者從商務用 Skype 伺服器（內部部署）移至商務用 Skype Online](move-users-from-on-premises-to-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="54e70-122">[Move the user from Skype for Business Server (on premises) to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span></span>
  - <span data-ttu-id="54e70-123">一旦使用者位於商務用 Skype Online 中，請將使用者 TeamsUpgradePolicy 指派為 mode = TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="54e70-123">Once the user is homed in Skype for Business Online, assign the user TeamsUpgradePolicy with mode= TeamsOnly.</span></span> <span data-ttu-id="54e70-124">若要授與 TeamsOnly 模式，請從商務用 Skype Online PowerShell 視窗執行下列 Cmdlet：`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span><span class="sxs-lookup"><span data-stu-id="54e70-124">To grant TeamsOnly mode, run the following cmdlet from a Skype for Business Online PowerShell window: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span></span>
- <span data-ttu-id="54e70-125">如果您有來自商務用 Skype Server 2015 的系統管理工具 CU8 或更新版本，您可以使用以上的方法，也可以使用下列所述的一個步驟進行移動。</span><span class="sxs-lookup"><span data-stu-id="54e70-125">If you have admin tools from Skype for Business Server 2015 CU8 or later, you can use the method above, or you can do this move in one step as described below.</span></span> <span data-ttu-id="54e70-126">此外，您可以選擇性地在商務用 Skype 用戶端中提供通知，然後再將其移至小組，並選擇性地讓商務用 Skype 用戶端自行下載團隊用戶端。</span><span class="sxs-lookup"><span data-stu-id="54e70-126">In addition, you can optionally provide a notification within the Skype for Business client prior to moving them to Teams Only as well as optionally have the Teams client silently downloaded by the Skype for Business client.</span></span>

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="54e70-127">僅在內部部署至小組，直接從商務用 Skype 移動使用者</span><span class="sxs-lookup"><span data-stu-id="54e70-127">Move a user directly from Skype for Business on premises to Teams Only</span></span>

<span data-ttu-id="54e70-128">在商務用 Skype 2015 Server 中的內部部署系統管理工具（含 CU8）和商務用 Skype Server 2019，可讓您在單一步驟中使用 PowerShell 或商務用 Skype Server [控制台] 中的 Move-CsUser Cmdlet，將使用者移至 [僅限團隊模式] 模式，如下所述。</span><span class="sxs-lookup"><span data-stu-id="54e70-128">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to move users from on premises to Teams Only mode in a single step using either the Move-CsUser cmdlet in PowerShell or the Skype for Business Server Control Panel, as described below.</span></span>

### <a name="move-to-teams-using-move-csuser"></a><span data-ttu-id="54e70-129">移至使用 Move-CsUser 的小組</span><span class="sxs-lookup"><span data-stu-id="54e70-129">Move to Teams using Move-CsUser</span></span>

<span data-ttu-id="54e70-130">您可以從內部部署商務用 Skype 管理命令介面 PowerShell] 視窗中取得 Move-CsUser。</span><span class="sxs-lookup"><span data-stu-id="54e70-130">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="54e70-131">下列步驟和所需的許可權與將使用者移至商務用 Skype Online 的方式相同，唯一不同的是，您也必須指定 MoveToTeams 參數，而且您必須確認使用者已被授與「小組」的授權（以及商務用 Skype Online）。</span><span class="sxs-lookup"><span data-stu-id="54e70-131">The steps below and permissions required are the same as moving a user to Skype for Business Online, except that you must also specify the MoveToTeams switch and you must ensure that the user has also been granted a license for Teams (in addition to Skype for Business Online).</span></span>

<span data-ttu-id="54e70-132">在內部部署環境和 Office 365 組織中，您必須具有足夠的許可權，如[必要的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)所述。</span><span class="sxs-lookup"><span data-stu-id="54e70-132">You must have sufficient privileges in both the on-premises environment and the Office 365 organization, as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="54e70-133">您可以在兩個環境中使用具有許可權的單一帳戶，也可以使用內部部署認證來啟動內部部署商務用 Skype Server 管理命令介面視窗，並使用此`-Credential`參數指定 office 365 帳戶的認證，其必要的 office 365 系統管理角色。</span><span class="sxs-lookup"><span data-stu-id="54e70-133">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="54e70-134">若要使用 Move-CsUser 將使用者移至僅限小組模式：</span><span class="sxs-lookup"><span data-stu-id="54e70-134">To move a user to Teams Only mode using Move-CsUser:</span></span>

- <span data-ttu-id="54e70-135">使用`Identity`參數指定要移動的使用者。</span><span class="sxs-lookup"><span data-stu-id="54e70-135">Specify the user to move using the `Identity` parameter.</span></span>
- <span data-ttu-id="54e70-136">指定-Target 參數的值為 "sipfed"。<span>com "。</span><span class="sxs-lookup"><span data-stu-id="54e70-136">Specify the     -Target     parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="54e70-137">指定`MoveToTeams`參數。</span><span class="sxs-lookup"><span data-stu-id="54e70-137">Specify the `MoveToTeams` switch.</span></span>
- <span data-ttu-id="54e70-138">如果您在內部部署和 Office 365 中沒有一個具有足夠許可權的帳戶，請使用`-credential`參數提供 Office 365 中具有足夠許可權的帳戶。</span><span class="sxs-lookup"><span data-stu-id="54e70-138">If you do not have one account with sufficient permissions in both on premises and Office 365, use the `-credential` parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="54e70-139">若具有 Office 365 許可權的帳戶不是以「name.onmicrosoft.com17」結尾。<span>com "，您必須指定`-HostedMigrationOverrideUrl`參數，並在必要的[管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述的值正確。</span><span class="sxs-lookup"><span data-stu-id="54e70-139">If the account with permissions in Office 365 does not end in “onmicrosoft.<span>com”, you must specify the `-HostedMigrationOverrideUrl` parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="54e70-140">下列指令程式順序可用來將使用者移至 TeamsOnly，並假設 Office 365 身分憑證是個別的帳戶，並以 Get-Credential 提示的輸入提供。</span><span class="sxs-lookup"><span data-stu-id="54e70-140">The following cmdlet sequence can be used to move a user to TeamsOnly, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a><span data-ttu-id="54e70-141">移至使用商務用 Skype Server 的小組控制台</span><span class="sxs-lookup"><span data-stu-id="54e70-141">Move to Teams using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="54e70-142">開啟商務用 Skype Server [控制台] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="54e70-142">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="54e70-143">在左側導覽中，選擇 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="54e70-143">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="54e70-144">使用 [**尋找**] 來找出您想要移至小組的使用者。</span><span class="sxs-lookup"><span data-stu-id="54e70-144">Use **Find** to locate the user(s) you would like to move to Teams.</span></span>
4. <span data-ttu-id="54e70-145">選取使用者，然後從清單上方的 [**動作**] 下拉式清單中，選擇 [**將選取的使用者移至小組**]。</span><span class="sxs-lookup"><span data-stu-id="54e70-145">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Teams**.</span></span>
5. <span data-ttu-id="54e70-146">在精靈中，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="54e70-146">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="54e70-147">如果出現提示，請以 onmicrosoft.com 結尾的帳戶登入 Office 365，具有足夠的許可權。</span><span class="sxs-lookup"><span data-stu-id="54e70-147">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="54e70-148">按 **[下一步** **]，然後再一**次移動使用者。</span><span class="sxs-lookup"><span data-stu-id="54e70-148">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="54e70-149">請注意，關於成功或失敗的狀態訊息是在主要控制台應用程式的頂端，而不是在嚮導中提供。</span><span class="sxs-lookup"><span data-stu-id="54e70-149">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a><span data-ttu-id="54e70-150">通知您的商務用 Skype 內部部署使用者即將進行的移動到團隊</span><span class="sxs-lookup"><span data-stu-id="54e70-150">Notify your Skype for Business on-premises users of the upcoming move to Teams</span></span>

<span data-ttu-id="54e70-151">商務用 Skype Server 2015 中的內部部署系統管理工具與 CU8，以及商務用 Skype Server 2019 中的內部部署系統管理工具，可讓您通知即將進行的內部部署商務用 Skype 使用者即將進行的移動到團隊。</span><span class="sxs-lookup"><span data-stu-id="54e70-151">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to notify on-premises Skype for Business users of their upcoming move to Teams.</span></span> <span data-ttu-id="54e70-152">當您啟用這些通知時，使用者會在其商務用 Skype 用戶端（Win32、Mac、web 和行動裝置）上看到通知，如下所示。</span><span class="sxs-lookup"><span data-stu-id="54e70-152">When you enable these notifications, users will see a notification in their Skype for Business client (Win32, Mac, web, and mobile) as shown below.</span></span> <span data-ttu-id="54e70-153">如果使用者按一下 [ **Try it** ] 按鈕，將會在安裝團隊用戶端時將其啟動;否則，使用者會在其瀏覽器中流覽至小組的 web 版本。</span><span class="sxs-lookup"><span data-stu-id="54e70-153">If users click the **Try it** button, the Teams client will be launched if it is installed; otherwise, users will be navigated to the web version of Teams in their browser.</span></span> <span data-ttu-id="54e70-154">依預設，啟用通知時，Win32 商務用 Skype 用戶端無訊息地下載團隊用戶端，以便在將使用者移至僅限小組模式之前可使用豐富型用戶端;不過，您也可以停用此行為。</span><span class="sxs-lookup"><span data-stu-id="54e70-154">By default, when notifications are enabled, Win32 Skype for Business clients silently download the Teams client so that the rich client is available prior to moving the user to Teams Only mode; however, you can also disable this behavior.</span></span>  <span data-ttu-id="54e70-155">使用內部部署版本設定通知`TeamsUpgradePolicy`，且 Win32 用戶端的無訊息下載是透過內部部署`TeamsUpgradeConfiguration` Cmdlet 來控制的。</span><span class="sxs-lookup"><span data-stu-id="54e70-155">Notifications are configured using the on-premises version of `TeamsUpgradePolicy`, and silent download for Win32 clients is controlled via the on-premises `TeamsUpgradeConfiguration` cmdlet.</span></span>

> [!TIP]
> <span data-ttu-id="54e70-156">部分伺服器可能需要重新開機，以在商務用 Skype 2015 中使用 CU8。</span><span class="sxs-lookup"><span data-stu-id="54e70-156">Some servers may need to reboot for this to work in Skype for Business 2015 with CU8.</span></span>

![即將到來移至小組的通知](../media/teams-upgrade-notification.png)

<span data-ttu-id="54e70-158">若要通知內部部署使用者，他們很快就會升級為小組，使用 NotifySfBUsers = true 來建立新的 TeamsUpgradePolicy 實例。</span><span class="sxs-lookup"><span data-stu-id="54e70-158">To notify on-premises users that they will soon be upgraded to Teams, create a new instance of TeamsUpgradePolicy with NotifySfBUsers=true.</span></span> <span data-ttu-id="54e70-159">然後，您可以將原則直接指派給使用者，或透過設定網站、集區或全域層級的原則，將該原則指派給您想要通知的使用者。</span><span class="sxs-lookup"><span data-stu-id="54e70-159">Then assign that policy to the users who you want to notify, either by assigning the policy directly to the user or by setting the policy at the site, pool, or global level.</span></span> <span data-ttu-id="54e70-160">下列 Cmdlet 會建立並授與使用者層級原則：</span><span class="sxs-lookup"><span data-stu-id="54e70-160">The following cmdlets create and grant a user-level policy:</span></span>

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

<span data-ttu-id="54e70-161">透過商務用 Skype Win32 用戶端自動下載小組是透過內部部署 TeamsUpgradeConfiguration Cmdlet 搭配 DownloadTeams 參數來控制。</span><span class="sxs-lookup"><span data-stu-id="54e70-161">Automatic download of Teams via the Skype for Business Win32 client is controlled via the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="54e70-162">您可以在全域、網站及集區層級建立此設定。</span><span class="sxs-lookup"><span data-stu-id="54e70-162">You create this configuration on a global, site, and pool level.</span></span> <span data-ttu-id="54e70-163">例如，下列命令會建立網站 Redmond1 的設定：</span><span class="sxs-lookup"><span data-stu-id="54e70-163">For example, the following command creates the configuration for the site Redmond1:</span></span>

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

<span data-ttu-id="54e70-164">DownloadTeams 的值預設為 True;不過，只有在指定的使用者 NotifySfbUser = True 時，*才*會使用此參數。</span><span class="sxs-lookup"><span data-stu-id="54e70-164">By default, the value of DownloadTeams is True; however, it is *only* honored if NotifySfbUser = True for a given user.</span></span>

## <a name="see-also"></a><span data-ttu-id="54e70-165">請參閱</span><span class="sxs-lookup"><span data-stu-id="54e70-165">See also</span></span>

[<span data-ttu-id="54e70-166">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="54e70-166">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[<span data-ttu-id="54e70-167">授與 CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="54e70-167">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[<span data-ttu-id="54e70-168">搭配使用 Teams 與商務用 Skype 之組織的移轉和互通性指引</span><span class="sxs-lookup"><span data-stu-id="54e70-168">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="54e70-169">與商務用 Skype 共存</span><span class="sxs-lookup"><span data-stu-id="54e70-169">Coexistence with Skype for Business</span></span>](/microsoftteams/coexistence-chat-calls-presence)
