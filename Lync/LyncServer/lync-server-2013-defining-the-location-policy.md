---
title: Lync Server 2013： 定義位置原則
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
ms.openlocfilehash: 64c164f24f0f2c140a140b7343dd526979cc2bff
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-location-policy-for-lync-server-2013"></a><span data-ttu-id="0ab73-102">定義 Lync Server 2013 的位置原則</span><span class="sxs-lookup"><span data-stu-id="0ab73-102">Defining the location policy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ab73-103">_**主題上次修改日期：** 2012年-10-29_</span><span class="sxs-lookup"><span data-stu-id="0ab73-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="0ab73-104">每個位置原則都包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="0ab73-104">Each location policy contains the following information:</span></span>

  - <span data-ttu-id="0ab73-105">**已啟用緊急服務**</span><span class="sxs-lookup"><span data-stu-id="0ab73-105">**Emergency Services Enabled**</span></span>  
    <span data-ttu-id="0ab73-106">當此值為 [**是**] 時，用戶端會啟用 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="0ab73-106">When this value is **Yes**, the client is enabled for E9-1-1.</span></span> <span data-ttu-id="0ab73-107">當用戶端登錄時，它會嘗試取得從位置資訊服務的位置，且會包含一部分緊急電話的位置資訊。</span><span class="sxs-lookup"><span data-stu-id="0ab73-107">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>

<!-- end list -->

  - <span data-ttu-id="0ab73-108">**必要位置**</span><span class="sxs-lookup"><span data-stu-id="0ab73-108">**Location Required**</span></span>  
    <span data-ttu-id="0ab73-109">使用此設定僅當**已啟用緊急服務** 設為 [**是]**。</span><span class="sxs-lookup"><span data-stu-id="0ab73-109">This setting is used only when **Emergence Services Enabled** is set to **Yes**.</span></span>
    
    <span data-ttu-id="0ab73-110">您可以設定**位置所需**的設定，可定義的用戶端行為。</span><span class="sxs-lookup"><span data-stu-id="0ab73-110">You can configure the **Location Required** setting to define the client behavior.</span></span> <span data-ttu-id="0ab73-111">將值設定為 [**否]** 表示位置不會提示使用者。</span><span class="sxs-lookup"><span data-stu-id="0ab73-111">Setting the value to **No** means that the user will not be prompted for a location.</span></span> <span data-ttu-id="0ab73-112">設定為 **[是]** 的值表示使用者位置]，系統會提示，但可以解除提示。</span><span class="sxs-lookup"><span data-stu-id="0ab73-112">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="0ab73-113">設定**免責聲明**的值表示使用者會提示的位置，並且也會顯示免責聲明如果使用者嘗試解除提示。</span><span class="sxs-lookup"><span data-stu-id="0ab73-113">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="0ab73-114">在所有情況下，使用者可以繼續使用用戶端。</span><span class="sxs-lookup"><span data-stu-id="0ab73-114">In all cases, the user can continue to use the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0ab73-115">如果使用者手動輸入位置之前要啟用 E9-1-1，將不會出現免責聲明文字。</span><span class="sxs-lookup"><span data-stu-id="0ab73-115">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1.</span></span> <span data-ttu-id="0ab73-116">更新至免責聲明的文字不會檢視的檢視已經過免責聲明的使用者。</span><span class="sxs-lookup"><span data-stu-id="0ab73-116">Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="0ab73-117">**增強型緊急服務免責聲明**</span><span class="sxs-lookup"><span data-stu-id="0ab73-117">**Enhanced Emergency Service Disclaimer**</span></span>  
    <span data-ttu-id="0ab73-118">此設定指定免責聲明，如果他們關閉位置的提示，請參閱 < 的使用者。</span><span class="sxs-lookup"><span data-stu-id="0ab73-118">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="0ab73-119">在 Lync Server 2013 中，您可以使用位置原則來設定不同的免責聲明，不同地區設定或不同組的使用者。</span><span class="sxs-lookup"><span data-stu-id="0ab73-119">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0ab73-120">此位置原則設定與 Lync Server 2010]，其中您用於<STRONG>Set-cssipresponsecodetranslationrule</STRONG>指令程式設定為整個組織的全域免責聲明。</span><span class="sxs-lookup"><span data-stu-id="0ab73-120">This location policy setting differs from Lync Server 2010, where you used the <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet to set a global disclaimer for the entire organization.</span></span> <span data-ttu-id="0ab73-121">如果全域免責聲明已經存在，您需要在 [位置原則中指定該免責聲明。</span><span class="sxs-lookup"><span data-stu-id="0ab73-121">If a global disclaimer already exists, you need to specify that disclaimer in location policy.</span></span> <span data-ttu-id="0ab73-122">也就是說，Lync Server 2013 使用位置原則中指定的免責聲明。</span><span class="sxs-lookup"><span data-stu-id="0ab73-122">That is, Lync Server 2013 uses only disclaimers specified in location policy.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="0ab73-123">**緊急撥號字串**</span><span class="sxs-lookup"><span data-stu-id="0ab73-123">**Emergency Dial String**</span></span>  
    <span data-ttu-id="0ab73-124">此撥號對應表的字串 (小於前置 「 + 」，但包括由 Lync 使用者的撥號對應表規劃完成任何正規化) 表示通話時，緊急通話。</span><span class="sxs-lookup"><span data-stu-id="0ab73-124">This dial string (less the leading “+”, but including any normalization done by the Lync user’s Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="0ab73-125">**緊急撥號字串**會導致用戶端包括位置和使用呼叫的回撥資訊。</span><span class="sxs-lookup"><span data-stu-id="0ab73-125">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0ab73-126">如果您的組織不使用外部線路存取首碼，您不需要建立對應的撥號對應表正規化規則，新增 「 + 」 之前傳送的呼叫輸出路由 Lync 集區伺服器; 上 911 字串「 + 」 會自動加在 Lync 用戶端，因為位置原則。</span><span class="sxs-lookup"><span data-stu-id="0ab73-126">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a “+” to the 911 string prior to sending the call to Outbound Routing on a Lync pool server; the “+” will be automatically prepended by the Lync client as a result of the location policy.</span></span> <span data-ttu-id="0ab73-127">不過，如果您的網站使用的外部存取首碼，您需要新增正規化規則至適用的撥號對應表原則階梯狀往外部存取首碼，並加入 「 + 」。</span><span class="sxs-lookup"><span data-stu-id="0ab73-127">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the “+”.</span></span> <span data-ttu-id="0ab73-128">例如，如果您的位置使用為 9 和使用者外部存取首碼撥 9&nbsp;911 來撥打緊急通話，用戶端會使用其撥號對應表原則正規化的需求，這要 +911 之前撥打的號碼評估的發話者的位置設定檔中的路由。</span><span class="sxs-lookup"><span data-stu-id="0ab73-128">For example, if your location uses an external access prefix of 9 and a user dials 9&nbsp;911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller’s location profile.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="0ab73-129">**緊急撥號字串遮罩**</span><span class="sxs-lookup"><span data-stu-id="0ab73-129">**Emergency Dial String Masks**</span></span>  
    <span data-ttu-id="0ab73-130">以分號分隔清單的撥號對應表字串會轉譯成**緊急撥號字串**所指定。</span><span class="sxs-lookup"><span data-stu-id="0ab73-130">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="0ab73-131">例如，可能會想要新增 112，這是大部分的歐洲的緊急服務號碼。</span><span class="sxs-lookup"><span data-stu-id="0ab73-131">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="0ab73-132">造訪 Lync 使用者從歐洲可能不知道要 911 是美國緊急電話號碼，但他們可以撥 112 並得到相同結果。</span><span class="sxs-lookup"><span data-stu-id="0ab73-132">A visiting Lync user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="0ab73-133">為與緊急撥號字串，不含"+"之前每一個數字，而且如果您使用外部線路存取碼時，務必要存取程式碼數字中移除使用者的撥號對應表原則中有正規化規則。</span><span class="sxs-lookup"><span data-stu-id="0ab73-133">As with the Emergency Dial String, do not include a “+” before each number, and if you use external line access codes, be sure there are normalization rules in the user’s Dial Plan policy to strip off the access code digit.</span></span>

<!-- end list -->

  - <span data-ttu-id="0ab73-134">**PSTN 使用方式**</span><span class="sxs-lookup"><span data-stu-id="0ab73-134">**PSTN Usage**</span></span>  
    <span data-ttu-id="0ab73-135">包含的路由路徑可決定哪一個 SIP 主幹、 PSTN 閘道或 ELIN 閘道緊急通話將會移至 [PSTN 使用方式的名稱。</span><span class="sxs-lookup"><span data-stu-id="0ab73-135">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0ab73-136">只有一個流量可以指派給位置原則。</span><span class="sxs-lookup"><span data-stu-id="0ab73-136">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="0ab73-137">此 PSTN 使用方式會覆寫指派給使用者的語音原則、 PSTN 使用方式，但僅適用於緊急撥號字串或下列其中一個緊急撥號字串遮罩撥打。</span><span class="sxs-lookup"><span data-stu-id="0ab73-137">This PSTN Usage overrides the PSTN Usages assigned to the user’s voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="0ab73-138">**通知 URI**</span><span class="sxs-lookup"><span data-stu-id="0ab73-138">**Notification URI**</span></span>  
    <span data-ttu-id="0ab73-139">指定的安全性人員接收立即訊息 (IM) 通知時撥打緊急電話的一或多個 SIP Uri。</span><span class="sxs-lookup"><span data-stu-id="0ab73-139">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed.</span></span> <span data-ttu-id="0ab73-140">支援的通訊群組。</span><span class="sxs-lookup"><span data-stu-id="0ab73-140">Distribution groups are supported.</span></span>

<!-- end list -->

  - <span data-ttu-id="0ab73-141">**會議 URI**</span><span class="sxs-lookup"><span data-stu-id="0ab73-141">**Conference URI**</span></span>  
    <span data-ttu-id="0ab73-142">會指定應該是警衛室時撥打緊急電話直接向內撥號 (DID) 號碼 （通常是安全性 desk 號碼）。</span><span class="sxs-lookup"><span data-stu-id="0ab73-142">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span>

<!-- end list -->

  - <span data-ttu-id="0ab73-143">**會議模式**</span><span class="sxs-lookup"><span data-stu-id="0ab73-143">**Conference Mode**</span></span>  
    <span data-ttu-id="0ab73-144">會指定如果會議 URI 是否將警衛緊急通話使用單向或雙向通訊。</span><span class="sxs-lookup"><span data-stu-id="0ab73-144">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span>

<!-- end list -->

  - <span data-ttu-id="0ab73-145">**位置重新整理間隔**</span><span class="sxs-lookup"><span data-stu-id="0ab73-145">**Location Refresh Interval**</span></span>  
    <span data-ttu-id="0ab73-146">從 [位置資訊服務的位置更新的用戶端要求之間指定的時間 （以小時為單位）。</span><span class="sxs-lookup"><span data-stu-id="0ab73-146">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="0ab73-147">值可以設定為任何介於 1 到 12。</span><span class="sxs-lookup"><span data-stu-id="0ab73-147">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="0ab73-148">預設值為 4。</span><span class="sxs-lookup"><span data-stu-id="0ab73-148">The default value is 4.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

