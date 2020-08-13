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
ms.openlocfilehash: 6a2f2d5575bee6e6b29b6a5c289cfa589a33c411
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-a-location-policy-in-lync-server-2013"></a><span data-ttu-id="aef0e-102">在 Lync Server 2013 中建立或修改位置原則</span><span class="sxs-lookup"><span data-stu-id="aef0e-102">Creating or modifying a location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aef0e-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="aef0e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="aef0e-104">在 Lync Server 2013 中，您可以使用位置原則，套用與增強型 9-1-1 (E9-1-1) 功能及使用者或連絡人的位置設定相關的設定。</span><span class="sxs-lookup"><span data-stu-id="aef0e-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="aef0e-105">位置原則會判斷使用者是否已啟用 E9-1-1，如果是，則會決定緊急電話的行為。</span><span class="sxs-lookup"><span data-stu-id="aef0e-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="aef0e-106">例如，您可以使用位置原則來定義組成緊急電話的數字 (例如，在美國為 911)、是否應自動告知公司的安全部門，以及應如何路由傳送來電。</span><span class="sxs-lookup"><span data-stu-id="aef0e-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="aef0e-107">您可以在 Lync Server 2013 [控制台] 中的 [**網路**設定] 群組設定位置原則。</span><span class="sxs-lookup"><span data-stu-id="aef0e-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="aef0e-108">從 Lync Server 控制台，您可以查看、建立、修改或刪除位置原則。</span><span class="sxs-lookup"><span data-stu-id="aef0e-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="aef0e-109">本節中的程序可用來建立或修改位置原則。</span><span class="sxs-lookup"><span data-stu-id="aef0e-109">Use the procedures in this section to create or modify a location policy.</span></span> <span data-ttu-id="aef0e-110">如需刪除位置原則的詳細資訊，請參閱[刪除位置原則中的 Lync Server 2013](lync-server-2013-deleting-a-location-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="aef0e-110">For details on deleting location policies, see [Deleting a location policy in Lync Server 2013](lync-server-2013-deleting-a-location-policy.md).</span></span>

<span data-ttu-id="aef0e-111">在 Lync Server 2013 中，您可以從位置資訊服務覆寫用戶端要求位置更新之間的預設時間長度。</span><span class="sxs-lookup"><span data-stu-id="aef0e-111">In Lync Server 2013, you can override the default amount of time between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="aef0e-112">預設值為 4 小時。</span><span class="sxs-lookup"><span data-stu-id="aef0e-112">The default value is 4 hours.</span></span> <span data-ttu-id="aef0e-113">使用 **Set-CsLocationPolicy** Cmdlet 搭配 LocationRefreshInterval 參數可以覆寫預設值。</span><span class="sxs-lookup"><span data-stu-id="aef0e-113">Use the **Set-CsLocationPolicy** cmdlet with the LocationRefreshInterval parameter to override the default value.</span></span>

<div>

## <a name="to-create-a-new-location-policy-in-lync-server-control-panel"></a><span data-ttu-id="aef0e-114">在 Lync Server 控制台中建立新的位置原則</span><span class="sxs-lookup"><span data-stu-id="aef0e-114">To create a new location policy in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="aef0e-115">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="aef0e-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aef0e-116">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="aef0e-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="aef0e-117">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="aef0e-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aef0e-118">在左導覽列中按一下 [網路設定]\*\*\*\*，然後按一下 [位置原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aef0e-118">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="aef0e-119">在「位置原則」\*\*\*\* 頁面上按一下 [新增]\*\*\*\*，然後選取您要建立的原則類型：</span><span class="sxs-lookup"><span data-stu-id="aef0e-119">On the **Location Policy** page, click **New** and then select the type of policy you want to create:</span></span>
    
      - <span data-ttu-id="aef0e-p105">若要建立網站原則，請按一下 [站台原則]\*\*\*\*。在 [選取站台]\*\*\*\* 中選擇要套用原則的網站，然後按一下 [確定]\*\*\*\*。在「新增位置原則」\*\*\*\* 頁面上，[範圍]\*\*\*\* 欄位會包含 [站台]\*\*\*\* 值，[名稱]\*\*\*\* 欄位則會包含您所選擇的網站名稱。您無法修改這些欄位。網站原則會自動套用至指定網站上的所有使用者，並且覆寫這些使用者的全域原則。</span><span class="sxs-lookup"><span data-stu-id="aef0e-p105">To create a site policy, click **Site policy**. In **Select a Site**, choose the site to which you want the policy applied and click **OK**. On the **New Location Policy** page, the **Scope** field contains the value **Site**, and the **Name** field contains the name of the site you chose. You cannot modify either of these fields. A site policy is automatically applied to all users on the specified site and overrides the global policy for those users.</span></span>
    
      - <span data-ttu-id="aef0e-p106">若要建立 [使用者原則]\*\*\*\*，請按一下 [使用者原則]\*\*\*\*。在 [新增位置原則]\*\*\*\* 中，[範圍]\*\*\*\* 欄位會包含 [使用者]\*\*\*\* 值。您無法修改此值。在 [名稱]\*\*\*\* 欄位中，輸入您要為此原則指定的名稱。使用者原則不會自動套用至任何使用者。在建立使用者原則後，您必須以手動方式將原則授與給要套用此原則的使用者或網路網站。</span><span class="sxs-lookup"><span data-stu-id="aef0e-p106">To create a **User policy**, click **User policy**. In the **New Location Policy**, the **Scope** field contains the value **User**. You cannot modify this value. In the **Name** field, type the name you want to give this policy. A user policy does not automatically apply to any users. After creating the user policy, you must manually grant the policy to the users or network sites to which you want to policy to apply.</span></span>

5.  <span data-ttu-id="aef0e-131">填入其餘欄位，如下所示：</span><span class="sxs-lookup"><span data-stu-id="aef0e-131">Fill in the remaining fields as follows:</span></span>
    
      - <span data-ttu-id="aef0e-132">**啟用增強型急診服務**    選取此核取方塊可讓與此原則相關聯的使用者 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="aef0e-132">**Enable enhanced emergency services**   Select this check box to enable the users associated with this policy for E9-1-1.</span></span> <span data-ttu-id="aef0e-133">啟用緊急服務後，Lync Server 用戶端將會在註冊時取得位置資訊，並在進行緊急通話時包含該資訊。</span><span class="sxs-lookup"><span data-stu-id="aef0e-133">When emergency services are enabled, Lync Server clients will retrieve location information on registration and include that information when an emergency call is made.</span></span>
    
      - <span data-ttu-id="aef0e-134">**位置**    指定下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="aef0e-134">**Location**   Specify one of the following values:</span></span>
        
          - <span data-ttu-id="aef0e-135">**必要**    當用戶端在新位置註冊時，系統會提示使用者輸入位置資訊。</span><span class="sxs-lookup"><span data-stu-id="aef0e-135">**Required**   The user will be prompted to input location information when the client registers at a new location.</span></span> <span data-ttu-id="aef0e-136">使用者可以不輸入任何資訊而將提示關閉。</span><span class="sxs-lookup"><span data-stu-id="aef0e-136">The user can dismiss the prompt without entering any information.</span></span> <span data-ttu-id="aef0e-137">如果輸入資訊，緊急服務提供者會先接聽緊急電話，以確認該位置在路由傳送至公用安全回應點 (PSAP) 操作員 (也就是911操作員) 。</span><span class="sxs-lookup"><span data-stu-id="aef0e-137">If information is entered, an emergency call will first be answered by the emergency services provider to verify the location before being routed to the Public Safety Answering Point (PSAP) operator (that is, the 911 operator).</span></span>
        
          - <span data-ttu-id="aef0e-138">**不需要**    不會提示使用者輸入位置。</span><span class="sxs-lookup"><span data-stu-id="aef0e-138">**Not Required**   The user will not be prompted for a location.</span></span> <span data-ttu-id="aef0e-139">當通話沒有地點資訊時，緊急服務提供者會接聽來電，並要求地點。</span><span class="sxs-lookup"><span data-stu-id="aef0e-139">When a call is made with no location information, the emergency services provider will answer the call and ask for a location.</span></span>
        
          - <span data-ttu-id="aef0e-140">**免責聲明**    此選項與**必要條件**相同，只是使用者無法在未輸入位置資訊的情況下關閉提示。</span><span class="sxs-lookup"><span data-stu-id="aef0e-140">**Disclaimer**   This option is the same as **Required** except that the user cannot dismiss the prompt without entering location information.</span></span> <span data-ttu-id="aef0e-141">使用者仍可完成緊急通話，但沒有輸入資訊，可以完成其他電話。</span><span class="sxs-lookup"><span data-stu-id="aef0e-141">The user can still complete an emergency call, but no other calls can be completed without entering the information.</span></span> <span data-ttu-id="aef0e-142">此外，還會向使用者顯示免責聲明文字，以提醒他們拒絕輸入位置資訊的後果。</span><span class="sxs-lookup"><span data-stu-id="aef0e-142">In addition, disclaimer text will be displayed to the user that can alert them to the consequences of declining to enter location information.</span></span> <span data-ttu-id="aef0e-143">若要設定免責聲明文字，您必須使用 Lync Server 管理命令介面來執行**CsLocationPolicy** Cmdlet，或使用 EnhancedEmergencyServiceDisclaimer 參數**New-CsLocationPolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aef0e-143">To set the disclaimer text, you must use Lync Server Management Shell to run the **Set-CsLocationPolicy** cmdlet or the **New-CsLocationPolicy** cmdlet with the EnhancedEmergencyServiceDisclaimer parameter.</span></span> <span data-ttu-id="aef0e-144">如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的[Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)或[New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) 。</span><span class="sxs-lookup"><span data-stu-id="aef0e-144">For details, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) or [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) in the Lync Server Management Shell documentation.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="aef0e-145">在 Lync Server 2013 中，您可以使用位置原則，針對不同的地區設定或不同的使用者集合設定不同的免責聲明，不同于在 Lync Server 2010 中，您只能為整個組織指定全域免責聲明。</span><span class="sxs-lookup"><span data-stu-id="aef0e-145">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users, unlike in Lync Server 2010 where you could specify only a global disclaimer for the entire organization.</span></span>

            
            </div>
    
      - <span data-ttu-id="aef0e-146">**僅限**     緊急服務的使用位置由於各種原因，Lync 可以使用位置資訊 (例如，將您目前位置的團隊) 通知。</span><span class="sxs-lookup"><span data-stu-id="aef0e-146">**Use location for emergency services only**   Lync can use location information for various reasons (for example, to notify teammates of your current location).</span></span> <span data-ttu-id="aef0e-147">選取此核取方塊可確保位置資訊僅供緊急通話之用。</span><span class="sxs-lookup"><span data-stu-id="aef0e-147">Select this check box to ensure location information is available only for use with an emergency call.</span></span>
    
      - <span data-ttu-id="aef0e-148">**PSTN 使用**     方式公用交換電話網路 (PSTN) 使用方式，用來判斷哪個語音路由將用來從使用此設定檔的用戶端路由緊急通話。</span><span class="sxs-lookup"><span data-stu-id="aef0e-148">**PSTN usage**   The public switched telephone network (PSTN) usage that will be used to determine which voice route will be used to route emergency calls from clients using this profile.</span></span> <span data-ttu-id="aef0e-149">與此使用方式關聯的路由應該指向緊急通話專用的 SIP 主幹，或緊急位置識別號碼 (ELIN) 閘道，可將緊急通話路由傳送至最近的公用安全回復點 (PSAP) 。</span><span class="sxs-lookup"><span data-stu-id="aef0e-149">The route associated with this usage should point to a SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>
    
      - <span data-ttu-id="aef0e-150">**緊急撥號號碼**    要撥通緊急服務的號碼。</span><span class="sxs-lookup"><span data-stu-id="aef0e-150">**Emergency dial number**   The number that is dialed to reach emergency services.</span></span> <span data-ttu-id="aef0e-151">此值在美國為 911。</span><span class="sxs-lookup"><span data-stu-id="aef0e-151">In the United States this value is 911.</span></span> <span data-ttu-id="aef0e-152">字串必須由 0 到 9 的數字組成，長度可為 1 到 10 位數字。</span><span class="sxs-lookup"><span data-stu-id="aef0e-152">The string must be made of the digits 0 through 9 and can be from 1 to 10 digits in length.</span></span>
    
      - <span data-ttu-id="aef0e-153">**急診撥號遮罩**    撥打時，要轉譯為 [緊急撥號號碼] 值的數位。</span><span class="sxs-lookup"><span data-stu-id="aef0e-153">**Emergency dial mask**   A number that you want to translate into the value of the emergency dial number value when it is dialed.</span></span> <span data-ttu-id="aef0e-154">例如，如果您在此欄位中輸入值212，而 [緊急撥號號碼] 欄位的值為911，如果使用者撥打212，將會對911進行呼叫。</span><span class="sxs-lookup"><span data-stu-id="aef0e-154">For example, if you enter a value of 212 in this field and the emergency dial number field has a value of 911, if a user dials 212 the call will be made to 911.</span></span> <span data-ttu-id="aef0e-155">這可讓您撥打備用的緊急號碼，並且仍然可以撥打緊急服務 (例如，如果來自國家或地區具有不同緊急號碼的某人嘗試撥打該國家或地區的號碼，而不是其目前在) 中的國家或地區號碼。</span><span class="sxs-lookup"><span data-stu-id="aef0e-155">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country or region with a different emergency number attempts to dial that country or region’s number rather than the number for the country or region they are currently in).</span></span> <span data-ttu-id="aef0e-156">您可以使用分號分隔多個值，藉此定義多組緊急撥話遮罩。</span><span class="sxs-lookup"><span data-stu-id="aef0e-156">You can define multiple emergency dial masks by separating the values with semicolons.</span></span> <span data-ttu-id="aef0e-157">例如，212; 414。</span><span class="sxs-lookup"><span data-stu-id="aef0e-157">For example, 212;414.</span></span> <span data-ttu-id="aef0e-158">字串的長度上限為 100 字元。</span><span class="sxs-lookup"><span data-stu-id="aef0e-158">Maximum length of the string is 100 characters.</span></span> <span data-ttu-id="aef0e-159">每個字元必須是 0 到 9 的數字。</span><span class="sxs-lookup"><span data-stu-id="aef0e-159">Each character must be a digit 0 through 9.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="aef0e-160">確保指定的撥號遮罩值與通話保留範圍中的數字不同。</span><span class="sxs-lookup"><span data-stu-id="aef0e-160">Ensure that the specified dial mask value is not the same as a number in a call park orbit range.</span></span> <span data-ttu-id="aef0e-161">通話保留路由優先於緊急撥號字串轉換。</span><span class="sxs-lookup"><span data-stu-id="aef0e-161">Call park routing will take precedence over emergency dial string conversion.</span></span> <span data-ttu-id="aef0e-162">若要檢視現有的通話駐留範圍，請按一下左導覽列中的 [語音功能]<STRONG></STRONG>，然後按一下 [通話駐留]<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="aef0e-162">To see the existing call park orbit ranges, click <STRONG>Voice Features</STRONG> in the left navigation bar and then click <STRONG>Call Park</STRONG>.</span></span> <span data-ttu-id="aef0e-163">如需詳細資訊，請參閱<A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">在 Lync Server 2013 中設定休止通話的電話號碼分機</A>。</span><span class="sxs-lookup"><span data-stu-id="aef0e-163">For details, see <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">Configure phone number extensions for parking calls in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="aef0e-164">**通知 URI**    進行緊急通話時， (URIs) 的一或多個 SIP 統一資源識別項。</span><span class="sxs-lookup"><span data-stu-id="aef0e-164">**Notification URI**   One or more SIP Uniform Resource Identifiers (URIs) to be notified when an emergency call is made.</span></span> <span data-ttu-id="aef0e-165">例如，每次有人撥打緊急電話時，就會透過立即訊息通知公司的安全部門。</span><span class="sxs-lookup"><span data-stu-id="aef0e-165">For example, the company security office could be notified through an instant message whenever an emergency call is made.</span></span> <span data-ttu-id="aef0e-166">如果可以使用來電者的位置，通知中會包含該位置的資訊。</span><span class="sxs-lookup"><span data-stu-id="aef0e-166">If the caller’s location is available that location will be included in the notification.</span></span> <span data-ttu-id="aef0e-167">可以使用逗號分隔的清單包含多個 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="aef0e-167">Multiple SIP URIs can be included as a comma-separated list.</span></span> <span data-ttu-id="aef0e-168">例如，"sip： security@litwareinc .com"，"sip： kmyer@litwareinc .com"。</span><span class="sxs-lookup"><span data-stu-id="aef0e-168">For example, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com".</span></span> <span data-ttu-id="aef0e-169">支援通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="aef0e-169">Distribution lists are supported.</span></span> <span data-ttu-id="aef0e-170">字串長度必須介於1到256個字元之間，且必須以前置詞 "sip：" 開頭。</span><span class="sxs-lookup"><span data-stu-id="aef0e-170">The string must be from 1 to 256 characters in length and must begin with the prefix "sip:".</span></span> <span data-ttu-id="aef0e-171">在您按一下 [通知 URI] 欄位之前，會顯示範例。</span><span class="sxs-lookup"><span data-stu-id="aef0e-171">Before you click in the Notification URI field an example is displayed.</span></span>
    
      - <span data-ttu-id="aef0e-172">**會議 URI**    在此案例中，將警衛至所撥打之任何緊急通話的協力廠商的 SIP URI （此為電話號碼）。</span><span class="sxs-lookup"><span data-stu-id="aef0e-172">**Conference URI**   The SIP URI, in this case the telephone number, of a third party that will be conferenced in to any emergency calls that are made.</span></span> <span data-ttu-id="aef0e-173">例如，公司的安全性辦公室可在緊急通話時接聽來電，並根據**會議模式**欄位) 中提供的值接聽或參與通話 (。</span><span class="sxs-lookup"><span data-stu-id="aef0e-173">For example, the company security office could receive a call when an emergency call is made and listen in or participate in that call (depending on the value supplied in the **Conference mode** field).</span></span> <span data-ttu-id="aef0e-174">字串長度必須為 1 到 256 字元，且開頭必須為首碼 sip:。</span><span class="sxs-lookup"><span data-stu-id="aef0e-174">The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</span></span> <span data-ttu-id="aef0e-175">會顯示範例，直到您在此欄位內按一下。</span><span class="sxs-lookup"><span data-stu-id="aef0e-175">An example is displayed until you click inside this field.</span></span>
    
      - <span data-ttu-id="aef0e-176">**會議模式**    [！注意] 如果您在 [**會議 URI** ] 欄位中指定值，則**會議模式**會決定協力廠商是否可以參與通話或只能接聽。</span><span class="sxs-lookup"><span data-stu-id="aef0e-176">**Conference mode**   If you specify a value in the **Conference URI** field, the **Conference mode** determines whether a third party can participate in the call or can only listen in.</span></span> <span data-ttu-id="aef0e-177">指定下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="aef0e-177">Specify one of the following options:</span></span>
        
          - <span data-ttu-id="aef0e-178">**單向**    協力廠商只能接聽來電者與 PSAP 操作員之間的交談。</span><span class="sxs-lookup"><span data-stu-id="aef0e-178">**One-way**   A third party can only listen to the conversation between the caller and the PSAP operator.</span></span>
        
          - <span data-ttu-id="aef0e-179">**雙向**    協力廠商可以接聽及參與來電者與 PSAP 操作員之間的呼叫。</span><span class="sxs-lookup"><span data-stu-id="aef0e-179">**Two-way**   A third party can listen in and participate in the call between the caller and the PSAP operator.</span></span>

6.  <span data-ttu-id="aef0e-180">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aef0e-180">Click **Commit**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="aef0e-p119">當您建立使用者原則時，該原則並不會自動套用至任何使用者或網路網站。若要將原則套用至使用者，請按一下左導覽列中的 [使用者]<STRONG></STRONG>。尋找要套用原則的使用者。在 [編輯]<STRONG></STRONG> 功能表上，按一下 [顯示詳細資料]<STRONG></STRONG>。在 [編輯 Lync Server 使用者]<STRONG></STRONG> 頁面上，從 [位置原則]<STRONG></STRONG> 下拉式清單中選取新的位置原則，然後按一下 [認可]<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="aef0e-p119">When you create a user policy, initially that policy does not apply to any users or network sites. To apply the policy to a user, click <STRONG>Users</STRONG> in the left navigation bar. Find the user to which you want to apply the policy. On the <STRONG>Edit</STRONG> menu, click <STRONG>Show details</STRONG>. On the <STRONG>Edit Lync Server User</STRONG> page, select the new location policy from the <STRONG>Location policy</STRONG> drop-down list and then click <STRONG>Commit</STRONG>.</span></span><BR><span data-ttu-id="aef0e-p120">若要將原則套用至網路網站，請按一下左導覽列中的 [網路設定]<STRONG></STRONG>，然後按一下 [站台]<STRONG></STRONG>。尋找要套用原則的網路網站。在 [編輯]<STRONG></STRONG> 功能表上，按一下 [顯示詳細資料]<STRONG></STRONG>。在 [編輯站台]<STRONG></STRONG> 中，從 [位置原則]<STRONG></STRONG> 下拉式清單中選取新的位置原則，然後按一下 [認可]<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="aef0e-p120">To apply the policy to a network site, click <STRONG>Network Configuration</STRONG> in the left navigation bar and then click <STRONG>Site</STRONG>. Find the network site to which you want to apply the policy. On the <STRONG>Edit</STRONG> menu, click <STRONG>Show details</STRONG>. In <STRONG>Edit Site</STRONG>, select the new location policy from the <STRONG>Location policy</STRONG> drop-down list and then click <STRONG>Commit</STRONG>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-location-policy-in-lync-server-control-panel"></a><span data-ttu-id="aef0e-190">在 Lync Server 控制台中修改位置原則</span><span class="sxs-lookup"><span data-stu-id="aef0e-190">To modify a location policy in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="aef0e-191">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="aef0e-191">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aef0e-192">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="aef0e-192">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="aef0e-193">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="aef0e-193">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aef0e-194">在左導覽列中按一下 **[網路設定]**，然後按一下 **[位置原則]**。</span><span class="sxs-lookup"><span data-stu-id="aef0e-194">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="aef0e-195">在 **[位置原則]** 頁面上，選取您要修改的位置原則。</span><span class="sxs-lookup"><span data-stu-id="aef0e-195">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="aef0e-196">在 [編輯]\*\*\*\* 功能表上，按一下 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aef0e-196">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="aef0e-197">在「編輯位置原則」\*\*\*\* 頁面上視需要修改欄位 (如需詳細資訊，請參閱本主題前述＜建立新的位置原則＞程序中的＜步驟 5＞)。</span><span class="sxs-lookup"><span data-stu-id="aef0e-197">On the **Edit Location Policy** page, modify the fields as necessary (for details, see Step 5 in the "To create a new location policy" procedures earlier in this topic).</span></span>

7.  <span data-ttu-id="aef0e-198">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aef0e-198">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aef0e-199">另請參閱</span><span class="sxs-lookup"><span data-stu-id="aef0e-199">See Also</span></span>


[<span data-ttu-id="aef0e-200">在 Lync Server 2013 中刪除位置原則</span><span class="sxs-lookup"><span data-stu-id="aef0e-200">Deleting a location policy in Lync Server 2013</span></span>](lync-server-2013-deleting-a-location-policy.md)  


[<span data-ttu-id="aef0e-201">定義 Lync Server 2013 的位置原則</span><span class="sxs-lookup"><span data-stu-id="aef0e-201">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)  


[<span data-ttu-id="aef0e-202">在 Lync Server 2013 中設定休止通話的電話號碼分機號碼</span><span class="sxs-lookup"><span data-stu-id="aef0e-202">Configure phone number extensions for parking calls in Lync Server 2013</span></span>](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

