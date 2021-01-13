---
title: 管理增強型9-1-1 與位置服務
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 商務用 skype 伺服器支援增強型 9-1-1 (E9-1-1) 呼叫從商務用 Skype 用戶端。 當您設定 E9-1-1 的商務用 Skype Server 時，來自商務用 Skype 的緊急通話包含緊急回應位置 (ERL) 位置資訊服務資料庫中的資訊。
ms.openlocfilehash: c5b626763de78495a2feaa5ecb1ba77e367bd77d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817473"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a><span data-ttu-id="afeb7-104">在 Busines Server 的 Skype 中管理增強型9-1-1 與位置服務</span><span class="sxs-lookup"><span data-stu-id="afeb7-104">Manage enhanced 9-1-1 and the Location service in Skype for Busines Server</span></span>

<span data-ttu-id="afeb7-105">商務用 skype 伺服器支援增強型 9-1-1 (E9-1-1) 呼叫從商務用 Skype 用戶端。</span><span class="sxs-lookup"><span data-stu-id="afeb7-105">Skype for Business Server supports Enhanced 9-1-1 (E9-1-1) calling from Skype for Business clients.</span></span> <span data-ttu-id="afeb7-106">當您設定 E9-1-1 的商務用 Skype Server 時，來自商務用 Skype 的緊急通話包含緊急回應位置 (ERL) 位置資訊服務資料庫中的資訊。</span><span class="sxs-lookup"><span data-stu-id="afeb7-106">When you configure Skype for Business Server for E9-1-1, emergency calls placed from Skype for Business include Emergency Response Location (ERL) information from the Location Information service database.</span></span> <span data-ttu-id="afeb7-107">使用本文中的程式來管理位置原則。</span><span class="sxs-lookup"><span data-stu-id="afeb7-107">Use the procedures in this article to manage location policy.</span></span>

> [!Note]
> <span data-ttu-id="afeb7-108">如需部署高級 Enterprise Voice 功能（如 E9-1-1 和 Location 資訊服務）的詳細資訊，請參閱 [Deploy Advanced Enterprise Voice features](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md)。</span><span class="sxs-lookup"><span data-stu-id="afeb7-108">For details on deploying advanced Enterprise Voice features, such as E9-1-1 and the Location Information service, see [Deploy advanced Enterprise Voice features](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md).</span></span>

<span data-ttu-id="afeb7-109">在商務用 Skype Server 中，您可以使用位置原則，套用與增強型 9-1-1 (E9-1-1) 功能及使用者或連絡人的位置設定相關的設定。</span><span class="sxs-lookup"><span data-stu-id="afeb7-109">In Skype for Business Server, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="afeb7-110">位置原則會判斷使用者是否已啟用 E9-1-1，如果是，則會決定緊急電話的行為。</span><span class="sxs-lookup"><span data-stu-id="afeb7-110">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="afeb7-111">例如，您可以使用位置原則來定義組成緊急電話的數字 (例如，在美國為 911)、是否應自動告知公司的安全部門，以及應如何路由傳送來電。</span><span class="sxs-lookup"><span data-stu-id="afeb7-111">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="afeb7-112">您可以在商務用 Skype Server [控制台] 中的 [ **網路** 設定] 群組中設定位置原則。</span><span class="sxs-lookup"><span data-stu-id="afeb7-112">You can configure location policies from the **Network Configuration** group in the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="afeb7-113">您可以從商務用 Skype Server 控制台，查看、建立、修改或刪除位置原則。</span><span class="sxs-lookup"><span data-stu-id="afeb7-113">From the Skype for Business Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="afeb7-114">請使用下列程序來檢視位置原則的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="afeb7-114">Use the following procedure to view information about location policies.</span></span> 


## <a name="view-location-policy-information"></a><span data-ttu-id="afeb7-115">查看位置原則資訊</span><span class="sxs-lookup"><span data-stu-id="afeb7-115">View location policy information</span></span> 

1.  <span data-ttu-id="afeb7-116">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="afeb7-116">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="afeb7-117">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="afeb7-117">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="afeb7-118">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **位置原則**]。</span><span class="sxs-lookup"><span data-stu-id="afeb7-118">In the left navigation bar, click **Network Configuration**, and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="afeb7-119">在 **[位置原則]** 頁面上，選取您要修改的位置原則。</span><span class="sxs-lookup"><span data-stu-id="afeb7-119">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="afeb7-120">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="afeb7-120">On the **Edit** menu, click **Show details**.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="afeb7-121">您一次只能檢視一個位置原則的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="afeb7-121">You can only view information about one location policy at a time.</span></span>

<span data-ttu-id="afeb7-p105">依預設會有名為「通用」的單一原則存在，且無法刪除或重新命名。但您可以修改全域原則。若您未建立網站原則或個別使用者原則，則所有使用者與連絡人都會套用此原則。特定的使用者必須套用個別使用者原則。</span><span class="sxs-lookup"><span data-stu-id="afeb7-p105">A single policy, called Global, exists by default and cannot be deleted or renamed. However, you can modify the Global policy. This policy will apply to all users and contacts, unless you create site policies or per-user policies. Per-user policies must be applied to specific users.</span></span>


## <a name="create-or-modify-a-location-policy"></a><span data-ttu-id="afeb7-126">建立或修改位置原則</span><span class="sxs-lookup"><span data-stu-id="afeb7-126">Create or modify a location policy</span></span> 

<span data-ttu-id="afeb7-127">在商務用 Skype Server 中，您可以從位置資訊服務覆寫用戶端要求進行位置更新之間的預設時間長度。</span><span class="sxs-lookup"><span data-stu-id="afeb7-127">In Skype for Business Server, you can override the default amount of time between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="afeb7-128">預設值為 4 小時。</span><span class="sxs-lookup"><span data-stu-id="afeb7-128">The default value is 4 hours.</span></span> <span data-ttu-id="afeb7-129">使用 **Set-CsLocationPolicy** Cmdlet 搭配 LocationRefreshInterval 參數可以覆寫預設值。</span><span class="sxs-lookup"><span data-stu-id="afeb7-129">Use the **Set-CsLocationPolicy** cmdlet with the LocationRefreshInterval parameter to override the default value.</span></span>


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a><span data-ttu-id="afeb7-130">在商務用 Skype Server 控制台中建立新的位置原則</span><span class="sxs-lookup"><span data-stu-id="afeb7-130">To create a new location policy in the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="afeb7-131">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="afeb7-131">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="afeb7-132">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="afeb7-132">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="afeb7-133">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **位置原則**]。</span><span class="sxs-lookup"><span data-stu-id="afeb7-133">In the left navigation bar, click **Network Configuration**, and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="afeb7-134">在「位置原則」頁面上按一下 [新增]，然後選取您要建立的原則類型：</span><span class="sxs-lookup"><span data-stu-id="afeb7-134">On the **Location Policy** page, click **New** and then select the type of policy you want to create:</span></span>
    
      - <span data-ttu-id="afeb7-p107">若要建立網站原則，請按一下 [站台原則]。在 [選取站台] 中選擇要套用原則的網站，然後按一下 [確定]。在「新增位置原則」頁面上，[範圍] 欄位會包含 [站台] 值，[名稱] 欄位則會包含您所選擇的網站名稱。您無法修改這些欄位。網站原則會自動套用至指定網站上的所有使用者，並且覆寫這些使用者的全域原則。</span><span class="sxs-lookup"><span data-stu-id="afeb7-p107">To create a site policy, click **Site policy**. In **Select a Site**, choose the site to which you want the policy applied and click **OK**. On the **New Location Policy** page, the **Scope** field contains the value **Site**, and the **Name** field contains the name of the site you chose. You cannot modify either of these fields. A site policy is automatically applied to all users on the specified site and overrides the global policy for those users.</span></span>
    
      - <span data-ttu-id="afeb7-p108">若要建立 [使用者原則]，請按一下 [使用者原則]。在 [新增位置原則] 中，[範圍] 欄位會包含 [使用者] 值。您無法修改此值。在 [名稱] 欄位中，輸入您要為此原則指定的名稱。使用者原則不會自動套用至任何使用者。在建立使用者原則後，您必須以手動方式將原則授與給要套用此原則的使用者或網路網站。</span><span class="sxs-lookup"><span data-stu-id="afeb7-p108">To create a **User policy**, click **User policy**. In the **New Location Policy**, the **Scope** field contains the value **User**. You cannot modify this value. In the **Name** field, type the name you want to give this policy. A user policy does not automatically apply to any users. After creating the user policy, you must manually grant the policy to the users or network sites to which you want to policy to apply.</span></span>

5.  <span data-ttu-id="afeb7-146">填入其餘欄位，如下所示：</span><span class="sxs-lookup"><span data-stu-id="afeb7-146">Fill in the remaining fields as follows:</span></span>
    
      - <span data-ttu-id="afeb7-147">**啟用增強型急診服務**   選取此核取方塊可讓與此原則相關聯的使用者 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="afeb7-147">**Enable enhanced emergency services**   Select this check box to enable the users associated with this policy for E9-1-1.</span></span> <span data-ttu-id="afeb7-148">啟用緊急服務後，商務用 Skype Server 用戶端將會在註冊時取得位置資訊，並在進行緊急通話時包含該資訊。</span><span class="sxs-lookup"><span data-stu-id="afeb7-148">When emergency services are enabled, Skype for Business Server clients will retrieve location information on registration and include that information when an emergency call is made.</span></span>
    
      - <span data-ttu-id="afeb7-149">**位置**   指定下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="afeb7-149">**Location**   Specify one of the following values:</span></span>
        
          - <span data-ttu-id="afeb7-150">**必要**   當用戶端在新位置註冊時，系統會提示使用者輸入位置資訊。</span><span class="sxs-lookup"><span data-stu-id="afeb7-150">**Required**   The user will be prompted to input location information when the client registers at a new location.</span></span> <span data-ttu-id="afeb7-151">使用者可以不輸入任何資訊而將提示關閉。</span><span class="sxs-lookup"><span data-stu-id="afeb7-151">The user can dismiss the prompt without entering any information.</span></span> <span data-ttu-id="afeb7-152">如果輸入資訊，緊急服務提供者會先接聽緊急電話，以確認該位置在路由傳送至公用安全回應點 (PSAP) 操作員 (也就是911操作員) 。</span><span class="sxs-lookup"><span data-stu-id="afeb7-152">If information is entered, an emergency call will first be answered by the emergency services provider to verify the location before being routed to the Public Safety Answering Point (PSAP) operator (that is, the 911 operator).</span></span>
        
          - <span data-ttu-id="afeb7-153">**不需要**   不會提示使用者輸入位置。</span><span class="sxs-lookup"><span data-stu-id="afeb7-153">**Not Required**   The user will not be prompted for a location.</span></span> <span data-ttu-id="afeb7-154">當通話沒有地點資訊時，緊急服務提供者會接聽來電，並要求地點。</span><span class="sxs-lookup"><span data-stu-id="afeb7-154">When a call is made with no location information, the emergency services provider will answer the call and ask for a location.</span></span>
        
          - <span data-ttu-id="afeb7-155">**免責聲明**   此選項與 **必要條件** 相同，只是使用者無法在未輸入位置資訊的情況下關閉提示。</span><span class="sxs-lookup"><span data-stu-id="afeb7-155">**Disclaimer**   This option is the same as **Required** except that the user cannot dismiss the prompt without entering location information.</span></span> <span data-ttu-id="afeb7-156">使用者仍可完成緊急通話，但沒有輸入資訊，可以完成其他電話。</span><span class="sxs-lookup"><span data-stu-id="afeb7-156">The user can still complete an emergency call, but no other calls can be completed without entering the information.</span></span> <span data-ttu-id="afeb7-157">此外，還會向使用者顯示免責聲明文字，以提醒他們拒絕輸入位置資訊的後果。</span><span class="sxs-lookup"><span data-stu-id="afeb7-157">In addition, disclaimer text will be displayed to the user that can alert them to the consequences of declining to enter location information.</span></span> <span data-ttu-id="afeb7-158">若要設定免責聲明文字，您必須使用商務用 Skype Server 管理命令介面來執行 **CsLocationPolicy** Cmdlet 或具有 EnhancedEmergencyServiceDisclaimer 參數的 **New-CsLocationPolicy** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="afeb7-158">To set the disclaimer text, you must use the Skype for Business Server Management Shell to run the **Set-CsLocationPolicy** cmdlet or the **New-CsLocationPolicy** cmdlet with the EnhancedEmergencyServiceDisclaimer parameter.</span></span> <span data-ttu-id="afeb7-159">如需詳細資訊，請參閱 [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 或 [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)。</span><span class="sxs-lookup"><span data-stu-id="afeb7-159">For details, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) or [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy).</span></span>
          
    
      - <span data-ttu-id="afeb7-160">**僅限緊急服務的使用位置** 商務用 Skype 可使用位置資訊，原因如下 (例如，將您目前位置的小組通知) 。</span><span class="sxs-lookup"><span data-stu-id="afeb7-160">**Use location for emergency services only** Skype for Business can use location information for various reasons (for example, to notify teammates of your current location).</span></span> <span data-ttu-id="afeb7-161">選取此核取方塊可確保位置資訊僅供緊急通話之用。</span><span class="sxs-lookup"><span data-stu-id="afeb7-161">Select this check box to ensure location information is available only for use with an emergency call.</span></span>
    
      - <span data-ttu-id="afeb7-162">**PSTN 使用**   方式  公用交換電話網路 (PSTN) 使用方式，用來判斷哪個語音路由將用來從使用此設定檔的用戶端路由緊急通話。</span><span class="sxs-lookup"><span data-stu-id="afeb7-162">**PSTN usage**   The public switched telephone network (PSTN) usage that will be used to determine which voice route will be used to route emergency calls from clients using this profile.</span></span> <span data-ttu-id="afeb7-163">與此使用方式關聯的路由應該指向緊急通話專用的 SIP 主幹，或緊急位置識別號碼 (ELIN) 閘道，可將緊急通話路由傳送至最近的公用安全回復點 (PSAP) 。</span><span class="sxs-lookup"><span data-stu-id="afeb7-163">The route associated with this usage should point to a SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>
    
      - <span data-ttu-id="afeb7-164">**緊急撥號號碼**   要撥通緊急服務的號碼。</span><span class="sxs-lookup"><span data-stu-id="afeb7-164">**Emergency dial number**   The number that is dialed to reach emergency services.</span></span> <span data-ttu-id="afeb7-165">此值在美國為 911。</span><span class="sxs-lookup"><span data-stu-id="afeb7-165">In the United States this value is 911.</span></span> <span data-ttu-id="afeb7-166">字串必須由 0 到 9 的數字組成，長度可為 1 到 10 位數字。</span><span class="sxs-lookup"><span data-stu-id="afeb7-166">The string must be made of the digits 0 through 9 and can be from 1 to 10 digits in length.</span></span>
    
      - <span data-ttu-id="afeb7-167">**急診撥號遮罩**   撥打時，要轉譯為 [緊急撥號號碼] 值的數位。</span><span class="sxs-lookup"><span data-stu-id="afeb7-167">**Emergency dial mask**   A number that you want to translate into the value of the emergency dial number value when it is dialed.</span></span> <span data-ttu-id="afeb7-168">例如，如果您在此欄位中輸入值212，而 [緊急撥號號碼] 欄位的值為911，如果使用者撥打212，將會對911進行呼叫。</span><span class="sxs-lookup"><span data-stu-id="afeb7-168">For example, if you enter a value of 212 in this field and the emergency dial number field has a value of 911, if a user dials 212 the call will be made to 911.</span></span> <span data-ttu-id="afeb7-169">這可讓您撥打備用的緊急號碼，並且仍然可以撥打緊急服務 (例如，如果來自國家或地區具有不同緊急號碼的某人嘗試撥打該國家或地區的號碼，而不是其目前在) 中的國家或地區號碼。</span><span class="sxs-lookup"><span data-stu-id="afeb7-169">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country or region with a different emergency number attempts to dial that country or region’s number rather than the number for the country or region they are currently in).</span></span> <span data-ttu-id="afeb7-170">您可以使用分號分隔多個值，藉此定義多組緊急撥話遮罩。</span><span class="sxs-lookup"><span data-stu-id="afeb7-170">You can define multiple emergency dial masks by separating the values with semicolons.</span></span> <span data-ttu-id="afeb7-171">例如，212; 414。</span><span class="sxs-lookup"><span data-stu-id="afeb7-171">For example, 212;414.</span></span> <span data-ttu-id="afeb7-172">字串的長度上限為 100 字元。</span><span class="sxs-lookup"><span data-stu-id="afeb7-172">Maximum length of the string is 100 characters.</span></span> <span data-ttu-id="afeb7-173">每個字元必須是 0 到 9 的數字。</span><span class="sxs-lookup"><span data-stu-id="afeb7-173">Each character must be a digit 0 through 9.</span></span>
      

        > [!IMPORTANT]  
        > <span data-ttu-id="afeb7-174">確保指定的撥號遮罩值與通話保留範圍中的數字不同。</span><span class="sxs-lookup"><span data-stu-id="afeb7-174">Ensure that the specified dial mask value is not the same as a number in a call park orbit range.</span></span> <span data-ttu-id="afeb7-175">通話保留路由優先於緊急撥號字串轉換。</span><span class="sxs-lookup"><span data-stu-id="afeb7-175">Call park routing will take precedence over emergency dial string conversion.</span></span> <span data-ttu-id="afeb7-176">若要檢視現有的通話駐留範圍，請按一下左導覽列中的 [語音功能]，然後按一下 [通話駐留]。</span><span class="sxs-lookup"><span data-stu-id="afeb7-176">To see the existing call park orbit ranges, click **Voice Features** in the left navigation bar and then click **Call Park**.</span></span> 

    
      - <span data-ttu-id="afeb7-177">**通知 URI**   進行緊急通話時， (URIs) 的一或多個 SIP 統一資源識別項。</span><span class="sxs-lookup"><span data-stu-id="afeb7-177">**Notification URI**   One or more SIP Uniform Resource Identifiers (URIs) to be notified when an emergency call is made.</span></span> <span data-ttu-id="afeb7-178">例如，每次有人撥打緊急電話時，就會透過立即訊息通知公司的安全部門。</span><span class="sxs-lookup"><span data-stu-id="afeb7-178">For example, the company security office could be notified through an instant message whenever an emergency call is made.</span></span> <span data-ttu-id="afeb7-179">如果可以使用來電者的位置，通知中會包含該位置的資訊。</span><span class="sxs-lookup"><span data-stu-id="afeb7-179">If the caller’s location is available that location will be included in the notification.</span></span> <span data-ttu-id="afeb7-180">可以使用逗號分隔的清單包含多個 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="afeb7-180">Multiple SIP URIs can be included as a comma-separated list.</span></span> <span data-ttu-id="afeb7-181">例如，"sip： security@litwareinc .com"，"sip： kmyer@litwareinc .com"。</span><span class="sxs-lookup"><span data-stu-id="afeb7-181">For example, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com".</span></span> <span data-ttu-id="afeb7-182">支援通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="afeb7-182">Distribution lists are supported.</span></span> <span data-ttu-id="afeb7-183">字串長度必須介於1到256個字元之間，且必須以前置詞 "sip：" 開頭。</span><span class="sxs-lookup"><span data-stu-id="afeb7-183">The string must be from 1 to 256 characters in length and must begin with the prefix "sip:".</span></span> <span data-ttu-id="afeb7-184">在您按一下 [通知 URI] 欄位之前，會顯示範例。</span><span class="sxs-lookup"><span data-stu-id="afeb7-184">Before you click in the Notification URI field an example is displayed.</span></span>
    
      - <span data-ttu-id="afeb7-185">**會議 URI**   在此案例中，將警衛至所撥打之任何緊急通話的協力廠商的 SIP URI （此為電話號碼）。</span><span class="sxs-lookup"><span data-stu-id="afeb7-185">**Conference URI**   The SIP URI, in this case the telephone number, of a third party that will be conferenced in to any emergency calls that are made.</span></span> <span data-ttu-id="afeb7-186">例如，公司的安全性辦公室可在緊急通話時接聽來電，並根據 **會議模式** 欄位) 中提供的值接聽或參與通話 (。</span><span class="sxs-lookup"><span data-stu-id="afeb7-186">For example, the company security office could receive a call when an emergency call is made and listen in or participate in that call (depending on the value supplied in the **Conference mode** field).</span></span> <span data-ttu-id="afeb7-187">字串長度必須為 1 到 256 字元，且開頭必須為首碼 sip:。</span><span class="sxs-lookup"><span data-stu-id="afeb7-187">The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</span></span> <span data-ttu-id="afeb7-188">會顯示範例，直到您在此欄位內按一下。</span><span class="sxs-lookup"><span data-stu-id="afeb7-188">An example is displayed until you click inside this field.</span></span>
    
      - <span data-ttu-id="afeb7-189">**會議模式**   [！注意] 如果您在 [ **會議 URI** ] 欄位中指定值，則 **會議模式** 會決定協力廠商是否可以參與通話或只能接聽。</span><span class="sxs-lookup"><span data-stu-id="afeb7-189">**Conference mode**   If you specify a value in the **Conference URI** field, the **Conference mode** determines whether a third party can participate in the call or can only listen in.</span></span> <span data-ttu-id="afeb7-190">指定下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="afeb7-190">Specify one of the following options:</span></span>
        
          - <span data-ttu-id="afeb7-191">**單向**   第三方只能聆聽來電者與 PSAP 接線員之間的對話。</span><span class="sxs-lookup"><span data-stu-id="afeb7-191">**One-way**   A third party can only listen to the conversation between the caller and the PSAP operator.</span></span>
        
          - <span data-ttu-id="afeb7-192">**雙向**   第三方可聆聽並參與來電者與 PSAP 接線員之間的通話。</span><span class="sxs-lookup"><span data-stu-id="afeb7-192">**Two-way**   A third party can listen in and participate in the call between the caller and the PSAP operator.</span></span>

6.  <span data-ttu-id="afeb7-193">按一下 [認可]。</span><span class="sxs-lookup"><span data-stu-id="afeb7-193">Click **Commit**.</span></span>


    > [!IMPORTANT]  
    > <span data-ttu-id="afeb7-194">當您建立使用者原則時，該原則並不會自動套用至任何使用者或網路網站。</span><span class="sxs-lookup"><span data-stu-id="afeb7-194">When you create a user policy, initially that policy does not apply to any users or network sites.</span></span> <span data-ttu-id="afeb7-195">若要將原則套用至使用者，請按一下左導覽列中的 [使用者]。</span><span class="sxs-lookup"><span data-stu-id="afeb7-195">To apply the policy to a user, click **Users** in the left navigation bar.</span></span> <span data-ttu-id="afeb7-196">尋找要套用原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="afeb7-196">Find the user to which you want to apply the policy.</span></span> <span data-ttu-id="afeb7-197">在 [編輯] 功能表上，按一下 [顯示詳細資料]。</span><span class="sxs-lookup"><span data-stu-id="afeb7-197">On the **Edit** menu, click **Show details**.</span></span> <span data-ttu-id="afeb7-198">在 [ **編輯服務器使用者** ] 頁面上，從 [ **位置原則** ] 下拉式清單中選取新的位置原則，然後按一下 [ **認可**]。</span><span class="sxs-lookup"><span data-stu-id="afeb7-198">On the **Edit Server User** page, select the new location policy from the **Location policy** drop-down list and then click **Commit**.</span></span><BR><span data-ttu-id="afeb7-p122">若要將原則套用至網路網站，請按一下左導覽列中的 [網路設定]，然後按一下 [站台]。尋找要套用原則的網路網站。在 [編輯] 功能表上，按一下 [顯示詳細資料]。在 [編輯站台] 中，從 [位置原則] 下拉式清單中選取新的位置原則，然後按一下 [認可]。</span><span class="sxs-lookup"><span data-stu-id="afeb7-p122">To apply the policy to a network site, click **Network Configuration** in the left navigation bar and then click **Site**. Find the network site to which you want to apply the policy. On the **Edit** menu, click **Show details**. In **Edit Site**, select the new location policy from the **Location policy** drop-down list and then click **Commit**.</span></span>


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a><span data-ttu-id="afeb7-203">在商務用 Skype Server 控制台中修改位置原則</span><span class="sxs-lookup"><span data-stu-id="afeb7-203">To modify a location policy in the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="afeb7-204">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="afeb7-204">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="afeb7-205">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="afeb7-205">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="afeb7-206">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **位置原則**]。</span><span class="sxs-lookup"><span data-stu-id="afeb7-206">In the left navigation bar, click **Network Configuration**, and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="afeb7-207">在 **[位置原則]** 頁面上，選取您要修改的位置原則。</span><span class="sxs-lookup"><span data-stu-id="afeb7-207">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="afeb7-208">在 [編輯] 功能表上，按一下 [顯示詳細資料]。</span><span class="sxs-lookup"><span data-stu-id="afeb7-208">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="afeb7-209">在「編輯位置原則」 頁面上視需要修改欄位 (如需詳細資訊，請參閱本主題前述＜建立新的位置原則＞程序中的＜步驟 5＞)。</span><span class="sxs-lookup"><span data-stu-id="afeb7-209">On the **Edit Location Policy** page, modify the fields as necessary (for details, see Step 5 in the "To create a new location policy" procedures earlier in this topic).</span></span>

7.  <span data-ttu-id="afeb7-210">按一下 [認可]。</span><span class="sxs-lookup"><span data-stu-id="afeb7-210">Click **Commit**.</span></span>

        
## <a name="delete-a-location-policy"></a><span data-ttu-id="afeb7-211">刪除位置原則</span><span class="sxs-lookup"><span data-stu-id="afeb7-211">Delete a location policy</span></span>


1.  <span data-ttu-id="afeb7-212">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="afeb7-212">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="afeb7-213">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="afeb7-213">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="afeb7-214">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **位置原則**]。</span><span class="sxs-lookup"><span data-stu-id="afeb7-214">In the left navigation bar, click **Network Configuration**, and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="afeb7-215">在 [ **位置原則** ] 頁面上，選取您要刪除的位置原則。</span><span class="sxs-lookup"><span data-stu-id="afeb7-215">On the **Location Policy** page, select the location policy that you want to delete.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="afeb7-216">您可以一次刪除一個以上的位置原則。</span><span class="sxs-lookup"><span data-stu-id="afeb7-216">You can delete more than one location policy at a time.</span></span> <span data-ttu-id="afeb7-217">若要執行此動作，請按住 CTRL 鍵並選取多個原則，並按住 CTRL 鍵。</span><span class="sxs-lookup"><span data-stu-id="afeb7-217">To do this, press CTRL and select multiple policies while holding down the CTRL key.</span></span> <span data-ttu-id="afeb7-218">或者，若要選取所有原則，請按一下 [**編輯**] 功能表上的 [全 **選**]。</span><span class="sxs-lookup"><span data-stu-id="afeb7-218">Or, to select all policies, click **Select all** on the **Edit** menu.</span></span>


5.  <span data-ttu-id="afeb7-219">在 **[編輯]** 功能表中，按一下 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="afeb7-219">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="afeb7-220">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="afeb7-220">Click **OK**.</span></span>

    > [!IMPORTANT]  
    > <span data-ttu-id="afeb7-221">您無法刪除全域位置原則。</span><span class="sxs-lookup"><span data-stu-id="afeb7-221">You cannot delete the Global location policy.</span></span> <span data-ttu-id="afeb7-222">如果您嘗試刪除通用原則，您會收到警告訊息，而且該原則會重設為其預設值。</span><span class="sxs-lookup"><span data-stu-id="afeb7-222">If you attempt to delete the Global policy you will receive a warning message and that policy will be reset to its default values.</span></span>


## <a name="see-also"></a><span data-ttu-id="afeb7-223">另請參閱</span><span class="sxs-lookup"><span data-stu-id="afeb7-223">See Also</span></span>

[<span data-ttu-id="afeb7-224">建立或修改網路網站</span><span class="sxs-lookup"><span data-stu-id="afeb7-224">Create or modify network sites</span></span>](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[<span data-ttu-id="afeb7-225">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="afeb7-225">New-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  

[<span data-ttu-id="afeb7-226">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="afeb7-226">Set-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 
 
[<span data-ttu-id="afeb7-227">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="afeb7-227">Remove-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  

[<span data-ttu-id="afeb7-228">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="afeb7-228">Get-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
