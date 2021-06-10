---
title: 小組的動態成員資格概觀
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何Microsoft Teams動態成員資格來支援Microsoft 365群組相關聯的團隊。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 74974f7b94a5d1bcadb340e132dae9e3b39a7704
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856322"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="384dd-103">小組的動態成員資格概觀</span><span class="sxs-lookup"><span data-stu-id="384dd-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="384dd-104">Microsoft Teams使用動態成員資格，支援Microsoft 365群組 *相關聯的團隊*。</span><span class="sxs-lookup"><span data-stu-id="384dd-104">Microsoft Teams supports teams associated with Microsoft 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="384dd-105">動態成員資格可讓團隊的成員資格由一或多個規則定義，這些規則會檢查 Azure AD Azure Active Directory (中的特定) 。</span><span class="sxs-lookup"><span data-stu-id="384dd-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="384dd-106">使用者屬性變更或使用者加入並離開租使用者時，系統會自動將使用者新增或移除至正確的團隊。</span><span class="sxs-lookup"><span data-stu-id="384dd-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="384dd-107">有了動態成員資格，您可以為貴組織中特定群組的使用者設定團隊。</span><span class="sxs-lookup"><span data-stu-id="384dd-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="384dd-108">可能的情況包括：</span><span class="sxs-lookup"><span data-stu-id="384dd-108">Possible scenarios include:</span></span>
- <span data-ttu-id="384dd-109">醫院可以建立不同的團隊，讓護士、醫生和醫生廣播通訊。</span><span class="sxs-lookup"><span data-stu-id="384dd-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="384dd-110">如果醫院仰賴臨時員工，這一點特別重要。</span><span class="sxs-lookup"><span data-stu-id="384dd-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="384dd-111">大學可以為特定學院內的所有教職員建立一個團隊，包括經常變更的教職員。</span><span class="sxs-lookup"><span data-stu-id="384dd-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="384dd-112">一家航空公司想要為每個航班建立一個團隊 (例如星期二下午從芝加哥直飛芝加哥到) 並需要自動指派或移除經常變更的乘務員。</span><span class="sxs-lookup"><span data-stu-id="384dd-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="384dd-113">使用這項功能，指定小組成員會根據一組特定的準則自動更新，而不是手動管理成員資格。</span><span class="sxs-lookup"><span data-stu-id="384dd-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="384dd-114">若要這麼做，進階版租使用者系統管理員可以將 Azure AD 授權和小組成員資格[](/azure/active-directory/users-groups-roles/groups-dynamic-membership)指派給任何使用者的 Azure AD 屬性，只要具備租使用者和系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="384dd-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="384dd-115">Microsoft Teams可能需要幾分鐘到最多 2 小時的時間，以反映動態成員資格變更一旦在團隊的 Microsoft 365 群組中生效。</span><span class="sxs-lookup"><span data-stu-id="384dd-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Microsoft 365 group for a team.</span></span>

<span data-ttu-id="384dd-116">將團隊與動態群組一起使用時：</span><span class="sxs-lookup"><span data-stu-id="384dd-116">When using teams with dynamic groups:</span></span>

- <span data-ttu-id="384dd-117">規則可以定義誰是團隊成員，但不能定義團隊擁有者。</span><span class="sxs-lookup"><span data-stu-id="384dd-117">Rules can define who is a team member, but not who is a team owner.</span></span>
- <span data-ttu-id="384dd-118">由於成員是由動態群組規則所定義，因此擁有者無法將使用者新增或移除為小組成員。</span><span class="sxs-lookup"><span data-stu-id="384dd-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
- <span data-ttu-id="384dd-119">Teams用戶端不允許團隊的成員管理。</span><span class="sxs-lookup"><span data-stu-id="384dd-119">Teams clients don't allow member management for the team.</span></span> <span data-ttu-id="384dd-120">新增成員、編輯成員角色、傳送及核准加入要求，以及離開團隊的選項都隱藏起來。</span><span class="sxs-lookup"><span data-stu-id="384dd-120">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>

<span data-ttu-id="384dd-121">若要建立使用動態成員資格的團隊，首先請建立動態Microsoft 365[群組，](/azure/active-directory/users-groups-roles/groups-create-rule)然後從該群組[建立團隊](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)。</span><span class="sxs-lookup"><span data-stu-id="384dd-121">To create a team that uses dynamic membership, start by [creating a dynamic Microsoft 365 group](/azure/active-directory/users-groups-roles/groups-create-rule) and then [create a team from that group](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).</span></span>

<span data-ttu-id="384dd-122">您可以將現有團隊變更為動態成員資格。</span><span class="sxs-lookup"><span data-stu-id="384dd-122">You can change an existing team to have a dynamic membership.</span></span> <span data-ttu-id="384dd-123">請參閱[將靜態群組成員資格變更為動態Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type)資訊。</span><span class="sxs-lookup"><span data-stu-id="384dd-123">See [Change static group membership to dynamic in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type) for information.</span></span>

## <a name="related-topics"></a><span data-ttu-id="384dd-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="384dd-124">Related topics</span></span>

[<span data-ttu-id="384dd-125">Microsoft Teams 的限制和規格</span><span class="sxs-lookup"><span data-stu-id="384dd-125">Limits and specifications for Microsoft Teams</span></span>](limits-specifications-teams.md)

[<span data-ttu-id="384dd-126">群組的動態成員資格規則Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="384dd-126">Dynamic membership rules for groups in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
