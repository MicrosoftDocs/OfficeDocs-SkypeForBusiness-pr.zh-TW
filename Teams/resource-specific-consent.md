---
title: Microsoft Teams 中的特定資源同意
author: cichur
ms.author: v-cichur
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解您需要設定哪些設定，以控制貴組織中團隊擁有者是否可以同意應用程式。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7b9379db7760fa8ef03440c24b93cb0223b4bee
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117621"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a><span data-ttu-id="86a3b-103">Microsoft Teams 中的特定資源同意</span><span class="sxs-lookup"><span data-stu-id="86a3b-103">Resource-specific consent in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="86a3b-104">Microsoft Teams 中的特定資源同意可讓團隊擁有者同意應用程式存取小組資料。</span><span class="sxs-lookup"><span data-stu-id="86a3b-104">Resource-specific consent in Microsoft Teams lets team owners give consent to apps to access team data.</span></span> <span data-ttu-id="86a3b-105">這類存取的範例包括讀取頻道訊息、建立及刪除頻道，以及建立及移除頻道標籤。</span><span class="sxs-lookup"><span data-stu-id="86a3b-105">Examples of such access include the ability to read channel messages, create and delete channels, and create and remove channel tabs.</span></span>

<span data-ttu-id="86a3b-106">做為系統管理員，您可以控制貴組織中團隊擁有者是否可以使用 Azure Active Directory (Azure AD) PowerShell 模組或 Azure 入口網站和 Microsoft Teams 系統管理中心，透過您設定設定來給予同意。</span><span class="sxs-lookup"><span data-stu-id="86a3b-106">As an admin, you control whether team owners in your organization can give consent through settings that you configure by using the Azure Active Directory (Azure AD) PowerShell module or the Azure portal and the Microsoft Teams admin center.</span></span>  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a><span data-ttu-id="86a3b-107">設定團隊擁有者是否可以同意應用程式</span><span class="sxs-lookup"><span data-stu-id="86a3b-107">Set whether team owners can give consent to apps</span></span>

<span data-ttu-id="86a3b-108">以下是您必須設定來控制團隊擁有者是否可以同意應用程式。</span><span class="sxs-lookup"><span data-stu-id="86a3b-108">Here are the settings that you must set to control whether team owners can give consent to apps.</span></span> <span data-ttu-id="86a3b-109">請務必檢查下列所有設定。</span><span class="sxs-lookup"><span data-stu-id="86a3b-109">Be sure to review all the following settings.</span></span>

### <a name="settings-in-azure-ad"></a><span data-ttu-id="86a3b-110">Azure AD 中的設定</span><span class="sxs-lookup"><span data-stu-id="86a3b-110">Settings in Azure AD</span></span>

<span data-ttu-id="86a3b-111">下列兩個設定會決定團隊擁有者是否可以同意應用程式。</span><span class="sxs-lookup"><span data-stu-id="86a3b-111">The following two settings determine whether team owners can give consent to apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="86a3b-112">變更這些設定並不會影響已獲得同意之 App 的存取資料。</span><span class="sxs-lookup"><span data-stu-id="86a3b-112">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="86a3b-113">例如，如果您設定這些設定以防止團隊擁有者同意，這些變更不會移除已授予的資料存取權。</span><span class="sxs-lookup"><span data-stu-id="86a3b-113">For example, if you configure these settings to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a><span data-ttu-id="86a3b-114">「使用者可以同意應用程式代表他們存取公司資料」設定</span><span class="sxs-lookup"><span data-stu-id="86a3b-114">The "Users can consent to apps accessing company data on their behalf" setting</span></span>

<span data-ttu-id="86a3b-115">此設定可控制貴組織的使用者是否能代表他們同意應用程式。</span><span class="sxs-lookup"><span data-stu-id="86a3b-115">This setting controls whether users in your organization can consent to apps on their behalf.</span></span> <span data-ttu-id="86a3b-116">若要讓團隊擁有者同意，此設定必須設為 **是**。</span><span class="sxs-lookup"><span data-stu-id="86a3b-116">To enable team owners to give consent, this setting must be set to **Yes**.</span></span> <span data-ttu-id="86a3b-117">若要管理此設定，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="86a3b-117">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="86a3b-118">在 Azure 入口網站中，前往 **企業應用程式**  >  **使用者設定**。</span><span class="sxs-lookup"><span data-stu-id="86a3b-118">In the Azure portal, go to **Enterprise applications** > **User settings**.</span></span>
2. <span data-ttu-id="86a3b-119">在 **企業應用程式** 下 **，將使用者可以同意** 代表其存取公司資料的 App 設為 **No 或 Yes。** </span><span class="sxs-lookup"><span data-stu-id="86a3b-119">Under **Enterprise applications**, set **Users can consent to apps accessing company data on their behalf** to **No** or **Yes**.</span></span>

<span data-ttu-id="86a3b-120">您也可以使用 PowerShell 管理此設定。</span><span class="sxs-lookup"><span data-stu-id="86a3b-120">You can also manage this setting using PowerShell.</span></span> <span data-ttu-id="86a3b-121">若要深入瞭解，請參閱將 [使用者內容設定為應用程式](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)。</span><span class="sxs-lookup"><span data-stu-id="86a3b-121">To learn more, see [Configure user content to applications](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).</span></span>

#### <a name="the-enablegroupspecificconsent-setting"></a><span data-ttu-id="86a3b-122">「EnableGroupSpecificConsent」設定</span><span class="sxs-lookup"><span data-stu-id="86a3b-122">The "EnableGroupSpecificConsent" setting</span></span>

<span data-ttu-id="86a3b-123">此設定可控制貴組織中使用者是否可以同意應用程式存取他們擁有之群組的公司資料。</span><span class="sxs-lookup"><span data-stu-id="86a3b-123">This setting controls whether users in your organization can consent to apps accessing company data for the groups that they own.</span></span> <span data-ttu-id="86a3b-124">必須啟用此設定，團隊擁有者才能表示同意。</span><span class="sxs-lookup"><span data-stu-id="86a3b-124">This setting must be enabled for team owners to give consent.</span></span> <span data-ttu-id="86a3b-125">若要瞭解如何使用 PowerShell 管理此設定的步驟，請參閱設定群組擁有者同意 [存取群組資料的應用程式](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)。</span><span class="sxs-lookup"><span data-stu-id="86a3b-125">For steps on how to manage this setting by using PowerShell, see [Configure group owner consent to apps accessing group data](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).</span></span>

### <a name="settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="86a3b-126">Microsoft Teams 系統管理中心的設定</span><span class="sxs-lookup"><span data-stu-id="86a3b-126">Settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="86a3b-127">除了 Azure AD 中的設定[](manage-apps.md#manage-org-wide-app-settings)之外，在管理應用程式頁面上的[](manage-apps.md)全組織應用程式設定、應用程式在管理應用程式頁面上是否受到封鎖或[](manage-apps.md#allow-and-block-apps)允許，以及指派給團隊擁有者的應用程式許可權政策，都決定團隊擁有者是否可以給予同意。 [](teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="86a3b-127">In addition to settings in Azure AD, [org-wide app settings](manage-apps.md#manage-org-wide-app-settings) on the [Manage apps](manage-apps.md) page, whether an app is blocked or allowed on the [Manage apps](manage-apps.md#allow-and-block-apps) page, and the [app permission policy](teams-app-permission-policies.md) assigned to the team owner determine whether a team owner can give consent.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="86a3b-128">變更這些設定並不會影響已獲得同意之 App 的存取資料。</span><span class="sxs-lookup"><span data-stu-id="86a3b-128">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="86a3b-129">例如，如果您停用全組織的協力廠商應用程式，或是封鎖特定應用程式，以防止團隊擁有者同意，這些變更不會移除已授予的資料存取權。</span><span class="sxs-lookup"><span data-stu-id="86a3b-129">For example, if you disable third-party apps org-wide or if you block specific apps to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a><span data-ttu-id="86a3b-130">全組織 App 設定中的 「允許協力廠商應用程式」設定</span><span class="sxs-lookup"><span data-stu-id="86a3b-130">The "Allow third party apps" setting in org-wide app settings</span></span>

<span data-ttu-id="86a3b-131">此全組織應用程式設定可控制貴組織中的使用者是否可以使用協力廠商應用程式。</span><span class="sxs-lookup"><span data-stu-id="86a3b-131">This org-wide app setting controls whether users in your organization can use third-party apps.</span></span> <span data-ttu-id="86a3b-132">此設定必須為啟用，才能讓團隊擁有者同意。</span><span class="sxs-lookup"><span data-stu-id="86a3b-132">This setting must be on to enable team owners to give consent.</span></span> <span data-ttu-id="86a3b-133">若要管理此設定，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="86a3b-133">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="86a3b-134">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **Teams 應用程式**  >  **管理** 應用程式，然後按一下 **[全組織應用程式設定**>。</span><span class="sxs-lookup"><span data-stu-id="86a3b-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
2. <span data-ttu-id="86a3b-135">在第 **三方應用程式下**，關閉或開啟允許 **協力廠商應用程式**。</span><span class="sxs-lookup"><span data-stu-id="86a3b-135">Under **Third party apps**, turn off or turn on **Allow third party apps**.</span></span>

    ![「在 Teams 中允許協力廠商應用程式」設定螢幕擷取畫面](media/resource-specific-consent-org-wide-setting.png)

<span data-ttu-id="86a3b-137">您可能需要等候 24 小時，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="86a3b-137">You may have to wait up to 24 hours for your changes to take effect.</span></span>

#### <a name="allow-or-block-the-app-at-the-org-level"></a><span data-ttu-id="86a3b-138">在組織層級允許或封鎖應用程式</span><span class="sxs-lookup"><span data-stu-id="86a3b-138">Allow or block the app at the org level</span></span>

<span data-ttu-id="86a3b-139">當您封鎖或允許管理應用程式頁面上的應用程式時[](manage-apps.md#allow-and-block-apps)，該應用程式會封鎖或允許貴組織的所有使用者使用。</span><span class="sxs-lookup"><span data-stu-id="86a3b-139">When you block or allow an app on the [Manage apps](manage-apps.md#allow-and-block-apps) page, that app is blocked or allowed for all users in your organization.</span></span> <span data-ttu-id="86a3b-140">只有允許應用程式時，團隊擁有者才能同意應用程式。</span><span class="sxs-lookup"><span data-stu-id="86a3b-140">Team owners can only give consent to an app if the app is allowed.</span></span> <span data-ttu-id="86a3b-141">若要允許或封鎖組織層級的應用程式，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="86a3b-141">To allow or block an app at the org level, do the following:</span></span>

1. <span data-ttu-id="86a3b-142">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。</span><span class="sxs-lookup"><span data-stu-id="86a3b-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="86a3b-143">在 [管理應用程式> 頁面上，選取應用程式，然後按一下 **[封鎖** 以封鎖它或按一下 **[允許** 允許該 App。</span><span class="sxs-lookup"><span data-stu-id="86a3b-143">On the Manage apps page, select the app, and then click **Block** to block it or click **Allow** to allow it.</span></span>

    ![全組織設定中封鎖的應用程式螢幕擷取畫面](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a><span data-ttu-id="86a3b-145">指派給團隊擁有者的應用程式權限原則</span><span class="sxs-lookup"><span data-stu-id="86a3b-145">App permission policy assigned to the team owner</span></span>

<span data-ttu-id="86a3b-146">團隊擁有者只能同意其應用程式權限原則允許其執行的應用程式。</span><span class="sxs-lookup"><span data-stu-id="86a3b-146">Team owners can only give consent to apps that their app permission policy allows them to run.</span></span> <span data-ttu-id="86a3b-147">若要查看及管理指派給團隊擁有者的應用程式許可權政策，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="86a3b-147">To view and manage the app permission policy that's assigned to a team owner, do the following:</span></span>

1. <span data-ttu-id="86a3b-148">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **使用者**。</span><span class="sxs-lookup"><span data-stu-id="86a3b-148">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="86a3b-149">按兩下團隊擁有者的顯示名稱，然後按一下 [ **政策>**。</span><span class="sxs-lookup"><span data-stu-id="86a3b-149">Double-click the display name of the team owner, and then click **Policies**.</span></span>
3. <span data-ttu-id="86a3b-150">指派給團隊擁有者的政策會列在 **應用程式許可權政策下**。</span><span class="sxs-lookup"><span data-stu-id="86a3b-150">The policy assigned to the team owner is listed under **App permission policy**.</span></span>
    - <span data-ttu-id="86a3b-151">若要指派不同的策略，請按一下 [ **編輯**」，然後選取您想要指派的策略。</span><span class="sxs-lookup"><span data-stu-id="86a3b-151">To assign a different policy, click **Edit**, and then select the policy that you want to assign.</span></span>
    - <span data-ttu-id="86a3b-152">若要編輯指派給團隊擁有者之策略的設定，請按一下該策略名稱，然後進行您想要的變更。</span><span class="sxs-lookup"><span data-stu-id="86a3b-152">To edit the settings of the policy that's assigned to the team owner, click the policy name, and then make the changes that you want.</span></span>  

## <a name="uploading-custom-apps"></a><span data-ttu-id="86a3b-153">上傳自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="86a3b-153">Uploading custom apps</span></span>

<span data-ttu-id="86a3b-154">上傳自訂應用程式 (亦稱為) 使用特定資源同意的側載應用程式時，應用程式必須來自其安裝的租使用者。</span><span class="sxs-lookup"><span data-stu-id="86a3b-154">When uploading a custom app (also known sideloading) that uses resource-specific consent, the app must come from the tenant that it's being installed to.</span></span> <span data-ttu-id="86a3b-155">換句話說，Azure AD 應用程式註冊必須來自此租使用者。</span><span class="sxs-lookup"><span data-stu-id="86a3b-155">In other words, the Azure AD app registration must be from this tenant.</span></span> <span data-ttu-id="86a3b-156">全域系統管理員不受此限制，而且可以直接將自訂應用程式從任何租使用者上傳至小組 (側載入) 或租使用者應用程式目錄。</span><span class="sxs-lookup"><span data-stu-id="86a3b-156">Global admins are exempted from this restriction, and can upload custom apps from any tenant, either directly to a team (sideloading) or to the tenant app catalog.</span></span>

## <a name="related-topics"></a><span data-ttu-id="86a3b-157">相關主題</span><span class="sxs-lookup"><span data-stu-id="86a3b-157">Related topics</span></span>

- [<span data-ttu-id="86a3b-158">可用的 RSC 許可權</span><span class="sxs-lookup"><span data-stu-id="86a3b-158">Available RSC permissions</span></span>](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [<span data-ttu-id="86a3b-159">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="86a3b-159">Microsoft Graph</span></span>](https://developer.microsoft.com/graph)
- [<span data-ttu-id="86a3b-160">在 Microsoft Teams 系統管理中心管理您的應用程式</span><span class="sxs-lookup"><span data-stu-id="86a3b-160">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="86a3b-161">在 Teams 中管理應用程式權限原則</span><span class="sxs-lookup"><span data-stu-id="86a3b-161">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)