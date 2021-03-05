---
title: Microsoft Teams 中的來賓存取
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
search.appverid: MET150
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
description: Microsoft Teams 中的來賓存取可將團隊和頻道的存取權授與給組織外部人員，讓貴組織中的團隊與組織外部的人員共同作業。
ms.openlocfilehash: bf1e5083b160bf79c1abe06bffd2a68bf4c0aaab
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421188"
---
# <a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="6ef07-103">Microsoft Teams 中的來賓存取</span><span class="sxs-lookup"><span data-stu-id="6ef07-103">Guest access in Microsoft Teams</span></span>

<span data-ttu-id="6ef07-104">透過來賓存取，您可以向組織外部的人員提供團隊、頻道中的文件、資源、聊天和應用程式的存取權，同時又能保有自身公司資料的完整控制權。</span><span class="sxs-lookup"><span data-stu-id="6ef07-104">With guest access, you can provide access to teams, documents in channels, resources, chats, and applications to people outside your organization, while maintaining control over your corporate data.</span></span>

> [!NOTE]
> <span data-ttu-id="6ef07-105">如果您只想尋找、通話、聊天及設定與其他組織人員的會議，請使用[外部存取](manage-external-access.md)。</span><span class="sxs-lookup"><span data-stu-id="6ef07-105">If you just want to find, call, chat, and set up meetings with people in other organizations, use [external access](manage-external-access.md).</span></span>

<span data-ttu-id="6ef07-106">來賓是不屬於員工、學生或組織成員的人員。</span><span class="sxs-lookup"><span data-stu-id="6ef07-106">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="6ef07-107">他們沒有貴組織的學校或公司帳戶。</span><span class="sxs-lookup"><span data-stu-id="6ef07-107">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="6ef07-108">例如，來賓可能包括有合作夥伴、廠商、供應商或顧問。</span><span class="sxs-lookup"><span data-stu-id="6ef07-108">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="6ef07-109">只要是不屬於貴組織成員的任何人都可以在 Teams 中新增為來賓。</span><span class="sxs-lookup"><span data-stu-id="6ef07-109">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="6ef07-110">這表示任何擁有商務帳戶（也就是 Azure Active Directory 帳戶）或消費者電子郵件帳戶（使用 Outlook.com、Gmail.com 或其他）的人員都能以來賓身分參與 Teams，擁有對團隊和頻道體驗的存取權。</span><span class="sxs-lookup"><span data-stu-id="6ef07-110">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with access to teams and channel experiences.</span></span>

<span data-ttu-id="6ef07-111">Teams 中的來賓與其他部分的 Microsoft 365 一樣，都受到相同的合規性和稽核保護，且可在 Azure AD 中管理這些來賓。</span><span class="sxs-lookup"><span data-stu-id="6ef07-111">Guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365, and can be managed within Azure AD.</span></span> <span data-ttu-id="6ef07-112">來賓存取受到 Azure AD 和 Microsoft 365 或 Office 365 服務的限制。</span><span class="sxs-lookup"><span data-stu-id="6ef07-112">Guest access is subject to Azure AD and Microsoft 365 or Office 365 service limits.</span></span>

<span data-ttu-id="6ef07-113">來賓體驗有刻意設計的限制。</span><span class="sxs-lookup"><span data-stu-id="6ef07-113">The guest experience has limitations by design.</span></span> <span data-ttu-id="6ef07-114">如需有關來賓在 Teams 中可以和不可以使用的功能完整清單，請參閱[團隊成員和來賓功能的比較](guest-experience.md#comparison-of-team-member-and-guest-capabilities)。</span><span class="sxs-lookup"><span data-stu-id="6ef07-114">For a full list of what a guest can and can't do in Teams, see [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ef07-115">對於共存的升級模式，來賓遵循 Teams 的全組織設定。</span><span class="sxs-lookup"><span data-stu-id="6ef07-115">Guests follow Teams Org-wide settings for the coexistence Upgrade mode.</span></span> <span data-ttu-id="6ef07-116">這項設定無法變更。</span><span class="sxs-lookup"><span data-stu-id="6ef07-116">This can't be changed.</span></span>

<span data-ttu-id="6ef07-117">若要設定來賓存取，請參閱 [在小組中與來賓共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)。</span><span class="sxs-lookup"><span data-stu-id="6ef07-117">To set up guest access, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span> 

<span data-ttu-id="6ef07-118">若要比較外部存取 (同盟) 和來賓存取 (並決定您應使用的方式)，請閱讀[在 Teams 中與其他組織的使用者通訊](communicate-with-users-from-other-organizations.md)。</span><span class="sxs-lookup"><span data-stu-id="6ef07-118">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

## <a name="set-up-guest-access"></a><span data-ttu-id="6ef07-119">設定來賓存取</span><span class="sxs-lookup"><span data-stu-id="6ef07-119">Set up guest access</span></span>

<span data-ttu-id="6ef07-120">Teams 中的來賓存取需要設定 Microsoft 365 中的其他設定，包括在 Azure AD、Microsoft 365 群組和 SharePoint 中的設定。</span><span class="sxs-lookup"><span data-stu-id="6ef07-120">Guest access in Teams requires configuring other settings in Microsoft 365, including settings in Azure AD, Microsoft 365 Groups, and SharePoint.</span></span> <span data-ttu-id="6ef07-121">如果您準備好要開始邀請來賓使用 Teams，請閱讀下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="6ef07-121">If you're ready to start inviting guests to teams, read one of the following:</span></span>

- <span data-ttu-id="6ef07-122">若要為 Teams 設定一般使用的來賓存取，請參閱 [在小組中與來賓共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)。</span><span class="sxs-lookup"><span data-stu-id="6ef07-122">To configure guest access for Teams for general use, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>
- <span data-ttu-id="6ef07-123">若要與合作夥伴組織共同作業，使用 Azure Active Directory 並允許來賓自行註冊以取得小組存取，請參閱 [使用受管理來賓建立 B2B 外部網路](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet)。</span><span class="sxs-lookup"><span data-stu-id="6ef07-123">To collaborate with a partner organization that uses Azure Active Directory and allow guests to self-enroll for team access, see [Create a B2B extranet with managed guests](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).</span></span>

<span data-ttu-id="6ef07-124">Teams 的來賓存取是一項全組織設定，預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="6ef07-124">Guest access in Teams is an organization-wide setting and is turned off by default.</span></span> <span data-ttu-id="6ef07-125">您可以透過使用 [敏感性標籤](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)，控制來賓對個別 Teams 的存取。</span><span class="sxs-lookup"><span data-stu-id="6ef07-125">You can control guest access to individual teams by using [sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

## <a name="how-a-guest-becomes-a-member-of-a-team"></a><span data-ttu-id="6ef07-126">來賓成為小組成員的方式</span><span class="sxs-lookup"><span data-stu-id="6ef07-126">How a guest becomes a member of a team</span></span>

1. <span data-ttu-id="6ef07-127">小組擁有者或 Microsoft 365 系統管理 [將來賓新增至小組](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。</span><span class="sxs-lookup"><span data-stu-id="6ef07-127">A team owner or a Microsoft 365 admin [adds a guest to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span>
2. <span data-ttu-id="6ef07-128">來賓會收到來自小組擁有者的歡迎電子郵件，其中具有小組相關資訊，以及現在成為成員預期有什麼優點。</span><span class="sxs-lookup"><span data-stu-id="6ef07-128">The guest receives a welcome email from the team owner, with information about the team and what to expect now that they're a member.</span></span>
3. <span data-ttu-id="6ef07-129">來賓接受邀請。</span><span class="sxs-lookup"><span data-stu-id="6ef07-129">The guest accepts the invitation.</span></span>
  <span data-ttu-id="6ef07-130">在 Azure Active Directory 中擁有公司或學校帳戶的來賓可以接受邀請並直接驗證。</span><span class="sxs-lookup"><span data-stu-id="6ef07-130">Guests who have a work or school account in Azure Active Directory can accept the invitation and authenticate directly.</span></span> <span data-ttu-id="6ef07-131">其他使用者會收到一次性密碼以驗證其身分識別 ([一次性密碼驗證](https://docs.microsoft.com/azure/active-directory/external-identities/one-time-passcode) 必要)。</span><span class="sxs-lookup"><span data-stu-id="6ef07-131">Other users are sent a one-time pass code to validate their identity ([One-time passcode authentication](https://docs.microsoft.com/azure/active-directory/external-identities/one-time-passcode) required).</span></span>
4. <span data-ttu-id="6ef07-132">接受邀請之後，來賓可以[參與小組和頻道](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499)、接收及回應頻道訊息、[存取頻道中的檔案](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e)、參與交談、加入會議、在文件上共同作業等等。</span><span class="sxs-lookup"><span data-stu-id="6ef07-132">After accepting the invitation, the guest can [participate in teams and channels](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), receive and respond to channel messages, [access files in channels](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), participate in chats, join meetings, collaborate on documents, and more.</span></span> 

<span data-ttu-id="6ef07-133">在 Teams 中，系統會清楚地識別來賓。</span><span class="sxs-lookup"><span data-stu-id="6ef07-133">In Teams, guests are clearly identified.</span></span> <span data-ttu-id="6ef07-134">來賓的名稱包括標籤 **(來賓)**，頻道包含一個圖示指出小組中有來賓。</span><span class="sxs-lookup"><span data-stu-id="6ef07-134">A guest's name includes the label **(Guest)**, and a channel includes an icon to indicate that there are guests on the team.</span></span> <span data-ttu-id="6ef07-135">如需詳細資訊，請參閱[來賓體驗像什麼](guest-experience.md)。</span><span class="sxs-lookup"><span data-stu-id="6ef07-135">For more details, see [What the guest experience is like](guest-experience.md).</span></span>
  
<span data-ttu-id="6ef07-136">來賓隨時可以離開 Teams 內的小組。</span><span class="sxs-lookup"><span data-stu-id="6ef07-136">Guests can leave the team at any time from within Teams.</span></span> <span data-ttu-id="6ef07-137">如需詳細資訊，請參閱[如何離開小組？](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)</span><span class="sxs-lookup"><span data-stu-id="6ef07-137">For details, see  [How do I leave a team?](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)</span></span>

> [!NOTE]
> <span data-ttu-id="6ef07-138">離開小組並不會將來賓帳戶直接從貴組織中移除。</span><span class="sxs-lookup"><span data-stu-id="6ef07-138">Leaving the team doesn't remove the guest account from your organization's directory.</span></span> <span data-ttu-id="6ef07-139">必須由 Microsoft 365 全域系統管理員或 Azure AD 系統管理員來完成。</span><span class="sxs-lookup"><span data-stu-id="6ef07-139">This must be done by a Microsoft 365 global admin or an Azure AD admin.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="6ef07-140">來賓存取的授權</span><span class="sxs-lookup"><span data-stu-id="6ef07-140">Licensing for guest access</span></span>

<span data-ttu-id="6ef07-141">來賓存取隨附於所有 Microsoft 365 商務標準版、Microsoft 365 企業版和 Microsoft 365 教育版訂閱。</span><span class="sxs-lookup"><span data-stu-id="6ef07-141">Guest access is included with all Microsoft 365 Business Standard, Microsoft 365 Enterprise, and Microsoft 365 Education subscriptions.</span></span> <span data-ttu-id="6ef07-142">您不需要額外的 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="6ef07-142">No additional Microsoft 365 license is necessary.</span></span> <span data-ttu-id="6ef07-143">Teams 未限制您可以新增的來賓數量。</span><span class="sxs-lookup"><span data-stu-id="6ef07-143">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="6ef07-144">不過，可新增至您租用戶的來賓總數可能受到 Azure AD 的付費功能限制。</span><span class="sxs-lookup"><span data-stu-id="6ef07-144">However, the total number of guests that can be added to your tenant may be restricted by the paid features of Azure AD.</span></span> <span data-ttu-id="6ef07-145">如需詳細資訊，請參閱 [ 適用於 Azure AD 外部身分的計費模型](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="6ef07-145">For more information, see [Billing model for Azure AD External Identities](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>

> [!NOTE]
> <span data-ttu-id="6ef07-146">僅擁有獨立版 Microsoft 365 訂閱方案（例如 Exchange Online Plan 2）的組織使用者將無法接受邀請成貴組織的來賓，因為 Teams 認為這些使用者屬於相同的組織。</span><span class="sxs-lookup"><span data-stu-id="6ef07-146">Users in your organization who have standalone Microsoft 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="6ef07-147">若要讓這些使用者使用 Teams，這些使用者必須獲派 Microsoft 365 商務標準版、Office 365 企業版或 Office 365 教育版訂閱。</span><span class="sxs-lookup"><span data-stu-id="6ef07-147">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="guest-access-reviews"></a><span data-ttu-id="6ef07-148">來賓存取權檢閱</span><span class="sxs-lookup"><span data-stu-id="6ef07-148">Guest access reviews</span></span>

<span data-ttu-id="6ef07-149">您可以針對群組成員或指派至應用程式的使用者，使用 Azure AD 建立存取權檢閱。</span><span class="sxs-lookup"><span data-stu-id="6ef07-149">You can use Azure AD to create an access review for group members or users assigned to an application.</span></span> <span data-ttu-id="6ef07-150">建立週期性的存取權檢閱可以節省您的時間。</span><span class="sxs-lookup"><span data-stu-id="6ef07-150">Creating recurring access reviews can save you time.</span></span> <span data-ttu-id="6ef07-151">如果您需要定期檢閱能夠存取應用程式、小組或群組成員的使用者，您可以定義這些檢閱的頻率。</span><span class="sxs-lookup"><span data-stu-id="6ef07-151">If you need to routinely review users who have access to an application, a team, or are members of a group, you can define the frequency of those reviews.</span></span> 

<span data-ttu-id="6ef07-152">您可以自行執行來賓存取，要求來賓查閱其成員資格，或要求應用程式擁有者或商務決策者執行存取權檢閱。</span><span class="sxs-lookup"><span data-stu-id="6ef07-152">You can perform a guest access review yourself, ask guests to review their own membership, or ask an application owner or business decision maker to perform the access review.</span></span> <span data-ttu-id="6ef07-153">使用 Azure 入口網站以執行來賓存取權檢閱。</span><span class="sxs-lookup"><span data-stu-id="6ef07-153">Use the Azure portal to perform guest access reviews.</span></span> <span data-ttu-id="6ef07-154">如需其他資訊，請參閱 [使用 Azure AD 存取權檢閱管理來賓存取](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)。</span><span class="sxs-lookup"><span data-stu-id="6ef07-154">For more information, see [Manage guest access with Azure AD access reviews](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6ef07-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="6ef07-155">Related topics</span></span>

[<span data-ttu-id="6ef07-156">與組織外部的人員共同作業</span><span class="sxs-lookup"><span data-stu-id="6ef07-156">Collaborating with people outside your organization</span></span>](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[<span data-ttu-id="6ef07-157">在特定的 Microsoft 365 群組或 Microsoft Teams 小組封鎖來賓</span><span class="sxs-lookup"><span data-stu-id="6ef07-157">Block guests from a specific Microsoft 365 group or Microsoft Teams team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="6ef07-158">建立安全的來賓共用環境</span><span class="sxs-lookup"><span data-stu-id="6ef07-158">Create a secure guest sharing environment</span></span>](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

[<span data-ttu-id="6ef07-159">連絡商務產品的客戶支援 - 系統管理說明</span><span class="sxs-lookup"><span data-stu-id="6ef07-159">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[<span data-ttu-id="6ef07-160">為 Teams 設定三層保護</span><span class="sxs-lookup"><span data-stu-id="6ef07-160">Configure Teams with three tiers of protection</span></span>](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
