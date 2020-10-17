---
title: Lync Server 2013：定義位置原則
description: Lync Server 2013：定義位置原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fddd5b2ce34e44240162e886672a236789857e7b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567535"
---
# <a name="defining-the-location-policy-for-lync-server-2013"></a><span data-ttu-id="6589b-103">定義 Lync Server 2013 的位置原則</span><span class="sxs-lookup"><span data-stu-id="6589b-103">Defining the location policy for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6589b-104">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="6589b-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="6589b-105">每個位置原則都包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="6589b-105">Each location policy contains the following information:</span></span>

  - <span data-ttu-id="6589b-106">**已啟用緊急服務**</span><span class="sxs-lookup"><span data-stu-id="6589b-106">**Emergency Services Enabled**</span></span>  
    <span data-ttu-id="6589b-107">當這個值為 **[是]** 時，用戶端會啟用 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="6589b-107">When this value is **Yes**, the client is enabled for E9-1-1.</span></span> <span data-ttu-id="6589b-108">當用戶端註冊時，它會嘗試從 Location 資訊服務取得位置，並將位置資訊包含在緊急通話的一部分中。</span><span class="sxs-lookup"><span data-stu-id="6589b-108">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>

<!-- end list -->

  - <span data-ttu-id="6589b-109">**需要位置**</span><span class="sxs-lookup"><span data-stu-id="6589b-109">**Location Required**</span></span>  
    <span data-ttu-id="6589b-110">只有當**啟用的服務**   設定為 **[是]** 時，才使用此設定。</span><span class="sxs-lookup"><span data-stu-id="6589b-110">This setting is used only when **Emergence Services Enabled** is set to **Yes**.</span></span>
    
    <span data-ttu-id="6589b-111">您可以設定 [ **必要的位置** ] 設定以定義用戶端行為。</span><span class="sxs-lookup"><span data-stu-id="6589b-111">You can configure the **Location Required** setting to define the client behavior.</span></span> <span data-ttu-id="6589b-112">將值設為 [ **否** ] 表示將不會提示使用者輸入位置。</span><span class="sxs-lookup"><span data-stu-id="6589b-112">Setting the value to **No** means that the user will not be prompted for a location.</span></span> <span data-ttu-id="6589b-113">將值設為 **[是]** ，表示系統會提示使用者輸入位置，但可以關閉提示。</span><span class="sxs-lookup"><span data-stu-id="6589b-113">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="6589b-114">將值設定為 **免責聲明** 表示會提示使用者輸入位置，而且會在使用者嘗試消除提示時顯示免責聲明。</span><span class="sxs-lookup"><span data-stu-id="6589b-114">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="6589b-115">在所有情況下，使用者都可以繼續使用用戶端。</span><span class="sxs-lookup"><span data-stu-id="6589b-115">In all cases, the user can continue to use the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6589b-116">若使用者在啟用 E9-1-1 前手動輸入位置，將不會顯示免責聲明文字。</span><span class="sxs-lookup"><span data-stu-id="6589b-116">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1.</span></span> <span data-ttu-id="6589b-117">已查看免責聲明的使用者將不會查看免責聲明文字的更新。</span><span class="sxs-lookup"><span data-stu-id="6589b-117">Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="6589b-118">**增強型緊急服務免責聲明**</span><span class="sxs-lookup"><span data-stu-id="6589b-118">**Enhanced Emergency Service Disclaimer**</span></span>  
    <span data-ttu-id="6589b-119">此設定指定使用者在其取消提示的位置時所看到的免責聲明。</span><span class="sxs-lookup"><span data-stu-id="6589b-119">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="6589b-120">在 Lync Server 2013 中，您可以使用位置原則為不同的地區設定或不同的使用者集合設定不同的免責聲明。</span><span class="sxs-lookup"><span data-stu-id="6589b-120">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6589b-121">此位置原則設定與 Lync Server 2010 不同，您可以使用 <STRONG>CsEnhancedEmergencyServiceDisclaimer</STRONG> Cmdlet 來設定整個組織的全域免責聲明。</span><span class="sxs-lookup"><span data-stu-id="6589b-121">This location policy setting differs from Lync Server 2010, where you used the <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet to set a global disclaimer for the entire organization.</span></span> <span data-ttu-id="6589b-122">若全域免責聲明已存在，您必須在位置原則中指定該免責聲明。</span><span class="sxs-lookup"><span data-stu-id="6589b-122">If a global disclaimer already exists, you need to specify that disclaimer in location policy.</span></span> <span data-ttu-id="6589b-123">也就是說，Lync Server 2013 只會使用在位置原則中指定的免責聲明。</span><span class="sxs-lookup"><span data-stu-id="6589b-123">That is, Lync Server 2013 uses only disclaimers specified in location policy.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="6589b-124">**緊急撥號字串**</span><span class="sxs-lookup"><span data-stu-id="6589b-124">**Emergency Dial String**</span></span>  
    <span data-ttu-id="6589b-125">此撥號字串 (較少的前置 "+"，但包括 Lync 使用者撥號對應表所執行的任何正規化) 表示通話是緊急通話。</span><span class="sxs-lookup"><span data-stu-id="6589b-125">This dial string (less the leading “+”, but including any normalization done by the Lync user’s Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="6589b-126">[ **緊急撥號] 字串** 會使用戶端在通話中包含位置和回呼資訊。</span><span class="sxs-lookup"><span data-stu-id="6589b-126">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6589b-127">如果您的組織未使用外部線路存取首碼，您不需要建立對應的撥號對應表正規化規則，在將呼叫傳送至 Lync 集區伺服器上的輸出路由之前，將 "+" 新增至911字串;「+」會因位置原則而自動加上 Lync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="6589b-127">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a “+” to the 911 string prior to sending the call to Outbound Routing on a Lync pool server; the “+” will be automatically prepended by the Lync client as a result of the location policy.</span></span> <span data-ttu-id="6589b-128">不過，如果您的網站使用外部存取前置詞，您必須將正規化規則新增至適用的撥號對應表原則，以去掉外部存取前置詞並新增 "+"。</span><span class="sxs-lookup"><span data-stu-id="6589b-128">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the “+”.</span></span> <span data-ttu-id="6589b-129">例如，如果您的位置使用外部存取前置詞9，而且使用者可撥打 9 &nbsp; 911 來進行緊急通話，用戶端會使用其撥號對應表原則，在來電者位置設定檔中的路由評估撥號號碼之前，先將此值與 + 911 進行正常化。</span><span class="sxs-lookup"><span data-stu-id="6589b-129">For example, if your location uses an external access prefix of 9 and a user dials 9&nbsp;911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller’s location profile.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="6589b-130">**緊急撥號字串遮罩**</span><span class="sxs-lookup"><span data-stu-id="6589b-130">**Emergency Dial String Masks**</span></span>  
    <span data-ttu-id="6589b-131">以分號分隔的撥號字串清單，可轉譯成指定的 **緊急撥號字串**。</span><span class="sxs-lookup"><span data-stu-id="6589b-131">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="6589b-132">例如，您可能想要新增112，也就是歐洲大多數的緊急服務號碼。</span><span class="sxs-lookup"><span data-stu-id="6589b-132">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="6589b-133">從歐洲取得的 Lync 使用者可能不會知道911是美國的緊急電話號碼，但可以撥打112並取得相同的結果。</span><span class="sxs-lookup"><span data-stu-id="6589b-133">A visiting Lync user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="6589b-134">如使用緊急撥號字串，請勿在每個號碼前加上 "+"，而且如果您使用外部行存取碼，請確定使用者的撥號對應表原則中有正規化規則可去掉存取碼位。</span><span class="sxs-lookup"><span data-stu-id="6589b-134">As with the Emergency Dial String, do not include a “+” before each number, and if you use external line access codes, be sure there are normalization rules in the user’s Dial Plan policy to strip off the access code digit.</span></span>

<!-- end list -->

  - <span data-ttu-id="6589b-135">**PSTN 使用方式**</span><span class="sxs-lookup"><span data-stu-id="6589b-135">**PSTN Usage**</span></span>  
    <span data-ttu-id="6589b-136">PSTN 使用方式的名稱，此介面包含決定 SIP 主幹、PSTN 閘道或 ELIN 閘道緊急通話將前往的路由路徑。</span><span class="sxs-lookup"><span data-stu-id="6589b-136">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6589b-137">一個位置原則只能有一個可用的使用方式。</span><span class="sxs-lookup"><span data-stu-id="6589b-137">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="6589b-138">這種 PSTN 使用方式會覆寫指派給使用者語音原則的 PSTN 使用方式，但是只適用于撥入緊急撥號字串或其中一個緊急撥號字串遮罩的來電。</span><span class="sxs-lookup"><span data-stu-id="6589b-138">This PSTN Usage overrides the PSTN Usages assigned to the user’s voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="6589b-139">**通知 URI**</span><span class="sxs-lookup"><span data-stu-id="6589b-139">**Notification URI**</span></span>  
    <span data-ttu-id="6589b-140">指定在進行緊急通話時，接收立即訊息 (IM) 通知的安全性人員一或多個 SIP URIs。</span><span class="sxs-lookup"><span data-stu-id="6589b-140">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed.</span></span> <span data-ttu-id="6589b-141">支援通訊群組。</span><span class="sxs-lookup"><span data-stu-id="6589b-141">Distribution groups are supported.</span></span>

<!-- end list -->

  - <span data-ttu-id="6589b-142">**會議 URI**</span><span class="sxs-lookup"><span data-stu-id="6589b-142">**Conference URI**</span></span>  
    <span data-ttu-id="6589b-143">指定「直接向內撥號 (已) 號碼 (通常是) 的安全性服務台號碼，應警衛在緊急通話時進行此設定。</span><span class="sxs-lookup"><span data-stu-id="6589b-143">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span>

<!-- end list -->

  - <span data-ttu-id="6589b-144">**會議模式**</span><span class="sxs-lookup"><span data-stu-id="6589b-144">**Conference Mode**</span></span>  
    <span data-ttu-id="6589b-145">指定是否要使用單向或雙向通訊，將會議 URI 警衛至緊急通話。</span><span class="sxs-lookup"><span data-stu-id="6589b-145">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span>

<!-- end list -->

  - <span data-ttu-id="6589b-146">**位置重新整理間隔**</span><span class="sxs-lookup"><span data-stu-id="6589b-146">**Location Refresh Interval**</span></span>  
    <span data-ttu-id="6589b-147">指定從位置資訊服務之位置更新之用戶端要求 (的時間) （以小時為單位）。</span><span class="sxs-lookup"><span data-stu-id="6589b-147">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="6589b-148">此值可設為1到12之間的任何值。</span><span class="sxs-lookup"><span data-stu-id="6589b-148">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="6589b-149">預設值為 4。</span><span class="sxs-lookup"><span data-stu-id="6589b-149">The default value is 4.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

