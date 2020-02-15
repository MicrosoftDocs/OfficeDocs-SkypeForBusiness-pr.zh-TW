---
title: Lync Server 2013 電話撥入式會議需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b80ab9db6b565530db211db8aa47e2e00cbd9cf2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="df715-102">Lync Server 2013 中的電話撥入式會議需求</span><span class="sxs-lookup"><span data-stu-id="df715-102">Dial-in conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df715-103">_**主題上次修改日期：** 2012年-09-30_</span><span class="sxs-lookup"><span data-stu-id="df715-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="df715-104">在您開始使用 Lync Server 2013 部署程序之前必須規劃的下列：</span><span class="sxs-lookup"><span data-stu-id="df715-104">Before you start the Lync Server 2013 deployment process you need to plan for the following:</span></span>

  - <span data-ttu-id="df715-105">要用於連線至公用交換的電話網路 (PSTN) 的組態</span><span class="sxs-lookup"><span data-stu-id="df715-105">The configuration to use for connecting to the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="df715-106">策略指派給撥入的電話撥入式會議地區的存取號碼</span><span class="sxs-lookup"><span data-stu-id="df715-106">Your strategy for assigning dial-in conferencing regions to dial-in access numbers</span></span>

  - <span data-ttu-id="df715-107">建立會議目錄的策略</span><span class="sxs-lookup"><span data-stu-id="df715-107">Your strategy for creating conference directories</span></span>

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a><span data-ttu-id="df715-108">規劃電話撥入式 PSTN 連線</span><span class="sxs-lookup"><span data-stu-id="df715-108">Planning for Dial-in PSTN Connectivity</span></span>

<span data-ttu-id="df715-109">電話撥入式會議需要至少一部中繼伺服器和至少一個 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="df715-109">Dial-in conferencing requires at least one Mediation Server and at least one PSTN gateway.</span></span>

<span data-ttu-id="df715-110">您可以部署中繼伺服器在中央網站，或在分支網站中。</span><span class="sxs-lookup"><span data-stu-id="df715-110">You can deploy a Mediation Server in a central site or in a branch site.</span></span> <span data-ttu-id="df715-111">在管理中心網站中，您可以組合的中繼伺服器上的前端集區或 Standard Edition 伺服器，或您可以將它部署在獨立伺服器或集區。</span><span class="sxs-lookup"><span data-stu-id="df715-111">In a central site, you can collocate a Mediation Server on a Front End pool or Standard Edition server, or you can deploy it on a stand-alone server or pool.</span></span> <span data-ttu-id="df715-112">在分支網站中，您可以部署中繼伺服器上獨立伺服器，或為 Survivable Branch Appliance 的元件。</span><span class="sxs-lookup"><span data-stu-id="df715-112">In a branch site, you can deploy a Mediation Server on a stand-alone server or as a component of the Survivable Branch Appliance.</span></span>

<span data-ttu-id="df715-113">您可以部署在中央網站，或在分支網站中的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="df715-113">You can deploy a PSTN gateway in a central site or in a branch site.</span></span> <span data-ttu-id="df715-114">在分支網站中，PSTN 閘道可以是獨立或 a Survivable Branch Appliance 的元件。</span><span class="sxs-lookup"><span data-stu-id="df715-114">In a branch site, the PSTN gateway can be stand-alone or a component of the Survivable Branch Appliance.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="df715-115">電話撥入式會議不使用媒體旁路，因為 A / V 會議伺服器不支援媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="df715-115">Dial-in conferencing does not use media bypass because A/V Conferencing Server do not support media bypass.</span></span>



</div>

<span data-ttu-id="df715-116">如需規劃您的設定，針對 [中繼伺服器和 PSTN 閘道的撥入式會議的詳細資訊，請參閱規劃文件中的[Lync Server 2013 中的中繼伺服器的元件和拓撲](lync-server-2013-components-and-topologies-for-mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="df715-116">For details about planning your configuration for Mediation Server and PSTN gateways for dial-in conferencing, see [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a><span data-ttu-id="df715-117">規劃撥入式會議區域</span><span class="sxs-lookup"><span data-stu-id="df715-117">Planning for Dial-in Conferencing Regions</span></span>

<span data-ttu-id="df715-118">電話撥入式組態中，在您建立撥號對應表和電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="df715-118">During dial-in configuration, you create dial plans and dial-in conferencing access numbers.</span></span> <span data-ttu-id="df715-119">撥號對應表是指定的數目和模式的數字的電話號碼，並將電話號碼轉譯成標準 E.164 格式進行通話路由傳送的正規化規則的集合。</span><span class="sxs-lookup"><span data-stu-id="df715-119">Dial plans are sets of normalization rules that specify the number and pattern of digits in a phone number and translate the phone number into the standard E.164 format for call routing.</span></span> <span data-ttu-id="df715-120">電話撥入式會議存取號碼是數字參與者電話加入會議。</span><span class="sxs-lookup"><span data-stu-id="df715-120">Dial-in conferencing access numbers are the numbers participants call to join a conference.</span></span>

<span data-ttu-id="df715-121">每個撥入式會議存取號碼必須是至少一個撥號對應表相關聯。</span><span class="sxs-lookup"><span data-stu-id="df715-121">Every dial-in conferencing access number must be associated with at least one dial plan.</span></span> <span data-ttu-id="df715-122">電話撥入式會議地區關聯其撥號對應表撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="df715-122">Dial-in conferencing regions associate a dial-in conferencing access number with its dial plans.</span></span> <span data-ttu-id="df715-123">當您設定撥號對應表時，您會指定套用至撥號對應表撥入式會議區域。</span><span class="sxs-lookup"><span data-stu-id="df715-123">When you set up a dial plan, you specify the dial-in conferencing region that applies to the dial plan.</span></span> <span data-ttu-id="df715-124">當您建立的撥入存取號碼時，您會選取適當的撥號對應表建立關聯的存取號碼的地區。</span><span class="sxs-lookup"><span data-stu-id="df715-124">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="df715-125">當您建立撥號對應表時，您指定的撥號對應表範圍： 使用者範圍、 集區的範圍或網站範圍。</span><span class="sxs-lookup"><span data-stu-id="df715-125">When you create a dial plan, you specify the scope of the dial plan: user scope, pool scope, or site scope.</span></span> <span data-ttu-id="df715-126">每位使用者是從最窄範圍套用至使用者指派撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="df715-126">Every user is assigned the dial plan from the narrowest scope that applies to the user.</span></span> <span data-ttu-id="df715-127">例如，使用者如果其中一個適用於指派使用者層級撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="df715-127">For example, a user is assigned a user-level dial plan, if one applies.</span></span> <span data-ttu-id="df715-128">如果使用者層級撥號對應表不會套用，指派給使用者集區層級撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="df715-128">If a user-level dial plan does not apply, the user is assigned a pool-level dial plan.</span></span> <span data-ttu-id="df715-129">如果集區層級撥號對應表不會套用，使用者會指派網站層級撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="df715-129">If a pool-level dial plan does not apply, the user is assigned a site-level dial plan.</span></span> <span data-ttu-id="df715-130">如果網站層級撥號對應表不會套用，使用者會指派全域撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="df715-130">If a site-level dial plan does not apply, the user is assigned the global dial plan.</span></span>

<span data-ttu-id="df715-131">在您設定的撥號對應表計劃之前，是重要的規劃您要的名稱，並使用區域的方式。</span><span class="sxs-lookup"><span data-stu-id="df715-131">Before you configure the dial plans, is it important to plan how you want to name and use regions.</span></span> <span data-ttu-id="df715-132">下列考量適用於電話撥入式會議區域：</span><span class="sxs-lookup"><span data-stu-id="df715-132">The following considerations apply to dial-in conferencing regions:</span></span>

  - <span data-ttu-id="df715-133">區域通常是與一個或多個辦公室相關聯的地理區域。</span><span class="sxs-lookup"><span data-stu-id="df715-133">A region is typically a geographical area that is associated with an office or group of offices.</span></span>

  - <span data-ttu-id="df715-134">撥入存取號碼與語言相關聯。</span><span class="sxs-lookup"><span data-stu-id="df715-134">Languages are associated with dial-in access numbers.</span></span> <span data-ttu-id="df715-135">如果您支援多種語言的地理區域，您應該決定要如何定義以支援多種語言的地區。</span><span class="sxs-lookup"><span data-stu-id="df715-135">If you support geographical areas that have multiple languages, you should decide how you want to define regions to support the multiple languages.</span></span> <span data-ttu-id="df715-136">例如，您可以定義多個區域根據組合的 geography 及語言]，或者也可能定義單一區域根據地理位置，具有不同撥入存取號碼的每一種語言。</span><span class="sxs-lookup"><span data-stu-id="df715-136">For example, you might define multiple regions based on a combination of geography and language, or you might define a single region based on geography and have a different dial-in access numbers for each language.</span></span>

  - <span data-ttu-id="df715-137">當使用者排程會議時，根據預設，會議會使用該使用者的撥號對應表所指定的區域。</span><span class="sxs-lookup"><span data-stu-id="df715-137">When a user schedules a meeting, by default the meeting uses the region specified by that user's dial plan.</span></span>

  - <span data-ttu-id="df715-138">根據預設，區域的撥入存取號碼的所有隨附在會議邀請。</span><span class="sxs-lookup"><span data-stu-id="df715-138">By default, the all of the dial-in access numbers for the region are included in the meeting invitation.</span></span>

  - <span data-ttu-id="df715-139">務必名稱區域，使清楚辨識。</span><span class="sxs-lookup"><span data-stu-id="df715-139">It is important to name regions so that they are clearly recognizable.</span></span> <span data-ttu-id="df715-140">使用者可以變更會議的區域，以便在邀請中包含不同的存取號碼使用區域的名稱。</span><span class="sxs-lookup"><span data-stu-id="df715-140">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span></span> <span data-ttu-id="df715-141">（當使用者使用 Outlook 來排程會議時，使用者使用線上會議增益集 for Lync 2013 變更地區）。</span><span class="sxs-lookup"><span data-stu-id="df715-141">(When users use Outlook to schedule a meeting, the user uses the Online Meeting Add-in for Lync 2013 to change the region).</span></span>

  - <span data-ttu-id="df715-142">設計區域應，讓任何想要撥入會議的受邀者可以看到本機存取號碼，在會議邀請。</span><span class="sxs-lookup"><span data-stu-id="df715-142">Regions should be designed so that any invitee who wants to dial into a conference can see a local access number in the conference invitation.</span></span>

  - <span data-ttu-id="df715-143">您可以使用 Lync Server 管理命令介面指令程式設定中存取區域內的數字會出現在 [電話撥入式會議設定] 頁面的順序 （和，因此，在會議邀請中的顯示的順序）。</span><span class="sxs-lookup"><span data-stu-id="df715-143">You can configure the order in which access numbers within a region appear on the Dial-in Conferencing Settings page (and, therefore, the order in which they appear in the conference invitation) by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="df715-144">從任何位置的任何使用者可以撥打任何撥入存取號碼來加入會議。</span><span class="sxs-lookup"><span data-stu-id="df715-144">Any user from any location can call any dial-in access number to join a conference.</span></span>

</div>

<div>

## <a name="planning-for-conference-directories"></a><span data-ttu-id="df715-145">規劃會議目錄</span><span class="sxs-lookup"><span data-stu-id="df715-145">Planning for Conference Directories</span></span>

<span data-ttu-id="df715-146">會議目錄維護參與者使用時使用 Lync 2013 加入會議的英數字元的會議 ID 與電話撥入式會議參與者加入會議所使用的僅限數字鍵台的會議 ID 之間的對應。</span><span class="sxs-lookup"><span data-stu-id="df715-146">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="df715-147">會議 ID 的格式如下：</span><span class="sxs-lookup"><span data-stu-id="df715-147">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="df715-148">建立多個會議目錄，可確保在建立大量的會議之前會議 Id 會保持簡短。</span><span class="sxs-lookup"><span data-stu-id="df715-148">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="df715-149">在一般每位使用者的會議數目與組織中，我們建議您在集區中建立一個的每個 999 使用者的會議目錄。</span><span class="sxs-lookup"><span data-stu-id="df715-149">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="df715-150">使用此指導方針會議識別碼可以通常是保持小型。</span><span class="sxs-lookup"><span data-stu-id="df715-150">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="df715-151">不過，一旦 （整個集區） 的會議目錄的數目超過 9，會議 ID 號碼將會成長到支援其他會議。</span><span class="sxs-lookup"><span data-stu-id="df715-151">However, once the number of conference directories (across the pools) exceed 9, the Conference ID number will grow to support additional conferences.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="df715-152">另請參閱</span><span class="sxs-lookup"><span data-stu-id="df715-152">See Also</span></span>


[<span data-ttu-id="df715-153">Lync Server 2013 中的中繼伺服器元件</span><span class="sxs-lookup"><span data-stu-id="df715-153">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  
[<span data-ttu-id="df715-154">撥號對應表和 Lync Server 2013 中的正規化規則</span><span class="sxs-lookup"><span data-stu-id="df715-154">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

