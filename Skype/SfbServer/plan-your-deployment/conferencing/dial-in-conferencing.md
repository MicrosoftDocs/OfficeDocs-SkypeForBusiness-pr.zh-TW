---
title: 規劃商務用 Skype Server 中的電話撥入式會議
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea024a26-37b3-410e-961b-83ab85c07540
description: 摘要：閱讀此主題以瞭解如何在商務用 Skype Server 中規劃電話撥入式會議。
ms.openlocfilehash: 31e422a07c34eaf17c09157c2e12ad843dbacb03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814003"
---
# <a name="plan-for-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="776c8-103">規劃商務用 Skype Server 中的電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="776c8-103">Plan for dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="776c8-104">**摘要：** 閱讀此主題以瞭解如何在商務用 Skype Server 中規劃電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="776c8-104">**Summary:** Read this topic to learn about planning for dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="776c8-105">電話撥入式會議是商務用 Skype 伺服器的選用功能，可讓會議出席者使用電話撥入會議，以加入會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="776c8-105">Dial-in conferencing is an optional feature of Skype for Business Server that allows meeting attendees to join the audio portion of a meeting by calling in to the meeting from a phone.</span></span> <span data-ttu-id="776c8-106">電話撥入式會議是音訊會議的子集，並且需要額外設定。</span><span class="sxs-lookup"><span data-stu-id="776c8-106">Dial-in conferencing is a subset of audio conferencing and requires additional configuration.</span></span> <span data-ttu-id="776c8-107">本主題說明在為組織部署電話撥入式會議之前，您需要考慮的事項。</span><span class="sxs-lookup"><span data-stu-id="776c8-107">This topic describes what you need to think about before deploying dial-in conferencing for your organization.</span></span> 
  
<span data-ttu-id="776c8-108">電話撥入式會議所需的部分元件是用於撥入式會議，有些則是企業語音元件。</span><span class="sxs-lookup"><span data-stu-id="776c8-108">Some of the components required for dial-in conferencing are specific to dial-in conferencing and some are Enterprise Voice components.</span></span> <span data-ttu-id="776c8-109">雖然電話撥入式會議使用企業語音所用的部分相同元件，但即使您不部署企業語音，也可以部署電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="776c8-109">Although dial-in conferencing uses some of the same components that Enterprise Voice uses, you can deploy dial-in conferencing even if you do not deploy Enterprise Voice.</span></span> <span data-ttu-id="776c8-110">本節說明電話撥入式會議所需的元件。</span><span class="sxs-lookup"><span data-stu-id="776c8-110">This section describes the components that are needed for dial-in conferencing.</span></span> <span data-ttu-id="776c8-111">如需規劃完整 Enterprise Voice 解決方案的詳細資訊，請參閱 [在商務用 Skype Server 中規劃企業語音方案](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="776c8-111">For more information about planning a complete Enterprise Voice solution, see [Plan your Enterprise Voice solution in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md).</span></span>
  
<span data-ttu-id="776c8-112">電話撥入式會議需要您透過部署轉送伺服器，為公用交換電話網路 (PSTN) 提供連線能力。</span><span class="sxs-lookup"><span data-stu-id="776c8-112">Dial-in conferencing requires that you provide connectivity to the public switched telephone network (PSTN) by deploying a Mediation Server.</span></span> <span data-ttu-id="776c8-113">除了部署轉送伺服器之外，您還必須考慮下列專案，以允許貴組織使用電話撥入式會議：</span><span class="sxs-lookup"><span data-stu-id="776c8-113">In addition to deploying a Mediation Server, you need to consider the following to allow dial-in conferencing for your organization:</span></span>
  
- <span data-ttu-id="776c8-114">連接到公用交換電話網路 (PSTN) 的計畫</span><span class="sxs-lookup"><span data-stu-id="776c8-114">Your plan for connecting to the public switched telephone network (PSTN)</span></span>
    
- <span data-ttu-id="776c8-115">您的撥號對應表、存取號碼和會議區域的計畫</span><span class="sxs-lookup"><span data-stu-id="776c8-115">Your plan for dial plans, access numbers, and conferencing regions</span></span>
    
- <span data-ttu-id="776c8-116">建立會議目錄的計畫</span><span class="sxs-lookup"><span data-stu-id="776c8-116">Your plan for creating conferencing directories</span></span>
    
- <span data-ttu-id="776c8-117">允許撥入存取的會議原則</span><span class="sxs-lookup"><span data-stu-id="776c8-117">Your conferencing policy for allowing dial-in access</span></span>
    
- <span data-ttu-id="776c8-118">支援 enterprise 和匿名使用者</span><span class="sxs-lookup"><span data-stu-id="776c8-118">Support for enterprise and anonymous users</span></span>
    
> [!NOTE]
> <span data-ttu-id="776c8-119">如果您部署電話撥入式會議，則必須在每個部署商務用 Skype Server 會議的集區中部署它。</span><span class="sxs-lookup"><span data-stu-id="776c8-119">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Skype for Business Server conferencing.</span></span> <span data-ttu-id="776c8-120">在每個集區中，您不需要指派存取號碼--參與者加入會議所撥打的號碼，但是您必須在每個集區中部署撥入功能。</span><span class="sxs-lookup"><span data-stu-id="776c8-120">You do not need to assign access numbers--the numbers participants call to join a conference--in every pool, but you must deploy the dial-in feature in every pool.</span></span> <span data-ttu-id="776c8-121">當使用者呼叫一個集區中的存取號碼，以在不同的集區加入商務用 Skype Server 會議時，此需求即支援記錄的名稱功能。</span><span class="sxs-lookup"><span data-stu-id="776c8-121">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Skype for Business Server conference in a different pool.</span></span> 
  
## <a name="plan-for-pstn-connectivity"></a><span data-ttu-id="776c8-122">規劃 PSTN 連線能力</span><span class="sxs-lookup"><span data-stu-id="776c8-122">Plan for PSTN connectivity</span></span>

<span data-ttu-id="776c8-123">電話撥入式會議至少需要一個轉送伺服器，且至少一部公用交換電話網路 (PSTN) 閘道。</span><span class="sxs-lookup"><span data-stu-id="776c8-123">Dial-in conferencing requires at least one Mediation Server and at least one public switched telephone network (PSTN) gateway.</span></span> 
  
<span data-ttu-id="776c8-124">您可以在中央網站或分支網站中部署轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="776c8-124">You can deploy a Mediation Server in a central site or in a branch site.</span></span> <span data-ttu-id="776c8-125">在中央網站中，您可以組合前端集區或 Standard Edition server 上的轉送伺服器，也可以將它部署在獨立的伺服器或集區上。</span><span class="sxs-lookup"><span data-stu-id="776c8-125">In a central site, you can collocate a Mediation Server on a Front End pool or Standard Edition server, or you can deploy it on a stand-alone server or pool.</span></span> <span data-ttu-id="776c8-126">在分支網站中，您可以在獨立伺服器或 Survivable Branch 裝置的元件上部署轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="776c8-126">In a branch site, you can deploy a Mediation Server on a stand-alone server or as a component of the Survivable Branch Appliance.</span></span>
  
<span data-ttu-id="776c8-127">您可以在中央網站或分支網站中部署 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="776c8-127">You can deploy a PSTN gateway in a central site or in a branch site.</span></span> <span data-ttu-id="776c8-128">在分支網站中，PSTN 閘道可以是獨立或 Survivable 分支裝置的元件。</span><span class="sxs-lookup"><span data-stu-id="776c8-128">In a branch site, the PSTN gateway can be stand-alone or a component of the Survivable Branch Appliance.</span></span>
  
<span data-ttu-id="776c8-129">如需有關轉送伺服器和 PSTN 閘道需求的詳細資訊，請參閱 lync [server component In 商務用 Skype 伺服器](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)、 [在商務](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)用 skype server 的拓撲產生器中部署轉送伺服器，以及 [在商務用 skype server 的拓撲產生器中定義閘道](../../deploy/deploy-enterprise-voice/define-a-gateway.md)。</span><span class="sxs-lookup"><span data-stu-id="776c8-129">For details about Mediation Server and PSTN gateway requirements, see [Mediation Server component in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md), [Deploy a Mediation Server in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md), and [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>
  
## <a name="plan-for-dial-plans-access-numbers-and-conferencing-regions"></a><span data-ttu-id="776c8-130">規劃撥號對應表、存取號碼和會議地區</span><span class="sxs-lookup"><span data-stu-id="776c8-130">Plan for dial plans, access numbers, and conferencing regions</span></span>

<span data-ttu-id="776c8-131">若要設定電話撥入式會議，您可以建立撥號對應表和電話撥入式會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="776c8-131">To configure dial-in conferencing, you create dial plans and dial-in conferencing access numbers.</span></span> <span data-ttu-id="776c8-132">您也可以指定撥入式會議存取號碼與其撥號對應表關聯的撥入區域。</span><span class="sxs-lookup"><span data-stu-id="776c8-132">You also specify the dial-in regions that associate a dial-in conferencing access number with its dial plans.</span></span> <span data-ttu-id="776c8-133">具體來說：</span><span class="sxs-lookup"><span data-stu-id="776c8-133">More specifically:</span></span>
  
- <span data-ttu-id="776c8-134">撥號對應表是一組正規化規則，可指定電話號碼中的位數和模式，並將電話號碼轉譯成通話路由所需的標準 e.164 格式。</span><span class="sxs-lookup"><span data-stu-id="776c8-134">Dial plans are sets of normalization rules that specify the number and pattern of digits in a phone number, and translate the phone number into the standard E.164 format required for call routing.</span></span>
    
- <span data-ttu-id="776c8-135">電話撥入式會議存取號碼是參與者加入會議所撥打的號碼。</span><span class="sxs-lookup"><span data-stu-id="776c8-135">Dial-in conferencing access numbers are the numbers participants call to join a conference.</span></span>
    
- <span data-ttu-id="776c8-136">每個電話撥入式會議存取號碼都必須與至少一個撥號對應表相關聯。</span><span class="sxs-lookup"><span data-stu-id="776c8-136">Every dial-in conferencing access number must be associated with at least one dial plan.</span></span> 
    
- <span data-ttu-id="776c8-137">每個撥號對應表都與會議地區相關聯。</span><span class="sxs-lookup"><span data-stu-id="776c8-137">Every dial plan is associated with a conferencing region.</span></span>
    
<span data-ttu-id="776c8-138">當您建立撥號對應表時，您可以指定套用至撥號對應表的電話撥入式會議區域。</span><span class="sxs-lookup"><span data-stu-id="776c8-138">When you create a dial plan, you specify the dial-in conferencing region that applies to the dial plan.</span></span> <span data-ttu-id="776c8-139">當您建立撥入存取號碼時，請選取相關聯的撥號對應表的存取號碼相關聯的地區。</span><span class="sxs-lookup"><span data-stu-id="776c8-139">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>
  
<span data-ttu-id="776c8-140">您也可以指定撥號對應表的範圍：「使用者範圍」、「集區」範圍或「網站範圍」。</span><span class="sxs-lookup"><span data-stu-id="776c8-140">You also specify the scope of the dial plan: user scope, pool scope, or site scope.</span></span> <span data-ttu-id="776c8-141">每個使用者都會從套用至使用者的最窄範圍指派撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="776c8-141">Every user is assigned the dial plan from the narrowest scope that applies to the user.</span></span> <span data-ttu-id="776c8-142">例如，如果有適用的使用者層級撥號對應表，則會指派給該使用者。</span><span class="sxs-lookup"><span data-stu-id="776c8-142">For example, a user is assigned a user-level dial plan, if one applies.</span></span> <span data-ttu-id="776c8-143">若未套用使用者層級撥號對應表，則會為使用者指派集區層級撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="776c8-143">If a user-level dial plan does not apply, the user is assigned a pool-level dial plan.</span></span> <span data-ttu-id="776c8-144">若未套用集區層級撥號對應表，則會為該使用者指派網站層級撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="776c8-144">If a pool-level dial plan does not apply, the user is assigned a site-level dial plan.</span></span> <span data-ttu-id="776c8-145">若未套用網站層級撥號對應表，則會將全域撥號對應表指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="776c8-145">If a site-level dial plan does not apply, the user is assigned the global dial plan.</span></span> 
  
<span data-ttu-id="776c8-146">在您設定撥號對應表之前，請務必規劃您想要命名及使用區域的方式。</span><span class="sxs-lookup"><span data-stu-id="776c8-146">Before you configure the dial plans, is it important to plan how you want to name and use regions.</span></span> <span data-ttu-id="776c8-147">下列考慮適用于電話撥入式會議地區：</span><span class="sxs-lookup"><span data-stu-id="776c8-147">The following considerations apply to dial-in conferencing regions:</span></span>
  
- <span data-ttu-id="776c8-148">地區通常是與辦公室或辦事處群組相關聯的地理區域。</span><span class="sxs-lookup"><span data-stu-id="776c8-148">A region is typically a geographical area that is associated with an office or group of offices.</span></span>
    
- <span data-ttu-id="776c8-149">語言與撥入存取號碼相關聯。</span><span class="sxs-lookup"><span data-stu-id="776c8-149">Languages are associated with dial-in access numbers.</span></span> <span data-ttu-id="776c8-150">如果您支援具有多種語言的地理區域，您應該決定要如何定義區域以支援多種語言。</span><span class="sxs-lookup"><span data-stu-id="776c8-150">If you support geographical areas that have multiple languages, you should decide how you want to define regions to support the multiple languages.</span></span> <span data-ttu-id="776c8-151">例如，您可以根據地理及語言的組合來定義多個地區，也可以根據地理位置定義單一區域，並為每一種語言使用不同的撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="776c8-151">For example, you might define multiple regions based on a combination of geography and language, or you might define a single region based on geography and have a different dial-in access numbers for each language.</span></span>
    
- <span data-ttu-id="776c8-152">當使用者排程會議時，會議預設會使用該使用者的撥號對應表所指定的地區。</span><span class="sxs-lookup"><span data-stu-id="776c8-152">When a user schedules a meeting, by default the meeting uses the region specified by that user's dial plan.</span></span>
    
- <span data-ttu-id="776c8-153">預設會在會議邀請中包含區域的所有撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="776c8-153">By default, all of the dial-in access numbers for the region are included in the meeting invitation.</span></span>
    
- <span data-ttu-id="776c8-154">請務必將地區命名為區域，使其清晰辨識。</span><span class="sxs-lookup"><span data-stu-id="776c8-154">It is important to name regions so that they are clearly recognizable.</span></span> <span data-ttu-id="776c8-155">使用者可以使用地區名稱來變更會議的區域，以邀請中包含不同的存取號碼。</span><span class="sxs-lookup"><span data-stu-id="776c8-155">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span></span> <span data-ttu-id="776c8-156"> (當使用者使用 Outlook 排程會議時，使用者會使用商務用 Skype 的線上會議增益集來變更地區) 。</span><span class="sxs-lookup"><span data-stu-id="776c8-156">(When users use Outlook to schedule a meeting, the user uses the Online Meeting Add-in for Skype for Business to change the region).</span></span>
    
- <span data-ttu-id="776c8-157">應該設計區域，以便任何想要撥入會議的被邀請者，都可以在會議邀請中看到本機存取號碼。</span><span class="sxs-lookup"><span data-stu-id="776c8-157">Regions should be designed so that any invitee who wants to dial into a conference can see a local access number in the conference invitation.</span></span>
    
- <span data-ttu-id="776c8-158">您可以設定地區內的存取號碼顯示在 [電話撥入式會議設定] 頁面 (，也就是透過商務用 Skype Server 管理命令介面 Cmdlet 出現在會議邀請) 中的順序。</span><span class="sxs-lookup"><span data-stu-id="776c8-158">You can configure the order in which access numbers within a region appear on the Dial-in Conferencing Settings page (and, therefore, the order in which they appear in the conference invitation) by using Skype for Business Server Management Shell cmdlets.</span></span>
    
- <span data-ttu-id="776c8-159">任何位置的任何使用者都可以撥打任何撥入存取號碼，以加入會議。</span><span class="sxs-lookup"><span data-stu-id="776c8-159">Any user from any location can call any dial-in access number to join a conference.</span></span>
    
<span data-ttu-id="776c8-160">如需建立撥號對應表的詳細資訊，請參閱 [在商務用 Skype Server 中建立或修改撥號對應](../../deploy/deploy-enterprise-voice/dial-plans.md) 表，以及 [在商務用 skype 中建立或修改正規化規則](../../deploy/deploy-enterprise-voice/normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="776c8-160">For more information about creating a dial plan, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) and [Create or modify a normalization rule in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span></span> 
  
## <a name="plan-for-conference-directories"></a><span data-ttu-id="776c8-161">規劃會議目錄</span><span class="sxs-lookup"><span data-stu-id="776c8-161">Plan for conference directories</span></span>

<span data-ttu-id="776c8-162">會議目錄會維護參與者在使用商務用 Skype 時加入會議時所用的字母數位會議識別碼之間的對應，以及電話撥入式會議參與者用來加入會議的僅限數位會議識別碼。</span><span class="sxs-lookup"><span data-stu-id="776c8-162">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="776c8-163">會議識別碼的格式如下：</span><span class="sxs-lookup"><span data-stu-id="776c8-163">The format of the conference ID is as follows:</span></span>
  

\<housekeeping digit (1 digit)\>\<conference directory (usually 1-2 digits)\>\<conference number (variable number of digits\>\<check digit (1 digit)\>


<span data-ttu-id="776c8-164">建立多個會議目錄可確保會議 IDs 持續縮短，直到建立大量會議為止。</span><span class="sxs-lookup"><span data-stu-id="776c8-164">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="776c8-165">在組織中，每位使用者的會議數目為典型，我們建議您針對集區中的每個999使用者建立一個會議目錄。</span><span class="sxs-lookup"><span data-stu-id="776c8-165">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="776c8-166">使用這種指導方針，會議 IDs 一般會變小。</span><span class="sxs-lookup"><span data-stu-id="776c8-166">Using this guideline, the conference IDs can generally be kept small.</span></span> <span data-ttu-id="776c8-167">不過，一旦集區 (的會議目錄數目) 超過9，會議識別碼號碼就會成長以支援其他會議。</span><span class="sxs-lookup"><span data-stu-id="776c8-167">However, once the number of conference directories (across the pools) exceed 9, the Conference ID number will grow to support additional conferences.</span></span>
  
## <a name="plan-for-a-conferencing-policy-that-allows-dial-in-access"></a><span data-ttu-id="776c8-168">規劃允許撥入存取的會議原則</span><span class="sxs-lookup"><span data-stu-id="776c8-168">Plan for a conferencing policy that allows dial-in access</span></span>

<span data-ttu-id="776c8-169">當您設定會議原則時，必須啟用會議以進行撥入存取。</span><span class="sxs-lookup"><span data-stu-id="776c8-169">Conferences must be enabled for dial-in access when you configure conferencing policies.</span></span> <span data-ttu-id="776c8-170">根據預設，啟用撥入功能的會議會在會議邀請中包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="776c8-170">By default, conferences that are enabled for dial-in access include the following information in the conference invitation:</span></span>
  
- <span data-ttu-id="776c8-171">識別會議的數值會議識別碼</span><span class="sxs-lookup"><span data-stu-id="776c8-171">A numeric conference ID that identifies the conference</span></span>
    
- <span data-ttu-id="776c8-172">一個或多個 PSTN 存取號碼</span><span class="sxs-lookup"><span data-stu-id="776c8-172">One or more PSTN access numbers</span></span>
    
- <span data-ttu-id="776c8-173">[電話撥入式會議設定] 頁面的連結，其中包含其相關語言的完整存取號碼清單。用來建立、重設或解除封鎖個人識別碼 (Pin 碼的位置) ;和其他資訊，例如雙音調多重頻率 (DTMF) 控制項</span><span class="sxs-lookup"><span data-stu-id="776c8-173">A link to a Dial-in Conferencing Settings page, which contains a complete list of access numbers with their associated languages; a place to create, reset, or unblock personal identification numbers (PINs); and other information, such as dual-tone multi-frequency (DTMF) controls</span></span>
    
<span data-ttu-id="776c8-174">如需有關會議原則的詳細資訊，請參閱在商務用 [Skype server 中設定電話撥入式會議](../../deploy/deploy-conferencing/dial-in-conferencing.md) ，以及 [管理商務用 skype server 中的會議原則](../../manage/conferencing/conferencing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="776c8-174">For more information about conferencing policies, see [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md) and [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>  

## <a name="support-for-enterprise-and-anonymous-users"></a><span data-ttu-id="776c8-175">支援 enterprise 和匿名使用者</span><span class="sxs-lookup"><span data-stu-id="776c8-175">Support for enterprise and anonymous users</span></span>

<span data-ttu-id="776c8-176">電話撥入式會議同時支援企業和匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="776c8-176">Dial-in conferencing supports both enterprise and anonymous users.</span></span> <span data-ttu-id="776c8-177">企業使用者在其組織內有 Active Directory 網域服務認證和商務用 Skype Server 帳戶。</span><span class="sxs-lookup"><span data-stu-id="776c8-177">Enterprise users have Active Directory Domain Services credentials and Skype for Business Server accounts within their organization.</span></span> <span data-ttu-id="776c8-178">匿名使用者在您組織內沒有企業認證。</span><span class="sxs-lookup"><span data-stu-id="776c8-178">Anonymous users do not have enterprise credentials within your organization.</span></span> <span data-ttu-id="776c8-179">在電話撥入式會議內容中，同盟協力廠商組織中使用 PSTN 連接至會議的使用者，會被視為匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="776c8-179">In the dial-in conferencing context, a user in a federated partner's organization who uses the PSTN to connect to a conference is treated like an anonymous user.</span></span> <span data-ttu-id="776c8-180">與其他環境不同，電話撥入式會議並不會驗證同盟使用者。</span><span class="sxs-lookup"><span data-stu-id="776c8-180">For dial-in conferencing, unlike other contexts, federated users are not authenticated.</span></span>
  
<span data-ttu-id="776c8-181">企業使用者或會議主席欲參加已啟用撥入存取功能的會議時，要撥打其中一個會議存取號碼，然後系統會提示他們輸入會議 ID。</span><span class="sxs-lookup"><span data-stu-id="776c8-181">Enterprise users or conference leaders who join a conference that is enabled for dial-in access dial one of the conference access numbers and then are prompted to enter the conference ID.</span></span> <span data-ttu-id="776c8-182">如果主席尚未加入會議，使用者可以輸入整合通訊 (UC) 分機 (或完整電話號碼) 和 PIN，或是等待主席准許加入會議。</span><span class="sxs-lookup"><span data-stu-id="776c8-182">If a leader has not yet joined the meeting, users can either enter their unified communications (UC) extension (or full phone number) and PIN or wait to be admitted by a leader.</span></span> <span data-ttu-id="776c8-183">會議召集人只要輸入 PIN 即可以主席身分加入會議。</span><span class="sxs-lookup"><span data-stu-id="776c8-183">The Meeting organizer can join the meeting as a leader by entering just their PIN.</span></span> <span data-ttu-id="776c8-184">前端伺服器會使用完整的電話號碼或分機和 PIN 碼的組合，將企業使用者唯一對應到其 Active Directory 認證。</span><span class="sxs-lookup"><span data-stu-id="776c8-184">The Front End Server uses the combination of full phone number or extension, and PIN, to uniquely map enterprise users to their Active Directory credentials.</span></span> <span data-ttu-id="776c8-185">因此，在會議中，企業使用者已通過驗證，而且是以名稱識別。</span><span class="sxs-lookup"><span data-stu-id="776c8-185">As a result, enterprise users are authenticated and identified by name in the conference.</span></span> <span data-ttu-id="776c8-186">企業使用者也可以擔任由召集人所預先定義的會議角色。</span><span class="sxs-lookup"><span data-stu-id="776c8-186">Enterprise users can also assume a conference role predefined by the organizer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="776c8-187">從 office IP 電話撥號或從商務用 Skype 伺服器應答撥號的企業使用者，不會提示他們輸入他們的電話號碼，因為已經過驗證。</span><span class="sxs-lookup"><span data-stu-id="776c8-187">Enterprise users who dial in from an office IP phone or from Skype for Business Server Attendant are not prompted for their phone number because they are already authenticated.</span></span> 
  
<span data-ttu-id="776c8-p118">匿名使用者欲加入電話撥入式會議時，要撥打其中一個會議存取號碼，然後系統會提示他們輸入會議 ID。未經驗證的匿名使用者還會收到提示來記錄其名稱。記錄的名稱可識別會議中未經驗證的使用者。匿名使用者要等到至少有一位主席或已驗證使用者加入會議後，才能加入會議；此外，不能指派預先定義的角色給匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="776c8-p118">Anonymous users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.</span></span>
  
> [!NOTE]
> <span data-ttu-id="776c8-p119">選擇不輸入電話號碼及 PIN 的企業使用者不會進行驗證。他們會收到提示，表示系統將記錄其名稱，並將其視為會議中的匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="776c8-p119">Enterprise users who choose not to enter their phone number and PIN are not authenticated. They are prompted to record their name and are treated as anonymous users in the conference.</span></span> 
  
<span data-ttu-id="776c8-194">當排程會議時，會議召集人可以選擇讓會議關閉或鎖定，以限制會議的存取權。</span><span class="sxs-lookup"><span data-stu-id="776c8-194">When scheduling a meeting, the meeting organizer can choose to restrict access to the meeting by making the meeting closed or locked.</span></span> <span data-ttu-id="776c8-195">在此情況下，要求撥入使用者進行驗證。</span><span class="sxs-lookup"><span data-stu-id="776c8-195">In this case, dial-in users are requested to authenticate.</span></span> 
  
- <span data-ttu-id="776c8-196">如果撥入使用者失敗或選擇 [不驗證]，他們會在主持人接受或拒絕時，將其轉接至會議廳，否則會中斷且中斷連線。</span><span class="sxs-lookup"><span data-stu-id="776c8-196">If dial-in users fail or choose not to authenticate, they are transferred to the lobby where they until a leader accepts or rejects them, or they time out and are disconnected.</span></span>
    
- <span data-ttu-id="776c8-197">在他們獲准參加會議之後，電話撥入式使用者可以參與會議的音訊部分，也可以使用電話鍵盤來執行雙音調多頻率 (DTMF) 命令。</span><span class="sxs-lookup"><span data-stu-id="776c8-197">After they are admitted to a conference, dial-in users can participate in the audio portion of the conference and can exercise dual-tone multi-frequency (DTMF) commands by using the phone keypad.</span></span>
    
- <span data-ttu-id="776c8-198">撥入領導人可以執行 DTMF 命令，以開啟或關閉參與者的靜音功能、鎖定或解除鎖定會議、允許來自會議廳的人員，以及開啟或關閉進入和結束公告。</span><span class="sxs-lookup"><span data-stu-id="776c8-198">Dial-in leaders can exercise DTMF commands to turn participants' ability to unmute on or off, lock or unlock the conference, admit people from the lobby, and turn entry and exit announcements on or off.</span></span>
    
- <span data-ttu-id="776c8-199">領導者也可以使用 DTMF 命令，讓所有人都從會議廳，這會變更會議的許可權，以允許後續加入的任何人。</span><span class="sxs-lookup"><span data-stu-id="776c8-199">Leaders can also use a DTMF command to admit everyone from the lobby, which changes the permissions of the meeting to allow anyone who subsequently joins.</span></span> 
    
- <span data-ttu-id="776c8-200">所有撥入參與者都可以執行 DTMF 命令，以聽取協助、聆聽會議名單及自行靜音。</span><span class="sxs-lookup"><span data-stu-id="776c8-200">All dial-in participants can exercise DTMF commands to hear Help, listen to the conference roster, and mute themselves.</span></span>
    
- <span data-ttu-id="776c8-201">撥入參與者 (也就是從 PSTN 撥號) 在會議期間收聽個人宣告，例如是否已靜音或 unmuted、是否正在錄製會議，或是否有人在大廳等候。</span><span class="sxs-lookup"><span data-stu-id="776c8-201">Dial-in participants (that is, whether or not they dial from the PSTN) hear personal announcements during the conference, such as whether they have been muted or unmuted, whether the meeting is being recorded, or whether someone is waiting in the lobby.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="776c8-202">透過按下連結 (而非撥入) 方式來加入會議的參與者，不會聽到個人宣告。</span><span class="sxs-lookup"><span data-stu-id="776c8-202">Participants who join the conference by clicking a link instead of dialing in do not hear personal announcements.</span></span> 
  

