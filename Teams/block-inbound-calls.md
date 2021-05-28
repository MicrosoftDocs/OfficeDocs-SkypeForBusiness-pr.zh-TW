---
title: 封鎖通話中的Microsoft Teams
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
ms.openlocfilehash: e584e9f0c16ef77424121c37ce87c6d63afb4b92
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689761"
---
# <a name="block-inbound-calls"></a><span data-ttu-id="7fff0-102">封鎖來電</span><span class="sxs-lookup"><span data-stu-id="7fff0-102">Block inbound calls</span></span>

<span data-ttu-id="7fff0-103">Microsoft 通話方案、直接路由和接線連線都支援封鎖從公用交換電話網絡 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="7fff0-103">Microsoft Calling Plans, Direct Routing, and Operator Connect all support blocking inbound calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="7fff0-104">此功能可讓系統管理員在租使用者全域層級定義號碼模式清單，以便針對相符專案清單檢查每個傳入 PSTN 呼叫的來電者識別碼。</span><span class="sxs-lookup"><span data-stu-id="7fff0-104">This feature allows an administrator to define a  list of number patterns at the tenant global level so that the caller ID of every incoming PSTN call to the tenant can be checked against the list for a match.</span></span> <span data-ttu-id="7fff0-105">如果相符，來電會遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="7fff0-105">If a match is made, an incoming call is rejected.</span></span>

<span data-ttu-id="7fff0-106">此來電封鎖功能僅適用于來自 PSTN 的來電，且僅適用于租使用者全域層級。</span><span class="sxs-lookup"><span data-stu-id="7fff0-106">This inbound call blocking feature only works on inbound calls that originate from the PSTN and only works on a tenant global level.</span></span> <span data-ttu-id="7fff0-107">個別Teams使用者無法操作此清單。</span><span class="sxs-lookup"><span data-stu-id="7fff0-107">Individual Teams users can’t manipulate this list.</span></span> <span data-ttu-id="7fff0-108">用戶端Teams允許個別使用者封鎖 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="7fff0-108">The Teams client does allow individual users to block PSTN calls.</span></span> <span data-ttu-id="7fff0-109">有關您的使用者如何實行通話封鎖的資訊，請參閱在 Teams 中[管理通話Teams。](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="7fff0-109">For information about how your end users can implement call blocking, see [Manage call settings in Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span>

>[!NOTE]
> <span data-ttu-id="7fff0-110">封鎖的來電者在遭到封鎖時，可能會遇到稍有不同的行為。</span><span class="sxs-lookup"><span data-stu-id="7fff0-110">Blocked callers may experience slightly different behaviors when they've been blocked.</span></span> <span data-ttu-id="7fff0-111">此行為是根據封鎖來電者的電信公司如何處理不允許成功完成通話的通知所決定。</span><span class="sxs-lookup"><span data-stu-id="7fff0-111">The behavior is based on how the blocked caller’s carrier handles the notification that the call isn't allowed to be successfully completed.</span></span> <span data-ttu-id="7fff0-112">範例可能包括電信公司訊息，指出通話無法以撥號完成，或只是放棄通話。</span><span class="sxs-lookup"><span data-stu-id="7fff0-112">Examples may include a carrier message stating the call can't be completed as dialed, or simply dropping the call.</span></span>

## <a name="call-blocking-admin-controls-and-information"></a><span data-ttu-id="7fff0-113">通話封鎖系統管理員控制項和資訊</span><span class="sxs-lookup"><span data-stu-id="7fff0-113">Call blocking admin controls and information</span></span>

<span data-ttu-id="7fff0-114">封鎖號碼的系統管理員控制項僅使用 PowerShell 提供。</span><span class="sxs-lookup"><span data-stu-id="7fff0-114">Admin controls for blocking numbers are provided using PowerShell only.</span></span> <span data-ttu-id="7fff0-115">數位區塊模式定義為正則運算式模式。</span><span class="sxs-lookup"><span data-stu-id="7fff0-115">Number block patterns are defined as regular expression patterns.</span></span> <span data-ttu-id="7fff0-116">運算式的順序是不重要的，清單中符合的第一個模式會導致通話遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="7fff0-116">The order of the expressions is unimportant – the first pattern matched in the list results in the call being blocked.</span></span> <span data-ttu-id="7fff0-117">在封鎖的來電者清單中新增或移除的新號碼或模式最多可能需要 24 小時，模式才能變成使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="7fff0-117">A new number or pattern that's added or removed in the blocked callers list may take up to 24 hours for the pattern to become active.</span></span>

## <a name="call-blocking-powershell-commands"></a><span data-ttu-id="7fff0-118">封鎖 PowerShell 命令的通話</span><span class="sxs-lookup"><span data-stu-id="7fff0-118">Call blocking PowerShell commands</span></span>

<span data-ttu-id="7fff0-119">您可以使用 **New-、Get-、Set-** 和 **Remove-CsInboundBlockedNumberPattern** Cmdlet 來管理數位模式。 </span><span class="sxs-lookup"><span data-stu-id="7fff0-119">You manage number patterns by using the **New-**, **Get-**, **Set-**, and **Remove-CsInboundBlockedNumberPattern** cmdlets.</span></span> <span data-ttu-id="7fff0-120">您可以使用這些 Cmdlet 來管理一個給定的模式，包括切換啟用給定模式的能力。</span><span class="sxs-lookup"><span data-stu-id="7fff0-120">You can manage a given pattern by using these cmdlets, including the ability to toggle the activation of a given pattern.</span></span>

- <span data-ttu-id="7fff0-121">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) 會針對每個清單，會返回新到租使用者清單的所有封鎖數位模式清單，包括名稱、描述、已啟用 (True/False) 和 Pattern。</span><span class="sxs-lookup"><span data-stu-id="7fff0-121">[Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) returns a list of all blocked number patterns added to the tenant list including Name, Description, Enabled (True/False), and Pattern for each.</span></span>
- <span data-ttu-id="7fff0-122">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) 會新增封鎖的號碼模式至租使用者清單。</span><span class="sxs-lookup"><span data-stu-id="7fff0-122">[New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) adds a blocked number pattern to the tenant list.</span></span>
- <span data-ttu-id="7fff0-123">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) 會從租使用者清單中移除封鎖的號碼模式。</span><span class="sxs-lookup"><span data-stu-id="7fff0-123">[Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) removes a blocked number pattern from the tenant list.</span></span>
- <span data-ttu-id="7fff0-124">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) 會修改租使用者清單中封鎖之數位模式的一或多個參數。</span><span class="sxs-lookup"><span data-stu-id="7fff0-124">[Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) modifies one or more parameters of a blocked number pattern in the tenant list.</span></span>

<span data-ttu-id="7fff0-125">檢視及啟用整個通話封鎖功能是由 **Get-** 和 **Set-CsTenantBlockingCallingNumbers** Cmdlet 管理。</span><span class="sxs-lookup"><span data-stu-id="7fff0-125">Viewing and activating the entire call blocking feature is managed through the **Get-** and **Set-CsTenantBlockingCallingNumbers** cmdlets.</span></span>

- <span data-ttu-id="7fff0-126">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) 會針對全域封鎖的編號清單，會返回輸入區塊編號模式和輸入免稅數位模式參數。</span><span class="sxs-lookup"><span data-stu-id="7fff0-126">[Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) returns the inbound block number patterns and the inbound exempt number patterns parameters for the global blocked number list.</span></span> <span data-ttu-id="7fff0-127">此 Cmdlet 也會將封鎖功能 (True 或 False) 。</span><span class="sxs-lookup"><span data-stu-id="7fff0-127">This cmdlet also returns whether blocking has been Enabled (True or False).</span></span> <span data-ttu-id="7fff0-128">除了開啟或關閉功能外，無法手動修改單一全域租使用者策略。</span><span class="sxs-lookup"><span data-stu-id="7fff0-128">There's a single global tenant policy that can't be modified manually other than to turn the feature on or off.</span></span>
- <span data-ttu-id="7fff0-129">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) 允許修改全域租使用者封鎖的通話，以在租使用者層級開啟和關閉。</span><span class="sxs-lookup"><span data-stu-id="7fff0-129">[Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) allows modifying the global tenant blocked calls to be turned on and off at the tenant level.</span></span>

### <a name="examples"></a><span data-ttu-id="7fff0-130">範例</span><span class="sxs-lookup"><span data-stu-id="7fff0-130">Examples</span></span>

#### <a name="block-a-number"></a><span data-ttu-id="7fff0-131">封鎖數位</span><span class="sxs-lookup"><span data-stu-id="7fff0-131">Block a number</span></span>

<span data-ttu-id="7fff0-132">在下列範例中，租使用者系統管理員想要封鎖號碼範圍 1 (312) 555-0000 到 1 (312) 555-9999 的所有來電。</span><span class="sxs-lookup"><span data-stu-id="7fff0-132">In the following example, the tenant administrator wants to block all calls coming from the number range 1 (312) 555-0000 to 1 (312) 555-9999.</span></span> <span data-ttu-id="7fff0-133">數位模式會建立，讓範圍中具有 + 首碼的數位和範圍中不含 + 首碼的數位都相符。</span><span class="sxs-lookup"><span data-stu-id="7fff0-133">The number pattern is created so that both numbers in range with + prefixed and numbers in the range without + prefixed are matched.</span></span> <span data-ttu-id="7fff0-134">您不需要在電話號碼中包含符號， () ，因為系統在比對之前會先去除這些符號。</span><span class="sxs-lookup"><span data-stu-id="7fff0-134">You don’t need to include the symbols – and () in the phone numbers because the system strips these symbols before matching.</span></span>  <span data-ttu-id="7fff0-135">若要開啟數位模式，Enabled **參數設定** 為 True。</span><span class="sxs-lookup"><span data-stu-id="7fff0-135">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span> <span data-ttu-id="7fff0-136">若要停用此特定數位模式，請設定參數為 False。</span><span class="sxs-lookup"><span data-stu-id="7fff0-136">To disable this specific number pattern, set the parameter to False.</span></span>

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

<span data-ttu-id="7fff0-137">在下一個範例中，租使用者系統管理員想要封鎖來自 412 (555-1234) 號碼 1 的所有通話。</span><span class="sxs-lookup"><span data-stu-id="7fff0-137">In the next example, the tenant administrator wants to block all calls coming from the number 1 (412) 555-1234.</span></span> <span data-ttu-id="7fff0-138">若要開啟數位模式，Enabled **參數設定** 為 True。</span><span class="sxs-lookup"><span data-stu-id="7fff0-138">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span>

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

<span data-ttu-id="7fff0-139">建立新模式會將模式預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="7fff0-139">Creating a new pattern adds the pattern as enabled by default.</span></span> <span data-ttu-id="7fff0-140">描述是提供詳細資訊的選擇性欄位。</span><span class="sxs-lookup"><span data-stu-id="7fff0-140">The description is an optional field to provide more information.</span></span>

<span data-ttu-id="7fff0-141">我們建議您提供有意義的名稱，以便輕鬆瞭解新增模式的原因。</span><span class="sxs-lookup"><span data-stu-id="7fff0-141">We recommend that you provide a meaningful name to easily understand why the pattern was added.</span></span> <span data-ttu-id="7fff0-142">如果只要封鎖垃圾郵件號碼，請考慮將規則命名為符合的數位模式，並根據需要在描述中新增其他資訊。</span><span class="sxs-lookup"><span data-stu-id="7fff0-142">In the case of simply blocking spam numbers, consider naming the rule the same as the number pattern that's being matched and add additional information in the description as required.</span></span>

<span data-ttu-id="7fff0-143">使用正則運算式和 Regex (模式) 。</span><span class="sxs-lookup"><span data-stu-id="7fff0-143">Patterns are matched using Regular Expressions (Regex).</span></span> <span data-ttu-id="7fff0-144">詳細資訊，請參閱使用 [Regex](#using-regex)。</span><span class="sxs-lookup"><span data-stu-id="7fff0-144">For more information, see [Using Regex](#using-regex).</span></span>

<span data-ttu-id="7fff0-145">在測試和驗證之前，請允許複製時間。</span><span class="sxs-lookup"><span data-stu-id="7fff0-145">Allow time for replication before you test and validate.</span></span> 

#### <a name="allow-a-number"></a><span data-ttu-id="7fff0-146">允許數位</span><span class="sxs-lookup"><span data-stu-id="7fff0-146">Allow a number</span></span>

<span data-ttu-id="7fff0-147">您可以移除封鎖的號碼模式，允許撥打號碼。</span><span class="sxs-lookup"><span data-stu-id="7fff0-147">You can allow a number to call by removing the blocked number pattern.</span></span> <span data-ttu-id="7fff0-148">在下列範例中，租使用者系統管理員想要允許 1 (412) 555-1234 再次撥打電話。</span><span class="sxs-lookup"><span data-stu-id="7fff0-148">In the following example, the tenant administrator wants to allow 1 (412) 555-1234 to make calls again.</span></span>

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```
 
<span data-ttu-id="7fff0-149">如果身分識別未知，請使用 **Get-CsInboundBlockedNumberPattern** Cmdlet 來先找出正確的模式，並記下身分識別。</span><span class="sxs-lookup"><span data-stu-id="7fff0-149">If the identity isn't known, use the **Get-CsInboundBlockedNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="7fff0-150">接著，執行 **Remove-CsInboundBlockedNumberPattern** Cmdlet，並傳遞適當的身分識別值。</span><span class="sxs-lookup"><span data-stu-id="7fff0-150">Then, run the **Remove-CsInboundBlockedNumberPattern** cmdlet and pass the appropriate identity value.</span></span>

<span data-ttu-id="7fff0-151">在測試和驗證之前，請允許複製時間。</span><span class="sxs-lookup"><span data-stu-id="7fff0-151">Allow time for replication before you test and validate.</span></span>

#### <a name="view-all-number-patterns"></a><span data-ttu-id="7fff0-152">查看所有數位模式</span><span class="sxs-lookup"><span data-stu-id="7fff0-152">View all number patterns</span></span>

<span data-ttu-id="7fff0-153">此 Cmdlet 會針對租使用者輸入的所有封鎖號碼清單：</span><span class="sxs-lookup"><span data-stu-id="7fff0-153">Running this cmdlet returns a list of all blocked numbers that are entered for a tenant:</span></span>

```powershell
Get-CsInboundBlockedNumberPattern
```

<span data-ttu-id="7fff0-154">使用內建的 PowerShell 篩選功能，以根據需要剖析所返回的值。</span><span class="sxs-lookup"><span data-stu-id="7fff0-154">Use built-in PowerShell filtering abilities to parse the returned values as required.</span></span>

## <a name="add-number-exceptions"></a><span data-ttu-id="7fff0-155">新增數位例外</span><span class="sxs-lookup"><span data-stu-id="7fff0-155">Add number exceptions</span></span>

<span data-ttu-id="7fff0-156">您可以使用 **New-、Get-、Set-** 和 **Remove-CsInboundExemptNumberPattern** Cmdlet，為封鎖的編號模式新增例外。  </span><span class="sxs-lookup"><span data-stu-id="7fff0-156">You can add exceptions to blocked number patterns by using the **New-**, **Get-**, **Set-**, and **Remove-CsInboundExemptNumberPattern** cmdlets.</span></span>

- <span data-ttu-id="7fff0-157">[New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) 會將數位例外模式新加到租使用者清單中。</span><span class="sxs-lookup"><span data-stu-id="7fff0-157">[New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) adds a number exception pattern to the tenant list.</span></span> 
- <span data-ttu-id="7fff0-158">[Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) 會返回新加入租使用者清單的所有數位例外模式清單。</span><span class="sxs-lookup"><span data-stu-id="7fff0-158">[Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) returns a list of all number exception patterns added to the tenant list.</span></span>
- <span data-ttu-id="7fff0-159">[Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) 將一或多個參數修改為租使用者清單中的數位例外模式。</span><span class="sxs-lookup"><span data-stu-id="7fff0-159">[Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) modifies one or more parameters to a number exception pattern in the tenant list.</span></span>
- <span data-ttu-id="7fff0-160">[Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) 會從租使用者清單中移除數位例外模式。</span><span class="sxs-lookup"><span data-stu-id="7fff0-160">[Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) removes a number exception pattern from the tenant list.</span></span>

### <a name="examples"></a><span data-ttu-id="7fff0-161">範例</span><span class="sxs-lookup"><span data-stu-id="7fff0-161">Examples</span></span>

#### <a name="add-a-number-exception"></a><span data-ttu-id="7fff0-162">新增數位例外</span><span class="sxs-lookup"><span data-stu-id="7fff0-162">Add a number exception</span></span>

<span data-ttu-id="7fff0-163">在下列範例中，租使用者系統管理員想要允許電話號碼 1 (312) 555-8882 和 1 (312) 555-8883 撥打電話給租使用者，即使這兩個電話號碼位於上述範例中封鎖的範圍。</span><span class="sxs-lookup"><span data-stu-id="7fff0-163">In the following example, the tenant administrator wants to allow the phone numbers 1 (312) 555-8882 and 1 (312) 555-8883 to make calls to the tenant, even if these two phone numbers are in the range that has been blocked in the example above.</span></span> <span data-ttu-id="7fff0-164">若要啟用此功能，會建立一個新的數位例外模式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7fff0-164">To enable this, a new number exception pattern is created as follows:</span></span>

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

<span data-ttu-id="7fff0-165">若要開啟數位模式，Enabled **參數設定** 為 True。</span><span class="sxs-lookup"><span data-stu-id="7fff0-165">To turn on the number pattern, the **Enabled** parameter is set to True.</span></span> <span data-ttu-id="7fff0-166">若要停用此特定數位模式，請設定參數為 False。</span><span class="sxs-lookup"><span data-stu-id="7fff0-166">To disable this specific number pattern, set the parameter to False.</span></span>


#### <a name="view-all-number-exceptions"></a><span data-ttu-id="7fff0-167">查看所有數位例外</span><span class="sxs-lookup"><span data-stu-id="7fff0-167">View all number exceptions</span></span>

<span data-ttu-id="7fff0-168">在此範例中， **身分識別** 參數為選擇性。</span><span class="sxs-lookup"><span data-stu-id="7fff0-168">In this example, the **Identity** parameter is optional.</span></span> <span data-ttu-id="7fff0-169">如果未指定 **Identity** 參數，此 Cmdlet 會返回為租使用者輸入的所有數位例外模式清單。</span><span class="sxs-lookup"><span data-stu-id="7fff0-169">If the **Identity** parameter isn't specified, this cmdlet returns a list of all number exception patterns entered for a tenant.</span></span>
 
```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```
 
```powershell
Get-CsInboundExemptNumberPattern 
```

#### <a name="modify-a-number-exception"></a><span data-ttu-id="7fff0-170">修改數位例外</span><span class="sxs-lookup"><span data-stu-id="7fff0-170">Modify a number exception</span></span>

<span data-ttu-id="7fff0-171">**Set-CsInboundExemptNumberPattern** Cmdlet 可讓您修改指定數位模式身分識別的一或多個參數。</span><span class="sxs-lookup"><span data-stu-id="7fff0-171">The **Set-CsInboundExemptNumberPattern** cmdlet lets you modify one or more parameters for a given number pattern identity.</span></span> <span data-ttu-id="7fff0-172">在此範例中， **需要身分** 識別參數。</span><span class="sxs-lookup"><span data-stu-id="7fff0-172">In this example, the **Identity** parameter is required.</span></span>
 
```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a><span data-ttu-id="7fff0-173">移除數位例外</span><span class="sxs-lookup"><span data-stu-id="7fff0-173">Remove a number exception</span></span>

<span data-ttu-id="7fff0-174">**Remove-CsInboundExemptNumberPattern** Cmdlet 會從租使用者清單中移除給定的數位模式。</span><span class="sxs-lookup"><span data-stu-id="7fff0-174">The **Remove-CsInboundExemptNumberPattern** cmdlet will remove the given number pattern from the tenant list.</span></span> <span data-ttu-id="7fff0-175">在此範例中， **需要身分** 識別參數。</span><span class="sxs-lookup"><span data-stu-id="7fff0-175">In this example, the **Identity** parameter is required.</span></span> 

<span data-ttu-id="7fff0-176">如果身分識別不明，請使用 **Get-CsInboundExemptNumberPattern** Cmdlet 來先找出正確的模式，並記下身分識別。</span><span class="sxs-lookup"><span data-stu-id="7fff0-176">If the identity isn't known, use the **Get-CsInboundExemptNumberPattern** cmdlet to first locate the proper pattern and note the identity.</span></span> <span data-ttu-id="7fff0-177">接著，執行 **Remove-CsInboundExemptNumberPattern** Cmdlet，並傳遞適當的身分識別值。</span><span class="sxs-lookup"><span data-stu-id="7fff0-177">Then, run the **Remove-CsInboundExemptNumberPattern** cmdlet and pass the appropriate identity value.</span></span><span data-ttu-id="7fff0-178">在測試和驗證之前，請允許複製時間。</span><span class="sxs-lookup"><span data-stu-id="7fff0-178"> Allow time for replication before you test and validate.</span></span>  

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a><span data-ttu-id="7fff0-179">測試數位是否被封鎖</span><span class="sxs-lookup"><span data-stu-id="7fff0-179">Test whether a number is blocked</span></span>

<span data-ttu-id="7fff0-180">使用 **Test-CsInboundBlockedNumberPattern** Cmdlet 來驗證是否已封鎖租使用者中的數位。</span><span class="sxs-lookup"><span data-stu-id="7fff0-180">Use the **Test-CsInboundBlockedNumberPattern** cmdlet to verify whether a number is blocked in the tenant.</span></span>
 
<span data-ttu-id="7fff0-181">**PhoneNumber 參數** 為必填專案，且應為不含任何其他字元的數值字串，例如 +、- 或 () 。</span><span class="sxs-lookup"><span data-stu-id="7fff0-181">The **PhoneNumber** parameter is required, and should be a numeric string without any additional characters, such as +, - or ().</span></span> <span data-ttu-id="7fff0-182">如果租使用者中的數位被封鎖，產生的 **IsNumberBlocked 參數** 會返回 True 的值;如果參數未封鎖，則參數會返回 False。</span><span class="sxs-lookup"><span data-stu-id="7fff0-182">The resulting **IsNumberBlocked** parameter returns a value of True if the number is blocked in the tenant; the parameter returns False if it's not blocked.</span></span>

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a><span data-ttu-id="7fff0-183">範例</span><span class="sxs-lookup"><span data-stu-id="7fff0-183">Examples</span></span>

<span data-ttu-id="7fff0-184">在這些範例中，您可以看見電話號碼 1 (312) 555-8884 會因為位於上述封鎖範圍而遭到封鎖，而電話號碼 1 (312) 555-8883 則允許撥打，因為應依據上述所建立之免稅。</span><span class="sxs-lookup"><span data-stu-id="7fff0-184">In these examples you can see that the phone number 1 (312) 555-8884 is blocked as it should be due to it being in the blocked range above, while the phone number 1 (312) 555-8883 is allowed to call as it should be based on the exemption created above.</span></span>

```PowerShell
Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558884

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : True
errorMessage    :

Test-CsInboundBlockedNumberPattern -PhoneNumber 13125558883

RunspaceId      : 09537e45-6f0c-4001-8b85-a79002707b0c
httpStatusCode  : NoContent
IsNumberBlocked : False
errorMessage    :
```

## <a name="using-regex"></a><span data-ttu-id="7fff0-185">使用 Regex</span><span class="sxs-lookup"><span data-stu-id="7fff0-185">Using Regex</span></span>

<span data-ttu-id="7fff0-186">封鎖來電者的模式比對是使用 Regex 完成。</span><span class="sxs-lookup"><span data-stu-id="7fff0-186">The pattern matching for blocking callers is done by using Regex.</span></span> <span data-ttu-id="7fff0-187">線上提供多種工具，可協助驗證 Regex 模式相符。</span><span class="sxs-lookup"><span data-stu-id="7fff0-187">Multiple tools are available online to help validate a Regex pattern match.</span></span> <span data-ttu-id="7fff0-188">如果您不熟悉 Regex 模式，建議您花一些時間熟悉基本功能。</span><span class="sxs-lookup"><span data-stu-id="7fff0-188">If you aren't familiar with Regex patterns, we recommend that you take some time to familiarize yourself with the basics.</span></span> <span data-ttu-id="7fff0-189">若要確定您獲得預期的結果，請使用驗證模式比對的工具，再新增封鎖的號碼比對至租使用者。</span><span class="sxs-lookup"><span data-stu-id="7fff0-189">To make sure you get expected results, use a tool for validating pattern matches before you add new blocked number matches to your tenant.</span></span>