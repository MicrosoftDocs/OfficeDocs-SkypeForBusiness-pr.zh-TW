---
title: 團隊的動態成員資格概覽
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解以 AAD 為基礎的動態團隊成員資格。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3d22c7f068617cd4c5c73c850a37eaa89a0c8efa
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569893"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="1720b-103">團隊的動態成員資格概覽</span><span class="sxs-lookup"><span data-stu-id="1720b-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="1720b-104">Microsoft 團隊支援使用*動態成員資格*與 Office 365 群組相關聯的小組。</span><span class="sxs-lookup"><span data-stu-id="1720b-104">Microsoft Teams supports teams associated with Office 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="1720b-105">動態成員資格可讓團隊的成員資格由一或多個在 Azure Active Directory （Azure AD）中檢查特定使用者屬性的規則所定義。</span><span class="sxs-lookup"><span data-stu-id="1720b-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="1720b-106">當使用者屬性變更或使用者加入並離開租使用者時，系統會自動新增或移除正確的團隊。</span><span class="sxs-lookup"><span data-stu-id="1720b-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="1720b-107">在動態成員資格中，您可以針對組織中的某些使用者設定小組 cohorts。</span><span class="sxs-lookup"><span data-stu-id="1720b-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="1720b-108">可能的案例包括：</span><span class="sxs-lookup"><span data-stu-id="1720b-108">Possible scenarios include:</span></span>
- <span data-ttu-id="1720b-109">醫院可以為護士、醫生和 surgeons 建立獨特的小組來廣播通訊。</span><span class="sxs-lookup"><span data-stu-id="1720b-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="1720b-110">如果醫院依賴 temp 員工，這一點尤為重要。</span><span class="sxs-lookup"><span data-stu-id="1720b-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="1720b-111">學校可以為特定大學中的所有教職員建立小組，包括經常變更的附屬教職員。</span><span class="sxs-lookup"><span data-stu-id="1720b-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="1720b-112">航空公司想要為每個航班建立小組（例如週二下午不停從芝加哥到亞特蘭大），而且經常變更的航班人員會視需要自動指派或移除。</span><span class="sxs-lookup"><span data-stu-id="1720b-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="1720b-113">使用此功能時，指定團隊的成員會根據一組特定的準則自動更新，而不是手動管理成員資格。</span><span class="sxs-lookup"><span data-stu-id="1720b-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="1720b-114">如果您有租使用者與管理員帳戶，只要擁有 Azure AD Premium P1 授權和團隊成員資格，就可以[由租使用者管理員指派](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)給任何使用者的 Azure ad 屬性。</span><span class="sxs-lookup"><span data-stu-id="1720b-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="1720b-115">Microsoft 團隊可能需要幾分鐘的時間，才能在小組的 Office 365 群組中生效，以反映出動態成員資格變更。</span><span class="sxs-lookup"><span data-stu-id="1720b-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Office 365 group for a team.</span></span>

> [!NOTE]
> - <span data-ttu-id="1720b-116">規則可以定義誰是團隊成員，而不是團隊擁有者。</span><span class="sxs-lookup"><span data-stu-id="1720b-116">Rules can define who is a team member, but not who is a team owner.</span></span>
> - <span data-ttu-id="1720b-117">請參閱 Microsoft 團隊針對團隊和頻道大小目前限制的[限制與規格](limits-specifications-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="1720b-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on team and channel sizes.</span></span>
> - <span data-ttu-id="1720b-118">因為成員是由動態群組規則所定義，所以擁有者將無法將使用者新增或移除為小組成員。</span><span class="sxs-lookup"><span data-stu-id="1720b-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
> - <span data-ttu-id="1720b-119">成員將無法留下動態群組所支援的小組。</span><span class="sxs-lookup"><span data-stu-id="1720b-119">Members will not be able to leave teams backed by dynamic groups.</span></span>


## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a><span data-ttu-id="1720b-120">使用動態成員資格建立及管理 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="1720b-120">Creating and managing an Office 365 group with dynamic membership</span></span>
<span data-ttu-id="1720b-121">以租使用者管理員身分登入時，請依照[建立動態群組和檢查狀態](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="1720b-121">While logged in as the tenant admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="1720b-122">如有需要，請參閱[Azure Active Directory 中群組的動態成員資格規則](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)。</span><span class="sxs-lookup"><span data-stu-id="1720b-122">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-o365-group"></a><span data-ttu-id="1720b-123">使用您的 O365 群組建立新團隊</span><span class="sxs-lookup"><span data-stu-id="1720b-123">Create a new team with your O365 group</span></span>

<span data-ttu-id="1720b-124">現在允許成員資格變更的時間生效，並以[Microsoft 團隊增強現有的 Office 365 群組](enhance-office-365-groups.md)中所述的方式來建立新的團隊。</span><span class="sxs-lookup"><span data-stu-id="1720b-124">Now allow time for the membership changes to take effect, and create a new team  as described in [Enhance Existing Office 365 groups with Microsoft Teams](enhance-office-365-groups.md).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="1720b-125">將動態成員資格套用至現有的團隊</span><span class="sxs-lookup"><span data-stu-id="1720b-125">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="1720b-126">您也可以使用現有的小組，並將其變更為擁有動態的成員資格，如在[Azure Active Directory 中將靜態群組成員資格變更為動態](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)時所述。</span><span class="sxs-lookup"><span data-stu-id="1720b-126">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="1720b-127">用戶端行為的變更</span><span class="sxs-lookup"><span data-stu-id="1720b-127">Changes in client behavior</span></span>

<span data-ttu-id="1720b-128">針對團隊啟用動態成員資格之後，團隊用戶端就不會再允許團隊成員管理了。</span><span class="sxs-lookup"><span data-stu-id="1720b-128">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="1720b-129">[新增成員]、[編輯成員角色]、[傳送及核准加入要求] 的選項，並讓團隊保持全部隱藏。</span><span class="sxs-lookup"><span data-stu-id="1720b-129">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
