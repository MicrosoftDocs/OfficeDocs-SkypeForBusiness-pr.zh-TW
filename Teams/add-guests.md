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
description: 系統管理員可以瞭解如何在 Microsoft 團隊桌面與 web 用戶端與 Azure Active Directory B2B 共同作業入口網站中新增來賓至組織。
ms.openlocfilehash: 7f75589c5252998fb0389c743b951c0fe88e613b
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662438"
---
# <a name="add-a-guest-to-a-team"></a><span data-ttu-id="42216-103">將來賓新增至團隊</span><span class="sxs-lookup"><span data-stu-id="42216-103">Add a guest to a team</span></span>

<span data-ttu-id="42216-104">任何擁有商務或消費者電子郵件帳戶的人員 (例如 Outlook、Gmail 或其他)，都能以來賓身分加入 Teams。</span><span class="sxs-lookup"><span data-stu-id="42216-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="42216-105">就像管理員一樣，您可以使用幾種方法，將新的來賓新增至組織：</span><span class="sxs-lookup"><span data-stu-id="42216-105">As an admin, you can add a new guest to the organization in a couple of ways:</span></span>

- <span data-ttu-id="42216-106">全域系統管理員或 Teams 系統管理員與團隊擁有者可在 Teams 用戶端或 Teams 系統管理中心中，將來賓新增至團隊。</span><span class="sxs-lookup"><span data-stu-id="42216-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="42216-107">若要深入瞭解，請參閱[將來賓新增至團隊](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。</span><span class="sxs-lookup"><span data-stu-id="42216-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="42216-108">如果您尚未設定來賓存取，請透過[在小組中與來賓共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)步驟設定。</span><span class="sxs-lookup"><span data-stu-id="42216-108">If you haven't set up guest access yet, go through the steps in the [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

- <span data-ttu-id="42216-109">透過 Azure Active Directory (Azure AD) B2B 共同作業，將來賓新增到您的組織。</span><span class="sxs-lookup"><span data-stu-id="42216-109">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="42216-110">如需詳細資訊，請參閱 [快速入門：在 Azure 入口網站中將來賓新增至您的目錄](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)。</span><span class="sxs-lookup"><span data-stu-id="42216-110">For details, check out [Quickstart: Add guests to your directory in the Azure portal](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

<span data-ttu-id="42216-111">系統管理員還可以透過指派 [來賓邀請者] 角色，將新增來賓到組織的權限委派給其他人。</span><span class="sxs-lookup"><span data-stu-id="42216-111">Admins can also delegate permissions to add guests to others in their organization by assigning the Guest Inviter role.</span></span> <span data-ttu-id="42216-112">如需詳細資訊，請參閱[啟用 B2B 外部共同作業和管理可以邀請來賓的使用者](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="42216-112">For more information, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span>

<span data-ttu-id="42216-113">透過 Azure AD B2B 共同作業功能，組織可為 B2B 使用者強制執行條件式存取和多重要素驗證 (MFA) 原則。</span><span class="sxs-lookup"><span data-stu-id="42216-113">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="42216-114">這些原則可以在租用戶層級、應用程式或個別使用者層級強制執行，與為組織全職員工和成員啟用原則的方式相同。</span><span class="sxs-lookup"><span data-stu-id="42216-114">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="42216-115">這類原則會在資源組織強制執行。</span><span class="sxs-lookup"><span data-stu-id="42216-115">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="42216-116">如需詳細資訊，請參閱[適用於 B2B 共同作業使用者的條件式存取](https://go.microsoft.com/fwlink/?linkid=857454)。</span><span class="sxs-lookup"><span data-stu-id="42216-116">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="42216-117">無法封鎖個別來賓。</span><span class="sxs-lookup"><span data-stu-id="42216-117">Individual guests can't be blocked.</span></span>

<span data-ttu-id="42216-118">您已透過 Azure AD B2B、Microsoft 365 群組或 SharePoint 新增的來賓已就緒，可以開始使用。</span><span class="sxs-lookup"><span data-stu-id="42216-118">Guests you have already added via Azure AD B2B, Microsoft 365 Groups, or SharePoint are ready to go.</span></span> <span data-ttu-id="42216-119">Microsoft 365 管理員或團隊擁有者可以將這些來賓新增至其各自的小組。</span><span class="sxs-lookup"><span data-stu-id="42216-119">The Microsoft 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="42216-120">如果您直接將來賓新增到與團隊相關聯的 Microsoft 365 群組，來賓就會取得該小組的存取權，但 Microsoft 365 群組不會產生邀請電子郵件給訪客，所以小組中的人員應該通知訪客。</span><span class="sxs-lookup"><span data-stu-id="42216-120">If you add a guest directly to the Microsoft 365 group associated with a team, the guest will get access to the team but the Microsoft 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="42216-121">來賓須遵守 [Microsoft 365 或 Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 的服務限制。</span><span class="sxs-lookup"><span data-stu-id="42216-121">Guests are subject to  [Microsoft 365 or Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="42216-122">您可以在 Azure AD 或 Microsoft 365 安全性中心追蹤來賓的新增狀態。</span><span class="sxs-lookup"><span data-stu-id="42216-122">You can track guest additions in Azure AD or the Microsoft 365 security center.</span></span> <span data-ttu-id="42216-123">在 Microsoft Teams 中新增來賓將經過稽核並記錄為「已新增成員至群組」的 Azure AD 群組管理活動。</span><span class="sxs-lookup"><span data-stu-id="42216-123">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="42216-124">如需詳細資訊，請參閱 [審核與報告 B2B](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) 共同作業使用者，並 [在規範中心搜尋審核記錄](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。</span><span class="sxs-lookup"><span data-stu-id="42216-124">For more details, see [Auditing and reporting a B2B collaboration user](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) and [Search the audit log in the compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>


## <a name="related-topics"></a><span data-ttu-id="42216-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="42216-125">Related topics</span></span>

[<span data-ttu-id="42216-126">在 Microsoft Teams 中授權來賓存取</span><span class="sxs-lookup"><span data-stu-id="42216-126">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)

[<span data-ttu-id="42216-127">在 Microsoft Teams 中開啟或關閉來賓存取</span><span class="sxs-lookup"><span data-stu-id="42216-127">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)
