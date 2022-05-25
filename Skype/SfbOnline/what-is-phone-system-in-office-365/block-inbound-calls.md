---
title: 在 商務用 Skype Online 中封鎖輸入通話
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Skype for Business
ms.localizationpriority: medium
ms.custom: Learn how to use PowerShell to manage inbound call blocking in Skype for Business Online.
description: 系統管理員可以瞭解如何在 商務用 Skype Online 中封鎖輸入通話。
ms.openlocfilehash: 40b43f669ededf7ac334c25c79b5af09140c075d
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671649"
---
# <a name="block-inbound-calls"></a>封鎖輸入通話

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

商務用 Skype線上通話方案現在支援封鎖公用交換電話網路 (PSTN) 的撥入通話。 此功能可讓使用者的全域號碼模式清單進行定義，以便在符合專案的清單中核取每一個 PSTN 來電到租使用者的來電者識別碼。 如果符合，則會拒絕來電。

此輸入通話封鎖功能僅適用于來自 PSTN 且只適用于租使用者-全球的輸入通話。 並非每個使用者都可使用。

此功能尚未提供直接路由使用。

>[!NOTE]
> 封鎖的來電者在遭到封鎖時，可能會遇到稍有不同的行為。 此行為是根據封鎖的來電者電信業者如何處理不允許成功完成通話的通知。 範例可能包括電信業者訊息，指出無法在撥號時完成通話，或直接撥出電話。

## <a name="call-blocking-admin-controls-and-information"></a>通話封鎖系統管理員控制項和資訊

管理員封鎖號碼的控制項僅使用 PowerShell 提供。 數位區塊模式定義為正則運算式模式。 運算式的順序不重要，清單中第一個符合的模式會導致通話遭到封鎖。 在 [封鎖的來電者] 清單中新增或移除的新號碼或模式可能需要長達 24 小時，模式才會變成使用中。

## <a name="call-blocking-powershell-commands"></a>呼叫封鎖 PowerShell 命令

數位模式是透過 ```CsInboundBlockedNumberPattern``` 命令 ```New``` 、、 ```Get``` 、 ```Set``` 和 ```Remove``` 來管理。 您可以使用這些 Cmdlet 來管理指定的模式，包括切換啟用指定模式的功能。
- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) 會傳回新增至租使用者清單的所有封鎖數位模式清單，包括名稱、描述、啟用 (True/False) ，以及每個模式。
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) 在租使用者清單中新增封鎖的數位模式。
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) 會從租使用者清單中移除封鎖的數位模式。
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) 修改了租使用者清單中封鎖數位模式的一或多個參數。

檢視和啟用整個通話封鎖功能是透過 ```CsTenantBlockingCallingNumbers``` 命令 ```Get``` 和 ```Set``` 。

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) 會傳回全域封鎖數位清單的參數，包括啟用 (True/False) 。 除了開啟或關閉此功能之外，無法手動修改單一全域租使用者原則。
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) 允許修改全域租使用者封鎖的通話，以在租使用者層級開啟和關閉。

### <a name="examples"></a>範例

#### <a name="block-a-number"></a>封鎖號碼

在此範例中 ```-Enabled``` ，和 ```-Description``` 參數為選用：

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

建立新模式會將模式新增為預設啟用。 描述是提供更多資訊的選擇性欄位。

我們建議您提供有意義的名稱，以輕鬆瞭解新增模式的原因。 若只要封鎖垃圾郵件號碼，請考慮將規則命名為符合的數位模式相同，並在描述中視需要新增其他資訊。

使用 Regex)  (一般運算式來比對模式。
測試和驗證之前，請允許複寫的時間。

#### <a name="allow-a-number"></a>允許數位

在此範例中 ```-Identity``` ，參數為必要：

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```

如果身分識別為未知，請先使用 ```Get-CsInboundBlockedNumberPattern``` Cmdlet 找到正確的模式，並記下身分識別。 然後，執行 ```Remove-CsTenantBlockedNumberPattern``` Cmdlet 並傳遞適當的身分識別值。

測試和驗證之前，請允許複寫的時間。

#### <a name="view-all-number-patterns"></a>檢視所有數位模式

執行此 Cmdlet 會傳回為租使用者輸入的所有封鎖號碼清單：

```powershell
Get-CsInboundBlockedNumberPattern
```

使用內建的 PowerShell 篩選功能，視需要剖析傳回的值。

## <a name="add-number-exceptions"></a>新增數位例外狀況

您可以透過 ```CsTenantBlockNumberExceptionPattern``` 命令、 ```Set``` ```New``` ```Get``` ```Remove``` 和 ，將封鎖的數位模式新增例外狀況。

- [New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) 在租使用者清單中新增數位例外模式。
- [Get-CsTenantBlockedNumberExceptionPattern 會](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) 傳回新增至租使用者清單的所有數位例外模式清單。
- [Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) 將一或多個參數修改為租使用者清單中的數位例外模式。
- [Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) 會從租使用者清單中移除數位例外模式。

### <a name="examples"></a>範例

#### <a name="add-a-number-exception"></a>新增數位例外狀況

在此範例中，會建立新的數位例外模式，並預設會將模式新增為啟用狀態。 ```-Description```和 ```-Enabled``` 參數是選用的。

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"
```

#### <a name="view-all-number-exceptions"></a>檢視所有數位例外狀況

在此範例中，-Identity 參數為選用。 ```-Identity```如果未指定參數，此 Cmdlet 會傳回針對租使用者輸入的所有數位例外模式清單。

```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>修改數位例外狀況

在此範例中，必須使用 -Identity 參數。 ```Set-CsTenantBlockedNumberExceptionPattern```Cmdlet 可讓您修改指定數位模式身分識別的一或多個參數。

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string>
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$"
```

#### <a name="remove-a-number-exception"></a>移除數位例外狀況

在此範例中 ```-Identity``` ，這是必要參數。 此 Cmdlet 會從租使用者清單中移除指定的數位模式。  如果身分識別為未知，請先使用 ```Get-CsInboundBlockedNumberPattern``` Cmdlet 找到正確的模式，並記下身分識別。 然後，執行 ```Remove-CsTenantBlockedNumberExceptionPattern``` Cmdlet 並傳遞適當的身分識別值。 測試和驗證之前，請允許複寫的時間。

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>測試是否封鎖數位

```Test-CsInboundBlockedNumberPattern```使用 Cmdlet 來確認租使用者中是否有封鎖數位。

在此範例中 ```-Phonenumber``` ，必須要有這些和 ```-Tenant``` 參數。 參數 ```-PhoneNumber``` 應為數值字串，而不需要任何額外的字元，例如 + 或 -。 在 TRPS 中 ```-Tenant parameter``` ，這是選用的。 如果在租使用者中封鎖該數位，則產生的 ```isNumberBlocked``` 參數會傳回 True 的值，如果沒有封鎖，則會傳回 False 值。

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|HTTPResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | 真        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|HTTPResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | 假        |         |

## <a name="a-note-about-regex"></a>Regex 的相關附注

如先前所述，封鎖來電者的模式比對是使用 Regex 完成。 線上提供多種工具，以協助驗證 Regex 模式的相符專案。 如果您不熟悉 Regex 模式，建議您花一些時間來熟悉基本概念。 若要確保您獲得預期的結果，請先使用工具驗證模式比對，然後再將新的封鎖數位相符專案新增至租使用者。

## <a name="related-topics"></a>相關主題

- [使用 Windows PowerShell 設定您的電腦以管理 商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
