---
title: 在商務用 Skype Online 中封鎖撥入通話
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
ms.openlocfilehash: 16a646af3e456bb68a2a582cad7d6b742100c650
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820913"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="6d334-102">封鎖撥入通話</span><span class="sxs-lookup"><span data-stu-id="6d334-102">Block inbound calls</span></span>

<span data-ttu-id="6d334-103">商務用 Skype Online 通話方案現在支援封鎖從公用交換電話網絡 (PSTN) 的入站通話。</span><span class="sxs-lookup"><span data-stu-id="6d334-103">Skype for Business Online Calling Plans now supports blocking of inbound calls from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="6d334-104">此功能可讓您針對清單中的每個撥入 PSTN 呼叫，針對其進行檢查，以進行數位模式的租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="6d334-104">This feature allows a tenant global list of number patterns to be defined so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="6d334-105">如果進行了相符，就會拒絕來電。</span><span class="sxs-lookup"><span data-stu-id="6d334-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="6d334-106">這個輸入呼叫封鎖功能只能在源自 PSTN 的撥入通話中運作，且僅適用于租使用者全域基礎。</span><span class="sxs-lookup"><span data-stu-id="6d334-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant-global basis.</span></span> <span data-ttu-id="6d334-107">在每個使用者的基礎上無法使用。</span><span class="sxs-lookup"><span data-stu-id="6d334-107">It's not available on a per-user basis.</span></span>  

<span data-ttu-id="6d334-108">此功能尚未提供給直接路由。</span><span class="sxs-lookup"><span data-stu-id="6d334-108">This feature isn't yet available for Direct Routing.</span></span>

>[!NOTE]
> <span data-ttu-id="6d334-109">封鎖的呼叫者可能會在已封鎖的情況中遇到稍有不同的行為。</span><span class="sxs-lookup"><span data-stu-id="6d334-109">Blocked callers may experience slightly different behaviors when they have been blocked.</span></span> <span data-ttu-id="6d334-110">此行為是根據封鎖的呼叫者的載波如何處理呼叫不允許成功完成的通知而定。</span><span class="sxs-lookup"><span data-stu-id="6d334-110">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="6d334-111">範例中可能會包含一則指示來電無法完成的載波訊息，或只是要放下通話。</span><span class="sxs-lookup"><span data-stu-id="6d334-111">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="6d334-112">呼叫封鎖管理員控制與資訊</span><span class="sxs-lookup"><span data-stu-id="6d334-112">Call blocking admin controls and information</span></span>

<span data-ttu-id="6d334-113">封鎖號碼的管理員控制項只使用 PowerShell 提供。</span><span class="sxs-lookup"><span data-stu-id="6d334-113">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="6d334-114">數位區塊模式定義為一般運算式模式。</span><span class="sxs-lookup"><span data-stu-id="6d334-114">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="6d334-115">運算式的順序不重要-清單中第一個符合的模式會導致通話封鎖。</span><span class="sxs-lookup"><span data-stu-id="6d334-115">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="6d334-116">在封鎖的呼叫者清單中新增或移除的新號碼或模式，模式可能需要長達24小時才能生效。</span><span class="sxs-lookup"><span data-stu-id="6d334-116">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="6d334-117">呼叫封鎖 PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="6d334-117">Call blocking PowerShell commands</span></span>

<span data-ttu-id="6d334-118">數位模式是透過 ```CsInboundBlockedNumberPattern``` 命令 ```New``` 、 ```Get``` 、和來管理 ```Set``` ```Remove``` 。</span><span class="sxs-lookup"><span data-stu-id="6d334-118">Number patterns are managed through the ```CsInboundBlockedNumberPattern``` commands ```New```, ```Get```, ```Set```, and ```Remove```.</span></span> <span data-ttu-id="6d334-119">您可以使用這些 Cmdlet 來管理指定的模式，包括切換指定模式啟用的功能。</span><span class="sxs-lookup"><span data-stu-id="6d334-119">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>
- <span data-ttu-id="6d334-120">[CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) 會傳回已新增至租使用者清單的所有封鎖數位模式清單，包括名稱、描述、啟用 (True/False) ，以及每個的模式。</span><span class="sxs-lookup"><span data-stu-id="6d334-120">[Get-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="6d334-121">[[新-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) ] 會將封鎖的數位模式新增至租使用者清單。</span><span class="sxs-lookup"><span data-stu-id="6d334-121">[New-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="6d334-122">[移除-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) 會從租使用者清單中移除封鎖的數位模式。</span><span class="sxs-lookup"><span data-stu-id="6d334-122">[Remove-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="6d334-123">[[設定] CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern)會修改租使用者清單中封鎖數位模式的一個或多個參數。</span><span class="sxs-lookup"><span data-stu-id="6d334-123">[Set-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="6d334-124">查看並啟用整個呼叫封鎖功能是透過 ```CsTenantBlockingCallingNumbers``` 命令和來管理 ```Get``` ```Set``` 。</span><span class="sxs-lookup"><span data-stu-id="6d334-124">Viewing and activating the entire call blocking feature is managed through the ```CsTenantBlockingCallingNumbers``` commands ```Get``` and ```Set```.</span></span>

- <span data-ttu-id="6d334-125">[CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) 會傳回全域封鎖號碼清單的參數，包括啟用 (True/False) 。</span><span class="sxs-lookup"><span data-stu-id="6d334-125">[Get-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the parameters for the global blocked number list including Enabled (True/False).</span></span> <span data-ttu-id="6d334-126">只有在開啟或關閉此功能時，才能手動修改單一全域租使用者原則。</span><span class="sxs-lookup"><span data-stu-id="6d334-126">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="6d334-127">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) 可讓您在租使用者層級開啟和關閉全域租使用者封鎖通話。</span><span class="sxs-lookup"><span data-stu-id="6d334-127">[Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="6d334-128">範例</span><span class="sxs-lookup"><span data-stu-id="6d334-128">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="6d334-129">封鎖數位</span><span class="sxs-lookup"><span data-stu-id="6d334-129">Block a number</span></span>

<span data-ttu-id="6d334-130">在這個範例中， ```-Enabled``` and ```-Description``` 參數是選擇性的：</span><span class="sxs-lookup"><span data-stu-id="6d334-130">In this example, the ```-Enabled``` and ```-Description``` parameters are optional:</span></span>

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

<span data-ttu-id="6d334-131">建立新的模式會將模式新增為 [預設啟用]。</span><span class="sxs-lookup"><span data-stu-id="6d334-131">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="6d334-132">[描述] 是一個可提供詳細資訊的選用欄位。</span><span class="sxs-lookup"><span data-stu-id="6d334-132">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="6d334-133">我們建議您提供有意義的名稱，以輕鬆瞭解新增模式的原因。</span><span class="sxs-lookup"><span data-stu-id="6d334-133">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="6d334-134">在只封鎖垃圾郵件號碼的情況下，請考慮將規則命名為與要相符的數位模式相同，然後根據需要在描述中新增其他資訊。</span><span class="sxs-lookup"><span data-stu-id="6d334-134">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="6d334-135">模式是使用正則運算式與 (Regex) 進行相符。</span><span class="sxs-lookup"><span data-stu-id="6d334-135">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="6d334-136">在進行測試和驗證前，請先留出時間進行複製。</span><span class="sxs-lookup"><span data-stu-id="6d334-136">Allow time for replication before you test and validate.</span></span>

#### <a name="allow-a-number"></a><span data-ttu-id="6d334-137">允許數位</span><span class="sxs-lookup"><span data-stu-id="6d334-137">Allow a number</span></span>

<span data-ttu-id="6d334-138">在這個範例中， ```-Identity``` 參數是必要的：</span><span class="sxs-lookup"><span data-stu-id="6d334-138">In this example, the ```-Identity``` parameter is required:</span></span>

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
<span data-ttu-id="6d334-139">如果不知道身分識別，請使用 ```Get-CsInboundBlockedNumberPattern``` Cmdlet 來先找出適當的模式，並記下身分識別。</span><span class="sxs-lookup"><span data-stu-id="6d334-139">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="6d334-140">然後，執行 ```Remove-CsTenantBlockedNumberPattern``` Cmdlet 並傳遞適當的身分識別值。</span><span class="sxs-lookup"><span data-stu-id="6d334-140">Then, run the ```Remove-CsTenantBlockedNumberPattern``` cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="6d334-141">在進行測試和驗證前，請先留出時間進行複製。</span><span class="sxs-lookup"><span data-stu-id="6d334-141">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="6d334-142">查看所有數位模式</span><span class="sxs-lookup"><span data-stu-id="6d334-142">View all number patterns</span></span>

<span data-ttu-id="6d334-143">執行此 Cmdlet 會傳回為租使用者輸入的所有封鎖號碼清單：</span><span class="sxs-lookup"><span data-stu-id="6d334-143">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="6d334-144">使用內建的 PowerShell 篩選功能，根據需要分析傳回的值。</span><span class="sxs-lookup"><span data-stu-id="6d334-144">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="6d334-145">新增數位例外狀況</span><span class="sxs-lookup"><span data-stu-id="6d334-145">Add number exceptions</span></span>

<span data-ttu-id="6d334-146">您可以透過 ```CsTenantBlockNumberExceptionPattern``` 命令、、、及等方式，將例外狀況新增至封鎖的編號模式 ```New``` ```Get``` ```Set``` ```Remove``` 。</span><span class="sxs-lookup"><span data-stu-id="6d334-146">You can add exceptions to blocked number patterns through the ```CsTenantBlockNumberExceptionPattern``` commands, ```New```, ```Get```, ```Set```, and ```Remove```.</span></span>

- <span data-ttu-id="6d334-147">[新-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) 會將數位例外模式新增至租使用者清單。</span><span class="sxs-lookup"><span data-stu-id="6d334-147">[New-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="6d334-148">[CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) 會傳回已新增至租使用者清單的所有數位例外模式清單。</span><span class="sxs-lookup"><span data-stu-id="6d334-148">[Get-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="6d334-149">[[設定] CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern)會將一個或多個參數修改為租使用者清單中的數位例外模式。</span><span class="sxs-lookup"><span data-stu-id="6d334-149">[Set-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="6d334-150">[移除-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) 會移除租使用者清單中的數位例外模式。</span><span class="sxs-lookup"><span data-stu-id="6d334-150">[Remove-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="6d334-151">範例</span><span class="sxs-lookup"><span data-stu-id="6d334-151">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="6d334-152">新增數位例外狀況</span><span class="sxs-lookup"><span data-stu-id="6d334-152">Add a number exception</span></span>

<span data-ttu-id="6d334-153">在這個範例中，會建立新的數位例外模式，而且預設會將模式新增為 [啟用]。</span><span class="sxs-lookup"><span data-stu-id="6d334-153">In this example, a new number exception pattern is created and will by default add the pattern as enabled.</span></span> <span data-ttu-id="6d334-154">```-Enabled```And ```-Description``` 參數是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="6d334-154">The ```-Enabled``` and ```-Description``` parameters are optional.</span></span>

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a><span data-ttu-id="6d334-155">查看所有數位例外狀況</span><span class="sxs-lookup"><span data-stu-id="6d334-155">View all number exceptions</span></span>

<span data-ttu-id="6d334-156">在這個範例中，-身分識別參數是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="6d334-156">In this example, the -Identity parameter is optional.</span></span> <span data-ttu-id="6d334-157">如果 ```-Identity``` 未指定參數，此 Cmdlet 會傳回為租使用者輸入的所有數位例外模式清單。</span><span class="sxs-lookup"><span data-stu-id="6d334-157">If the ```-Identity``` parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="6d334-158">修改數位例外狀況</span><span class="sxs-lookup"><span data-stu-id="6d334-158">Modify a number exception</span></span>

<span data-ttu-id="6d334-159">在這個範例中，-身分識別參數是強制性的。</span><span class="sxs-lookup"><span data-stu-id="6d334-159">In this example, the -Identity parameter is mandatory.</span></span> <span data-ttu-id="6d334-160">這個 ```Set-CsTenantBlockedNumberExceptionPattern``` Cmdlet 能讓您針對指定的數位模式身分修改一或多個參數。</span><span class="sxs-lookup"><span data-stu-id="6d334-160">The ```Set-CsTenantBlockedNumberExceptionPattern``` cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span>
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="6d334-161">移除數位例外狀況</span><span class="sxs-lookup"><span data-stu-id="6d334-161">Remove a number exception</span></span>

<span data-ttu-id="6d334-162">在這個範例中， ```-Identity``` 參數是必要的。</span><span class="sxs-lookup"><span data-stu-id="6d334-162">In this example, the ```-Identity``` parameter is required.</span></span> <span data-ttu-id="6d334-163">這個 Cmdlet 會從租使用者清單中移除指定的數位模式。</span><span class="sxs-lookup"><span data-stu-id="6d334-163">This cmdlet will remove the given number pattern from the tenant list.</span></span>  <span data-ttu-id="6d334-164">如果不知道身分識別，請使用 ```Get-CsInboundBlockedNumberPattern``` Cmdlet 來先找出適當的模式，並記下身分識別。</span><span class="sxs-lookup"><span data-stu-id="6d334-164">If the identity isn't known, use the ```Get-CsInboundBlockedNumberPattern``` cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="6d334-165">然後，執行 ```Remove-CsTenantBlockedNumberExceptionPattern``` Cmdlet 並傳遞適當的身分識別值。</span><span class="sxs-lookup"><span data-stu-id="6d334-165">Then, run the ```Remove-CsTenantBlockedNumberExceptionPattern``` cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="6d334-166">在進行測試和驗證前，請先留出時間進行複製。</span><span class="sxs-lookup"><span data-stu-id="6d334-166"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="6d334-167">測試是否已封鎖某個數位</span><span class="sxs-lookup"><span data-stu-id="6d334-167">Test whether a number is blocked</span></span>

<span data-ttu-id="6d334-168">使用 ```Test-CsInboundBlockedNumberPattern``` Cmdlet 驗證租使用者中是否有某個數位遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="6d334-168">Use the ```Test-CsInboundBlockedNumberPattern``` cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="6d334-169">在這個範例中， ```-Phonenumber``` ```-Tenant``` 需要和參數。</span><span class="sxs-lookup"><span data-stu-id="6d334-169">In this example, the ```-Phonenumber``` and ```-Tenant``` parameters are required.</span></span> <span data-ttu-id="6d334-170">```-PhoneNumber```參數應該是不含任何其他字元（例如 + 或-）的數值字串。</span><span class="sxs-lookup"><span data-stu-id="6d334-170">The ```-PhoneNumber``` parameter should be a numeric string without any additional characters such as + or -.</span></span> <span data-ttu-id="6d334-171">在 TRPS 中， ```-Tenant parameter``` 是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="6d334-171">In TRPS, the ```-Tenant parameter``` is optional.</span></span> <span data-ttu-id="6d334-172">如果該 ```isNumberBlocked``` 數位在租使用者中遭到封鎖，則結果參數會傳回 True 值，如果未封鎖，則傳回 False。</span><span class="sxs-lookup"><span data-stu-id="6d334-172">The resulting ```isNumberBlocked``` parameter returns a value of True if the number is blocked in the tenant and False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|<span data-ttu-id="6d334-173">HTTPResponseCode</span><span class="sxs-lookup"><span data-stu-id="6d334-173">httpResponseCode</span></span>  |<span data-ttu-id="6d334-174">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="6d334-174">isNumberBlocked</span></span>   |<span data-ttu-id="6d334-175">errorMessage</span><span class="sxs-lookup"><span data-stu-id="6d334-175">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="6d334-176">200</span><span class="sxs-lookup"><span data-stu-id="6d334-176">200</span></span>    | <span data-ttu-id="6d334-177">滿足</span><span class="sxs-lookup"><span data-stu-id="6d334-177">True</span></span>        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|<span data-ttu-id="6d334-178">HTTPResponseCode</span><span class="sxs-lookup"><span data-stu-id="6d334-178">httpResponseCode</span></span>  |<span data-ttu-id="6d334-179">isNumberBlocked</span><span class="sxs-lookup"><span data-stu-id="6d334-179">isNumberBlocked</span></span>   |<span data-ttu-id="6d334-180">errorMessage</span><span class="sxs-lookup"><span data-stu-id="6d334-180">errorMessage</span></span> |
|---------|---------|---------|
|<span data-ttu-id="6d334-181">200</span><span class="sxs-lookup"><span data-stu-id="6d334-181">200</span></span>    | <span data-ttu-id="6d334-182">虛假</span><span class="sxs-lookup"><span data-stu-id="6d334-182">False</span></span>        |         |

## <a name="a-note-about-regex"></a><span data-ttu-id="6d334-183">關於 Regex 的筆記</span><span class="sxs-lookup"><span data-stu-id="6d334-183">A note about Regex</span></span>

<span data-ttu-id="6d334-184">如前所述，封鎖式呼叫者的模式相符是使用 Regex 來完成。</span><span class="sxs-lookup"><span data-stu-id="6d334-184">As stated earlier, the pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="6d334-185">有多個工具可供線上使用，以協助驗證 Regex 模式相符。</span><span class="sxs-lookup"><span data-stu-id="6d334-185">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="6d334-186">如果您不熟悉 Regex 模式，建議您花一些時間來熟悉基本概念。</span><span class="sxs-lookup"><span data-stu-id="6d334-186">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="6d334-187">若要確保您取得預期的結果，請在您將封鎖的新數位與您的租使用者加入之前，使用驗證模式相符的工具。</span><span class="sxs-lookup"><span data-stu-id="6d334-187">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="6d334-188">相關主題</span><span class="sxs-lookup"><span data-stu-id="6d334-188">Related topics</span></span>

- [<span data-ttu-id="6d334-189">設定您的電腦以使用 Windows PowerShell 管理商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="6d334-189">Set up your computer to manage Skype for Business Online by using Windows PowerShell</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
