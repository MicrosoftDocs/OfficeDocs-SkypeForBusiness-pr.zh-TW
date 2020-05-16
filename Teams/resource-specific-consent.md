---
title: Microsoft 團隊中的資源特定同意
author: LanaChin
ms.author: v-lanac
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解您需要設定的設定，以控制貴組織中的小組擁有者是否可以同意 app。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54a0565f5126c899ed5fbf9527aa30f83c3bee3b
ms.sourcegitcommit: 296aeac481f901eb9d52b4f12a8c037afc49fa77
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2020
ms.locfileid: "44256571"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a><span data-ttu-id="d4f75-103">Microsoft 團隊中的資源特定同意</span><span class="sxs-lookup"><span data-stu-id="d4f75-103">Resource-specific consent in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="d4f75-104">Microsoft 團隊中的資源特定同意可讓小組擁有者同意存取小組資料的 app。</span><span class="sxs-lookup"><span data-stu-id="d4f75-104">Resource-specific consent in Microsoft Teams lets team owners give consent to apps to access team data.</span></span> <span data-ttu-id="d4f75-105">這類存取的範例包括閱讀頻道訊息、建立和刪除頻道，以及建立和移除頻道索引標籤的功能。</span><span class="sxs-lookup"><span data-stu-id="d4f75-105">Examples of such access include the ability to read channel messages, create and delete channels, and create and remove channel tabs.</span></span>

<span data-ttu-id="d4f75-106">如果您是管理員，您可以控制貴組織中的小組擁有者是否能透過您使用 Azure Active Directory （Azure AD） PowerShell 模組或 Azure 入口網站和 Microsoft 團隊系統管理中心來設定的設定進行同意。</span><span class="sxs-lookup"><span data-stu-id="d4f75-106">As an admin, you control whether team owners in your organization can give consent through settings that you configure by using the Azure Active Directory (Azure AD) PowerShell module or the Azure portal and the Microsoft Teams admin center.</span></span>  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a><span data-ttu-id="d4f75-107">設定團隊擁有者是否可授與應用程式的同意</span><span class="sxs-lookup"><span data-stu-id="d4f75-107">Set whether team owners can give consent to apps</span></span>

<span data-ttu-id="d4f75-108">您必須設定的設定，才能控制小組擁有者是否可以同意 app。</span><span class="sxs-lookup"><span data-stu-id="d4f75-108">Here are the settings that you must set to control whether team owners can give consent to apps.</span></span> <span data-ttu-id="d4f75-109">請務必查看下列所有設定。</span><span class="sxs-lookup"><span data-stu-id="d4f75-109">Be sure to review all the following settings.</span></span>

### <a name="settings-in-azure-ad"></a><span data-ttu-id="d4f75-110">Azure AD 中的設定</span><span class="sxs-lookup"><span data-stu-id="d4f75-110">Settings in Azure AD</span></span>

<span data-ttu-id="d4f75-111">下列兩個設定決定團隊擁有者是否可以同意 app。</span><span class="sxs-lookup"><span data-stu-id="d4f75-111">The following two settings determine whether team owners can give consent to apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4f75-112">變更這些設定中的任何一個，不會影響已獲同意之 app 的資料存取權。</span><span class="sxs-lookup"><span data-stu-id="d4f75-112">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="d4f75-113">例如，如果您將這些設定設定為防止小組擁有者同意，這些變更就不會移除已授與的資料存取權。</span><span class="sxs-lookup"><span data-stu-id="d4f75-113">For example, if you configure these settings to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a><span data-ttu-id="d4f75-114">「使用者可以同意代表自己存取公司資料的 app」設定</span><span class="sxs-lookup"><span data-stu-id="d4f75-114">The "Users can consent to apps accessing company data on their behalf" setting</span></span>

<span data-ttu-id="d4f75-115">此設定會控制貴組織中的使用者是否可以代表自己同意 app。</span><span class="sxs-lookup"><span data-stu-id="d4f75-115">This setting controls whether users in your organization can consent to apps on their behalf.</span></span> <span data-ttu-id="d4f75-116">若要讓小組擁有者授與同意，此設定必須設定為 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="d4f75-116">To enable team owners to give consent, this setting must be set to **Yes**.</span></span> <span data-ttu-id="d4f75-117">若要管理此設定，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d4f75-117">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="d4f75-118">在 Azure 入口網站中，移至 [**企業應用程式**]  >  **使用者設定**。</span><span class="sxs-lookup"><span data-stu-id="d4f75-118">In the Azure portal, go to **Enterprise applications** > **User settings**.</span></span>
2. <span data-ttu-id="d4f75-119">在 [**企業應用程式**] 底下，設定**使用者可以同意代表自己存取公司資料的應用程式** **，或\*\*\*\*選擇 [是]**。</span><span class="sxs-lookup"><span data-stu-id="d4f75-119">Under **Enterprise applications**, set **Users can consent to apps accessing company data on their behalf** to **No** or **Yes**.</span></span>

<span data-ttu-id="d4f75-120">您也可以使用 PowerShell 管理此設定。</span><span class="sxs-lookup"><span data-stu-id="d4f75-120">You can also manage this setting using PowerShell.</span></span> <span data-ttu-id="d4f75-121">若要深入瞭解，請參閱[設定使用者內容到應用程式](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)。</span><span class="sxs-lookup"><span data-stu-id="d4f75-121">To learn more, see [Configure user content to applications](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).</span></span>

#### <a name="the-enablegroupspecificconsent-setting"></a><span data-ttu-id="d4f75-122">"EnableGroupSpecificConsent" 設定</span><span class="sxs-lookup"><span data-stu-id="d4f75-122">The "EnableGroupSpecificConsent" setting</span></span>

<span data-ttu-id="d4f75-123">此設定會控制貴組織中的使用者是否可以同意針對其擁有之群組存取公司資料的 app。</span><span class="sxs-lookup"><span data-stu-id="d4f75-123">This setting controls whether users in your organization can consent to apps accessing company data for the groups that they own.</span></span> <span data-ttu-id="d4f75-124">必須為小組擁有者啟用此設定，才能授與同意。</span><span class="sxs-lookup"><span data-stu-id="d4f75-124">This setting must be enabled for team owners to give consent.</span></span> <span data-ttu-id="d4f75-125">如需如何使用 PowerShell 管理此設定的步驟，請參閱[將群組擁有者同意設定為存取群組資料的 app](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)。</span><span class="sxs-lookup"><span data-stu-id="d4f75-125">For steps on how to manage this setting by using PowerShell, see [Configure group owner consent to apps accessing group data](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).</span></span>

### <a name="settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="d4f75-126">Microsoft 團隊系統管理中心中的設定</span><span class="sxs-lookup"><span data-stu-id="d4f75-126">Settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="d4f75-127">除了 Azure AD 中的設定、[[管理應用程式](manage-apps.md)] 頁面上的 [集中式[應用程式設定](manage-apps.md#manage-org-wide-app-settings)]、[[管理應用程式](manage-apps.md#allow-and-block-apps)] 頁面上的 [已封鎖] 或 [允許]，以及分派給小組擁有者的[應用程式許可權原則](teams-app-permission-policies.md)，決定小組擁有者是否同意。</span><span class="sxs-lookup"><span data-stu-id="d4f75-127">In addition to settings in Azure AD, [org-wide app settings](manage-apps.md#manage-org-wide-app-settings) on the [Manage apps](manage-apps.md) page, whether an app is blocked or allowed on the [Manage apps](manage-apps.md#allow-and-block-apps) page, and the [app permission policy](teams-app-permission-policies.md) assigned to the team owner determine whether a team owner can give consent.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4f75-128">變更這些設定中的任何一個，不會影響已獲同意之 app 的資料存取權。</span><span class="sxs-lookup"><span data-stu-id="d4f75-128">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="d4f75-129">例如，如果您停用協力廠商應用程式，或是您封鎖特定 app 來避免小組擁有者同意，這些變更不會移除已授與的資料存取權。</span><span class="sxs-lookup"><span data-stu-id="d4f75-129">For example, if you disable third-party apps org-wide or if you block specific apps to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a><span data-ttu-id="d4f75-130">整個組織內應用程式設定中的 [允許協力廠商應用程式] 設定</span><span class="sxs-lookup"><span data-stu-id="d4f75-130">The "Allow third party apps" setting in org-wide app settings</span></span>

<span data-ttu-id="d4f75-131">此全組織式應用程式設定可控制貴組織中的使用者是否可以使用協力廠商應用程式。</span><span class="sxs-lookup"><span data-stu-id="d4f75-131">This org-wide app setting controls whether users in your organization can use third-party apps.</span></span> <span data-ttu-id="d4f75-132">此設定必須是開啟的，才能讓小組擁有者同意。</span><span class="sxs-lookup"><span data-stu-id="d4f75-132">This setting must be on to enable team owners to give consent.</span></span> <span data-ttu-id="d4f75-133">若要管理此設定，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d4f75-133">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="d4f75-134">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理 app**]，然後按一下 [**全組織式應用程式設定**]。</span><span class="sxs-lookup"><span data-stu-id="d4f75-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
2. <span data-ttu-id="d4f75-135">在 [**協力廠商應用程式**] 底下，關閉或開啟 [**允許協力廠商應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="d4f75-135">Under **Third party apps**, turn off or turn on **Allow third party apps**.</span></span>

    ![[在小組中允許協力廠商應用程式] 設定的螢幕擷取畫面](media/resource-specific-consent-org-wide-setting.png)

<span data-ttu-id="d4f75-137">您可能需要等候 24 小時，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="d4f75-137">You may have to wait up to 24 hours for your changes to take effect.</span></span>

#### <a name="allow-or-block-the-app-at-the-org-level"></a><span data-ttu-id="d4f75-138">允許或封鎖組織層級的應用程式</span><span class="sxs-lookup"><span data-stu-id="d4f75-138">Allow or block the app at the org level</span></span>

<span data-ttu-id="d4f75-139">當您封鎖或允許 [[管理應用程式](manage-apps.md#allow-and-block-apps)] 頁面上的應用程式時，該應用程式會遭到封鎖，或您組織中的所有使用者都能使用該 app。</span><span class="sxs-lookup"><span data-stu-id="d4f75-139">When you block or allow an app on the [Manage apps](manage-apps.md#allow-and-block-apps) page, that app is blocked or allowed for all users in your organization.</span></span> <span data-ttu-id="d4f75-140">小組擁有者只會在允許應用程式時，同意 app。</span><span class="sxs-lookup"><span data-stu-id="d4f75-140">Team owners can only give consent to an app if the app is allowed.</span></span> <span data-ttu-id="d4f75-141">若要允許或封鎖組織階層的 app，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d4f75-141">To allow or block an app at the org level, do the following:</span></span>

1. <span data-ttu-id="d4f75-142">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="d4f75-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="d4f75-143">在 [管理應用程式] 頁面上，選取應用程式，然後按一下 [**封鎖**] 來封鎖它，或按一下 [**允許**] 以允許它。</span><span class="sxs-lookup"><span data-stu-id="d4f75-143">On the Manage apps page, select the app, and then click **Block** to block it or click **Allow** to allow it.</span></span>

    ![組織內設定中封鎖 app 的螢幕擷取畫面](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a><span data-ttu-id="d4f75-145">指派給小組擁有者的 App 許可權原則</span><span class="sxs-lookup"><span data-stu-id="d4f75-145">App permission policy assigned to the team owner</span></span>

<span data-ttu-id="d4f75-146">小組擁有者只可以同意其 app 許可權原則允許其執行的 app。</span><span class="sxs-lookup"><span data-stu-id="d4f75-146">Team owners can only give consent to apps that their app permission policy allows them to run.</span></span> <span data-ttu-id="d4f75-147">若要查看及管理指派給小組擁有者的應用程式許可權原則，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d4f75-147">To view and manage the app permission policy that's assigned to a team owner, do the following:</span></span>

1. <span data-ttu-id="d4f75-148">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="d4f75-148">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="d4f75-149">按兩下小組擁有者的顯示名稱，然後按一下 [**原則**]。</span><span class="sxs-lookup"><span data-stu-id="d4f75-149">Double-click the display name of the team owner, and then click **Policies**.</span></span>
3. <span data-ttu-id="d4f75-150">指派給小組擁有者的原則會列在 [**應用程式許可權原則**] 底下。</span><span class="sxs-lookup"><span data-stu-id="d4f75-150">The policy assigned to the team owner is listed under **App permission policy**.</span></span>
    - <span data-ttu-id="d4f75-151">若要指派其他原則，請按一下 [**編輯**]，然後選取您要指派的原則。</span><span class="sxs-lookup"><span data-stu-id="d4f75-151">To assign a different policy, click **Edit**, and then select the policy that you want to assign.</span></span>
    - <span data-ttu-id="d4f75-152">若要編輯指派給小組擁有者的原則設定，請按一下 [原則名稱]，然後進行所要的變更。</span><span class="sxs-lookup"><span data-stu-id="d4f75-152">To edit the settings of the policy that's assigned to the team owner, click the policy name, and then make the changes that you want.</span></span>  

## <a name="uploading-custom-apps"></a><span data-ttu-id="d4f75-153">上傳自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="d4f75-153">Uploading custom apps</span></span>

<span data-ttu-id="d4f75-154">當您上傳使用資源特定同意的自訂應用程式（也稱為旁載）時，應用程式必須來自要安裝的租使用者。</span><span class="sxs-lookup"><span data-stu-id="d4f75-154">When uploading a custom app (also known sideloading) that uses resource-specific consent, the app must come from the tenant that it's being installed to.</span></span> <span data-ttu-id="d4f75-155">換句話說，Azure AD app 註冊必須來自于此租使用者。</span><span class="sxs-lookup"><span data-stu-id="d4f75-155">In other words, the Azure AD app registration must be from this tenant.</span></span> <span data-ttu-id="d4f75-156">全域管理員會免除此限制，而且可以從任何租使用者直接上傳至小組（側載）或租使用者目錄的自訂 app。</span><span class="sxs-lookup"><span data-stu-id="d4f75-156">Global admins are exempted from this restriction, and can upload custom apps from any tenant, either directly to a team (sideloading) or to the tenant app catalog.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d4f75-157">相關主題</span><span class="sxs-lookup"><span data-stu-id="d4f75-157">Related topics</span></span>

- [<span data-ttu-id="d4f75-158">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="d4f75-158">Microsoft Graph</span></span>](https://developer.microsoft.com/graph)
- [<span data-ttu-id="d4f75-159">在 Microsoft 團隊系統管理中心管理您的應用程式</span><span class="sxs-lookup"><span data-stu-id="d4f75-159">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="d4f75-160">在 Teams 中管理應用程式權限原則</span><span class="sxs-lookup"><span data-stu-id="d4f75-160">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
