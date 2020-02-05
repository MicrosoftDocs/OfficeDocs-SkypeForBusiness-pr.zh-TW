---
title: 移動使用者從內部部署商務用 skype
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
description: 了解如何將使用者移至 Skype，商務 online。
ms.openlocfilehash: 6653ca8fe7082f0cabd2057c078f7d0d8d6f0389
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726753"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="7d4c5-103">移動使用者從內部部署商務用 skype</span><span class="sxs-lookup"><span data-stu-id="7d4c5-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="7d4c5-104">移動使用者從內部部署用 skype for Business Online 之後，使用者互動與 Skype for Business Online 其功能。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="7d4c5-105">Skype for Business Online 中，將可使用任何存在於內部部署的連絡人和任何現有的會議使用者召集的未來會更新，以使連結指向商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="7d4c5-106">如果使用者已啟用音訊會議，會議也會包含電話撥入式座標。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="7d4c5-107">若要將使用者從內部部署環境移至 Skype，商務，請使用 Move-csuser cmdlet 或 Skype for Business Server Control Panel，這兩種都是內部部署工具。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="7d4c5-108">才可繼續任何使用者，請務必檢閱[必要條件](move-users-between-on-premises-and-cloud.md#prerequisites)，將使用者移至雲端。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="7d4c5-109">使用 Move-csuser 移動使用者</span><span class="sxs-lookup"><span data-stu-id="7d4c5-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="7d4c5-110">Move-csuser 是來自商務 Management Shell PowerShell 視窗，內部部署商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="7d4c5-111">[所需的系統管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)所述，您必須具有足夠的權限，這兩個內部部署環境中也如所示的 Office 365 租用戶。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-111">You must have sufficient privileges in both the on-premises environment as well as in the Office 365 tenant as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="7d4c5-112">您可以使用單一帳戶的權限在這兩個環境中，或者您可以使用內部部署認證，啟動 Business Server 管理命令介面視窗內部部署商務用 Skype，並使用`-Credential`參數，以指定必要的 Office 365 系統管理角色與 Office 365 帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-112">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="7d4c5-113">將使用者移至線上使用 Move-csuser:</span><span class="sxs-lookup"><span data-stu-id="7d4c5-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="7d4c5-114">指定使用者移動使用 Identity 參數。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="7d4c5-115">指定-Target 參數具有值 「 sipfed.online.lync。<span>com"。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="7d4c5-116">如果您不具備一個帳戶具有足夠權限兩者在內部部署和 Office 365 中，使用-credential 參數，以提供具有足夠的權限，在 Office 365 中的帳戶。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="7d4c5-117">如果使用 Office 365 中的權限的帳戶未結束於 」 on.microsoft。<span>com 」，然後如所述[所需的系統管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)，您必須使用正確的值指定-HostedMigrationOverrideUrl 參數。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-117">If the account with permissions in Office 365 does not end in “on.microsoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

 > [!NOTE]
 > <span data-ttu-id="7d4c5-118">您必須決定正確的 HostedMigrationOverrideUrl 值租用戶。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-118">You must determine the correct HostedMigrationOverrideUrl value for your tenant.</span></span> <span data-ttu-id="7d4c5-119">這可以藉由瀏覽至商務版系統管理中心舊版商務用 Skype 輕鬆完成。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-119">this can be easily done by navigating to the Legacy Skype for Business admin center.</span></span> <span data-ttu-id="7d4c5-120">決定的前置詞-XXXXXXX.online.lync.com 查詢和新增 /HostedMigration/hostedmigrationservice.svc。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-120">determine the prefix - XXXXXXX.online.lync.com and append /HostedMigration/hostedmigrationservice.svc.</span></span> <span data-ttu-id="7d4c5-121">例如：https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc一旦您已識別值，將其用於 $url 變數，如下所示。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-121">for example: https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc Once you identified the value, use it for the $url variable as shown below.</span></span>

<span data-ttu-id="7d4c5-122">下列指令程式順序可以用來移動使用者 skype 線上商務，並假設的 Office 365 認證是不同的帳戶，並提供做為 Get-credential 出現提示時輸入。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-122">The following cmdlet sequence can be used to move a user to Skype for Business Online, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="7d4c5-123">如果啟用 MFA （多重要素驗證） 的系統管理員帳戶，未指定-Credential 參數。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-123">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="7d4c5-124">系統管理員會被提示輸入認證。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-124">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="7d4c5-125">與 Skype for Business Server Control Panel 移動使用者</span><span class="sxs-lookup"><span data-stu-id="7d4c5-125">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="7d4c5-126">開啟 Skype for Business 伺服器控制項] 面板應用程式。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-126">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="7d4c5-127">在左導覽中，選擇 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-127">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="7d4c5-128">若要找出您想要將移至 Skype for Business Online 使用者使用 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-128">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="7d4c5-129">選取的使用者，然後從清單上方的 [**動作**] 下拉式清單，選擇 [**移至商務用 Skype 的所選的使用者**。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-129">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="7d4c5-130">在精靈中，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-130">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="7d4c5-131">如果出現提示，以登入 Office 365，結束於帳戶。 onmicrosoft.com 且具有足夠的權限。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-131">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="7d4c5-132">按一下 [**下一步**，然後**下一步**一個更多時間來移動使用者。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-132">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="7d4c5-133">請注意，在主要 [控制台] 應用程式，而不是以精靈頂端提供有關成功或失敗的狀態訊息。</span><span class="sxs-lookup"><span data-stu-id="7d4c5-133">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d4c5-134">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7d4c5-134">See also</span></span>

[<span data-ttu-id="7d4c5-135">Move-csuser</span><span class="sxs-lookup"><span data-stu-id="7d4c5-135">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)
