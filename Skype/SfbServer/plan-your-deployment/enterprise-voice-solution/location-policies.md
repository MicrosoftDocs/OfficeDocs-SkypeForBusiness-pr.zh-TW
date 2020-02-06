---
title: 規劃商務用 Skype Server 的位置原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 請閱讀本主題，以瞭解如何在商務用 Skype Server Enterprise Voice 中規劃增強式緊急服務（E9-1）部署的位置原則。
ms.openlocfilehash: 5064197dd8d23113d7bfeca30fd3596d5ee89c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802803"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="48432-103">規劃商務用 Skype Server 的位置原則</span><span class="sxs-lookup"><span data-stu-id="48432-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="48432-104">請閱讀本主題，以瞭解如何在商務用 Skype Server Enterprise Voice 中規劃增強式緊急服務（E9-1）部署的位置原則。</span><span class="sxs-lookup"><span data-stu-id="48432-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="48432-105">商務用 Skype 伺服器現在支援設定用戶端的多個緊急電話號碼。</span><span class="sxs-lookup"><span data-stu-id="48432-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="48432-106">如果您想要設定多個緊急電話號碼，您必須遵循[規劃商務用 Skype Server 中的多個緊急電話號碼](multiple-emergency-numbers.md)，並在[商務用 skype 中設定多個緊急電話](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)號碼。</span><span class="sxs-lookup"><span data-stu-id="48432-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="48432-107">您可以使用商務用 Skype 的 [控制台] 或使用[CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) Cmdlet 來建立位置原則。</span><span class="sxs-lookup"><span data-stu-id="48432-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="48432-108">如需詳細資訊，請參閱[在商務用 Skype Server 中建立位置原則](../../deploy/deploy-enterprise-voice/create-location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="48432-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="48432-109">每個位置原則都包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="48432-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="48432-110">**啟用增強型9-1-1**</span><span class="sxs-lookup"><span data-stu-id="48432-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="48432-111">啟用此值時，會啟用用戶端以增強緊急服務（E9-1-1）。</span><span class="sxs-lookup"><span data-stu-id="48432-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="48432-112">用戶端註冊時，它會嘗試從位置資訊服務取得位置，並將位置資訊包含在緊急通話的一部分。</span><span class="sxs-lookup"><span data-stu-id="48432-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="48432-113">**位置**</span><span class="sxs-lookup"><span data-stu-id="48432-113">**Location**</span></span>
  
<span data-ttu-id="48432-114">此設定僅在啟用 [**啟用增強型 9-1-1** ] 時使用。</span><span class="sxs-lookup"><span data-stu-id="48432-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="48432-115">您可以設定**位置**設定，以定義用戶端行為，如下所示：</span><span class="sxs-lookup"><span data-stu-id="48432-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="48432-116">將此值設定為 [**否**] 表示系統不會提示使用者輸入位置。</span><span class="sxs-lookup"><span data-stu-id="48432-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="48432-117">將此值設定為 **[是]** 表示系統會提示使用者輸入位置，但可以關閉提示。</span><span class="sxs-lookup"><span data-stu-id="48432-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="48432-118">將此值設定為 [**免責聲明**] 表示系統會提示使用者輸入位置，而且在他們嘗試關閉提示時也會顯示免責聲明。</span><span class="sxs-lookup"><span data-stu-id="48432-118">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="48432-119">在任何情況下，使用者都可以繼續使用用戶端。</span><span class="sxs-lookup"><span data-stu-id="48432-119">In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="48432-120">如果使用者在啟用 E9 前手動輸入位置，則不會顯示免責聲明文字-1-1。</span><span class="sxs-lookup"><span data-stu-id="48432-120">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1.</span></span> <span data-ttu-id="48432-121">已查看免責聲明的使用者將不會看到免責聲明文字的更新。</span><span class="sxs-lookup"><span data-stu-id="48432-121">Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="48432-122">**增強的緊急服務免責聲明**</span><span class="sxs-lookup"><span data-stu-id="48432-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="48432-123">此設定會指定使用者在關閉位置提示時所看到的免責聲明。</span><span class="sxs-lookup"><span data-stu-id="48432-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="48432-124">在商務用 Skype Server 中，您可以使用位置原則，針對不同的地區設定或不同的使用者集設定不同的免責聲明。</span><span class="sxs-lookup"><span data-stu-id="48432-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="48432-125">**緊急撥號字串（E9-1-1 個撥號號碼）**</span><span class="sxs-lookup"><span data-stu-id="48432-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="48432-126">這個撥號字串（較少前導 "+"，但包含使用者撥號計畫所完成的任何正常化）表示通話是緊急通話。</span><span class="sxs-lookup"><span data-stu-id="48432-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="48432-127">[**緊急撥號字串**] 會讓用戶端在通話中加入位置和回呼資訊。</span><span class="sxs-lookup"><span data-stu-id="48432-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="48432-128">如果您的組織未使用外部線路存取首碼，您就不需要建立對應的撥號方案正常化規則，在執行商務用 Skype Server 的伺服器上，將呼叫新增至911字串。[+] 會自動前置商務用 Skype 用戶端，因為位置原則。</span><span class="sxs-lookup"><span data-stu-id="48432-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="48432-129">不過，如果您的網站使用外部存取前置詞，您必須將正常化規則新增到可分割外部存取前置詞的適用撥號方案原則，並新增 "+"。</span><span class="sxs-lookup"><span data-stu-id="48432-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="48432-130">例如，如果您的位置使用外部存取首碼9，且使用者將 9 911 撥打電話給您，則在呼叫者的位置設定檔中，用戶端將會使用其撥號方案原則將此值與 + 911 標準化。</span><span class="sxs-lookup"><span data-stu-id="48432-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="48432-131">**緊急撥號字串遮罩（E9-1-1）撥號遮罩）**</span><span class="sxs-lookup"><span data-stu-id="48432-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="48432-132">以分號分隔的撥號字串清單，可翻譯成指定的**緊急撥號字串**。</span><span class="sxs-lookup"><span data-stu-id="48432-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="48432-133">例如，您可能會想要新增112，這是大多數歐洲的緊急服務號碼。</span><span class="sxs-lookup"><span data-stu-id="48432-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="48432-134">從歐洲造訪商務用 Skype 使用者可能不知道911是美國的緊急電話號碼，但他們可以撥打112並取得相同的結果。</span><span class="sxs-lookup"><span data-stu-id="48432-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="48432-135">就像緊急撥號字串一樣，請不要在每個數位前加上 "+"，而且如果您使用外部線路存取代碼，請務必在使用者的撥號計畫原則中有正常化規則來剝離存取代碼位數。</span><span class="sxs-lookup"><span data-stu-id="48432-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="48432-136">**PSTN 使用量**</span><span class="sxs-lookup"><span data-stu-id="48432-136">**PSTN usage**</span></span>
  
<span data-ttu-id="48432-137">PSTN 使用的名稱，其中包含判斷哪些 SIP 幹線、PSTN 閘道或 ELIN 閘道緊急呼叫將前往的路由路徑。</span><span class="sxs-lookup"><span data-stu-id="48432-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="48432-138">位置原則只能指派一個用法。</span><span class="sxs-lookup"><span data-stu-id="48432-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="48432-139">此 PSTN 使用會覆寫指派給使用者語音原則的 PSTN 使用量，但只適用于緊急撥號字串或其中一個緊急撥號字串遮罩的呼叫。</span><span class="sxs-lookup"><span data-stu-id="48432-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="48432-140">**通知 URI**</span><span class="sxs-lookup"><span data-stu-id="48432-140">**Notification URI**</span></span>
  
<span data-ttu-id="48432-141">指定在發出緊急通話時接收立即訊息（IM）通知的安全性人員的一個或多個 SIP Uri。</span><span class="sxs-lookup"><span data-stu-id="48432-141">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed.</span></span> <span data-ttu-id="48432-142">支援通訊群組。</span><span class="sxs-lookup"><span data-stu-id="48432-142">Distribution groups are supported.</span></span>
  
 <span data-ttu-id="48432-143">**會議 URI**</span><span class="sxs-lookup"><span data-stu-id="48432-143">**Conference URI**</span></span>
  
<span data-ttu-id="48432-144">指定在發出緊急通話時，應 conferenced 的直接向內撥號（已登錄）號碼（通常是安全服務台號碼）。</span><span class="sxs-lookup"><span data-stu-id="48432-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="48432-145">**會議模式**</span><span class="sxs-lookup"><span data-stu-id="48432-145">**Conference Mode**</span></span>
  
<span data-ttu-id="48432-146">指定是否要使用單向或雙向通訊，將會議 URI conferenced 到緊急通話中。</span><span class="sxs-lookup"><span data-stu-id="48432-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="48432-147">**位置重新整理間隔**</span><span class="sxs-lookup"><span data-stu-id="48432-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="48432-148">指定從位置資訊服務傳送位置更新之用戶端要求的時間長度（以小時為單位）。</span><span class="sxs-lookup"><span data-stu-id="48432-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="48432-149">這個值可以設定為1到12之間的任何值。</span><span class="sxs-lookup"><span data-stu-id="48432-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="48432-150">預設值為4。</span><span class="sxs-lookup"><span data-stu-id="48432-150">The default value is 4.</span></span>
  

