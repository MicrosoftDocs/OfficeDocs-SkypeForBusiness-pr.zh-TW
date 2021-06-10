---
title: 在 Teams - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 在本文中，您將瞭解如何規劃在 Teams 中執行Teams。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ab70daffa91b534f15b032cd0c137efe89abb438
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117811"
---
# <a name="plan-for-governance-in-teams"></a><span data-ttu-id="69f33-103">Teams 中的控管方案</span><span class="sxs-lookup"><span data-stu-id="69f33-103">Plan for governance in Teams</span></span>

<span data-ttu-id="69f33-104">Teams提供一組豐富的工具，以執行貴組織可能需要的任何管理功能。</span><span class="sxs-lookup"><span data-stu-id="69f33-104">Teams provides a rich set of tools to implement any governance capabilities your organization might require.</span></span> <span data-ttu-id="69f33-105">本文引導 IT 專業人員提出正確的問題，以判斷其管理需求，以及如何符合這些需求。</span><span class="sxs-lookup"><span data-stu-id="69f33-105">This article guides IT pros to ask the right questions to determine their requirements for governance, and how to meet them.</span></span> 

> [!Tip] 
> <span data-ttu-id="69f33-106">請觀看下列會話，進一步瞭解如何在 Microsoft Teams 中管理、管理和[生命週期](https://aka.ms/teams-governance)Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="69f33-106">Watch the following session to learn about more about Governance in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)</span></span>

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a><span data-ttu-id="69f33-107">群組和團隊建立、命名、分類和來賓存取</span><span class="sxs-lookup"><span data-stu-id="69f33-107">Group and team creation, naming, classification, and guest access</span></span>

<span data-ttu-id="69f33-108">貴組織可能會要求您對團隊的命名和分類方式、來賓是否可以新增為小組成員，以及誰可以建立團隊，實行嚴格的控制措施。</span><span class="sxs-lookup"><span data-stu-id="69f33-108">Your organization might require that you implement strict controls on how teams are named and classified, whether guests can be added as team members, and who can create teams.</span></span> <span data-ttu-id="69f33-109">您可以使用 Azure AD Azure Active Directory (和敏感度) 來設定這些區域。</span><span class="sxs-lookup"><span data-stu-id="69f33-109">You can configure these areas by using Azure Active Directory (Azure AD) and sensitivity labels.</span></span> 

<br>

|-        |-        |-        |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |<span data-ttu-id="69f33-110">決策點</span><span class="sxs-lookup"><span data-stu-id="69f33-110">Decision points</span></span>|<ul><li><span data-ttu-id="69f33-111">貴組織是否需要團隊的特定命名慣例？</span><span class="sxs-lookup"><span data-stu-id="69f33-111">Does your organization require a specific naming convention for teams?</span></span></li><li><span data-ttu-id="69f33-112">團隊創作者需要將組織特定分類指派給團隊的能力嗎？</span><span class="sxs-lookup"><span data-stu-id="69f33-112">Do team creators need the ability to assign organization-specific classifications to teams?</span></span></li><li><span data-ttu-id="69f33-113">您需要根據每個團隊限制將來賓新增到團隊的能力嗎？</span><span class="sxs-lookup"><span data-stu-id="69f33-113">Do you need to restrict the ability to add guests to teams on a per-team basis?</span></span></li><li><span data-ttu-id="69f33-114">貴組織是否需要限制誰可以建立團隊？</span><span class="sxs-lookup"><span data-stu-id="69f33-114">Does your organization require limiting who can create teams?</span></span></li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|<span data-ttu-id="69f33-115">後續步驟</span><span class="sxs-lookup"><span data-stu-id="69f33-115">Next steps</span></span>|<ul><li><span data-ttu-id="69f33-116">記錄貴組織建立團隊、命名、分類和來賓存取的需求。</span><span class="sxs-lookup"><span data-stu-id="69f33-116">Document your organization’s requirements for team creation, naming, classification, and guest access.</span></span></li><li><span data-ttu-id="69f33-117">規劃將這些要求作為您推行計畫的一Teams一部分。</span><span class="sxs-lookup"><span data-stu-id="69f33-117">Plan to implement these requirements as a part of your Teams rollout.</span></span></li><li><span data-ttu-id="69f33-118">溝通併發布您的Teams，讓使用者瞭解他們預期的行為。</span><span class="sxs-lookup"><span data-stu-id="69f33-118">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!NOTE]
> <span data-ttu-id="69f33-119">若要協助您提前規劃， [請進一步瞭解如何設定這些策略，以及需要哪些授權](/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)。</span><span class="sxs-lookup"><span data-stu-id="69f33-119">To help you plan ahead, [learn more about setting these policies and what licenses they require](/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).</span></span>
> 
> [!NOTE]
> <span data-ttu-id="69f33-120">限制群組和團隊建立可能會降低使用者的生產力，因為許多Microsoft 365 Office 365服務需要建立群組，服務才能運作。</span><span class="sxs-lookup"><span data-stu-id="69f33-120">Limiting group and team creation can slow your users’ productivity, because many Microsoft 365 and Office 365 services require that groups be created for the service to function.</span></span> <span data-ttu-id="69f33-121">若要瞭解詳細資訊，請流覽至 並展開[為什麼控制誰Microsoft 365群組](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)。</span><span class="sxs-lookup"><span data-stu-id="69f33-121">For additional information, navigate to and expand [Why control who creates Microsoft 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).</span></span>


#### <a name="additional-information"></a><span data-ttu-id="69f33-122">其他資訊</span><span class="sxs-lookup"><span data-stu-id="69f33-122">Additional information</span></span>

<span data-ttu-id="69f33-123">在您決定需求之後，您可以使用 Azure AD 控制項來實施需求。</span><span class="sxs-lookup"><span data-stu-id="69f33-123">After you’ve determined your requirements, you can implement them by using Azure AD controls.</span></span> <span data-ttu-id="69f33-124">有關如何執行這些設定的技術指南，請參閱：</span><span class="sxs-lookup"><span data-stu-id="69f33-124">For technical guidance on how to implement these settings, see:</span></span>

- [<span data-ttu-id="69f33-125">Azure Active Directory Cmdlet 來設定群組設定</span><span class="sxs-lookup"><span data-stu-id="69f33-125">Azure Active Directory cmdlets for configuring group settings</span></span>](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [<span data-ttu-id="69f33-126">針對群組中的群組Microsoft 365命名Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="69f33-126">Enforce a naming policy for Microsoft 365 groups in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-naming-policy)

- [<span data-ttu-id="69f33-127">Microsoft 365群組命名政策</span><span class="sxs-lookup"><span data-stu-id="69f33-127">Microsoft 365 Groups naming policy</span></span>](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [<span data-ttu-id="69f33-128">使用敏感度標籤來保護網站Microsoft Teams、Microsoft 365群組SharePoint內容</span><span class="sxs-lookup"><span data-stu-id="69f33-128">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [<span data-ttu-id="69f33-129">群組、團隊和團隊的生命週期結束選項Yammer</span><span class="sxs-lookup"><span data-stu-id="69f33-129">End of lifecycle options for groups, teams, and Yammer</span></span>](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a><span data-ttu-id="69f33-130">群組和小組到期、保留和存檔</span><span class="sxs-lookup"><span data-stu-id="69f33-130">Group and team expiration, retention, and archiving</span></span>

<span data-ttu-id="69f33-131">貴組織可能對於設定到期、保留和存檔團隊和團隊資料 (通道訊息和頻道檔案設定) 。</span><span class="sxs-lookup"><span data-stu-id="69f33-131">Your organization might have additional requirements for setting policies for expiration, retention, and archiving teams and teams data (channel messages and channel files).</span></span> <span data-ttu-id="69f33-132">您可以設定群組到期政策，以自動管理群組的生命週期和保留政策，以視需要保留或刪除資訊，而且您可以將團隊 (設定為唯讀模式) ，以保留不再使用中之團隊的時間點視圖。</span><span class="sxs-lookup"><span data-stu-id="69f33-132">You can configure group expiration policies to automatically manage the lifecycle of the group and retention policies to preserve or delete information as needed, and you can archive teams (set them to read-only mode) to preserve a point-in-time view of a team that’s no longer active.</span></span> <span data-ttu-id="69f33-133">請注意，已存檔的團隊會繼續採用到期原則，除非排除或續約，否則可能會刪除。</span><span class="sxs-lookup"><span data-stu-id="69f33-133">Note that teams that are archived continue to have the expiration policy applied and may be deleted unless excluded or renewed.</span></span>

|-          |-           |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="69f33-135">決策點</span><span class="sxs-lookup"><span data-stu-id="69f33-135">Decision points</span></span>|<ul><li><span data-ttu-id="69f33-136">您的組織是否需要為團隊指定到期日？</span><span class="sxs-lookup"><span data-stu-id="69f33-136">Does your organization require specifying an expiration date for teams?</span></span></li><li><span data-ttu-id="69f33-137">貴組織是否需要將特定的資料保留原則適用于團隊？</span><span class="sxs-lookup"><span data-stu-id="69f33-137">Does your organization require specific data retention policies be applied to teams?</span></span></li><li><span data-ttu-id="69f33-138">貴組織是否預期需要能夠將非使用中團隊存檔，才能將內容保留為唯讀狀態？</span><span class="sxs-lookup"><span data-stu-id="69f33-138">Does your organization expect to require the ability to archive inactive teams to preserve the content in a read-only state?</span></span></li></ul>|
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/><span data-ttu-id="69f33-140">後續步驟</span><span class="sxs-lookup"><span data-stu-id="69f33-140">Next steps</span></span>|<ul><li><span data-ttu-id="69f33-141">記錄貴組織對於小組到期、資料保留和存檔的需求。</span><span class="sxs-lookup"><span data-stu-id="69f33-141">Document your organization’s requirements for team expiration, data retention, and archiving.</span></span></li><li><span data-ttu-id="69f33-142">規劃將這些要求作為您推行計畫的一Teams一部分。</span><span class="sxs-lookup"><span data-stu-id="69f33-142">Plan to implement these requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="69f33-143">溝通併發布您的Teams，讓使用者瞭解他們預期的行為。</span><span class="sxs-lookup"><span data-stu-id="69f33-143">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
> <span data-ttu-id="69f33-144">使用下表來捕獲貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="69f33-144">Use the following table to capture your organization’s requirements.</span></span>

|<span data-ttu-id="69f33-145">功能</span><span class="sxs-lookup"><span data-stu-id="69f33-145">Capability</span></span> |<span data-ttu-id="69f33-146">詳細資料</span><span class="sxs-lookup"><span data-stu-id="69f33-146">Details</span></span> |<span data-ttu-id="69f33-147">需要 Azure AD 進階版授權</span><span class="sxs-lookup"><span data-stu-id="69f33-147">Azure AD Premium license required</span></span> |<span data-ttu-id="69f33-148">決策</span><span class="sxs-lookup"><span data-stu-id="69f33-148">Decision</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="69f33-149">到期政策</span><span class="sxs-lookup"><span data-stu-id="69f33-149">Expiration policy</span></span> |<span data-ttu-id="69f33-150">設定到期Microsoft 365管理群組的生命週期。</span><span class="sxs-lookup"><span data-stu-id="69f33-150">Manage the lifecycle of Microsoft 365 groups by setting an expiration policy.</span></span> |<span data-ttu-id="69f33-151">P1</span><span class="sxs-lookup"><span data-stu-id="69f33-151">P1</span></span> |<span data-ttu-id="69f33-152">待定</span><span class="sxs-lookup"><span data-stu-id="69f33-152">TBD</span></span>|
|<span data-ttu-id="69f33-153">保留原則</span><span class="sxs-lookup"><span data-stu-id="69f33-153">Retention policy</span></span> |<span data-ttu-id="69f33-154">在安全性與合規性中心設定資料保留Teams保留&刪除資料。</span><span class="sxs-lookup"><span data-stu-id="69f33-154">Retain or delete data for a specific time period by setting retention policies for Teams in the Security & compliance center.</span></span> <span data-ttu-id="69f33-155">**注意**：使用這項功能需要授權Microsoft 365或Office 365 企業版 E3 或更新版。</span><span class="sxs-lookup"><span data-stu-id="69f33-155">**Note**: Using this feature requires licensing of Microsoft 365 or Office 365 Enterprise E3 or above.</span></span> |<span data-ttu-id="69f33-156">否</span><span class="sxs-lookup"><span data-stu-id="69f33-156">No</span></span> |<span data-ttu-id="69f33-157">待定</span><span class="sxs-lookup"><span data-stu-id="69f33-157">TBD</span></span> |
|<span data-ttu-id="69f33-158">存檔和還原</span><span class="sxs-lookup"><span data-stu-id="69f33-158">Archive and restore</span></span> |<span data-ttu-id="69f33-159">當團隊不再作用中，但您想要保留該團隊供參考，或日後重新啟用時，請將其存檔。</span><span class="sxs-lookup"><span data-stu-id="69f33-159">Archive a team when it’s no longer active but you want to keep it around for reference or to reactivate in the future.</span></span> |<span data-ttu-id="69f33-160">否</span><span class="sxs-lookup"><span data-stu-id="69f33-160">No</span></span> |<span data-ttu-id="69f33-161">待定</span><span class="sxs-lookup"><span data-stu-id="69f33-161">TBD</span></span> |

> [!Note]
> <span data-ttu-id="69f33-162">群組到期是 Azure AD 進階版功能。</span><span class="sxs-lookup"><span data-stu-id="69f33-162">Group expiration is an Azure AD Premium feature.</span></span> <span data-ttu-id="69f33-163">若要提供這項功能，您的租使用者必須擁有 Azure AD 進階版，且授權給設定設定及受影響群組成員的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="69f33-163">For this feature to be available, your tenant must have a subscription to Azure AD Premium and licenses for the administrator who configures the settings and the members of the affected groups.</span></span>

#### <a name="additional-information"></a><span data-ttu-id="69f33-164">其他資訊</span><span class="sxs-lookup"><span data-stu-id="69f33-164">Additional information</span></span>

<span data-ttu-id="69f33-165">有關如何執行這些設定的技術指南，請參閱：</span><span class="sxs-lookup"><span data-stu-id="69f33-165">For technical guidance on how to implement these settings, see:</span></span>

- <span data-ttu-id="69f33-166">[設定群組Microsoft 365到期](/azure/active-directory/users-groups-roles/groups-lifecycle)。</span><span class="sxs-lookup"><span data-stu-id="69f33-166">[Set up Microsoft 365 groups expiration](/azure/active-directory/users-groups-roles/groups-lifecycle).</span></span>

- <span data-ttu-id="69f33-167">[設定Teams保留原則](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="69f33-167">[Set up Teams retention policies](retention-policies.md).</span></span>

- <span data-ttu-id="69f33-168">[將小組存檔或還原](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。</span><span class="sxs-lookup"><span data-stu-id="69f33-168">[Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>

## <a name="group-and-team-membership-management"></a><span data-ttu-id="69f33-169">群組和小組成員資格管理</span><span class="sxs-lookup"><span data-stu-id="69f33-169">Group and team membership management</span></span>

<span data-ttu-id="69f33-170">對於需要快速上機和登出或使用者和來賓的團隊來說，一致管理專案成員或受限制的群組是必要的。</span><span class="sxs-lookup"><span data-stu-id="69f33-170">Consistently managing members of project based, or restricted groups are necessary for teams that require rapid onboarding and offboarding or users and guests.</span></span> <span data-ttu-id="69f33-171">貴組織可能也需要確認所有目前的成員都有商務理由可以組成團隊。</span><span class="sxs-lookup"><span data-stu-id="69f33-171">Your organization may also need to make sure all current members have the business justification to be in a team.</span></span> <span data-ttu-id="69f33-172">管理成員可能比較困難，因為團隊擁有者可以離開，而使用者通常不會在專案結束時或變更角色時自行離開群組。</span><span class="sxs-lookup"><span data-stu-id="69f33-172">Managing members can be hard because team owners can leave and users don’t usually leave groups on their own accord when a project ends or when they change roles.</span></span> <span data-ttu-id="69f33-173">管理群組成員資格，讓使用者可于需要時存取，但確保群組沒有不當存取風險的最佳方法，是透過兩個區程式：權利管理和存取審查。</span><span class="sxs-lookup"><span data-stu-id="69f33-173">The best way to manage group membership that allows users to get access when needed but ensure the group doesn't have a risk of inappropriate access is through two district processes: entitlement management and access reviews.</span></span>

<span data-ttu-id="69f33-174">[權利管理](/azure/active-directory/governance/entitlement-management-overview) 可讓您委派給專案經理等人員，以收集所有所需的資源，包括團隊成員資格，到單一套件中。</span><span class="sxs-lookup"><span data-stu-id="69f33-174">[Entitlement management](/azure/active-directory/governance/entitlement-management-overview) allows you to delegate to someone, such as a project manager, to collect all the resources that are needed, including teams memberships, into a single package.</span></span> <span data-ttu-id="69f33-175">他們也可以定義誰可以提出要求：租使用者中的使用者或其他已連接組織的使用者。</span><span class="sxs-lookup"><span data-stu-id="69f33-175">They can also define who can make requests: either users in your tenant or from other connected organizations.</span></span> <span data-ttu-id="69f33-176">專案經理會收到電子郵件中的存取要求，並核准或拒絕 MyAccess 入口網站中的要求。</span><span class="sxs-lookup"><span data-stu-id="69f33-176">The project manager will receive access requests in their email and approve or deny requests in the MyAccess portal.</span></span> <span data-ttu-id="69f33-177">系統管理員可以設定存取條件，以包含到期日或期間，除非已續約存取權，否則使用者或來賓會從小組中移除。</span><span class="sxs-lookup"><span data-stu-id="69f33-177">Administrators can configure the conditions of access to include an expiry date or period by when the user or guest will be removed from the team unless access is renewed.</span></span> <span data-ttu-id="69f33-178">系統管理員也可以設定與團隊相關聯的群組，以參與存取審查。</span><span class="sxs-lookup"><span data-stu-id="69f33-178">Administrators can also set up the groups associated with teams to take part in access reviews.</span></span> <span data-ttu-id="69f33-179">針對 [存取審查](/azure/active-directory/governance/access-reviews-overview)，群組擁有者會收到定期提醒，提醒他們檢查小組成員。</span><span class="sxs-lookup"><span data-stu-id="69f33-179">For [access reviews](/azure/active-directory/governance/access-reviews-overview), the group owners will receive regular reminders to review the members of a team.</span></span> <span data-ttu-id="69f33-180">Access 評論包含建議，讓群組擁有者更容易完成其一般證明程式。</span><span class="sxs-lookup"><span data-stu-id="69f33-180">Access reviews include recommendations, which makes it easier for group owners to go through their regular attestation process.</span></span>

|-|-|-|
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | <span data-ttu-id="69f33-181">決策點</span><span class="sxs-lookup"><span data-stu-id="69f33-181">Decision points</span></span> | <span data-ttu-id="69f33-182">貴組織是否需要一致的程式來管理一或多個團隊的成員資格？</span><span class="sxs-lookup"><span data-stu-id="69f33-182">Does your organization require a consistent process for managing membership of one or more teams?</span></span> <br> <span data-ttu-id="69f33-183">貴組織是否要求擁有者或成員本身定期證明他們繼續成為一或多個團隊的成員？</span><span class="sxs-lookup"><span data-stu-id="69f33-183">Does your organization require owners, or the members themselves, to justify their continued membership of one or more teams on a regular basis?</span></span> <br> <span data-ttu-id="69f33-184">貴組織是否需要使用者和來賓核准，要求存取資源，包括團隊、群組、SharePoint網站和應用程式？</span><span class="sxs-lookup"><span data-stu-id="69f33-184">Does your organization require approval for users and guests to request access to resources including teams, groups, SharePoint sites, and apps?</span></span> |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| <span data-ttu-id="69f33-185">下一個步驟？</span><span class="sxs-lookup"><span data-stu-id="69f33-185">Next steps?</span></span> | <span data-ttu-id="69f33-186">記錄每個團隊或特定團隊的成員資格到期組織需求。</span><span class="sxs-lookup"><span data-stu-id="69f33-186">Document your organizations requirements for each team or specific teams for membership expiry.</span></span><br><span data-ttu-id="69f33-187">規劃貴組織如何將小組、群組、SharePoint網站和應用程式組合在存取套件中。</span><span class="sxs-lookup"><span data-stu-id="69f33-187">Plan how your organization can bundle teams, groups, SharePoint sites, and apps together in access packages.</span></span><br><span data-ttu-id="69f33-188">規劃哪些人員需要核准或拒絕存取要求，例如要求者主管、專案經理、連線組織的贊助者或貴組織的安全性專員。</span><span class="sxs-lookup"><span data-stu-id="69f33-188">Plan which people, such as the requestor's manager, a project manager, a sponsor for a connected organization or a security officer in your organization will need to approve or deny access requests.</span></span> |

> [!TIP]
> <span data-ttu-id="69f33-189">使用下表來捕獲貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="69f33-189">Use the following table to capture your organization’s requirements.</span></span>

| <span data-ttu-id="69f33-190">功能</span><span class="sxs-lookup"><span data-stu-id="69f33-190">Capability</span></span> | <span data-ttu-id="69f33-191">詳細資料</span><span class="sxs-lookup"><span data-stu-id="69f33-191">Details</span></span> | <span data-ttu-id="69f33-192">需要 Azure AD 進階版授權</span><span class="sxs-lookup"><span data-stu-id="69f33-192">Azure AD Premium license required</span></span> | <span data-ttu-id="69f33-193">決策</span><span class="sxs-lookup"><span data-stu-id="69f33-193">Decision</span></span> |
|:-|:-|:-|:-|
| <span data-ttu-id="69f33-194">Access 評論</span><span class="sxs-lookup"><span data-stu-id="69f33-194">Access reviews</span></span> | <span data-ttu-id="69f33-195">設定存取審查以定期重新認證特定團隊的成員資格</span><span class="sxs-lookup"><span data-stu-id="69f33-195">Setup access reviews to recertify the membership of specific teams at regular interval</span></span> | <span data-ttu-id="69f33-196">P2</span><span class="sxs-lookup"><span data-stu-id="69f33-196">P2</span></span> | <span data-ttu-id="69f33-197">待定</span><span class="sxs-lookup"><span data-stu-id="69f33-197">TBD</span></span> |
| <span data-ttu-id="69f33-198">權利管理</span><span class="sxs-lookup"><span data-stu-id="69f33-198">Entitlement management</span></span> | <span data-ttu-id="69f33-199">設定存取套件，讓使用者和來賓要求存取團隊</span><span class="sxs-lookup"><span data-stu-id="69f33-199">Setup access package to allow users and guests to request access to teams</span></span> | <span data-ttu-id="69f33-200">P2</span><span class="sxs-lookup"><span data-stu-id="69f33-200">P2</span></span> | <span data-ttu-id="69f33-201">待定</span><span class="sxs-lookup"><span data-stu-id="69f33-201">TBD</span></span> |

> [!NOTE]
> <span data-ttu-id="69f33-202">若要協助您提前規劃， [請深入瞭解他們需要哪些授權](https://azure.microsoft.com/pricing/details/active-directory/)。</span><span class="sxs-lookup"><span data-stu-id="69f33-202">To help you plan ahead, [learn more about what licenses they require](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

### <a name="additional-information"></a><span data-ttu-id="69f33-203">其他資訊</span><span class="sxs-lookup"><span data-stu-id="69f33-203">Additional information</span></span>

<span data-ttu-id="69f33-204">有關如何執行這些設定的技術指南，請參閱：</span><span class="sxs-lookup"><span data-stu-id="69f33-204">For technical guidance on how to implement these settings, see:</span></span>

- [<span data-ttu-id="69f33-205">權利管理</span><span class="sxs-lookup"><span data-stu-id="69f33-205">Entitlement management</span></span>](/azure/active-directory/governance/entitlement-management-overview)
- [<span data-ttu-id="69f33-206">Access 評論</span><span class="sxs-lookup"><span data-stu-id="69f33-206">Access reviews</span></span>](/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a><span data-ttu-id="69f33-207">Teams功能管理</span><span class="sxs-lookup"><span data-stu-id="69f33-207">Teams feature management</span></span>

<span data-ttu-id="69f33-208">系統管理與生命週期管理的另一Teams是控制使用者可存取的功能的能力。</span><span class="sxs-lookup"><span data-stu-id="69f33-208">Another important aspect of governance and lifecycle management for Teams is the ability to control what features your users will have access to.</span></span> <span data-ttu-id="69f33-209">您可以管理訊息、會議及通話功能，Microsoft 365組織層級Office 365或每個使用者。</span><span class="sxs-lookup"><span data-stu-id="69f33-209">You can manage messaging, meeting, and calling features, either at the Microsoft 365 or Office 365 organization level or per-user.</span></span>


|-        |-        |
|---------|---------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="69f33-211">決策點</span><span class="sxs-lookup"><span data-stu-id="69f33-211">Decision points</span></span>|<ul><li><span data-ttu-id="69f33-212">貴組織是否需要限制Teams租使用者的功能？</span><span class="sxs-lookup"><span data-stu-id="69f33-212">Does your organization require limiting Teams features for your entire tenant?</span></span></li><li><span data-ttu-id="69f33-213">貴組織是否需要限制Teams使用者的功能？</span><span class="sxs-lookup"><span data-stu-id="69f33-213">Does your organization require limiting Teams features for specific users?</span></span></li></ul>|
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/><span data-ttu-id="69f33-215">後續步驟</span><span class="sxs-lookup"><span data-stu-id="69f33-215">Next steps</span></span>|<ul><li><span data-ttu-id="69f33-216">記錄貴組織限制租使用者Teams使用者層級的功能需求。</span><span class="sxs-lookup"><span data-stu-id="69f33-216">Document your organization’s requirements for limiting Teams features at the tenant and user level.</span></span></li><li><span data-ttu-id="69f33-217">規劃將您的特定需求作為您推行計畫的一Teams一部分。</span><span class="sxs-lookup"><span data-stu-id="69f33-217">Plan to implement your specific requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="69f33-218">溝通併發布您的Teams告知使用者他們預期的行為。</span><span class="sxs-lookup"><span data-stu-id="69f33-218">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

### <a name="teams-feature-management-focus-areas"></a><span data-ttu-id="69f33-219">Teams功能管理焦點區域</span><span class="sxs-lookup"><span data-stu-id="69f33-219">Teams feature management focus areas</span></span>

<span data-ttu-id="69f33-220">Teams提供精細的功能，可透過政策控制訊息、會議、通話和即時活動功能等。</span><span class="sxs-lookup"><span data-stu-id="69f33-220">Teams provides granular capabilities for controlling messaging, meeting, calling, and live event features and more, via policies.</span></span> <span data-ttu-id="69f33-221">根據預設，不同的原則可以適用于所有使用者，也可以根據貴組織的要求，將每個使用者都適用。</span><span class="sxs-lookup"><span data-stu-id="69f33-221">Different policies can be applied to all users by default or per user as required by your organization.</span></span> 

<span data-ttu-id="69f33-222">有關所有設定的詳細清單，包括如何為貴組織執行這些設定的技術指南，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="69f33-222">For detailed lists of all settings, including technical guidance on how to implement them for your organization, see the following articles:</span></span>

- [<span data-ttu-id="69f33-223">管理組織的 Microsoft Teams 設定</span><span class="sxs-lookup"><span data-stu-id="69f33-223">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)
- [<span data-ttu-id="69f33-224">在轉換至新 Microsoft Teams 系統管理中心期間管理 Teams</span><span class="sxs-lookup"><span data-stu-id="69f33-224">Manage Teams during the transition to the new Microsoft Teams admin center</span></span>](manage-teams-skypeforbusiness-admin-center.md)
- [<span data-ttu-id="69f33-225">Microsoft Teams 中的私人頻道</span><span class="sxs-lookup"><span data-stu-id="69f33-225">Private channels in Microsoft Teams</span></span>](private-channels.md)
- [<span data-ttu-id="69f33-226">管理 Teams 中的會議原則</span><span class="sxs-lookup"><span data-stu-id="69f33-226">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="69f33-227">在 Teams 中管理訊息原則</span><span class="sxs-lookup"><span data-stu-id="69f33-227">Manage messaging policies in Teams</span></span>](messaging-policies-in-teams.md)
- [<span data-ttu-id="69f33-228">在系統管理中心管理Microsoft Teams應用程式</span><span class="sxs-lookup"><span data-stu-id="69f33-228">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)

<span data-ttu-id="69f33-229">此外，您可以設定頻道的仲裁，並給予特定使用者仲裁者功能，讓他們可以控制誰可以建立頻道文章並回復他們。</span><span class="sxs-lookup"><span data-stu-id="69f33-229">Additionally, you can set up moderation for a channel and give moderator capabilities to certain users so that they can control who can create channel posts and respond to them.</span></span> <span data-ttu-id="69f33-230">詳細資訊[，](manage-channel-moderation-in-teams.md)請參閱在 Microsoft Teams 中設定及管理頻道模式。</span><span class="sxs-lookup"><span data-stu-id="69f33-230">See [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md) for more information.</span></span>

## <a name="security-and-compliance"></a><span data-ttu-id="69f33-231">安全性與合規性</span><span class="sxs-lookup"><span data-stu-id="69f33-231">Security and compliance</span></span>

<span data-ttu-id="69f33-232">Teams以 Microsoft 365 和 Office 365 進位安全性和合規性功能為根據，支援稽核與報告、合規性內容搜尋、電子探索、法律保留和保留政策。</span><span class="sxs-lookup"><span data-stu-id="69f33-232">Teams is built on the advanced security and compliance capabilities of Microsoft 365 and Office 365 and supports auditing and reporting, compliance content search, e-discovery, Legal Hold, and retention policies.</span></span>

> [!Important]
> <span data-ttu-id="69f33-233">如果貴組織有合規性和安全性需求，請于本文的安全性與合規性概觀一文中，查看[本主題](security-compliance-overview.md)提供Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="69f33-233">If your organization has compliance and security requirements, review the in-depth content provided about this topic in the article [Overview of security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="69f33-234">相關主題</span><span class="sxs-lookup"><span data-stu-id="69f33-234">Related topics</span></span>

[<span data-ttu-id="69f33-235">Teams 的控管快速入門</span><span class="sxs-lookup"><span data-stu-id="69f33-235">Governance quick start for Teams</span></span>](teams-adoption-governance-quick-start.md)

[<span data-ttu-id="69f33-236">Microsoft 365安全性與合規性的授權&指南</span><span class="sxs-lookup"><span data-stu-id="69f33-236">Microsoft 365 licensing guidance for security & compliance</span></span>](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->