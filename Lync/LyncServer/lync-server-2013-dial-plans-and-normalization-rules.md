---
title: Lync Server 2013：撥號對應表和正常化規則
description: Lync Server 2013：撥號對應表和正常化規則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0341d0c5267a2272ff45bd93408b2bd14f0ceeaa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559739"
---
# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="0e624-103">Lync Server 2013 的撥號對應表和正常化規則</span><span class="sxs-lookup"><span data-stu-id="0e624-103">Dial plans and normalization rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e624-104">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0e624-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0e624-105">撥號對應表是一個具名的正規化規則集，可將具名位置、個別使用者或連絡人物件的電話號碼轉譯成單一標準 (E.164) 格式，以便進行電話授權和電話路由傳送。</span><span class="sxs-lookup"><span data-stu-id="0e624-105">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span>

<span data-ttu-id="0e624-106">正規化規則會針對每個指定位置、使用者或連絡人物件，定義要如何路由傳送以各種格式表達的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0e624-106">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span> <span data-ttu-id="0e624-107">視其撥號位置和進行通話的人員或連絡人物件而定，相同的撥號字串可能會以不同的方式轉譯和轉譯。</span><span class="sxs-lookup"><span data-stu-id="0e624-107">The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object making the call.</span></span>

<div>

## <a name="dial-plan-scope"></a><span data-ttu-id="0e624-108">撥號對應表範圍</span><span class="sxs-lookup"><span data-stu-id="0e624-108">Dial Plan Scope</span></span>

<span data-ttu-id="0e624-109">撥號對應表的 *範圍* 決定可以套用撥號對應表的階層層級。</span><span class="sxs-lookup"><span data-stu-id="0e624-109">A dial plan’s *scope* determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="0e624-110">在 Lync Server 中，使用者可以指派特定的每一使用者撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="0e624-110">In Lync Server, a user can be assigned a specific per-user dial plan.</span></span> <span data-ttu-id="0e624-111">若未指派使用者撥號對應表，則會套用註冊機構集區撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="0e624-111">If a user dial plan is not assigned, the Registrar pool dial plan is applied.</span></span> <span data-ttu-id="0e624-112">如果沒有註冊機構集區撥號對應表，則會套用網站撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="0e624-112">If there is no Registrar pool dial plan, the site dial plan is applied.</span></span> <span data-ttu-id="0e624-113">最後，如果沒有其他適用于使用者的撥號對應表，則會套用全域撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="0e624-113">Finally, if there is no other dial plan applicable to the user, the global dial plan is applied.</span></span>

<span data-ttu-id="0e624-114">用戶端透過在使用者登入 Lync Server 時所提供的頻帶內布建設定，取得撥號對應表的範圍層級。</span><span class="sxs-lookup"><span data-stu-id="0e624-114">Clients obtain dial plan scope levels through in-band provisioning settings that are provided when users log on to Lync Server.</span></span> <span data-ttu-id="0e624-115">身為系統管理員，您可以使用 Lync Server 控制台管理及指派撥號對應表的範圍層級。</span><span class="sxs-lookup"><span data-stu-id="0e624-115">As the administrator, you can manage and assign dial plan scope levels by using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0e624-116">服務層級公用交換電話網路 (PSTN) 閘道撥號對應表會套用至特定閘道上的來電。</span><span class="sxs-lookup"><span data-stu-id="0e624-116">The service level public switched telephone network (PSTN) gateway dial plan is applied to the incoming calls from a particular gateway.</span></span>



</div>

<span data-ttu-id="0e624-117">撥號對應表範圍層級的定義如下：</span><span class="sxs-lookup"><span data-stu-id="0e624-117">Dial plan scope levels are defined as follows:</span></span>

  - <span data-ttu-id="0e624-118">**使用者撥號** 對應表：可以指派給個別的使用者、群組或連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="0e624-118">**User dial plan:** Can be assigned to individual users, groups, or contact objects.</span></span> <span data-ttu-id="0e624-119">當接到電話內容設定為使用者預設值時，語音應用程式可以查閱個別使用者撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="0e624-119">Voice applications can look up a per-user dial plan when a call is received with the phone-context set to user-default.</span></span> <span data-ttu-id="0e624-120">出於指派撥號對應表的目的，連絡人物件會被視為個別使用者。</span><span class="sxs-lookup"><span data-stu-id="0e624-120">For the purpose of assigning a dial plan, a contact object is treated as an individual user.</span></span>

  - <span data-ttu-id="0e624-121">**集區撥號** 對應表：可在拓撲中的任何 PSTN 閘道或註冊機構的服務層級建立。</span><span class="sxs-lookup"><span data-stu-id="0e624-121">**Pool dial plan:** Can be created at the service level for any PSTN gateway or Registrar in your topology.</span></span> <span data-ttu-id="0e624-122">若要定義集區撥號對應表，您必須指定撥號對應表所套用的特定服務 (PSTN 閘道或註冊機集區) 。</span><span class="sxs-lookup"><span data-stu-id="0e624-122">To define a pool dial plan, you must specify the particular service (PSTN gateway or Registrar pool) to which the dial plan applies.</span></span>

  - <span data-ttu-id="0e624-123">**網站撥號** 對應表：可以針對整個網站建立，但對於指派集區撥號對應表或使用者撥號對應表的任何使用者、群組或連絡人物件除外。</span><span class="sxs-lookup"><span data-stu-id="0e624-123">**Site dial plan:** Can be created for an entire site, except for any users, groups, or contact objects that are assigned a pool dial plan or user dial plan.</span></span> <span data-ttu-id="0e624-124">若要定義網站撥號對應表，您必須指定要套用撥號對應表的網站。</span><span class="sxs-lookup"><span data-stu-id="0e624-124">To define a site dial plan, you must specify the site to which the dial plan applies.</span></span>

  - <span data-ttu-id="0e624-125">**全域撥號** 對應表：隨產品安裝的預設撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="0e624-125">**Global dial plan:** The default dial plan installed with the product.</span></span> <span data-ttu-id="0e624-126">您可以編輯全域撥號對應表，但無法加以刪除。</span><span class="sxs-lookup"><span data-stu-id="0e624-126">You can edit the global dial plan, but you cannot delete it.</span></span> <span data-ttu-id="0e624-127">此撥號對應表適用于部署中的所有 Enterprise Voice 使用者、群組和連絡人物件，除非您設定和指派具有更特定範圍的撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="0e624-127">This dial plan applies to all Enterprise Voice users, groups, and contact objects in your deployment, unless you configure and assign a dial plan with a more specific scope.</span></span>

</div>

<div>

## <a name="planning-for-dial-plans"></a><span data-ttu-id="0e624-128">規劃撥號對應表</span><span class="sxs-lookup"><span data-stu-id="0e624-128">Planning for Dial Plans</span></span>

<span data-ttu-id="0e624-129">若要規劃撥號對應表，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="0e624-129">To plan a dial plan, follow these steps:</span></span>

  - <span data-ttu-id="0e624-130">列出您的組織擁有 office 的所有地區設定。</span><span class="sxs-lookup"><span data-stu-id="0e624-130">List all the locales in which your organization has an office.</span></span>
    
    <span data-ttu-id="0e624-131">清單必須是最新和完整的。</span><span class="sxs-lookup"><span data-stu-id="0e624-131">The list must be up-to-date and complete.</span></span> <span data-ttu-id="0e624-132">當公司組織演變時，將需要進行修訂。</span><span class="sxs-lookup"><span data-stu-id="0e624-132">It will need to be revised as company organization evolves.</span></span> <span data-ttu-id="0e624-133">在具有眾多小型分公司的大型跨國公司中，這可能是一項耗時的工作。</span><span class="sxs-lookup"><span data-stu-id="0e624-133">In a large, multinational company with numerous small branch offices, this can be a time-consuming task.</span></span>

  - <span data-ttu-id="0e624-134">識別每個網站的有效號碼模式。</span><span class="sxs-lookup"><span data-stu-id="0e624-134">Identify valid number patterns for each site.</span></span>
    
    <span data-ttu-id="0e624-135">規劃撥號對應表的最費時的部分是識別每個網站的有效號碼模式。</span><span class="sxs-lookup"><span data-stu-id="0e624-135">The most time-consuming part of planning your dial plans is identifying the valid number patterns for each site.</span></span> <span data-ttu-id="0e624-136">在某些情況下，您可以將您為一個撥號對應表編寫的正規化規則複製到其他撥號對應表，尤其是在對應的網站位於相同的國家/地區或大陸時。</span><span class="sxs-lookup"><span data-stu-id="0e624-136">In some cases, you may be able to copy normalization rules that you have written for one dial plan to other dial plans, especially if the corresponding sites are within the same country/region or even continent.</span></span> <span data-ttu-id="0e624-137">在其他情況下，對一個撥號對應表中的數位所做的小變更，可能足以在其他撥號對應表中使用它們。</span><span class="sxs-lookup"><span data-stu-id="0e624-137">In other cases, small changes to numbers in one dial plan may be enough to use them in other dial plans.</span></span>

  - <span data-ttu-id="0e624-138">開發用於命名撥號對應表的全組織模式。</span><span class="sxs-lookup"><span data-stu-id="0e624-138">Develop an organization-wide scheme for naming dial plans.</span></span>
    
    <span data-ttu-id="0e624-139">採用標準命名架構可確保整個組織的一致性，並使維護和更新變得更容易。</span><span class="sxs-lookup"><span data-stu-id="0e624-139">Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>

  - <span data-ttu-id="0e624-140">決定單一位置是否需要多個撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="0e624-140">Decide whether multiple dial plans are required for a single location.</span></span>
    
    <span data-ttu-id="0e624-141">如果您的組織跨多個位置維護單一撥號對應表，您可能仍然需要針對從專用交換機 (PBX) 進行遷移的 Enterprise Voice 使用者建立個別的撥號對應表，且必須保留現有的副檔名。</span><span class="sxs-lookup"><span data-stu-id="0e624-141">If your organization maintains a single dial plan across multiple locations, you may still need to create a separate dial plan for Enterprise Voice users who are migrating from a private branch exchange (PBX) and who need to have their existing extensions retained.</span></span>

  - <span data-ttu-id="0e624-142">決定是否需要每個使用者的撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="0e624-142">Decide whether per-user dial plans are required.</span></span> <span data-ttu-id="0e624-143">例如，如果您在分支網站上有使用者向中央網站註冊，或是您有在 Survivable Branch 裝置上註冊的使用者，則可以針對使用個別使用者撥號對應表及正規化規則的使用者考慮特殊的撥號案例。</span><span class="sxs-lookup"><span data-stu-id="0e624-143">For example, if you have users at a branch site who are registered with the central site or if you have users who are registered on a Survivable Branch Appliance, you can consider special dialing scenarios for such users using per-user dial plans and normalization rules.</span></span> <span data-ttu-id="0e624-144">如需詳細資訊，請參閱 [Lync Server 2013 的分支網站恢復需求](lync-server-2013-branch-site-resiliency-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0e624-144">For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span></span>

  - <span data-ttu-id="0e624-145">依照本主題先前所述，確定撥號對應表範圍 () 。</span><span class="sxs-lookup"><span data-stu-id="0e624-145">Determine dial plan scope (as previously described in this topic).</span></span>

<span data-ttu-id="0e624-146">若要建立撥號對應表，您可以在必要時使用 Lync Server 控制台或 Lync Server 管理命令介面來指定下欄欄位中的值。</span><span class="sxs-lookup"><span data-stu-id="0e624-146">To create a dial plan, you specify values in the following fields, as required, by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="name-and-simple-name"></a><span data-ttu-id="0e624-147">名稱和簡易名稱</span><span class="sxs-lookup"><span data-stu-id="0e624-147">Name and Simple Name</span></span>

<span data-ttu-id="0e624-148">針對使用者撥號對應表，您應該指定識別撥號對應表所指派之使用者、群組或連絡人物件的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="0e624-148">For user dial plans, you should specify a descriptive name that identifies the users, groups, or contact objects to which the dial plan will be assigned.</span></span> <span data-ttu-id="0e624-149">針對網站撥號對應表，[名稱] 欄位會預先填入網站名稱，而且無法變更。</span><span class="sxs-lookup"><span data-stu-id="0e624-149">For site dial plans, the Name field is prepopulated with the site name and cannot be changed.</span></span> <span data-ttu-id="0e624-150">針對集區撥號對應表，[名稱] 欄位會預先填入 PSTN 閘道或前端集區完整功能變數名稱 (FQDN) 且無法變更。</span><span class="sxs-lookup"><span data-stu-id="0e624-150">For pool dial plans, the Name field is prepopulated with the PSTN gateway or Front End pool fully qualified domain name (FQDN) and cannot be changed.</span></span>

<span data-ttu-id="0e624-151">撥號對應表的 *簡易名稱* 會預先填入一個衍生自撥號對應表名稱的字串。</span><span class="sxs-lookup"><span data-stu-id="0e624-151">The dial plan *Simple Name* is prepopulated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="0e624-152">[簡易名稱] 欄位是可編輯的，可讓您為撥號對應表建立更具描述性的命名慣例。</span><span class="sxs-lookup"><span data-stu-id="0e624-152">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="0e624-153">[ *簡易名稱* ] 值不能是空的，而且必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="0e624-153">The *Simple Name* value cannot be empty and must be unique.</span></span> <span data-ttu-id="0e624-154">最佳作法是針對整個組織制定命名慣例，然後在所有網站和使用者中統一使用此慣例。</span><span class="sxs-lookup"><span data-stu-id="0e624-154">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

</div>

<div>

## <a name="description"></a><span data-ttu-id="0e624-155">描述</span><span class="sxs-lookup"><span data-stu-id="0e624-155">Description</span></span>

<span data-ttu-id="0e624-156">建議您輸入適用于對應撥號對應表之地理位置的一般識別名稱。</span><span class="sxs-lookup"><span data-stu-id="0e624-156">We recommend that you type the common, recognizable name of the geographic location to which the corresponding dial plan applies.</span></span> <span data-ttu-id="0e624-157">例如，如果撥號對應表名稱是 London.Contoso.com，則建議的描述將是倫敦。</span><span class="sxs-lookup"><span data-stu-id="0e624-157">For example, if the dial plan name is London.Contoso.com, the recommended description would be London.</span></span>

</div>

<div>

## <a name="dial-in-conferencing-region"></a><span data-ttu-id="0e624-158">電話撥入式會議區域</span><span class="sxs-lookup"><span data-stu-id="0e624-158">Dial-in Conferencing Region</span></span>

<span data-ttu-id="0e624-159">若要部署電話撥入式會議，您必須指定電話撥入式會議區域，以將電話撥入式會議存取號碼與撥號對應表產生關聯。</span><span class="sxs-lookup"><span data-stu-id="0e624-159">If you are deploying dial-in conferencing, you will need to specify a dial-in conferencing region to associate dial-in conferencing access numbers with a dial plan.</span></span>

</div>

<div>

## <a name="external-access-prefix"></a><span data-ttu-id="0e624-160">外部存取前置詞</span><span class="sxs-lookup"><span data-stu-id="0e624-160">External Access Prefix</span></span>

<span data-ttu-id="0e624-161">您可以指定最多四個字元的外部存取前置詞 (\# 、 \* 和 0-9) 如果使用者需要撥打一或多個其他前導數位 (例如，9) 以取得外部行。</span><span class="sxs-lookup"><span data-stu-id="0e624-161">You can specify an external access prefix of up to four characters (\#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0e624-162">如果您指定了外部存取前置詞，則不需要建立額外的正規化規則來容納前置詞。</span><span class="sxs-lookup"><span data-stu-id="0e624-162">If you specify an external access prefix, you do not need to create an additional normalization rule to accommodate the prefix.</span></span>



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a><span data-ttu-id="0e624-163">正規化規則</span><span class="sxs-lookup"><span data-stu-id="0e624-163">Normalization Rules</span></span>

<span data-ttu-id="0e624-164">正規化規則會定義以不同格式表示的電話號碼如何路由傳送至指定的位置。</span><span class="sxs-lookup"><span data-stu-id="0e624-164">Normalization rules define how phone numbers expressed in various formats are to be routed for the named location.</span></span> <span data-ttu-id="0e624-165">您可以根據撥號的地區設定，以不同方式轉譯和轉譯相同的數位字串。</span><span class="sxs-lookup"><span data-stu-id="0e624-165">The same number string may be interpreted and translated differently, depending on the locale from which it is dialed.</span></span> <span data-ttu-id="0e624-166">您可以使用正規化規則進行呼叫路由，因為使用者在其連絡人清單中輸入電話號碼時可以使用各種格式。</span><span class="sxs-lookup"><span data-stu-id="0e624-166">Normalization rules are necessary for call routing because users can, and do, use various formats when entering phone numbers in their Contacts lists.</span></span>

<span data-ttu-id="0e624-167">將使用者提供的電話號碼正常化，可提供一致的格式，可協助下列工作：</span><span class="sxs-lookup"><span data-stu-id="0e624-167">Normalizing user-supplied phone numbers provides a consistent format that facilitates the following tasks:</span></span>

  - <span data-ttu-id="0e624-168">將撥打的號碼與預定收件者的 SIP-URI 相符。</span><span class="sxs-lookup"><span data-stu-id="0e624-168">Match a dialed number to the intended recipient’s SIP-URI.</span></span>

  - <span data-ttu-id="0e624-169">將撥號授權規則套用至呼叫方。</span><span class="sxs-lookup"><span data-stu-id="0e624-169">Apply dialing authorization rules to the calling party.</span></span>

<span data-ttu-id="0e624-170">下列號碼欄位是您的正規化規則可能需要考慮的欄位：</span><span class="sxs-lookup"><span data-stu-id="0e624-170">The following number fields are among those that your normalization rules may need to account for:</span></span>

  - <span data-ttu-id="0e624-171">撥號對應表</span><span class="sxs-lookup"><span data-stu-id="0e624-171">Dial plan</span></span>

  - <span data-ttu-id="0e624-172">國碼</span><span class="sxs-lookup"><span data-stu-id="0e624-172">Country code</span></span>

  - <span data-ttu-id="0e624-173">區功能變數代碼</span><span class="sxs-lookup"><span data-stu-id="0e624-173">Area code</span></span>

  - <span data-ttu-id="0e624-174">延伸長度</span><span class="sxs-lookup"><span data-stu-id="0e624-174">Length of extension</span></span>

  - <span data-ttu-id="0e624-175">網站前置詞</span><span class="sxs-lookup"><span data-stu-id="0e624-175">Site prefix</span></span>

<div>

## <a name="creating-normalization-rules"></a><span data-ttu-id="0e624-176">建立正常化規則</span><span class="sxs-lookup"><span data-stu-id="0e624-176">Creating Normalization Rules</span></span>

<span data-ttu-id="0e624-177">正規化規則使用 .NET Framework 正則運算式，指定伺服器用以將撥號字串轉譯為 e.164 格式，以執行反向號碼查閱的數位匹配模式。</span><span class="sxs-lookup"><span data-stu-id="0e624-177">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format for the purpose of performing reverse number lookup.</span></span> <span data-ttu-id="0e624-178">您可以在 Lync Server 控制台中建立正規化規則，方法是手動輸入運算式，或輸入要比對的撥號字串的開始位數和長度，並讓 Lync Server 控制台為您產生對應的正則運算式。</span><span class="sxs-lookup"><span data-stu-id="0e624-178">You create normalization rules in the Lync Server Control Panel either by entering the expressions manually, or by entering the starting digits and the length of the dial strings to be matched and letting the Lync Server Control Panel generate the corresponding regular expression for you.</span></span> <span data-ttu-id="0e624-179">無論是哪一種方式，當您完成時，您都可以輸入測試號碼，以驗證正規化規則如預期的方式運作。</span><span class="sxs-lookup"><span data-stu-id="0e624-179">Either way, when you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="0e624-180">如需使用 .NET Framework 正則運算式的詳細資訊，請參閱 at .NET Framework 正則運算式 [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) 。</span><span class="sxs-lookup"><span data-stu-id="0e624-180">For details about using .NET Framework regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a><span data-ttu-id="0e624-181">正常化規則範例</span><span class="sxs-lookup"><span data-stu-id="0e624-181">Sample Normalization Rules</span></span>

<span data-ttu-id="0e624-182">下表顯示以 .NET Framework 正則運算式形式寫入的範例正常化規則。</span><span class="sxs-lookup"><span data-stu-id="0e624-182">The following table shows sample normalization rules that are written as .NET Framework regular expressions.</span></span> <span data-ttu-id="0e624-183">範例只是範例，並不是建立您自己的正規化規則的規範性參考。</span><span class="sxs-lookup"><span data-stu-id="0e624-183">The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a><span data-ttu-id="0e624-184">表 1. 使用 .NET Framework 正則運算式的正常化規則</span><span class="sxs-lookup"><span data-stu-id="0e624-184">Table 1.Normalization Rules Using .NET Framework Regular Expressions</span></span>

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
<th><span data-ttu-id="0e624-185">規則名稱</span><span class="sxs-lookup"><span data-stu-id="0e624-185">Rule name</span></span></th>
<th><span data-ttu-id="0e624-186">描述</span><span class="sxs-lookup"><span data-stu-id="0e624-186">Description</span></span></th>
<th><span data-ttu-id="0e624-187">號碼模式</span><span class="sxs-lookup"><span data-stu-id="0e624-187">Number pattern</span></span></th>
<th><span data-ttu-id="0e624-188">Translation</span><span class="sxs-lookup"><span data-stu-id="0e624-188">Translation</span></span></th>
<th><span data-ttu-id="0e624-189">範例</span><span class="sxs-lookup"><span data-stu-id="0e624-189">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e624-190">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="0e624-190">4digitExtension</span></span></p></td>
<td><p><span data-ttu-id="0e624-191">轉譯4位數的分機號碼</span><span class="sxs-lookup"><span data-stu-id="0e624-191">Translates 4-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="0e624-192">^ ( \d {4}) $</span><span class="sxs-lookup"><span data-stu-id="0e624-192">^(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="0e624-193">+ 1425555 $ 1</span><span class="sxs-lookup"><span data-stu-id="0e624-193">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="0e624-194">0100會轉譯成 + 14255550100</span><span class="sxs-lookup"><span data-stu-id="0e624-194">0100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e624-195">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="0e624-195">5digitExtension</span></span></p></td>
<td><p><span data-ttu-id="0e624-196">轉譯5位數的分機號碼</span><span class="sxs-lookup"><span data-stu-id="0e624-196">Translates 5-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="0e624-197">^ 5 ( \d {4}) $</span><span class="sxs-lookup"><span data-stu-id="0e624-197">^5(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="0e624-198">+ 1425555 $ 1</span><span class="sxs-lookup"><span data-stu-id="0e624-198">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="0e624-199">50100會轉譯成 + 14255550100</span><span class="sxs-lookup"><span data-stu-id="0e624-199">50100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e624-200">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="0e624-200">7digitcallingRedmond</span></span></p></td>
<td><p><span data-ttu-id="0e624-201">將7位數號碼轉譯為 Redmond 當地號碼</span><span class="sxs-lookup"><span data-stu-id="0e624-201">Translates 7-digit numbers to Redmond local numbers</span></span></p></td>
<td><p><span data-ttu-id="0e624-202">^ ( \d {7}) $</span><span class="sxs-lookup"><span data-stu-id="0e624-202">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="0e624-203">+ 1425 $ 1</span><span class="sxs-lookup"><span data-stu-id="0e624-203">+1425$1</span></span></p></td>
<td><p><span data-ttu-id="0e624-204">5550100會轉譯成 + 14255550100</span><span class="sxs-lookup"><span data-stu-id="0e624-204">5550100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e624-205">7digitcallingDallas</span><span class="sxs-lookup"><span data-stu-id="0e624-205">7digitcallingDallas</span></span></p></td>
<td><p><span data-ttu-id="0e624-206">將7位數號碼轉譯為達拉斯當地號碼</span><span class="sxs-lookup"><span data-stu-id="0e624-206">Translates 7-digit numbers to Dallas local numbers</span></span></p></td>
<td><p><span data-ttu-id="0e624-207">^ ( \d {7}) $</span><span class="sxs-lookup"><span data-stu-id="0e624-207">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="0e624-208">+ 1972 $ 1</span><span class="sxs-lookup"><span data-stu-id="0e624-208">+1972$1</span></span></p></td>
<td><p><span data-ttu-id="0e624-209">5550100會轉譯成 + 19725550100</span><span class="sxs-lookup"><span data-stu-id="0e624-209">5550100 is translated to +19725550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e624-210">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="0e624-210">10digitcallingUS</span></span></p></td>
<td><p><span data-ttu-id="0e624-211">翻譯美國的10位數數位</span><span class="sxs-lookup"><span data-stu-id="0e624-211">Translates 10-digit numbers in the United States</span></span></p></td>
<td><p><span data-ttu-id="0e624-212">^ ( \d {10}) $</span><span class="sxs-lookup"><span data-stu-id="0e624-212">^(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="0e624-213">+ 1 $ 1</span><span class="sxs-lookup"><span data-stu-id="0e624-213">+1$1</span></span></p></td>
<td><p><span data-ttu-id="0e624-214">2065550100會轉譯成 + 12065550100</span><span class="sxs-lookup"><span data-stu-id="0e624-214">2065550100 is translated to +12065550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e624-215">LDCallingUS</span><span class="sxs-lookup"><span data-stu-id="0e624-215">LDCallingUS</span></span></p></td>
<td><p><span data-ttu-id="0e624-216">轉譯美國具有長途首碼的號碼</span><span class="sxs-lookup"><span data-stu-id="0e624-216">Translates numbers with long distance prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="0e624-217">^ 1 ( \d {10}) $</span><span class="sxs-lookup"><span data-stu-id="0e624-217">^1(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="0e624-218">+ $1</span><span class="sxs-lookup"><span data-stu-id="0e624-218">+$1</span></span></p></td>
<td><p><span data-ttu-id="0e624-219">12145550100會轉譯成 + 2145550100</span><span class="sxs-lookup"><span data-stu-id="0e624-219">12145550100 is translated to +2145550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e624-220">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="0e624-220">IntlCallingUS</span></span></p></td>
<td><p><span data-ttu-id="0e624-221">轉譯美國國際首碼的號碼</span><span class="sxs-lookup"><span data-stu-id="0e624-221">Translates numbers with international prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="0e624-222">^ 011 ( \d \* ) $</span><span class="sxs-lookup"><span data-stu-id="0e624-222">^011(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="0e624-223">+ $1</span><span class="sxs-lookup"><span data-stu-id="0e624-223">+$1</span></span></p></td>
<td><p><span data-ttu-id="0e624-224">01191445550100會轉譯成 + 91445550100</span><span class="sxs-lookup"><span data-stu-id="0e624-224">01191445550100 is translated to +91445550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e624-225">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="0e624-225">RedmondOperator</span></span></p></td>
<td><p><span data-ttu-id="0e624-226">轉譯0到 Redmond 運算子</span><span class="sxs-lookup"><span data-stu-id="0e624-226">Translates 0 to Redmond Operator</span></span></p></td>
<td><p><span data-ttu-id="0e624-227">^ $0</span><span class="sxs-lookup"><span data-stu-id="0e624-227">^0$</span></span></p></td>
<td><p><span data-ttu-id="0e624-228">+ 14255550100</span><span class="sxs-lookup"><span data-stu-id="0e624-228">+14255550100</span></span></p></td>
<td><p><span data-ttu-id="0e624-229">0會轉譯成 + 14255550100</span><span class="sxs-lookup"><span data-stu-id="0e624-229">0 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e624-230">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="0e624-230">RedmondSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="0e624-231">轉譯具有) 網路首碼 (6 和 Redmond 網站碼 (222 的數位) </span><span class="sxs-lookup"><span data-stu-id="0e624-231">Translates numbers with on-net prefix (6) and Redmond site code (222)</span></span></p></td>
<td><p><span data-ttu-id="0e624-232">^ 6222 ( \d {4}) $</span><span class="sxs-lookup"><span data-stu-id="0e624-232">^6222(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="0e624-233">+ 1425555 $ 1</span><span class="sxs-lookup"><span data-stu-id="0e624-233">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="0e624-234">62220100會轉譯成 + 14255550100</span><span class="sxs-lookup"><span data-stu-id="0e624-234">62220100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e624-235">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="0e624-235">NYSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="0e624-236">轉譯具有) 網路首碼的號碼 (6 和 NY 網站碼 (333) </span><span class="sxs-lookup"><span data-stu-id="0e624-236">Translates numbers with on-net prefix (6) and NY site code (333)</span></span></p></td>
<td><p><span data-ttu-id="0e624-237">^ 6333 ( \d {4}) $</span><span class="sxs-lookup"><span data-stu-id="0e624-237">^6333(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="0e624-238">+ 1202555 $ 1</span><span class="sxs-lookup"><span data-stu-id="0e624-238">+1202555$1</span></span></p></td>
<td><p><span data-ttu-id="0e624-239">63330100會轉譯成 + 12025550100</span><span class="sxs-lookup"><span data-stu-id="0e624-239">63330100 is translated to +12025550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e624-240">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="0e624-240">DallasSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="0e624-241">轉譯具有) 網路首碼 (6 和達拉斯 site code (444 的數位) </span><span class="sxs-lookup"><span data-stu-id="0e624-241">Translates numbers with on-net prefix (6) and Dallas site code (444)</span></span></p></td>
<td><p><span data-ttu-id="0e624-242">^ 6444 ( \d {4}) $</span><span class="sxs-lookup"><span data-stu-id="0e624-242">^6444(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="0e624-243">+ 1972555 $ 1</span><span class="sxs-lookup"><span data-stu-id="0e624-243">+1972555$1</span></span></p></td>
<td><p><span data-ttu-id="0e624-244">64440100會轉譯成 + 19725550100</span><span class="sxs-lookup"><span data-stu-id="0e624-244">64440100 is translated to +19725550100</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0e624-245">下表根據上表所示的正規化規則，顯示 Redmond （華盛頓）州的範例撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="0e624-245">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a><span data-ttu-id="0e624-246">表 2.</span><span class="sxs-lookup"><span data-stu-id="0e624-246">Table 2.</span></span> <span data-ttu-id="0e624-247">以表1顯示的正規化規則為依據的 Redmond 撥號對應表</span><span class="sxs-lookup"><span data-stu-id="0e624-247">Redmond Dial Plan Based on Normalization Rules Shown in Table 1</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e624-248">Redmond forestFQDN</span><span class="sxs-lookup"><span data-stu-id="0e624-248">Redmond.forestFQDN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e624-249">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="0e624-249">5digitExtension</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e624-250">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="0e624-250">7digitcallingRedmond</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e624-251">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="0e624-251">10digitcallingUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e624-252">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="0e624-252">IntlCallingUS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e624-253">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="0e624-253">RedmondSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e624-254">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="0e624-254">NYSitePrefix</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e624-255">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="0e624-255">DallasSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e624-256">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="0e624-256">RedmondOperator</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="0e624-257">上表所顯示的正規化規則名稱不會包含空格，但這是選擇性的考慮。</span><span class="sxs-lookup"><span data-stu-id="0e624-257">The normalization rules names shown in the preceding table do not include spaces, but this is a matter of choice.</span></span> <span data-ttu-id="0e624-258">例如，表格中的第一個名稱可以是 "5 位數副檔名" 或 "5 位數擴充"，而且仍然有效。</span><span class="sxs-lookup"><span data-stu-id="0e624-258">The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

