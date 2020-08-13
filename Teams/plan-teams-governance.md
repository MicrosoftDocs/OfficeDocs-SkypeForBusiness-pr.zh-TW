---
title: 在小組中規劃管理-Microsoft 團隊
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/10/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 在本文中，您將瞭解如何規劃在團隊中實施系統管理功能。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea48b4df3313784cf129cf483aebac341917cb21
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656354"
---
# <a name="plan-for-governance-in-teams"></a><span data-ttu-id="b3604-103">Teams 中的控管方案</span><span class="sxs-lookup"><span data-stu-id="b3604-103">Plan for governance in Teams</span></span>

<span data-ttu-id="b3604-104">團隊會提供一組豐富的工具來實施貴組織可能需要的任何管轄功能。</span><span class="sxs-lookup"><span data-stu-id="b3604-104">Teams provides a rich set of tools to implement any governance capabilities your organization might require.</span></span> <span data-ttu-id="b3604-105">本文將指導 IT 專業人員提出正確的問題，以決定其管理需求，以及如何滿足他們的需求。</span><span class="sxs-lookup"><span data-stu-id="b3604-105">This article guides IT pros to ask the right questions to determine their requirements for governance, and how to meet them.</span></span> 

> [!Tip] 
> <span data-ttu-id="b3604-106">請觀看下列會話，深入瞭解 Microsoft 團隊中的管轄：[管理、管理與生命週期](https://aka.ms/teams-governance)</span><span class="sxs-lookup"><span data-stu-id="b3604-106">Watch the following session to learn about more about Governance in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)</span></span>

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a><span data-ttu-id="b3604-107">群組和小組建立、命名、分類和來賓存取</span><span class="sxs-lookup"><span data-stu-id="b3604-107">Group and team creation, naming, classification, and guest access</span></span>

<span data-ttu-id="b3604-108">您的組織可能會要求您在小組命名及分類的方式上執行嚴格的控制，您可以將來賓新增為小組成員，以及誰可以建立團隊。</span><span class="sxs-lookup"><span data-stu-id="b3604-108">Your organization might require that you implement strict controls on how teams are named and classified, whether guests can be added as team members, and who can create teams.</span></span> <span data-ttu-id="b3604-109">您可以使用 Azure Active Directory (Azure AD) 來設定這些區域。</span><span class="sxs-lookup"><span data-stu-id="b3604-109">You can configure each of these areas by using Azure Active Directory (Azure AD).</span></span> 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |<span data-ttu-id="b3604-110">決策點</span><span class="sxs-lookup"><span data-stu-id="b3604-110">Decision points</span></span>|<ul><li><span data-ttu-id="b3604-111">貴組織是否需要適用于團隊的特定命名慣例？</span><span class="sxs-lookup"><span data-stu-id="b3604-111">Does your organization require a specific naming convention for teams?</span></span></li><li><span data-ttu-id="b3604-112">小組創作者是否需要能夠將組織特定分類指派給團隊？</span><span class="sxs-lookup"><span data-stu-id="b3604-112">Do team creators need the ability to assign organization-specific classifications to teams?</span></span></li><li><span data-ttu-id="b3604-113">您是否需要限制將來賓新增到小組的人員的能力？</span><span class="sxs-lookup"><span data-stu-id="b3604-113">Do you need to restrict the ability to add guests to teams on a per-team basis?</span></span></li><li><span data-ttu-id="b3604-114">貴組織是否需要限制誰可以建立團隊？</span><span class="sxs-lookup"><span data-stu-id="b3604-114">Does your organization require limiting who can create teams?</span></span></li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|<span data-ttu-id="b3604-115">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b3604-115">Next steps</span></span>|<ul><li><span data-ttu-id="b3604-116">記錄貴組織建立、命名、分類和來賓存取的需求。</span><span class="sxs-lookup"><span data-stu-id="b3604-116">Document your organization’s requirements for team creation, naming, classification, and guest access.</span></span></li><li><span data-ttu-id="b3604-117">規劃將這些需求作為小組推出的一部分來執行。</span><span class="sxs-lookup"><span data-stu-id="b3604-117">Plan to implement these requirements as a part of your Teams rollout.</span></span></li><li><span data-ttu-id="b3604-118">溝通及發佈您的原則，以告知小組使用者他們可以預期的行為。</span><span class="sxs-lookup"><span data-stu-id="b3604-118">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
> <span data-ttu-id="b3604-119">使用下表來捕獲貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="b3604-119">Use the following table to capture your organization’s requirements.</span></span>

|<span data-ttu-id="b3604-120">功能</span><span class="sxs-lookup"><span data-stu-id="b3604-120">Capability</span></span> |<span data-ttu-id="b3604-121">詳細資料</span><span class="sxs-lookup"><span data-stu-id="b3604-121">Details</span></span> |<span data-ttu-id="b3604-122">Azure AD Premium</span><span class="sxs-lookup"><span data-stu-id="b3604-122">Azure AD Premium</span></span> <br> <span data-ttu-id="b3604-123">需要授權</span><span class="sxs-lookup"><span data-stu-id="b3604-123">license required</span></span> |<span data-ttu-id="b3604-124">決議</span><span class="sxs-lookup"><span data-stu-id="b3604-124">Decision</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="b3604-125">團隊命名原則</span><span class="sxs-lookup"><span data-stu-id="b3604-125">Team naming policy</span></span> | <span data-ttu-id="b3604-126">使用以前置詞為基礎的自訂封鎖字。</span><span class="sxs-lookup"><span data-stu-id="b3604-126">Use Prefix-Suffix–based, Custom Blocked Words.</span></span> |<span data-ttu-id="b3604-127">P1</span><span class="sxs-lookup"><span data-stu-id="b3604-127">P1</span></span> |<span data-ttu-id="b3604-128">TBD</span><span class="sxs-lookup"><span data-stu-id="b3604-128">TBD</span></span> |
|<span data-ttu-id="b3604-129">小組分類</span><span class="sxs-lookup"><span data-stu-id="b3604-129">Team classification</span></span> |<span data-ttu-id="b3604-130">指派分類給小組。</span><span class="sxs-lookup"><span data-stu-id="b3604-130">Assign classifications to teams.</span></span> |<span data-ttu-id="b3604-131">P1</span><span class="sxs-lookup"><span data-stu-id="b3604-131">P1</span></span> |<span data-ttu-id="b3604-132">TBD</span><span class="sxs-lookup"><span data-stu-id="b3604-132">TBD</span></span> |
|<span data-ttu-id="b3604-133">小組來賓存取</span><span class="sxs-lookup"><span data-stu-id="b3604-133">Team guest access</span></span> |<span data-ttu-id="b3604-134">允許或禁止將來賓新增至小組。</span><span class="sxs-lookup"><span data-stu-id="b3604-134">Allow or prevent guests from being added to teams.</span></span> |<span data-ttu-id="b3604-135">否</span><span class="sxs-lookup"><span data-stu-id="b3604-135">No</span></span> |<span data-ttu-id="b3604-136">TBD</span><span class="sxs-lookup"><span data-stu-id="b3604-136">TBD</span></span> |
|<span data-ttu-id="b3604-137">小組建立</span><span class="sxs-lookup"><span data-stu-id="b3604-137">Team creation</span></span> |<span data-ttu-id="b3604-138">將小組建立限制為管理員。</span><span class="sxs-lookup"><span data-stu-id="b3604-138">Limit team creation to administrators.</span></span> |<span data-ttu-id="b3604-139">否</span><span class="sxs-lookup"><span data-stu-id="b3604-139">No</span></span> |<span data-ttu-id="b3604-140">TBD</span><span class="sxs-lookup"><span data-stu-id="b3604-140">TBD</span></span>|
|<span data-ttu-id="b3604-141">小組建立</span><span class="sxs-lookup"><span data-stu-id="b3604-141">Team creation</span></span> |<span data-ttu-id="b3604-142">將小組建立限制為安全群組成員。</span><span class="sxs-lookup"><span data-stu-id="b3604-142">Limit team creation to security group members.</span></span> |<span data-ttu-id="b3604-143">P1</span><span class="sxs-lookup"><span data-stu-id="b3604-143">P1</span></span> |<span data-ttu-id="b3604-144">TBD</span><span class="sxs-lookup"><span data-stu-id="b3604-144">TBD</span></span>|

> [!NOTE]
> <span data-ttu-id="b3604-145">若要協助您預先規劃，請[進一步瞭解如何設定這些原則以及他們所需的授權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)。</span><span class="sxs-lookup"><span data-stu-id="b3604-145">To help you plan ahead, [learn more about setting these policies and what licenses they require](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).</span></span>
> 
> [!NOTE]
> <span data-ttu-id="b3604-146">限制群組和小組建立可能會降低使用者的生產力，因為許多 Microsoft 365 和 Office 365 服務都需要建立群組才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="b3604-146">Limiting group and team creation can slow your users’ productivity, because many Microsoft 365 and Office 365 services require that groups be created for the service to function.</span></span> <span data-ttu-id="b3604-147">如需其他資訊，請流覽並展開[控制誰能建立 Microsoft 365 群組的原因](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)。</span><span class="sxs-lookup"><span data-stu-id="b3604-147">For additional information, navigate to and expand [Why control who creates Microsoft 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).</span></span>


#### <a name="additional-information"></a><span data-ttu-id="b3604-148">其他資訊</span><span class="sxs-lookup"><span data-stu-id="b3604-148">Additional information</span></span>

<span data-ttu-id="b3604-149">在您決定需求之後，您可以使用 Azure AD 控制項來實現它們。</span><span class="sxs-lookup"><span data-stu-id="b3604-149">After you’ve determined your requirements, you can implement them by using Azure AD controls.</span></span> <span data-ttu-id="b3604-150">如需如何實現這些設定的技術指導方針，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b3604-150">For technical guidance on how to implement these settings, see:</span></span>

- <span data-ttu-id="b3604-151">[Azure Active Directory Cmdlet，用於設定群組設定](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)。</span><span class="sxs-lookup"><span data-stu-id="b3604-151">[Azure Active Directory cmdlets for configuring group settings](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets).</span></span>

- <span data-ttu-id="b3604-152">[在 Azure Active Directory 中強制執行 Microsoft 365 群組的命名原則](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)。</span><span class="sxs-lookup"><span data-stu-id="b3604-152">[Enforce a naming policy for Microsoft 365 groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).</span></span>

- <span data-ttu-id="b3604-153">[Microsoft 365 群組命名原則](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。</span><span class="sxs-lookup"><span data-stu-id="b3604-153">[Microsoft 365 Groups naming policy](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>


## <a name="group-and-team-expiration-retention-and-archiving"></a><span data-ttu-id="b3604-154">群組和小組到期、保留及封存</span><span class="sxs-lookup"><span data-stu-id="b3604-154">Group and team expiration, retention, and archiving</span></span>

<span data-ttu-id="b3604-155">您的組織可能對設定到期、保留及封存團隊及小組資料 (通道訊息及) 通道檔案的其他需求。</span><span class="sxs-lookup"><span data-stu-id="b3604-155">Your organization might have additional requirements for setting policies for expiration, retention, and archiving teams and teams data (channel messages and channel files).</span></span> <span data-ttu-id="b3604-156">您可以設定群組過期原則來自動管理群組和保留原則的生命週期，以根據需要保留或刪除資訊，而且您可以將團隊封存 (將其設為唯讀模式) ，以保留不在使用中的小組的時間點視圖。</span><span class="sxs-lookup"><span data-stu-id="b3604-156">You can configure group expiration policies to automatically manage the lifecycle of the group and retention policies to preserve or delete information as needed, and you can archive teams (set them to read-only mode) to preserve a point-in-time view of a team that’s no longer active.</span></span>

|           |            |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="b3604-158">決策點</span><span class="sxs-lookup"><span data-stu-id="b3604-158">Decision points</span></span>|<ul><li><span data-ttu-id="b3604-159">貴組織是否需要指定團隊的到期日？</span><span class="sxs-lookup"><span data-stu-id="b3604-159">Does your organization require specifying an expiration date for teams?</span></span></li><li><span data-ttu-id="b3604-160">貴組織是否需要將特定的資料保留原則套用至團隊？</span><span class="sxs-lookup"><span data-stu-id="b3604-160">Does your organization require specific data retention policies be applied to teams?</span></span></li><li><span data-ttu-id="b3604-161">貴組織是否希望能夠封存不活躍的小組，以保持內容處於唯讀狀態？</span><span class="sxs-lookup"><span data-stu-id="b3604-161">Does your organization expect to require the ability to archive inactive teams to preserve the content in a read-only state?</span></span></li></ul>|
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/><span data-ttu-id="b3604-163">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b3604-163">Next steps</span></span>|<ul><li><span data-ttu-id="b3604-164">記錄貴組織的小組到期、資料保留及封存需求。</span><span class="sxs-lookup"><span data-stu-id="b3604-164">Document your organization’s requirements for team expiration, data retention, and archiving.</span></span></li><li><span data-ttu-id="b3604-165">規劃將這些需求作為您團隊推出的一部分來執行。</span><span class="sxs-lookup"><span data-stu-id="b3604-165">Plan to implement these requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="b3604-166">溝通及發佈您的原則，以告知小組使用者他們可以預期的行為。</span><span class="sxs-lookup"><span data-stu-id="b3604-166">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
> <span data-ttu-id="b3604-167">使用下表來捕獲貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="b3604-167">Use the following table to capture your organization’s requirements.</span></span>

|<span data-ttu-id="b3604-168">功能</span><span class="sxs-lookup"><span data-stu-id="b3604-168">Capability</span></span> |<span data-ttu-id="b3604-169">詳細資料</span><span class="sxs-lookup"><span data-stu-id="b3604-169">Details</span></span> |<span data-ttu-id="b3604-170">需要 Azure AD Premium 授權</span><span class="sxs-lookup"><span data-stu-id="b3604-170">Azure AD Premium license required</span></span> |<span data-ttu-id="b3604-171">決議</span><span class="sxs-lookup"><span data-stu-id="b3604-171">Decision</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="b3604-172">過期原則</span><span class="sxs-lookup"><span data-stu-id="b3604-172">Expiration policy</span></span> |<span data-ttu-id="b3604-173">設定過期原則，管理 Microsoft 365 群組的週期。</span><span class="sxs-lookup"><span data-stu-id="b3604-173">Manage the lifecycle of Microsoft 365 groups by setting an expiration policy.</span></span> |<span data-ttu-id="b3604-174">P1</span><span class="sxs-lookup"><span data-stu-id="b3604-174">P1</span></span> |<span data-ttu-id="b3604-175">TBD</span><span class="sxs-lookup"><span data-stu-id="b3604-175">TBD</span></span>|
|<span data-ttu-id="b3604-176">保留原則</span><span class="sxs-lookup"><span data-stu-id="b3604-176">Retention policy</span></span> |<span data-ttu-id="b3604-177">在安全性 & 合規性中心設定小組的保留原則，以保留或刪除特定時段內的資料。</span><span class="sxs-lookup"><span data-stu-id="b3604-177">Retain or delete data for a specific time period by setting retention policies for Teams in the Security & compliance center.</span></span> <span data-ttu-id="b3604-178">**注意**：使用這項功能需要授權 Microsoft 365 或 Office 365 Enterprise E3 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="b3604-178">**Note**: Using this feature requires licensing of Microsoft 365 or Office 365 Enterprise E3 or above.</span></span> |<span data-ttu-id="b3604-179">否</span><span class="sxs-lookup"><span data-stu-id="b3604-179">No</span></span> |<span data-ttu-id="b3604-180">TBD</span><span class="sxs-lookup"><span data-stu-id="b3604-180">TBD</span></span> |
|<span data-ttu-id="b3604-181">封存和還原</span><span class="sxs-lookup"><span data-stu-id="b3604-181">Archive and restore</span></span> |<span data-ttu-id="b3604-182">當小組已不在使用中，但您想要保留以供參考或在將來重新啟用時，請封存團隊。</span><span class="sxs-lookup"><span data-stu-id="b3604-182">Archive a team when it’s no longer active but you want to keep it around for reference or to reactivate in the future.</span></span> |<span data-ttu-id="b3604-183">否</span><span class="sxs-lookup"><span data-stu-id="b3604-183">No</span></span> |<span data-ttu-id="b3604-184">TBD</span><span class="sxs-lookup"><span data-stu-id="b3604-184">TBD</span></span> |

> [!Note]
> <span data-ttu-id="b3604-185">[群組到期] 是 Azure AD Premium 功能。</span><span class="sxs-lookup"><span data-stu-id="b3604-185">Group expiration is an Azure AD Premium feature.</span></span> <span data-ttu-id="b3604-186">若要使用此功能，您的租使用者必須具備 Azure AD Premium 的訂閱，以及設定受影響群組之成員之系統管理員的授權。</span><span class="sxs-lookup"><span data-stu-id="b3604-186">For this feature to be available, your tenant must have a subscription to Azure AD Premium and licenses for the administrator who configures the settings and the members of the affected groups.</span></span>

#### <a name="additional-information"></a><span data-ttu-id="b3604-187">其他資訊</span><span class="sxs-lookup"><span data-stu-id="b3604-187">Additional information</span></span>

<span data-ttu-id="b3604-188">如需如何實現這些設定的技術指導方針，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b3604-188">For technical guidance on how to implement these settings, see:</span></span>

- <span data-ttu-id="b3604-189">[設定 Microsoft 365 群組到期](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)日。</span><span class="sxs-lookup"><span data-stu-id="b3604-189">[Set up Microsoft 365 groups expiration](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).</span></span>

- <span data-ttu-id="b3604-190">[設定小組保留原則](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b3604-190">[Set up Teams retention policies](retention-policies.md).</span></span>

- <span data-ttu-id="b3604-191">封存[或還原團隊](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。</span><span class="sxs-lookup"><span data-stu-id="b3604-191">[Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>

## <a name="group-and-team-membership-management"></a><span data-ttu-id="b3604-192">群組和小組成員資格管理</span><span class="sxs-lookup"><span data-stu-id="b3604-192">Group and team membership management</span></span>

<span data-ttu-id="b3604-193">在需要快速加入和脫離或使用者和來賓的小組中，始終如一地管理以專案為基礎的成員或受限制的群組是必要的。</span><span class="sxs-lookup"><span data-stu-id="b3604-193">Consistently managing members of project based, or restricted groups are necessary for teams that require rapid onboarding and offboarding or users and guests.</span></span> <span data-ttu-id="b3604-194">貴組織也可能需要確保所有目前成員都能在小組中進行業務調整。</span><span class="sxs-lookup"><span data-stu-id="b3604-194">Your organization may also need to make sure all current members have the business justification to be in a team.</span></span> <span data-ttu-id="b3604-195">管理成員可能很困難，因為小組擁有者可以離開，而且使用者通常不會在專案結束或變更角色時離開群組本身。</span><span class="sxs-lookup"><span data-stu-id="b3604-195">Managing members can be hard because team owners can leave and users don’t usually leave groups on their own accord when a project ends or when they change roles.</span></span> <span data-ttu-id="b3604-196">管理群組成員資格的最佳方式，可讓使用者在需要時取得存取權，但確定群組沒有不當存取的風險是透過兩個地區流程： [權利管理與存取權審查]。</span><span class="sxs-lookup"><span data-stu-id="b3604-196">The best way to manage group membership that allows users to get access when needed but ensure the group doesn't have a risk of inappropriate access is through two district processes: entitlement management and access reviews.</span></span>

<span data-ttu-id="b3604-197">[[權利管理](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)] 可讓您委派給某個人（例如專案經理），以便將所需的所有資源（包括團隊成員資格）收集到單一套件中。</span><span class="sxs-lookup"><span data-stu-id="b3604-197">[Entitlement management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) allows you to delegate to someone, such as a project manager, to collect all the resources that are needed, including teams memberships, into a single package.</span></span> <span data-ttu-id="b3604-198">他們也可以定義誰可以發出要求：您租使用者中的使用者或來自其他已連接的組織。</span><span class="sxs-lookup"><span data-stu-id="b3604-198">They can also define who can make requests: either users in your tenant or from other connected organizations.</span></span> <span data-ttu-id="b3604-199">專案經理將會在其電子郵件中收到存取要求，並在 MyAccess 入口網站中核准或拒絕要求。</span><span class="sxs-lookup"><span data-stu-id="b3604-199">The project manager will receive access requests in their email and approve or deny requests in the MyAccess portal.</span></span> <span data-ttu-id="b3604-200">系統管理員可以設定 access 的條件，以包含到期日或期間（除非 access 已更新），否則將會從團隊中移除使用者或來賓。</span><span class="sxs-lookup"><span data-stu-id="b3604-200">Administrators can configure the conditions of access to include an expiry date or period by when the user or guest will be removed from the team unless access is renewed.</span></span> <span data-ttu-id="b3604-201">系統管理員也可以設定與團隊相關聯的群組，以參與 access 評論。</span><span class="sxs-lookup"><span data-stu-id="b3604-201">Administrators can also set up the groups associated with teams to take part in access reviews.</span></span> <span data-ttu-id="b3604-202">針對[access 評論](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)，群組擁有者會收到定期提醒，以查看小組成員。</span><span class="sxs-lookup"><span data-stu-id="b3604-202">For [access reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview), the group owners will receive regular reminders to review the members of a team.</span></span> <span data-ttu-id="b3604-203">Access 評論包括建議，讓群組擁有者能更輕鬆地完成標準認證程式。</span><span class="sxs-lookup"><span data-stu-id="b3604-203">Access reviews include recommendations, which makes it easier for group owners to go through their regular attestation process.</span></span>

||||
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | <span data-ttu-id="b3604-204">決策點</span><span class="sxs-lookup"><span data-stu-id="b3604-204">Decision points</span></span> | <span data-ttu-id="b3604-205">貴組織需要一致的程式來管理一或多位團隊的成員資格嗎？</span><span class="sxs-lookup"><span data-stu-id="b3604-205">Does your organization require a consistent process for managing membership of one or more teams?</span></span> <br> <span data-ttu-id="b3604-206">貴組織是否需要擁有者或成員本身，以定期向一或多個小組的持續成員資格進行調整？</span><span class="sxs-lookup"><span data-stu-id="b3604-206">Does your organization require owners, or the members themselves, to justify their continued membership of one or more teams on a regular basis?</span></span> <br> <span data-ttu-id="b3604-207">您的組織是否需要核准使用者和來賓要求對資源的存取權，包括團隊、群組、SharePoint 網站和應用程式？</span><span class="sxs-lookup"><span data-stu-id="b3604-207">Does your organization require approval for users and guests to request access to resources including teams, groups, SharePoint sites, and apps?</span></span> |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| <span data-ttu-id="b3604-208">後續步驟？</span><span class="sxs-lookup"><span data-stu-id="b3604-208">Next steps?</span></span> | <span data-ttu-id="b3604-209">針對每個小組或特定小組，為成員資格到期記錄您的組織需求。</span><span class="sxs-lookup"><span data-stu-id="b3604-209">Document your organizations requirements for each team or specific teams for membership expiry.</span></span><br><span data-ttu-id="b3604-210">規劃貴組織可以如何將團隊、群組、SharePoint 網站和應用程式捆綁到 access 套件中。</span><span class="sxs-lookup"><span data-stu-id="b3604-210">Plan how your organization can bundle teams, groups, SharePoint sites, and apps together in access packages.</span></span><br><span data-ttu-id="b3604-211">規劃哪些人（例如要求者的管理員）、專案經理、連線組織的主辦人或貴組織中的安全專員，都必須核准或拒絕存取要求。</span><span class="sxs-lookup"><span data-stu-id="b3604-211">Plan which people, such as the requestor's manager, a project manager, a sponsor for a connected organization or a security officer in your organization will need to approve or deny access requests.</span></span> |

> [!TIP]
> <span data-ttu-id="b3604-212">使用下表來捕獲貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="b3604-212">Use the following table to capture your organization’s requirements.</span></span>

| <span data-ttu-id="b3604-213">功能</span><span class="sxs-lookup"><span data-stu-id="b3604-213">Capability</span></span> | <span data-ttu-id="b3604-214">詳細資料</span><span class="sxs-lookup"><span data-stu-id="b3604-214">Details</span></span> | <span data-ttu-id="b3604-215">需要 Azure AD Premium 授權</span><span class="sxs-lookup"><span data-stu-id="b3604-215">Azure AD Premium license required</span></span> | <span data-ttu-id="b3604-216">決議</span><span class="sxs-lookup"><span data-stu-id="b3604-216">Decision</span></span> |
|:-|:-|:-|:-|
| <span data-ttu-id="b3604-217">Access 評論</span><span class="sxs-lookup"><span data-stu-id="b3604-217">Access reviews</span></span> | <span data-ttu-id="b3604-218">設定存取權審查，以定期 recertify 特定團隊的成員資格</span><span class="sxs-lookup"><span data-stu-id="b3604-218">Setup access reviews to recertify the membership of specific teams at regular interval</span></span> | <span data-ttu-id="b3604-219">又</span><span class="sxs-lookup"><span data-stu-id="b3604-219">P2</span></span> | <span data-ttu-id="b3604-220">TBD</span><span class="sxs-lookup"><span data-stu-id="b3604-220">TBD</span></span> |
| <span data-ttu-id="b3604-221">權利管理</span><span class="sxs-lookup"><span data-stu-id="b3604-221">Entitlement management</span></span> | <span data-ttu-id="b3604-222">設定存取套件，讓使用者與客人要求對團隊進行存取權</span><span class="sxs-lookup"><span data-stu-id="b3604-222">Setup access package to allow users and guests to request access to teams</span></span> | <span data-ttu-id="b3604-223">又</span><span class="sxs-lookup"><span data-stu-id="b3604-223">P2</span></span> | <span data-ttu-id="b3604-224">TBD</span><span class="sxs-lookup"><span data-stu-id="b3604-224">TBD</span></span> |

> [!NOTE]
> <span data-ttu-id="b3604-225">若要協助您預先規劃，請[進一步瞭解他們所需的授權](https://azure.microsoft.com/pricing/details/active-directory/)。</span><span class="sxs-lookup"><span data-stu-id="b3604-225">To help you plan ahead, [learn more about what licenses they require](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

### <a name="additional-information"></a><span data-ttu-id="b3604-226">其他資訊</span><span class="sxs-lookup"><span data-stu-id="b3604-226">Additional information</span></span>

<span data-ttu-id="b3604-227">如需如何實現這些設定的技術指導方針，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b3604-227">For technical guidance on how to implement these settings, see:</span></span>

- [<span data-ttu-id="b3604-228">權利管理</span><span class="sxs-lookup"><span data-stu-id="b3604-228">Entitlement management</span></span>](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)
- [<span data-ttu-id="b3604-229">Access 評論</span><span class="sxs-lookup"><span data-stu-id="b3604-229">Access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a><span data-ttu-id="b3604-230">團隊功能管理</span><span class="sxs-lookup"><span data-stu-id="b3604-230">Teams feature management</span></span>

<span data-ttu-id="b3604-231">小組管理與生命週期管理的另一個重要方面，就是控制您的使用者可以存取哪些功能的功能。</span><span class="sxs-lookup"><span data-stu-id="b3604-231">Another important aspect of governance and lifecycle management for Teams is the ability to control what features your users will have access to.</span></span> <span data-ttu-id="b3604-232">您可以在 Microsoft 365 或 Office 365 組織層級或每位使用者，管理訊息、會議和通話功能。</span><span class="sxs-lookup"><span data-stu-id="b3604-232">You can manage messaging, meeting, and calling features, either at the Microsoft 365 or Office 365 organization level or per-user.</span></span>


|         |         |
|---------|---------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="b3604-234">決策點</span><span class="sxs-lookup"><span data-stu-id="b3604-234">Decision points</span></span>|<ul><li><span data-ttu-id="b3604-235">貴組織是否需要限制您整個租使用者的小組功能？</span><span class="sxs-lookup"><span data-stu-id="b3604-235">Does your organization require limiting Teams features for your entire tenant?</span></span></li><li><span data-ttu-id="b3604-236">貴組織是否需要限制特定使用者的小組功能？</span><span class="sxs-lookup"><span data-stu-id="b3604-236">Does your organization require limiting Teams features for specific users?</span></span></li></ul>|
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/><span data-ttu-id="b3604-238">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b3604-238">Next steps</span></span>|<ul><li><span data-ttu-id="b3604-239">在租使用者層級中記錄您組織限制小組功能的需求。</span><span class="sxs-lookup"><span data-stu-id="b3604-239">Document your organization’s requirements for limiting Teams features at the tenant and user level.</span></span></li><li><span data-ttu-id="b3604-240">規劃將您的特定需求作為小組推出的一部分來實現。</span><span class="sxs-lookup"><span data-stu-id="b3604-240">Plan to implement your specific requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="b3604-241">溝通及發佈您的原則，以告知小組使用者他們可以預期的行為。</span><span class="sxs-lookup"><span data-stu-id="b3604-241">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

### <a name="teams-feature-management-focus-areas"></a><span data-ttu-id="b3604-242">團隊功能管理焦點區域</span><span class="sxs-lookup"><span data-stu-id="b3604-242">Teams feature management focus areas</span></span>

<span data-ttu-id="b3604-243">團隊可透過原則提供精確的功能，以控制訊息、會議、通話及即時事件功能等等。</span><span class="sxs-lookup"><span data-stu-id="b3604-243">Teams provides granular capabilities for controlling messaging, meeting, calling, and live event features and more, via policies.</span></span> <span data-ttu-id="b3604-244">根據貴組織的需求，預設或每位使用者都可以套用不同的原則。</span><span class="sxs-lookup"><span data-stu-id="b3604-244">Different policies can be applied to all users by default or per user as required by your organization.</span></span> 

<span data-ttu-id="b3604-245">如需所有設定的詳細清單，包括如何針對您的組織實施相關的技術指導方針，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="b3604-245">For detailed lists of all settings, including technical guidance on how to implement them for your organization, see the following articles:</span></span>

- [<span data-ttu-id="b3604-246">管理組織的 Microsoft Teams 設定</span><span class="sxs-lookup"><span data-stu-id="b3604-246">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)
- [<span data-ttu-id="b3604-247">在轉換至新 Microsoft Teams 系統管理中心期間管理 Teams</span><span class="sxs-lookup"><span data-stu-id="b3604-247">Manage Teams during the transition to the new Microsoft Teams admin center</span></span>](manage-teams-skypeforbusiness-admin-center.md)
- [<span data-ttu-id="b3604-248">在團隊中管理會議原則</span><span class="sxs-lookup"><span data-stu-id="b3604-248">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="b3604-249">管理小組中的訊息傳遞原則</span><span class="sxs-lookup"><span data-stu-id="b3604-249">Manage messaging policies in Teams</span></span>](messaging-policies-in-teams.md)

<span data-ttu-id="b3604-250">此外，您可以為頻道設定裁決，並向特定使用者提供仲裁者的功能，讓他們能夠控制誰可以建立頻道發佈及回復。</span><span class="sxs-lookup"><span data-stu-id="b3604-250">Additionally, you can set up moderation for a channel and give moderator capabilities to certain users so that they can control who can create channel posts and respond to them.</span></span> <span data-ttu-id="b3604-251">如需詳細資訊，請參閱[在 Microsoft 團隊中設定和管理 [頻道裁決](manage-channel-moderation-in-teams.md)]。</span><span class="sxs-lookup"><span data-stu-id="b3604-251">See [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md) for more information.</span></span>

## <a name="security-and-compliance"></a><span data-ttu-id="b3604-252">安全性與合規性</span><span class="sxs-lookup"><span data-stu-id="b3604-252">Security and compliance</span></span>

<span data-ttu-id="b3604-253">團隊是以 Microsoft 365 和 Office 365 的高級安全性與合規性功能為基礎，並支援審核與報告、合規性內容搜尋、電子探索、法律封存及保留原則。</span><span class="sxs-lookup"><span data-stu-id="b3604-253">Teams is built on the advanced security and compliance capabilities of Microsoft 365 and Office 365 and supports auditing and reporting, compliance content search, e-discovery, Legal Hold, and retention policies.</span></span>

> [!Important]
> <span data-ttu-id="b3604-254">如果您的組織具備合規性與安全性需求，請參閱在[Microsoft 團隊中的安全性與合規性一](security-compliance-overview.md)文中所提供的深入閱讀本主題的內容。</span><span class="sxs-lookup"><span data-stu-id="b3604-254">If your organization has compliance and security requirements, review the in-depth content provided about this topic in the article [Overview of security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b3604-255">相關主題</span><span class="sxs-lookup"><span data-stu-id="b3604-255">Related topics</span></span>

<span data-ttu-id="b3604-256">[Teams 的控管快速入門](teams-adoption-governance-quick-start.md) (英文)</span><span class="sxs-lookup"><span data-stu-id="b3604-256">[Governance quick start for Teams](teams-adoption-governance-quick-start.md)</span></span>

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
