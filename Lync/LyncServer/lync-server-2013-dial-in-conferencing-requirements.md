---
title: Lync Server 2013 電話撥入式會議需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2f4878e81a28b5d51726cb1f3e2dc5c7c5aa0fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977122"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="0d070-102">Lync Server 2013 中的電話撥入式會議需求</span><span class="sxs-lookup"><span data-stu-id="0d070-102">Dial-in conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d070-103">_**主題上次修改日期：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="0d070-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="0d070-104">開始進行 Lync Server 2013 部署程式之前，您需要規劃下列各項：</span><span class="sxs-lookup"><span data-stu-id="0d070-104">Before you start the Lync Server 2013 deployment process you need to plan for the following:</span></span>

  - <span data-ttu-id="0d070-105">用來連線到公用交換電話網絡（PSTN）的設定</span><span class="sxs-lookup"><span data-stu-id="0d070-105">The configuration to use for connecting to the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="0d070-106">將電話撥入式會議區域指派給撥入式存取號碼的策略</span><span class="sxs-lookup"><span data-stu-id="0d070-106">Your strategy for assigning dial-in conferencing regions to dial-in access numbers</span></span>

  - <span data-ttu-id="0d070-107">建立會議目錄的策略</span><span class="sxs-lookup"><span data-stu-id="0d070-107">Your strategy for creating conference directories</span></span>

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a><span data-ttu-id="0d070-108">規劃撥入 PSTN 連接</span><span class="sxs-lookup"><span data-stu-id="0d070-108">Planning for Dial-in PSTN Connectivity</span></span>

<span data-ttu-id="0d070-109">電話撥入式會議需要至少一個中繼伺服器和至少一個 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="0d070-109">Dial-in conferencing requires at least one Mediation Server and at least one PSTN gateway.</span></span>

<span data-ttu-id="0d070-110">您可以在中央網站或分支網站中部署中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="0d070-110">You can deploy a Mediation Server in a central site or in a branch site.</span></span> <span data-ttu-id="0d070-111">在中央網站中，您可以 collocate 前端池或標準版伺服器上的中繼伺服器，或將它部署在獨立伺服器或池中。</span><span class="sxs-lookup"><span data-stu-id="0d070-111">In a central site, you can collocate a Mediation Server on a Front End pool or Standard Edition server, or you can deploy it on a stand-alone server or pool.</span></span> <span data-ttu-id="0d070-112">在分支網站中，您可以在獨立伺服器或 Survivable 分支裝置的元件上部署轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="0d070-112">In a branch site, you can deploy a Mediation Server on a stand-alone server or as a component of the Survivable Branch Appliance.</span></span>

<span data-ttu-id="0d070-113">您可以在中央網站或分支網站中部署 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="0d070-113">You can deploy a PSTN gateway in a central site or in a branch site.</span></span> <span data-ttu-id="0d070-114">在分支網站中，PSTN 閘道可以獨立或 Survivable 分支裝置的元件。</span><span class="sxs-lookup"><span data-stu-id="0d070-114">In a branch site, the PSTN gateway can be stand-alone or a component of the Survivable Branch Appliance.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0d070-115">電話撥入式會議不會使用媒體旁路，因為 A/V 會議伺服器不支援媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="0d070-115">Dial-in conferencing does not use media bypass because A/V Conferencing Server do not support media bypass.</span></span>



</div>

<span data-ttu-id="0d070-116">如需規劃您為進行電話撥入式會議的中繼伺服器和 PSTN 閘道設定的詳細資料，請參閱規劃檔中的[Lync server 2013 中的中繼伺服器元件與拓撲](lync-server-2013-components-and-topologies-for-mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="0d070-116">For details about planning your configuration for Mediation Server and PSTN gateways for dial-in conferencing, see [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a><span data-ttu-id="0d070-117">規劃電話撥入式會議區域</span><span class="sxs-lookup"><span data-stu-id="0d070-117">Planning for Dial-in Conferencing Regions</span></span>

<span data-ttu-id="0d070-118">在撥入設定期間，您會建立撥號方案和電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="0d070-118">During dial-in configuration, you create dial plans and dial-in conferencing access numbers.</span></span> <span data-ttu-id="0d070-119">撥號方案是一組正常化規則，可指定電話號碼中的數位和位數，並將電話號碼轉譯為呼叫路由的標準 e. 164 格式。</span><span class="sxs-lookup"><span data-stu-id="0d070-119">Dial plans are sets of normalization rules that specify the number and pattern of digits in a phone number and translate the phone number into the standard E.164 format for call routing.</span></span> <span data-ttu-id="0d070-120">電話撥入式會議存取號碼是參與者加入會議的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="0d070-120">Dial-in conferencing access numbers are the numbers participants call to join a conference.</span></span>

<span data-ttu-id="0d070-121">每個電話撥入式會議存取號碼必須與至少一個撥號方案相關聯。</span><span class="sxs-lookup"><span data-stu-id="0d070-121">Every dial-in conferencing access number must be associated with at least one dial plan.</span></span> <span data-ttu-id="0d070-122">電話撥入式會議區域會將電話撥入式會議存取號碼與撥號方案建立關聯。</span><span class="sxs-lookup"><span data-stu-id="0d070-122">Dial-in conferencing regions associate a dial-in conferencing access number with its dial plans.</span></span> <span data-ttu-id="0d070-123">當您設定撥號方案時，請指定適用于撥號計畫的電話撥入式會議區域。</span><span class="sxs-lookup"><span data-stu-id="0d070-123">When you set up a dial plan, you specify the dial-in conferencing region that applies to the dial plan.</span></span> <span data-ttu-id="0d070-124">當您建立撥入存取號碼時，請選取將存取號碼與適當的撥號方案相關聯的地區。</span><span class="sxs-lookup"><span data-stu-id="0d070-124">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="0d070-125">當您建立撥號方案時，您可以指定撥號方案的範圍： [使用者範圍]、[池範圍] 或 [網站範圍]。</span><span class="sxs-lookup"><span data-stu-id="0d070-125">When you create a dial plan, you specify the scope of the dial plan: user scope, pool scope, or site scope.</span></span> <span data-ttu-id="0d070-126">每個使用者都會從適用于使用者的最窄範圍指派撥號方案。</span><span class="sxs-lookup"><span data-stu-id="0d070-126">Every user is assigned the dial plan from the narrowest scope that applies to the user.</span></span> <span data-ttu-id="0d070-127">例如，如果您有一個使用者層級撥號方案，則會指派給該使用者。</span><span class="sxs-lookup"><span data-stu-id="0d070-127">For example, a user is assigned a user-level dial plan, if one applies.</span></span> <span data-ttu-id="0d070-128">如果沒有套用使用者層級撥號方案，則會將使用者指派為「泳池層級撥號」方案。</span><span class="sxs-lookup"><span data-stu-id="0d070-128">If a user-level dial plan does not apply, the user is assigned a pool-level dial plan.</span></span> <span data-ttu-id="0d070-129">如果沒有套用池層級撥號方案，就會為使用者指派網站層級的撥號方案。</span><span class="sxs-lookup"><span data-stu-id="0d070-129">If a pool-level dial plan does not apply, the user is assigned a site-level dial plan.</span></span> <span data-ttu-id="0d070-130">如果網站層級撥號方案不適用，則會為使用者指派全域撥號方案。</span><span class="sxs-lookup"><span data-stu-id="0d070-130">If a site-level dial plan does not apply, the user is assigned the global dial plan.</span></span>

<span data-ttu-id="0d070-131">在您設定撥號方案之前，請務必規劃您想要如何命名及使用地區。</span><span class="sxs-lookup"><span data-stu-id="0d070-131">Before you configure the dial plans, is it important to plan how you want to name and use regions.</span></span> <span data-ttu-id="0d070-132">下列考慮適用于電話撥入式會議區域：</span><span class="sxs-lookup"><span data-stu-id="0d070-132">The following considerations apply to dial-in conferencing regions:</span></span>

  - <span data-ttu-id="0d070-133">地區通常是與辦公室或辦公室群組相關聯的地理區域。</span><span class="sxs-lookup"><span data-stu-id="0d070-133">A region is typically a geographical area that is associated with an office or group of offices.</span></span>

  - <span data-ttu-id="0d070-134">[語言] 與 [撥入存取號碼] 相關聯。</span><span class="sxs-lookup"><span data-stu-id="0d070-134">Languages are associated with dial-in access numbers.</span></span> <span data-ttu-id="0d070-135">如果您支援具有多種語言的地理區域，您應該決定要如何定義區域來支援多種語言。</span><span class="sxs-lookup"><span data-stu-id="0d070-135">If you support geographical areas that have multiple languages, you should decide how you want to define regions to support the multiple languages.</span></span> <span data-ttu-id="0d070-136">例如，您可能會根據地理與語言的組合來定義多個區域，或者您可以根據地理位置定義單一區域，並針對每個語言使用不同的撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="0d070-136">For example, you might define multiple regions based on a combination of geography and language, or you might define a single region based on geography and have a different dial-in access numbers for each language.</span></span>

  - <span data-ttu-id="0d070-137">當使用者排程會議時，預設情況下，會議會使用該使用者撥號計畫所指定的區域。</span><span class="sxs-lookup"><span data-stu-id="0d070-137">When a user schedules a meeting, by default the meeting uses the region specified by that user's dial plan.</span></span>

  - <span data-ttu-id="0d070-138">根據預設，該區域的所有撥入存取號碼都會包含在會議邀請中。</span><span class="sxs-lookup"><span data-stu-id="0d070-138">By default, the all of the dial-in access numbers for the region are included in the meeting invitation.</span></span>

  - <span data-ttu-id="0d070-139">請務必為區域命名，以便清楚辨識。</span><span class="sxs-lookup"><span data-stu-id="0d070-139">It is important to name regions so that they are clearly recognizable.</span></span> <span data-ttu-id="0d070-140">使用者可以使用地區名稱來變更會議的區域，以便邀請中包含不同的存取號碼。</span><span class="sxs-lookup"><span data-stu-id="0d070-140">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span></span> <span data-ttu-id="0d070-141">（當使用者使用 Outlook 排程會議時，使用者會使用 Lync 2013 的線上會議增益集來變更區域）。</span><span class="sxs-lookup"><span data-stu-id="0d070-141">(When users use Outlook to schedule a meeting, the user uses the Online Meeting Add-in for Lync 2013 to change the region).</span></span>

  - <span data-ttu-id="0d070-142">區域應該設計為想要撥入會議的任何被邀請者，都可以在會議邀請中看到本機存取號碼。</span><span class="sxs-lookup"><span data-stu-id="0d070-142">Regions should be designed so that any invitee who wants to dial into a conference can see a local access number in the conference invitation.</span></span>

  - <span data-ttu-id="0d070-143">您可以在 [電話撥入式會議設定] 頁面（也就是這些號碼在會議邀請中出現的順序），使用 Lync Server 管理命令介面 Cmdlet 來設定其在區域內顯示的順序。</span><span class="sxs-lookup"><span data-stu-id="0d070-143">You can configure the order in which access numbers within a region appear on the Dial-in Conferencing Settings page (and, therefore, the order in which they appear in the conference invitation) by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="0d070-144">任何位置的使用者都可以呼叫任何撥入存取號碼來加入會議。</span><span class="sxs-lookup"><span data-stu-id="0d070-144">Any user from any location can call any dial-in access number to join a conference.</span></span>

</div>

<div>

## <a name="planning-for-conference-directories"></a><span data-ttu-id="0d070-145">規劃會議目錄</span><span class="sxs-lookup"><span data-stu-id="0d070-145">Planning for Conference Directories</span></span>

<span data-ttu-id="0d070-146">在使用 Lync 2013 時，會議目錄會維持參與者用來加入會議的字母數位會議 ID 之間的對應，以及電話撥入式會議參與者用來加入會議的僅限數位會議 ID。</span><span class="sxs-lookup"><span data-stu-id="0d070-146">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="0d070-147">會議 ID 的格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="0d070-147">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="0d070-148">建立多個會議目錄可確保會議 Id 保持不變，直到建立大量的會議為止。</span><span class="sxs-lookup"><span data-stu-id="0d070-148">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="0d070-149">在每位使用者有典型會議數的組織中，我們建議您為池中的每個999使用者建立一個會議目錄。</span><span class="sxs-lookup"><span data-stu-id="0d070-149">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="0d070-150">使用這種準則，會議 Id 通常可以保持很小的狀態。</span><span class="sxs-lookup"><span data-stu-id="0d070-150">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="0d070-151">不過，一旦會議目錄數（跨多個池）超過9個，會議 ID 號碼就會增長以支援其他會議。</span><span class="sxs-lookup"><span data-stu-id="0d070-151">However, once the number of conference directories (across the pools) exceed 9, the Conference ID number will grow to support additional conferences.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0d070-152">請參閱</span><span class="sxs-lookup"><span data-stu-id="0d070-152">See Also</span></span>


[<span data-ttu-id="0d070-153">Lync Server 2013 中的中繼伺服器元件</span><span class="sxs-lookup"><span data-stu-id="0d070-153">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  
[<span data-ttu-id="0d070-154">Lync Server 2013 中的撥號方案和正常化規則</span><span class="sxs-lookup"><span data-stu-id="0d070-154">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

