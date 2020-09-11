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
search.appverid: MET150
ms.reviewer: sbhatta
f1.keywords:
- NOCSH
localization_priority: Priority
description: 系統管理員可以了解如何將新的來賓使用者新增至 Microsoft Teams 桌面版和網頁用戶端中的組織，以及 Azure Active Directory B2B 共同作業入口網站。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a67fd7ed111c1020eaf133e96e26ae03d4250637
ms.sourcegitcommit: 207c58563b7b2aba274b067cf64242abd7a33c2c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405710"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="a507a-103">將來賓新增至團隊</span><span class="sxs-lookup"><span data-stu-id="a507a-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="a507a-104">任何擁有商務或消費者電子郵件帳戶的人員 (例如 Outlook、Gmail 或其他)，都能以來賓身分加入 Teams。</span><span class="sxs-lookup"><span data-stu-id="a507a-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="a507a-105">身為系統管理員，您可以透過幾種方式將新來賓使用者新增至組織：</span><span class="sxs-lookup"><span data-stu-id="a507a-105">As an admin, you can add a new guest user to the organization in a couple of ways:</span></span>
- <span data-ttu-id="a507a-106">全域系統管理員或 Teams 系統管理員與團隊擁有者可在 Teams 用戶端或 Teams 系統管理中心中，將來賓新增至團隊。</span><span class="sxs-lookup"><span data-stu-id="a507a-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="a507a-107">若要深入瞭解，請參閱[將來賓新增至團隊](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。</span><span class="sxs-lookup"><span data-stu-id="a507a-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="a507a-108">如果您尚未設定來賓存取，請透過[在小組中與來賓共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)步驟設定。</span><span class="sxs-lookup"><span data-stu-id="a507a-108">If you haven't set up guest access yet, go through the steps in the [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

- <span data-ttu-id="a507a-109">透過 Azure Active Directory (Azure AD) B2B 共同作業，將來賓新增到您的組織。</span><span class="sxs-lookup"><span data-stu-id="a507a-109">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="a507a-110">全域系統管理員可以利用 Azure AD B2B 共同作業功能邀請並授權多個外部使用者，方法是將逗號分隔值 (CSV) 檔 (列數上限為 2000 列) 上傳到 B2B 共同作業入口網站。</span><span class="sxs-lookup"><span data-stu-id="a507a-110">Azure AD B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="a507a-111">如需詳細資訊，請參閱 [Azure Active Directory B2B 共同作業](https://go.microsoft.com/fwlink/p/?linkid=826383)。</span><span class="sxs-lookup"><span data-stu-id="a507a-111">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="a507a-112">系統管理員還可以透過指派 [來賓邀請者] 角色，將新增來賓到組織的權限委派給其他人。</span><span class="sxs-lookup"><span data-stu-id="a507a-112">Admins can also delegate permissions to add guests to others in their organization by assigning the Guest Inviter role.</span></span> <span data-ttu-id="a507a-113">如需詳細資訊，請參閱[啟用 B2B 外部共同作業和管理可以邀請來賓的使用者](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="a507a-113">For more information, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span>

<span data-ttu-id="a507a-114">透過 Azure AD B2B 共同作業功能，組織可為 B2B 使用者強制執行條件式存取和多重要素驗證 (MFA) 原則。</span><span class="sxs-lookup"><span data-stu-id="a507a-114">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="a507a-115">這些原則可以在租用戶層級、應用程式或個別使用者層級強制執行，與為組織全職員工和成員啟用原則的方式相同。</span><span class="sxs-lookup"><span data-stu-id="a507a-115">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="a507a-116">這類原則會在資源組織強制執行。</span><span class="sxs-lookup"><span data-stu-id="a507a-116">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="a507a-117">如需詳細資訊，請參閱[適用於 B2B 共同作業使用者的條件式存取](https://go.microsoft.com/fwlink/?linkid=857454)。</span><span class="sxs-lookup"><span data-stu-id="a507a-117">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="a507a-118">無法封鎖個別來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="a507a-118">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="a507a-119">您透過 Azure AD B2B、Microsoft 365 群組或 SharePoint Online 新增的來賓使用者已準備就緒。</span><span class="sxs-lookup"><span data-stu-id="a507a-119">Guest users you have already added via Azure AD B2B, Microsoft 365 Groups, or SharePoint Online are ready to go.</span></span> <span data-ttu-id="a507a-120">Microsoft 365 或 Office 365 系統管理員或團隊擁有者可將這些來賓新增至個別團隊中。</span><span class="sxs-lookup"><span data-stu-id="a507a-120">The Microsoft 365 or Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="a507a-121">如果團隊已使用 Microsoft 365 群組，且已將來賓新增至群組，來賓將可存取團隊。</span><span class="sxs-lookup"><span data-stu-id="a507a-121">If a team is already with a Microsoft 365 group and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="a507a-122">透過 Microsoft 365 群組新增來賓並不會為來賓產生邀請電子郵件，因此團隊中的人員應通知來賓。</span><span class="sxs-lookup"><span data-stu-id="a507a-122">Adding a guest via the Microsoft 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="a507a-123">來賓須遵守 [Microsoft 365 或 Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 的服務限制。</span><span class="sxs-lookup"><span data-stu-id="a507a-123">Guests are subject to  [Microsoft 365 or Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="a507a-124">您可以在 Azure AD 或 Microsoft 365 安全性中心追蹤來賓的新增狀態。</span><span class="sxs-lookup"><span data-stu-id="a507a-124">You can track guest additions in Azure AD or the Microsoft 365 security center.</span></span> <span data-ttu-id="a507a-125">在 Microsoft Teams 中新增來賓將經過稽核並記錄為「已新增成員至群組」的 Azure AD 群組管理活動。</span><span class="sxs-lookup"><span data-stu-id="a507a-125">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="a507a-126">如需詳細資訊，請參閱[稽核及報告 B2B 共同作業使用者](https://go.microsoft.com/fwlink/p/?linkid=858884)，以及[在 Microsoft 365 安全性中心搜尋稽核記錄](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)。</span><span class="sxs-lookup"><span data-stu-id="a507a-126">For more details, see [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Microsoft 365 security center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>


## <a name="more-information"></a><span data-ttu-id="a507a-127">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="a507a-127">More information</span></span>

[<span data-ttu-id="a507a-128">在 Microsoft Teams 中授權來賓存取</span><span class="sxs-lookup"><span data-stu-id="a507a-128">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="a507a-129">在 Microsoft Teams 中開啟或關閉來賓存取</span><span class="sxs-lookup"><span data-stu-id="a507a-129">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="a507a-130">使用 PowerShell 控制來賓對團隊的存取</span><span class="sxs-lookup"><span data-stu-id="a507a-130">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)
