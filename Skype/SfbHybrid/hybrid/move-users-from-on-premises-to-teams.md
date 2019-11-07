---
title: 將使用者從 Skype for Business Server 2019 移至 Teams
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
description: 摘要： 了解如何移轉使用者設定，並將使用者移至 Teams。
ms.openlocfilehash: 0d37fc1a875763552b2b0cebbd29a0f9c7a62e8d
ms.sourcegitcommit: b9710149ad0bb321929139118b7df0bc4cca08de
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/06/2019
ms.locfileid: "38010616"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="6150b-103">將使用者從內部部署移至 Teams</span><span class="sxs-lookup"><span data-stu-id="6150b-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="6150b-104">當使用者從內部部署移至 [僅小組時，使用者的 Skype 商務首頁移從內部部署至 online 並指派給使用者 TeamsUpgradePolicy 搭配 mode = TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="6150b-104">When a user is moved from on premises to Teams Only, the user’s Skype for Business home is moved from on premises to online and the user is assigned TeamsUpgradePolicy with mode=TeamsOnly.</span></span>  <span data-ttu-id="6150b-105">之後使用者從移動內部部署到 TeamsOnly 模式：</span><span class="sxs-lookup"><span data-stu-id="6150b-105">After a user is moved from on-premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="6150b-106">所有內送呼叫和聊天室的其他使用者 （無論是從 Skype 傳送基於商業或小組），將會在使用者的 microsoft Teams 用戶端推送。</span><span class="sxs-lookup"><span data-stu-id="6150b-106">All incoming calls and chats from other users (whether sent from Skype for Business or Teams), will land in the user’s Teams client.</span></span>
- <span data-ttu-id="6150b-107">使用者將能夠與其他使用商務用 Skype （無論是線上或內部） 的使用者交互操作。</span><span class="sxs-lookup"><span data-stu-id="6150b-107">The user will be able to interoperate with other users who use Skype for Business (whether online or on premises).</span></span>
- <span data-ttu-id="6150b-108">使用者將能夠彼此通訊同盟組織中的使用者。</span><span class="sxs-lookup"><span data-stu-id="6150b-108">The user will be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="6150b-109">使用該使用者排定新會議是 Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="6150b-109">New meetings scheduled by that user are Teams meetings.</span></span>
- <span data-ttu-id="6150b-110">使用者仍然可以加入任何 Skype for Business 會議。</span><span class="sxs-lookup"><span data-stu-id="6150b-110">User can still join any Skype for Business meetings.</span></span>
- <span data-ttu-id="6150b-111">使用者的既有會議排定在未來將從內部部署移轉到小組。</span><span class="sxs-lookup"><span data-stu-id="6150b-111">The user’s pre-existing meetings scheduled for the future will be migrated from on-premises to Teams.</span></span>
- <span data-ttu-id="6150b-112">連絡人已經存在於內部部署中可用的小組使用者第一次登入之後，很快就。</span><span class="sxs-lookup"><span data-stu-id="6150b-112">Contacts that existed on premises are available in Teams shortly after the user logs on for the first time.</span></span>
- <span data-ttu-id="6150b-113">使用者無法起始通話或聊天從商務用 Skype，也可以排程商務用 Skype 中的新會議。</span><span class="sxs-lookup"><span data-stu-id="6150b-113">Users cannot initiate calls or chats from Skype for Business, nor can they schedule new meetings in Skype for Business.</span></span> <span data-ttu-id="6150b-114">如果使用者嘗試開啟 Skype 商務用戶端，系統將會重新導向至使用 Teams，如下所示。</span><span class="sxs-lookup"><span data-stu-id="6150b-114">If they attempt to open the Skype for Business client, they will be redirected to use Teams as shown below.</span></span> <span data-ttu-id="6150b-115">如果未安裝 microsoft Teams 用戶端，他們將會進入小組使用其瀏覽器網頁版。</span><span class="sxs-lookup"><span data-stu-id="6150b-115">If the Teams client is not installed, they will be directed to the web version of Teams using their browser.</span></span><br><br>
    <span data-ttu-id="6150b-116">![將使用者重新導向至 Teams 的郵件](../media/go-to-teams-page.png)</span><span class="sxs-lookup"><span data-stu-id="6150b-116">![Message redirecting a user to Teams](../media/go-to-teams-page.png)</span></span>

<span data-ttu-id="6150b-117">才可繼續任何使用者，請務必檢閱[必要條件](move-users-between-on-premises-and-cloud.md#prerequisites)，將使用者移至雲端。</span><span class="sxs-lookup"><span data-stu-id="6150b-117">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span> <span data-ttu-id="6150b-118">也請務必檢閱[移轉及組織使用 Teams 與商務用 Skype 互通性指導](/microsoftteams/migration-interop-guidance-for-teams-with-skype)。</span><span class="sxs-lookup"><span data-stu-id="6150b-118">Also be sure to review [Migration and interoperability guidance for organizations using Teams together with Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>


> [!NOTE]
> <span data-ttu-id="6150b-119">整合的連絡人存放區應該停用內部 SfB 帳戶移至 Teams 連絡人。</span><span class="sxs-lookup"><span data-stu-id="6150b-119">Unified Contact Store should be disabled on the on-prem SfB account for the contact to be moved to Teams.</span></span>


<span data-ttu-id="6150b-120">有兩種方法可以將使用者從內部部署移至小組：</span><span class="sxs-lookup"><span data-stu-id="6150b-120">There are two methods to move a user from on premises to Teams:</span></span>

- <span data-ttu-id="6150b-121">如果您使用版本早於 Skype for Business Server 2015 CU8，移動要求 （其中可以寫成指令碼完成一起以單一步驟中，若有需要） 兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="6150b-121">If you are using a version earlier than Skype for Business Server 2015 CU8, the move requires two steps (which can be scripted to be done together as a single step, if desired):</span></span>
  - <span data-ttu-id="6150b-122">[將使用者從 Skype for Business Server （內部） 商務用 skype 移動](move-users-from-on-premises-to-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="6150b-122">[Move the user from Skype for Business Server (on premises) to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span></span>
  - <span data-ttu-id="6150b-123">一旦使用者位於 skype for Business Online，指派給使用者 TeamsUpgradePolicy 模式 = TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="6150b-123">Once the user is homed in Skype for Business Online, assign the user TeamsUpgradePolicy with mode= TeamsOnly.</span></span> <span data-ttu-id="6150b-124">若要授與 TeamsOnly 模式，請執行下列指令程式從 Skype for Business Online PowerShell 視窗：`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span><span class="sxs-lookup"><span data-stu-id="6150b-124">To grant TeamsOnly mode, run the following cmdlet from a Skype for Business Online PowerShell window: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span></span>
- <span data-ttu-id="6150b-125">如果您有從 Skype for Business Server 2015 CU8 或更新版本的系統管理工具，您可以使用，與上述方法，或者您可以執行此移動一個步驟如下所示。</span><span class="sxs-lookup"><span data-stu-id="6150b-125">If you have admin tools from Skype for Business Server 2015 CU8 or later, you can use the method above, or you can do this move in one step as described below.</span></span> <span data-ttu-id="6150b-126">此外，您可以選擇性地提供商務用戶端之前將他們移至 [僅 Teams 商務用 Skype 中的通知，以及 （選用） 有 Teams 用戶端透過 Skype 商務用戶端自動下載。</span><span class="sxs-lookup"><span data-stu-id="6150b-126">In addition, you can optionally provide a notification within the Skype for Business client prior to moving them to Teams Only as well as optionally have the Teams client silently downloaded by the Skype for Business client.</span></span>

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="6150b-127">僅小組內部移動使用者直接從商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="6150b-127">Move a user directly from Skype for Business on premises to Teams Only</span></span>

<span data-ttu-id="6150b-128">在商務用 Skype Server 2015 與 CU8，以及 skype for Business Server 2019 中，內部部署系統管理工具可讓您將使用者從內部部署移至 Teams 只在單一步驟中使用 Move-csuser cmdlet，在 PowerShell 中的，或是用 Skype for Business Se 模式rver 控制台] 中，如下所示。</span><span class="sxs-lookup"><span data-stu-id="6150b-128">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to move users from on premises to Teams Only mode in a single step using either the Move-CsUser cmdlet in PowerShell or the Skype for Business Server Control Panel, as described below.</span></span>

### <a name="move-to-teams-using-move-csuser"></a><span data-ttu-id="6150b-129">移至 Teams 使用 Move-csuser</span><span class="sxs-lookup"><span data-stu-id="6150b-129">Move to Teams using Move-CsUser</span></span>

<span data-ttu-id="6150b-130">Move-csuser 是來自商務 Management Shell PowerShell 視窗，內部部署商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="6150b-130">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="6150b-131">所需權限與執行下列步驟會將使用者移至 Skype for Business Online，您還必須指定 MoveToTeams 參數，而您必須確定，使用者也已授與授權 （除了商務用 Skype 的 teams 的相同Online)。</span><span class="sxs-lookup"><span data-stu-id="6150b-131">The steps below and permissions required are the same as moving a user to Skype for Business Online, except that you must also specify the MoveToTeams switch and you must ensure that the user has also been granted a license for Teams (in addition to Skype for Business Online).</span></span>

<span data-ttu-id="6150b-132">[所需的系統管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)所述，您必須具有足夠的權限，在內部部署環境和 Office 365 租用戶中。</span><span class="sxs-lookup"><span data-stu-id="6150b-132">You must have sufficient privileges in both the on-premises environment and the Office 365 tenant, as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="6150b-133">您可以使用單一帳戶的權限在這兩個環境中，或者您可以使用內部部署認證，啟動 Business Server 管理命令介面視窗內部部署商務用 Skype，並使用`-Credential`參數，以指定 Office 365 認證具有必要的 Office 365 系統管理角色的帳戶。</span><span class="sxs-lookup"><span data-stu-id="6150b-133">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="6150b-134">若要將使用者移至 Teams 只使用 Move-csuser 的模式：</span><span class="sxs-lookup"><span data-stu-id="6150b-134">To move a user to Teams Only mode using Move-CsUser:</span></span>

- <span data-ttu-id="6150b-135">指定使用者移動使用`Identity`參數。</span><span class="sxs-lookup"><span data-stu-id="6150b-135">Specify the user to move using the `Identity` parameter.</span></span>
- <span data-ttu-id="6150b-136">指定-Target 參數具有值 「 sipfed.online.lync。<span>com"。</span><span class="sxs-lookup"><span data-stu-id="6150b-136">Specify the     -Target     parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="6150b-137">指定`MoveToTeams`切換。</span><span class="sxs-lookup"><span data-stu-id="6150b-137">Specify the `MoveToTeams` switch.</span></span>
- <span data-ttu-id="6150b-138">如果您不具備一個帳戶具有足夠權限兩者在內部部署和 Office 365 中，使用`-credential`參數，以提供具有足夠的權限，在 Office 365 中的帳戶。</span><span class="sxs-lookup"><span data-stu-id="6150b-138">If you do not have one account with sufficient permissions in both on premises and Office 365, use the `-credential` parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="6150b-139">如果使用 Office 365 中的權限的帳戶未結束於 」 onmicrosoft。<span>com 」，您必須指定`-HostedMigrationOverrideUrl`具有正確的值做為[所需的系統管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)> 中所述的參數。</span><span class="sxs-lookup"><span data-stu-id="6150b-139">If the account with permissions in Office 365 does not end in “onmicrosoft.<span>com”, you must specify the `-HostedMigrationOverrideUrl` parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="6150b-140">下列指令程式順序可以用來將使用者移至 TeamsOnly，並假設的 Office 365 認證是不同的帳戶，並提供做為 Get-credential 出現提示時輸入。</span><span class="sxs-lookup"><span data-stu-id="6150b-140">The following cmdlet sequence can be used to move a user to TeamsOnly, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

    ```
    $cred=Get-Credential
    $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
    ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6150b-141">移至 Teams 使用 Skype for Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="6150b-141">Move to Teams using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="6150b-142">開啟 Skype for Business 伺服器控制項] 面板應用程式。</span><span class="sxs-lookup"><span data-stu-id="6150b-142">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="6150b-143">在左導覽中，選擇 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="6150b-143">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="6150b-144">若要找出您想要將移至小組的使用者使用 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="6150b-144">Use **Find** to locate the user(s) you would like to move to Teams.</span></span>
4. <span data-ttu-id="6150b-145">選取的使用者，然後再從清單上方的 [**動作**] 下拉式清單，選擇 [**移到 Teams 的所選的使用者**。</span><span class="sxs-lookup"><span data-stu-id="6150b-145">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Teams**.</span></span>
5. <span data-ttu-id="6150b-146">在精靈中，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6150b-146">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="6150b-147">如果出現提示，以登入 Office 365，結束於帳戶。 onmicrosoft.com 且具有足夠的權限。</span><span class="sxs-lookup"><span data-stu-id="6150b-147">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="6150b-148">按一下 [**下一步**，然後**下一步**一個更多時間來移動使用者。</span><span class="sxs-lookup"><span data-stu-id="6150b-148">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="6150b-149">請注意，在主要 [控制台] 應用程式，而不是以精靈頂端提供有關成功或失敗的狀態訊息。</span><span class="sxs-lookup"><span data-stu-id="6150b-149">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a><span data-ttu-id="6150b-150">通知您 Skype for Business 上內部部署使用者即將移動到 Teams 的</span><span class="sxs-lookup"><span data-stu-id="6150b-150">Notify your Skype for Business on-premises users of the upcoming move to Teams</span></span>

<span data-ttu-id="6150b-151">在商務用 Skype Server 2015 與 CU8，以及 skype for Business Server 2019 中，內部部署系統管理工具可讓您以通知他們即將來臨的移至 Teams 的商務使用者內部部署商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="6150b-151">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to notify on-premises Skype for Business users of their upcoming move to Teams.</span></span> <span data-ttu-id="6150b-152">當您啟用這些通知時，使用者會看到其 Skype 商務用戶端 （Win32、 Mac、 web 和行動） 中的通知，如下所示。</span><span class="sxs-lookup"><span data-stu-id="6150b-152">When you enable these notifications, users will see a notification in their Skype for Business client (Win32, Mac, web, and mobile) as shown below.</span></span> <span data-ttu-id="6150b-153">若已安裝; 如果使用者按一下 [**再**] 按鈕，將會啟動 microsoft Teams 用戶端否則，使用者會巡覽至 Teams 網頁版在其瀏覽器中。</span><span class="sxs-lookup"><span data-stu-id="6150b-153">If users click the **Try it** button, the Teams client will be launched if it is installed; otherwise, users will be navigated to the web version of Teams in their browser.</span></span> <span data-ttu-id="6150b-154">根據預設，通知啟用時，Win32 Skype for Business 的用戶端以無訊息方式下載 microsoft Teams 用戶端使豐富型用戶端可再將使用者移至只 Teams 模式;不過，您可以也停用此行為。</span><span class="sxs-lookup"><span data-stu-id="6150b-154">By default, when notifications are enabled, Win32 Skype for Business clients silently download the Teams client so that the rich client is available prior to moving the user to Teams Only mode; however, you can also disable this behavior.</span></span>  <span data-ttu-id="6150b-155">使用內部部署版的設定通知`TeamsUpgradePolicy`，Win32 用戶端的無訊息下載控制透過內部部署和`TeamsUpgradeConfiguration`指令程式。</span><span class="sxs-lookup"><span data-stu-id="6150b-155">Notifications are configured using the on-premises version of `TeamsUpgradePolicy`, and silent download for Win32 clients is controlled via the on-premises `TeamsUpgradeConfiguration` cmdlet.</span></span>

> [!TIP]
> <span data-ttu-id="6150b-156">某些伺服器可能需要重新開機，此功能在 Skype for Business 2015 CU8 中運作。</span><span class="sxs-lookup"><span data-stu-id="6150b-156">Some servers may need to reboot for this to work in Skype for Business 2015 with CU8.</span></span>

![即將移動到 Teams 的通知](../media/teams-upgrade-notification.png)

<span data-ttu-id="6150b-158">若要通知的內部使用者，他們會推出升級成小組，建立 TeamsUpgradePolicy 的新執行個體與 NotifySfBUsers = true。</span><span class="sxs-lookup"><span data-stu-id="6150b-158">To notify on-premises users that they will soon be upgraded to Teams, create a new instance of TeamsUpgradePolicy with NotifySfBUsers=true.</span></span> <span data-ttu-id="6150b-159">然後將該原則指派給您想要通知，藉由將原則指派給使用者直接或透過網站、 集區，或全域層級設定此原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="6150b-159">Then assign that policy to the users who you want to notify, either by assigning the policy directly to the user or by setting the policy at the site, pool, or global level.</span></span> <span data-ttu-id="6150b-160">下列指令程式建立，並授與使用者層級的原則：</span><span class="sxs-lookup"><span data-stu-id="6150b-160">The following cmdlets create and grant a user-level policy:</span></span>

```
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

<span data-ttu-id="6150b-161">自動下載透過 Skype 商務 Win32 用戶端的小組是透過內部部署 TeamsUpgradeConfiguration 指令程式，搭配 DownloadTeams 參數控制。</span><span class="sxs-lookup"><span data-stu-id="6150b-161">Automatic download of Teams via the Skype for Business Win32 client is controlled via the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="6150b-162">您建立此組態的全域、 網站及集區層級。</span><span class="sxs-lookup"><span data-stu-id="6150b-162">You create this configuration on a global, site, and pool level.</span></span> <span data-ttu-id="6150b-163">例如，下列命令會建立 Redmond1 網站的設定：</span><span class="sxs-lookup"><span data-stu-id="6150b-163">For example, the following command creates the configuration for the site Redmond1:</span></span>

`New-CsTeamsUpgradeConfiguration -Identity “site:redmond1”`

<span data-ttu-id="6150b-164">根據預設，DownloadTeams 的值為 True;不過，它是*只*接受如果 NotifySfbUser = True 針對指定的使用者。</span><span class="sxs-lookup"><span data-stu-id="6150b-164">By default, the value of DownloadTeams is True; however, it is *only* honored if NotifySfbUser = True for a given user.</span></span>

## <a name="see-also"></a><span data-ttu-id="6150b-165">請參閱</span><span class="sxs-lookup"><span data-stu-id="6150b-165">See also</span></span>

[<span data-ttu-id="6150b-166">Move-csuser</span><span class="sxs-lookup"><span data-stu-id="6150b-166">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[<span data-ttu-id="6150b-167">授與 CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="6150b-167">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[<span data-ttu-id="6150b-168">組織使用 Teams 與 Skype for Business 的移轉和互通性指導</span><span class="sxs-lookup"><span data-stu-id="6150b-168">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="6150b-169">商務用 Skype 共存</span><span class="sxs-lookup"><span data-stu-id="6150b-169">Coexistence with Skype for Business</span></span>](/microsoftteams/coexistence-chat-calls-presence)
