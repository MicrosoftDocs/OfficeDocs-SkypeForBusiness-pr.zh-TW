---
title: 管理 Microsoft 團隊中的來賓存取權
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解如何建立您的第一份團隊與頻道、快速使用中的應用程式、監視器使用量與意見反應，以及取得資源以規劃貴組織內的推出。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 83f4e4cdff4515f89a5b3fe68c91d848f9ae5dda
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326450"
---
<a name="manage-guest-access-in-microsoft-teams"></a><span data-ttu-id="aec6a-103">管理 Microsoft 團隊中的來賓存取權</span><span class="sxs-lookup"><span data-stu-id="aec6a-103">Manage guest access in Microsoft Teams</span></span>
======================================

> [!IMPORTANT]
> <span data-ttu-id="aec6a-104">您可能需要等候幾個小時，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="aec6a-104">You may have to wait a few hours for your changes to take effect.</span></span> 

<span data-ttu-id="aec6a-105">**來賓**是 microsoft 團隊中的使用者類型，包括所有 Microsoft 365 商務標準版、Office 365 企業版、Microsoft 365 Business Basic 及 Office 365 教育版訂閱。</span><span class="sxs-lookup"><span data-stu-id="aec6a-105">**Guest** is a user type in Microsoft Teams that is included with all Microsoft 365 Business Standard, Office 365 Enterprise, Microsoft 365 Business Basic, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="aec6a-106">您不需要額外的 Office 365 授權。</span><span class="sxs-lookup"><span data-stu-id="aec6a-106">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="aec6a-107">請參閱以下有關[來賓存取授權](#guest-access-licensing-limits)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="aec6a-107">Read more about [guest access licensing](#guest-access-licensing-limits) below.</span></span>

<span data-ttu-id="aec6a-108">[團隊訪客存取] 是租使用者層級設定，預設為關閉狀態。</span><span class="sxs-lookup"><span data-stu-id="aec6a-108">Teams guest access is a tenant-level setting and is turned off by default.</span></span> <span data-ttu-id="aec6a-109">如需如何開啟來賓存取的詳細資料，請參閱[開啟或關閉對團隊的來賓存取權](set-up-guests.md)，或使用[來賓存取檢查清單](guest-access-checklist.md)逐步引導您完成設定。</span><span class="sxs-lookup"><span data-stu-id="aec6a-109">For details about how to turn on guest access, see [Turn on or turn off guest access to Teams](set-up-guests.md), or use the [Guest access checklist ](guest-access-checklist.md) to walk you through the setup.</span></span>

<span data-ttu-id="aec6a-110">開啟來賓存取之後，您可以使用[管理組織的 [管理團隊設定](enable-features-office-365.md)] 中所述的控制項來設定來賓的設定，並在[轉至新的 Microsoft 團隊系統管理中心時管理團隊](manage-teams-skypeforbusiness-admin-center.md)。</span><span class="sxs-lookup"><span data-stu-id="aec6a-110">After guest access is turned on, you can configure settings for guests using the controls described in [Manage Teams settings for your organization](enable-features-office-365.md) and [Manage Teams during the transition to the new Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md).</span></span>     
    
<span data-ttu-id="aec6a-111">IT 管理員可以在租使用者層級新增來賓、設定及管理來賓使用者原則和許可權，以及拉入來賓使用者活動的報告。</span><span class="sxs-lookup"><span data-stu-id="aec6a-111">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, and pull reports on guest user activity.</span></span> <span data-ttu-id="aec6a-112">這些控制項可在 [團隊管理中心] 中取得。</span><span class="sxs-lookup"><span data-stu-id="aec6a-112">These controls are available in the Teams admin center.</span></span> <span data-ttu-id="aec6a-113">來賓使用者的內容和活動與 Office 365 的其他部分相容性和審核保護的行為低於相同。</span><span class="sxs-lookup"><span data-stu-id="aec6a-113">Guest user content and activities fall under the same compliance and auditing protection as the rest of Office 365.</span></span>

<span data-ttu-id="aec6a-114">小組擁有者可以邀請新的來賓，並將現有的目錄來賓使用者新增至團隊系統管理中心的小組。</span><span class="sxs-lookup"><span data-stu-id="aec6a-114">Team owners can invite new guests and add existing directory guest users to their teams in the Teams admin center.</span></span> <span data-ttu-id="aec6a-115">在 [**團隊**  >  **管理團隊**] 頁面上識別來賓使用者，並針對**組織範圍的 [設定**  >  **來賓存取權**] 頁面上的來賓設定與頻道相關的功能。</span><span class="sxs-lookup"><span data-stu-id="aec6a-115">Identify guest users on the **Teams** > **Manage teams** page, and set channel-related capabilities for guests on the  **Org-wide settings** > **Guest access** page.</span></span> <span data-ttu-id="aec6a-116">[設定] 包括允許來賓建立、更新及刪除頻道，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="aec6a-116">Settings include allowing guests to create, update, and delete channels, as shown in the following illustration.</span></span>

![團隊中的來賓許可權設定](media/manage-guest-access-image1.png)
  
<span data-ttu-id="aec6a-118">您可以使用 Azure Active Directory （Azure AD）入口網站來管理來賓及其對 Office 365 和團隊資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="aec6a-118">You can use the Azure Active Directory (Azure AD) portal to manage guests and their access to Office 365 and Teams resources.</span></span> <span data-ttu-id="aec6a-119">團隊訪客存取可使用 Azure AD 企業對企業（B2B）共同作業功能做為基礎基礎結構，以儲存身分識別屬性、成員資格以及多重要素驗證設定等安全性原則資訊。</span><span class="sxs-lookup"><span data-stu-id="aec6a-119">Teams guest access makes use of Azure AD business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="aec6a-120">若要深入瞭解 Azure AD B2B，請參閱[什麼是 AZURE AD b2b 共同作業？](https://go.microsoft.com/fwlink/p/?linkid=853011)以及[AZURE Active Directory b2b 合作常見問題](https://go.microsoft.com/fwlink/p/?linkid=853020)。</span><span class="sxs-lookup"><span data-stu-id="aec6a-120">To learn more about Azure AD B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>

> [!NOTE]
> <span data-ttu-id="aec6a-121">Microsoft 團隊永遠會採用 Azure AD 外部設定，以允許或禁止來賓使用者新增至租使用者。</span><span class="sxs-lookup"><span data-stu-id="aec6a-121">Microsoft Teams always honors Azure AD external settings to allow or prevent guest user additions to the tenant.</span></span> <span data-ttu-id="aec6a-122">如需詳細資訊，請參閱[授權 Microsoft 團隊中的來賓存取](Teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="aec6a-122">For more details, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>


## <a name="guest-access-licensing-limits"></a><span data-ttu-id="aec6a-123">來賓存取授許可權制</span><span class="sxs-lookup"><span data-stu-id="aec6a-123">Guest access licensing limits</span></span>

<span data-ttu-id="aec6a-124">Teams 未限制您可以新增的來賓數量。</span><span class="sxs-lookup"><span data-stu-id="aec6a-124">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="aec6a-125">然而，可以新增至租用戶的來賓總數會依據您 Azure AD 授權的允許量而定，通常是每位授權使用者允許 5 位來賓。</span><span class="sxs-lookup"><span data-stu-id="aec6a-125">However, the total number of guests that can be added to your tenant is based on what your Azure AD licensing allows - usually 5 guests per licensed user.</span></span> <span data-ttu-id="aec6a-126">如需詳細資訊，請參閱 [Azure AD B2B 共同作業授權](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="aec6a-126">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>

<span data-ttu-id="aec6a-127">由於這些授許可權制（並將您的租使用者保持在最新狀態），因此您應該定期檢查來賓存取權，以找出有權存取不需要的使用者。</span><span class="sxs-lookup"><span data-stu-id="aec6a-127">Because of these licensing limitations (and to keep your tenant up-to-date), you should review guest access periodically to identify users who have access that they don't need anymore.</span></span> <span data-ttu-id="aec6a-128">您可以使用 Azure AD 來建立群組成員或指派給應用程式的使用者的存取權審查。</span><span class="sxs-lookup"><span data-stu-id="aec6a-128">You can use Azure AD to create an access review for group members or users assigned to an application.</span></span> <span data-ttu-id="aec6a-129">建立週期性存取檢查可節省您的時間。</span><span class="sxs-lookup"><span data-stu-id="aec6a-129">Creating recurring access reviews can save you time.</span></span> <span data-ttu-id="aec6a-130">如果您需要例行查看有權存取應用程式或群組成員的使用者，您可以定義這些評論的頻率。</span><span class="sxs-lookup"><span data-stu-id="aec6a-130">If you need to routinely review users who have access to an application or are members of a group, you can define the frequency of those reviews.</span></span> 

<span data-ttu-id="aec6a-131">您可以自行執行來賓存取權審查、要求客人審查自己的成員資格，或是要求應用程式擁有者或商業決策人來執行存取審查。</span><span class="sxs-lookup"><span data-stu-id="aec6a-131">You can perform a guest access review yourself, ask guests to review their own membership, or ask an application owner or business decision maker to perform the access review.</span></span> <span data-ttu-id="aec6a-132">使用 Azure 入口網站執行來賓存取審查。</span><span class="sxs-lookup"><span data-stu-id="aec6a-132">Use the Azure portal to perform guest access reviews.</span></span> <span data-ttu-id="aec6a-133">如需詳細資訊，請參閱[使用 AZURE AD access 評論管理來賓存取](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)。</span><span class="sxs-lookup"><span data-stu-id="aec6a-133">For more information, see [Manage guest access with Azure AD access reviews](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).</span></span>

###  <a name="prerequisites-for-azure-ad-access-reviews"></a><span data-ttu-id="aec6a-134">Azure AD access 評論的先決條件</span><span class="sxs-lookup"><span data-stu-id="aec6a-134">Prerequisites for Azure AD access reviews</span></span>

<span data-ttu-id="aec6a-135">您可以在 Microsoft 企業行動 + 安全性，E5 隨附的高級 P2 版本的 Azure AD 中使用 Access 評論。</span><span class="sxs-lookup"><span data-stu-id="aec6a-135">Access reviews are available with the Premium P2 edition of Azure AD, which is included in Microsoft Enterprise Mobility + Security, E5.</span></span> <span data-ttu-id="aec6a-136">如需詳細資訊，請參閱[Azure Active Directory 版本](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)。</span><span class="sxs-lookup"><span data-stu-id="aec6a-136">For more information, see [Azure Active Directory editions](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="aec6a-137">與此功能互動的每個使用者，只要建立評論、填寫評論或確認其存取權，就必須擁有授權。</span><span class="sxs-lookup"><span data-stu-id="aec6a-137">Each user who interacts with this feature by creating a review, filling out a review, or confirming their access, must have a license.</span></span>



## <a name="lag-time-for-guest-access-settings-to-take-effect"></a><span data-ttu-id="aec6a-138">[來賓存取設定] 生效的延後時間</span><span class="sxs-lookup"><span data-stu-id="aec6a-138">Lag time for guest access settings to take effect</span></span>

<span data-ttu-id="aec6a-139">針對 Azure Active Directory 中的來賓存取設定，您需要幾個小時的時間，變更才會在 Microsoft 365 或 Office 365 上生效。</span><span class="sxs-lookup"><span data-stu-id="aec6a-139">For the guest access settings in Azure Active Directory, it takes a few hours for the changes to take effect across Microsoft 365 or Office 365.</span></span> <span data-ttu-id="aec6a-140">當使用者嘗試將來賓新增到其小組時，如果使用者看到「與您的系統管理員聯繫」的訊息，可能是因為來賓功能尚未開啟，或設定尚未生效。</span><span class="sxs-lookup"><span data-stu-id="aec6a-140">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been turned on or the settings aren't effective yet.</span></span> <span data-ttu-id="aec6a-141">如需設定來賓存取問題的相關說明，請參閱[疑難排解團隊中的來賓存取權](troubleshoot-guest-access.md)。</span><span class="sxs-lookup"><span data-stu-id="aec6a-141">For help with problems setting up guest access, read [Troubleshoot guest access in Teams](troubleshoot-guest-access.md).</span></span>

  
## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="aec6a-142">外部存取 (同盟) 與來賓存取</span><span class="sxs-lookup"><span data-stu-id="aec6a-142">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="aec6a-143">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="aec6a-143">More information</span></span>

<span data-ttu-id="aec6a-144">如需使用 PowerShell 來管理來賓存取的相關資訊，請參閱[使用 powershell 控制對團隊的來賓存取權](guest-access-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="aec6a-144">For information about using PowerShell to manage guest access, see [Use PowerShell to control guest access to a team](guest-access-powershell.md).</span></span>


