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
localization_priority: Normal
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
ms.openlocfilehash: 266830f29f98d517450f4062ff23de9a7582a24f
ms.sourcegitcommit: 207e6aa97867e3fd80734cc839c0c5858bca24c8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/30/2020
ms.locfileid: "49476992"
---
# <a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="cc85b-103">Microsoft Teams 中的來賓存取</span><span class="sxs-lookup"><span data-stu-id="cc85b-103">Guest access in Microsoft Teams</span></span>

<span data-ttu-id="cc85b-104">有了來賓存取權，您就可以為組織外部人員提供對團隊、頻道、資源、聊天和應用程式的存取權，同時維持對公司資料的控制權。</span><span class="sxs-lookup"><span data-stu-id="cc85b-104">With guest access, you can provide access to teams, documents in channels, resources, chats, and applications to people outside your organization, while maintaining control over your corporate data.</span></span>

<span data-ttu-id="cc85b-105">來賓是不屬於員工、學生或組織成員的人員。</span><span class="sxs-lookup"><span data-stu-id="cc85b-105">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="cc85b-106">他們沒有貴組織的學校或公司帳戶。</span><span class="sxs-lookup"><span data-stu-id="cc85b-106">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="cc85b-107">例如，來賓可能包括有合作夥伴、廠商、供應商或顧問。</span><span class="sxs-lookup"><span data-stu-id="cc85b-107">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="cc85b-108">只要是不屬於貴組織成員的任何人都可以在 Teams 中新增為來賓。</span><span class="sxs-lookup"><span data-stu-id="cc85b-108">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="cc85b-109">這表示任何擁有商務帳戶的人 (也就是， (有 Outlook.com、Gmail.com 或其他) 人的 Azure Active Directory 帳戶) 或消費者電子郵件帳戶時，都可以使用團隊和頻道體驗，在小組中參與來賓。</span><span class="sxs-lookup"><span data-stu-id="cc85b-109">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with access to teams and channel experiences.</span></span>

<span data-ttu-id="cc85b-110">團隊中的來賓與其他 Microsoft 365 的相容性和審核保護功能所涵蓋，且可在 Azure AD 中進行管理。</span><span class="sxs-lookup"><span data-stu-id="cc85b-110">Guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365, and can be managed within Azure AD.</span></span> <span data-ttu-id="cc85b-111">來賓存取受到 Azure AD 和 Microsoft 365 或 Office 365 服務的限制。</span><span class="sxs-lookup"><span data-stu-id="cc85b-111">Guest access is subject to Azure AD and Microsoft 365 or Office 365 service limits.</span></span>

<span data-ttu-id="cc85b-112">來賓體驗有刻意設計的限制。</span><span class="sxs-lookup"><span data-stu-id="cc85b-112">The guest experience has limitations by design.</span></span> <span data-ttu-id="cc85b-113">如需訪客在小組中能及不能執行之動作的完整清單，請參閱 [比較小組成員和來賓的功能](guest-experience.md#comparison-of-team-member-and-guest-capabilities)。</span><span class="sxs-lookup"><span data-stu-id="cc85b-113">For a full list of what a guest can and can't do in Teams, see [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc85b-114">對於共存的升級模式，來賓存取遵循 Teams 的全組織設定。</span><span class="sxs-lookup"><span data-stu-id="cc85b-114">Guest users follow Teams Org-wide settings for the coexistence Upgrade mode.</span></span> <span data-ttu-id="cc85b-115">這項設定無法變更。</span><span class="sxs-lookup"><span data-stu-id="cc85b-115">This can't be changed.</span></span>

<span data-ttu-id="cc85b-116">若要設定來賓存取權，請參閱 [與團隊中的來賓共同](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)作業。</span><span class="sxs-lookup"><span data-stu-id="cc85b-116">To set up guest access, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span> 

<span data-ttu-id="cc85b-117">若要比較外部存取 (同盟) 和來賓存取 (並決定您應使用的方式)，請閱讀[在 Teams 中與其他組織的使用者通訊](communicate-with-users-from-other-organizations.md)。</span><span class="sxs-lookup"><span data-stu-id="cc85b-117">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

## <a name="set-up-guest-access"></a><span data-ttu-id="cc85b-118">設定來賓存取權</span><span class="sxs-lookup"><span data-stu-id="cc85b-118">Set up guest access</span></span>

<span data-ttu-id="cc85b-119">團隊中的來賓存取需要在 Microsoft 365 中設定其他設定，包括 Azure AD、Microsoft 365 群組和 SharePoint 中的設定。</span><span class="sxs-lookup"><span data-stu-id="cc85b-119">Guest access in Teams requires configuring other settings in Microsoft 365, including settings in Azure AD, Microsoft 365 Groups, and SharePoint.</span></span> <span data-ttu-id="cc85b-120">如果您準備好要開始邀請客人給小組，請閱讀下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="cc85b-120">If you're ready to start inviting guests to teams, read one of the following:</span></span>

- <span data-ttu-id="cc85b-121">若要設定供團隊使用的來賓存取權，請參閱 [與團隊中的來賓共同](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)作業。</span><span class="sxs-lookup"><span data-stu-id="cc85b-121">To configure guest access for Teams for general use, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>
- <span data-ttu-id="cc85b-122">若要與使用 Azure Active Directory 的合作夥伴組織共同作業，並允許來賓自行註冊小組存取，請參閱 [使用受管理的來賓建立 B2B extranet](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet)。</span><span class="sxs-lookup"><span data-stu-id="cc85b-122">To collaborate with a partner organization that uses Azure Active Directory and allow guests to self-enroll for team access, see [Create a B2B extranet with managed guests](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).</span></span>

<span data-ttu-id="cc85b-123">團隊中的來賓存取權是全組織的設定，預設為關閉狀態。</span><span class="sxs-lookup"><span data-stu-id="cc85b-123">Guest access in Teams is an organization-wide setting and is turned off by default.</span></span> <span data-ttu-id="cc85b-124">您可以使用 [敏感度標籤](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)控制對個別團隊的來賓存取權。</span><span class="sxs-lookup"><span data-stu-id="cc85b-124">You can control guest access to individual teams by using [sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

## <a name="how-a-guest-becomes-a-member-of-a-team"></a><span data-ttu-id="cc85b-125">來賓成為小組成員的方式</span><span class="sxs-lookup"><span data-stu-id="cc85b-125">How a guest becomes a member of a team</span></span>

1. <span data-ttu-id="cc85b-126">小組擁有者或 Microsoft 365 系統管理員會 [將來賓新增至小組](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。</span><span class="sxs-lookup"><span data-stu-id="cc85b-126">A team owner or a Microsoft 365 admin [adds a guest to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span>
2. <span data-ttu-id="cc85b-127">來賓會收到來自小組擁有者的歡迎電子郵件，其中具有小組相關資訊，以及現在成為成員預期有什麼優點。</span><span class="sxs-lookup"><span data-stu-id="cc85b-127">The guest receives a welcome email from the team owner, with information about the team and what to expect now that they're a member.</span></span>
3. <span data-ttu-id="cc85b-128">來賓接受邀請。</span><span class="sxs-lookup"><span data-stu-id="cc85b-128">The guest accepts the invitation.</span></span>
  <span data-ttu-id="cc85b-129">在 Azure Active Directory 中擁有公司或學校帳戶的來賓使用者，可以接受邀請並直接進行驗證。</span><span class="sxs-lookup"><span data-stu-id="cc85b-129">Guest users who have an work or school account in Azure Active Directory can accept the invitation and authenticate directly.</span></span> <span data-ttu-id="cc85b-130">其他使用者傳送一次性傳遞程式碼，以驗證其身分識別 (需要) 的一次性 [密碼驗證](https://docs.microsoft.com/azure/active-directory/external-identities/one-time-passcode) 。</span><span class="sxs-lookup"><span data-stu-id="cc85b-130">Other users are sent a one-time pass code to validate their identity ([One-time passcode authentication](https://docs.microsoft.com/azure/active-directory/external-identities/one-time-passcode) required).</span></span>
4. <span data-ttu-id="cc85b-131">接受邀請之後，來賓可以[參與小組和頻道](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499)、接收及回應頻道訊息、[存取頻道中的檔案](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e)、參與交談、加入會議、在文件上共同作業等等。</span><span class="sxs-lookup"><span data-stu-id="cc85b-131">After accepting the invitation, the guest can [participate in teams and channels](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), receive and respond to channel messages, [access files in channels](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), participate in chats, join meetings, collaborate on documents, and more.</span></span> 

<span data-ttu-id="cc85b-132">在 Teams 中，系統會清楚地識別來賓。</span><span class="sxs-lookup"><span data-stu-id="cc85b-132">In Teams, guests are clearly identified.</span></span> <span data-ttu-id="cc85b-133">來賓使用者的名稱包括標籤 **(來賓)**，頻道包含一個圖示指出小組中有來賓。</span><span class="sxs-lookup"><span data-stu-id="cc85b-133">A guest user's name includes the label **(Guest)**, and a channel includes an icon to indicate that there are guests on the team.</span></span> <span data-ttu-id="cc85b-134">如需詳細資訊，請參閱[來賓體驗像什麼](guest-experience.md)。</span><span class="sxs-lookup"><span data-stu-id="cc85b-134">For more details, see [What the guest experience is like](guest-experience.md).</span></span>
  
<span data-ttu-id="cc85b-135">來賓隨時可以離開 Teams 內的小組。</span><span class="sxs-lookup"><span data-stu-id="cc85b-135">Guests can leave the team at any time from within Teams.</span></span> <span data-ttu-id="cc85b-136">如需詳細資訊，請參閱[如何離開小組？](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)</span><span class="sxs-lookup"><span data-stu-id="cc85b-136">For details, see  [How do I leave a team?](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)</span></span>

> [!NOTE]
> <span data-ttu-id="cc85b-137">離開團隊後，不會從組織的目錄中移除來賓帳戶。</span><span class="sxs-lookup"><span data-stu-id="cc85b-137">Leaving the team doesn't remove the guest account from your organization's directory.</span></span> <span data-ttu-id="cc85b-138">這必須由 Microsoft 365 全域管理員或 Azure AD 系統管理員來完成。</span><span class="sxs-lookup"><span data-stu-id="cc85b-138">This must be done by a Microsoft 365 global admin or an Azure AD admin.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="cc85b-139">來賓存取的授權</span><span class="sxs-lookup"><span data-stu-id="cc85b-139">Licensing for guest access</span></span>

<span data-ttu-id="cc85b-140">來賓存取包含在所有 Microsoft 365 商務標準版、Microsoft 365 企業版及 Microsoft 365 教育版訂閱中。</span><span class="sxs-lookup"><span data-stu-id="cc85b-140">Guest access is included with all Microsoft 365 Business Standard, Microsoft 365 Enterprise, and Microsoft 365 Education subscriptions.</span></span> <span data-ttu-id="cc85b-141">不需要額外的 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="cc85b-141">No additional Microsoft 365 license is necessary.</span></span> <span data-ttu-id="cc85b-142">Teams 未限制您可以新增的來賓數量。</span><span class="sxs-lookup"><span data-stu-id="cc85b-142">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="cc85b-143">不過，可新增至您租用戶的來賓總數可能受到 Azure AD 的付費功能限制。</span><span class="sxs-lookup"><span data-stu-id="cc85b-143">However, the total number of guests that can be added to your tenant may be restricted by the paid features of Azure AD.</span></span> <span data-ttu-id="cc85b-144">如需詳細資訊，請參閱 [AZURE AD 外部身分識別的計費模型](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="cc85b-144">For more information, see [Billing model for Azure AD External Identities](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>

> [!NOTE]
> <span data-ttu-id="cc85b-145">貴組織中擁有獨立 Microsoft 365 訂閱者案（例如 Exchange Online 方案2）的使用者，不能受到受邀者對您組織的訪客，因為小組會認為這些使用者屬於同一個組織。</span><span class="sxs-lookup"><span data-stu-id="cc85b-145">Users in your organization who have standalone Microsoft 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="cc85b-146">若要讓這些使用者使用 Teams，這些使用者必須獲派 Microsoft 365 商務標準版、Office 365 企業版或 Office 365 教育版訂閱。</span><span class="sxs-lookup"><span data-stu-id="cc85b-146">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="guest-access-reviews"></a><span data-ttu-id="cc85b-147">來賓存取審查</span><span class="sxs-lookup"><span data-stu-id="cc85b-147">Guest access reviews</span></span>

<span data-ttu-id="cc85b-148">您可以使用 Azure AD 來建立群組成員或指派給應用程式的使用者的存取權審查。</span><span class="sxs-lookup"><span data-stu-id="cc85b-148">You can use Azure AD to create an access review for group members or users assigned to an application.</span></span> <span data-ttu-id="cc85b-149">建立週期性存取檢查可節省您的時間。</span><span class="sxs-lookup"><span data-stu-id="cc85b-149">Creating recurring access reviews can save you time.</span></span> <span data-ttu-id="cc85b-150">如果您需要例行查看有權存取應用程式、團隊或群組成員的使用者，您可以定義這些評論的頻率。</span><span class="sxs-lookup"><span data-stu-id="cc85b-150">If you need to routinely review users who have access to an application, a team, or are members of a group, you can define the frequency of those reviews.</span></span> 

<span data-ttu-id="cc85b-151">您可以自行執行來賓存取權審查、要求客人審查自己的成員資格，或是要求應用程式擁有者或商業決策人來執行存取審查。</span><span class="sxs-lookup"><span data-stu-id="cc85b-151">You can perform a guest access review yourself, ask guests to review their own membership, or ask an application owner or business decision maker to perform the access review.</span></span> <span data-ttu-id="cc85b-152">使用 Azure 入口網站執行來賓存取審查。</span><span class="sxs-lookup"><span data-stu-id="cc85b-152">Use the Azure portal to perform guest access reviews.</span></span> <span data-ttu-id="cc85b-153">如需詳細資訊，請參閱 [使用 AZURE AD access 評論管理來賓存取](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)。</span><span class="sxs-lookup"><span data-stu-id="cc85b-153">For more information, see [Manage guest access with Azure AD access reviews](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cc85b-154">相關主題</span><span class="sxs-lookup"><span data-stu-id="cc85b-154">Related topics</span></span>

[<span data-ttu-id="cc85b-155">與組織外部人員共同作業</span><span class="sxs-lookup"><span data-stu-id="cc85b-155">Collaborating with people outside your organization</span></span>](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[<span data-ttu-id="cc85b-156">封鎖特定 Microsoft 365 群組或 Microsoft 團隊小組的來賓使用者</span><span class="sxs-lookup"><span data-stu-id="cc85b-156">Block guest users from a specific Microsoft 365 group or Microsoft Teams team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="cc85b-157">建立安全的來賓共用環境</span><span class="sxs-lookup"><span data-stu-id="cc85b-157">Create a secure guest sharing environment</span></span>](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

[<span data-ttu-id="cc85b-158">連絡商務產品的客戶支援 - 系統管理說明</span><span class="sxs-lookup"><span data-stu-id="cc85b-158">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[<span data-ttu-id="cc85b-159">使用三層保護層級來設定團隊</span><span class="sxs-lookup"><span data-stu-id="cc85b-159">Configure Teams with three tiers of protection</span></span>](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
