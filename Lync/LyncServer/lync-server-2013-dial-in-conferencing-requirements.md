---
title: Lync Server 2013 電話撥入式會議需求
description: Lync Server 2013 電話撥入式會議需求。
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
ms.openlocfilehash: 0850204993935998c4c098bc7c2866a8a6f3fa1e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552479"
---
# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="20a38-103">Lync Server 2013 中的電話撥入式會議需求</span><span class="sxs-lookup"><span data-stu-id="20a38-103">Dial-in conferencing requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20a38-104">_**主題上次修改日期：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="20a38-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="20a38-105">開始 Lync Server 2013 部署程式之前，您需要規劃下列各項：</span><span class="sxs-lookup"><span data-stu-id="20a38-105">Before you start the Lync Server 2013 deployment process you need to plan for the following:</span></span>

  - <span data-ttu-id="20a38-106">連接到公用交換電話網路 (PSTN) 所用的設定</span><span class="sxs-lookup"><span data-stu-id="20a38-106">The configuration to use for connecting to the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="20a38-107">將電話撥入式會議地區指派給撥入存取號碼的策略</span><span class="sxs-lookup"><span data-stu-id="20a38-107">Your strategy for assigning dial-in conferencing regions to dial-in access numbers</span></span>

  - <span data-ttu-id="20a38-108">您建立會議目錄的策略</span><span class="sxs-lookup"><span data-stu-id="20a38-108">Your strategy for creating conference directories</span></span>

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a><span data-ttu-id="20a38-109">規劃撥入 PSTN 連接</span><span class="sxs-lookup"><span data-stu-id="20a38-109">Planning for Dial-in PSTN Connectivity</span></span>

<span data-ttu-id="20a38-110">電話撥入式會議至少需要一個轉送伺服器和至少一個 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="20a38-110">Dial-in conferencing requires at least one Mediation Server and at least one PSTN gateway.</span></span>

<span data-ttu-id="20a38-111">您可以在中央網站或分支網站中部署轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="20a38-111">You can deploy a Mediation Server in a central site or in a branch site.</span></span> <span data-ttu-id="20a38-112">在中央網站中，您可以組合前端集區或 Standard Edition server 上的轉送伺服器，也可以將它部署在獨立的伺服器或集區上。</span><span class="sxs-lookup"><span data-stu-id="20a38-112">In a central site, you can collocate a Mediation Server on a Front End pool or Standard Edition server, or you can deploy it on a stand-alone server or pool.</span></span> <span data-ttu-id="20a38-113">在分支網站中，您可以在獨立伺服器或 Survivable Branch 裝置的元件上部署轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="20a38-113">In a branch site, you can deploy a Mediation Server on a stand-alone server or as a component of the Survivable Branch Appliance.</span></span>

<span data-ttu-id="20a38-114">您可以在中央網站或分支網站中部署 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="20a38-114">You can deploy a PSTN gateway in a central site or in a branch site.</span></span> <span data-ttu-id="20a38-115">在分支網站中，PSTN 閘道可以是獨立或 Survivable 分支裝置的元件。</span><span class="sxs-lookup"><span data-stu-id="20a38-115">In a branch site, the PSTN gateway can be stand-alone or a component of the Survivable Branch Appliance.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="20a38-116">電話撥入式會議不會使用媒體旁路，因為 A/V 會議伺服器不支援媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="20a38-116">Dial-in conferencing does not use media bypass because A/V Conferencing Server do not support media bypass.</span></span>



</div>

<span data-ttu-id="20a38-117">如需規劃撥入式會議的轉送伺服器和 PSTN 閘道設定的詳細資訊，請參閱規劃檔中的 Lync Server 2013 中的「中繼」 [伺服器的元件和拓撲](lync-server-2013-components-and-topologies-for-mediation-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="20a38-117">For details about planning your configuration for Mediation Server and PSTN gateways for dial-in conferencing, see [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a><span data-ttu-id="20a38-118">規劃電話撥入式會議區域</span><span class="sxs-lookup"><span data-stu-id="20a38-118">Planning for Dial-in Conferencing Regions</span></span>

<span data-ttu-id="20a38-119">在撥入設定期間，您可以建立撥號對應表和電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="20a38-119">During dial-in configuration, you create dial plans and dial-in conferencing access numbers.</span></span> <span data-ttu-id="20a38-120">撥號對應表是一組正規化規則，可指定電話號碼中的位數和模式，並將電話號碼轉譯為標準的 e.164 格式，以供通話路由使用。</span><span class="sxs-lookup"><span data-stu-id="20a38-120">Dial plans are sets of normalization rules that specify the number and pattern of digits in a phone number and translate the phone number into the standard E.164 format for call routing.</span></span> <span data-ttu-id="20a38-121">電話撥入式會議存取號碼是參與者加入會議所撥打的號碼。</span><span class="sxs-lookup"><span data-stu-id="20a38-121">Dial-in conferencing access numbers are the numbers participants call to join a conference.</span></span>

<span data-ttu-id="20a38-122">每個電話撥入式會議存取號碼都必須與至少一個撥號對應表相關聯。</span><span class="sxs-lookup"><span data-stu-id="20a38-122">Every dial-in conferencing access number must be associated with at least one dial plan.</span></span> <span data-ttu-id="20a38-123">電話撥入式會議區域會將電話撥入式會議存取號碼與其撥號對應表產生關聯。</span><span class="sxs-lookup"><span data-stu-id="20a38-123">Dial-in conferencing regions associate a dial-in conferencing access number with its dial plans.</span></span> <span data-ttu-id="20a38-124">當您設定撥號對應表時，您可以指定套用至撥號對應表的電話撥入式會議區域。</span><span class="sxs-lookup"><span data-stu-id="20a38-124">When you set up a dial plan, you specify the dial-in conferencing region that applies to the dial plan.</span></span> <span data-ttu-id="20a38-125">當您建立撥入存取號碼時，請選取相關聯的撥號對應表的存取號碼相關聯的地區。</span><span class="sxs-lookup"><span data-stu-id="20a38-125">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="20a38-126">當您建立撥號對應表時，您可以指定撥號對應表的範圍：「使用者範圍」、「集區」範圍或「網站範圍」。</span><span class="sxs-lookup"><span data-stu-id="20a38-126">When you create a dial plan, you specify the scope of the dial plan: user scope, pool scope, or site scope.</span></span> <span data-ttu-id="20a38-127">每個使用者都會從套用至使用者的最窄範圍指派撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="20a38-127">Every user is assigned the dial plan from the narrowest scope that applies to the user.</span></span> <span data-ttu-id="20a38-128">例如，如果有適用的使用者層級撥號對應表，則會指派給該使用者。</span><span class="sxs-lookup"><span data-stu-id="20a38-128">For example, a user is assigned a user-level dial plan, if one applies.</span></span> <span data-ttu-id="20a38-129">若未套用使用者層級撥號對應表，則會為使用者指派集區層級撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="20a38-129">If a user-level dial plan does not apply, the user is assigned a pool-level dial plan.</span></span> <span data-ttu-id="20a38-130">若未套用集區層級撥號對應表，則會為該使用者指派網站層級撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="20a38-130">If a pool-level dial plan does not apply, the user is assigned a site-level dial plan.</span></span> <span data-ttu-id="20a38-131">若未套用網站層級撥號對應表，則會將全域撥號對應表指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="20a38-131">If a site-level dial plan does not apply, the user is assigned the global dial plan.</span></span>

<span data-ttu-id="20a38-132">在您設定撥號對應表之前，請務必規劃您想要命名及使用區域的方式。</span><span class="sxs-lookup"><span data-stu-id="20a38-132">Before you configure the dial plans, is it important to plan how you want to name and use regions.</span></span> <span data-ttu-id="20a38-133">下列考慮適用于電話撥入式會議地區：</span><span class="sxs-lookup"><span data-stu-id="20a38-133">The following considerations apply to dial-in conferencing regions:</span></span>

  - <span data-ttu-id="20a38-134">地區通常是與辦公室或辦事處群組相關聯的地理區域。</span><span class="sxs-lookup"><span data-stu-id="20a38-134">A region is typically a geographical area that is associated with an office or group of offices.</span></span>

  - <span data-ttu-id="20a38-135">語言與撥入存取號碼相關聯。</span><span class="sxs-lookup"><span data-stu-id="20a38-135">Languages are associated with dial-in access numbers.</span></span> <span data-ttu-id="20a38-136">如果您支援具有多種語言的地理區域，您應該決定要如何定義區域以支援多種語言。</span><span class="sxs-lookup"><span data-stu-id="20a38-136">If you support geographical areas that have multiple languages, you should decide how you want to define regions to support the multiple languages.</span></span> <span data-ttu-id="20a38-137">例如，您可以根據地理及語言的組合來定義多個地區，也可以根據地理位置定義單一區域，並為每一種語言使用不同的撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="20a38-137">For example, you might define multiple regions based on a combination of geography and language, or you might define a single region based on geography and have a different dial-in access numbers for each language.</span></span>

  - <span data-ttu-id="20a38-138">當使用者排程會議時，會議預設會使用該使用者的撥號對應表所指定的地區。</span><span class="sxs-lookup"><span data-stu-id="20a38-138">When a user schedules a meeting, by default the meeting uses the region specified by that user's dial plan.</span></span>

  - <span data-ttu-id="20a38-139">預設會在會議邀請中包含區域的所有撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="20a38-139">By default, the all of the dial-in access numbers for the region are included in the meeting invitation.</span></span>

  - <span data-ttu-id="20a38-140">請務必將地區命名為區域，使其清晰辨識。</span><span class="sxs-lookup"><span data-stu-id="20a38-140">It is important to name regions so that they are clearly recognizable.</span></span> <span data-ttu-id="20a38-141">使用者可以使用地區名稱來變更會議的區域，以邀請中包含不同的存取號碼。</span><span class="sxs-lookup"><span data-stu-id="20a38-141">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span></span> <span data-ttu-id="20a38-142"> (當使用者使用 Outlook 排程會議時，使用者會使用 Lync 2013 的線上會議增益集，以變更地區) 。</span><span class="sxs-lookup"><span data-stu-id="20a38-142">(When users use Outlook to schedule a meeting, the user uses the Online Meeting Add-in for Lync 2013 to change the region).</span></span>

  - <span data-ttu-id="20a38-143">應該設計區域，以便任何想要撥入會議的被邀請者，都可以在會議邀請中看到本機存取號碼。</span><span class="sxs-lookup"><span data-stu-id="20a38-143">Regions should be designed so that any invitee who wants to dial into a conference can see a local access number in the conference invitation.</span></span>

  - <span data-ttu-id="20a38-144">您可以設定地區內的存取號碼顯示在 [電話撥入式會議設定] 頁面 (，也就是使用 Lync Server 管理命令介面 Cmdlet 在會議邀請) 中顯示的順序。</span><span class="sxs-lookup"><span data-stu-id="20a38-144">You can configure the order in which access numbers within a region appear on the Dial-in Conferencing Settings page (and, therefore, the order in which they appear in the conference invitation) by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="20a38-145">任何位置的任何使用者都可以撥打任何撥入存取號碼，以加入會議。</span><span class="sxs-lookup"><span data-stu-id="20a38-145">Any user from any location can call any dial-in access number to join a conference.</span></span>

</div>

<div>

## <a name="planning-for-conference-directories"></a><span data-ttu-id="20a38-146">規劃會議目錄</span><span class="sxs-lookup"><span data-stu-id="20a38-146">Planning for Conference Directories</span></span>

<span data-ttu-id="20a38-147">會議目錄會維護在使用 Lync 2013 時，參與者用來加入會議的字母數位會議 ID 之間的對應，以及電話撥入式會議參與者用來加入會議的僅限數位會議識別碼。</span><span class="sxs-lookup"><span data-stu-id="20a38-147">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="20a38-148">會議識別碼的格式如下：</span><span class="sxs-lookup"><span data-stu-id="20a38-148">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="20a38-149">建立多個會議目錄可確保會議 IDs 持續縮短，直到建立大量會議為止。</span><span class="sxs-lookup"><span data-stu-id="20a38-149">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="20a38-150">在組織中，每位使用者的會議數目為典型，我們建議您針對集區中的每個999使用者建立一個會議目錄。</span><span class="sxs-lookup"><span data-stu-id="20a38-150">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="20a38-151">使用此指導方針時，會議 IDs 通常可以保持很小。</span><span class="sxs-lookup"><span data-stu-id="20a38-151">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="20a38-152">不過，一旦集區 (的會議目錄數目) 超過9，會議識別碼號碼就會成長以支援其他會議。</span><span class="sxs-lookup"><span data-stu-id="20a38-152">However, once the number of conference directories (across the pools) exceed 9, the Conference ID number will grow to support additional conferences.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="20a38-153">另請參閱</span><span class="sxs-lookup"><span data-stu-id="20a38-153">See Also</span></span>


[<span data-ttu-id="20a38-154">Lync Server 2013 中的轉送伺服器元件</span><span class="sxs-lookup"><span data-stu-id="20a38-154">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  
[<span data-ttu-id="20a38-155">Lync Server 2013 的撥號對應表和正常化規則</span><span class="sxs-lookup"><span data-stu-id="20a38-155">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

