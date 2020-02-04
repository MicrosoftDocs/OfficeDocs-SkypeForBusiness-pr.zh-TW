---
title: Microsoft Teams 中的來賓存取
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
description: Microsoft Teams 中的來賓存取可將團隊和頻道的存取權授與給組織外部人員，讓貴組織中的團隊與組織外部的人員共同作業。
localization_priority: Priority
f1.keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3490d208f95138d9aad57d69f55957dafb8734e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707548"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="15baf-103">Microsoft Teams 中的來賓存取</span><span class="sxs-lookup"><span data-stu-id="15baf-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="15baf-104">來賓存取可讓您將組織外部的個別使用者新增至 Microsoft Teams 中的團隊和頻道。</span><span class="sxs-lookup"><span data-stu-id="15baf-104">Guest access lets you add individual users from outside your organization to your teams and channels in Microsoft Teams.</span></span> 

<span data-ttu-id="15baf-105">若要比較外部存取 (同盟) 和來賓存取 (並決定您應使用的方式)，請閱讀[在 Teams 中與其他組織的使用者通訊](communicate-with-users-from-other-organizations.md)。</span><span class="sxs-lookup"><span data-stu-id="15baf-105">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

<span data-ttu-id="15baf-106">如果您已在組織中開啟來賓存取，請從[來賓存取檢查清單](guest-access-checklist.md)開始。</span><span class="sxs-lookup"><span data-stu-id="15baf-106">If you're ready to turn on guest access in your organization, start with the [Guest access checklist](guest-access-checklist.md).</span></span>

## <a name="guest-access-overview"></a><span data-ttu-id="15baf-107">來賓存取概觀</span><span class="sxs-lookup"><span data-stu-id="15baf-107">Guest access overview</span></span>

<span data-ttu-id="15baf-108">來賓存取可將 Teams 中現有團隊和頻道的存取權授與給組織外部人員，讓貴組織中的團隊與組織外部的人員共同作業。</span><span class="sxs-lookup"><span data-stu-id="15baf-108">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels in Teams.</span></span> <span data-ttu-id="15baf-109">任何擁有商務或消費者電子郵件帳戶的人員 (例如 Outlook、Gmail 或其他)，都能以來賓身分參與 Teams，擁有小組聊天、會議及檔案的完整存取權。</span><span class="sxs-lookup"><span data-stu-id="15baf-109">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span> <span data-ttu-id="15baf-110">身為 Teams 系統管理員的您可以控制來賓在 Teams 中可以 (和不可以) 使用的功能，請參閱[管理來賓存取](manage-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="15baf-110">As the Teams admin, you control which features guests can (and can't) use in Teams - check out [Manage guest access](manage-guests.md).</span></span>

<span data-ttu-id="15baf-111">來賓存取在 Teams 中是全組織設定，依預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="15baf-111">Guest access is an org-wide setting in Teams and is turned off by default.</span></span> <span data-ttu-id="15baf-112">來賓存取受到 Azure AD 和 Office 365 的服務限制。</span><span class="sxs-lookup"><span data-stu-id="15baf-112">Guest access is subject to Azure AD and Office 365 service limits.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="15baf-113">對於共存的升級模式，來賓存取遵循 Teams 的全組織設定。</span><span class="sxs-lookup"><span data-stu-id="15baf-113">Guest users follow Teams Org-wide settings for the coexistence Upgrade mode.</span></span> <span data-ttu-id="15baf-114">這項設定無法變更。</span><span class="sxs-lookup"><span data-stu-id="15baf-114">This can't be changed.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="15baf-115">來賓存取的授權</span><span class="sxs-lookup"><span data-stu-id="15baf-115">Licensing for guest access</span></span>

<span data-ttu-id="15baf-116">來賓存取隨附於所有 Office 365 商務進階版、Office 365 企業版和 Office 365 教育版訂閱。</span><span class="sxs-lookup"><span data-stu-id="15baf-116">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="15baf-117">您不需要額外的 Office 365 授權。</span><span class="sxs-lookup"><span data-stu-id="15baf-117">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="15baf-118">Teams 未限制您可以新增的來賓數量。</span><span class="sxs-lookup"><span data-stu-id="15baf-118">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="15baf-119">然而，可以新增至租用戶的來賓總數會依據您 Azure AD 授權的允許量而定，通常是每位授權使用者允許 5 位來賓。</span><span class="sxs-lookup"><span data-stu-id="15baf-119">However, the total number of guests that can be added to your tenant is based on what your Azure AD licensing allows - usually 5 guests per licensed user.</span></span> <span data-ttu-id="15baf-120">如需詳細資訊，請參閱 [Azure AD B2B 共同作業授權](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="15baf-120">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>


> [!NOTE]
> <span data-ttu-id="15baf-121">僅擁有獨立版 Office 365 訂閱方案 (例如 Exchange Online Plan 2) 的組織使用者將無法受邀為貴組織的來賓，因為 Teams 認為這些使用者屬於相同的組織。</span><span class="sxs-lookup"><span data-stu-id="15baf-121">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="15baf-122">若要讓這些使用者使用 Teams，這些使用者必須獲派 Office 365 商務進階版、Office 365 企業版或 Office 365 教育版訂閱。</span><span class="sxs-lookup"><span data-stu-id="15baf-122">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="15baf-123">何謂來賓？</span><span class="sxs-lookup"><span data-stu-id="15baf-123">Who is a guest?</span></span>

<span data-ttu-id="15baf-124">來賓是不屬於員工、學生或組織成員的人員。</span><span class="sxs-lookup"><span data-stu-id="15baf-124">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="15baf-125">他們沒有貴組織的學校或公司帳戶。</span><span class="sxs-lookup"><span data-stu-id="15baf-125">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="15baf-126">例如，來賓可能包括有合作夥伴、廠商、供應商或顧問。</span><span class="sxs-lookup"><span data-stu-id="15baf-126">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="15baf-127">只要是不屬於貴組織成員的任何人都可以在 Teams 中新增為來賓。</span><span class="sxs-lookup"><span data-stu-id="15baf-127">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="15baf-128">這表示擁有商務帳戶 (也就是 Active Directory 帳戶) 或消費者電子郵件帳戶 (使用 Outlook.com、Gmail.com 或其他) 的任何人都能以來賓身分參與 Teams，擁有團隊和頻道體驗的完整存取權。</span><span class="sxs-lookup"><span data-stu-id="15baf-128">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span>

<span data-ttu-id="15baf-129">若要深入了解來賓可以和不可以使用的功能，請參閱[在 Microsoft Teams 中授權來賓存取](teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="15baf-129">To learn more about what a guest can and can't do, read [Authorize guest access in Microsoft Teams](teams-dependencies.md).</span></span> <span data-ttu-id="15baf-130">或請查看[比較團隊成員和來賓功能](guest-experience.md#comparison-of-team-member-and-guest-capabilities)表格。</span><span class="sxs-lookup"><span data-stu-id="15baf-130">Or check out the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> 

<span data-ttu-id="15baf-131">最後，Teams 中的所有來賓與其他部分的 Office 365 一樣，都受到相同的合規性和稽核保護，可在 Azure AD 中安全地管理。</span><span class="sxs-lookup"><span data-stu-id="15baf-131">Finally, all guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="15baf-132">為什麼要使用來賓存取？</span><span class="sxs-lookup"><span data-stu-id="15baf-132">Why use guest access?</span></span>

<span data-ttu-id="15baf-133">透過來賓存取，使用 Teams 的組織可以向合作夥伴提供團隊、頻道中的文件、資源、聊天和應用程式的存取權，同時又能保有自身公司資料的完整控制權。</span><span class="sxs-lookup"><span data-stu-id="15baf-133">With guest access, organizations that use Teams can provide access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="15baf-134">Teams 中的所有來賓與其他部分的 Office 365 一樣，都受到相同的合規性和稽核保護，可在 Azure AD 中安全地管理這些來賓。</span><span class="sxs-lookup"><span data-stu-id="15baf-134">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="15baf-135">了解來賓的限制</span><span class="sxs-lookup"><span data-stu-id="15baf-135">Understand the limitations for guests</span></span>

<span data-ttu-id="15baf-136">來賓體驗有刻意設計的限制。</span><span class="sxs-lookup"><span data-stu-id="15baf-136">The guest experience has limitations by design.</span></span> <span data-ttu-id="15baf-137">請確定您了解來賓體驗，這樣您才不會嘗試修正不是問題的項目。</span><span class="sxs-lookup"><span data-stu-id="15baf-137">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="15baf-138">例如，以下是 Microsoft Teams 來賓無法使用的部分功能清單：</span><span class="sxs-lookup"><span data-stu-id="15baf-138">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="15baf-139">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="15baf-139">OneDrive for Business</span></span>
- <span data-ttu-id="15baf-140">在 Teams 外部執行人員搜尋</span><span class="sxs-lookup"><span data-stu-id="15baf-140">People search outside of Teams</span></span>
- <span data-ttu-id="15baf-141">行事曆、排程會議或會議詳細資料</span><span class="sxs-lookup"><span data-stu-id="15baf-141">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="15baf-142">PSTN</span><span class="sxs-lookup"><span data-stu-id="15baf-142">PSTN</span></span>
- <span data-ttu-id="15baf-143">組織圖</span><span class="sxs-lookup"><span data-stu-id="15baf-143">Organization chart</span></span>
- <span data-ttu-id="15baf-144">建立或修改團隊</span><span class="sxs-lookup"><span data-stu-id="15baf-144">Create or revise a team</span></span>
- <span data-ttu-id="15baf-145">瀏覽團隊</span><span class="sxs-lookup"><span data-stu-id="15baf-145">Browse for a team</span></span>
- <span data-ttu-id="15baf-146">將檔案上傳至個人對個人的聊天</span><span class="sxs-lookup"><span data-stu-id="15baf-146">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="15baf-147">目前，Teams 僅支援由 [Azure B2B 所定義](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)來賓使用者的狀態 1 和狀態 2</span><span class="sxs-lookup"><span data-stu-id="15baf-147">Currently, Teams supports only State 1 and State 2 types of guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span></span>

<span data-ttu-id="15baf-148">如需來賓在 Teams 中可以和不可以使用的功能完整清單，請參閱[比較團隊成員和來賓功能](guest-experience.md#comparison-of-team-member-and-guest-capabilities)表格。</span><span class="sxs-lookup"><span data-stu-id="15baf-148">For a full list of what a guest can and can't do in Teams, see the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> <span data-ttu-id="15baf-149">若要深入了解 Office 365 等級的來賓存取，請參閱[將來賓新增至 Office 365 群組](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)。</span><span class="sxs-lookup"><span data-stu-id="15baf-149">To learn more about guest access at the Office 365 level, read [Adding guests to Office 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>


## <a name="more-information"></a><span data-ttu-id="15baf-150">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="15baf-150">More information</span></span>

[<span data-ttu-id="15baf-151">連絡商務產品的客戶支援 - 系統管理說明</span><span class="sxs-lookup"><span data-stu-id="15baf-151">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)  
[<span data-ttu-id="15baf-152">Office 365 群組的來賓存取權</span><span class="sxs-lookup"><span data-stu-id="15baf-152">Guest access in Office 365 Groups</span></span>](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
