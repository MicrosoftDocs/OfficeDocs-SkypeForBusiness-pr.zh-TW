---
title: 在小組中規劃管理-Microsoft 團隊
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/10/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 瞭解如何規劃在團隊中實施管理功能。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7fd782df443504a20a6010f07ac15b9078e570a7
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780202"
---
# <a name="plan-for-governance-in-teams"></a><span data-ttu-id="2b5a6-103">Teams 中的控管方案</span><span class="sxs-lookup"><span data-stu-id="2b5a6-103">Plan for governance in Teams</span></span>

<span data-ttu-id="2b5a6-104">團隊會提供一組豐富的工具來實施貴組織可能需要的任何管轄功能。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-104">Teams provides a rich set of tools to implement any governance capabilities your organization might require.</span></span> <span data-ttu-id="2b5a6-105">本文將指導 IT 專業人員提出正確的問題，以決定其管理需求，以及如何滿足他們的需求。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-105">This article guides IT pros to ask the right questions to determine their requirements for governance, and how to meet them.</span></span> 

> [!Tip] 
> <span data-ttu-id="2b5a6-106">請觀看下列會話，深入瞭解 Microsoft 團隊中的管轄：[管理、管理與生命週期](https://aka.ms/teams-governance)</span><span class="sxs-lookup"><span data-stu-id="2b5a6-106">Watch the following session to learn about more about Governance in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)</span></span>

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a><span data-ttu-id="2b5a6-107">群組和小組建立、命名、分類和來賓存取</span><span class="sxs-lookup"><span data-stu-id="2b5a6-107">Group and team creation, naming, classification, and guest access</span></span>

<span data-ttu-id="2b5a6-108">您的組織可能會要求您在小組命名及分類的方式上執行嚴格的控制，您可以將來賓新增為小組成員，以及誰可以建立團隊。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-108">Your organization might require that you implement strict controls on how teams are named and classified, whether guests can be added as team members, and who can create teams.</span></span> <span data-ttu-id="2b5a6-109">您可以使用 Azure Active Directory （Azure AD）來設定這些區域中的每一個。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-109">You can configure each of these areas by using Azure Active Directory (Azure AD).</span></span> 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |<span data-ttu-id="2b5a6-110">決策點</span><span class="sxs-lookup"><span data-stu-id="2b5a6-110">Decision points</span></span>|<ul><li><span data-ttu-id="2b5a6-111">貴組織是否需要適用于團隊的特定命名慣例？</span><span class="sxs-lookup"><span data-stu-id="2b5a6-111">Does your organization require a specific naming convention for teams?</span></span></li><li><span data-ttu-id="2b5a6-112">小組創作者是否需要能夠將組織特定分類指派給團隊？</span><span class="sxs-lookup"><span data-stu-id="2b5a6-112">Do team creators need the ability to assign organization-specific classifications to teams?</span></span></li><li><span data-ttu-id="2b5a6-113">您是否需要限制將來賓新增到小組的人員的能力？</span><span class="sxs-lookup"><span data-stu-id="2b5a6-113">Do you need to restrict the ability to add guests to teams on a per-team basis?</span></span></li><li><span data-ttu-id="2b5a6-114">貴組織是否需要限制誰可以建立團隊？</span><span class="sxs-lookup"><span data-stu-id="2b5a6-114">Does your organization require limiting who can create teams?</span></span></li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|<span data-ttu-id="2b5a6-115">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2b5a6-115">Next steps</span></span>|<ul><li><span data-ttu-id="2b5a6-116">記錄貴組織建立、命名、分類和來賓存取的需求。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-116">Document your organization’s requirements for team creation, naming, classification, and guest access.</span></span></li><li><span data-ttu-id="2b5a6-117">規劃將這些需求作為小組推出的一部分來執行。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-117">Plan to implement these requirements as a part of your Teams rollout.</span></span></li><li><span data-ttu-id="2b5a6-118">溝通及發佈您的原則，以告知小組使用者他們可以預期的行為。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-118">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
> <span data-ttu-id="2b5a6-119">使用下表來捕獲貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-119">Use the following table to capture your organization’s requirements.</span></span>

|<span data-ttu-id="2b5a6-120">功能</span><span class="sxs-lookup"><span data-stu-id="2b5a6-120">Capability</span></span> |<span data-ttu-id="2b5a6-121">詳細資料</span><span class="sxs-lookup"><span data-stu-id="2b5a6-121">Details</span></span> |<span data-ttu-id="2b5a6-122">Azure AD Premium</span><span class="sxs-lookup"><span data-stu-id="2b5a6-122">Azure AD Premium</span></span> <br> <span data-ttu-id="2b5a6-123">需要授權</span><span class="sxs-lookup"><span data-stu-id="2b5a6-123">license required</span></span> |<span data-ttu-id="2b5a6-124">決議</span><span class="sxs-lookup"><span data-stu-id="2b5a6-124">Decision</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="2b5a6-125">團隊命名原則</span><span class="sxs-lookup"><span data-stu-id="2b5a6-125">Team naming policy</span></span> | <span data-ttu-id="2b5a6-126">使用以前置詞為基礎的自訂封鎖字。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-126">Use Prefix-Suffix–based, Custom Blocked Words.</span></span> |<span data-ttu-id="2b5a6-127">P1</span><span class="sxs-lookup"><span data-stu-id="2b5a6-127">P1</span></span> |<span data-ttu-id="2b5a6-128">TBD</span><span class="sxs-lookup"><span data-stu-id="2b5a6-128">TBD</span></span> |
|<span data-ttu-id="2b5a6-129">小組分類</span><span class="sxs-lookup"><span data-stu-id="2b5a6-129">Team classification</span></span> |<span data-ttu-id="2b5a6-130">指派分類給小組。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-130">Assign classifications to teams.</span></span> |<span data-ttu-id="2b5a6-131">P1</span><span class="sxs-lookup"><span data-stu-id="2b5a6-131">P1</span></span> |<span data-ttu-id="2b5a6-132">TBD</span><span class="sxs-lookup"><span data-stu-id="2b5a6-132">TBD</span></span> |
|<span data-ttu-id="2b5a6-133">小組來賓存取</span><span class="sxs-lookup"><span data-stu-id="2b5a6-133">Team guest access</span></span> |<span data-ttu-id="2b5a6-134">允許或禁止將來賓新增至小組。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-134">Allow or prevent guests from being added to teams.</span></span> |<span data-ttu-id="2b5a6-135">否</span><span class="sxs-lookup"><span data-stu-id="2b5a6-135">No</span></span> |<span data-ttu-id="2b5a6-136">TBD</span><span class="sxs-lookup"><span data-stu-id="2b5a6-136">TBD</span></span> |
|<span data-ttu-id="2b5a6-137">小組建立</span><span class="sxs-lookup"><span data-stu-id="2b5a6-137">Team creation</span></span> |<span data-ttu-id="2b5a6-138">將小組建立限制為管理員。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-138">Limit team creation to administrators.</span></span> |<span data-ttu-id="2b5a6-139">否</span><span class="sxs-lookup"><span data-stu-id="2b5a6-139">No</span></span> |<span data-ttu-id="2b5a6-140">TBD</span><span class="sxs-lookup"><span data-stu-id="2b5a6-140">TBD</span></span>|
|<span data-ttu-id="2b5a6-141">小組建立</span><span class="sxs-lookup"><span data-stu-id="2b5a6-141">Team creation</span></span> |<span data-ttu-id="2b5a6-142">將小組建立限制為安全群組成員。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-142">Limit team creation to security group members.</span></span> |<span data-ttu-id="2b5a6-143">P1</span><span class="sxs-lookup"><span data-stu-id="2b5a6-143">P1</span></span> |<span data-ttu-id="2b5a6-144">TBD</span><span class="sxs-lookup"><span data-stu-id="2b5a6-144">TBD</span></span>|

> [!NOTE]
> <span data-ttu-id="2b5a6-145">若要協助您預先規劃，請[進一步瞭解如何設定這些原則以及他們所需的授權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-145">To help you plan ahead, [learn more about setting these policies and what licenses they require](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).</span></span>
> 
> [!NOTE]
> <span data-ttu-id="2b5a6-146">限制群組和小組建立會降低使用者的生產力，因為許多 Office 365 服務都需要建立群組才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-146">Limiting group and team creation can slow your users’ productivity, because many Office 365 services require that groups be created for the service to function.</span></span> <span data-ttu-id="2b5a6-147">如需其他資訊，請流覽並展開[控制誰能建立 Microsoft 365 群組的原因](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-147">For additional information, navigate to and expand [Why control who creates Microsoft 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).</span></span>


#### <a name="additional-information"></a><span data-ttu-id="2b5a6-148">其他資訊</span><span class="sxs-lookup"><span data-stu-id="2b5a6-148">Additional information</span></span>

<span data-ttu-id="2b5a6-149">在您決定需求之後，您可以使用 Azure AD 控制項來實現它們。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-149">After you’ve determined your requirements, you can implement them by using Azure AD controls.</span></span> <span data-ttu-id="2b5a6-150">如需如何實現這些設定的技術指導方針，請參閱：</span><span class="sxs-lookup"><span data-stu-id="2b5a6-150">For technical guidance on how to implement these settings, see:</span></span>

- <span data-ttu-id="2b5a6-151">[Azure Active Directory Cmdlet，用於設定群組設定](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-151">[Azure Active Directory cmdlets for configuring group settings](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets).</span></span>

- <span data-ttu-id="2b5a6-152">[在 Azure Active Directory 中強制執行 Microsoft 365 群組的命名原則](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-152">[Enforce a naming policy for Microsoft 365 groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).</span></span>

- <span data-ttu-id="2b5a6-153">[Microsoft 365 群組命名原則](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-153">[Microsoft 365 Groups naming policy](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>


## <a name="group-and-team-expiration-retention-and-archiving"></a><span data-ttu-id="2b5a6-154">群組和小組到期、保留及封存</span><span class="sxs-lookup"><span data-stu-id="2b5a6-154">Group and team expiration, retention, and archiving</span></span>

<span data-ttu-id="2b5a6-155">您的組織可能對設定到期、保留及封存團隊與團隊資料（頻道訊息和頻道檔案）的需求有額外需求。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-155">Your organization might have additional requirements for setting policies for expiration, retention, and archiving teams and teams data (channel messages and channel files).</span></span> <span data-ttu-id="2b5a6-156">您可以設定群組過期原則，以自動管理群組和保留原則的生命週期，以根據需要保留或刪除資訊，而且您可以將團隊封存（將其設為唯讀模式），以保留不在使用中的小組的時間點視圖。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-156">You can configure group expiration policies to automatically manage the lifecycle of the group and retention policies to preserve or delete information as needed, and you can archive teams (set them to read-only mode) to preserve a point-in-time view of a team that’s no longer active.</span></span>

|           |            |
|-----------|------------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="2b5a6-158">決策點</span><span class="sxs-lookup"><span data-stu-id="2b5a6-158">Decision points</span></span>|<ul><li><span data-ttu-id="2b5a6-159">貴組織是否需要指定團隊的到期日？</span><span class="sxs-lookup"><span data-stu-id="2b5a6-159">Does your organization require specifying an expiration date for teams?</span></span></li><li><span data-ttu-id="2b5a6-160">貴組織是否需要將特定的資料保留原則套用至團隊？</span><span class="sxs-lookup"><span data-stu-id="2b5a6-160">Does your organization require specific data retention policies be applied to teams?</span></span></li><li><span data-ttu-id="2b5a6-161">貴組織是否希望能夠封存不活躍的小組，以保持內容處於唯讀狀態？</span><span class="sxs-lookup"><span data-stu-id="2b5a6-161">Does your organization expect to require the ability to archive inactive teams to preserve the content in a read-only state?</span></span></li></ul>|
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/><span data-ttu-id="2b5a6-163">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2b5a6-163">Next steps</span></span>|<ul><li><span data-ttu-id="2b5a6-164">記錄貴組織的小組到期、資料保留及封存需求。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-164">Document your organization’s requirements for team expiration, data retention, and archiving.</span></span></li><li><span data-ttu-id="2b5a6-165">規劃將這些需求作為您團隊推出的一部分來執行。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-165">Plan to implement these requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="2b5a6-166">溝通及發佈您的原則，以告知小組使用者他們可以預期的行為。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-166">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
> <span data-ttu-id="2b5a6-167">使用下表來捕獲貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-167">Use the following table to capture your organization’s requirements.</span></span>

|<span data-ttu-id="2b5a6-168">功能</span><span class="sxs-lookup"><span data-stu-id="2b5a6-168">Capability</span></span> |<span data-ttu-id="2b5a6-169">詳細資料</span><span class="sxs-lookup"><span data-stu-id="2b5a6-169">Details</span></span> |<span data-ttu-id="2b5a6-170">需要 Azure AD Premium 授權</span><span class="sxs-lookup"><span data-stu-id="2b5a6-170">Azure AD Premium license required</span></span> |<span data-ttu-id="2b5a6-171">決議</span><span class="sxs-lookup"><span data-stu-id="2b5a6-171">Decision</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="2b5a6-172">過期原則</span><span class="sxs-lookup"><span data-stu-id="2b5a6-172">Expiration policy</span></span> |<span data-ttu-id="2b5a6-173">設定過期原則，管理 Microsoft 365 群組的週期。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-173">Manage the lifecycle of Microsoft 365 groups by setting an expiration policy.</span></span> |<span data-ttu-id="2b5a6-174">P1</span><span class="sxs-lookup"><span data-stu-id="2b5a6-174">P1</span></span> |<span data-ttu-id="2b5a6-175">TBD</span><span class="sxs-lookup"><span data-stu-id="2b5a6-175">TBD</span></span>|
|<span data-ttu-id="2b5a6-176">保留原則</span><span class="sxs-lookup"><span data-stu-id="2b5a6-176">Retention policy</span></span> |<span data-ttu-id="2b5a6-177">在安全性 & 合規性中心設定小組的保留原則，以保留或刪除特定時段內的資料。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-177">Retain or delete data for a specific time period by setting retention policies for Teams in the Security & compliance center.</span></span> <span data-ttu-id="2b5a6-178">**注意**：使用這項功能需要授權 Office 365 Enterprise E3 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-178">**Note**: Using this feature requires licensing of Office 365 Enterprise E3 or above.</span></span> |<span data-ttu-id="2b5a6-179">否</span><span class="sxs-lookup"><span data-stu-id="2b5a6-179">No</span></span> |<span data-ttu-id="2b5a6-180">TBD</span><span class="sxs-lookup"><span data-stu-id="2b5a6-180">TBD</span></span> |
|<span data-ttu-id="2b5a6-181">封存和還原</span><span class="sxs-lookup"><span data-stu-id="2b5a6-181">Archive and restore</span></span> |<span data-ttu-id="2b5a6-182">當小組已不在使用中，但您想要保留以供參考或在將來重新啟用時，請封存團隊。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-182">Archive a team when it’s no longer active but you want to keep it around for reference or to reactivate in the future.</span></span> |<span data-ttu-id="2b5a6-183">否</span><span class="sxs-lookup"><span data-stu-id="2b5a6-183">No</span></span> |<span data-ttu-id="2b5a6-184">TBD</span><span class="sxs-lookup"><span data-stu-id="2b5a6-184">TBD</span></span> |

> [!Note]
> <span data-ttu-id="2b5a6-185">[群組到期] 是 Azure AD Premium 功能。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-185">Group expiration is an Azure AD Premium feature.</span></span> <span data-ttu-id="2b5a6-186">若要使用此功能，您的租使用者必須具備 Azure AD Premium 的訂閱，以及設定受影響群組之成員之系統管理員的授權。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-186">For this feature to be available, your tenant must have a subscription to Azure AD Premium and licenses for the administrator who configures the settings and the members of the affected groups.</span></span>

#### <a name="additional-information"></a><span data-ttu-id="2b5a6-187">其他資訊</span><span class="sxs-lookup"><span data-stu-id="2b5a6-187">Additional information</span></span>

<span data-ttu-id="2b5a6-188">如需如何實現這些設定的技術指導方針，請參閱：</span><span class="sxs-lookup"><span data-stu-id="2b5a6-188">For technical guidance on how to implement these settings, see:</span></span>

- <span data-ttu-id="2b5a6-189">[設定 Microsoft 365 群組到期](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)日。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-189">[Set up Microsoft 365 groups expiration](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).</span></span>

- <span data-ttu-id="2b5a6-190">[設定小組保留原則](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-190">[Set up Teams retention policies](retention-policies.md).</span></span>

- <span data-ttu-id="2b5a6-191">封存[或還原團隊](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-191">[Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>


## <a name="teams-feature-management"></a><span data-ttu-id="2b5a6-192">團隊功能管理</span><span class="sxs-lookup"><span data-stu-id="2b5a6-192">Teams feature management</span></span>

<span data-ttu-id="2b5a6-193">小組管理與生命週期管理的另一個重要方面，就是控制您的使用者可以存取哪些功能的功能。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-193">Another important aspect of governance and lifecycle management for Teams is the ability to control what features your users will have access to.</span></span> <span data-ttu-id="2b5a6-194">您可以在 Office 365 的組織層級或每位使用者，管理訊息、會議和通話功能。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-194">You can manage messaging, meeting, and calling features, either at the Office 365 organization level or per-user.</span></span> 


|         |         |
|---------|---------|
| ![描繪決策點的圖示](media/audio_conferencing_image7.png) <br/><span data-ttu-id="2b5a6-196">決策點</span><span class="sxs-lookup"><span data-stu-id="2b5a6-196">Decision points</span></span>|<ul><li><span data-ttu-id="2b5a6-197">貴組織是否需要限制您整個租使用者的小組功能？</span><span class="sxs-lookup"><span data-stu-id="2b5a6-197">Does your organization require limiting Teams features for your entire tenant?</span></span></li><li><span data-ttu-id="2b5a6-198">貴組織是否需要限制特定使用者的小組功能？</span><span class="sxs-lookup"><span data-stu-id="2b5a6-198">Does your organization require limiting Teams features for specific users?</span></span></li></ul>|
| ![描繪後續步驟的圖示](media/audio_conferencing_image9.png)<br/><span data-ttu-id="2b5a6-200">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2b5a6-200">Next steps</span></span>|<ul><li><span data-ttu-id="2b5a6-201">在租使用者層級中記錄您組織限制小組功能的需求。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-201">Document your organization’s requirements for limiting Teams features at the tenant and user level.</span></span></li><li><span data-ttu-id="2b5a6-202">規劃將您的特定需求作為小組推出的一部分來實現。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-202">Plan to implement your specific requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="2b5a6-203">溝通及發佈您的原則，以告知小組使用者他們可以預期的行為。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-203">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

### <a name="teams-feature-management-focus-areas"></a><span data-ttu-id="2b5a6-204">團隊功能管理焦點區域</span><span class="sxs-lookup"><span data-stu-id="2b5a6-204">Teams feature management focus areas</span></span>

<span data-ttu-id="2b5a6-205">團隊可透過原則提供精確的功能，以控制訊息、會議、通話及即時事件功能等等。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-205">Teams provides granular capabilities for controlling messaging, meeting, calling, and live event features and more, via policies.</span></span> <span data-ttu-id="2b5a6-206">根據貴組織的需求，預設或每位使用者都可以套用不同的原則。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-206">Different policies can be applied to all users by default or per user as required by your organization.</span></span> 

<span data-ttu-id="2b5a6-207">如需所有設定的詳細清單，包括如何針對您的組織實施相關的技術指導方針，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="2b5a6-207">For detailed lists of all settings, including technical guidance on how to implement them for your organization, see the following articles:</span></span>

- [<span data-ttu-id="2b5a6-208">管理組織的 Microsoft Teams 設定</span><span class="sxs-lookup"><span data-stu-id="2b5a6-208">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)
- [<span data-ttu-id="2b5a6-209">在轉換至新 Microsoft Teams 系統管理中心期間管理 Teams</span><span class="sxs-lookup"><span data-stu-id="2b5a6-209">Manage Teams during the transition to the new Microsoft Teams admin center</span></span>](manage-teams-skypeforbusiness-admin-center.md)
- [<span data-ttu-id="2b5a6-210">在團隊中管理會議原則</span><span class="sxs-lookup"><span data-stu-id="2b5a6-210">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="2b5a6-211">管理小組中的訊息傳遞原則</span><span class="sxs-lookup"><span data-stu-id="2b5a6-211">Manage messaging policies in Teams</span></span>](messaging-policies-in-teams.md)

<span data-ttu-id="2b5a6-212">此外，您可以為頻道設定裁決，並向特定使用者提供仲裁者的功能，讓他們能夠控制誰可以建立頻道發佈及回復。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-212">Additionally, you can set up moderation for a channel and give moderator capabilities to certain users so that they can control who can create channel posts and respond to them.</span></span> <span data-ttu-id="2b5a6-213">如需詳細資訊，請參閱[在 Microsoft 團隊中設定和管理 [頻道裁決](manage-channel-moderation-in-teams.md)]。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-213">See [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md) for more information.</span></span>

## <a name="security-and-compliance"></a><span data-ttu-id="2b5a6-214">安全性與合規性</span><span class="sxs-lookup"><span data-stu-id="2b5a6-214">Security and compliance</span></span>

<span data-ttu-id="2b5a6-215">團隊是以 Office 365 的高級安全性與合規性功能為基礎，並支援審計與報告、合規性內容搜尋、電子探索、法律封存及保留原則。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-215">Teams is built on the advanced security and compliance capabilities of Office 365 and supports auditing and reporting, compliance content search, e-discovery, Legal Hold, and retention policies.</span></span> 

> [!Important]
> <span data-ttu-id="2b5a6-216">如果您的組織具備合規性與安全性需求，請參閱在[Microsoft 團隊中的安全性與合規性一](security-compliance-overview.md)文中所提供的深入閱讀本主題的內容。</span><span class="sxs-lookup"><span data-stu-id="2b5a6-216">If your organization has compliance and security requirements, review the in-depth content provided about this topic in the article [Overview of security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2b5a6-217">相關主題</span><span class="sxs-lookup"><span data-stu-id="2b5a6-217">Related topics</span></span>

<span data-ttu-id="2b5a6-218">[Teams 的控管快速入門](teams-adoption-governance-quick-start.md) (英文)</span><span class="sxs-lookup"><span data-stu-id="2b5a6-218">[Governance quick start for Teams](teams-adoption-governance-quick-start.md)</span></span>

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
