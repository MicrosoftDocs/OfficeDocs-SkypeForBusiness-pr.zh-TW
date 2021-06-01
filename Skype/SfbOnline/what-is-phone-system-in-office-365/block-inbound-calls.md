---
title: 封鎖線上商務用 Skype來電
ms.author: v-cichur
author: cichur
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Skype for Business
localization_priority: Normal
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
ms.openlocfilehash: dae0d585df2f67904712e9220f16213a2f925369
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238029"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="fce0a-102">封鎖來電</span><span class="sxs-lookup"><span data-stu-id="fce0a-102">Block inbound calls</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="fce0a-103">商務用 Skype線上通話方案現在支援封鎖從公用交換電話網路或 PSTN (來電) 。</span><span class="sxs-lookup"><span data-stu-id="fce0a-103">Skype for Business Online Calling Plans now supports blocking of inbound calls from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="fce0a-104">此功能可定義租使用者全域號碼模式清單，以便針對相符專案清單檢查每個傳入 PSTN 呼叫的來電者識別碼。</span><span class="sxs-lookup"><span data-stu-id="fce0a-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="fce0a-105">如果相符，來電會遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="fce0a-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="fce0a-106">此來電封鎖功能僅適用于來自 PSTN 的來電，且僅適用于租使用者全域。</span><span class="sxs-lookup"><span data-stu-id="fce0a-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="fce0a-107">它無法以每個使用者為基礎使用。</span><span class="sxs-lookup"><span data-stu-id="fce0a-107">It's not available on a per-user basis.</span></span>  

<span data-ttu-id="fce0a-108">這項功能目前還不適用於直接路由。</span><span class="sxs-lookup"><span data-stu-id="fce0a-108">This feature isn't yet available for Direct Routing.</span></span>

>[!NOTE]
> <span data-ttu-id="fce0a-109">封鎖的來電者在遭到封鎖時，可能會遇到稍有不同的行為。</span><span class="sxs-lookup"><span data-stu-id="fce0a-109">Blocked callers may experience slightly different behaviors when they have been blocked.</span></span> <span data-ttu-id="fce0a-110">此行為是根據封鎖來電者的電信公司如何處理不允許成功完成通話的通知所決定。</span><span class="sxs-lookup"><span data-stu-id="fce0a-110">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="fce0a-111">範例可能包括電信公司訊息，指出通話無法以撥號完成，或只是放棄通話。</span><span class="sxs-lookup"><span data-stu-id="fce0a-111">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="fce0a-112">通話封鎖系統管理控制項和資訊</span><span class="sxs-lookup"><span data-stu-id="fce0a-112">Call blocking admin controls and information</span></span>

<span data-ttu-id="fce0a-113">封鎖號碼的系統管理員控制項僅使用 PowerShell 提供。</span><span class="sxs-lookup"><span data-stu-id="fce0a-113">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="fce0a-114">數位區塊模式定義為正則運算式模式。</span><span class="sxs-lookup"><span data-stu-id="fce0a-114">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="fce0a-115">運算式的順序是不重要的，清單中符合的第一個模式會導致通話遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="fce0a-115">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="fce0a-116">在封鎖的來電者清單中新增或移除的新號碼或模式最多可能需要 24 小時，模式才能變成使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="fce0a-116">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="fce0a-117">封鎖 PowerShell 命令的通話</span><span class="sxs-lookup"><span data-stu-id="fce0a-117">Call blocking PowerShell commands</span></span>

<span data-ttu-id="fce0a-118">數位模式會透過 ```CsInboundBlockedNumberPattern``` 命令 ```New``` ```Get``` 、、和 進行管理 ```Set``` ```Remove``` 。</span><span class="sxs-lookup"><span data-stu-id="fce0a-118">Number patterns are managed through the ```CsInboundBlockedNumberPattern``` commands ```New```, ```Get```, ```Set```, and ```Remove```.</span></span> <span data-ttu-id="fce0a-119">您可以使用這些 Cmdlet 來管理一個給定的模式，包括切換啟用給定模式的能力。</span><span class="sxs-lookup"><span data-stu-id="fce0a-119">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>
- <span data-ttu-id="fce0a-120">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) 會針對每個清單，會返回新到租使用者清單的所有封鎖數位模式清單，包括名稱、描述、已啟用 (True/False) 和 Pattern。</span><span class="sxs-lookup"><span data-stu-id="fce0a-120">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="fce0a-121">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) 會新增封鎖的號碼模式至租使用者清單。</span><span class="sxs-lookup"><span data-stu-id="fce0a-121">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="fce0a-122">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) 會從租使用者清單中移除封鎖的號碼模式。</span><span class="sxs-lookup"><span data-stu-id="fce0a-122">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="fce0a-123">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) 會修改租使用者清單中封鎖之數位模式的一或多個參數。</span><span class="sxs-lookup"><span data-stu-id="fce0a-123">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="fce0a-124">檢視及啟用整個通話封鎖功能是由命令 ```CsTenantBlockingCallingNumbers``` 和 ```Get``` 管理 ```Set``` 。</span><span class="sxs-lookup"><span data-stu-id="fce0a-124">Viewing and activating the entire call blocking feature is managed through the ```CsTenantBlockingCallingNumbers``` commands ```Get``` and ```Set```.</span></span>

- <span data-ttu-id="fce0a-125">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) 會返回全域封鎖數位清單的參數，包括啟用 (True/False) 。</span><span class="sxs-lookup"><span data-stu-id="fce0a-125">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="fce0a-126">除了開啟或關閉功能外，無法手動修改單一全域租使用者策略。</span><span class="sxs-lookup"><span data-stu-id="fce0a-126">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="fce0a-127">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) 允許修改全域租使用者封鎖的通話，以在租使用者層級開啟和關閉。</span><span class="sxs-lookup"><span data-stu-id="fce0a-127">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="fce0a-128">範例</span><span class="sxs-lookup"><span data-stu-id="fce0a-128">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="fce0a-129">封鎖數位</span><span class="sxs-lookup"><span data-stu-id="fce0a-129">Block a number</span></span>

<span data-ttu-id="fce0a-130">在此範例中，and ```-Enabled``` ```-Description``` 參數為選擇性：</span><span class="sxs-lookup"><span data-stu-id="fce0a-130">In this example, the ```-Enabled``` and ```-Description``` parameters are optional:</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="fce0a-131">建立新模式會將模式預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="fce0a-131">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="fce0a-132">描述是提供詳細資訊的選擇性欄位。</span><span class="sxs-lookup"><span data-stu-id="fce0a-132">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="fce0a-133">我們建議您提供有意義的名稱，以便輕鬆瞭解新增模式的原因。</span><span class="sxs-lookup"><span data-stu-id="fce0a-133">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="fce0a-134">如果只要封鎖垃圾郵件號碼，請考慮將規則命名為符合的數位模式，並根據需要在描述中新增其他資訊。</span><span class="sxs-lookup"><span data-stu-id="fce0a-134">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="fce0a-135">使用正則運算式和 Regex (模式) 。</span><span class="sxs-lookup"><span data-stu-id="fce0a-135">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="fce0a-136">在測試和驗證之前，請允許複製時間。</span><span class="sxs-lookup"><span data-stu-id="fce0a-136">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="fce0a-137">允許數位</span><span class="sxs-lookup"><span data-stu-id="fce0a-137">Allow a number</span></span>

<span data-ttu-id="fce0a-138">在此範例中， ```-Identity``` 參數為必填項：</span><span class="sxs-lookup"><span data-stu-id="fce0a-138">In this example, the ```-Identity``` parameter is required:</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="fce0a-139">如果身分識別未知，請使用 Cmdlet 先找出正確的模式，並 ```Get-CsInboundBlockedNumberPattern``` 記下身分識別。</span><span class="sxs-lookup"><span data-stu-id="fce0a-139">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="fce0a-140">接著，執行 ```Remove-CsTenantBlockedNumberPattern``` Cmdlet 並傳遞適當的身分識別值。</span><span class="sxs-lookup"><span data-stu-id="fce0a-140">Then, run the ```Remove-CsTenantBlockedNumberPattern``` cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="fce0a-141">在測試和驗證之前，請允許複製時間。</span><span class="sxs-lookup"><span data-stu-id="fce0a-141">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="fce0a-142">查看所有數位模式</span><span class="sxs-lookup"><span data-stu-id="fce0a-142">View all number patterns</span></span>

<span data-ttu-id="fce0a-143">此 Cmdlet 會針對租使用者輸入的所有封鎖號碼清單：</span><span class="sxs-lookup"><span data-stu-id="fce0a-143">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="fce0a-144">使用內建的 PowerShell 篩選功能，以根據需要剖析所返回的值。</span><span class="sxs-lookup"><span data-stu-id="fce0a-144">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="fce0a-145">新增數位例外</span><span class="sxs-lookup"><span data-stu-id="fce0a-145">Add number exceptions</span></span>

<span data-ttu-id="fce0a-146">您可以透過命令、和 來新增例外情形到封鎖的編號 ```CsTenantBlockNumberExceptionPattern``` ```New``` ```Get``` ```Set``` 模式 ```Remove``` 。</span><span class="sxs-lookup"><span data-stu-id="fce0a-146">You can add exceptions to blocked number patterns through the ```CsTenantBlockNumberExceptionPattern``` commands, ```New```, ```Get```, ```Set```, and ```Remove```.</span></span>

- <span data-ttu-id="fce0a-147">[New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) 會將數位例外模式新增到租使用者清單中。</span><span class="sxs-lookup"><span data-stu-id="fce0a-147">[New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="fce0a-148">[Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) 會返回新加入租使用者清單的所有數位例外模式清單。</span><span class="sxs-lookup"><span data-stu-id="fce0a-148">[Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="fce0a-149">[Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) 會修改一或多個參數至租使用者清單中的數位例外模式。</span><span class="sxs-lookup"><span data-stu-id="fce0a-149">[Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="fce0a-150">[Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) 會從租使用者清單中移除數位例外模式。</span><span class="sxs-lookup"><span data-stu-id="fce0a-150">[Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="fce0a-151">範例</span><span class="sxs-lookup"><span data-stu-id="fce0a-151">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="fce0a-152">新增數位例外</span><span class="sxs-lookup"><span data-stu-id="fce0a-152">Add a number exception</span></span>

<span data-ttu-id="fce0a-153">在此範例中，會建立新的數位例外模式，且預設會新增為已啟用的模式。</span><span class="sxs-lookup"><span data-stu-id="fce0a-153">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="fce0a-154">和 ```-Enabled``` ```-Description``` 參數為選擇性。</span><span class="sxs-lookup"><span data-stu-id="fce0a-154">The ```-Enabled``` and ```-Description``` parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="fce0a-155">查看所有數位例外</span><span class="sxs-lookup"><span data-stu-id="fce0a-155">View all number exceptions</span></span>

<span data-ttu-id="fce0a-156">在此範例中，-Identity 參數為選擇性。</span><span class="sxs-lookup"><span data-stu-id="fce0a-156">In this example, the -Identity parameter is optional.</span></span> <span data-ttu-id="fce0a-157">如果未指定參數，此 Cmdlet 會返回為租使用者輸入的所有數位例外 ```-Identity``` 模式清單。</span><span class="sxs-lookup"><span data-stu-id="fce0a-157">If the ```-Identity``` parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="fce0a-158">修改數位例外</span><span class="sxs-lookup"><span data-stu-id="fce0a-158">Modify a number exception</span></span>

<span data-ttu-id="fce0a-159">在此範例中，-Identity 參數為必填專案。</span><span class="sxs-lookup"><span data-stu-id="fce0a-159">In this example, the -Identity parameter is mandatory.</span></span> <span data-ttu-id="fce0a-160">```Set-CsTenantBlockedNumberExceptionPattern```Cmdlet 可讓您修改指定數位模式身分識別的一或多個參數。</span><span class="sxs-lookup"><span data-stu-id="fce0a-160">The ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="fce0a-161">移除數位例外</span><span class="sxs-lookup"><span data-stu-id="fce0a-161">Remove a number exception</span></span>

<span data-ttu-id="fce0a-162">在此範例中， ```-Identity``` 參數為必填項。</span><span class="sxs-lookup"><span data-stu-id="fce0a-162">In this example, the ```-Identity``` parameter is required.</span></span> <span data-ttu-id="fce0a-163">此 Cmdlet 會移除租使用者清單中的給定數位模式。</span><span class="sxs-lookup"><span data-stu-id="fce0a-163">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="fce0a-164">如果身分識別未知，請使用 Cmdlet 先找出正確的模式，並 ```Get-CsInboundBlockedNumberPattern``` 記下身分識別。</span><span class="sxs-lookup"><span data-stu-id="fce0a-164">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="fce0a-165">接著，執行 ```Remove-CsTenantBlockedNumberExceptionPattern``` Cmdlet 並傳遞適當的身分識別值。</span><span class="sxs-lookup"><span data-stu-id="fce0a-165">Then, run the ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="fce0a-166">在測試和驗證之前，請允許複製時間。</span><span class="sxs-lookup"><span data-stu-id="fce0a-166"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="fce0a-167">測試數位是否被封鎖</span><span class="sxs-lookup"><span data-stu-id="fce0a-167">Test whether a number is blocked</span></span>

<span data-ttu-id="fce0a-168">使用 ```Test-CsInboundBlockedNumberPattern``` Cmdlet 驗證租使用者中是否封鎖數位。</span><span class="sxs-lookup"><span data-stu-id="fce0a-168">Use the ```Test-CsInboundBlockedNumberPattern``` cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="fce0a-169">在此範例中， ```-Phonenumber``` 需要 ```-Tenant``` and 參數。</span><span class="sxs-lookup"><span data-stu-id="fce0a-169">In this example, the ```-Phonenumber``` and ```-Tenant``` parameters are required.</span></span> <span data-ttu-id="fce0a-170">參數 ```-PhoneNumber``` 應為不含任何其他字元的數值字串，例如 + 或 -。</span><span class="sxs-lookup"><span data-stu-id="fce0a-170">The ```-PhoneNumber``` parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="fce0a-171">在 TRPS 中 ```-Tenant parameter``` ，是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="fce0a-171">In TRPS, the ```-Tenant parameter``` is optional.</span></span> <span data-ttu-id="fce0a-172">如果租使用者中的數位被封鎖，產生的參數會返回 True 的值，如果未封鎖，則會返回 ```isNumberBlocked``` False 值。</span><span class="sxs-lookup"><span data-stu-id="fce0a-172">The resulting ```isNumberBlocked``` parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="fce0a-173">HTTPResponseCode</span><span class="sxs-lookup"><span data-stu-id="fce0a-173">httpResponseCode</span></span>  |<span data-ttu-id="fce0a-174">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="fce0a-174">isNumberBlocked</span></span>   |<span data-ttu-id="fce0a-175">errorMessage</span><span class="sxs-lookup"><span data-stu-id="fce0a-175">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="fce0a-176">200</span><span class="sxs-lookup"><span data-stu-id="fce0a-176">200</span></span>    | <span data-ttu-id="fce0a-177">真</span><span class="sxs-lookup"><span data-stu-id="fce0a-177">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="fce0a-178">HTTPResponseCode</span><span class="sxs-lookup"><span data-stu-id="fce0a-178">httpResponseCode</span></span>  |<span data-ttu-id="fce0a-179">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="fce0a-179">isNumberBlocked</span></span>   |<span data-ttu-id="fce0a-180">errorMessage</span><span class="sxs-lookup"><span data-stu-id="fce0a-180">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="fce0a-181">200</span><span class="sxs-lookup"><span data-stu-id="fce0a-181">200</span></span>    | <span data-ttu-id="fce0a-182">假</span><span class="sxs-lookup"><span data-stu-id="fce0a-182">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="fce0a-183">Regex 注意事項</span><span class="sxs-lookup"><span data-stu-id="fce0a-183">A note about Regex</span></span>

<span data-ttu-id="fce0a-184">如先前所述，封鎖來電者的模式比對是使用 Regex 完成。</span><span class="sxs-lookup"><span data-stu-id="fce0a-184">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="fce0a-185">線上提供多種工具，可協助驗證 Regex 模式相符。</span><span class="sxs-lookup"><span data-stu-id="fce0a-185">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="fce0a-186">如果您不熟悉 Regex 模式，建議您花一些時間熟悉基本功能。</span><span class="sxs-lookup"><span data-stu-id="fce0a-186">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="fce0a-187">若要確定您獲得預期的結果，請使用驗證模式比對的工具，再新增封鎖的號碼比對至租使用者。</span><span class="sxs-lookup"><span data-stu-id="fce0a-187">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="fce0a-188">相關主題</span><span class="sxs-lookup"><span data-stu-id="fce0a-188">Related topics</span></span>

- [<span data-ttu-id="fce0a-189">設定您的電腦以使用 商務用 Skype管理線上Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fce0a-189">Set up your computer to manage Skype for Business Online by using Windows PowerShell</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
