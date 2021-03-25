---
title: 將來賓新增至團隊
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
ms.reviewer: rafarhi
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: 管理員可以瞭解如何在 Microsoft Teams 桌面與 Web 用戶端和 Azure Active Directory B2B 共同合作入口網站中新增來賓至組織。
ms.openlocfilehash: 1d44aff9b62a5ba6de7c22499f5a20f187d7781b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109079"
---
# <a name="add-a-guest-to-a-team"></a><span data-ttu-id="30e53-103">將來賓新增至團隊</span><span class="sxs-lookup"><span data-stu-id="30e53-103">Add a guest to a team</span></span>

<span data-ttu-id="30e53-104">任何擁有商務或消費者電子郵件帳戶的人員 (例如 Outlook、Gmail 或其他)，都能以來賓身分加入 Teams。</span><span class="sxs-lookup"><span data-stu-id="30e53-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="30e53-105">做為系統管理員，您可以用多種方式將新來賓新加入組織：</span><span class="sxs-lookup"><span data-stu-id="30e53-105">As an admin, you can add a new guest to the organization in a couple of ways:</span></span>

- <span data-ttu-id="30e53-106">全域系統管理員或 Teams 系統管理員與團隊擁有者可在 Teams 用戶端或 Teams 系統管理中心中，將來賓新增至團隊。</span><span class="sxs-lookup"><span data-stu-id="30e53-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="30e53-107">若要深入瞭解，請參閱[將來賓新增至團隊](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。</span><span class="sxs-lookup"><span data-stu-id="30e53-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="30e53-108">如果您尚未設定來賓存取，請透過[在小組中與來賓共同作業](/microsoft-365/solutions/collaborate-as-team)步驟設定。</span><span class="sxs-lookup"><span data-stu-id="30e53-108">If you haven't set up guest access yet, go through the steps in the [Collaborate with guests in a team](/microsoft-365/solutions/collaborate-as-team).</span></span>

- <span data-ttu-id="30e53-109">透過 Azure Active Directory (Azure AD) B2B 共同作業，將來賓新增到您的組織。</span><span class="sxs-lookup"><span data-stu-id="30e53-109">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="30e53-110">若要瞭解詳細資料，請參閱 [快速入門：在 Azure](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)入口網站中新增來賓至您的目錄。</span><span class="sxs-lookup"><span data-stu-id="30e53-110">For details, check out [Quickstart: Add guests to your directory in the Azure portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

<span data-ttu-id="30e53-111">系統管理員還可以透過指派 [來賓邀請者] 角色，將新增來賓到組織的權限委派給其他人。</span><span class="sxs-lookup"><span data-stu-id="30e53-111">Admins can also delegate permissions to add guests to others in their organization by assigning the Guest Inviter role.</span></span> <span data-ttu-id="30e53-112">如需詳細資訊，請參閱[啟用 B2B 外部共同作業和管理可以邀請來賓的使用者](/azure/active-directory/external-identities/delegate-invitations) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="30e53-112">For more information, see [Enable B2B external collaboration and manage who can invite guests](/azure/active-directory/external-identities/delegate-invitations).</span></span>

<span data-ttu-id="30e53-113">透過 Azure AD B2B 共同作業功能，組織可為 B2B 使用者強制執行條件式存取和多重要素驗證 (MFA) 原則。</span><span class="sxs-lookup"><span data-stu-id="30e53-113">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="30e53-114">這些原則可以在租用戶層級、應用程式或個別使用者層級強制執行，與為組織全職員工和成員啟用原則的方式相同。</span><span class="sxs-lookup"><span data-stu-id="30e53-114">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="30e53-115">這類原則會在資源組織強制執行。</span><span class="sxs-lookup"><span data-stu-id="30e53-115">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="30e53-116">如需詳細資訊，請參閱[適用於 B2B 共同作業使用者的條件式存取](/azure/active-directory/external-identities/conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="30e53-116">For more information, see  [Conditional access for B2B collaboration users](/azure/active-directory/external-identities/conditional-access).</span></span> <span data-ttu-id="30e53-117">無法封鎖個別來賓。</span><span class="sxs-lookup"><span data-stu-id="30e53-117">Individual guests can't be blocked.</span></span>

<span data-ttu-id="30e53-118">已經透過 Azure AD B2B、Microsoft 365 群組或 SharePoint 新增的來賓已準備就緒。</span><span class="sxs-lookup"><span data-stu-id="30e53-118">Guests you have already added via Azure AD B2B, Microsoft 365 Groups, or SharePoint are ready to go.</span></span> <span data-ttu-id="30e53-119">Microsoft 365 系統管理員或團隊擁有者可以將這些來賓新增到各自的團隊。</span><span class="sxs-lookup"><span data-stu-id="30e53-119">The Microsoft 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="30e53-120">如果您直接將來賓新增到與小組相關聯的 Microsoft 365 群組，來賓會取得團隊的存取權，但 Microsoft 365 群組不會產生邀請電子郵件給來賓，因此團隊的某個人應該通知來賓。</span><span class="sxs-lookup"><span data-stu-id="30e53-120">If you add a guest directly to the Microsoft 365 group associated with a team, the guest will get access to the team but the Microsoft 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="30e53-121">來賓須遵守 [Microsoft 365 或 Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library) 和 [Azure Active Directory](/azure/active-directory/external-identities/current-limitations) 的服務限制。</span><span class="sxs-lookup"><span data-stu-id="30e53-121">Guests are subject to  [Microsoft 365 or Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library) and [Azure Active Directory](/azure/active-directory/external-identities/current-limitations) service limits.</span></span>

<span data-ttu-id="30e53-122">您可以在 Azure AD 或 Microsoft 365 安全性中心追蹤來賓的新增狀態。</span><span class="sxs-lookup"><span data-stu-id="30e53-122">You can track guest additions in Azure AD or the Microsoft 365 security center.</span></span> <span data-ttu-id="30e53-123">在 Microsoft Teams 中新增來賓將經過稽核並記錄為「已新增成員至群組」的 Azure AD 群組管理活動。</span><span class="sxs-lookup"><span data-stu-id="30e53-123">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="30e53-124">有關詳細資料，請參閱稽核及報告 [B2B 共同合作使用者](/azure/active-directory/external-identities/auditing-and-reporting) ，以及搜尋合規性中心的 [稽核記錄](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。</span><span class="sxs-lookup"><span data-stu-id="30e53-124">For more details, see [Auditing and reporting a B2B collaboration user](/azure/active-directory/external-identities/auditing-and-reporting) and [Search the audit log in the compliance Center](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>


## <a name="related-topics"></a><span data-ttu-id="30e53-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="30e53-125">Related topics</span></span>

[<span data-ttu-id="30e53-126">在 Microsoft Teams 中授權來賓存取</span><span class="sxs-lookup"><span data-stu-id="30e53-126">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)

[<span data-ttu-id="30e53-127">在 Microsoft Teams 中開啟或關閉來賓存取</span><span class="sxs-lookup"><span data-stu-id="30e53-127">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)