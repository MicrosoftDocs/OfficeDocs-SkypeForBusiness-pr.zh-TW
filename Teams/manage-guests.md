---
title: 管理 Microsoft 團隊中的來賓存取權
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: IT 管理員可以在租使用者層級新增來賓、設定及管理來賓使用者原則和許可權、決定哪些使用者可以邀請客人, 以及拉入來賓使用者活動的報告。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0d65060049204f13d32158ba6c21ee18917df154
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2019
ms.locfileid: "36184299"
---
<a name="manage-guest-access-in-microsoft-teams"></a><span data-ttu-id="fd941-103">管理 Microsoft 團隊中的來賓存取權</span><span class="sxs-lookup"><span data-stu-id="fd941-103">Manage guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="fd941-104">**來賓**是 Microsoft 團隊中的使用者/授權類型, 包含在所有 Office 365 商務版 Premium、Office 365 企業版和 Office 365 教育版訂閱中。</span><span class="sxs-lookup"><span data-stu-id="fd941-104">**Guest** is a user/license type in Microsoft Teams that is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="fd941-105">不需要額外的 Office 365 授權。</span><span class="sxs-lookup"><span data-stu-id="fd941-105">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="fd941-106">[團隊訪客存取] 是租使用者層級設定, 預設為關閉狀態。</span><span class="sxs-lookup"><span data-stu-id="fd941-106">Teams guest access is a tenant-level setting and is turned off by default.</span></span> <span data-ttu-id="fd941-107">如需如何啟用來賓存取的詳細資料, 請參閱[開啟或關閉 Microsoft 團隊的來賓存取權](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="fd941-107">For details about how to enable guest access, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>

<span data-ttu-id="fd941-108">開啟**來賓**使用者/授權類型之後, 您可以透過在組織中的 [[管理 Microsoft 團隊設定](enable-features-office-365.md)] 中所述的控制項來設定來賓的設定, 並在[轉換為新的 Microsoft 團隊期間管理團隊。系統管理中心](manage-teams-skypeforbusiness-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="fd941-108">After the **Guest** user/license type is turned on, you can configure settings for guests via the controls described in [Manage Microsoft Teams settings for your organization](enable-features-office-365.md) and [Manage Teams during the transition to the new Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md).</span></span>     
    
<span data-ttu-id="fd941-109">IT 管理員可以在租使用者層級新增來賓、設定及管理來賓使用者原則和許可權, 以及拉入來賓使用者活動的報告。</span><span class="sxs-lookup"><span data-stu-id="fd941-109">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, and pull reports on guest user activity.</span></span> <span data-ttu-id="fd941-110">您可以透過 Microsoft 團隊系統管理中心來使用這些控制項。</span><span class="sxs-lookup"><span data-stu-id="fd941-110">These controls are available through the Microsoft Teams admin center.</span></span> <span data-ttu-id="fd941-111">來賓使用者的內容和活動與 Office 365 的其他部分相容性和審核保護都是相同的。</span><span class="sxs-lookup"><span data-stu-id="fd941-111">Guest user content and activities are under the same compliance and auditing protection as the rest of Office 365.</span></span>

<span data-ttu-id="fd941-112">小組擁有者可以邀請新的來賓, 並將現有的目錄來賓使用者新增至他們的小組。</span><span class="sxs-lookup"><span data-stu-id="fd941-112">Team owners can invite new guests and add existing directory guest users to their teams.</span></span> <span data-ttu-id="fd941-113">團隊擁有者可以透過**團隊** > **管理團隊**來識別來賓使用者, 以及透過**整個組織的設定** > **來賓存取**來設定來賓的頻道相關功能, 包括允許來賓建立、更新及刪除頻道, 如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="fd941-113">Team owners can identify guest users via **Teams** > **Manage teams**, and set channel-related capabilities for guests via **Org-wide settings** > **Guest access**, including allowing guests to create, update, and delete channels, as shown in the following illustration.</span></span>

![團隊中的來賓許可權設定](media/manage-guest-access-image1.png)
  
<span data-ttu-id="fd941-115">您可以使用 Azure Active Directory (Azure AD) 入口網站來管理來賓及其對 Office 365 和團隊資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="fd941-115">You can use the Azure Active Directory (Azure AD) portal to manage guests and their access to Office 365 and Teams resources.</span></span> <span data-ttu-id="fd941-116">團隊訪客存取可使用 Azure AD 企業對企業 (B2B) 共同作業功能做為基礎基礎結構, 以儲存身分識別屬性、成員資格以及多重要素驗證設定等安全性原則資訊。</span><span class="sxs-lookup"><span data-stu-id="fd941-116">Teams guest access makes use of Azure AD business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="fd941-117">若要深入瞭解 Azure AD B2B, 請參閱[什麼是 AZURE AD b2b 共同作業？](https://go.microsoft.com/fwlink/p/?linkid=853011)以及[AZURE Active Directory b2b 合作常見問題](https://go.microsoft.com/fwlink/p/?linkid=853020)。</span><span class="sxs-lookup"><span data-stu-id="fd941-117">To learn more about Azure AD B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>

> [!NOTE]
> <span data-ttu-id="fd941-118">Microsoft 團隊永遠會採用 Azure AD 外部設定, 以允許或禁止來賓使用者新增至租使用者。</span><span class="sxs-lookup"><span data-stu-id="fd941-118">Microsoft Teams always honors Azure AD external settings to allow or prevent guest user additions to the tenant.</span></span> <span data-ttu-id="fd941-119">如需詳細資訊, 請參閱[授權 Microsoft 團隊中的來賓存取](Teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="fd941-119">For more details, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
  
## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="fd941-120">來賓存取與外部存取 (同盟)</span><span class="sxs-lookup"><span data-stu-id="fd941-120">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="review-guest-access-periodically"></a><span data-ttu-id="fd941-121">定期審查來賓存取權</span><span class="sxs-lookup"><span data-stu-id="fd941-121">Review guest access periodically</span></span>

<span data-ttu-id="fd941-122">在 [團隊] 中, 您可以為每個授權的使用者新增5個來賓。</span><span class="sxs-lookup"><span data-stu-id="fd941-122">In Teams, you can add 5 guests for each licensed user.</span></span> <span data-ttu-id="fd941-123">由於這項限制, 或由於您想要將您的租使用者保持在最新狀態, 因此您應該定期檢查來賓存取權, 以找出有存取權並不需要的使用者。</span><span class="sxs-lookup"><span data-stu-id="fd941-123">Because of this limitation, or because you want to keep your tenant up to date, you should review guest access periodically to identify users who have access that they don't need anymore.</span></span> <span data-ttu-id="fd941-124">您可以使用 Azure AD 來建立群組成員或指派給應用程式的使用者的存取權審查。</span><span class="sxs-lookup"><span data-stu-id="fd941-124">You can use Azure AD to create an access review for group members or users assigned to an application.</span></span> <span data-ttu-id="fd941-125">建立週期性存取檢查可節省您的時間。</span><span class="sxs-lookup"><span data-stu-id="fd941-125">Creating recurring access reviews can save you time.</span></span> <span data-ttu-id="fd941-126">如果您需要例行查看有權存取應用程式或群組成員的使用者, 您可以定義這些評論的頻率。</span><span class="sxs-lookup"><span data-stu-id="fd941-126">If you need to routinely review users who have access to an application or are members of a group, you can define the frequency of those reviews.</span></span> 

<span data-ttu-id="fd941-127">您可以自行執行來賓存取權審查、要求客人審查自己的成員資格, 或是要求應用程式擁有者或商業決策人來執行存取審查。</span><span class="sxs-lookup"><span data-stu-id="fd941-127">You can perform a guest access review yourself, ask guests to review their own membership, or ask an application owner or business decision maker to perform the access review.</span></span> <span data-ttu-id="fd941-128">您使用 Azure 入口網站來執行來賓存取審查。</span><span class="sxs-lookup"><span data-stu-id="fd941-128">You use the Azure portal to perform guest access reviews.</span></span> <span data-ttu-id="fd941-129">如需詳細資訊, 請參閱[使用 AZURE AD access 評論管理來賓存取](https://docs.microsoft.com/en-us/azure/active-directory/governance/manage-guest-access-with-access-reviews)。</span><span class="sxs-lookup"><span data-stu-id="fd941-129">For more information, see [Manage guest access with Azure AD access reviews](https://docs.microsoft.com/en-us/azure/active-directory/governance/manage-guest-access-with-access-reviews).</span></span>

###  <a name="prerequisites"></a><span data-ttu-id="fd941-130">先決條件</span><span class="sxs-lookup"><span data-stu-id="fd941-130">Prerequisites</span></span>

<span data-ttu-id="fd941-131">您可以在 Microsoft 企業行動 + 安全性, E5 隨附的高級 P2 版本的 Azure AD 中使用 Access 評論。</span><span class="sxs-lookup"><span data-stu-id="fd941-131">Access reviews are available with the Premium P2 edition of Azure AD, which is included in Microsoft Enterprise Mobility + Security, E5.</span></span> <span data-ttu-id="fd941-132">如需詳細資訊, 請參閱[Azure Active Directory 版本](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis)。</span><span class="sxs-lookup"><span data-stu-id="fd941-132">For more information, see [Azure Active Directory editions](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="fd941-133">與此功能互動的每個使用者, 只要建立評論、填寫評論或確認其存取權, 就必須擁有授權。</span><span class="sxs-lookup"><span data-stu-id="fd941-133">Each user who interacts with this feature by creating a review, filling out a review, or confirming their access, must have a license.</span></span>

<span data-ttu-id="fd941-134">小組不會限制您可以新增的來賓數目。</span><span class="sxs-lookup"><span data-stu-id="fd941-134">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="fd941-135">不過, 可以新增到您租使用者的來賓總數, 就是根據 AAD 授權所允許的專案數目。</span><span class="sxs-lookup"><span data-stu-id="fd941-135">However, the total number of guests that can be added to your tenant is based on what your AAD licensing allows.</span></span> <span data-ttu-id="fd941-136">如需詳細資訊, 請參閱[AZURE AD B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance)共同版授權。</span><span class="sxs-lookup"><span data-stu-id="fd941-136">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span></span>

## <a name="guest-access-latencies"></a><span data-ttu-id="fd941-137">來賓存取延遲</span><span class="sxs-lookup"><span data-stu-id="fd941-137">Guest access latencies</span></span>

<span data-ttu-id="fd941-138">來賓設定是在 Azure AD 中設定。</span><span class="sxs-lookup"><span data-stu-id="fd941-138">The guest settings are set in Azure AD.</span></span> <span data-ttu-id="fd941-139">在您的 Office 365 組織中, 變更的時間必須是2小時到24小時才能生效。</span><span class="sxs-lookup"><span data-stu-id="fd941-139">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="fd941-140">當使用者嘗試將來賓新增到其小組時, 如果使用者看到「與您的系統管理員聯繫」的訊息, 可能是因為來賓功能尚未啟用或設定尚未生效。</span><span class="sxs-lookup"><span data-stu-id="fd941-140">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings aren't effective yet.</span></span>

## <a name="more-information"></a><span data-ttu-id="fd941-141">其他資訊</span><span class="sxs-lookup"><span data-stu-id="fd941-141">More information</span></span>

<span data-ttu-id="fd941-142">如需使用 PowerShell 來管理來賓存取的相關資訊, 請參閱[使用 powershell 控制對團隊的來賓存取權](guest-access-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="fd941-142">For information about using PowerShell to manage guest access, see [Use PowerShell to control guest access to a team](guest-access-powershell.md).</span></span>


