---
title: Microsoft Teams 中的來賓存取
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
description: Microsoft Teams 中的來賓存取可將團隊和頻道的存取權授與給組織外部人員，讓貴組織中的團隊與組織外部的人員共同作業。
ms.openlocfilehash: f04fce7f75df32111b2577119c12b14eadf963b9
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761239"
---
# <a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="aa311-103">Microsoft Teams 中的來賓存取</span><span class="sxs-lookup"><span data-stu-id="aa311-103">Guest access in Microsoft Teams</span></span>

<span data-ttu-id="aa311-104">來賓存取可將 Teams 中現有團隊和頻道的存取權授與給組織外部人員，讓貴組織中的團隊與組織外部的人員共同作業。</span><span class="sxs-lookup"><span data-stu-id="aa311-104">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels in Teams.</span></span> <span data-ttu-id="aa311-105">任何擁有商務或消費者電子郵件帳戶的人（例如 Microsoft 365、Outlook、Gmail 或其他人），都可以在擁有小組聊天、會議和檔案的完整存取權的小組中，以來賓的身分參與。</span><span class="sxs-lookup"><span data-stu-id="aa311-105">Anyone with a business or consumer email account, such as Microsoft 365, Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span> <span data-ttu-id="aa311-106">身為 Teams 系統管理員的您可以控制來賓在 Teams 中可以 (和不可以) 使用的功能，請參閱[管理來賓存取](manage-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="aa311-106">As the Teams admin, you control which features guests can (and can't) use in Teams - check out [Manage guest access](manage-guests.md).</span></span>

<span data-ttu-id="aa311-107">若要比較外部存取 (同盟) 和來賓存取 (並決定您應使用的方式)，請閱讀[在 Teams 中與其他組織的使用者通訊](communicate-with-users-from-other-organizations.md)。</span><span class="sxs-lookup"><span data-stu-id="aa311-107">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

<span data-ttu-id="aa311-108">來賓存取在 Teams 中是全組織設定，依預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="aa311-108">Guest access is an org-wide setting in Teams and is turned off by default.</span></span> <span data-ttu-id="aa311-109"> (您可以使用 [敏感度標籤](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)控制對個別團隊的來賓存取權。 ) </span><span class="sxs-lookup"><span data-stu-id="aa311-109">(You can control guest access to individual teams by using [sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).)</span></span>

<span data-ttu-id="aa311-110">如果您準備好要開始邀請客人給小組，請閱讀下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="aa311-110">If you're ready to start inviting guests to teams, read one of the following:</span></span>

- <span data-ttu-id="aa311-111">若要設定供團隊使用的來賓存取權，請參閱 [與團隊中的來賓共同](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)作業。</span><span class="sxs-lookup"><span data-stu-id="aa311-111">To configure guest access for Teams for general use, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>
- <span data-ttu-id="aa311-112">若要與使用 Azure Active Directory 的合作夥伴組織共同作業，並允許來賓自行註冊小組存取，請參閱 [使用受管理的來賓建立 B2B extranet](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet)。</span><span class="sxs-lookup"><span data-stu-id="aa311-112">To collaborate with a partner organization that uses Azure Active Directory and allow guests to self-enroll for team access, see [Create a B2B extranet with managed guests](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).</span></span>

<span data-ttu-id="aa311-113">來賓存取受到 Azure AD 和 Microsoft 365 或 Office 365 服務的限制。</span><span class="sxs-lookup"><span data-stu-id="aa311-113">Guest access is subject to Azure AD and Microsoft 365 or Office 365 service limits.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa311-114">對於共存的升級模式，來賓存取遵循 Teams 的全組織設定。</span><span class="sxs-lookup"><span data-stu-id="aa311-114">Guest users follow Teams Org-wide settings for the coexistence Upgrade mode.</span></span> <span data-ttu-id="aa311-115">這項設定無法變更。</span><span class="sxs-lookup"><span data-stu-id="aa311-115">This can't be changed.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="aa311-116">來賓存取的授權</span><span class="sxs-lookup"><span data-stu-id="aa311-116">Licensing for guest access</span></span>

<span data-ttu-id="aa311-117">來賓存取隨附於所有 Microsoft 365 商務標準版、Office 365 企業版和 Office 365 教育版訂閱。</span><span class="sxs-lookup"><span data-stu-id="aa311-117">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="aa311-118">您不需要額外的 Microsoft 365 或 Office 365 授權。</span><span class="sxs-lookup"><span data-stu-id="aa311-118">No additional Microsoft 365 or Office 365 license is necessary.</span></span> <span data-ttu-id="aa311-119">Teams 未限制您可以新增的來賓數量。</span><span class="sxs-lookup"><span data-stu-id="aa311-119">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="aa311-120">不過，可新增至您租用戶的來賓總數可能受到 Azure AD 的付費功能限制。</span><span class="sxs-lookup"><span data-stu-id="aa311-120">However, the total number of guests that can be added to your tenant may be restricted by the paid features of Azure AD.</span></span> <span data-ttu-id="aa311-121">如需詳細資訊，請參閱 [Azure AD B2B 共同作業授權](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="aa311-121">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>


> [!NOTE]
> <span data-ttu-id="aa311-122">僅擁有獨立版 Microsoft 365 或 Office 365 訂閱方案 (例如 Exchange Online Plan 2) 的組織使用者將無法受邀為貴組織的來賓，因為 Teams 認為這些使用者屬於相同的組織。</span><span class="sxs-lookup"><span data-stu-id="aa311-122">Users in your organization who have standalone Microsoft 365 or Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="aa311-123">若要讓這些使用者使用 Teams，這些使用者必須獲派 Microsoft 365 商務標準版、Office 365 企業版或 Office 365 教育版訂閱。</span><span class="sxs-lookup"><span data-stu-id="aa311-123">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="aa311-124">何謂來賓？</span><span class="sxs-lookup"><span data-stu-id="aa311-124">Who is a guest?</span></span>

<span data-ttu-id="aa311-125">來賓是不屬於員工、學生或組織成員的人員。</span><span class="sxs-lookup"><span data-stu-id="aa311-125">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="aa311-126">他們沒有貴組織的學校或公司帳戶。</span><span class="sxs-lookup"><span data-stu-id="aa311-126">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="aa311-127">例如，來賓可能包括有合作夥伴、廠商、供應商或顧問。</span><span class="sxs-lookup"><span data-stu-id="aa311-127">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="aa311-128">只要是不屬於貴組織成員的任何人都可以在 Teams 中新增為來賓。</span><span class="sxs-lookup"><span data-stu-id="aa311-128">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="aa311-129">這表示擁有商務帳戶 (也就是 Active Directory 帳戶) 或消費者電子郵件帳戶 (使用 Outlook.com、Gmail.com 或其他) 的任何人都能以來賓身分參與 Teams，擁有團隊和頻道體驗的完整存取權。</span><span class="sxs-lookup"><span data-stu-id="aa311-129">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span>

<span data-ttu-id="aa311-130">若要深入了解來賓可以和不可以使用的功能，請參閱[在 Microsoft Teams 中授權來賓存取](teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="aa311-130">To learn more about what a guest can and can't do, read [Authorize guest access in Microsoft Teams](teams-dependencies.md).</span></span> <span data-ttu-id="aa311-131">或請查看[比較團隊成員和來賓功能](guest-experience.md#comparison-of-team-member-and-guest-capabilities)表格。</span><span class="sxs-lookup"><span data-stu-id="aa311-131">Or check out the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> 

<span data-ttu-id="aa311-132">最後，小組中的所有來賓都涵蓋與 Microsoft 365 其餘的相容性和審核保護，而且可以在 Azure AD 中進行管理。</span><span class="sxs-lookup"><span data-stu-id="aa311-132">Finally, all guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365, and can be managed within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="aa311-133">為什麼要使用來賓存取？</span><span class="sxs-lookup"><span data-stu-id="aa311-133">Why use guest access?</span></span>

<span data-ttu-id="aa311-134">透過來賓存取，使用 Teams 的組織可以向合作夥伴提供團隊、頻道中的文件、資源、聊天和應用程式的存取權，同時又能保有自身公司資料的完整控制權。</span><span class="sxs-lookup"><span data-stu-id="aa311-134">With guest access, organizations that use Teams can provide access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> 

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="aa311-135">了解來賓的限制</span><span class="sxs-lookup"><span data-stu-id="aa311-135">Understand the limitations for guests</span></span>

<span data-ttu-id="aa311-136">來賓體驗有刻意設計的限制。</span><span class="sxs-lookup"><span data-stu-id="aa311-136">The guest experience has limitations by design.</span></span> <span data-ttu-id="aa311-137">請確定您了解來賓體驗，這樣您才不會嘗試修正不是問題的項目。</span><span class="sxs-lookup"><span data-stu-id="aa311-137">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="aa311-138">以下是 Microsoft 團隊中的來賓無法使用的一些功能清單：</span><span class="sxs-lookup"><span data-stu-id="aa311-138">Here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="aa311-139">OneDrive</span><span class="sxs-lookup"><span data-stu-id="aa311-139">OneDrive</span></span>
- <span data-ttu-id="aa311-140">在 Teams 外部執行人員搜尋</span><span class="sxs-lookup"><span data-stu-id="aa311-140">People search outside of Teams</span></span>
- <span data-ttu-id="aa311-141">行事曆、排程會議或會議詳細資料</span><span class="sxs-lookup"><span data-stu-id="aa311-141">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="aa311-142">PSTN</span><span class="sxs-lookup"><span data-stu-id="aa311-142">PSTN</span></span>
- <span data-ttu-id="aa311-143">組織圖</span><span class="sxs-lookup"><span data-stu-id="aa311-143">Organization chart</span></span>
- <span data-ttu-id="aa311-144">建立或修改團隊</span><span class="sxs-lookup"><span data-stu-id="aa311-144">Create or revise a team</span></span>
- <span data-ttu-id="aa311-145">瀏覽團隊</span><span class="sxs-lookup"><span data-stu-id="aa311-145">Browse for a team</span></span>
- <span data-ttu-id="aa311-146">將檔案上傳至個人對個人的聊天</span><span class="sxs-lookup"><span data-stu-id="aa311-146">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="aa311-147">目前，團隊只支援 [狀態1和省2類型的來賓使用者](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span><span class="sxs-lookup"><span data-stu-id="aa311-147">Currently, Teams supports only [State 1 and State 2 types of guest users](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span></span>

<span data-ttu-id="aa311-148">如需來賓在 Teams 中可以和不可以使用的功能完整清單，請參閱[比較團隊成員和來賓功能](guest-experience.md#comparison-of-team-member-and-guest-capabilities)表格。</span><span class="sxs-lookup"><span data-stu-id="aa311-148">For a full list of what a guest can and can't do in Teams, see the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> <span data-ttu-id="aa311-149">若要深入瞭解 Microsoft 365 層級的來賓存取權，請閱讀 [與組織外部人員](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)共同作業。</span><span class="sxs-lookup"><span data-stu-id="aa311-149">To learn more about guest access at the Microsoft 365 level, read [Collaborating with people outside your organization](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization).</span></span>


## <a name="related-topics"></a><span data-ttu-id="aa311-150">相關主題</span><span class="sxs-lookup"><span data-stu-id="aa311-150">Related topics</span></span>

[<span data-ttu-id="aa311-151">連絡商務產品的客戶支援 - 系統管理說明</span><span class="sxs-lookup"><span data-stu-id="aa311-151">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[<span data-ttu-id="aa311-152">使用三層保護層級來設定團隊</span><span class="sxs-lookup"><span data-stu-id="aa311-152">Configure Teams with three tiers of protection</span></span>](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
