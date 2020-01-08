---
title: Lync Server 2013：撥號方案與正常化規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d399c49db109a7bac1a1cd3ac430280cb70f665
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="702b0-102">Lync Server 2013 中的撥號方案和正常化規則</span><span class="sxs-lookup"><span data-stu-id="702b0-102">Dial plans and normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="702b0-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="702b0-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="702b0-104">撥號方案是一組命名的正常化規則，可將命名位置、個別使用者或連絡人物件的電話號碼轉換成單一標準（e. 164）格式，以用於手機授權及呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="702b0-104">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span>

<span data-ttu-id="702b0-105">正常化規則定義以各種格式表示的電話號碼如何針對每一個指定的位置、使用者或連絡人物件進行路由。</span><span class="sxs-lookup"><span data-stu-id="702b0-105">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span> <span data-ttu-id="702b0-106">根據撥號位置，以及進行呼叫的人員或連絡人物件，可能會以不同方式來轉譯和翻譯相同的撥號字串。</span><span class="sxs-lookup"><span data-stu-id="702b0-106">The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object making the call.</span></span>

<div>

## <a name="dial-plan-scope"></a><span data-ttu-id="702b0-107">撥號計畫範圍</span><span class="sxs-lookup"><span data-stu-id="702b0-107">Dial Plan Scope</span></span>

<span data-ttu-id="702b0-108">撥號計畫的*範圍*決定您可以套用撥號方案的階層等級。</span><span class="sxs-lookup"><span data-stu-id="702b0-108">A dial plan’s *scope* determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="702b0-109">在 Lync Server 中，使用者可以指派特定的每個使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="702b0-109">In Lync Server, a user can be assigned a specific per-user dial plan.</span></span> <span data-ttu-id="702b0-110">如果未指派使用者撥號方案，則會套用註冊機構池撥號方案。</span><span class="sxs-lookup"><span data-stu-id="702b0-110">If a user dial plan is not assigned, the Registrar pool dial plan is applied.</span></span> <span data-ttu-id="702b0-111">如果沒有註冊機構池撥號方案，則會套用網站撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="702b0-111">If there is no Registrar pool dial plan, the site dial plan is applied.</span></span> <span data-ttu-id="702b0-112">最後，如果沒有任何其他適用于使用者的撥號方案，就會套用全域撥號對應方案。</span><span class="sxs-lookup"><span data-stu-id="702b0-112">Finally, if there is no other dial plan applicable to the user, the global dial plan is applied.</span></span>

<span data-ttu-id="702b0-113">用戶端透過在使用者登入 Lync Server 時所提供的頻帶內提供設定來取得撥號方案範圍層級。</span><span class="sxs-lookup"><span data-stu-id="702b0-113">Clients obtain dial plan scope levels through in-band provisioning settings that are provided when users log on to Lync Server.</span></span> <span data-ttu-id="702b0-114">就像管理員一樣，您可以使用 Lync Server [控制台] 管理及指派撥號方案範圍階層。</span><span class="sxs-lookup"><span data-stu-id="702b0-114">As the administrator, you can manage and assign dial plan scope levels by using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="702b0-115">服務層級的公用交換電話網絡（PSTN）閘道撥號方案會套用至來自特定閘道的撥入通話。</span><span class="sxs-lookup"><span data-stu-id="702b0-115">The service level public switched telephone network (PSTN) gateway dial plan is applied to the incoming calls from a particular gateway.</span></span>



</div>

<span data-ttu-id="702b0-116">撥號規劃範圍階層定義如下：</span><span class="sxs-lookup"><span data-stu-id="702b0-116">Dial plan scope levels are defined as follows:</span></span>

  - <span data-ttu-id="702b0-117">**使用者撥號方案：** 可以指派給個別的使用者、群組或連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="702b0-117">**User dial plan:** Can be assigned to individual users, groups, or contact objects.</span></span> <span data-ttu-id="702b0-118">當您收到來電時，語音應用程式可以查詢每個使用者的撥號方案，並將手機內容設定為 [使用者預設值]。</span><span class="sxs-lookup"><span data-stu-id="702b0-118">Voice applications can look up a per-user dial plan when a call is received with the phone-context set to user-default.</span></span> <span data-ttu-id="702b0-119">出於指派撥號方案的目的，連絡人物件會被視為個別使用者。</span><span class="sxs-lookup"><span data-stu-id="702b0-119">For the purpose of assigning a dial plan, a contact object is treated as an individual user.</span></span>

  - <span data-ttu-id="702b0-120">**池撥號方案：** 可在您拓撲中的任何 PSTN 閘道或註冊機構的服務層級建立。</span><span class="sxs-lookup"><span data-stu-id="702b0-120">**Pool dial plan:** Can be created at the service level for any PSTN gateway or Registrar in your topology.</span></span> <span data-ttu-id="702b0-121">若要定義池子撥號方案，您必須指定要套用撥號方案之特定服務（PSTN 閘道或註冊機構池）。</span><span class="sxs-lookup"><span data-stu-id="702b0-121">To define a pool dial plan, you must specify the particular service (PSTN gateway or Registrar pool) to which the dial plan applies.</span></span>

  - <span data-ttu-id="702b0-122">**網站撥號方案：** 可以針對整個網站建立，除了指派了 [泳池撥號方案] 或 [使用者撥號方案] 的任何使用者、群組或連絡人物件之外。</span><span class="sxs-lookup"><span data-stu-id="702b0-122">**Site dial plan:** Can be created for an entire site, except for any users, groups, or contact objects that are assigned a pool dial plan or user dial plan.</span></span> <span data-ttu-id="702b0-123">若要定義網站撥號計畫，您必須指定要套用撥號計畫的網站。</span><span class="sxs-lookup"><span data-stu-id="702b0-123">To define a site dial plan, you must specify the site to which the dial plan applies.</span></span>

  - <span data-ttu-id="702b0-124">**全域撥號方案：** 與產品一起安裝的預設撥號方案。</span><span class="sxs-lookup"><span data-stu-id="702b0-124">**Global dial plan:** The default dial plan installed with the product.</span></span> <span data-ttu-id="702b0-125">您可以編輯全域撥號方案，但無法將其刪除。</span><span class="sxs-lookup"><span data-stu-id="702b0-125">You can edit the global dial plan, but you cannot delete it.</span></span> <span data-ttu-id="702b0-126">除非您使用更具體的範圍設定並指派撥號方案，否則此撥號方案會套用至您部署中的所有企業語音使用者、群組和連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="702b0-126">This dial plan applies to all Enterprise Voice users, groups, and contact objects in your deployment, unless you configure and assign a dial plan with a more specific scope.</span></span>

</div>

<div>

## <a name="planning-for-dial-plans"></a><span data-ttu-id="702b0-127">規劃撥號方案</span><span class="sxs-lookup"><span data-stu-id="702b0-127">Planning for Dial Plans</span></span>

<span data-ttu-id="702b0-128">若要規劃撥號方案，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="702b0-128">To plan a dial plan, follow these steps:</span></span>

  - <span data-ttu-id="702b0-129">列出貴組織擁有 office 的所有地區設定。</span><span class="sxs-lookup"><span data-stu-id="702b0-129">List all the locales in which your organization has an office.</span></span>
    
    <span data-ttu-id="702b0-130">清單必須是最新的，而且是完整的。</span><span class="sxs-lookup"><span data-stu-id="702b0-130">The list must be up-to-date and complete.</span></span> <span data-ttu-id="702b0-131">隨著公司組織的演變，必須進行修改。</span><span class="sxs-lookup"><span data-stu-id="702b0-131">It will need to be revised as company organization evolves.</span></span> <span data-ttu-id="702b0-132">在有眾多小型分支機搆的大型跨國公司公司中，這可能是一個非常耗時的工作。</span><span class="sxs-lookup"><span data-stu-id="702b0-132">In a large, multinational company with numerous small branch offices, this can be a time-consuming task.</span></span>

  - <span data-ttu-id="702b0-133">找出每個網站的有效數字模式。</span><span class="sxs-lookup"><span data-stu-id="702b0-133">Identify valid number patterns for each site.</span></span>
    
    <span data-ttu-id="702b0-134">規劃撥號方案最耗時的部分是識別每個網站的有效數字模式。</span><span class="sxs-lookup"><span data-stu-id="702b0-134">The most time-consuming part of planning your dial plans is identifying the valid number patterns for each site.</span></span> <span data-ttu-id="702b0-135">在某些情況下，您可以將您針對某個撥號方案所撰寫的正常化規則複製到其他撥號方案，尤其是對應的網站在相同的國家/地區或偶洲中。</span><span class="sxs-lookup"><span data-stu-id="702b0-135">In some cases, you may be able to copy normalization rules that you have written for one dial plan to other dial plans, especially if the corresponding sites are within the same country/region or even continent.</span></span> <span data-ttu-id="702b0-136">在其他情況下，單一撥號方案中的數位變更較小，可能就足以在其他撥號方案中使用它們。</span><span class="sxs-lookup"><span data-stu-id="702b0-136">In other cases, small changes to numbers in one dial plan may be enough to use them in other dial plans.</span></span>

  - <span data-ttu-id="702b0-137">為命名撥號方案開發組織範圍的配置。</span><span class="sxs-lookup"><span data-stu-id="702b0-137">Develop an organization-wide scheme for naming dial plans.</span></span>
    
    <span data-ttu-id="702b0-138">採用標準命名配置，可確保整個組織的一致性，並讓維護與更新變得更容易。</span><span class="sxs-lookup"><span data-stu-id="702b0-138">Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>

  - <span data-ttu-id="702b0-139">決定單一位置是否需要多個撥號方案。</span><span class="sxs-lookup"><span data-stu-id="702b0-139">Decide whether multiple dial plans are required for a single location.</span></span>
    
    <span data-ttu-id="702b0-140">如果您的組織在多個位置維持單一撥號方案，您可能仍需要為從私人分支 exchange （PBX）遷移且需要保留其現有副檔名的企業語音使用者建立一個單獨的撥號方案。</span><span class="sxs-lookup"><span data-stu-id="702b0-140">If your organization maintains a single dial plan across multiple locations, you may still need to create a separate dial plan for Enterprise Voice users who are migrating from a private branch exchange (PBX) and who need to have their existing extensions retained.</span></span>

  - <span data-ttu-id="702b0-141">決定是否需要每個使用者的撥號方案。</span><span class="sxs-lookup"><span data-stu-id="702b0-141">Decide whether per-user dial plans are required.</span></span> <span data-ttu-id="702b0-142">例如，如果您在已向中央網站註冊的分支網站上有使用者，或者如果您擁有在 Survivable 分支裝置上註冊的使用者，您可以考慮使用每個使用者的撥號方案和正常化規則來進行這類使用者的特殊撥號案例.</span><span class="sxs-lookup"><span data-stu-id="702b0-142">For example, if you have users at a branch site who are registered with the central site or if you have users who are registered on a Survivable Branch Appliance, you can consider special dialing scenarios for such users using per-user dial plans and normalization rules.</span></span> <span data-ttu-id="702b0-143">如需詳細資訊，請參閱[Lync Server 2013 的分支網站復原需求](lync-server-2013-branch-site-resiliency-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="702b0-143">For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span></span>

  - <span data-ttu-id="702b0-144">決定撥號方案範圍（如本主題前面所述）。</span><span class="sxs-lookup"><span data-stu-id="702b0-144">Determine dial plan scope (as previously described in this topic).</span></span>

<span data-ttu-id="702b0-145">若要建立撥號方案，請根據需要使用 Lync Server [控制台] 或 [Lync Server 管理命令介面] 來指定下欄欄位中的值。</span><span class="sxs-lookup"><span data-stu-id="702b0-145">To create a dial plan, you specify values in the following fields, as required, by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="name-and-simple-name"></a><span data-ttu-id="702b0-146">名稱與簡單名稱</span><span class="sxs-lookup"><span data-stu-id="702b0-146">Name and Simple Name</span></span>

<span data-ttu-id="702b0-147">針對使用者撥號方案，您應該指定識別撥號計畫將指派之使用者、群組或連絡人物件的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="702b0-147">For user dial plans, you should specify a descriptive name that identifies the users, groups, or contact objects to which the dial plan will be assigned.</span></span> <span data-ttu-id="702b0-148">針對網站撥號方案，[名稱] 欄位會預先填入網站名稱，且無法變更。</span><span class="sxs-lookup"><span data-stu-id="702b0-148">For site dial plans, the Name field is prepopulated with the site name and cannot be changed.</span></span> <span data-ttu-id="702b0-149">針對池撥號方案，[名稱] 欄位會預先填入 PSTN 閘道或前端池的完整功能變數名稱（FQDN），而且無法變更。</span><span class="sxs-lookup"><span data-stu-id="702b0-149">For pool dial plans, the Name field is prepopulated with the PSTN gateway or Front End pool fully qualified domain name (FQDN) and cannot be changed.</span></span>

<span data-ttu-id="702b0-150">使用從撥號方案名稱衍生的字串預先填入撥號計畫*簡單名稱*。</span><span class="sxs-lookup"><span data-stu-id="702b0-150">The dial plan *Simple Name* is prepopulated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="702b0-151">[簡易名稱] 欄位為 [可編輯]，可讓您為撥號方案建立更具描述性的命名慣例。</span><span class="sxs-lookup"><span data-stu-id="702b0-151">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="702b0-152">[*簡易名稱*] 值不能為空白，且必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="702b0-152">The *Simple Name* value cannot be empty and must be unique.</span></span> <span data-ttu-id="702b0-153">最佳做法是為您的整個組織開發一個命名慣例，然後在所有網站和使用者中統一使用這個慣例。</span><span class="sxs-lookup"><span data-stu-id="702b0-153">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

</div>

<div>

## <a name="description"></a><span data-ttu-id="702b0-154">描述</span><span class="sxs-lookup"><span data-stu-id="702b0-154">Description</span></span>

<span data-ttu-id="702b0-155">我們建議您輸入所要套用之對應撥號方案之地理位置的通用、可識別名稱。</span><span class="sxs-lookup"><span data-stu-id="702b0-155">We recommend that you type the common, recognizable name of the geographic location to which the corresponding dial plan applies.</span></span> <span data-ttu-id="702b0-156">例如，如果撥號方案名稱是 London.Contoso.com，則建議使用倫敦的描述。</span><span class="sxs-lookup"><span data-stu-id="702b0-156">For example, if the dial plan name is London.Contoso.com, the recommended description would be London.</span></span>

</div>

<div>

## <a name="dial-in-conferencing-region"></a><span data-ttu-id="702b0-157">電話撥入式會議區域</span><span class="sxs-lookup"><span data-stu-id="702b0-157">Dial-in Conferencing Region</span></span>

<span data-ttu-id="702b0-158">如果您要部署電話撥入式會議，您將需要指定電話撥入式會議區域，以將電話撥入式會議存取號碼與撥號方案建立關聯。</span><span class="sxs-lookup"><span data-stu-id="702b0-158">If you are deploying dial-in conferencing, you will need to specify a dial-in conferencing region to associate dial-in conferencing access numbers with a dial plan.</span></span>

</div>

<div>

## <a name="external-access-prefix"></a><span data-ttu-id="702b0-159">外部存取首碼</span><span class="sxs-lookup"><span data-stu-id="702b0-159">External Access Prefix</span></span>

<span data-ttu-id="702b0-160">如果使用者需要撥一或多個額外的前導數位（\#例如\*，9）來取得外部線路，您可以指定最多四個字元（，和0-9）的外部存取前置詞。</span><span class="sxs-lookup"><span data-stu-id="702b0-160">You can specify an external access prefix of up to four characters (\#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="702b0-161">如果您指定外部存取前置詞，就不需要建立額外的正常化規則來容納該前置詞。</span><span class="sxs-lookup"><span data-stu-id="702b0-161">If you specify an external access prefix, you do not need to create an additional normalization rule to accommodate the prefix.</span></span>



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a><span data-ttu-id="702b0-162">正常化規則</span><span class="sxs-lookup"><span data-stu-id="702b0-162">Normalization Rules</span></span>

<span data-ttu-id="702b0-163">正常化規則定義以各種格式表示的電話號碼如何路由至指定位置。</span><span class="sxs-lookup"><span data-stu-id="702b0-163">Normalization rules define how phone numbers expressed in various formats are to be routed for the named location.</span></span> <span data-ttu-id="702b0-164">根據撥號的地區設定，相同的數位字串可能會以不同的方式加以轉譯和翻譯。</span><span class="sxs-lookup"><span data-stu-id="702b0-164">The same number string may be interpreted and translated differently, depending on the locale from which it is dialed.</span></span> <span data-ttu-id="702b0-165">需要進行呼叫路由的正常化規則，因為使用者可以在連絡人清單中輸入電話號碼時，使用不同的格式。</span><span class="sxs-lookup"><span data-stu-id="702b0-165">Normalization rules are necessary for call routing because users can, and do, use various formats when entering phone numbers in their Contacts lists.</span></span>

<span data-ttu-id="702b0-166">正常化使用者提供的電話號碼提供一致的格式，可協助進行下列工作：</span><span class="sxs-lookup"><span data-stu-id="702b0-166">Normalizing user-supplied phone numbers provides a consistent format that facilitates the following tasks:</span></span>

  - <span data-ttu-id="702b0-167">將撥入號碼與預期收件者的 SIP URI 相符。</span><span class="sxs-lookup"><span data-stu-id="702b0-167">Match a dialed number to the intended recipient’s SIP-URI.</span></span>

  - <span data-ttu-id="702b0-168">將撥號授權規則套用至呼叫方。</span><span class="sxs-lookup"><span data-stu-id="702b0-168">Apply dialing authorization rules to the calling party.</span></span>

<span data-ttu-id="702b0-169">下列數位欄位就是您的正常化規則可能需要考慮的專案：</span><span class="sxs-lookup"><span data-stu-id="702b0-169">The following number fields are among those that your normalization rules may need to account for:</span></span>

  - <span data-ttu-id="702b0-170">撥號方案</span><span class="sxs-lookup"><span data-stu-id="702b0-170">Dial plan</span></span>

  - <span data-ttu-id="702b0-171">國家/地區代碼</span><span class="sxs-lookup"><span data-stu-id="702b0-171">Country code</span></span>

  - <span data-ttu-id="702b0-172">區功能變數代碼</span><span class="sxs-lookup"><span data-stu-id="702b0-172">Area code</span></span>

  - <span data-ttu-id="702b0-173">延伸長度</span><span class="sxs-lookup"><span data-stu-id="702b0-173">Length of extension</span></span>

  - <span data-ttu-id="702b0-174">網站首碼</span><span class="sxs-lookup"><span data-stu-id="702b0-174">Site prefix</span></span>

<div>

## <a name="creating-normalization-rules"></a><span data-ttu-id="702b0-175">建立正常化規則</span><span class="sxs-lookup"><span data-stu-id="702b0-175">Creating Normalization Rules</span></span>

<span data-ttu-id="702b0-176">正常化規則使用 .NET Framework 正則運算式指定數位匹配模式，伺服器將撥號字串轉換為 E. 164 格式，以執行 [反向數位查閱] 的目的。</span><span class="sxs-lookup"><span data-stu-id="702b0-176">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format for the purpose of performing reverse number lookup.</span></span> <span data-ttu-id="702b0-177">您可以在 Lync Server 控制台中建立正常化規則，方法是手動輸入運算式，或輸入要相符的撥號字串的起始位數和長度，讓 Lync Server 控制台產生對應的正則運算式。</span><span class="sxs-lookup"><span data-stu-id="702b0-177">You create normalization rules in the Lync Server Control Panel either by entering the expressions manually, or by entering the starting digits and the length of the dial strings to be matched and letting the Lync Server Control Panel generate the corresponding regular expression for you.</span></span> <span data-ttu-id="702b0-178">不論是哪一種方式，當您完成時，您可以輸入測試號碼來驗證正常化規則是否如預期的那樣運作。</span><span class="sxs-lookup"><span data-stu-id="702b0-178">Either way, when you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="702b0-179">如需使用 .NET Framework 正則運算式的詳細資料，請參閱 ".NET Framework [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)正則運算式"。</span><span class="sxs-lookup"><span data-stu-id="702b0-179">For details about using .NET Framework regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a><span data-ttu-id="702b0-180">範例正常化規則</span><span class="sxs-lookup"><span data-stu-id="702b0-180">Sample Normalization Rules</span></span>

<span data-ttu-id="702b0-181">下表顯示已寫入為 .NET Framework 一般運算式的範例正常化規則。</span><span class="sxs-lookup"><span data-stu-id="702b0-181">The following table shows sample normalization rules that are written as .NET Framework regular expressions.</span></span> <span data-ttu-id="702b0-182">這些範例只是範例，並不代表建立您自己的正常化規則的規範性參考。</span><span class="sxs-lookup"><span data-stu-id="702b0-182">The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a><span data-ttu-id="702b0-183">資料表 1. 使用 .NET Framework 一般運算式的正常化規則</span><span class="sxs-lookup"><span data-stu-id="702b0-183">Table 1.Normalization Rules Using .NET Framework Regular Expressions</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="702b0-184">規則名稱</span><span class="sxs-lookup"><span data-stu-id="702b0-184">Rule name</span></span></th>
<th><span data-ttu-id="702b0-185">描述</span><span class="sxs-lookup"><span data-stu-id="702b0-185">Description</span></span></th>
<th><span data-ttu-id="702b0-186">數位模式</span><span class="sxs-lookup"><span data-stu-id="702b0-186">Number pattern</span></span></th>
<th><span data-ttu-id="702b0-187">翻譯</span><span class="sxs-lookup"><span data-stu-id="702b0-187">Translation</span></span></th>
<th><span data-ttu-id="702b0-188">範例</span><span class="sxs-lookup"><span data-stu-id="702b0-188">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="702b0-189">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="702b0-189">4digitExtension</span></span></p></td>
<td><p><span data-ttu-id="702b0-190">翻譯4位數延伸</span><span class="sxs-lookup"><span data-stu-id="702b0-190">Translates 4-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="702b0-191">^ （\d{4}） $</span><span class="sxs-lookup"><span data-stu-id="702b0-191">^(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="702b0-192">+ 1425555 $ 1</span><span class="sxs-lookup"><span data-stu-id="702b0-192">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="702b0-193">0100已轉譯為 + 14255550100</span><span class="sxs-lookup"><span data-stu-id="702b0-193">0100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="702b0-194">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="702b0-194">5digitExtension</span></span></p></td>
<td><p><span data-ttu-id="702b0-195">翻譯5位數延伸</span><span class="sxs-lookup"><span data-stu-id="702b0-195">Translates 5-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="702b0-196">^ 5 （\d{4}） $</span><span class="sxs-lookup"><span data-stu-id="702b0-196">^5(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="702b0-197">+ 1425555 $ 1</span><span class="sxs-lookup"><span data-stu-id="702b0-197">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="702b0-198">50100已轉譯為 + 14255550100</span><span class="sxs-lookup"><span data-stu-id="702b0-198">50100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="702b0-199">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="702b0-199">7digitcallingRedmond</span></span></p></td>
<td><p><span data-ttu-id="702b0-200">將7位數的數位轉換成雷德式當地電話號碼</span><span class="sxs-lookup"><span data-stu-id="702b0-200">Translates 7-digit numbers to Redmond local numbers</span></span></p></td>
<td><p><span data-ttu-id="702b0-201">^ （\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="702b0-201">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="702b0-202">+ 1425 $ 1</span><span class="sxs-lookup"><span data-stu-id="702b0-202">+1425$1</span></span></p></td>
<td><p><span data-ttu-id="702b0-203">5550100已轉譯為 + 14255550100</span><span class="sxs-lookup"><span data-stu-id="702b0-203">5550100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="702b0-204">7digitcallingDallas</span><span class="sxs-lookup"><span data-stu-id="702b0-204">7digitcallingDallas</span></span></p></td>
<td><p><span data-ttu-id="702b0-205">將7位數的數位轉換成達拉斯當地數位</span><span class="sxs-lookup"><span data-stu-id="702b0-205">Translates 7-digit numbers to Dallas local numbers</span></span></p></td>
<td><p><span data-ttu-id="702b0-206">^ （\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="702b0-206">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="702b0-207">+ 1972 $ 1</span><span class="sxs-lookup"><span data-stu-id="702b0-207">+1972$1</span></span></p></td>
<td><p><span data-ttu-id="702b0-208">5550100已轉譯為 + 19725550100</span><span class="sxs-lookup"><span data-stu-id="702b0-208">5550100 is translated to +19725550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="702b0-209">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="702b0-209">10digitcallingUS</span></span></p></td>
<td><p><span data-ttu-id="702b0-210">在美國翻譯10位數的數位</span><span class="sxs-lookup"><span data-stu-id="702b0-210">Translates 10-digit numbers in the United States</span></span></p></td>
<td><p><span data-ttu-id="702b0-211">^ （\d{10}） $</span><span class="sxs-lookup"><span data-stu-id="702b0-211">^(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="702b0-212">+ 1 $ 1</span><span class="sxs-lookup"><span data-stu-id="702b0-212">+1$1</span></span></p></td>
<td><p><span data-ttu-id="702b0-213">2065550100已轉譯為 + 12065550100</span><span class="sxs-lookup"><span data-stu-id="702b0-213">2065550100 is translated to +12065550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="702b0-214">LDCallingUS</span><span class="sxs-lookup"><span data-stu-id="702b0-214">LDCallingUS</span></span></p></td>
<td><p><span data-ttu-id="702b0-215">在美國轉換含長途的數位</span><span class="sxs-lookup"><span data-stu-id="702b0-215">Translates numbers with long distance prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="702b0-216">^ 1 （\d{10}） $</span><span class="sxs-lookup"><span data-stu-id="702b0-216">^1(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="702b0-217">+ $1</span><span class="sxs-lookup"><span data-stu-id="702b0-217">+$1</span></span></p></td>
<td><p><span data-ttu-id="702b0-218">12145550100已轉譯為 + 2145550100</span><span class="sxs-lookup"><span data-stu-id="702b0-218">12145550100 is translated to +2145550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="702b0-219">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="702b0-219">IntlCallingUS</span></span></p></td>
<td><p><span data-ttu-id="702b0-220">在美國翻譯含國際首碼的數位</span><span class="sxs-lookup"><span data-stu-id="702b0-220">Translates numbers with international prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="702b0-221">^ 011 （\d \*） $</span><span class="sxs-lookup"><span data-stu-id="702b0-221">^011(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="702b0-222">+ $1</span><span class="sxs-lookup"><span data-stu-id="702b0-222">+$1</span></span></p></td>
<td><p><span data-ttu-id="702b0-223">01191445550100已轉譯為 + 91445550100</span><span class="sxs-lookup"><span data-stu-id="702b0-223">01191445550100 is translated to +91445550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="702b0-224">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="702b0-224">RedmondOperator</span></span></p></td>
<td><p><span data-ttu-id="702b0-225">轉譯0到雷德蒙運算子</span><span class="sxs-lookup"><span data-stu-id="702b0-225">Translates 0 to Redmond Operator</span></span></p></td>
<td><p><span data-ttu-id="702b0-226">^ $0</span><span class="sxs-lookup"><span data-stu-id="702b0-226">^0$</span></span></p></td>
<td><p><span data-ttu-id="702b0-227">+ 14255550100</span><span class="sxs-lookup"><span data-stu-id="702b0-227">+14255550100</span></span></p></td>
<td><p><span data-ttu-id="702b0-228">0已轉譯為 + 14255550100</span><span class="sxs-lookup"><span data-stu-id="702b0-228">0 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="702b0-229">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="702b0-229">RedmondSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="702b0-230">使用網路上的前置詞（6）和雷德蒙的網站程式碼（222）轉譯數位</span><span class="sxs-lookup"><span data-stu-id="702b0-230">Translates numbers with on-net prefix (6) and Redmond site code (222)</span></span></p></td>
<td><p><span data-ttu-id="702b0-231">^ 6222 （\d{4}） $</span><span class="sxs-lookup"><span data-stu-id="702b0-231">^6222(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="702b0-232">+ 1425555 $ 1</span><span class="sxs-lookup"><span data-stu-id="702b0-232">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="702b0-233">62220100已轉譯為 + 14255550100</span><span class="sxs-lookup"><span data-stu-id="702b0-233">62220100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="702b0-234">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="702b0-234">NYSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="702b0-235">使用網路上的前置詞（6）和 NY 網站代碼（333）轉譯數位</span><span class="sxs-lookup"><span data-stu-id="702b0-235">Translates numbers with on-net prefix (6) and NY site code (333)</span></span></p></td>
<td><p><span data-ttu-id="702b0-236">^ 6333 （\d{4}） $</span><span class="sxs-lookup"><span data-stu-id="702b0-236">^6333(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="702b0-237">+ 1202555 $ 1</span><span class="sxs-lookup"><span data-stu-id="702b0-237">+1202555$1</span></span></p></td>
<td><p><span data-ttu-id="702b0-238">63330100已轉譯為 + 12025550100</span><span class="sxs-lookup"><span data-stu-id="702b0-238">63330100 is translated to +12025550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="702b0-239">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="702b0-239">DallasSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="702b0-240">使用網路上的前置詞（6）和達拉斯網站程式碼（444）轉譯數位</span><span class="sxs-lookup"><span data-stu-id="702b0-240">Translates numbers with on-net prefix (6) and Dallas site code (444)</span></span></p></td>
<td><p><span data-ttu-id="702b0-241">^ 6444 （\d{4}） $</span><span class="sxs-lookup"><span data-stu-id="702b0-241">^6444(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="702b0-242">+ 1972555 $ 1</span><span class="sxs-lookup"><span data-stu-id="702b0-242">+1972555$1</span></span></p></td>
<td><p><span data-ttu-id="702b0-243">64440100已轉譯為 + 19725550100</span><span class="sxs-lookup"><span data-stu-id="702b0-243">64440100 is translated to +19725550100</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="702b0-244">下表說明雷蒙德、華盛頓、英國的範例撥號方案，根據上表所示的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="702b0-244">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a><span data-ttu-id="702b0-245">表格2。</span><span class="sxs-lookup"><span data-stu-id="702b0-245">Table 2.</span></span> <span data-ttu-id="702b0-246">以資料表1所示之正常化規則為基礎的雷德蒙式撥號方案</span><span class="sxs-lookup"><span data-stu-id="702b0-246">Redmond Dial Plan Based on Normalization Rules Shown in Table 1</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="702b0-247">雷德 forestFQDN</span><span class="sxs-lookup"><span data-stu-id="702b0-247">Redmond.forestFQDN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="702b0-248">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="702b0-248">5digitExtension</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="702b0-249">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="702b0-249">7digitcallingRedmond</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="702b0-250">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="702b0-250">10digitcallingUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="702b0-251">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="702b0-251">IntlCallingUS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="702b0-252">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="702b0-252">RedmondSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="702b0-253">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="702b0-253">NYSitePrefix</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="702b0-254">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="702b0-254">DallasSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="702b0-255">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="702b0-255">RedmondOperator</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="702b0-256">上表中顯示的正常化規則名稱不會包含空格，但這是選擇的考慮。</span><span class="sxs-lookup"><span data-stu-id="702b0-256">The normalization rules names shown in the preceding table do not include spaces, but this is a matter of choice.</span></span> <span data-ttu-id="702b0-257">例如，資料表中的第一個名稱可以是 "5 位數副檔名" 或 "5 位數副檔名"，但仍然有效。</span><span class="sxs-lookup"><span data-stu-id="702b0-257">The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

