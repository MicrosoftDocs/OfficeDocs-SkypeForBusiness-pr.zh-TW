---
title: Lync Server 2013：定義位置原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26b0e9aca4b3e66202d6b3c4a47b90db4f207fda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a><span data-ttu-id="437f3-102">定義 Lync Server 2013 的位置原則</span><span class="sxs-lookup"><span data-stu-id="437f3-102">Defining the location policy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="437f3-103">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="437f3-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="437f3-104">每個位置原則都包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="437f3-104">Each location policy contains the following information:</span></span>

  - <span data-ttu-id="437f3-105">**已啟用緊急服務**</span><span class="sxs-lookup"><span data-stu-id="437f3-105">**Emergency Services Enabled**</span></span>  
    <span data-ttu-id="437f3-106">如果此值為 **[是]**，則會為 E9-1-1 啟用用戶端。</span><span class="sxs-lookup"><span data-stu-id="437f3-106">When this value is **Yes**, the client is enabled for E9-1-1.</span></span> <span data-ttu-id="437f3-107">用戶端註冊時，它會嘗試從位置資訊服務取得位置，並將位置資訊包含在緊急通話的一部分。</span><span class="sxs-lookup"><span data-stu-id="437f3-107">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>

<!-- end list -->

  - <span data-ttu-id="437f3-108">**需要位置**</span><span class="sxs-lookup"><span data-stu-id="437f3-108">**Location Required**</span></span>  
    <span data-ttu-id="437f3-109">此設定僅在 [**啟用** 中的服務] 設定為 **[是]** 時使用。</span><span class="sxs-lookup"><span data-stu-id="437f3-109">This setting is used only when **Emergence Services Enabled** is set to **Yes**.</span></span>
    
    <span data-ttu-id="437f3-110">您可以設定**所需的位置**設定，以定義用戶端行為。</span><span class="sxs-lookup"><span data-stu-id="437f3-110">You can configure the **Location Required** setting to define the client behavior.</span></span> <span data-ttu-id="437f3-111">將此值設定為 [**否**] 表示系統不會提示使用者輸入位置。</span><span class="sxs-lookup"><span data-stu-id="437f3-111">Setting the value to **No** means that the user will not be prompted for a location.</span></span> <span data-ttu-id="437f3-112">將此值設定為 **[是]** 表示系統會提示使用者輸入位置，但可以關閉提示。</span><span class="sxs-lookup"><span data-stu-id="437f3-112">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="437f3-113">將此值設定為 [**免責聲明**] 表示系統會提示使用者輸入位置，而且在他們嘗試關閉提示時也會顯示免責聲明。</span><span class="sxs-lookup"><span data-stu-id="437f3-113">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="437f3-114">在任何情況下，使用者都可以繼續使用用戶端。</span><span class="sxs-lookup"><span data-stu-id="437f3-114">In all cases, the user can continue to use the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="437f3-115">如果使用者在啟用 E9 前手動輸入位置，則不會顯示免責聲明文字-1-1。</span><span class="sxs-lookup"><span data-stu-id="437f3-115">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1.</span></span> <span data-ttu-id="437f3-116">已查看免責聲明的使用者將不會看到免責聲明文字的更新。</span><span class="sxs-lookup"><span data-stu-id="437f3-116">Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="437f3-117">**增強的緊急服務免責聲明**</span><span class="sxs-lookup"><span data-stu-id="437f3-117">**Enhanced Emergency Service Disclaimer**</span></span>  
    <span data-ttu-id="437f3-118">此設定會指定使用者在關閉位置提示時所看到的免責聲明。</span><span class="sxs-lookup"><span data-stu-id="437f3-118">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="437f3-119">在 Lync Server 2013 中，您可以使用位置原則，針對不同的地區設定或不同的使用者集設定不同的免責聲明。</span><span class="sxs-lookup"><span data-stu-id="437f3-119">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="437f3-120">這個位置原則設定與 Lync Server 2010 不同，您使用<STRONG>CsEnhancedEmergencyServiceDisclaimer</STRONG> Cmdlet 來為整個組織設定全域免責聲明。</span><span class="sxs-lookup"><span data-stu-id="437f3-120">This location policy setting differs from Lync Server 2010, where you used the <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet to set a global disclaimer for the entire organization.</span></span> <span data-ttu-id="437f3-121">如果全域免責聲明已存在，您必須在位置原則中指定該免責聲明。</span><span class="sxs-lookup"><span data-stu-id="437f3-121">If a global disclaimer already exists, you need to specify that disclaimer in location policy.</span></span> <span data-ttu-id="437f3-122">也就是說，Lync Server 2013 只使用位置原則中指定的免責聲明。</span><span class="sxs-lookup"><span data-stu-id="437f3-122">That is, Lync Server 2013 uses only disclaimers specified in location policy.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="437f3-123">**緊急撥號字串**</span><span class="sxs-lookup"><span data-stu-id="437f3-123">**Emergency Dial String**</span></span>  
    <span data-ttu-id="437f3-124">這個撥號字串（較少前導 "+"，但包括 Lync 使用者的撥號計畫所完成的任何正常化）表示通話是緊急通話。</span><span class="sxs-lookup"><span data-stu-id="437f3-124">This dial string (less the leading “+”, but including any normalization done by the Lync user’s Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="437f3-125">[**緊急撥號字串**] 會讓用戶端在通話中加入位置和回呼資訊。</span><span class="sxs-lookup"><span data-stu-id="437f3-125">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="437f3-126">如果您的組織未使用外部線路存取首碼，您就不需要建立對應的撥號方案正常化規則，在將呼叫傳送到 Lync 伺服器上的輸出路由之前，將 "+" 新增至911字串;由於位置原則，Lync 用戶端將自動預先加上 "+"。</span><span class="sxs-lookup"><span data-stu-id="437f3-126">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a “+” to the 911 string prior to sending the call to Outbound Routing on a Lync pool server; the “+” will be automatically prepended by the Lync client as a result of the location policy.</span></span> <span data-ttu-id="437f3-127">不過，如果您的網站使用外部存取前置詞，您必須將正常化規則新增到可分割外部存取前置詞的適用撥號方案原則，並新增 "+"。</span><span class="sxs-lookup"><span data-stu-id="437f3-127">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the “+”.</span></span> <span data-ttu-id="437f3-128">例如，如果您的位置使用外部存取首碼9，且使用者要撥 9&nbsp;911 來撥打緊急電話，則用戶端將會使用撥號方案911原則，在撥打電話號碼之後，再由呼叫者的位置設定檔中的路由評估。</span><span class="sxs-lookup"><span data-stu-id="437f3-128">For example, if your location uses an external access prefix of 9 and a user dials 9&nbsp;911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller’s location profile.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="437f3-129">**緊急撥號字串遮罩**</span><span class="sxs-lookup"><span data-stu-id="437f3-129">**Emergency Dial String Masks**</span></span>  
    <span data-ttu-id="437f3-130">以分號分隔的撥號字串清單，可翻譯成指定的**緊急撥號字串**。</span><span class="sxs-lookup"><span data-stu-id="437f3-130">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="437f3-131">例如，您可能會想要新增112，這是大多數歐洲的緊急服務號碼。</span><span class="sxs-lookup"><span data-stu-id="437f3-131">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="437f3-132">從歐洲造訪 Lync 使用者可能不知道911是美國的緊急電話號碼，但他們可以撥打112並取得相同的結果。</span><span class="sxs-lookup"><span data-stu-id="437f3-132">A visiting Lync user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="437f3-133">就像緊急撥號字串一樣，請不要在每個數位前加上 "+"，而且如果您使用外部線路存取代碼，請務必在使用者的撥號計畫原則中有正常化規則來剝離存取代碼位數。</span><span class="sxs-lookup"><span data-stu-id="437f3-133">As with the Emergency Dial String, do not include a “+” before each number, and if you use external line access codes, be sure there are normalization rules in the user’s Dial Plan policy to strip off the access code digit.</span></span>

<!-- end list -->

  - <span data-ttu-id="437f3-134">**PSTN 使用方式**</span><span class="sxs-lookup"><span data-stu-id="437f3-134">**PSTN Usage**</span></span>  
    <span data-ttu-id="437f3-135">PSTN 使用的名稱，其中包含判斷哪些 SIP 幹線、PSTN 閘道或 ELIN 閘道緊急呼叫將前往的路由路徑。</span><span class="sxs-lookup"><span data-stu-id="437f3-135">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="437f3-136">位置原則只能指派一個用法。</span><span class="sxs-lookup"><span data-stu-id="437f3-136">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="437f3-137">此 PSTN 使用會覆寫指派給使用者語音原則的 PSTN 使用量，但只適用于緊急撥號字串或其中一個緊急撥號字串遮罩的呼叫。</span><span class="sxs-lookup"><span data-stu-id="437f3-137">This PSTN Usage overrides the PSTN Usages assigned to the user’s voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="437f3-138">**通知 URI**</span><span class="sxs-lookup"><span data-stu-id="437f3-138">**Notification URI**</span></span>  
    <span data-ttu-id="437f3-139">指定在發出緊急通話時接收立即訊息（IM）通知的安全性人員的一個或多個 SIP Uri。</span><span class="sxs-lookup"><span data-stu-id="437f3-139">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed.</span></span> <span data-ttu-id="437f3-140">支援通訊群組。</span><span class="sxs-lookup"><span data-stu-id="437f3-140">Distribution groups are supported.</span></span>

<!-- end list -->

  - <span data-ttu-id="437f3-141">**會議 URI**</span><span class="sxs-lookup"><span data-stu-id="437f3-141">**Conference URI**</span></span>  
    <span data-ttu-id="437f3-142">指定在發出緊急通話時，應 conferenced 的直接向內撥號（已登錄）號碼（通常是安全服務台號碼）。</span><span class="sxs-lookup"><span data-stu-id="437f3-142">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span>

<!-- end list -->

  - <span data-ttu-id="437f3-143">**會議模式**</span><span class="sxs-lookup"><span data-stu-id="437f3-143">**Conference Mode**</span></span>  
    <span data-ttu-id="437f3-144">指定是否要使用單向或雙向通訊，將會議 URI conferenced 到緊急通話中。</span><span class="sxs-lookup"><span data-stu-id="437f3-144">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span>

<!-- end list -->

  - <span data-ttu-id="437f3-145">**位置重新整理間隔**</span><span class="sxs-lookup"><span data-stu-id="437f3-145">**Location Refresh Interval**</span></span>  
    <span data-ttu-id="437f3-146">指定從位置資訊服務傳送位置更新之用戶端要求的時間長度（以小時為單位）。</span><span class="sxs-lookup"><span data-stu-id="437f3-146">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="437f3-147">這個值可以設定為1到12之間的任何值。</span><span class="sxs-lookup"><span data-stu-id="437f3-147">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="437f3-148">預設值為4。</span><span class="sxs-lookup"><span data-stu-id="437f3-148">The default value is 4.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

