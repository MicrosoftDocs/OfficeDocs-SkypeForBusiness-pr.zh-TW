---
title: 將使用者從雲端移至內部部署
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
description: 瞭解如何將使用者從商務用 Skype Online 移至內部部署。
ms.openlocfilehash: 0add74a2480f4caed493e6e448427aa2462db714
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779669"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a><span data-ttu-id="ea234-103">將使用者從雲端移至內部部署</span><span class="sxs-lookup"><span data-stu-id="ea234-103">Move users from the cloud to on-premises</span></span> 

<span data-ttu-id="ea234-104">如有需要，您可以將先前從內部部署遷移的使用者移至雲端（不論只使用商務用 Skype Online 或小組），都可以移回內部部署。</span><span class="sxs-lookup"><span data-stu-id="ea234-104">If needed, you can move a user who was previously migrated from on-premises to the cloud (whether using Skype for Business Online or Teams Only) back to on-premises.</span></span> <span data-ttu-id="ea234-105">若要將使用者從商務用 Skype Online 或 TeamsOnly 模式移回商務用 Skype Server 的內部部署部署，請使用 Move-CsUser Cmdlet 或商務用 Skype Server 控制台，這兩者都是內部部署工具。</span><span class="sxs-lookup"><span data-stu-id="ea234-105">To move users from either Skype for Business Online or TeamsOnly mode back to an on-premises deployment of Skype for Business Server, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> <span data-ttu-id="ea234-106">當您將使用者移回內部部署時，您必須決定要將使用者移至哪一個集區。</span><span class="sxs-lookup"><span data-stu-id="ea234-106">When you move a user back to an on-premises deployment, you must decide which pool to move the user to.</span></span>

> [!Important]
> <span data-ttu-id="ea234-107">如果使用者先前處於 TeamsOnly 模式，而且您使用的是舊版商務用 Skype Server 2015 與 CU8，您也必須為該使用者移除 TeamsUpgradePolicy 的 TeamsOnly 模式指派。</span><span class="sxs-lookup"><span data-stu-id="ea234-107">If the user was previously in TeamsOnly mode, and you are using an earlier version than Skype for Business Server 2015 with CU8, then you must also remove the TeamsOnly mode assignment of TeamsUpgradePolicy for that user.</span></span> <span data-ttu-id="ea234-108">內部部署使用者不得具有 mode = TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="ea234-108">On-premises users must not have mode= TeamsOnly.</span></span>  <span data-ttu-id="ea234-109">後續版本的商務用 Skype Server 會自動移除此指派。</span><span class="sxs-lookup"><span data-stu-id="ea234-109">Subsequent versions of Skype for Business Server automatically remove this assignment.</span></span> <span data-ttu-id="ea234-110">如需詳細資訊，請參閱[授與 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)。</span><span class="sxs-lookup"><span data-stu-id="ea234-110">For more details, see [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ea234-111">必要條件</span><span class="sxs-lookup"><span data-stu-id="ea234-111">Prerequisites</span></span>

- <span data-ttu-id="ea234-112">組織必須正確設定 Azure AD Connect，並同步處理使用者的所有相關屬性，如[Configure AZURE AD Connect](configure-azure-ad-connect.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="ea234-112">The organization must have Azure AD Connect properly configured and be syncing all relevant attributes for the user, as described in [Configure Azure AD Connect](configure-azure-ad-connect.md).</span></span>
- <span data-ttu-id="ea234-113">從線上移回內部部署的使用者，必須已存在於內部部署 Active Directory 中。</span><span class="sxs-lookup"><span data-stu-id="ea234-113">The user being moved from online back to on-premises must already exist in the on-premises Active Directory.</span></span>
- <span data-ttu-id="ea234-114">必須設定商務用 skype 混合（如[設定商務用 skype 混合](configure-federation-with-skype-for-business-online.md)式中所述）。</span><span class="sxs-lookup"><span data-stu-id="ea234-114">Skype for Business hybrid must be configured, as described in [Configure Skype for Business hybrid](configure-federation-with-skype-for-business-online.md).</span></span>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="ea234-115">將使用者移回內部部署</span><span class="sxs-lookup"><span data-stu-id="ea234-115">Moving users back to on-premises</span></span>

<span data-ttu-id="ea234-116">一旦您將使用者從雲端移回內部部署：</span><span class="sxs-lookup"><span data-stu-id="ea234-116">Once you move a user from the cloud back to on-premises:</span></span>

- <span data-ttu-id="ea234-117">使用者會與您的商務用 Skype Server 部署進行互動，以進行其功能。</span><span class="sxs-lookup"><span data-stu-id="ea234-117">The user interacts with your Skype for Business Server deployment for its functionality.</span></span> 
- <span data-ttu-id="ea234-118">任何存在於商務用 Skype Online 或小組中的連絡人，都將遷移至商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="ea234-118">Any contacts that existed in either Skype for Business Online or Teams are migrated  to Skype for Business Server.</span></span> <span data-ttu-id="ea234-119">這兩組連絡人會合並，然後再遷移回內部部署。</span><span class="sxs-lookup"><span data-stu-id="ea234-119">The two sets of contacts are merged and then migrated back to on-premises.</span></span>  <span data-ttu-id="ea234-120">此外，預先存在於小組中的連絡人仍會保留在小組中。</span><span class="sxs-lookup"><span data-stu-id="ea234-120">In addition, contacts that are pre-existing in Teams remain in Teams.</span></span>
- <span data-ttu-id="ea234-121">如果使用者也使用小組，他們將無法與商務用 Skype 使用者互動，也無法與同盟組織中的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="ea234-121">If the user also uses Teams, they will not have the ability to interoperate with Skype for Business users, nor will they be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="ea234-122">商務用 Skype Online 中的會議*不*會自動遷移回內部部署。</span><span class="sxs-lookup"><span data-stu-id="ea234-122">Meetings in Skype for Business Online are *not* automatically migrated back to on-premises.</span></span> <span data-ttu-id="ea234-123">使用者應重新排定其會議，如果需要，也應使用[會議遷移工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)。</span><span class="sxs-lookup"><span data-stu-id="ea234-123">Users should either reschedule their meetings or, if desired, use the [Meeting Migration Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4).</span></span>

### <a name="move-users-with-move-csuser"></a><span data-ttu-id="ea234-124">使用 Move-CsUser 移動使用者</span><span class="sxs-lookup"><span data-stu-id="ea234-124">Move users with Move-CsUser</span></span>

<span data-ttu-id="ea234-125">您可以從內部部署商務用 Skype 管理命令介面 PowerShell] 視窗中取得 Move-CsUser。</span><span class="sxs-lookup"><span data-stu-id="ea234-125">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="ea234-126">在內部部署環境和 Office 365 組織中，您必須具有足夠的許可權，如[必要的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)所述。</span><span class="sxs-lookup"><span data-stu-id="ea234-126">You must have sufficient privileges in both the on-premises environment as well as the Office 365 organization, as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="ea234-127">您可以在兩個環境中使用具有許可權的單一帳戶，也可以使用內部部署認證來啟動內部部署商務用 Skype Server 管理命令介面視窗，並使用此`-Credential`參數指定 office 365 帳戶的認證，其必要的 office 365 系統管理角色。</span><span class="sxs-lookup"><span data-stu-id="ea234-127">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="ea234-128">若要使用 Move-CsUser 將使用者移至內部部署：</span><span class="sxs-lookup"><span data-stu-id="ea234-128">To move a user to on-premises using Move-CsUser:</span></span>

- <span data-ttu-id="ea234-129">使用 Identity 參數指定要移動的使用者。</span><span class="sxs-lookup"><span data-stu-id="ea234-129">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="ea234-130">使用要主控使用者之所需內部部署集區的完整功能變數名稱，指定-Target 參數。</span><span class="sxs-lookup"><span data-stu-id="ea234-130">Specify the -Target parameter with the fully qualified domain name of the desired on-premises pool that will host the user.</span></span>
- <span data-ttu-id="ea234-131">如果您在內部部署和 Office 365 中沒有一個具有足夠許可權的帳戶，請使用-credential 參數，在 Office 365 中提供具有足夠許可權的帳戶。</span><span class="sxs-lookup"><span data-stu-id="ea234-131">If you do not have one account with sufficient permissions in both on-premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="ea234-132">若具有 Office 365 許可權的帳戶不是以「on.microsoft.com」結尾，您必須指定-HostedMigrationOverrideUrl 參數，並在[必要的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述的值正確。</span><span class="sxs-lookup"><span data-stu-id="ea234-132">If the account with permissions in Office 365 does not end in “on.microsoft.com”, you must specify the -HostedMigrationOverrideUrl parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="ea234-133">下列 Cmdlet 順序可用來將使用者移至商務用 Skype Server，並假設 Office 365 身分憑證是個別的帳戶，並以 Get-Credential 提示的輸入提供。</span><span class="sxs-lookup"><span data-stu-id="ea234-133">The following cmdlet sequence can be used to move a user to Skype for Business Server, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a><span data-ttu-id="ea234-134">使用商務用 Skype Server 控制台移動使用者</span><span class="sxs-lookup"><span data-stu-id="ea234-134">Move users with the Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ea234-135">開啟商務用 Skype Server [控制台] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="ea234-135">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="ea234-136">在左側導覽中，選擇 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="ea234-136">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="ea234-137">使用 [**尋找**] 來找出您想要移回到內部部署的使用者。</span><span class="sxs-lookup"><span data-stu-id="ea234-137">Use **Find** to locate the user(s) you would like to move back to on-premises.</span></span>
4. <span data-ttu-id="ea234-138">選取使用者，然後從清單上方的 [**動作**] 下拉式清單中，選擇 [**將選取的使用者移至內部部署**]。</span><span class="sxs-lookup"><span data-stu-id="ea234-138">Select the user(s), and then from the **Action** dropdown above the list, choose **Move selected users to on-premises**.</span></span>
5. <span data-ttu-id="ea234-139">在嚮導中，選取將主控使用者的使用者集區，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ea234-139">In the wizard, select the user pool that will host the user and click **Next**.</span></span>
6. <span data-ttu-id="ea234-140">如果出現提示，請以 onmicrosoft.com 結尾的帳戶登入 Office 365，具有足夠的許可權。</span><span class="sxs-lookup"><span data-stu-id="ea234-140">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="ea234-141">按 **[下一步** **]，然後再一**次移動使用者。</span><span class="sxs-lookup"><span data-stu-id="ea234-141">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="ea234-142">請注意，關於成功或失敗的狀態訊息是在主要控制台應用程式的頂端，而不是在嚮導中提供。</span><span class="sxs-lookup"><span data-stu-id="ea234-142">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

### <a name="removing-teamsonly-mode"></a><span data-ttu-id="ea234-143">移除 TeamsOnly 模式</span><span class="sxs-lookup"><span data-stu-id="ea234-143">Removing TeamsOnly mode</span></span>

<span data-ttu-id="ea234-144">如果您使用的版本低於商務用 Skype 2015 與 CU8，且使用者會移回內部部署的 TeamsOnly 模式，您必須`TeamsUpgradePolicy`先移除 UpgradeToTeams 實例，然後才能移動使用者內部部署。</span><span class="sxs-lookup"><span data-stu-id="ea234-144">If you are using a version earlier than Skype for Business 2015 with CU8 and the user is being moved back to on-premises in TeamsOnly mode, you must remove the UpgradeToTeams instance of `TeamsUpgradePolicy` before you move the user on-premises.</span></span> <span data-ttu-id="ea234-145">您可以使用不同的模式明確授與原則，或只為該使用者移除現有的原則指派，以使用通用原則（只要您租使用者的全域原則不是 UpgradeToTeams）。</span><span class="sxs-lookup"><span data-stu-id="ea234-145">You can either explicitly grant a policy with a different mode or simply remove the existing policy assignment for that user to use the global policy (as long as your tenant’s global policy is not UpgradeToTeams).</span></span>

<span data-ttu-id="ea234-146">若要移除使用者的 TeamsUpgradePolicy 指派，請從商務用 Skype Online PowerShell 視窗執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ea234-146">To remove the user’s assignment of TeamsUpgradePolicy, run the following cmdlet from a Skype for Business Online PowerShell window:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

<span data-ttu-id="ea234-147">或者，若要指派另一個沒有 mode = TeamsOnly 的 TeamsUpgradePolicy 實例，您可以指定所需實例的名稱做為 Cmdlet 中 PolicyName 參數的值。</span><span class="sxs-lookup"><span data-stu-id="ea234-147">Alternatively, to assign another instance of TeamsUpgradePolicy that does not have mode=TeamsOnly, you can specify the name of the desired instance as the value of PolicyName parameter in the cmdlet.</span></span> <span data-ttu-id="ea234-148">若要查看 TeamsUpgradePolicy 的可用實例清單，請執行 CsTeamsUpgradePolicy。</span><span class="sxs-lookup"><span data-stu-id="ea234-148">To see a list of available instances of TeamsUpgradePolicy, run Get-CsTeamsUpgradePolicy.</span></span>


## <a name="see-also"></a><span data-ttu-id="ea234-149">請參閱</span><span class="sxs-lookup"><span data-stu-id="ea234-149">See also</span></span>

[<span data-ttu-id="ea234-150">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="ea234-150">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)
