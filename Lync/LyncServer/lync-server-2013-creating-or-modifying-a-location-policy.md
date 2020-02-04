---
title: Lync Server 2013：建立或修改位置原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying a location policy
ms:assetid: 10338418-4da4-42df-b231-f52098c08dae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687971(v=OCS.15)
ms:contentKeyID: 49733557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1648e845fc3759e7083c2443013f89fb49c1b00f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-a-location-policy-in-lync-server-2013"></a><span data-ttu-id="9d689-102">在 Lync Server 2013 中建立或修改位置原則</span><span class="sxs-lookup"><span data-stu-id="9d689-102">Creating or modifying a location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d689-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9d689-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9d689-104">在 Lync Server 2013 中，您可以使用位置原則來套用與增強版9-1-1 （E9-1）功能相關的設定，以及使用者或連絡人的位置設定。</span><span class="sxs-lookup"><span data-stu-id="9d689-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="9d689-105">位置原則會判斷使用者是否已啟用 E9-1-1，以及是否有緊急通話的行為。</span><span class="sxs-lookup"><span data-stu-id="9d689-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="9d689-106">例如，您可以使用位置原則來定義代表緊急通話的號碼（例如，911在美國）、企業安全性是否應該自動收到通知，以及如何路由通話。</span><span class="sxs-lookup"><span data-stu-id="9d689-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="9d689-107">您可以在 Lync Server 2013 [控制台] 的 [**網路**設定] 群組中設定位置原則。</span><span class="sxs-lookup"><span data-stu-id="9d689-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="9d689-108">在 Lync Server [控制台] 中，您可以查看、建立、修改或刪除位置原則。</span><span class="sxs-lookup"><span data-stu-id="9d689-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="9d689-109">使用本節中的程式來建立或修改位置原則。</span><span class="sxs-lookup"><span data-stu-id="9d689-109">Use the procedures in this section to create or modify a location policy.</span></span> <span data-ttu-id="9d689-110">如需有關刪除位置原則的詳細資訊，請參閱[刪除 Lync Server 2013 中的位置原則](lync-server-2013-deleting-a-location-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="9d689-110">For details on deleting location policies, see [Deleting a location policy in Lync Server 2013](lync-server-2013-deleting-a-location-policy.md).</span></span>

<span data-ttu-id="9d689-111">在 Lync Server 2013 中，您可以覆寫來自位置資訊服務之位置更新之用戶端要求的預設時間長度。</span><span class="sxs-lookup"><span data-stu-id="9d689-111">In Lync Server 2013, you can override the default amount of time between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="9d689-112">預設值為4小時。</span><span class="sxs-lookup"><span data-stu-id="9d689-112">The default value is 4 hours.</span></span> <span data-ttu-id="9d689-113">將**CsLocationPolicy** Cmdlet 與 LocationRefreshInterval 參數搭配使用，以覆寫預設值。</span><span class="sxs-lookup"><span data-stu-id="9d689-113">Use the **Set-CsLocationPolicy** cmdlet with the LocationRefreshInterval parameter to override the default value.</span></span>

<div>

## <a name="to-create-a-new-location-policy-in-lync-server-control-panel"></a><span data-ttu-id="9d689-114">在 Lync Server [控制台] 中建立新的位置原則</span><span class="sxs-lookup"><span data-stu-id="9d689-114">To create a new location policy in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9d689-115">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="9d689-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9d689-116">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="9d689-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9d689-117">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="9d689-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9d689-118">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**位置原則**]。</span><span class="sxs-lookup"><span data-stu-id="9d689-118">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="9d689-119">在 [**位置原則**] 頁面上，按一下 [**新增**]，然後選取您要建立的原則類型：</span><span class="sxs-lookup"><span data-stu-id="9d689-119">On the **Location Policy** page, click **New** and then select the type of policy you want to create:</span></span>
    
      - <span data-ttu-id="9d689-120">若要建立網站原則，按一下 [**網站原則**]。</span><span class="sxs-lookup"><span data-stu-id="9d689-120">To create a site policy, click **Site policy**.</span></span> <span data-ttu-id="9d689-121">在 [**選取網站**] 中，選擇您要套用原則的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="9d689-121">In **Select a Site**, choose the site to which you want the policy applied and click **OK**.</span></span> <span data-ttu-id="9d689-122">在 [**新的位置原則**] 頁面上，[**範圍**] 欄位包含 [值]**網站**，而 [**名稱**] 欄位則包含您所選擇的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="9d689-122">On the **New Location Policy** page, the **Scope** field contains the value **Site**, and the **Name** field contains the name of the site you chose.</span></span> <span data-ttu-id="9d689-123">您無法修改其中一個欄位。</span><span class="sxs-lookup"><span data-stu-id="9d689-123">You cannot modify either of these fields.</span></span> <span data-ttu-id="9d689-124">網站原則會自動套用至指定網站上的所有使用者，並覆寫這些使用者的全域原則。</span><span class="sxs-lookup"><span data-stu-id="9d689-124">A site policy is automatically applied to all users on the specified site and overrides the global policy for those users.</span></span>
    
      - <span data-ttu-id="9d689-125">若要建立**使用者原則**，按一下 [**使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="9d689-125">To create a **User policy**, click **User policy**.</span></span> <span data-ttu-id="9d689-126">在**新的位置原則**中，[**範圍**] 欄位包含 [**使用者**] 值。</span><span class="sxs-lookup"><span data-stu-id="9d689-126">In the **New Location Policy**, the **Scope** field contains the value **User**.</span></span> <span data-ttu-id="9d689-127">您無法修改這個值。</span><span class="sxs-lookup"><span data-stu-id="9d689-127">You cannot modify this value.</span></span> <span data-ttu-id="9d689-128">在 [**名稱**] 欄位中，輸入您要賦予此原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="9d689-128">In the **Name** field, type the name you want to give this policy.</span></span> <span data-ttu-id="9d689-129">使用者原則不會自動套用至任何使用者。</span><span class="sxs-lookup"><span data-stu-id="9d689-129">A user policy does not automatically apply to any users.</span></span> <span data-ttu-id="9d689-130">建立使用者原則之後，您必須手動將原則授與您要套用原則的使用者或網路網站。</span><span class="sxs-lookup"><span data-stu-id="9d689-130">After creating the user policy, you must manually grant the policy to the users or network sites to which you want to policy to apply.</span></span>

5.  <span data-ttu-id="9d689-131">請按照下列步驟填寫其餘欄位：</span><span class="sxs-lookup"><span data-stu-id="9d689-131">Fill in the remaining fields as follows:</span></span>
    
      - <span data-ttu-id="9d689-132">**啟用 [增強緊急服務**   ] 選取此核取方塊，以啟用與此原則關聯的使用者 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="9d689-132">**Enable enhanced emergency services**   Select this check box to enable the users associated with this policy for E9-1-1.</span></span> <span data-ttu-id="9d689-133">啟用緊急服務時，Lync Server 用戶端會在註冊時取得位置資訊，並在發出緊急通話時包含該資訊。</span><span class="sxs-lookup"><span data-stu-id="9d689-133">When emergency services are enabled, Lync Server clients will retrieve location information on registration and include that information when an emergency call is made.</span></span>
    
      - <span data-ttu-id="9d689-134">**位置**   指定下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="9d689-134">**Location**   Specify one of the following values:</span></span>
        
          - <span data-ttu-id="9d689-135">**必要**   ：用戶端在新位置註冊時，系統會提示使用者輸入位置資訊。</span><span class="sxs-lookup"><span data-stu-id="9d689-135">**Required**   The user will be prompted to input location information when the client registers at a new location.</span></span> <span data-ttu-id="9d689-136">使用者可以關閉提示，而不需輸入任何資訊。</span><span class="sxs-lookup"><span data-stu-id="9d689-136">The user can dismiss the prompt without entering any information.</span></span> <span data-ttu-id="9d689-137">如果輸入了資訊，緊急電話會在傳送到公用安全應答點（PSAP）運算子（也就是911運算子）之前，先由緊急服務提供者應答以驗證該位置。</span><span class="sxs-lookup"><span data-stu-id="9d689-137">If information is entered, an emergency call will first be answered by the emergency services provider to verify the location before being routed to the Public Safety Answering Point (PSAP) operator (that is, the 911 operator).</span></span>
        
          - <span data-ttu-id="9d689-138">**不需要**   使用者系統不會提示您輸入位置。</span><span class="sxs-lookup"><span data-stu-id="9d689-138">**Not Required**   The user will not be prompted for a location.</span></span> <span data-ttu-id="9d689-139">當通話不含位置資訊時，緊急服務提供者將接聽通話並要求位置。</span><span class="sxs-lookup"><span data-stu-id="9d689-139">When a call is made with no location information, the emergency services provider will answer the call and ask for a location.</span></span>
        
          - <span data-ttu-id="9d689-140">**免責聲明**   除了使用者無法在不輸入位置資訊的情況下關閉提示之外，這個選項也是**必要**的。</span><span class="sxs-lookup"><span data-stu-id="9d689-140">**Disclaimer**   This option is the same as **Required** except that the user cannot dismiss the prompt without entering location information.</span></span> <span data-ttu-id="9d689-141">使用者仍然可以完成緊急通話，但不需輸入資訊，就能完成其他通話。</span><span class="sxs-lookup"><span data-stu-id="9d689-141">The user can still complete an emergency call, but no other calls can be completed without entering the information.</span></span> <span data-ttu-id="9d689-142">此外，系統會向使用者顯示免責聲明文字，讓他們能夠提醒您拒絕輸入位置資訊的後果。</span><span class="sxs-lookup"><span data-stu-id="9d689-142">In addition, disclaimer text will be displayed to the user that can alert them to the consequences of declining to enter location information.</span></span> <span data-ttu-id="9d689-143">若要設定免責聲明文字，您必須使用 Lync Server Management Shell 來執行**CsLocationPolicy** Cmdlet，或使用 EnhancedEmergencyServiceDisclaimer 參數的**新 CsLocationPolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9d689-143">To set the disclaimer text, you must use Lync Server Management Shell to run the **Set-CsLocationPolicy** cmdlet or the **New-CsLocationPolicy** cmdlet with the EnhancedEmergencyServiceDisclaimer parameter.</span></span> <span data-ttu-id="9d689-144">如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的[設定 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)或[CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) 。</span><span class="sxs-lookup"><span data-stu-id="9d689-144">For details, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) or [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) in the Lync Server Management Shell documentation.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="9d689-145">在 Lync Server 2013 中，您可以使用位置原則，針對不同的地區設定或不同的使用者組設定不同的免責聲明，不像在 Lync Server 2010 中，您只能為整個組織指定全域免責聲明。</span><span class="sxs-lookup"><span data-stu-id="9d689-145">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users, unlike in Lync Server 2010 where you could specify only a global disclaimer for the entire organization.</span></span>

            
            </div>
    
      - <span data-ttu-id="9d689-146">**針對急診 services 使用位置只有**   Lync 可以出於各種原因使用位置資訊（例如，通知小組目前的位置）。</span><span class="sxs-lookup"><span data-stu-id="9d689-146">**Use location for emergency services only**   Lync can use location information for various reasons (for example, to notify teammates of your current location).</span></span> <span data-ttu-id="9d689-147">選取此核取方塊以確保位置資訊只能供緊急通話使用。</span><span class="sxs-lookup"><span data-stu-id="9d689-147">Select this check box to ensure location information is available only for use with an emergency call.</span></span>
    
      - <span data-ttu-id="9d689-148">**PSTN 使用**   公開交換電話網絡（PSTN）用法，用來判斷哪種語音路線將用來從使用此設定檔的用戶端傳送緊急通話。</span><span class="sxs-lookup"><span data-stu-id="9d689-148">**PSTN usage**   The public switched telephone network (PSTN) usage that will be used to determine which voice route will be used to route emergency calls from clients using this profile.</span></span> <span data-ttu-id="9d689-149">與此使用相關聯的路線應該指向專用於緊急通話的 SIP 幹線，或指向將緊急呼叫路由到最接近的公用安全應答點（PSAP）的緊急位置識別號碼（ELIN）閘道。</span><span class="sxs-lookup"><span data-stu-id="9d689-149">The route associated with this usage should point to a SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>
    
      - <span data-ttu-id="9d689-150">**緊急撥號號碼**   撥號以達到緊急服務的號碼。</span><span class="sxs-lookup"><span data-stu-id="9d689-150">**Emergency dial number**   The number that is dialed to reach emergency services.</span></span> <span data-ttu-id="9d689-151">在美國，此值為911。</span><span class="sxs-lookup"><span data-stu-id="9d689-151">In the United States this value is 911.</span></span> <span data-ttu-id="9d689-152">字串必須由數位0到9組成，且長度不能超過1到10個數字。</span><span class="sxs-lookup"><span data-stu-id="9d689-152">The string must be made of the digits 0 through 9 and can be from 1 to 10 digits in length.</span></span>
    
      - <span data-ttu-id="9d689-153">**緊急撥號遮罩**   您要在撥入時，要轉換成 [緊急撥號號碼] 值的數位。</span><span class="sxs-lookup"><span data-stu-id="9d689-153">**Emergency dial mask**   A number that you want to translate into the value of the emergency dial number value when it is dialed.</span></span> <span data-ttu-id="9d689-154">例如，如果您在這個欄位中輸入212的值，而 [緊急電話撥入號碼] 欄位的值為911，則使用者212撥打電話時，將會對911進行該通話。</span><span class="sxs-lookup"><span data-stu-id="9d689-154">For example, if you enter a value of 212 in this field and the emergency dial number field has a value of 911, if a user dials 212 the call will be made to 911.</span></span> <span data-ttu-id="9d689-155">這可讓您撥打備用的緊急電話號碼，而且仍能撥打電話給緊急服務（例如，如果某個國家或地區有不同緊急號碼的人嘗試撥打該國家或地區的號碼，而不是他們目前所在的國家或地區）。</span><span class="sxs-lookup"><span data-stu-id="9d689-155">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country or region with a different emergency number attempts to dial that country or region’s number rather than the number for the country or region they are currently in).</span></span> <span data-ttu-id="9d689-156">您可以使用分號來分隔值，以定義多個緊急撥號遮罩。</span><span class="sxs-lookup"><span data-stu-id="9d689-156">You can define multiple emergency dial masks by separating the values with semicolons.</span></span> <span data-ttu-id="9d689-157">例如，212; 414。</span><span class="sxs-lookup"><span data-stu-id="9d689-157">For example, 212;414.</span></span> <span data-ttu-id="9d689-158">字串的最大長度為100個字元。</span><span class="sxs-lookup"><span data-stu-id="9d689-158">Maximum length of the string is 100 characters.</span></span> <span data-ttu-id="9d689-159">每個字元都必須是數位0到9。</span><span class="sxs-lookup"><span data-stu-id="9d689-159">Each character must be a digit 0 through 9.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="9d689-160">確定指定的撥號遮罩值與 [通話駐留] 軌道範圍中的數位不同。</span><span class="sxs-lookup"><span data-stu-id="9d689-160">Ensure that the specified dial mask value is not the same as a number in a call park orbit range.</span></span> <span data-ttu-id="9d689-161">通話駐留路由將會優先于緊急撥號字串轉換。</span><span class="sxs-lookup"><span data-stu-id="9d689-161">Call park routing will take precedence over emergency dial string conversion.</span></span> <span data-ttu-id="9d689-162">若要查看現有的通話公園軌道範圍，請按一下左側導覽列中的 [<STRONG>語音功能</STRONG>]，然後按一下 [<STRONG>通話駐留</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="9d689-162">To see the existing call park orbit ranges, click <STRONG>Voice Features</STRONG> in the left navigation bar and then click <STRONG>Call Park</STRONG>.</span></span> <span data-ttu-id="9d689-163">如需詳細資訊，請參閱<A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">在 Lync Server 2013 中設定停用通話的電話號碼延伸</A>。</span><span class="sxs-lookup"><span data-stu-id="9d689-163">For details, see <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">Configure phone number extensions for parking calls in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="9d689-164">**通知 URI**   一或多個 SIP 統一資源識別項（uri），會在發出緊急通話時收到通知。</span><span class="sxs-lookup"><span data-stu-id="9d689-164">**Notification URI**   One or more SIP Uniform Resource Identifiers (URIs) to be notified when an emergency call is made.</span></span> <span data-ttu-id="9d689-165">例如，只要進行緊急通話，公司安全性 office 就會透過立即訊息通知。</span><span class="sxs-lookup"><span data-stu-id="9d689-165">For example, the company security office could be notified through an instant message whenever an emergency call is made.</span></span> <span data-ttu-id="9d689-166">如果呼叫者的位置可供使用，該位置將會包含在通知中。</span><span class="sxs-lookup"><span data-stu-id="9d689-166">If the caller’s location is available that location will be included in the notification.</span></span> <span data-ttu-id="9d689-167">多個 SIP Uri 可以包含為以逗號分隔的清單。</span><span class="sxs-lookup"><span data-stu-id="9d689-167">Multiple SIP URIs can be included as a comma-separated list.</span></span> <span data-ttu-id="9d689-168">例如，"sip： security@litwareinc .com"，"sip： kmyer@litwareinc .com"。</span><span class="sxs-lookup"><span data-stu-id="9d689-168">For example, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com".</span></span> <span data-ttu-id="9d689-169">支援通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="9d689-169">Distribution lists are supported.</span></span> <span data-ttu-id="9d689-170">字串的長度必須是1到256個字元，且必須以前置詞「sip：」開頭。</span><span class="sxs-lookup"><span data-stu-id="9d689-170">The string must be from 1 to 256 characters in length and must begin with the prefix "sip:".</span></span> <span data-ttu-id="9d689-171">在您按一下 [通知 URI] 欄位之前，會顯示範例。</span><span class="sxs-lookup"><span data-stu-id="9d689-171">Before you click in the Notification URI field an example is displayed.</span></span>
    
      - <span data-ttu-id="9d689-172">**會議 uri**   在此案例中，將會 conferenced 到所進行的任何緊急呼叫的 SIP uri （在此例中為）的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="9d689-172">**Conference URI**   The SIP URI, in this case the telephone number, of a third party that will be conferenced in to any emergency calls that are made.</span></span> <span data-ttu-id="9d689-173">例如，當緊急通話發出並接聽電話或參與通話時（視 [**會議模式]** 欄位中提供的值而定），公司安全性 office 可能會接聽來電。</span><span class="sxs-lookup"><span data-stu-id="9d689-173">For example, the company security office could receive a call when an emergency call is made and listen in or participate in that call (depending on the value supplied in the **Conference mode** field).</span></span> <span data-ttu-id="9d689-174">字串必須是介於1到256個字元的長度，且必須以前置詞 sip 開頭：。</span><span class="sxs-lookup"><span data-stu-id="9d689-174">The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</span></span> <span data-ttu-id="9d689-175">在此欄位內按一下，就會顯示範例。</span><span class="sxs-lookup"><span data-stu-id="9d689-175">An example is displayed until you click inside this field.</span></span>
    
      - <span data-ttu-id="9d689-176">**[會議模式]**   如果您在 [**會議 URI** ] 欄位中指定值，**會議模式**會判斷協力廠商是否可以參與通話，或只能接聽。</span><span class="sxs-lookup"><span data-stu-id="9d689-176">**Conference mode**   If you specify a value in the **Conference URI** field, the **Conference mode** determines whether a third party can participate in the call or can only listen in.</span></span> <span data-ttu-id="9d689-177">指定下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="9d689-177">Specify one of the following options:</span></span>
        
          - <span data-ttu-id="9d689-178">**單向第**三方只能聽取來電者與 PSAP 操作員之間的交談。   </span><span class="sxs-lookup"><span data-stu-id="9d689-178">**One-way**   A third party can only listen to the conversation between the caller and the PSAP operator.</span></span>
        
          - <span data-ttu-id="9d689-179">\*\*\*\* 協力廠商可以接聽並參與呼叫者與 PSAP 操作員之間的通話。   </span><span class="sxs-lookup"><span data-stu-id="9d689-179">**Two-way**   A third party can listen in and participate in the call between the caller and the PSAP operator.</span></span>

6.  <span data-ttu-id="9d689-180">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9d689-180">Click **Commit**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9d689-181">當您建立使用者原則時，最初該原則不會套用至任何使用者或網路網站。</span><span class="sxs-lookup"><span data-stu-id="9d689-181">When you create a user policy, initially that policy does not apply to any users or network sites.</span></span> <span data-ttu-id="9d689-182">若要將原則套用至使用者，請按一下左側導覽列中的 [<STRONG>使用者</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="9d689-182">To apply the policy to a user, click <STRONG>Users</STRONG> in the left navigation bar.</span></span> <span data-ttu-id="9d689-183">尋找您要套用原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="9d689-183">Find the user to which you want to apply the policy.</span></span> <span data-ttu-id="9d689-184">按一下 [<STRONG>編輯</STRONG>] 功能表上的 [<STRONG>顯示詳細資料</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="9d689-184">On the <STRONG>Edit</STRONG> menu, click <STRONG>Show details</STRONG>.</span></span> <span data-ttu-id="9d689-185">在 [<STRONG>編輯 Lync Server 使用者</STRONG>] 頁面上，從 [<STRONG>位置原則</STRONG>] 下拉式清單中選取新的位置原則，然後按一下 [Commit] （<STRONG>提交</STRONG>）。</span><span class="sxs-lookup"><span data-stu-id="9d689-185">On the <STRONG>Edit Lync Server User</STRONG> page, select the new location policy from the <STRONG>Location policy</STRONG> drop-down list and then click <STRONG>Commit</STRONG>.</span></span><BR><span data-ttu-id="9d689-186">若要將原則套用至網路網站，請按一下左側導覽列中的 [<STRONG>網路</STRONG>設定]，然後按一下 [<STRONG>網站</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="9d689-186">To apply the policy to a network site, click <STRONG>Network Configuration</STRONG> in the left navigation bar and then click <STRONG>Site</STRONG>.</span></span> <span data-ttu-id="9d689-187">尋找您要套用原則的網路網站。</span><span class="sxs-lookup"><span data-stu-id="9d689-187">Find the network site to which you want to apply the policy.</span></span> <span data-ttu-id="9d689-188">按一下 [<STRONG>編輯</STRONG>] 功能表上的 [<STRONG>顯示詳細資料</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="9d689-188">On the <STRONG>Edit</STRONG> menu, click <STRONG>Show details</STRONG>.</span></span> <span data-ttu-id="9d689-189">在 [<STRONG>編輯網站</STRONG>] 中，從 [<STRONG>位置原則</STRONG>] 下拉式清單中選取新的位置原則，然後按一下 [Commit] （<STRONG>提交</STRONG>）。</span><span class="sxs-lookup"><span data-stu-id="9d689-189">In <STRONG>Edit Site</STRONG>, select the new location policy from the <STRONG>Location policy</STRONG> drop-down list and then click <STRONG>Commit</STRONG>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-location-policy-in-lync-server-control-panel"></a><span data-ttu-id="9d689-190">在 Lync Server [控制台] 中修改位置原則</span><span class="sxs-lookup"><span data-stu-id="9d689-190">To modify a location policy in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9d689-191">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="9d689-191">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9d689-192">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="9d689-192">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9d689-193">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="9d689-193">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9d689-194">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**位置原則**]。</span><span class="sxs-lookup"><span data-stu-id="9d689-194">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="9d689-195">在 [**位置原則**] 頁面上，選取您要修改的位置原則。</span><span class="sxs-lookup"><span data-stu-id="9d689-195">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="9d689-196">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="9d689-196">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="9d689-197">在 [**編輯位置原則**] 頁面上，視需要修改欄位（如需詳細資訊，請參閱本主題前面的「建立新位置原則中的步驟5」）。</span><span class="sxs-lookup"><span data-stu-id="9d689-197">On the **Edit Location Policy** page, modify the fields as necessary (for details, see Step 5 in the "To create a new location policy" procedures earlier in this topic).</span></span>

7.  <span data-ttu-id="9d689-198">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9d689-198">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9d689-199">請參閱</span><span class="sxs-lookup"><span data-stu-id="9d689-199">See Also</span></span>


[<span data-ttu-id="9d689-200">刪除 Lync Server 2013 中的位置原則</span><span class="sxs-lookup"><span data-stu-id="9d689-200">Deleting a location policy in Lync Server 2013</span></span>](lync-server-2013-deleting-a-location-policy.md)  


[<span data-ttu-id="9d689-201">定義 Lync Server 2013 的位置原則</span><span class="sxs-lookup"><span data-stu-id="9d689-201">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)  


[<span data-ttu-id="9d689-202">在 Lync Server 2013 中設定停用通話的電話號碼延伸</span><span class="sxs-lookup"><span data-stu-id="9d689-202">Configure phone number extensions for parking calls in Lync Server 2013</span></span>](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

