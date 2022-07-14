---
title: 在 Microsoft Teams 中封鎖輸入通話
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
ms.custom: ''
description: 瞭解如何使用 PowerShell 管理輸入通話封鎖。
ms.openlocfilehash: 217a4fe6770d916e9013acf7f90ebf6a5556b837
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789598"
---
# <a name="block-inbound-calls"></a>封鎖輸入通話

Microsoft 通話方案、直接路由和運算子連線都支援封鎖來自公用交換電話網路 (PSTN) 的撥入通話。 此功能可讓系統管理員在租使用者全域層級定義號碼模式清單，以便針對符合的清單檢查每一個 PSTN 來電給租使用者的來電者識別碼。 如果符合，則會拒絕來電。

此輸入通話封鎖功能僅適用于來自 PSTN 且只適用于租使用者全域層級的輸入通話。 個別 Teams 使用者無法操作此清單。 Teams 用戶端允許個別使用者封鎖 PSTN 通話。 如需使用者如何實作通話封鎖的相關資訊，請參閱 [管理 Teams 中的通話設定](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)。

> [!NOTE]
> 封鎖的來電者在遭到封鎖時，可能會遇到稍微不同的行為。 此行為是根據封鎖的來電者電信業者如何處理不允許成功完成通話的通知。 範例可能包括電信業者訊息，指出無法在撥號時完成通話，或直接撥出電話。

## <a name="call-blocking-admin-controls-and-information"></a>通話封鎖系統管理員控制項和資訊

管理員封鎖號碼的控制項僅使用 PowerShell 提供。 數位區塊模式定義為正則運算式模式。 運算式的順序不重要，清單中第一個符合的模式會導致通話遭到封鎖。 在 [封鎖的來電者] 清單中新增或移除的新號碼或模式可能需要長達 24 小時，模式才會變成使用中。

## <a name="call-blocking-powershell-commands"></a>呼叫封鎖 PowerShell 命令

您可以使用 **New-**、 **Get-**、 **Set-** 和 **Remove-CsInboundBlockedNumberPattern** Cmdlet 來管理數位模式。 您可以使用這些 Cmdlet 來管理指定的模式，包括切換啟用指定模式的功能。

- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) 會傳回新增至租使用者清單的所有封鎖數位模式清單，包括名稱、描述、啟用 (True/False) ，以及每個模式。
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) 在租使用者清單中新增封鎖的數位模式。
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) 會從租使用者清單中移除封鎖的數位模式。
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) 修改了租使用者清單中封鎖數位模式的一或多個參數。

檢視和啟用整個通話封鎖功能是透過 **Get-and** **Set-CsTenantBlockingCallingNumbers** Cmdlet 來管理。

- [Get-CsTenantBlockedCallingNumbers 會](/powershell/module/skype/get-cstenantblockedcallingnumbers) 傳回輸入區塊數位模式，以及全域封鎖數位清單的輸入免除數位模式參數。 此 Cmdlet 也會傳回封鎖是否已啟用 (True 或 False) 。 除了開啟或關閉此功能之外，無法手動修改單一全域租使用者原則。
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) 允許修改全域租使用者封鎖的通話，以在租使用者層級開啟和關閉。

### <a name="examples"></a>範例

#### <a name="block-a-number"></a>封鎖號碼

在下列範例中，租使用者系統管理員想要封鎖來自號碼範圍 1 (312 的所有來電) 555-0000 到 1 (312) 555-9999。 會建立數位模式，讓範圍中有 + 首碼的數位和範圍中沒有 + 首碼的數位相符。 您不需要在電話號碼中包含符號 – 和 () ，因為系統會在相符之前先去除這些符號。  若要開啟數位模式， **Enabled** 參數設定為 True。 若要停用此特定數位模式，請將參數設定為 False。

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

在下一個範例中，租使用者系統管理員想要封鎖來自號碼 1 (412 的所有來電) 555-1234。 若要開啟數位模式， **Enabled** 參數設定為 True。

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

建立新模式會將模式新增為預設啟用。 描述是提供更多資訊的選擇性欄位。

我們建議您提供有意義的名稱，以輕鬆瞭解新增模式的原因。 若只要封鎖垃圾郵件號碼，請考慮將規則命名為符合的數位模式相同，並在描述中視需要新增其他資訊。

使用 Regex)  (一般運算式來比對模式。 如需詳細資訊，請參閱 [使用 Regex](#using-regex)。

測試和驗證之前，請允許複寫的時間。

#### <a name="allow-a-number"></a>允許數位

您可以移除封鎖的號碼模式，允許撥打號碼。 在下列範例中，租使用者系統管理員想要允許 1 (412) 555-1234 再次撥打電話。

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```

如果身分識別為未知，請使用 **Get-CsInboundBlockedNumberPattern** Cmdlet，先找出正確的模式並記下身分識別。 然後，執行 **Remove-CsInboundBlockedNumberPattern** Cmdlet 並傳遞適當的身分識別值。

測試和驗證之前，請允許複寫的時間。

#### <a name="view-all-number-patterns"></a>檢視所有數位模式

執行此 Cmdlet 會傳回為租使用者輸入的所有封鎖號碼清單：

```powershell
Get-CsInboundBlockedNumberPattern
```

使用內建的 PowerShell 篩選功能，視需要剖析傳回的值。

## <a name="add-number-exceptions"></a>新增數位例外狀況

您可以使用 **New-**、 **Get-**、 **Set-** 和 **Remove-CsInboundExemptNumberPattern** Cmdlet 來新增封鎖的數位模式例外狀況。

- [New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) 在租使用者清單中新增數位例外模式。
- [Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) 會傳回新增至租使用者清單的所有數位例外模式清單。
- [Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) 會將一或多個參數修改為租使用者清單中的數位例外模式。
- [Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) 會從租使用者清單中移除數位例外模式。

### <a name="examples"></a>範例

#### <a name="add-a-number-exception"></a>新增數位例外狀況

在下列範例中，租使用者系統管理員想要允許電話號碼 1 (312) 555-8882 和 1 (312) 555-8883 撥打給租使用者，即使這兩個電話號碼位於上述範例中封鎖的範圍中。 若要啟用此功能，會建立新的數位例外模式，如下所示：

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

若要開啟數位模式， **Enabled** 參數設定為 True。 若要停用此特定數位模式，請將參數設定為 False。

#### <a name="view-all-number-exceptions"></a>檢視所有數位例外狀況

在此範例中， **[身分識別]** 參數為選用。 如果未指定 **身分識別** 參數，此 Cmdlet 會傳回針對租使用者輸入的所有數位例外模式清單。

```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Get-CsInboundExemptNumberPattern
```

#### <a name="modify-a-number-exception"></a>修改數位例外狀況

**Set-CsInboundExemptNumberPattern** Cmdlet 可讓您修改指定數位模式身分識別的一或多個參數。 在此範例中，需要 **身分識別** 參數。

```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string>
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a>移除數位例外狀況

**Remove-CsInboundExemptNumberPattern** Cmdlet 會從租使用者清單中移除指定的數位模式。 在此範例中，需要 **身分識別** 參數。

如果身分識別為未知，請使用 **Get-CsInboundExemptNumberPattern** Cmdlet，先找出正確的模式並記下身分識別。 然後，執行 **Remove-CsInboundExemptNumberPattern** Cmdlet 並傳遞適當的身分識別值。 測試和驗證之前，請允許複寫的時間。

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a>測試是否封鎖數位

使用 **Test-CsInboundBlockedNumberPattern** Cmdlet 來確認租使用者中是否有封鎖數位。

**PhoneNumber** 參數是必要的，且應為數字字串，且不需要任何其他字元，例如 +、- 或 () 。 結果 **IsNumberBlocked 參數會在** 租使用者中封鎖該數位時傳回 True 的值;如果沒有封鎖，參數會傳回 False。

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a>範例

在這些範例中，您可以看到電話號碼 1 (312) 555-8884 因為位於上述封鎖範圍而遭封鎖，而電話號碼 1 (312) 555-8883 則可撥打，因為它應以上述建立的免稅為基礎。

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

## <a name="using-regex"></a>使用 Regex

封鎖來電者的模式比對是使用 Regex 完成。 線上提供多種工具，以協助驗證 Regex 模式的相符專案。 如果您不熟悉 Regex 模式，建議您花一些時間來熟悉基本概念。 若要確保您獲得預期的結果，請先使用工具驗證模式比對，然後再將新的封鎖數位相符專案新增至租使用者。
