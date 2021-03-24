---
title: 將使用者從內部部署移動至商務用 Skype Online
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
description: 瞭解如何將使用者移至商務用 Skype Online。
ms.openlocfilehash: 4d74cdebc5477d0204f69b64c2c05a4435212b3f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110619"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="b44f7-103">將使用者從內部部署移動至商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="b44f7-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="b44f7-104">在您將使用者從內部部署移至商務用 Skype Online 後，使用者會與商務用 Skype Online 互動以取得其功能。</span><span class="sxs-lookup"><span data-stu-id="b44f7-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="b44f7-105">您可以在商務用 Skype Online 中使用任何存在於內部部署的連絡人，而且任何已組織未來組織之使用者的現有會議，都將會更新，讓連結指向商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="b44f7-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="b44f7-106">如果使用者已啟用音訊會議，則會議也會包含撥入座標。</span><span class="sxs-lookup"><span data-stu-id="b44f7-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="b44f7-107">若要將內部部署環境中的使用者移至商務用 Skype Online，請使用 Move-CsUser Cmdlet 或商務用 Skype Server 控制台，這兩者都是內部部署工具。</span><span class="sxs-lookup"><span data-stu-id="b44f7-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="b44f7-108">移動任何使用者之前，請務必先檢查 [必要條件](move-users-between-on-premises-and-cloud.md#prerequisites) ，將使用者移至雲端。</span><span class="sxs-lookup"><span data-stu-id="b44f7-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="b44f7-109">使用 Move-CsUser 移動使用者</span><span class="sxs-lookup"><span data-stu-id="b44f7-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="b44f7-110">您可以從內部部署商務用 Skype 管理命令介面 PowerShell] 視窗中取得 Move-CsUser。</span><span class="sxs-lookup"><span data-stu-id="b44f7-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="b44f7-111">您必須在內部部署環境和 Microsoft 365/Office 365 組織中具備足夠的許可權，如 [必要的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)所述。</span><span class="sxs-lookup"><span data-stu-id="b44f7-111">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365/Office 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="b44f7-112">您可以在兩個環境中使用具有許可權的單一帳戶，也可以使用內部部署認證來啟動內部部署商務用 Skype Server 管理命令介面視窗，並使用 `-Credential` 參數來指定使用必要系統管理角色之 Microsoft 365 或 Office 365 帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="b44f7-112">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="b44f7-113">若要使用 Move-CsUser 將使用者移至線上：</span><span class="sxs-lookup"><span data-stu-id="b44f7-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="b44f7-114">使用 Identity 參數指定要移動的使用者。</span><span class="sxs-lookup"><span data-stu-id="b44f7-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="b44f7-115">指定-Target 參數的值為 "sipfed <span> "。com "。</span><span class="sxs-lookup"><span data-stu-id="b44f7-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="b44f7-116">如果您在內部部署和 Office 365 中沒有一個具有足夠許可權的帳戶，請使用-credential 參數，在 Office 365 中提供具有足夠許可權的帳戶。</span><span class="sxs-lookup"><span data-stu-id="b44f7-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="b44f7-117">若具有 Office 365 許可權的帳戶不是以 ". name.onmicrosoft.com17" 結尾。 <span>com "，則您必須指定-HostedMigrationOverrideUrl 參數，並在 [必要的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述的值正確。</span><span class="sxs-lookup"><span data-stu-id="b44f7-117">If the account with permissions in Office 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="b44f7-118">您可以使用下列 Cmdlet 順序，將使用者移至商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="b44f7-118">The following cmdlet sequence can be used to move a user to Skype for Business Online.</span></span> <span data-ttu-id="b44f7-119">它假設 Microsoft 365 或 Office 365 身分憑證是個別的帳戶，並以 Get-Credential 提示的輸入提供。</span><span class="sxs-lookup"><span data-stu-id="b44f7-119">It assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="b44f7-120">如果系統管理員帳戶為 MFA (Multi-Factor 驗證) 啟用，請勿指定-Credential 參數。</span><span class="sxs-lookup"><span data-stu-id="b44f7-120">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="b44f7-121">系統會提示系統管理員輸入認證。</span><span class="sxs-lookup"><span data-stu-id="b44f7-121">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="b44f7-122">使用商務用 Skype Server 控制台移動使用者</span><span class="sxs-lookup"><span data-stu-id="b44f7-122">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="b44f7-123">開啟商務用 Skype Server [控制台] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="b44f7-123">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="b44f7-124">在左側導覽中，選擇 [ **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="b44f7-124">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="b44f7-125">使用 [ **尋找** ] 來找出使用者 (s) 您想要移至商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="b44f7-125">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="b44f7-126">選取 [使用者 (s) ]，然後從清單上方的 [ **動作** ] 下拉式清單中，選擇 [ **將選取的使用者移至商務用 Skype Online**]。</span><span class="sxs-lookup"><span data-stu-id="b44f7-126">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="b44f7-127">在精靈中，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b44f7-127">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="b44f7-128">如果出現提示，請以 onmicrosoft.com 結尾的帳戶登入 Microsoft 365 或 Office 365，具有足夠的許可權。</span><span class="sxs-lookup"><span data-stu-id="b44f7-128">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="b44f7-129">按 **[下一步** **]，然後再一** 次移動使用者。</span><span class="sxs-lookup"><span data-stu-id="b44f7-129">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="b44f7-130">請注意，關於成功或失敗的狀態訊息是在主要控制台應用程式的頂端，而不是在嚮導中提供。</span><span class="sxs-lookup"><span data-stu-id="b44f7-130">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="b44f7-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b44f7-131">See also</span></span>

[<span data-ttu-id="b44f7-132">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="b44f7-132">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)