---
title: 在 Microsoft Teams 中授權來賓存取
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- SPO_Content
ms.reviewer: sbhatta
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
description: 透過四種不同的授權等級管理 Microsoft Teams 的來賓存取功能。
appliesto:
- Microsoft Teams
ms.openlocfilehash: f9ecf6893539204909bb6f583bbba982e8ee8d19
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656154"
---
<a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="00b7e-103">在 Microsoft Teams 中授權來賓存取</span><span class="sxs-lookup"><span data-stu-id="00b7e-103">Authorize guest access in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="00b7e-104">為滿足貴組織的需求，您可以透過四種不同的授權等級管理 Microsoft Teams 的來賓存取功能。</span><span class="sxs-lookup"><span data-stu-id="00b7e-104">To satisfy your organization’s requirements, you can manage Microsoft Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="00b7e-105">所有授權等級都適用於您的 Microsoft 365 或 Office 365 組織。</span><span class="sxs-lookup"><span data-stu-id="00b7e-105">All the authorization levels apply to your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="00b7e-106">每個授權等級控制的來賓體驗如下所示：</span><span class="sxs-lookup"><span data-stu-id="00b7e-106">Each authorization level controls the guest experience as shown below:</span></span>

- <span data-ttu-id="00b7e-107">**Azure Active Directory**：Microsoft Teams 的來賓存取需要 Azure AD 企業對企業 (B2B) 平台。</span><span class="sxs-lookup"><span data-stu-id="00b7e-107">**Azure Active Directory**: Guest access in Microsoft Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="00b7e-108">此授權等級控制目錄、租用戶和應用程式層級的來賓體驗。</span><span class="sxs-lookup"><span data-stu-id="00b7e-108">This authorization level controls the guest experience at the directory, tenant, and application level.</span></span>
- <span data-ttu-id="00b7e-109">**Microsoft Teams**：僅控制 Microsoft Teams 中的來賓體驗。</span><span class="sxs-lookup"><span data-stu-id="00b7e-109">**Microsoft Teams**: Controls the guest experience in Microsoft Teams only.</span></span>
- <span data-ttu-id="00b7e-110">**Microsoft 365 群組**：控制 Microsoft 365 群組和 Microsoft Teams 中的來賓體驗。</span><span class="sxs-lookup"><span data-stu-id="00b7e-110">**Microsoft 365 Groups**: Controls the guest experience in Microsoft 365 Groups and Microsoft Teams.</span></span>
- <span data-ttu-id="00b7e-111">**SharePoint Online 和商務用 OneDrive**：控制 SharePoint Online、商務用 OneDrive、Microsoft 365 群組和 Microsoft Teams 中的來賓體驗。</span><span class="sxs-lookup"><span data-stu-id="00b7e-111">**SharePoint Online and OneDrive for Business**: Controls the guest experience in SharePoint Online, OneDrive for Business, Microsoft 365 Groups, and Microsoft Teams.</span></span>

<span data-ttu-id="00b7e-112">這些不同的授權等級能夠讓您彈性設定貴組織的來賓存取。</span><span class="sxs-lookup"><span data-stu-id="00b7e-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="00b7e-113">例如，如果您不想在 Microsoft Teams 中允許來賓使用者，但是想要在貴組織中全面允許來賓使用者，只要在 Microsoft Teams 中關閉來賓存取即可。</span><span class="sxs-lookup"><span data-stu-id="00b7e-113">For example, if you don’t want to allow guest users in your Microsoft Teams but want to allow it overall in your organization, just turn off guest access in Microsoft Teams.</span></span> <span data-ttu-id="00b7e-114">另一個範例：您可以啟用 Azure AD、Microsoft Teams 和群組等級的來賓存取，但是接著在符合一或多個準則 (例如資料分類等於機密) 的小組中，停用所選小組的新增來賓使用者功能。</span><span class="sxs-lookup"><span data-stu-id="00b7e-114">Another example: You could enable guest access at the Azure AD, Teams, and Groups levels, but then disable the addition of guest users on selected teams that match one or more criteria such as data classification equals confidential.</span></span> <span data-ttu-id="00b7e-115">SharePoint Online 和商務用 OneDrive 擁有自己的來賓存取設定，不需要依賴 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="00b7e-115">SharePoint Online and OneDrive for Business have their own guest access settings that don't rely on Microsoft 365 Groups.</span></span>

> [!NOTE]
> <span data-ttu-id="00b7e-116">來賓會受 [Microsoft 365 和 Office 365 服務描述](https://go.microsoft.com/fwlink/p/?linkid=282347)和 [Azure AD B2B 共同作業限制](https://go.microsoft.com/fwlink/p/?linkid=853019)中所描述的服務限制。</span><span class="sxs-lookup"><span data-stu-id="00b7e-116">Guests are subject to the service limits described in [Microsoft 365 and Office 365 service descriptions](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Limitations of Azure AD B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=853019).</span></span> 

<span data-ttu-id="00b7e-117">以下圖表顯示在 Azure Active Directory、Microsoft Teams 和 Microsoft 365 或 Office 365 之間，來賓存取之授權相依性的授權方式和整合。</span><span class="sxs-lookup"><span data-stu-id="00b7e-117">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Microsoft Teams, and Microsoft 365 or Office 365.</span></span>

![來賓存取的授權相依性圖表。](media/teams_dependencies_image1.png)

<span data-ttu-id="00b7e-119">以下圖表以高等級的角度，顯示透過一般來賓存取的邀請與兌換流程，使用者體驗搭配權限模型的運作方式。</span><span class="sxs-lookup"><span data-stu-id="00b7e-119">The next diagram shows, at a high level, how the user experience works with the permission model through a typical guest access invitation and redemption flow.</span></span>

![邀請與兌換流程圖表](media/authorize-guest-image1.png)

<span data-ttu-id="00b7e-121">此處請特別注意，應用程式、Bot 和連接器可能需要各自的權限集和/或使用者帳戶專屬的同意。</span><span class="sxs-lookup"><span data-stu-id="00b7e-121">It’s important to note here that apps, bots, and connectors might require their own set of permissions and/or consent specific to the user account.</span></span> <span data-ttu-id="00b7e-122">這些情況可能需要個別授權。</span><span class="sxs-lookup"><span data-stu-id="00b7e-122">These might need to be granted separately.</span></span> <span data-ttu-id="00b7e-123">同樣地，SharePoint 可能會針對特定使用者、使用者群組或甚至是在網站層級，強制規定額外的外部共用界限。</span><span class="sxs-lookup"><span data-stu-id="00b7e-123">Similarly, SharePoint might impose extra external sharing boundaries for a specific user, groups of users, or even at the site level.</span></span>

<span data-ttu-id="00b7e-124">以上兩張圖表也可以在 [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true) 中使用。</span><span class="sxs-lookup"><span data-stu-id="00b7e-124">The previous two diagrams are also available in [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true).</span></span>

## <a name="control-guest-access-in-azure-active-directory"></a><span data-ttu-id="00b7e-125">控制 Azure Active Directory 的來賓存取</span><span class="sxs-lookup"><span data-stu-id="00b7e-125">Control guest access in Azure Active Directory</span></span>

<span data-ttu-id="00b7e-126">使用 Azure AD 來判斷外部共同作業者是否能以來賓身分受邀進入您的租用戶，以及採取何種方式。</span><span class="sxs-lookup"><span data-stu-id="00b7e-126">Use Azure AD to determine whether external collaborators can be invited into your tenant as guests, and in what ways.</span></span> <span data-ttu-id="00b7e-127">如需 Azure B2B 來賓存取的詳細資訊，請參閱[什麼是 Azure Active Directory B2B 中的來賓使用者存取權](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)。</span><span class="sxs-lookup"><span data-stu-id="00b7e-127">For more information about Azure B2B guest access, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span></span> <span data-ttu-id="00b7e-128">如需 Azure AD 角色的詳細資訊，請參閱[從 Azure Active Directory 租用戶中的合作夥伴組織授與權限給使用者](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role)。</span><span class="sxs-lookup"><span data-stu-id="00b7e-128">For information about Azure AD roles, see [Grant permissions to users from partner organizations in your Azure Active Directory tenant](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role).</span></span>

<span data-ttu-id="00b7e-129">邀請的設定會套用到租用戶層級，然後在目錄、租用戶和應用程式層級控制來賓體驗。</span><span class="sxs-lookup"><span data-stu-id="00b7e-129">The settings for invitations apply at the tenant level and control the guest experience at the directory, tenant, and application level.</span></span> <span data-ttu-id="00b7e-130">若要在 Azure 入口網站設定這些設定，前往 **[Azure Active Directory]** > **[使用者]** > **[使用者設定]**，在 **[外部使用者]** 之下，選取 **[管理外部共同作業設定]**。</span><span class="sxs-lookup"><span data-stu-id="00b7e-130">To configure these settings in the Azure portal, go to **Azure Active Directory** > **Users** > **User settings**, and under **External users**, select **Manage external collaboration settings**.</span></span>

<span data-ttu-id="00b7e-131">Azure AD 包含有下列設定可設定外部使用者：</span><span class="sxs-lookup"><span data-stu-id="00b7e-131">Azure AD includes the following settings to configure external users:</span></span>

- <span data-ttu-id="00b7e-132">**[來賓使用者權限受限]**：**[是]** 表示來賓沒有某些目錄工作的權限，例如列舉使用者、群組或其他目錄資源。</span><span class="sxs-lookup"><span data-stu-id="00b7e-132">**Guest user permissions are limited**: **Yes** means that guests don't have permission for certain directory tasks, such as enumerate users, groups, or other directory resources.</span></span> <span data-ttu-id="00b7e-133">此外，來賓不能指派為您目錄中的系統管理角色。</span><span class="sxs-lookup"><span data-stu-id="00b7e-133">In addition, guests can't be assigned to administrative roles in your directory.</span></span> <span data-ttu-id="00b7e-134">**[否]** 表示來賓與您目錄中的一般使用者一樣，擁有相同的目錄資料存取權。</span><span class="sxs-lookup"><span data-stu-id="00b7e-134">**No** means that guests have the same access to directory data that regular users have in your directory.</span></span>
- <span data-ttu-id="00b7e-135">**[系統管理員與來賓邀請者角色中的使用者可以邀請]**：**[是]** 表示系統管理員和來賓邀請者角色中的使用者將可以邀請來賓加入租用戶。</span><span class="sxs-lookup"><span data-stu-id="00b7e-135">**Admins and users in the guest inviter role can invite**: **Yes** means that admins and users in the guest inviter role will be able to invite guests to the tenant.</span></span> <span data-ttu-id="00b7e-136">**[否]** 表示系統管理員和使用者無法邀請來賓加入租用戶。</span><span class="sxs-lookup"><span data-stu-id="00b7e-136">**No** means admins and users can't invite guests to the tenant.</span></span>
- <span data-ttu-id="00b7e-137">**成員可邀請**：若要允許您目錄中的非系統管理員成員邀請來賓，請將此原則設定為 **[是]** (建議使用)。</span><span class="sxs-lookup"><span data-stu-id="00b7e-137">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="00b7e-138">如果您希望只讓系統管理員新增來賓，可以將此原則設定為 **[否]**。</span><span class="sxs-lookup"><span data-stu-id="00b7e-138">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="00b7e-139">請記住，設定為 **[否]** 將會限制非系統管理員小組擁有者的來賓體驗；他們只能在已由系統管理員在 AAD 中新增的 Teams 中新增來賓。</span><span class="sxs-lookup"><span data-stu-id="00b7e-139">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
- <span data-ttu-id="00b7e-140">**[來賓可邀請]**：**[是]** 表示目錄中的來賓可以邀請其他來賓，在受 Azure AD 保護的資源 (例如 SharePoint 網站或 Azure 資源) 上共同作業。</span><span class="sxs-lookup"><span data-stu-id="00b7e-140">**Guests can invite**: **Yes** means that guests in your directory can invite other guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="00b7e-141">**[否]** 表示來賓無法邀請其他來賓與貴組織共同作業。</span><span class="sxs-lookup"><span data-stu-id="00b7e-141">**No** means that guests can't invite other guests to collaborate with your organization.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="00b7e-142">Teams 目前不支援來賓邀請者角色，因此，即使您將 **[來賓可邀請]** 設定為 **[是]**，來賓仍無法在 Teams 中邀請其他來賓。</span><span class="sxs-lookup"><span data-stu-id="00b7e-142">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
 
<span data-ttu-id="00b7e-143">如需有關控制誰可以邀請來賓的詳細資訊，請參閱[委派 Azure Active Directory B2B 共同作業邀請](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="00b7e-143">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

> [!NOTE]
> <span data-ttu-id="00b7e-144">您也可以管理哪些網域可以做為來賓受邀加入您的租用戶。</span><span class="sxs-lookup"><span data-stu-id="00b7e-144">You can also manage which domains can be invited into your tenant as guests.</span></span> <span data-ttu-id="00b7e-145">請參閱[允許/封鎖來賓獲得 Microsoft 365 群組的存取權限](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="00b7e-145">See [Allow/Block guest access to Microsoft 365 Groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups).</span></span>

<span data-ttu-id="00b7e-146">您不需要將使用者來賓帳戶手動新增到 Azure AD B2B，因為當您將來賓新增到 Teams 時，帳戶會自動新增到目錄。</span><span class="sxs-lookup"><span data-stu-id="00b7e-146">Adding the user guest account manually to Azure AD B2B is not required, as the account will be added to the directory automatically when you add the guest to Teams.</span></span>

### <a name="licensing-for-guest-access"></a><span data-ttu-id="00b7e-147">來賓存取的授權</span><span class="sxs-lookup"><span data-stu-id="00b7e-147">Licensing for guest access</span></span>
<span data-ttu-id="00b7e-148">來賓存取的授權是 Azure AD 授權的一部分。</span><span class="sxs-lookup"><span data-stu-id="00b7e-148">Guest access licensing is part of Azure AD licensing.</span></span> <span data-ttu-id="00b7e-149">來賓存取隨附於所有 Microsoft 365 商務標準版和 Office 365 企業版訂閱。</span><span class="sxs-lookup"><span data-stu-id="00b7e-149">Guest access is included with all Microsoft 365 Business Standard and Office 365 Enterprise subscriptions.</span></span> <span data-ttu-id="00b7e-150">如需有關授權的詳細資訊，請參閱 [Azure Active Directory B2B 共同作業授權指引](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="00b7e-150">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>


> [!NOTE]
> <span data-ttu-id="00b7e-151">僅擁有獨立版 Office 365 訂閱方案 (例如 Exchange Online Plan 2) 的組織使用者將無法受邀為貴組織的來賓，因為 Teams 認為這些使用者屬於相同的組織。</span><span class="sxs-lookup"><span data-stu-id="00b7e-151">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="00b7e-152">若要讓這些使用者使用 Teams，這些使用者必須獲派 Microsoft 365 商務標準版、Office 365 企業版或 Office 365 教育版訂閱。</span><span class="sxs-lookup"><span data-stu-id="00b7e-152">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="control-guest-access-in-teams"></a><span data-ttu-id="00b7e-153">控制 Teams 的來賓存取</span><span class="sxs-lookup"><span data-stu-id="00b7e-153">Control guest access in Teams</span></span>

<span data-ttu-id="00b7e-154">Teams 的來賓存取依預設會關閉。</span><span class="sxs-lookup"><span data-stu-id="00b7e-154">Guest access is turned off by default in Teams.</span></span> <span data-ttu-id="00b7e-155">若要開啟來賓存取，請參閱[開啟或關閉 Microsoft Teams 的來賓存取](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="00b7e-155">To turn on guest access, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span> 


## <a name="control-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="00b7e-156">控制 Microsoft 365 群組的來賓存取</span><span class="sxs-lookup"><span data-stu-id="00b7e-156">Control guest access in Microsoft 365 Groups</span></span>

<span data-ttu-id="00b7e-157">在 Microsoft 365 群組中，您可以控制貴組織中所有 Microsoft 365 群組和 Microsoft Teams 小組的新增來賓使用者和來賓存取。</span><span class="sxs-lookup"><span data-stu-id="00b7e-157">From Microsoft 365 Groups, you can control adding guest users and guest access to all Microsoft 365 Groups and Microsoft Teams teams in your organization.</span></span>

1. <span data-ttu-id="00b7e-158">使用您的全域系統管理員帳戶登入 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)。</span><span class="sxs-lookup"><span data-stu-id="00b7e-158">Sign in with your global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>

2. <span data-ttu-id="00b7e-159">在左側，選擇 **[設定]**，然後選取 **[服務]&amp; [增益集]**。</span><span class="sxs-lookup"><span data-stu-id="00b7e-159">On the left, choose **Settings** and then select **Services &amp; add-ins**.</span></span>

3. <span data-ttu-id="00b7e-160">選取 **Microsoft 365 群組**。</span><span class="sxs-lookup"><span data-stu-id="00b7e-160">Select **Microsoft 365 Groups**.</span></span>

     ![[設定] 中的 [Microsoft 365 群組] 螢幕擷取畫面](media/authorize-guest-image2.png)
  
4. <span data-ttu-id="00b7e-162">在 [Microsoft 365 群組] 頁面上，根據您是否想讓貴組織外部的小組和群組擁有者存取 Microsoft 365 群組而定，將開關切換為 **[開啟]** 或 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="00b7e-162">On the Microsoft 365 Groups page, set the toggle to **On** or **Off**, depending on whether you want to let team and group owners outside your organization access Microsoft 365 Groups.</span></span> <span data-ttu-id="00b7e-163">按一下或點選 **[讓群組擁有者將貴組織外部的人員新增到群組]** 旁的 **[開啟]**。</span><span class="sxs-lookup"><span data-stu-id="00b7e-163">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span> <span data-ttu-id="00b7e-164">如果您將開關切換為 **[開啟]**，您會看到另一個用來控制是否要讓群組和小組擁有者將組織外部人員新增至 Microsoft 365 群組和 Microsoft Teams 的選項。</span><span class="sxs-lookup"><span data-stu-id="00b7e-164">If you turn this toggle to **On**, you'll see another option to control whether you want to let group and team owners add people outside your organization to Microsoft 365 Groups and Microsoft Teams.</span></span> <span data-ttu-id="00b7e-165">如果您想讓群組和小組擁有者新增來賓使用者，請將此開關設定為 **[開啟]**。</span><span class="sxs-lookup"><span data-stu-id="00b7e-165">Set this toggle to **On** if you want to let group and team owners add guest users.</span></span> 
 
   ![[Microsoft 365 群組] 面板及選項已開啟的螢幕擷取畫面](media/authorize-guest-image3.png)

<span data-ttu-id="00b7e-167">這些設定會套用到租用戶層級，控制 Microsoft 365 群組和 Teams 中的來賓體驗。</span><span class="sxs-lookup"><span data-stu-id="00b7e-167">These settings apply at the tenant level and control the guest experience in Microsoft 365 Groups and Teams.</span></span>

<span data-ttu-id="00b7e-168">如需有關群組中的來賓存取，包括來賓存取的運作方式、來賓存取的管理方法以及常見問題的解答等詳細資訊，請參閱 [管理 Microsoft 365 群組中的來賓存取權](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups?view=o365-worldwide#manage-groups-guest-access)以及[Microsoft 365 群組的來賓存取權](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)。</span><span class="sxs-lookup"><span data-stu-id="00b7e-168">See [Manage guest access in Microsoft 365 groups](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups?view=o365-worldwide#manage-groups-guest-access) and [Guest access in Microsoft 365 Groups](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6) for more information about guest access in groups, including how guest access works, how to manage guest access, and answers to frequently asked questions.</span></span>

## <a name="control-guest-access-to-sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="00b7e-169">控制 SharePoint Online 和商務用 OneDrive 的來賓存取</span><span class="sxs-lookup"><span data-stu-id="00b7e-169">Control guest access to SharePoint Online and OneDrive for Business</span></span>

<span data-ttu-id="00b7e-170">Teams 需要 SharePoint Online 和商務用 OneDrive 來儲存頻道和聊天交談的檔案和文件。</span><span class="sxs-lookup"><span data-stu-id="00b7e-170">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span>  

<span data-ttu-id="00b7e-171">如需完整的 Teams 來賓存取體驗，Microsoft 365 及 Office 365 系統管理員必須設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="00b7e-171">For the full Teams guest access experience, Microsoft 365 and Office 365 admins need to configure the following settings:</span></span>

- <span data-ttu-id="00b7e-172">在 SharePoint Online：選取 **[現有的來賓]**、**[新的及現有來賓]** 或 **[任何人]**。</span><span class="sxs-lookup"><span data-stu-id="00b7e-172">In SharePoint Online: Select **Existing guests**, **New and existing guests**, or **Anyone**.</span></span>

    <span data-ttu-id="00b7e-173">如需詳細資訊，請參閱[開啟或關閉外部共用](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)。</span><span class="sxs-lookup"><span data-stu-id="00b7e-173">For more information, see [Turn external sharing on or off](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off).</span></span>

- <span data-ttu-id="00b7e-174">在 Microsoft 365 群組：開啟 **[讓群組擁有者將貴組織外部的人員新增到群組]**</span><span class="sxs-lookup"><span data-stu-id="00b7e-174">In Microsoft 365 Groups: Turn on **Let group owners add people outside the organization to groups**</span></span>

    <span data-ttu-id="00b7e-175">如需詳細資訊，請參閱上述的[控制 Microsoft 365 群組的來賓存取](#control-guest-access-in-microsoft-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="00b7e-175">For more information, see [Control guest access in Microsoft 365 Groups](#control-guest-access-in-microsoft-365-groups), above.</span></span>
  
<span data-ttu-id="00b7e-176">這些設定會套用到租用戶層級，控制 SharePoint Online、商務用 OneDrive、Microsoft 365 群組和 Teams 中的來賓體驗。</span><span class="sxs-lookup"><span data-stu-id="00b7e-176">These settings apply at the tenant level and control the guest experience in SharePoint Online, OneDrive for Business, Microsoft 365 Groups, and Teams.</span></span>

<span data-ttu-id="00b7e-177">針對連接至 Teams 的小組網站，您可以管理 SharePoint Online 外部使用者設定。</span><span class="sxs-lookup"><span data-stu-id="00b7e-177">You can manage SharePoint Online external user settings for the team sites connected to Teams.</span></span> <span data-ttu-id="00b7e-178">若要深入了解，請參閱[管理 SharePoint 小組網站設定](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)。</span><span class="sxs-lookup"><span data-stu-id="00b7e-178">To learn more, see  [Manage your SharePoint team site settings](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="00b7e-179">外部存取 (同盟) 與來賓存取</span><span class="sxs-lookup"><span data-stu-id="00b7e-179">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a><span data-ttu-id="00b7e-180">相關主題</span><span class="sxs-lookup"><span data-stu-id="00b7e-180">Related topics</span></span>

- [<span data-ttu-id="00b7e-181">Microsoft 365 來賓共用設定參考</span><span class="sxs-lookup"><span data-stu-id="00b7e-181">Microsoft 365 guest sharing settings reference</span></span>](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)
