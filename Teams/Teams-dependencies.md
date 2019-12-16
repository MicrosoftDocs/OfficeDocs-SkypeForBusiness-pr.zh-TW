---
title: 在 Microsoft Teams 中授權來賓存取
author: lanachin
ms.author: v-lanac
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
description: 透過四種不同的授權等級管理 Microsoft Teams 的來賓存取功能。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 200e0d94948d735786fd1775fc803c6017bd3100
ms.sourcegitcommit: c15ab82834005b9a19247e06488f1f21161fc426
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/13/2019
ms.locfileid: "40019977"
---
<a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="47c8b-103">在 Microsoft Teams 中授權來賓存取</span><span class="sxs-lookup"><span data-stu-id="47c8b-103">Authorize guest access in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="47c8b-104">為滿足貴組織的需求，您可以透過四種不同的授權等級管理 Microsoft Teams 的來賓存取功能。</span><span class="sxs-lookup"><span data-stu-id="47c8b-104">To satisfy your organization’s requirements, you can manage Microsoft Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="47c8b-105">所有授權等級都適用於您的 Office 365 租用戶。</span><span class="sxs-lookup"><span data-stu-id="47c8b-105">All the authorization levels apply to your Office 365 tenant.</span></span> <span data-ttu-id="47c8b-106">每個授權等級控制的來賓體驗如下所示：</span><span class="sxs-lookup"><span data-stu-id="47c8b-106">Each authorization level controls the guest experience as shown below:</span></span>

- <span data-ttu-id="47c8b-107">**Azure Active Directory**：Microsoft Teams 的來賓存取需要 Azure AD 企業對企業 (B2B) 平台。</span><span class="sxs-lookup"><span data-stu-id="47c8b-107">**Azure Active Directory**: Guest access in Microsoft Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="47c8b-108">此授權等級控制目錄、租用戶和應用程式層級的來賓體驗。</span><span class="sxs-lookup"><span data-stu-id="47c8b-108">This authorization level controls the guest experience at the directory, tenant, and application level.</span></span>
- <span data-ttu-id="47c8b-109">**Microsoft Teams**：僅控制 Microsoft Teams 中的來賓體驗。</span><span class="sxs-lookup"><span data-stu-id="47c8b-109">**Microsoft Teams**: Controls the guest experience in Microsoft Teams only.</span></span>
- <span data-ttu-id="47c8b-110">**Office 365 群組**：控制 Office 365 群組和 Microsoft Teams 中的來賓體驗。</span><span class="sxs-lookup"><span data-stu-id="47c8b-110">**Office 365 Groups**: Controls the guest experience in Office 365 Groups and Microsoft Teams.</span></span>
- <span data-ttu-id="47c8b-111">**SharePoint Online 和商務用 OneDrive**：控制 SharePoint Online、商務用 OneDrive、Office 365 群組和 Microsoft Teams 中的來賓體驗。</span><span class="sxs-lookup"><span data-stu-id="47c8b-111">**SharePoint Online and OneDrive for Business**: Controls the guest experience in SharePoint Online, OneDrive for Business, Office 365 Groups, and Microsoft Teams.</span></span>

<span data-ttu-id="47c8b-112">這些不同的授權等級能夠讓您彈性設定貴組織的來賓存取。</span><span class="sxs-lookup"><span data-stu-id="47c8b-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="47c8b-113">例如，如果您不想在 Microsoft Teams 中允許來賓使用者，但是想要在貴組織中全面允許來賓使用者，只要在 Microsoft Teams 中關閉來賓存取即可。</span><span class="sxs-lookup"><span data-stu-id="47c8b-113">For example, if you don’t want to allow guest users in your Microsoft Teams but want to allow it overall in your organization, just turn off guest access in Microsoft Teams.</span></span> <span data-ttu-id="47c8b-114">另一個範例：您可以啟用 Azure AD、Microsoft Teams 和群組等級的來賓存取，但是接著在符合一或多個準則 (例如資料分類等於機密) 的小組中，停用所選小組的新增來賓使用者功能。</span><span class="sxs-lookup"><span data-stu-id="47c8b-114">Another example: You could enable guest access at the Azure AD, Teams, and Groups levels, but then disable the addition of guest users on selected teams that match one or more criteria such as data classification equals confidential.</span></span> <span data-ttu-id="47c8b-115">SharePoint Online 和商務用 OneDrive 擁有自己的來賓存取設定，不需要依賴 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="47c8b-115">SharePoint Online and OneDrive for Business have their own guest access settings that don't rely on Office 365 Groups.</span></span>

> [!NOTE]
> <span data-ttu-id="47c8b-116">來賓須遵守 [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 的服務限制。</span><span class="sxs-lookup"><span data-stu-id="47c8b-116">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span> 

<span data-ttu-id="47c8b-117">以下圖表顯示在 Azure Active Directory、Microsoft Teams 和 Office 365 之間，來賓存取之授權相依性的授權方式和整合。</span><span class="sxs-lookup"><span data-stu-id="47c8b-117">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Microsoft Teams, and Office 365.</span></span>

![來賓存取的授權相依性圖表。](media/teams_dependencies_image1.png)

<span data-ttu-id="47c8b-119">以下圖表以高等級的角度，顯示透過一般來賓存取的邀請與兌換流程，使用者體驗搭配權限模型的運作方式。</span><span class="sxs-lookup"><span data-stu-id="47c8b-119">The next diagram shows, at a high level, how the user experience works with the permission model through a typical guest access invitation and redemption flow.</span></span>

![邀請與兌換流程圖表](media/authorize-guest-image1.png)

<span data-ttu-id="47c8b-121">此處請特別注意，應用程式、Bot 和連接器可能需要各自的權限集和/或使用者帳戶專屬的同意。</span><span class="sxs-lookup"><span data-stu-id="47c8b-121">It’s important to note here that apps, bots, and connectors might require their own set of permissions and/or consent specific to the user account.</span></span> <span data-ttu-id="47c8b-122">這些情況可能需要個別授權。</span><span class="sxs-lookup"><span data-stu-id="47c8b-122">These might need to be granted separately.</span></span> <span data-ttu-id="47c8b-123">同樣地，SharePoint 可能會針對特定使用者、使用者群組或甚至是在網站層級，強制規定額外的外部共用界限。</span><span class="sxs-lookup"><span data-stu-id="47c8b-123">Similarly, SharePoint might impose extra external sharing boundaries for a specific user, groups of users, or even at the site level.</span></span>

<span data-ttu-id="47c8b-124">以上兩張圖表也可以在 [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true) 中使用。</span><span class="sxs-lookup"><span data-stu-id="47c8b-124">The previous two diagrams are also available in [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true).</span></span>

## <a name="control-guest-access-in-azure-active-directory"></a><span data-ttu-id="47c8b-125">控制 Azure Active Directory 的來賓存取</span><span class="sxs-lookup"><span data-stu-id="47c8b-125">Control guest access in Azure Active Directory</span></span>

<span data-ttu-id="47c8b-126">使用 Azure AD 來判斷外部共同作業者是否能以來賓身分受邀進入您的租用戶，以及採取何種方式。</span><span class="sxs-lookup"><span data-stu-id="47c8b-126">Use Azure AD to determine whether external collaborators can be invited into your tenant as guests, and in what ways.</span></span> <span data-ttu-id="47c8b-127">如需 Azure B2B 來賓存取的詳細資訊，請參閱[什麼是 Azure Active Directory B2B 中的來賓使用者存取權](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)。</span><span class="sxs-lookup"><span data-stu-id="47c8b-127">For more information about Azure B2B guest access, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span></span> <span data-ttu-id="47c8b-128">如需 Azure AD 角色的詳細資訊，請參閱[從 Azure Active Directory 租用戶中的合作夥伴組織授與權限給使用者](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role)。</span><span class="sxs-lookup"><span data-stu-id="47c8b-128">For information about Azure AD roles, see [Grant permissions to users from partner organizations in your Azure Active Directory tenant](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role).</span></span>

<span data-ttu-id="47c8b-129">邀請的設定會套用到租用戶層級，然後在目錄、租用戶和應用程式層級控制來賓體驗。</span><span class="sxs-lookup"><span data-stu-id="47c8b-129">The settings for invitations apply at the tenant level and control the guest experience at the directory, tenant, and application level.</span></span> <span data-ttu-id="47c8b-130">若要在 Azure 入口網站設定這些設定，前往 [Azure Active Directory]\*\*\*\* > [使用者]\*\*\*\* > [使用者設定]\*\*\*\*，在 [外部使用者]\*\*\*\* 之下，選取 [管理外部共同作業設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="47c8b-130">To configure these settings in the Azure portal, go to **Azure Active Directory** > **Users** > **User settings**, and under **External users**, select **Manage external collaboration settings**.</span></span>

<span data-ttu-id="47c8b-131">Azure AD 包含有下列設定可設定外部使用者：</span><span class="sxs-lookup"><span data-stu-id="47c8b-131">Azure AD includes the following settings to configure external users:</span></span>

- <span data-ttu-id="47c8b-132">[來賓使用者權限受限]\*\*\*\*：[是]\*\*\*\* 表示來賓沒有某些目錄工作的權限，例如列舉使用者、群組或其他目錄資源。</span><span class="sxs-lookup"><span data-stu-id="47c8b-132">**Guest user permissions are limited**: **Yes** means that guests don't have permission for certain directory tasks, such as enumerate users, groups, or other directory resources.</span></span> <span data-ttu-id="47c8b-133">此外，來賓不能指派為您目錄中的系統管理角色。</span><span class="sxs-lookup"><span data-stu-id="47c8b-133">In addition, guests can't be assigned to administrative roles in your directory.</span></span> <span data-ttu-id="47c8b-134">[否]\*\*\*\* 表示來賓與您目錄中的一般使用者一樣，擁有相同的目錄資料存取權。</span><span class="sxs-lookup"><span data-stu-id="47c8b-134">**No** means that guests have the same access to directory data that regular users have in your directory.</span></span>
- <span data-ttu-id="47c8b-135">[系統管理員與來賓邀請者角色中的使用者可以邀請]\*\*\*\*：[是]\*\*\*\* 表示系統管理員和來賓邀請者角色中的使用者將可以邀請來賓加入租用戶。</span><span class="sxs-lookup"><span data-stu-id="47c8b-135">**Admins and users in the guest inviter role can invite**: **Yes** means that admins and users in the guest inviter role will be able to invite guests to the tenant.</span></span> <span data-ttu-id="47c8b-136">[否]\*\*\*\* 表示系統管理員和使用者無法邀請來賓加入租用戶。</span><span class="sxs-lookup"><span data-stu-id="47c8b-136">**No** means admins and users can't invite guests to the tenant.</span></span>
- <span data-ttu-id="47c8b-137">[成員可邀請]\*\*\*\*：[是]\*\*\*\* 表示目錄中的非系統管理員成員可以邀請來賓，在受 Azure AD 保護的資源 (例如 SharePoint 網站或 Azure 資源) 上共同作業。</span><span class="sxs-lookup"><span data-stu-id="47c8b-137">**Members can invite**: **Yes** means that non-admin members of your directory can invite guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="47c8b-138">[否]\*\*\*\* 表示僅系統管理員可以邀請來賓加入目錄。</span><span class="sxs-lookup"><span data-stu-id="47c8b-138">**No** means that only admins can invite guests to your directory.</span></span></br>
      
    > [!IMPORTANT]
    > <span data-ttu-id="47c8b-139">若要讓來賓存取能在 Teams 中完整運作，您必須將 [成員可邀請]\*\*\*\* 設定為 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="47c8b-139">For guest access to work at all in Teams, you must set **Members can invite** to **Yes**.</span></span>
- <span data-ttu-id="47c8b-140">[來賓可邀請]\*\*\*\*：[是]\*\*\*\* 表示目錄中的來賓可以邀請其他來賓，在受 Azure AD 保護的資源 (例如 SharePoint 網站或 Azure 資源) 上共同作業。</span><span class="sxs-lookup"><span data-stu-id="47c8b-140">**Guests can invite**: **Yes** means that guests in your directory can invite other guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="47c8b-141">[否]\*\*\*\* 表示來賓無法邀請其他來賓與貴組織共同作業。</span><span class="sxs-lookup"><span data-stu-id="47c8b-141">**No** means that guests can't invite other guests to collaborate with your organization.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="47c8b-142">Teams 目前不支援來賓邀請者角色，因此，即使您將 [來賓可邀請]\*\*\*\* 設定為 [是]\*\*\*\*，來賓仍無法在 Teams 中邀請其他來賓。</span><span class="sxs-lookup"><span data-stu-id="47c8b-142">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
 
<span data-ttu-id="47c8b-143">如需有關控制誰可以邀請來賓的詳細資訊，請參閱[委派 Azure Active Directory B2B 共同作業邀請](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)。</span><span class="sxs-lookup"><span data-stu-id="47c8b-143">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

> [!NOTE]
> <span data-ttu-id="47c8b-144">您也可以管理哪些網域可以做為來賓受邀加入您的租用戶。</span><span class="sxs-lookup"><span data-stu-id="47c8b-144">You can also manage which domains can be invited into your tenant as guests.</span></span> <span data-ttu-id="47c8b-145">請參閱[允許/封鎖來賓獲得 Office 365 群組的存取權限](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="47c8b-145">See [Allow/Block guest access to Office 365 Groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups).</span></span>

<span data-ttu-id="47c8b-146">您不需要將使用者來賓帳戶手動新增到 Azure AD B2B，因為當您將來賓新增到 Teams 時，帳戶會自動新增到目錄。</span><span class="sxs-lookup"><span data-stu-id="47c8b-146">Adding the user guest account manually to Azure AD B2B is not required, as the account will be added to the directory automatically when you add the guest to Teams.</span></span>

### <a name="licensing-for-guest-access"></a><span data-ttu-id="47c8b-147">來賓存取的授權</span><span class="sxs-lookup"><span data-stu-id="47c8b-147">Licensing for guest access</span></span>
<span data-ttu-id="47c8b-148">來賓存取的授權是 Azure AD 授權的一部分。</span><span class="sxs-lookup"><span data-stu-id="47c8b-148">Guest access licensing is part of Azure AD licensing.</span></span> <span data-ttu-id="47c8b-149">來賓存取隨附於所有 Office 365 商務進階版和 Office 365 企業版訂閱。</span><span class="sxs-lookup"><span data-stu-id="47c8b-149">Guest access is included with all OFfice 365 Business Premium and Office 365 Enterprise subscriptions.</span></span> <span data-ttu-id="47c8b-150">如需有關授權的詳細資訊，請參閱 [Azure Active Directory B2B 共同作業授權指引](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="47c8b-150">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>


> [!NOTE]
> <span data-ttu-id="47c8b-151">僅擁有獨立版 Office 365 訂閱方案 (例如 Exchange Online Plan 2) 的組織使用者將無法受邀為貴組織的來賓，因為 Teams 認為這些使用者屬於相同的組織。</span><span class="sxs-lookup"><span data-stu-id="47c8b-151">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="47c8b-152">若要讓這些使用者使用 Teams，這些使用者必須獲派 Office 365 商務進階版、Office 365 企業版或 Office 365 教育版訂閱。</span><span class="sxs-lookup"><span data-stu-id="47c8b-152">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="control-guest-access-in-teams"></a><span data-ttu-id="47c8b-153">控制 Teams 的來賓存取</span><span class="sxs-lookup"><span data-stu-id="47c8b-153">Control guest access in Teams</span></span>

<span data-ttu-id="47c8b-154">Teams 的來賓存取依預設會關閉。</span><span class="sxs-lookup"><span data-stu-id="47c8b-154">Guest access is turned off by default in Teams.</span></span> <span data-ttu-id="47c8b-155">若要開啟來賓存取，請參閱[開啟或關閉 Microsoft Teams 的來賓存取](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="47c8b-155">To turn on guest access, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span> 


## <a name="control-guest-access-in-office-365-groups"></a><span data-ttu-id="47c8b-156">控制 Office 365 群組的來賓存取</span><span class="sxs-lookup"><span data-stu-id="47c8b-156">Control guest access in Office 365 Groups</span></span>

<span data-ttu-id="47c8b-157">在 Office 365 群組中，您可以控制貴組織中所有 Office 365 群組和 Microsoft Teams 小組的新增來賓使用者和來賓存取。</span><span class="sxs-lookup"><span data-stu-id="47c8b-157">From Office 365 Groups, you can control adding guest users and guest access to all Office 365 Groups and Microsoft Teams teams in your organization.</span></span>

1. <span data-ttu-id="47c8b-158">使用您的 Office 365 全域系統管理員帳戶登入 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)。</span><span class="sxs-lookup"><span data-stu-id="47c8b-158">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>

2. <span data-ttu-id="47c8b-159">在左側，選擇 [設定]\*\*\*\*，然後選取 [服務]**&amp; [增益集]**。</span><span class="sxs-lookup"><span data-stu-id="47c8b-159">On the left, choose **Settings** and then select **Services &amp; add-ins**.</span></span>

3. <span data-ttu-id="47c8b-160">選取 [Office 365 群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="47c8b-160">Select **Office 365 Groups**.</span></span>

     ![[設定] 中的 [Office 365 群組] 螢幕擷取畫面](media/authorize-guest-image2.png)
  
4. <span data-ttu-id="47c8b-162">在 [Office 365 群組] 頁面上，根據您是否想讓貴組織外部的小組和群組擁有者存取 Office 365 群組而定，將開關切換為 [開啟]\*\*\*\* 或 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="47c8b-162">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending on whether you want to let team and group owners outside your organization access Office 365 Groups.</span></span> <span data-ttu-id="47c8b-163">按一下或點選 [讓群組擁有者將貴組織外部的人員新增到群組]\*\*\*\* 旁的 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="47c8b-163">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span> <span data-ttu-id="47c8b-164">如果您將開關切換為 [開啟]\*\*\*\*，您會看到另一個用來控制是否要讓群組和小組擁有者將組織外部人員新增至 Office 365 群組和 Microsoft Teams 的選項。</span><span class="sxs-lookup"><span data-stu-id="47c8b-164">If you turn this toggle to **On**, you'll see another option to control whether you want to let group and team owners add people outside your organization to Office 365 Groups and Microsoft Teams.</span></span> <span data-ttu-id="47c8b-165">如果您想讓群組和小組擁有者新增來賓使用者，請將此開關設定為 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="47c8b-165">Set this toggle to **On** if you want to let group and team owners add guest users.</span></span> 
 
   ![[Office 365 群組] 面板及選項已開啟的螢幕擷取畫面](media/authorize-guest-image3.png)

<span data-ttu-id="47c8b-167">這些設定會套用到租用戶層級，控制 Office 365 群組和 Teams 中的來賓體驗。</span><span class="sxs-lookup"><span data-stu-id="47c8b-167">These settings apply at the tenant level and control the guest experience in Office 365 Groups and Teams.</span></span>

<span data-ttu-id="47c8b-168">如需有關群組中的來賓存取，包括來賓存取的運作方式、來賓存取的管理方法以及常見問題的解答等詳細資訊，請參閱 [Office 365 群組的來賓存取權](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)。</span><span class="sxs-lookup"><span data-stu-id="47c8b-168">See [Guest access in Office 365 Groups](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6) for more information about guest access in groups, including how guest access works, how to manage guest access, and answers to frequently asked questions.</span></span>

## <a name="control-guest-access-to-sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="47c8b-169">控制 SharePoint Online 和商務用 OneDrive 的來賓存取</span><span class="sxs-lookup"><span data-stu-id="47c8b-169">Control guest access to SharePoint Online and OneDrive for Business</span></span>

<span data-ttu-id="47c8b-170">Teams 需要 SharePoint Online 和商務用 OneDrive 來儲存頻道和聊天交談的檔案和文件。</span><span class="sxs-lookup"><span data-stu-id="47c8b-170">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span>  

<span data-ttu-id="47c8b-171">如需完整的 Teams 來賓存取體驗，Office 365 系統管理員必須設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="47c8b-171">For the full Teams guest access experience, Office 365 admins need to configure the following settings:</span></span>

- <span data-ttu-id="47c8b-172">在 SharePoint Online：選取 [現有的來賓]\*\*\*\*、[新的及現有來賓]\*\*\*\* 或 [任何人]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="47c8b-172">In SharePoint Online: Select **Existing guests**, **New and existing guests**, or **Anyone**.</span></span>

    <span data-ttu-id="47c8b-173">如需詳細資訊，請參閱[開啟或關閉外部共用](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)。</span><span class="sxs-lookup"><span data-stu-id="47c8b-173">For more information, see [Turn external sharing on or off](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off).</span></span>

- <span data-ttu-id="47c8b-174">在 Office 365 群組：開啟 [讓群組擁有者將貴組織外部的人員新增到群組]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="47c8b-174">In Office 365 Groups: Turn on **Let group owners add people outside the organization to groups**</span></span>

    <span data-ttu-id="47c8b-175">如需詳細資訊，請參閱上述的[控制 Office 365 群組的來賓存取](#control-guest-access-in-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="47c8b-175">For more information, see [Control guest access in Office 365 Groups](#control-guest-access-in-office-365-groups), above.</span></span>
  
<span data-ttu-id="47c8b-176">這些設定會套用到租用戶層級，控制 SharePoint Online、商務用 OneDrive、Office 365 群組和 Teams 中的來賓體驗。</span><span class="sxs-lookup"><span data-stu-id="47c8b-176">These settings apply at the tenant level and control the guest experience in SharePoint Online, OneDrive for Business, Office 365 Groups, and Teams.</span></span>

<span data-ttu-id="47c8b-177">針對連接至 Teams 的小組網站，您可以管理 SharePoint Online 外部使用者設定。</span><span class="sxs-lookup"><span data-stu-id="47c8b-177">You can manage SharePoint Online external user settings for the team sites connected to Teams.</span></span> <span data-ttu-id="47c8b-178">若要深入了解，請參閱[管理 SharePoint 小組網站設定](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)。</span><span class="sxs-lookup"><span data-stu-id="47c8b-178">To learn more, see  [Manage your SharePoint team site settings](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="47c8b-179">外部存取 (同盟) 與來賓存取</span><span class="sxs-lookup"><span data-stu-id="47c8b-179">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a><span data-ttu-id="47c8b-180">相關主題</span><span class="sxs-lookup"><span data-stu-id="47c8b-180">Related topics</span></span>

- [<span data-ttu-id="47c8b-181">Microsoft 365 來賓共用設定參考</span><span class="sxs-lookup"><span data-stu-id="47c8b-181">Microsoft 365 guest sharing settings reference</span></span>](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)
