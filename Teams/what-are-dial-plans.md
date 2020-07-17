---
title: 什麼是撥號對應表？
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.dialplans.overview
- Calling Plans
description: '瞭解您可以在小組中使用的撥號方案類型（PSTN 呼叫撥號方案），以及如何為您的組織選擇一個電話。  '
ms.openlocfilehash: ddd2de412d0ddd00135f9b095eb2d14c8fc4c922
ms.sourcegitcommit: 91f6db3cdb4f2b7761d2b21f0f4eef405edacd5f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2020
ms.locfileid: "45153575"
---
# <a name="what-are-dial-plans"></a><span data-ttu-id="e6277-103">什麼是撥號對應表？</span><span class="sxs-lookup"><span data-stu-id="e6277-103">What are dial plans?</span></span>

<span data-ttu-id="e6277-104">撥號方案是一組命名的正常化規則，可將個別使用者撥打的電話號碼轉換成替代格式（通常是 E. 164），以進行呼叫授權及呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="e6277-104">A dial plan is a named set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="e6277-105">撥號計畫由一或多個正常化規則所組成，這些規則定義以不同格式表示的電話號碼如何轉換為替代格式。</span><span class="sxs-lookup"><span data-stu-id="e6277-105">A dial plan consists of one or more normalization rules that define how phone numbers expressed in various formats are translated to an alternate format.</span></span> <span data-ttu-id="e6277-106">在不同的撥號方案中，相同的撥號字串可能會以不同的方式加以轉譯，因此，根據指派給特定使用者的撥號方案而定，相同的撥入號碼可能會以不同的方式進行轉換和路由。</span><span class="sxs-lookup"><span data-stu-id="e6277-106">The same dial string may be interpreted and translated differently in different dial plans, so depending on which dial plan is assigned to a given user, the same dialed number may be translated and routed differently.</span></span> <span data-ttu-id="e6277-107">最多可以有1000個租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="e6277-107">There can be a maximum of 1,000 tenant dial plans.</span></span>

<span data-ttu-id="e6277-108">請參閱[建立及管理撥號計畫](create-and-manage-dial-plans.md)，以建立和管理租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="e6277-108">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage tenant dial plans.</span></span>

## <a name="tenant-dial-plan-scope"></a><span data-ttu-id="e6277-109">租使用者撥號計畫範圍</span><span class="sxs-lookup"><span data-stu-id="e6277-109">Tenant dial plan scope</span></span>

<span data-ttu-id="e6277-110">撥號計畫的範圍決定您可以套用撥號方案的階層等級。</span><span class="sxs-lookup"><span data-stu-id="e6277-110">A dial plan's scope determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="e6277-111">用戶端透過提供設定來取得適當的撥號方案，這些設定是在使用者登入小組時自動提供的。</span><span class="sxs-lookup"><span data-stu-id="e6277-111">Clients get the appropriate dial plan through provisioning settings that are automatically provided when users sign in to Teams.</span></span> <span data-ttu-id="e6277-112">以管理員身分，您可以使用 Microsoft 團隊系統管理中心或遠端 PowerShell 來管理和指派撥號計畫範圍階層。</span><span class="sxs-lookup"><span data-stu-id="e6277-112">As an admin, you can manage and assign dial plan scope levels by using the Microsoft Teams admin center or Remote PowerShell.</span></span>

<span data-ttu-id="e6277-113">在團隊中，有兩種類型的撥號方案：服務範圍與租使用者範圍（適用于您的組織）。</span><span class="sxs-lookup"><span data-stu-id="e6277-113">In Teams, there are two types of dial plans: service-scoped and tenant-scoped (which is for your organization).</span></span> <span data-ttu-id="e6277-114">系統會針對每個有電話系統的國家或地區定義服務範圍撥號方案。</span><span class="sxs-lookup"><span data-stu-id="e6277-114">A service-scoped dial plan is defined for every country or region where Phone System is available.</span></span> <span data-ttu-id="e6277-115">系統會自動為每位使用者指派與指派給使用者的使用位置相符的服務國家撥入方案。</span><span class="sxs-lookup"><span data-stu-id="e6277-115">Each user is automatically assigned the service country dial plan that matches the usage location assigned to the user.</span></span> <span data-ttu-id="e6277-116">您無法變更服務國家/地區撥號方案，但您可以建立租使用者範圍撥號方案，這會增加服務的國家/地區撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="e6277-116">You can't change the service country dial plan, but you can create tenant scoped dial plans, which augment the service country dial plan.</span></span> <span data-ttu-id="e6277-117">隨著用戶端的設定，他們會取得「有效的撥號方案」，它會結合服務國家/地區撥號方案和適當範圍的租使用者撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="e6277-117">As clients are provisioned, they obtain an "effective dial plan," which is a combination of the service country dial plan and the appropriately scoped tenant dial plan.</span></span> <span data-ttu-id="e6277-118">因此，您不需要在租使用者撥號方案中定義所有正常化規則，因為它們可能已存在於服務國家/地區撥號計畫中。</span><span class="sxs-lookup"><span data-stu-id="e6277-118">Therefore, it's not necessary to define all normalization rules in tenant dial plans as they might already exist in the service country dial plan.</span></span>

<span data-ttu-id="e6277-119">租使用者撥號方案可進一步分為兩個作用中-租使用者範圍或使用者範圍。</span><span class="sxs-lookup"><span data-stu-id="e6277-119">Tenant dial plans can be further broken into two scopes - tenant-scope or user-scope.</span></span> <span data-ttu-id="e6277-120">如果租使用者定義並指派使用者範圍的撥號方案，該使用者將會提供使用者服務國家/地區撥號方案的有效撥號計畫，以及指派的使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="e6277-120">If a tenant defines and assigns a user-scoped dial plan, that user will be provisioned with an effective dial plan of the user's service country dial plan and the assigned user dial plan.</span></span> <span data-ttu-id="e6277-121">如果租使用者定義租使用者範圍的撥號方案，但沒有指派使用者範圍的撥號方案，則該使用者將會使用使用者的服務國家/地區撥號方案和租使用者撥號方案的有效撥號方案進行設定。</span><span class="sxs-lookup"><span data-stu-id="e6277-121">If a tenant defines a tenant-scoped dial plan but doesn't assign a user-scoped dial plan, then that user will be provisioned with an effective dial plan of the user's service country dial plan and the tenant dial plan.</span></span>

<span data-ttu-id="e6277-122">下列是團隊中撥號方案的繼承模型。</span><span class="sxs-lookup"><span data-stu-id="e6277-122">The following is the inheritance model of dial plans in Teams.</span></span>

![如何在團隊中繼承撥號方案](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

<span data-ttu-id="e6277-124">下列是可能的有效撥號方案：</span><span class="sxs-lookup"><span data-stu-id="e6277-124">The following are the possible effective dial plans:</span></span>

 <span data-ttu-id="e6277-125">**服務國家/地區**如果未定義租使用者範圍的撥號方案，且未將租使用者範圍的撥號計畫指派給已設定的使用者，則使用者將會收到對應至與其使用位置相關聯之服務國家/地區的有效撥號方案。</span><span class="sxs-lookup"><span data-stu-id="e6277-125">**Service Country** If no tenant scoped dial plan is defined and no tenant user scoped dial plan is assigned to the provisioned user, the user will receive an effective dial plan mapped to the service country associated with their usage location.</span></span>

 <span data-ttu-id="e6277-126">**租使用者全域服務國家/地區**如果已定義租使用者的撥號方案，但未指派給使用者，則已置備的使用者會收到一份有效的撥號方案，其中包含合併的租使用者撥號方案，以及與其使用位置相關聯的服務國家/地區撥號方案。</span><span class="sxs-lookup"><span data-stu-id="e6277-126">**Tenant Global - Service Country** If a tenant user dial plan is defined but not assigned to a user, the provisioned user will receive an effective dial plan consisting of a merged tenant dial plan and the service country dial plan associated with their usage location.</span></span>

 <span data-ttu-id="e6277-127">**租使用者-服務國家/地區**如果已定義租使用者的撥號方案並指派給使用者，則已置備的使用者會收到一份有效的撥號方案，其中包含合併的租使用者撥號方案，以及與其使用位置相關聯的服務國家/地區撥號方案。</span><span class="sxs-lookup"><span data-stu-id="e6277-127">**Tenant User - Service Country** If a tenant user dial plan is defined and assigned to a user, the provisioned user will receive an effective dial plan consisting of the merged tenant user dial plan and the service country dial plan associated with their usage location.</span></span>

<span data-ttu-id="e6277-128">請參閱[建立及管理撥號計畫](create-and-manage-dial-plans.md)，以建立您的租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="e6277-128">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.</span></span>

> [!NOTE]
> <span data-ttu-id="e6277-129">在沒有撥號方案正常化規則套用至撥入號碼的情況下，撥號字串仍會正常化為 [+ CC]，其中 CC 是撥號使用者使用位置的國家/地區代碼。</span><span class="sxs-lookup"><span data-stu-id="e6277-129">In the scenario where no dial plan normalization rules apply to a dialed number, the dialed string is still normalized to prepend "+CC" where CC is the country code of the dialing user's usage location.</span></span> <span data-ttu-id="e6277-130">這適用于通話方案、直接路由和 PSTN 會議撥出案例。</span><span class="sxs-lookup"><span data-stu-id="e6277-130">This applies to Calling Plans, Direct Routing and PSTN Conference dial-out scenarios.</span></span>

## <a name="planning-for-tenant-dial-plans"></a><span data-ttu-id="e6277-131">規劃租使用者撥號方案</span><span class="sxs-lookup"><span data-stu-id="e6277-131">Planning for tenant dial plans</span></span>

<span data-ttu-id="e6277-132">若要規劃自訂撥號方案，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e6277-132">To plan custom dial plans, follow these steps:</span></span>

- <span data-ttu-id="e6277-133">**步驟 1**決定是否需要自訂撥號方案，以增強使用者的撥號體驗。</span><span class="sxs-lookup"><span data-stu-id="e6277-133">**Step 1** Decide whether a custom dial plan is needed to enhance the user dialing experience.</span></span> <span data-ttu-id="e6277-134">通常，必須支援非 E. 164 撥號，例如分機或縮寫國家撥號。</span><span class="sxs-lookup"><span data-stu-id="e6277-134">Typically, the need for one would be to support non-E.164 dialing, such as extensions or abbreviated national dialing.</span></span>

- <span data-ttu-id="e6277-135">**步驟 2**判斷您是否需要承租人全域或租使用者範圍的撥號方案，或兩者皆可。</span><span class="sxs-lookup"><span data-stu-id="e6277-135">**Step 2** Determine whether tenant global or tenant user scoped dial plans are needed, or both.</span></span> <span data-ttu-id="e6277-136">如果使用者有不同的本機撥號需求，就需要使用者範圍的撥號方案。</span><span class="sxs-lookup"><span data-stu-id="e6277-136">User scoped dial plans are needed if users have different local dialing requirements.</span></span>

- <span data-ttu-id="e6277-137">**步驟 3**針對每個所需的撥號方案，找出有效的數位模式。</span><span class="sxs-lookup"><span data-stu-id="e6277-137">**Step 3** Identify valid number patterns for each required dial plan.</span></span> <span data-ttu-id="e6277-138">只有服務層級撥號方案中未定義的數位模式是必要的。</span><span class="sxs-lookup"><span data-stu-id="e6277-138">Only the number patterns that are not defined in the service level country dial plans are required.</span></span>

- <span data-ttu-id="e6277-139">**步驟 4**為命名撥號方案開發組織範圍的配置。</span><span class="sxs-lookup"><span data-stu-id="e6277-139">**Step 4** Develop an organization-wide scheme for naming dial plans.</span></span> <span data-ttu-id="e6277-140">採用標準命名配置，可確保整個組織的一致性，並讓維護與更新變得更容易。</span><span class="sxs-lookup"><span data-stu-id="e6277-140">Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>


## <a name="creating-your-new-tenant-dial-plan"></a><span data-ttu-id="e6277-141">建立新的租使用者撥號方案</span><span class="sxs-lookup"><span data-stu-id="e6277-141">Creating your new tenant dial plan</span></span>

<span data-ttu-id="e6277-142">當您建立新的撥號方案時，您必須放入所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="e6277-142">When you create a new dial plan, you must put in the information that is required.</span></span>

### <a name="name-and-simple-name"></a><span data-ttu-id="e6277-143">名稱與簡單名稱</span><span class="sxs-lookup"><span data-stu-id="e6277-143">Name and simple name</span></span>

<span data-ttu-id="e6277-144">針對使用者撥號方案，您應該指定一個描述名稱，以識別將指派撥號方案的使用者。</span><span class="sxs-lookup"><span data-stu-id="e6277-144">For user dial plans, you should specify a descriptive name that identifies the users to which the dial plan will be assigned.</span></span> <span data-ttu-id="e6277-145">撥號計畫簡單名稱是使用從撥號方案名稱衍生的字串預先填入。</span><span class="sxs-lookup"><span data-stu-id="e6277-145">The dial plan Simple Name is pre-populated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="e6277-146">[簡易名稱] 欄位為 [可編輯]，可讓您為撥號方案建立更具描述性的命名慣例。</span><span class="sxs-lookup"><span data-stu-id="e6277-146">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="e6277-147">[簡易名稱] 值不能為空白，且必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e6277-147">The Simple Name value cannot be empty and must be unique.</span></span> <span data-ttu-id="e6277-148">最佳做法是為您的整個組織開發一個命名慣例，然後在所有網站和使用者中統一使用這個慣例。</span><span class="sxs-lookup"><span data-stu-id="e6277-148">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

### <a name="description"></a><span data-ttu-id="e6277-149">描述</span><span class="sxs-lookup"><span data-stu-id="e6277-149">Description</span></span>

<span data-ttu-id="e6277-150">我們建議您輸入適用之地理位置的通用、可識別名稱，或對應的撥號方案所屬的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="e6277-150">We recommend that you type the common, recognizable name of the geographic location or group of users to which the corresponding dial plan applies.</span></span>

### <a name="external-access-prefix"></a><span data-ttu-id="e6277-151">外部存取首碼</span><span class="sxs-lookup"><span data-stu-id="e6277-151">External access prefix</span></span>
<span data-ttu-id="e6277-152"><a name="bkexternalprefix"> </a></span><span class="sxs-lookup"><span data-stu-id="e6277-152"><a name="bkexternalprefix"> </a></span></span>

<span data-ttu-id="e6277-153">如果使用者需要撥一或多個額外的前導數位（例如，9）來取得外部線路，您可以指定最多四個字元（#、\* 及0-9）的外部存取前置詞。</span><span class="sxs-lookup"><span data-stu-id="e6277-153">You can specify an external access prefix of up to four characters (#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

> [!NOTE]
> <span data-ttu-id="e6277-154">如果您指定外部存取首碼，就不需要建立額外的正常化規則來容納該前置詞。</span><span class="sxs-lookup"><span data-stu-id="e6277-154">If you specify an external access prefix, you don't need to create an additional normalization rule to accommodate the prefix.</span></span>

<span data-ttu-id="e6277-155">請參閱[建立及管理撥號計畫](create-and-manage-dial-plans.md)，以建立您的租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="e6277-155">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.</span></span>

## <a name="normalization-rules"></a><span data-ttu-id="e6277-156">正規化規則</span><span class="sxs-lookup"><span data-stu-id="e6277-156">Normalization rules</span></span>
<span data-ttu-id="e6277-157"><a name="bknormalizationrule"> </a></span><span class="sxs-lookup"><span data-stu-id="e6277-157"><a name="bknormalizationrule"> </a></span></span>

<span data-ttu-id="e6277-158">正常化規則定義以各種格式表示的電話號碼的翻譯方式。</span><span class="sxs-lookup"><span data-stu-id="e6277-158">Normalization rules define how phone numbers expressed in various formats are to be translated.</span></span> <span data-ttu-id="e6277-159">根據撥號的地區設定，相同的數位字串可能會以不同的方式加以轉譯和翻譯。</span><span class="sxs-lookup"><span data-stu-id="e6277-159">The same number string may be interpreted and translated differently, depending on the locale from which it is dialed.</span></span> <span data-ttu-id="e6277-160">如果使用者需要能夠撥號的內部或外部號碼的縮寫，可能需要正常化規則。</span><span class="sxs-lookup"><span data-stu-id="e6277-160">Normalization rules may be necessary if users need to be able to dial abbreviated internal or external numbers.</span></span>

<span data-ttu-id="e6277-161">必須將一或多個正常化規則指派給撥號方案。</span><span class="sxs-lookup"><span data-stu-id="e6277-161">One or more normalization rules must be assigned to the dial plan.</span></span> <span data-ttu-id="e6277-162">正常化規則是從上到下，因此它們在租使用者撥號方案中出現的順序非常重要。</span><span class="sxs-lookup"><span data-stu-id="e6277-162">Normalization rules are matched from top to bottom, so the order in which they appear in a tenant dial plan is important.</span></span> <span data-ttu-id="e6277-163">例如，如果租使用者撥號方案有10個正常化規則，則在第一個正常化規則（如果沒有匹配的秒數）之後，就會嘗試從第一個正常化規則開始，依此類推。</span><span class="sxs-lookup"><span data-stu-id="e6277-163">For example, if a tenant dial plan has 10 normalization rules, the dialed number matching logic will be tried starting with the first normalization rule, if there isn't a match then the second, and so forth.</span></span> <span data-ttu-id="e6277-164">如果進行了相符，就會使用該規則，而且不會對任何其他已定義的規則進行比較。</span><span class="sxs-lookup"><span data-stu-id="e6277-164">If a match is made, that rule is used and there is no effort to match any other rules that are defined.</span></span> <span data-ttu-id="e6277-165">在指定的租使用者撥號方案中，最多可以有50正常化規則。</span><span class="sxs-lookup"><span data-stu-id="e6277-165">There can be a maximum of 50 normalization rules in a given tenant dial plan.</span></span>

### <a name="determining-the-required-normalization-rules"></a><span data-ttu-id="e6277-166">判斷所需的正常化規則</span><span class="sxs-lookup"><span data-stu-id="e6277-166">Determining the required normalization rules</span></span>

<span data-ttu-id="e6277-167">因為任何租使用者撥號方案都會與指定的使用者服務國家/地區撥號方案進行有效的合併，所以很可能必須評估服務國家/地區撥號方案的正常化規則，才能判斷需要哪些租使用者撥號規劃正常化規則。</span><span class="sxs-lookup"><span data-stu-id="e6277-167">Because any tenant dial plan is effectively merged with a given user's service country dial plan, it is likely that the service country dial plan's normalization rules need to be evaluated in order to determine which tenant dial plan normalization rules are needed.</span></span> <span data-ttu-id="e6277-168">CsEffectiveTenantDialPlan Cmdlet 可用來**達到**此目的。</span><span class="sxs-lookup"><span data-stu-id="e6277-168">The **Get-CsEffectiveTenantDialPlan** cmdlet can be used for this purpose.</span></span> <span data-ttu-id="e6277-169">這個 Cmdlet 會將使用者的身分識別當作輸入參數，並傳回所有適用于使用者的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="e6277-169">The cmdlet takes the user's identity as the input parameter and will return all normalization rules that are applicable to the user.</span></span>

### <a name="creating-normalization-rules"></a><span data-ttu-id="e6277-170">建立正常化規則</span><span class="sxs-lookup"><span data-stu-id="e6277-170">Creating normalization rules</span></span>
<span data-ttu-id="e6277-171"><a name="createrule"> </a></span><span class="sxs-lookup"><span data-stu-id="e6277-171"><a name="createrule"> </a></span></span>

<span data-ttu-id="e6277-172">正常化規則使用 .NET Framework 正則運算式，指定伺服器用來將撥號字串轉換成 E. 164 格式的數位相符模式。</span><span class="sxs-lookup"><span data-stu-id="e6277-172">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format.</span></span> <span data-ttu-id="e6277-173">您可以透過指定相符的正則運算式來建立正常化規則，以及在找到相符專案時要完成的翻譯。</span><span class="sxs-lookup"><span data-stu-id="e6277-173">Normalization rules can be created by specifying the regular expression for the match and the translation to be done when a match is found.</span></span> <span data-ttu-id="e6277-174">完成後，您可以輸入測試號碼來驗證正常化規則是否如預期的那樣運作。</span><span class="sxs-lookup"><span data-stu-id="e6277-174">When you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="e6277-175">如需使用 .NET Framework 正則運算式的詳細資料，請參閱[.Net Framework 正則運算式](https://go.microsoft.com/fwlink/p/?linkId=140927)。</span><span class="sxs-lookup"><span data-stu-id="e6277-175">For details about using .NET Framework regular expressions, see [.NET Framework Regular Expressions](https://go.microsoft.com/fwlink/p/?linkId=140927).</span></span>

<span data-ttu-id="e6277-176">請參閱[建立及管理撥號計畫](create-and-manage-dial-plans.md)，以建立及管理您的租使用者撥號方案的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="e6277-176">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage normalization rules for your tenant dial plans.</span></span>

### <a name="sample-normalization-rules"></a><span data-ttu-id="e6277-177">範例正常化規則</span><span class="sxs-lookup"><span data-stu-id="e6277-177">Sample normalization rules</span></span>

<span data-ttu-id="e6277-178">下表顯示已寫入為 .NET Framework 一般運算式的範例正常化規則。</span><span class="sxs-lookup"><span data-stu-id="e6277-178">The following table shows sample normalization rules that are written as .NET Framework regular expressions.</span></span> <span data-ttu-id="e6277-179">這些範例只是範例，並不代表建立您自己的正常化規則的規範性參考。</span><span class="sxs-lookup"><span data-stu-id="e6277-179">The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

<span data-ttu-id="e6277-180"><a name="regularexpression"> </a> 
 **使用 .net Framework 一般運算式的正常化規則**</span><span class="sxs-lookup"><span data-stu-id="e6277-180"><a name="regularexpression"> </a>
**Normalization rules using .NET Framework regular expressions**</span></span>

| <span data-ttu-id="e6277-181">規則名稱</span><span class="sxs-lookup"><span data-stu-id="e6277-181">Rule name</span></span><br/> | <span data-ttu-id="e6277-182">描述</span><span class="sxs-lookup"><span data-stu-id="e6277-182">Description</span></span><br/> | <span data-ttu-id="e6277-183">數位模式</span><span class="sxs-lookup"><span data-stu-id="e6277-183">Number pattern</span></span><br/> | <span data-ttu-id="e6277-184">翻譯</span><span class="sxs-lookup"><span data-stu-id="e6277-184">Translation</span></span><br/> | <span data-ttu-id="e6277-185">範例</span><span class="sxs-lookup"><span data-stu-id="e6277-185">Example</span></span><br/> |
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e6277-186">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="e6277-186">4digitExtension</span></span>  <br/> |<span data-ttu-id="e6277-187">翻譯4位數延伸。</span><span class="sxs-lookup"><span data-stu-id="e6277-187">Translates 4-digit extensions.</span></span>  <br/> |<span data-ttu-id="e6277-188">^ （ \\ d {4} ） $</span><span class="sxs-lookup"><span data-stu-id="e6277-188">^(\\d{4})$</span></span>  <br/> |<span data-ttu-id="e6277-189">+ 1425555 $ 1</span><span class="sxs-lookup"><span data-stu-id="e6277-189">+1425555$1</span></span>  <br/> |<span data-ttu-id="e6277-190">0100已轉譯為 + 14255550100</span><span class="sxs-lookup"><span data-stu-id="e6277-190">0100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="e6277-191">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="e6277-191">5digitExtension</span></span>  <br/> |<span data-ttu-id="e6277-192">翻譯5位數的延伸。</span><span class="sxs-lookup"><span data-stu-id="e6277-192">Translates 5-digit extensions.</span></span>  <br/> |<span data-ttu-id="e6277-193">^ 5 （ \\ d {4} ） $</span><span class="sxs-lookup"><span data-stu-id="e6277-193">^5(\\d{4})$</span></span>  <br/> |<span data-ttu-id="e6277-194">+ 1425555 $ 1</span><span class="sxs-lookup"><span data-stu-id="e6277-194">+1425555$1</span></span>  <br/> |<span data-ttu-id="e6277-195">50100已轉譯為 + 14255550100</span><span class="sxs-lookup"><span data-stu-id="e6277-195">50100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="e6277-196">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="e6277-196">7digitcallingRedmond</span></span>  <br/> |<span data-ttu-id="e6277-197">將7位數的數位轉譯為雷德式當地電話號碼。</span><span class="sxs-lookup"><span data-stu-id="e6277-197">Translates 7-digit numbers to Redmond local numbers.</span></span>  <br/> |<span data-ttu-id="e6277-198">^ （ \\ d {7} ） $</span><span class="sxs-lookup"><span data-stu-id="e6277-198">^(\\d{7})$</span></span>  <br/> |<span data-ttu-id="e6277-199">+ 1425 $ 1</span><span class="sxs-lookup"><span data-stu-id="e6277-199">+1425$1</span></span>  <br/> |<span data-ttu-id="e6277-200">5550100已轉譯為 + 14255550100</span><span class="sxs-lookup"><span data-stu-id="e6277-200">5550100 is translated to +14255550100</span></span>  <br/>|
|<span data-ttu-id="e6277-201">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="e6277-201">RedmondOperator</span></span>  <br/> |<span data-ttu-id="e6277-202">將0轉換為雷德運算子。</span><span class="sxs-lookup"><span data-stu-id="e6277-202">Translates 0 to Redmond Operator.</span></span>  <br/> |<span data-ttu-id="e6277-203">^ $0</span><span class="sxs-lookup"><span data-stu-id="e6277-203">^0$</span></span>  <br/> |<span data-ttu-id="e6277-204">+ 14255550100</span><span class="sxs-lookup"><span data-stu-id="e6277-204">+14255550100</span></span>  <br/> |<span data-ttu-id="e6277-205">0已轉譯為 + 14255550100</span><span class="sxs-lookup"><span data-stu-id="e6277-205">0 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="e6277-206">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="e6277-206">RedmondSitePrefix</span></span>  <br/> |<span data-ttu-id="e6277-207">使用網路上的前置詞（6）和雷德蒙的網站程式碼（222）來轉譯數位。</span><span class="sxs-lookup"><span data-stu-id="e6277-207">Translates numbers with on-net prefix (6) and Redmond site code (222).</span></span>  <br/> |<span data-ttu-id="e6277-208">^ 6222 （ \\ d {4} ） $</span><span class="sxs-lookup"><span data-stu-id="e6277-208">^6222(\\d{4})$</span></span>  <br/> |<span data-ttu-id="e6277-209">+ 1425555 $ 1</span><span class="sxs-lookup"><span data-stu-id="e6277-209">+1425555$1</span></span>  <br/> |<span data-ttu-id="e6277-210">62220100已轉譯為 + 14255550100</span><span class="sxs-lookup"><span data-stu-id="e6277-210">62220100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="e6277-211">5digitRange</span><span class="sxs-lookup"><span data-stu-id="e6277-211">5digitRange</span></span>  <br/> |<span data-ttu-id="e6277-212">翻譯5位數的延伸開始于3-7 （含）之間的數位範圍。</span><span class="sxs-lookup"><span data-stu-id="e6277-212">Translates 5-digit extensions starting with the digit range between 3-7 inclusive.</span></span>  <br/> |<span data-ttu-id="e6277-213">^ （[3-7] \\ d {4} ） $</span><span class="sxs-lookup"><span data-stu-id="e6277-213">^([3-7]\\d{4})$</span></span>  <br/> |<span data-ttu-id="e6277-214">+ 142555 $ 1</span><span class="sxs-lookup"><span data-stu-id="e6277-214">+142555$1</span></span> <br/> |<span data-ttu-id="e6277-215">54567已轉譯為 + 14255554567</span><span class="sxs-lookup"><span data-stu-id="e6277-215">54567 is translated to +14255554567</span></span>  <br/> |
|<span data-ttu-id="e6277-216">PrefixAdded</span><span class="sxs-lookup"><span data-stu-id="e6277-216">PrefixAdded</span></span>  <br/> |<span data-ttu-id="e6277-217">在包含第一個和第三個數字限制的9位數數位的前面加上國家/地區的首碼。</span><span class="sxs-lookup"><span data-stu-id="e6277-217">Adds a country prefix in front of a 9 digit number with restrictions on the first and third digits.</span></span>  <br/> |<span data-ttu-id="e6277-218">^ （[2-9] \\ d \\ d [2-9] \\ d {6} ） $</span><span class="sxs-lookup"><span data-stu-id="e6277-218">^([2-9]\\d\\d[2-9]\\d{6})$</span></span>  <br/> |<span data-ttu-id="e6277-219">1 $ 1</span><span class="sxs-lookup"><span data-stu-id="e6277-219">1$1</span></span>  <br/> |<span data-ttu-id="e6277-220">4255554567已轉換為14255554567</span><span class="sxs-lookup"><span data-stu-id="e6277-220">4255554567 is translated to 14255554567</span></span>  <br/> |
|<span data-ttu-id="e6277-221">NoTranslation</span><span class="sxs-lookup"><span data-stu-id="e6277-221">NoTranslation</span></span>  <br/> |<span data-ttu-id="e6277-222">符合5位數但沒有翻譯。</span><span class="sxs-lookup"><span data-stu-id="e6277-222">Match 5 digits but no translation.</span></span>  <br/> |<span data-ttu-id="e6277-223">^ （ \\ d {5} ） $</span><span class="sxs-lookup"><span data-stu-id="e6277-223">^(\\d{5})$</span></span>  <br/> |<span data-ttu-id="e6277-224">$1</span><span class="sxs-lookup"><span data-stu-id="e6277-224">$1</span></span>  <br/> |<span data-ttu-id="e6277-225">34567已轉換為34567</span><span class="sxs-lookup"><span data-stu-id="e6277-225">34567 is translated to 34567</span></span>  <br/> |

 <span data-ttu-id="e6277-226">**以上述正常化規則為基礎的雷蒙德撥號方案。**</span><span class="sxs-lookup"><span data-stu-id="e6277-226">**Redmond dial plan based on normalization rules shown above.**</span></span>

 <span data-ttu-id="e6277-227">下表說明雷蒙德、華盛頓、英國的範例撥號方案，根據上表所示的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="e6277-227">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

| <span data-ttu-id="e6277-228">雷德蒙撥號方案</span><span class="sxs-lookup"><span data-stu-id="e6277-228">Redmond dial plan</span></span><br/> |
|:-----------------------|                                                                                                                      
| <span data-ttu-id="e6277-229">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="e6277-229">5digitExtension</span></span> <br/> |                                                                                                                                    
| <span data-ttu-id="e6277-230">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="e6277-230">7digitcallingRedmond</span></span> <br/> |
| <span data-ttu-id="e6277-231">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="e6277-231">RedmondSitePrefix</span></span> <br/> |
| <span data-ttu-id="e6277-232">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="e6277-232">RedmondOperator</span></span> <br/> |

> [!NOTE]
> <span data-ttu-id="e6277-233">上表所示的正常化規則名稱不會包含空格，但這是選擇的考慮。</span><span class="sxs-lookup"><span data-stu-id="e6277-233">The normalization rules names shown in the preceding table don't include spaces, but this is a matter of choice.</span></span> <span data-ttu-id="e6277-234">例如，資料表中的第一個名稱可以是 "5 位數副檔名" 或 "5 位數副檔名"，但仍然有效。</span><span class="sxs-lookup"><span data-stu-id="e6277-234">The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e6277-235">相關主題</span><span class="sxs-lookup"><span data-stu-id="e6277-235">Related topics</span></span>

[<span data-ttu-id="e6277-236">建立和管理撥號對應表</span><span class="sxs-lookup"><span data-stu-id="e6277-236">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)

[<span data-ttu-id="e6277-237">通話方案所用的不同類型的電話號碼</span><span class="sxs-lookup"><span data-stu-id="e6277-237">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="e6277-238">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="e6277-238">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="e6277-239">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="e6277-239">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

<span data-ttu-id="e6277-240">[緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="e6277-240">[Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
