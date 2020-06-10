---
title: 將來賓新增至團隊
author: somakbhattacharyya
ms.author: sbhatta
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
ms.openlocfilehash: ea1670078a61366e1ab0207368a58f9ad2b900ab
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2020
ms.locfileid: "44609831"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="2f77f-103">將來賓新增至團隊</span><span class="sxs-lookup"><span data-stu-id="2f77f-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="2f77f-104">任何擁有商務或消費者電子郵件帳戶的人員 (例如 Outlook、Gmail 或其他)，都能以來賓身分加入 Teams。</span><span class="sxs-lookup"><span data-stu-id="2f77f-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="2f77f-105">身為系統管理員，您可以透過幾種方式將新來賓使用者新增至組織：</span><span class="sxs-lookup"><span data-stu-id="2f77f-105">As an admin, you can add a new guest user to the organization in a couple of ways:</span></span>
- <span data-ttu-id="2f77f-106">全域系統管理員或 Teams 系統管理員與團隊擁有者可在 Teams 用戶端或 Teams 系統管理中心中，將來賓新增至團隊。</span><span class="sxs-lookup"><span data-stu-id="2f77f-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="2f77f-107">若要深入瞭解，請參閱[將來賓新增至團隊](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。</span><span class="sxs-lookup"><span data-stu-id="2f77f-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="2f77f-108">如果您尚未設定來賓存取，請進行[來賓存取檢查清單](guest-access-checklist.md)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="2f77f-108">If you haven't set up guest access yet, go through the steps in the [Guest access checklist](guest-access-checklist.md).</span></span>

> [!NOTE] 
> <span data-ttu-id="2f77f-109">啟用 **[系統管理員和來賓邀請者角色中的使用者可邀請]** 時，則不適用。</span><span class="sxs-lookup"><span data-stu-id="2f77f-109">This does not apply when **Admins and users in the guest inviter role can invite** is enabled.</span></span> <span data-ttu-id="2f77f-110">這是因為 Teams 不支援來賓邀請者角色。</span><span class="sxs-lookup"><span data-stu-id="2f77f-110">This is because the guest inviter role isn't supported in Teams.</span></span>

- <span data-ttu-id="2f77f-111">透過 Azure Active Directory (Azure AD) B2B 共同作業，將來賓新增到您的組織。</span><span class="sxs-lookup"><span data-stu-id="2f77f-111">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="2f77f-112">全域系統管理員可以利用 Azure AD B2B 共同作業功能邀請並授權多個外部使用者，方法是將逗號分隔值 (CSV) 檔 (列數上限為 2000 列) 上傳到 B2B 共同作業入口網站。</span><span class="sxs-lookup"><span data-stu-id="2f77f-112">Azure AD B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="2f77f-113">如需詳細資訊，請參閱 [Azure Active Directory B2B 共同作業](https://go.microsoft.com/fwlink/p/?linkid=826383)。</span><span class="sxs-lookup"><span data-stu-id="2f77f-113">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="2f77f-114">透過 Azure AD B2B 共同作業功能，組織可為 B2B 使用者強制執行條件式存取和多重要素驗證 (MFA) 原則。</span><span class="sxs-lookup"><span data-stu-id="2f77f-114">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="2f77f-115">這些原則可以在租用戶層級、應用程式或個別使用者層級強制執行，與為組織全職員工和成員啟用原則的方式相同。</span><span class="sxs-lookup"><span data-stu-id="2f77f-115">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="2f77f-116">這類原則會在資源組織強制執行。</span><span class="sxs-lookup"><span data-stu-id="2f77f-116">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="2f77f-117">如需詳細資訊，請參閱[適用於 B2B 共同作業使用者的條件式存取](https://go.microsoft.com/fwlink/?linkid=857454)。</span><span class="sxs-lookup"><span data-stu-id="2f77f-117">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="2f77f-118">無法封鎖個別來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="2f77f-118">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="2f77f-119">您透過 Azure AD B2B、Microsoft 365 群組或 SharePoint Online 新增的來賓使用者已準備就緒。</span><span class="sxs-lookup"><span data-stu-id="2f77f-119">Guest users you have already added via Azure AD B2B, Microsoft 365 Groups, or SharePoint Online are ready to go.</span></span> <span data-ttu-id="2f77f-120">Microsoft 365 或 Office 365 系統管理員或團隊擁有者可將這些來賓新增至個別團隊中。</span><span class="sxs-lookup"><span data-stu-id="2f77f-120">The Microsoft 365 or Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="2f77f-121">如果團隊已使用 Microsoft 365 群組，且已將來賓新增至群組，來賓將可存取團隊。</span><span class="sxs-lookup"><span data-stu-id="2f77f-121">If a team is already with a Microsoft 365 group and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="2f77f-122">透過 Microsoft 365 群組新增來賓並不會為來賓產生邀請電子郵件，因此團隊中的人員應通知來賓。</span><span class="sxs-lookup"><span data-stu-id="2f77f-122">Adding a guest via the Microsoft 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="2f77f-123">來賓須遵守 [Microsoft 365 或 Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 和 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 的服務限制。</span><span class="sxs-lookup"><span data-stu-id="2f77f-123">Guests are subject to  [Microsoft 365 or Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="2f77f-124">您可以在 Azure AD 或 Microsoft 365 安全性中心追蹤來賓的新增狀態。</span><span class="sxs-lookup"><span data-stu-id="2f77f-124">You can track guest additions in Azure AD or the Microsoft 365 security center.</span></span> <span data-ttu-id="2f77f-125">在 Microsoft Teams 中新增來賓將經過稽核並記錄為「已新增成員至群組」的 Azure AD 群組管理活動。</span><span class="sxs-lookup"><span data-stu-id="2f77f-125">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="2f77f-126">如需詳細資訊，請參閱[稽核及報告 B2B 共同作業使用者](https://go.microsoft.com/fwlink/p/?linkid=858884)，以及[在 Microsoft 365 安全性中心搜尋稽核記錄](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)。</span><span class="sxs-lookup"><span data-stu-id="2f77f-126">For more details, see [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Microsoft 365 security center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>


## <a name="more-information"></a><span data-ttu-id="2f77f-127">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="2f77f-127">More information</span></span>

[<span data-ttu-id="2f77f-128">在 Microsoft Teams 中授權來賓存取</span><span class="sxs-lookup"><span data-stu-id="2f77f-128">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="2f77f-129">在 Microsoft Teams 中開啟或關閉來賓存取</span><span class="sxs-lookup"><span data-stu-id="2f77f-129">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="2f77f-130">使用 PowerShell 控制來賓對團隊的存取</span><span class="sxs-lookup"><span data-stu-id="2f77f-130">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)
