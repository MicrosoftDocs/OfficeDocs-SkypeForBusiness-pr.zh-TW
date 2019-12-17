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
f1keywords: ms.teamsadmincenter.voice.dialplans.overview
ms.custom:
- Calling Plans
description: '瞭解您可以在小組中使用的撥號方案類型（PSTN 呼叫撥號方案），以及如何為您的組織選擇一個電話。  '
ms.openlocfilehash: 0dadb0335f622bb297d4299aafc50a40dafcc583
ms.sourcegitcommit: dc240b123efb03d5ab0545d650a973bf60d04506
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/17/2019
ms.locfileid: "40069324"
---
# <a name="what-are-dial-plans"></a><span data-ttu-id="ec6ad-103">什麼是撥號對應表？</span><span class="sxs-lookup"><span data-stu-id="ec6ad-103">What are dial plans?</span></span>

<span data-ttu-id="ec6ad-104">撥號方案是一組命名的正常化規則，可將個別使用者撥打的電話號碼轉換成替代格式（通常是 E. 164），以進行呼叫授權及呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-104">A dial plan is a named set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="ec6ad-105">撥號計畫由一或多個正常化規則所組成，這些規則定義以不同格式表示的電話號碼如何轉換為替代格式。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-105">A dial plan consists of one or more normalization rules that define how phone numbers expressed in various formats are translated to an alternate format.</span></span> <span data-ttu-id="ec6ad-106">在不同的撥號方案中，相同的撥號字串可能會以不同的方式加以轉譯，因此，根據指派給特定使用者的撥號方案而定，相同的撥入號碼可能會以不同的方式進行轉換和路由。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-106">The same dial string may be interpreted and translated differently in different dial plans, so depending on which dial plan is assigned to a given user, the same dialed number may be translated and routed differently.</span></span>

<span data-ttu-id="ec6ad-107">請參閱[建立及管理撥號計畫](create-and-manage-dial-plans.md)，以建立和管理租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-107">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage tenant dial plans.</span></span>

## <a name="tenant-dial-plan-scope"></a><span data-ttu-id="ec6ad-108">租使用者撥號計畫範圍</span><span class="sxs-lookup"><span data-stu-id="ec6ad-108">Tenant dial plan scope</span></span>

<span data-ttu-id="ec6ad-109">撥號計畫的範圍決定您可以套用撥號方案的階層等級。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-109">A dial plan's scope determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="ec6ad-110">用戶端透過提供設定來取得適當的撥號方案，這些設定是在使用者登入小組時自動提供的。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-110">Clients get the appropriate dial plan through provisioning settings that are automatically provided when users sign in to Teams.</span></span> <span data-ttu-id="ec6ad-111">以管理員身分，您可以使用 Microsoft 團隊系統管理中心或遠端 PowerShell 來管理和指派撥號計畫範圍階層。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-111">As an admin, you can manage and assign dial plan scope levels by using the Microsoft Teams admin center or Remote PowerShell.</span></span>

<span data-ttu-id="ec6ad-112">在團隊中，有兩種類型的撥號方案：服務範圍與租使用者範圍（適用于您的組織）。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-112">In Teams, there are two types of dial plans: service-scoped and tenant-scoped (which is for your organization).</span></span> <span data-ttu-id="ec6ad-113">系統會針對每個有電話系統的國家或地區定義服務範圍撥號方案。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-113">A service-scoped dial plan is defined for every country or region where Phone System is available.</span></span> <span data-ttu-id="ec6ad-114">系統會自動為每位使用者指派與指派給使用者的使用位置相符的服務國家撥入方案。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-114">Each user is automatically assigned the service country dial plan that matches the usage location assigned to the user.</span></span> <span data-ttu-id="ec6ad-115">您無法變更服務國家/地區撥號方案，但您可以建立租使用者範圍撥號方案，這會增加服務的國家/地區撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-115">You can't change the service country dial plan, but you can create tenant scoped dial plans, which augment the service country dial plan.</span></span> <span data-ttu-id="ec6ad-116">隨著用戶端的設定，他們會取得「有效的撥號方案」，它會結合服務國家/地區撥號方案和適當範圍的租使用者撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-116">As clients are provisioned, they obtain an "effective dial plan," which is a combination of the service country dial plan and the appropriately scoped tenant dial plan.</span></span> <span data-ttu-id="ec6ad-117">因此，您不需要在租使用者撥號方案中定義所有正常化規則，因為它們可能已存在於服務國家/地區撥號計畫中。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-117">Therefore, it's not necessary to define all normalization rules in tenant dial plans as they might already exist in the service country dial plan.</span></span>

<span data-ttu-id="ec6ad-118">租使用者撥號方案可進一步分為兩個作用中-租使用者範圍或使用者範圍。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-118">Tenant dial plans can be further broken into two scopes - tenant-scope or user-scope.</span></span> <span data-ttu-id="ec6ad-119">如果租使用者定義並指派使用者範圍的撥號方案，該使用者將會提供使用者服務國家/地區撥號方案的有效撥號計畫，以及指派的使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-119">If a tenant defines and assigns a user-scoped dial plan, that user will be provisioned with an effective dial plan of the user's service country dial plan and the assigned user dial plan.</span></span> <span data-ttu-id="ec6ad-120">如果租使用者定義租使用者範圍的撥號方案，但沒有指派使用者範圍的撥號方案，則該使用者將會使用使用者的服務國家/地區撥號方案和租使用者撥號方案的有效撥號方案進行設定。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-120">If a tenant defines a tenant-scoped dial plan but doesn't assign a user-scoped dial plan, then that user will be provisioned with an effective dial plan of the user's service country dial plan and the tenant dial plan.</span></span>

<span data-ttu-id="ec6ad-121">下列是團隊中撥號方案的繼承模型。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-121">The following is the inheritance model of dial plans in Teams.</span></span>

![如何在團隊中繼承撥號方案](media/b2744f33-ebbd-4c23-bfba-1747312ab178.png)

<span data-ttu-id="ec6ad-123">下列是可能的有效撥號方案：</span><span class="sxs-lookup"><span data-stu-id="ec6ad-123">The following are the possible effective dial plans:</span></span>

 <span data-ttu-id="ec6ad-124">**服務國家/地區**如果未定義租使用者範圍的撥號方案，且未將租使用者範圍的撥號計畫指派給已設定的使用者，則使用者將會收到對應至與其使用位置相關聯之服務國家/地區的有效撥號方案。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-124">**Service Country** If no tenant scoped dial plan is defined and no tenant user scoped dial plan is assigned to the provisioned user, the user will receive an effective dial plan mapped to the service country associated with their usage location.</span></span>

 <span data-ttu-id="ec6ad-125">**租使用者全域服務國家/地區**如果已定義租使用者的撥號方案，但未指派給使用者，則已置備的使用者會收到一份有效的撥號方案，其中包含合併的租使用者撥號方案，以及與其使用位置相關聯的服務國家/地區撥號方案。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-125">**Tenant Global - Service Country** If a tenant user dial plan is defined but not assigned to a user, the provisioned user will receive an effective dial plan consisting of a merged tenant dial plan and the service country dial plan associated with their usage location.</span></span>

 <span data-ttu-id="ec6ad-126">**租使用者-服務國家/地區**如果已定義租使用者的撥號方案並指派給使用者，則已置備的使用者會收到一份有效的撥號方案，其中包含合併的租使用者撥號方案，以及與其使用位置相關聯的服務國家/地區撥號方案。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-126">**Tenant User - Service Country** If a tenant user dial plan is defined and assigned to a user, the provisioned user will receive an effective dial plan consisting of the merged tenant user dial plan and the service country dial plan associated with their usage location.</span></span>

<span data-ttu-id="ec6ad-127">請參閱[建立及管理撥號計畫](create-and-manage-dial-plans.md)，以建立您的租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-127">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.</span></span>

## <a name="planning-for-tenant-dial-plans"></a><span data-ttu-id="ec6ad-128">規劃租使用者撥號方案</span><span class="sxs-lookup"><span data-stu-id="ec6ad-128">Planning for tenant dial plans</span></span>

<span data-ttu-id="ec6ad-129">若要規劃自訂撥號方案，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ec6ad-129">To plan custom dial plans, follow these steps:</span></span>

- <span data-ttu-id="ec6ad-130">**步驟 1**決定是否需要自訂撥號方案，以增強使用者的撥號體驗。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-130">**Step 1** Decide whether a custom dial plan is needed to enhance the user dialing experience.</span></span> <span data-ttu-id="ec6ad-131">通常，必須支援非 E. 164 撥號，例如分機或縮寫國家撥號。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-131">Typically, the need for one would be to support non-E.164 dialing, such as extensions or abbreviated national dialing.</span></span>

- <span data-ttu-id="ec6ad-132">**步驟 2**判斷您是否需要承租人全域或租使用者範圍的撥號方案，或兩者皆可。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-132">**Step 2** Determine whether tenant global or tenant user scoped dial plans are needed, or both.</span></span> <span data-ttu-id="ec6ad-133">如果使用者有不同的本機撥號需求，就需要使用者範圍的撥號方案。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-133">User scoped dial plans are needed if users have different local dialing requirements.</span></span>

- <span data-ttu-id="ec6ad-134">**步驟 3**針對每個所需的撥號方案，找出有效的數位模式。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-134">**Step 3** Identify valid number patterns for each required dial plan.</span></span> <span data-ttu-id="ec6ad-135">只有服務層級撥號方案中未定義的數位模式是必要的。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-135">Only the number patterns that are not defined in the service level country dial plans are required.</span></span>

- <span data-ttu-id="ec6ad-136">**步驟 4**為命名撥號方案開發組織範圍的配置。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-136">**Step 4** Develop an organization-wide scheme for naming dial plans.</span></span> <span data-ttu-id="ec6ad-137">採用標準命名配置，可確保整個組織的一致性，並讓維護與更新變得更容易。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-137">Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>


## <a name="creating-your-new-tenant-dial-plan"></a><span data-ttu-id="ec6ad-138">建立新的租使用者撥號方案</span><span class="sxs-lookup"><span data-stu-id="ec6ad-138">Creating your new tenant dial plan</span></span>

<span data-ttu-id="ec6ad-139">當您建立新的撥號方案時，您必須放入所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-139">When you create a new dial plan, you must put in the information that is required.</span></span>

### <a name="name-and-simple-name"></a><span data-ttu-id="ec6ad-140">名稱與簡單名稱</span><span class="sxs-lookup"><span data-stu-id="ec6ad-140">Name and simple name</span></span>

<span data-ttu-id="ec6ad-141">針對使用者撥號方案，您應該指定一個描述名稱，以識別將指派撥號方案的使用者。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-141">For user dial plans, you should specify a descriptive name that identifies the users to which the dial plan will be assigned.</span></span> <span data-ttu-id="ec6ad-142">撥號計畫簡單名稱是使用從撥號方案名稱衍生的字串預先填入。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-142">The dial plan Simple Name is pre-populated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="ec6ad-143">[簡易名稱] 欄位為 [可編輯]，可讓您為撥號方案建立更具描述性的命名慣例。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-143">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="ec6ad-144">[簡易名稱] 值不能為空白，且必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-144">The Simple Name value cannot be empty and must be unique.</span></span> <span data-ttu-id="ec6ad-145">最佳做法是為您的整個組織開發一個命名慣例，然後在所有網站和使用者中統一使用這個慣例。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-145">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

### <a name="description"></a><span data-ttu-id="ec6ad-146">描述</span><span class="sxs-lookup"><span data-stu-id="ec6ad-146">Description</span></span>

<span data-ttu-id="ec6ad-147">我們建議您輸入適用之地理位置的通用、可識別名稱，或對應的撥號方案所屬的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-147">We recommend that you type the common, recognizable name of the geographic location or group of users to which the corresponding dial plan applies.</span></span>

### <a name="external-access-prefix"></a><span data-ttu-id="ec6ad-148">外部存取首碼</span><span class="sxs-lookup"><span data-stu-id="ec6ad-148">External access prefix</span></span>
<span data-ttu-id="ec6ad-149"><a name="bkexternalprefix"> </a></span><span class="sxs-lookup"><span data-stu-id="ec6ad-149"></span></span>

<span data-ttu-id="ec6ad-150">如果使用者需要撥一或多個額外的前導數位（例如，9）來取得外部線路，您可以指定最多四個字元（#、\* 及0-9）的外部存取前置詞。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-150">You can specify an external access prefix of up to four characters (#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

> [!NOTE]
> <span data-ttu-id="ec6ad-151">如果您指定外部存取首碼，就不需要建立額外的正常化規則來容納該前置詞。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-151">If you specify an external access prefix, you don't need to create an additional normalization rule to accommodate the prefix.</span></span>

<span data-ttu-id="ec6ad-152">請參閱[建立及管理撥號計畫](create-and-manage-dial-plans.md)，以建立您的租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-152">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create your tenant dial plans.</span></span>

## <a name="normalization-rules"></a><span data-ttu-id="ec6ad-153">正規化規則</span><span class="sxs-lookup"><span data-stu-id="ec6ad-153">Normalization rules</span></span>
<span data-ttu-id="ec6ad-154"><a name="bknormalizationrule"> </a></span><span class="sxs-lookup"><span data-stu-id="ec6ad-154"></span></span>

<span data-ttu-id="ec6ad-155">正常化規則定義以各種格式表示的電話號碼的翻譯方式。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-155">Normalization rules define how phone numbers expressed in various formats are to be translated.</span></span> <span data-ttu-id="ec6ad-156">根據撥號的地區設定，相同的數位字串可能會以不同的方式加以轉譯和翻譯。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-156">The same number string may be interpreted and translated differently, depending on the locale from which it is dialed.</span></span> <span data-ttu-id="ec6ad-157">如果使用者需要能夠撥號的內部或外部號碼的縮寫，可能需要正常化規則。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-157">Normalization rules may be necessary if users need to be able to dial abbreviated internal or external numbers.</span></span>

<span data-ttu-id="ec6ad-158">必須將一或多個正常化規則指派給撥號方案。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-158">One or more normalization rules must be assigned to the dial plan.</span></span> <span data-ttu-id="ec6ad-159">正常化規則是從上到下，因此它們在租使用者撥號方案中出現的順序非常重要。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-159">Normalization rules are matched from top to bottom, so the order in which they appear in a tenant dial plan is important.</span></span> <span data-ttu-id="ec6ad-160">例如，如果租使用者撥號方案有10個正常化規則，則在第一個正常化規則（如果沒有匹配的秒數）之後，就會嘗試從第一個正常化規則開始，依此類推。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-160">For example, if a tenant dial plan has 10 normalization rules, the dialed number matching logic will be tried starting with the first normalization rule, if there isn't a match then the second, and so forth.</span></span> <span data-ttu-id="ec6ad-161">如果進行了相符，就會使用該規則，而且不會對任何其他已定義的規則進行比較。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-161">If a match is made, that rule is used and there is no effort to match any other rules that are defined.</span></span> <span data-ttu-id="ec6ad-162">在指定的租使用者撥號方案中，最多可以有50正常化規則。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-162">There can be a maximum of 50 normalization rules in a given tenant dial plan.</span></span>

### <a name="determining-the-required-normalization-rules"></a><span data-ttu-id="ec6ad-163">判斷所需的正常化規則</span><span class="sxs-lookup"><span data-stu-id="ec6ad-163">Determining the required normalization rules</span></span>

<span data-ttu-id="ec6ad-164">因為任何租使用者撥號方案都會與指定的使用者服務國家/地區撥號方案進行有效的合併，所以很可能必須評估服務國家/地區撥號方案的正常化規則，才能判斷需要哪些租使用者撥號規劃正常化規則。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-164">Because any tenant dial plan is effectively merged with a given user's service country dial plan, it is likely that the service country dial plan's normalization rules need to be evaluated in order to determine which tenant dial plan normalization rules are needed.</span></span> <span data-ttu-id="ec6ad-165">CsEffectiveTenantDialPlan Cmdlet 可用來**達到**此目的。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-165">The **Get-CsEffectiveTenantDialPlan** cmdlet can be used for this purpose.</span></span> <span data-ttu-id="ec6ad-166">這個 Cmdlet 會將使用者的身分識別當作輸入參數，並傳回所有適用于使用者的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-166">The cmdlet takes the user's identity as the input parameter and will return all normalization rules that are applicable to the user.</span></span>

### <a name="creating-normalization-rules"></a><span data-ttu-id="ec6ad-167">建立正常化規則</span><span class="sxs-lookup"><span data-stu-id="ec6ad-167">Creating normalization rules</span></span>
<span data-ttu-id="ec6ad-168"><a name="createrule"> </a> <a name="regularexpression"> </a></span><span class="sxs-lookup"><span data-stu-id="ec6ad-168"></span></span>

<span data-ttu-id="ec6ad-169">正常化規則使用 .NET Framework 正則運算式，指定伺服器用來將撥號字串轉換成 E. 164 格式的數位相符模式。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-169">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format.</span></span> <span data-ttu-id="ec6ad-170">您可以透過指定相符的正則運算式來建立正常化規則，以及在找到相符專案時要完成的翻譯。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-170">Normalization rules can be created by specifying the regular expression for the match and the translation to be done when a match is found.</span></span> <span data-ttu-id="ec6ad-171">完成後，您可以輸入測試號碼來驗證正常化規則是否如預期的那樣運作。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-171">When you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="ec6ad-172">如需使用 .NET Framework 正則運算式的詳細資料，請參閱[.Net Framework 正則運算式](https://go.microsoft.com/fwlink/p/?linkId=140927)。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-172">For details about using .NET Framework regular expressions, see [.NET Framework Regular Expressions](https://go.microsoft.com/fwlink/p/?linkId=140927).</span></span>

<span data-ttu-id="ec6ad-173">請參閱[建立及管理撥號計畫](create-and-manage-dial-plans.md)，以建立及管理您的租使用者撥號方案的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-173">See [Create and manage dial plans](create-and-manage-dial-plans.md) to create and manage normalization rules for your tenant dial plans.</span></span>

### <a name="sample-normalization-rules"></a><span data-ttu-id="ec6ad-174">範例正常化規則</span><span class="sxs-lookup"><span data-stu-id="ec6ad-174">Sample normalization rules</span></span>

<span data-ttu-id="ec6ad-175">下表顯示已寫入為 .NET Framework 一般運算式的範例正常化規則。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-175">The following table shows sample normalization rules that are written as .NET Framework regular expressions.</span></span> <span data-ttu-id="ec6ad-176">這些範例只是範例，並不代表建立您自己的正常化規則的規範性參考。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-176">The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

 <span data-ttu-id="ec6ad-177">**使用 .NET Framework 一般運算式的正常化規則**<a name="#regularexpression"> </a></span><span class="sxs-lookup"><span data-stu-id="ec6ad-177">**Normalization rules using .NET Framework regular expressions**<a name="#regularexpression"> </a></span></span>

||||||
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ec6ad-178">**規則名稱**</span><span class="sxs-lookup"><span data-stu-id="ec6ad-178">**Rule name**</span></span> <br/> |<span data-ttu-id="ec6ad-179">**描述**</span><span class="sxs-lookup"><span data-stu-id="ec6ad-179">**Description**</span></span> <br/> |<span data-ttu-id="ec6ad-180">**數位模式**</span><span class="sxs-lookup"><span data-stu-id="ec6ad-180">**Number pattern**</span></span> <br/> |<span data-ttu-id="ec6ad-181">**翻譯**</span><span class="sxs-lookup"><span data-stu-id="ec6ad-181">**Translation**</span></span> <br/> |<span data-ttu-id="ec6ad-182">**範例**</span><span class="sxs-lookup"><span data-stu-id="ec6ad-182">**Example**</span></span> <br/> |
|<span data-ttu-id="ec6ad-183">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="ec6ad-183">4digitExtension</span></span>  <br/> |<span data-ttu-id="ec6ad-184">翻譯4位數延伸。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-184">Translates 4-digit extensions.</span></span>  <br/> |<span data-ttu-id="ec6ad-185">^ （\\d{4}） $</span><span class="sxs-lookup"><span data-stu-id="ec6ad-185">^(\\d{4})$</span></span>  <br/> |<span data-ttu-id="ec6ad-186">+ 1425555 $ 1</span><span class="sxs-lookup"><span data-stu-id="ec6ad-186">+1425555$1</span></span>  <br/> |<span data-ttu-id="ec6ad-187">0100已轉譯為 + 14255550100</span><span class="sxs-lookup"><span data-stu-id="ec6ad-187">0100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="ec6ad-188">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="ec6ad-188">5digitExtension</span></span>  <br/> |<span data-ttu-id="ec6ad-189">翻譯5位數的延伸。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-189">Translates 5-digit extensions.</span></span>  <br/> |<span data-ttu-id="ec6ad-190">^ 5 （\\d{4}） $</span><span class="sxs-lookup"><span data-stu-id="ec6ad-190">^5(\\d{4})$</span></span>  <br/> |<span data-ttu-id="ec6ad-191">+ 1425555 $ 1</span><span class="sxs-lookup"><span data-stu-id="ec6ad-191">+1425555$1</span></span>  <br/> |<span data-ttu-id="ec6ad-192">50100已轉譯為 + 14255550100</span><span class="sxs-lookup"><span data-stu-id="ec6ad-192">50100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="ec6ad-193">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="ec6ad-193">7digitcallingRedmond</span></span>  <br/> |<span data-ttu-id="ec6ad-194">將7位數的數位轉譯為雷德式當地電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-194">Translates 7-digit numbers to Redmond local numbers.</span></span>  <br/> |<span data-ttu-id="ec6ad-195">^ （\\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="ec6ad-195">^(\\d{7})$</span></span>  <br/> |<span data-ttu-id="ec6ad-196">+ 1425 $ 1</span><span class="sxs-lookup"><span data-stu-id="ec6ad-196">+1425$1</span></span>  <br/> |<span data-ttu-id="ec6ad-197">5550100已轉譯為 + 14255550100</span><span class="sxs-lookup"><span data-stu-id="ec6ad-197">5550100 is translated to +14255550100</span></span>  <br/>|
|<span data-ttu-id="ec6ad-198">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="ec6ad-198">RedmondOperator</span></span>  <br/> |<span data-ttu-id="ec6ad-199">將0轉換為雷德運算子。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-199">Translates 0 to Redmond Operator.</span></span>  <br/> |<span data-ttu-id="ec6ad-200">^ $0</span><span class="sxs-lookup"><span data-stu-id="ec6ad-200">^0$</span></span>  <br/> |<span data-ttu-id="ec6ad-201">+ 14255550100</span><span class="sxs-lookup"><span data-stu-id="ec6ad-201">+14255550100</span></span>  <br/> |<span data-ttu-id="ec6ad-202">0已轉譯為 + 14255550100</span><span class="sxs-lookup"><span data-stu-id="ec6ad-202">0 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="ec6ad-203">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="ec6ad-203">RedmondSitePrefix</span></span>  <br/> |<span data-ttu-id="ec6ad-204">使用網路上的前置詞（6）和雷德蒙的網站程式碼（222）來轉譯數位。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-204">Translates numbers with on-net prefix (6) and Redmond site code (222).</span></span>  <br/> |<span data-ttu-id="ec6ad-205">^ 6222 （\\d{4}） $</span><span class="sxs-lookup"><span data-stu-id="ec6ad-205">^6222(\\d{4})$</span></span>  <br/> |<span data-ttu-id="ec6ad-206">+ 1425555 $ 1</span><span class="sxs-lookup"><span data-stu-id="ec6ad-206">+1425555$1</span></span>  <br/> |<span data-ttu-id="ec6ad-207">62220100已轉譯為 + 14255550100</span><span class="sxs-lookup"><span data-stu-id="ec6ad-207">62220100 is translated to +14255550100</span></span>  <br/> |
|<span data-ttu-id="ec6ad-208">5digitRange</span><span class="sxs-lookup"><span data-stu-id="ec6ad-208">5digitRange</span></span>  <br/> |<span data-ttu-id="ec6ad-209">翻譯5位數的延伸開始于3-7 （含）之間的數位範圍。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-209">Translates 5-digit extensions starting with the digit range between 3-7 inclusive.</span></span>  <br/> |<span data-ttu-id="ec6ad-210">^ （[3-7]\\d{4}） $</span><span class="sxs-lookup"><span data-stu-id="ec6ad-210">^([3-7]\\d{4})$</span></span>  <br/> |<span data-ttu-id="ec6ad-211">+ 142555 $ 1</span><span class="sxs-lookup"><span data-stu-id="ec6ad-211">+142555$1</span></span> <br/> |<span data-ttu-id="ec6ad-212">54567已轉譯為 + 14255554567</span><span class="sxs-lookup"><span data-stu-id="ec6ad-212">54567 is translated to +14255554567</span></span>  <br/> |
|<span data-ttu-id="ec6ad-213">PrefixAdded</span><span class="sxs-lookup"><span data-stu-id="ec6ad-213">PrefixAdded</span></span>  <br/> |<span data-ttu-id="ec6ad-214">在包含第一個和第三個數字限制的9位數數位的前面加上國家/地區的首碼。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-214">Adds a country prefix in front of a 9 digit number with restrictions on the first and third digits.</span></span>  <br/> |<span data-ttu-id="ec6ad-215">^ （[2-9]\\d\\d [2-9]\\d{6}） $</span><span class="sxs-lookup"><span data-stu-id="ec6ad-215">^([2-9]\\d\\d[2-9]\\d{6})$</span></span>  <br/> |<span data-ttu-id="ec6ad-216">1 $ 1</span><span class="sxs-lookup"><span data-stu-id="ec6ad-216">1$1</span></span>  <br/> |<span data-ttu-id="ec6ad-217">4255554567已轉換為14255554567</span><span class="sxs-lookup"><span data-stu-id="ec6ad-217">4255554567 is translated to 14255554567</span></span>  <br/> |
|<span data-ttu-id="ec6ad-218">NoTranslation</span><span class="sxs-lookup"><span data-stu-id="ec6ad-218">NoTranslation</span></span>  <br/> |<span data-ttu-id="ec6ad-219">符合5位數但沒有翻譯。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-219">Match 5 digits but no translation.</span></span>  <br/> |<span data-ttu-id="ec6ad-220">^ （\\d{5}） $</span><span class="sxs-lookup"><span data-stu-id="ec6ad-220">^(\\d{5})$</span></span>  <br/> |<span data-ttu-id="ec6ad-221">$1</span><span class="sxs-lookup"><span data-stu-id="ec6ad-221">$1</span></span>  <br/> |<span data-ttu-id="ec6ad-222">34567已轉換為34567</span><span class="sxs-lookup"><span data-stu-id="ec6ad-222">34567 is translated to 34567</span></span>  <br/> |

 <span data-ttu-id="ec6ad-223">**以上述正常化規則為基礎的雷蒙德撥號方案。**</span><span class="sxs-lookup"><span data-stu-id="ec6ad-223">**Redmond dial plan based on normalization rules shown above.**</span></span>

 <span data-ttu-id="ec6ad-224">下表說明雷蒙德、華盛頓、英國的範例撥號方案，根據上表所示的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-224">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

| |
|:---------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="ec6ad-225">**雷德蒙撥號方案**</span><span class="sxs-lookup"><span data-stu-id="ec6ad-225">**Redmond dial plan**</span></span> <br/>                                                                                                                              |
| <span data-ttu-id="ec6ad-226">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="ec6ad-226">5digitExtension</span></span> <br/>                                                                                                                                    |
| <span data-ttu-id="ec6ad-227">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="ec6ad-227">7digitcallingRedmond</span></span> <br/>                                                                                                                               |
| <span data-ttu-id="ec6ad-228">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="ec6ad-228">RedmondSitePrefix</span></span> <br/>                                                                                                                                  |
| <span data-ttu-id="ec6ad-229">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="ec6ad-229">RedmondOperator</span></span> <br/>                                                                                                                                    |

> [!NOTE]
> <span data-ttu-id="ec6ad-230">上表所示的正常化規則名稱不會包含空格，但這是選擇的考慮。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-230">The normalization rules names shown in the preceding table don't include spaces, but this is a matter of choice.</span></span> <span data-ttu-id="ec6ad-231">例如，資料表中的第一個名稱可以是 "5 位數副檔名" 或 "5 位數副檔名"，但仍然有效。</span><span class="sxs-lookup"><span data-stu-id="ec6ad-231">The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ec6ad-232">相關主題</span><span class="sxs-lookup"><span data-stu-id="ec6ad-232">Related topics</span></span>

[<span data-ttu-id="ec6ad-233">建立和管理撥號對應表</span><span class="sxs-lookup"><span data-stu-id="ec6ad-233">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)

[<span data-ttu-id="ec6ad-234">通話方案所用的不同類型的電話號碼</span><span class="sxs-lookup"><span data-stu-id="ec6ad-234">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="ec6ad-235">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="ec6ad-235">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="ec6ad-236">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="ec6ad-236">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

<span data-ttu-id="ec6ad-237">[緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="ec6ad-237">[Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
