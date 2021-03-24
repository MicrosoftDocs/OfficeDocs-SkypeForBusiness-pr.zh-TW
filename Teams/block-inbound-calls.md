---
title: 在 Microsoft Teams 中封鎖來電
ms.author: v-cichur
author: cichur
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking.
ms.openlocfilehash: fcf50f96f352cfb72ff3bd700f2118c3cda51dd7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092861"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="50154-102">封鎖來電</span><span class="sxs-lookup"><span data-stu-id="50154-102">Block inbound calls</span></span>

<span data-ttu-id="50154-103">電話系統直接路由和通話方案支援封鎖從公用交換電話網絡 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="50154-103">Phone System Direct Routing and Calling Plans support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="50154-104">此功能可定義租使用者全域號碼模式清單，以便針對相符專案清單檢查每個傳入 PSTN 呼叫的來電者識別碼。</span><span class="sxs-lookup"><span data-stu-id="50154-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="50154-105">如果相符，來電會遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="50154-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="50154-106">此來電封鎖功能僅適用于來自 PSTN 的來電，且僅適用于租使用者全域。</span><span class="sxs-lookup"><span data-stu-id="50154-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="50154-107">它無法以每個使用者為基礎使用。</span><span class="sxs-lookup"><span data-stu-id="50154-107">It's not available on a per-user basis.</span></span>  

>[!NOTE]
> <span data-ttu-id="50154-108">封鎖的來電者在遭到封鎖時，可能會遇到稍有不同的行為。</span><span class="sxs-lookup"><span data-stu-id="50154-108">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="50154-109">此行為是根據封鎖來電者的電信公司如何處理不允許成功完成通話的通知所決定。</span><span class="sxs-lookup"><span data-stu-id="50154-109">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="50154-110">範例可能包括電信公司訊息，指出通話無法以撥號完成，或只是放棄通話。</span><span class="sxs-lookup"><span data-stu-id="50154-110">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="50154-111">通話封鎖系統管理員控制項和資訊</span><span class="sxs-lookup"><span data-stu-id="50154-111">Call blocking admin controls and information</span></span>

<span data-ttu-id="50154-112">封鎖號碼的系統管理員控制項僅使用 PowerShell 提供。</span><span class="sxs-lookup"><span data-stu-id="50154-112">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="50154-113">數位區塊模式定義為正則運算式模式。</span><span class="sxs-lookup"><span data-stu-id="50154-113">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="50154-114">運算式的順序是不重要的，清單中符合的第一個模式會導致通話遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="50154-114">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="50154-115">在封鎖的來電者清單中新增或移除的新號碼或模式最多可能需要 24 小時，模式才能變成使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="50154-115">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="50154-116">封鎖 PowerShell 命令的通話</span><span class="sxs-lookup"><span data-stu-id="50154-116">Call blocking PowerShell commands</span></span>

<span data-ttu-id="50154-117">您可以使用新增、取得、設定、**移除**     - **CsInboundBlockedNumberPattern** Cmdlet 來管理數位模式。</span><span class="sxs-lookup"><span data-stu-id="50154-117">You manage number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="50154-118">您可以使用這些 Cmdlet 來管理一個給定的模式，包括切換啟用給定模式的能力。</span><span class="sxs-lookup"><span data-stu-id="50154-118">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="50154-119">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) 會針對每個清單，會返回新到租使用者清單的所有封鎖數位模式清單，包括名稱、描述、已啟用 (True/False) 和 Pattern。</span><span class="sxs-lookup"><span data-stu-id="50154-119">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="50154-120">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) 會新增封鎖的號碼模式至租使用者清單。</span><span class="sxs-lookup"><span data-stu-id="50154-120">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="50154-121">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) 會從租使用者清單中移除封鎖的號碼模式。</span><span class="sxs-lookup"><span data-stu-id="50154-121">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="50154-122">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) 會修改租使用者清單中封鎖之數位模式的一或多個參數。</span><span class="sxs-lookup"><span data-stu-id="50154-122">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="50154-123">檢視及啟用整個通話封鎖功能是由取得、設定 \*\*\*\*  - **CsTenantBlockingCallingNumbers** Cmdlet 管理。</span><span class="sxs-lookup"><span data-stu-id="50154-123">Viewing and activating the entire call blocking feature is managed through the **Get**, **Set** -**CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="50154-124">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) 會返回全域封鎖數位清單的參數，包括啟用 (True/False) 。</span><span class="sxs-lookup"><span data-stu-id="50154-124">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="50154-125">除了開啟或關閉功能外，無法手動修改單一全域租使用者策略。</span><span class="sxs-lookup"><span data-stu-id="50154-125">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="50154-126">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) 允許修改全域租使用者封鎖的通話，以在租使用者層級開啟和關閉。</span><span class="sxs-lookup"><span data-stu-id="50154-126">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="50154-127">範例</span><span class="sxs-lookup"><span data-stu-id="50154-127">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="50154-128">封鎖數位</span><span class="sxs-lookup"><span data-stu-id="50154-128">Block a number</span></span>

<span data-ttu-id="50154-129">在此範例中， **啟用** 和 **描述** 參數為選擇性。</span><span class="sxs-lookup"><span data-stu-id="50154-129">In this example, the **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="50154-130">建立新模式會將模式預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="50154-130">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="50154-131">描述是提供詳細資訊的選擇性欄位。</span><span class="sxs-lookup"><span data-stu-id="50154-131">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="50154-132">我們建議您提供有意義的名稱，以便輕鬆瞭解新增模式的原因。</span><span class="sxs-lookup"><span data-stu-id="50154-132">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="50154-133">如果只要封鎖垃圾郵件號碼，請考慮將規則命名為符合的數位模式，並根據需要在描述中新增其他資訊。</span><span class="sxs-lookup"><span data-stu-id="50154-133">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="50154-134">使用正則運算式和 Regex (模式) 。</span><span class="sxs-lookup"><span data-stu-id="50154-134">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="50154-135">在測試和驗證之前，請允許複製時間。</span><span class="sxs-lookup"><span data-stu-id="50154-135">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="50154-136">允許數位</span><span class="sxs-lookup"><span data-stu-id="50154-136">Allow a number</span></span>

<span data-ttu-id="50154-137">在此範例中， **需要身分** 識別參數。</span><span class="sxs-lookup"><span data-stu-id="50154-137">In this example, the **Identity** parameter is required.</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="50154-138">如果身分識別未知，請使用 **Get-CsInboundBlockedNumberPattern** Cmdlet 來先找出正確的模式，並記下身分識別。</span><span class="sxs-lookup"><span data-stu-id="50154-138">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="50154-139">接著，執行 **Remove-CsTenantBlockedNumberPattern** Cmdlet，並傳遞適當的身分識別值。</span><span class="sxs-lookup"><span data-stu-id="50154-139">Then, run the **Remove-CsTenantBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="50154-140">在測試和驗證之前，請允許複製時間。</span><span class="sxs-lookup"><span data-stu-id="50154-140">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="50154-141">查看所有數位模式</span><span class="sxs-lookup"><span data-stu-id="50154-141">View all number patterns</span></span>

<span data-ttu-id="50154-142">此 Cmdlet 會針對租使用者輸入的所有封鎖號碼清單：</span><span class="sxs-lookup"><span data-stu-id="50154-142">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="50154-143">使用內建的 PowerShell 篩選功能，以根據需要剖析所返回的值。</span><span class="sxs-lookup"><span data-stu-id="50154-143">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="50154-144">新增數位例外</span><span class="sxs-lookup"><span data-stu-id="50154-144">Add number exceptions</span></span>

<span data-ttu-id="50154-145">您可以使用新增、取得、設定、移除 \*\*\*\* \*\*\*\* \*\*\*\*  - **CsTenantBlockNumberExceptionPattern** Cmdlet，為封鎖的編號模式新增例外。</span><span class="sxs-lookup"><span data-stu-id="50154-145">You can add exceptions to blocked number patterns by using the **New**, **Get**, **Set**, **Remove** -**CsTenantBlockNumberExceptionPattern** cmdlets.</span></span>

- <span data-ttu-id="50154-146">[New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) 會將數位例外模式新增到租使用者清單中。</span><span class="sxs-lookup"><span data-stu-id="50154-146">[New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="50154-147">[Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) 會返回新加入租使用者清單的所有數位例外模式清單。</span><span class="sxs-lookup"><span data-stu-id="50154-147">[Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="50154-148">[Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) 會修改一或多個參數至租使用者清單中的數位例外模式。</span><span class="sxs-lookup"><span data-stu-id="50154-148">[Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="50154-149">[Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) 會從租使用者清單中移除數位例外模式。</span><span class="sxs-lookup"><span data-stu-id="50154-149">[Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="50154-150">範例</span><span class="sxs-lookup"><span data-stu-id="50154-150">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="50154-151">新增數位例外</span><span class="sxs-lookup"><span data-stu-id="50154-151">Add a number exception</span></span>

<span data-ttu-id="50154-152">在此範例中，會建立新的數位例外模式，且預設會新增為已啟用的模式。</span><span class="sxs-lookup"><span data-stu-id="50154-152">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="50154-153">啟用 **和\*\*\*\*描述** 參數為選擇性。</span><span class="sxs-lookup"><span data-stu-id="50154-153">The **Enabled** and **Description** parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="50154-154">查看所有數位例外</span><span class="sxs-lookup"><span data-stu-id="50154-154">View all number exceptions</span></span>

<span data-ttu-id="50154-155">在此範例中， **身分識別** 參數為選擇性。</span><span class="sxs-lookup"><span data-stu-id="50154-155">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="50154-156">如果未指定 **Identity** 參數，此 Cmdlet 會返回為租使用者輸入的所有數位例外模式清單。</span><span class="sxs-lookup"><span data-stu-id="50154-156">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="50154-157">修改數位例外</span><span class="sxs-lookup"><span data-stu-id="50154-157">Modify a number exception</span></span>

<span data-ttu-id="50154-158">在此範例中， **身分識別** 參數為必填專案。</span><span class="sxs-lookup"><span data-stu-id="50154-158">In this example, the **Identity** parameter is mandatory.</span></span> <span data-ttu-id="50154-159">**Set-CsTenantBlockedNumberExceptionPattern** Cmdlet 可讓您修改一或多個指定數位模式身分識別的參數。</span><span class="sxs-lookup"><span data-stu-id="50154-159">The **Set-CsTenantBlockedNumberExceptionPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="50154-160">移除數位例外</span><span class="sxs-lookup"><span data-stu-id="50154-160">Remove a number exception</span></span>

<span data-ttu-id="50154-161">在此範例中， **需要身分** 識別參數。</span><span class="sxs-lookup"><span data-stu-id="50154-161">In this example, the **Identity** parameter is required.</span></span> <span data-ttu-id="50154-162">此 Cmdlet 會從租使用者清單中移除給定的數位模式。</span><span class="sxs-lookup"><span data-stu-id="50154-162">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="50154-163">如果身分識別未知，請使用 **Get-CsInboundBlockedNumberPattern** Cmdlet 來先找出正確的模式，並記下身分識別。</span><span class="sxs-lookup"><span data-stu-id="50154-163">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="50154-164">接著，執行 **Remove-CsTenantBlockedNumberExceptionPattern** Cmdlet，並傳遞適當的身分識別值。</span><span class="sxs-lookup"><span data-stu-id="50154-164">Then, run the **Remove-CsTenantBlockedNumberExceptionPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="50154-165">在測試和驗證之前，請允許複製時間。</span><span class="sxs-lookup"><span data-stu-id="50154-165"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="50154-166">測試數位是否被封鎖</span><span class="sxs-lookup"><span data-stu-id="50154-166">Test whether a number is blocked</span></span>

<span data-ttu-id="50154-167">使用 **Test-CsInboundBlockedNumberPattern** Cmdlet 來驗證是否已封鎖租使用者中的數位。</span><span class="sxs-lookup"><span data-stu-id="50154-167">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="50154-168">在此範例中， **需要 PhoneNumber** 和 **租使用者** 參數。</span><span class="sxs-lookup"><span data-stu-id="50154-168">In this example, the **PhoneNumber** and **Tenant** parameters are required.</span></span> <span data-ttu-id="50154-169">**PhoneNumber 參數** 應該是不含任何其他字元的數值字串，例如 + 或 -。</span><span class="sxs-lookup"><span data-stu-id="50154-169">The **PhoneNumber** parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="50154-170">在 TRPS 中， **租使用者參數** 為選擇性。</span><span class="sxs-lookup"><span data-stu-id="50154-170">In TRPS, the **Tenant parameter** is optional.</span></span> <span data-ttu-id="50154-171">如果租使用者中的數位被封鎖，則產生的 **isNumberBlocked 參數** 會返回 True 的值，如果尚未封鎖，則為 False。</span><span class="sxs-lookup"><span data-stu-id="50154-171">The resulting **isNumberBlocked** parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="50154-172">HTTPResponseCode</span><span class="sxs-lookup"><span data-stu-id="50154-172">httpResponseCode</span></span>  |<span data-ttu-id="50154-173">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="50154-173">isNumberBlocked</span></span>   |<span data-ttu-id="50154-174">errorMessage</span><span class="sxs-lookup"><span data-stu-id="50154-174">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="50154-175">200</span><span class="sxs-lookup"><span data-stu-id="50154-175">200</span></span>    | <span data-ttu-id="50154-176">真</span><span class="sxs-lookup"><span data-stu-id="50154-176">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="50154-177">HTTPResponseCode</span><span class="sxs-lookup"><span data-stu-id="50154-177">httpResponseCode</span></span>  |<span data-ttu-id="50154-178">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="50154-178">isNumberBlocked</span></span>   |<span data-ttu-id="50154-179">errorMessage</span><span class="sxs-lookup"><span data-stu-id="50154-179">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="50154-180">200</span><span class="sxs-lookup"><span data-stu-id="50154-180">200</span></span>    | <span data-ttu-id="50154-181">假</span><span class="sxs-lookup"><span data-stu-id="50154-181">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="50154-182">Regex 注意事項</span><span class="sxs-lookup"><span data-stu-id="50154-182">A note about Regex</span></span>

<span data-ttu-id="50154-183">如先前所述，封鎖來電者的模式比對是使用 Regex 完成。</span><span class="sxs-lookup"><span data-stu-id="50154-183">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="50154-184">線上提供多種工具，可協助驗證 Regex 模式相符。</span><span class="sxs-lookup"><span data-stu-id="50154-184">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="50154-185">如果您不熟悉 Regex 模式，建議您花一些時間熟悉基本功能。</span><span class="sxs-lookup"><span data-stu-id="50154-185">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="50154-186">若要確定您獲得預期的結果，請使用驗證模式比對的工具，再新增封鎖的號碼比對至租使用者。</span><span class="sxs-lookup"><span data-stu-id="50154-186">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>