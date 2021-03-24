---
title: 規劃商務用 Skype Server 的位置原則
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: 閱讀此主題以瞭解如何在商務用 Skype Server Enterprise Voice 中規劃增強型緊急服務 (E9-1-1) 部署的位置原則。
ms.openlocfilehash: 3d9c574d18351594d9773f02770e960c993ae401
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101449"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="5ca35-103">規劃商務用 Skype Server 的位置原則</span><span class="sxs-lookup"><span data-stu-id="5ca35-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="5ca35-104">閱讀此主題以瞭解如何在商務用 Skype Server Enterprise Voice 中規劃增強型緊急服務 (E9-1-1) 部署的位置原則。</span><span class="sxs-lookup"><span data-stu-id="5ca35-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5ca35-105">商務用 Skype 伺服器現在支援為用戶端設定多個緊急號碼。</span><span class="sxs-lookup"><span data-stu-id="5ca35-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="5ca35-106">如果您想要設定多個緊急號碼，必須遵循在商務用 skype [Server 中規劃多個緊急](multiple-emergency-numbers.md) 號碼的資訊，並 [在商務用 skype 中設定多個緊急號碼](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="5ca35-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="5ca35-107">您可以使用商務用 Skype 控制台或使用 [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) Cmdlet 來建立位置原則。</span><span class="sxs-lookup"><span data-stu-id="5ca35-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="5ca35-108">如需詳細資訊，請參閱 [在商務用 Skype Server 中建立位置原則](../../deploy/deploy-enterprise-voice/create-location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5ca35-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="5ca35-109">每個位置原則都包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="5ca35-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="5ca35-110">**啟用增強型9-1-1**</span><span class="sxs-lookup"><span data-stu-id="5ca35-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="5ca35-111">啟用此值時，會為用戶端啟用增強型緊急服務， (E9-1-1) 。</span><span class="sxs-lookup"><span data-stu-id="5ca35-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="5ca35-112">當用戶端註冊時，它會嘗試從 Location 資訊服務取得位置，並將位置資訊包含在緊急通話的一部分中。</span><span class="sxs-lookup"><span data-stu-id="5ca35-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="5ca35-113">**位置**</span><span class="sxs-lookup"><span data-stu-id="5ca35-113">**Location**</span></span>
  
<span data-ttu-id="5ca35-114">只有在啟用 **增強型 9-1-1** 時，才會使用此設定。</span><span class="sxs-lookup"><span data-stu-id="5ca35-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="5ca35-115">您可以設定 **位置** 設定，以定義用戶端行為，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5ca35-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="5ca35-116">將值設為 [ **否** ] 表示將不會提示使用者輸入位置。</span><span class="sxs-lookup"><span data-stu-id="5ca35-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="5ca35-117">將值設為 **[是]** ，表示系統會提示使用者輸入位置，但可以關閉提示。</span><span class="sxs-lookup"><span data-stu-id="5ca35-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="5ca35-118">將值設定為 **免責聲明** 表示會提示使用者輸入位置，而且會在使用者嘗試消除提示時顯示免責聲明。</span><span class="sxs-lookup"><span data-stu-id="5ca35-118">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="5ca35-119">在所有情況下，使用者都可以繼續使用用戶端。</span><span class="sxs-lookup"><span data-stu-id="5ca35-119">In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5ca35-120">若使用者在啟用 E9-1-1 前手動輸入位置，將不會顯示免責聲明文字。</span><span class="sxs-lookup"><span data-stu-id="5ca35-120">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1.</span></span> <span data-ttu-id="5ca35-121">已查看免責聲明的使用者將不會查看免責聲明文字的更新。</span><span class="sxs-lookup"><span data-stu-id="5ca35-121">Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="5ca35-122">**增強型緊急服務免責聲明**</span><span class="sxs-lookup"><span data-stu-id="5ca35-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="5ca35-123">此設定指定使用者在其取消提示的位置時所看到的免責聲明。</span><span class="sxs-lookup"><span data-stu-id="5ca35-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="5ca35-124">在商務用 Skype Server 中，您可以使用位置原則，針對不同的地區設定或不同的使用者組設定不同的免責聲明。</span><span class="sxs-lookup"><span data-stu-id="5ca35-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="5ca35-125">**緊急撥號字串 (E9-1-1 撥號號碼)**</span><span class="sxs-lookup"><span data-stu-id="5ca35-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="5ca35-126">此撥號字串 (較少的前置 "+"，但包含使用者撥號對應表所完成的任何正規化) 表示通話是緊急通話。</span><span class="sxs-lookup"><span data-stu-id="5ca35-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="5ca35-127">[ **緊急撥號] 字串** 會使用戶端在通話中包含位置和回呼資訊。</span><span class="sxs-lookup"><span data-stu-id="5ca35-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5ca35-128">如果您的組織未使用外部線路存取首碼，您不需要建立對應的撥號對應表正規化規則，可在執行商務用 Skype 伺服器的伺服器上的呼叫輸出路由傳送呼叫之前，將 "+" 新增至911字串。由於位置原則的結果，商務用 Skype 用戶端會自動前置 "+"。</span><span class="sxs-lookup"><span data-stu-id="5ca35-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="5ca35-129">不過，如果您的網站使用外部存取前置詞，您必須將正規化規則新增至適用的撥號對應表原則，以去掉外部存取前置詞並新增 "+"。</span><span class="sxs-lookup"><span data-stu-id="5ca35-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="5ca35-130">例如，如果您的位置使用外部存取前置詞9，而且使用者可撥打 9 911 撥打緊急電話，用戶端會使用其撥號對應表原則，在來電者位置設定檔中的路由評估撥號號碼之前，先將此值標準化為 + 911。</span><span class="sxs-lookup"><span data-stu-id="5ca35-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="5ca35-131">**緊急撥號字串遮罩 (E9-1-1 撥號遮罩)**</span><span class="sxs-lookup"><span data-stu-id="5ca35-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="5ca35-132">以分號分隔的撥號字串清單，可轉譯成指定的 **緊急撥號字串**。</span><span class="sxs-lookup"><span data-stu-id="5ca35-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="5ca35-133">例如，您可能想要新增112，也就是歐洲大多數的緊急服務號碼。</span><span class="sxs-lookup"><span data-stu-id="5ca35-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="5ca35-134">從歐洲訪問商務用 Skype 使用者可能不會知道911是美國的緊急電話號碼，但可以撥打112並取得相同的結果。</span><span class="sxs-lookup"><span data-stu-id="5ca35-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="5ca35-135">如使用緊急撥號字串，請勿在每個號碼前加上 "+"，而且如果您使用外部行存取碼，請確定使用者的撥號對應表原則中有正規化規則可去掉存取碼位。</span><span class="sxs-lookup"><span data-stu-id="5ca35-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="5ca35-136">**PSTN 使用方式**</span><span class="sxs-lookup"><span data-stu-id="5ca35-136">**PSTN usage**</span></span>
  
<span data-ttu-id="5ca35-137">PSTN 使用方式的名稱，此介面包含決定 SIP 主幹、PSTN 閘道或 ELIN 閘道緊急通話將前往的路由路徑。</span><span class="sxs-lookup"><span data-stu-id="5ca35-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5ca35-138">一個位置原則只能有一個可用的使用方式。</span><span class="sxs-lookup"><span data-stu-id="5ca35-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="5ca35-139">這種 PSTN 使用方式會覆寫指派給使用者語音原則的 PSTN 使用方式，但是只適用于撥入緊急撥號字串或其中一個緊急撥號字串遮罩的來電。</span><span class="sxs-lookup"><span data-stu-id="5ca35-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="5ca35-140">**通知 URI**</span><span class="sxs-lookup"><span data-stu-id="5ca35-140">**Notification URI**</span></span>
  
<span data-ttu-id="5ca35-141">指定在進行緊急通話時，接收立即訊息 (IM) 通知的安全性人員一或多個 SIP URIs。</span><span class="sxs-lookup"><span data-stu-id="5ca35-141">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed.</span></span> <span data-ttu-id="5ca35-142">支援通訊群組。</span><span class="sxs-lookup"><span data-stu-id="5ca35-142">Distribution groups are supported.</span></span>
  
 <span data-ttu-id="5ca35-143">**會議 URI**</span><span class="sxs-lookup"><span data-stu-id="5ca35-143">**Conference URI**</span></span>
  
<span data-ttu-id="5ca35-144">指定「直接向內撥號 (已) 號碼 (通常是) 的安全性服務台號碼，應警衛在緊急通話時進行此設定。</span><span class="sxs-lookup"><span data-stu-id="5ca35-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="5ca35-145">**會議模式**</span><span class="sxs-lookup"><span data-stu-id="5ca35-145">**Conference Mode**</span></span>
  
<span data-ttu-id="5ca35-146">指定是否要使用單向或雙向通訊，將會議 URI 警衛至緊急通話。</span><span class="sxs-lookup"><span data-stu-id="5ca35-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="5ca35-147">**位置重新整理間隔**</span><span class="sxs-lookup"><span data-stu-id="5ca35-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="5ca35-148">指定從位置資訊服務之位置更新之用戶端要求 (的時間) （以小時為單位）。</span><span class="sxs-lookup"><span data-stu-id="5ca35-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="5ca35-149">此值可設為1到12之間的任何值。</span><span class="sxs-lookup"><span data-stu-id="5ca35-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="5ca35-150">預設值為 4。</span><span class="sxs-lookup"><span data-stu-id="5ca35-150">The default value is 4.</span></span>
