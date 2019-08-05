---
title: 將使用者從內部部署移至商務用 Skype Online
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
description: 瞭解如何將使用者移至商務用 Skype Online。
ms.openlocfilehash: 90d225eb725690566f23b73b3626cbcf1f42c8c7
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/22/2019
ms.locfileid: "36185518"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="e5121-103">將使用者從內部部署移至商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="e5121-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="e5121-104">在您將使用者從內部部署移至商務用 Skype Online 之後, 使用者就能與商務用 Skype Online 互動以取得其功能。</span><span class="sxs-lookup"><span data-stu-id="e5121-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="e5121-105">您可以在商務用 Skype Online 中使用內部部署的任何連絡人, 以及針對未來所組織的任何現有會議進行更新, 讓連結指向商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="e5121-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="e5121-106">如果使用者已啟用音訊會議, 會議也會包含撥入座標。</span><span class="sxs-lookup"><span data-stu-id="e5121-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="e5121-107">若要將使用者從內部部署環境移至商務用 Skype Online, 請使用 Move-csuser Cmdlet 或商務用 Skype Server 控制台, 這兩者都是內部部署工具。</span><span class="sxs-lookup"><span data-stu-id="e5121-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="e5121-108">在移動任何使用者之前, 請務必先檢查[先決條件](move-users-between-on-premises-and-cloud.md#prerequisites), 才能將使用者移至雲端。</span><span class="sxs-lookup"><span data-stu-id="e5121-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="e5121-109">移動 Move-csuser 的使用者</span><span class="sxs-lookup"><span data-stu-id="e5121-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="e5121-110">您可以從內部部署商務用 Skype Management Shell PowerShell 視窗中取得 Move-csuser。</span><span class="sxs-lookup"><span data-stu-id="e5121-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="e5121-111">您在內部部署環境以及 Office 365 租使用者中都必須具備足夠的許可權, 如[所需的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。</span><span class="sxs-lookup"><span data-stu-id="e5121-111">You must have sufficient privileges in both the on-premises environment as well as in the Office 365 tenant as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="e5121-112">您可以使用單一帳戶, 在這兩個環境中都有許可權, 或者您可以在內部部署的商務用 Skype Server Management Shell 視窗中使用內部部署認證, 並使用`-Credential`參數來指定 Office 365 的認證。具有必要的 Office 365 系統管理角色的帳戶。</span><span class="sxs-lookup"><span data-stu-id="e5121-112">You can either use a single account that has privileges in both environments, or you can start an on-premise Skype for Business Server Management Shell window with on-premise credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="e5121-113">若要使用移動流覽 Move-csuser 將使用者移至線上:</span><span class="sxs-lookup"><span data-stu-id="e5121-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="e5121-114">使用身分識別參數指定要移動的使用者。</span><span class="sxs-lookup"><span data-stu-id="e5121-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="e5121-115">指定-Target 參數, 其值為 "sipfed. lync。<span>com "。</span><span class="sxs-lookup"><span data-stu-id="e5121-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="e5121-116">如果您沒有一個帳戶在內部部署和 Office 365 中都有足夠的許可權, 請使用-credential 參數, 在 Office 365 中提供具有足夠許可權的帳戶。</span><span class="sxs-lookup"><span data-stu-id="e5121-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="e5121-117">如果 Office 365 中具有許可權的帳戶不是以 "on." 結尾。<span>com ", 則您必須指定-HostedMigrationOverrideUrl 參數, 並在[所需的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中描述正確的值。</span><span class="sxs-lookup"><span data-stu-id="e5121-117">If the account with permissions in Office 365 does not end in “on.microsoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

 > [!NOTE]
 > <span data-ttu-id="e5121-118">您必須為租使用者判斷正確的 HostedMigrationOverrideUrl 值。</span><span class="sxs-lookup"><span data-stu-id="e5121-118">You must determine the correct HostedMigrationOverrideUrl value for your tenant.</span></span> <span data-ttu-id="e5121-119">您可以流覽到舊版商務用 Skype 系統管理中心來輕鬆地完成此動作。</span><span class="sxs-lookup"><span data-stu-id="e5121-119">this can be easily done by navigating to the Legacy Skype for Business admin center.</span></span> <span data-ttu-id="e5121-120">決定首碼-XXXXXXX.online.lync.com 和 append/HostedMigration/hostedmigrationservice.svc。</span><span class="sxs-lookup"><span data-stu-id="e5121-120">determine the prefix - XXXXXXX.online.lync.com and append /HostedMigration/hostedmigrationservice.svc.</span></span> <span data-ttu-id="e5121-121">例如: https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc一旦您識別出該值, 就會將它用於 $url 變數, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="e5121-121">for example: https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc Once you identified the value, use it for the $url variable as shown below.</span></span>

<span data-ttu-id="e5121-122">下列 Cmdlet 序列可用來將使用者移至商務用 Skype Online, 並假設 Office 365 認證是獨立的帳戶, 並提供取得認證提示的輸入。</span><span class="sxs-lookup"><span data-stu-id="e5121-122">The following cmdlet sequence can be used to move a user to Skype for Business Online, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="e5121-123">如果系統管理員帳戶已啟用 MFA (多重要素驗證), 請勿指定-Credential 參數。</span><span class="sxs-lookup"><span data-stu-id="e5121-123">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="e5121-124">系統會提示系統管理員輸入認證。</span><span class="sxs-lookup"><span data-stu-id="e5121-124">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="e5121-125">在商務用 Skype Server 的 [控制台] 中移動使用者</span><span class="sxs-lookup"><span data-stu-id="e5121-125">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="e5121-126">開啟商務用 Skype Server 的 [控制台] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="e5121-126">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="e5121-127">在左側導覽中, 選擇 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="e5121-127">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="e5121-128">使用 [**尋找**], 找出您想要移至商務用 Skype Online 的使用者。</span><span class="sxs-lookup"><span data-stu-id="e5121-128">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="e5121-129">選取使用者, 然後從清單上方的 [**動作**] 下拉式清單中, 選擇 [**將選取的使用者移至商務用 Skype Online**]。</span><span class="sxs-lookup"><span data-stu-id="e5121-129">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="e5121-130">在嚮導中, 按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e5121-130">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="e5121-131">如果出現提示, 請以 onmicrosoft.com 結尾的帳戶登入 Office 365, 且具有足夠的許可權。</span><span class="sxs-lookup"><span data-stu-id="e5121-131">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="e5121-132">按一下 **[下一步**], 然後再按一次, 以移動使用者。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e5121-132">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="e5121-133">請注意, 關於成功或失敗的狀態訊息是在主要控制台 app 的頂端提供, 而不是在嚮導中。</span><span class="sxs-lookup"><span data-stu-id="e5121-133">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5121-134">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e5121-134">See also</span></span>

[<span data-ttu-id="e5121-135">移動流覽 Move-csuser</span><span class="sxs-lookup"><span data-stu-id="e5121-135">Move-CsUser</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)
