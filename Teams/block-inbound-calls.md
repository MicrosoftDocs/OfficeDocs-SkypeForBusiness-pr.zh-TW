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
ms.localizationpriority: medium
ms.custom: Learn how to use PowerShell to manage inbound call blocking.
ms.openlocfilehash: 6388c65e5f2c8600c263153b1a943bf485670fe4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58631427"
---
# <a name="block-inbound-calls"></a>封鎖來電

Microsoft 通話方案、直接路由和接線連線都支援封鎖從公用交換電話網絡或 PSTN (來電) 。 此功能可讓系統管理員在租使用者全域層級定義號碼模式清單，以便針對相符專案清單檢查每個傳入 PSTN 來電的本機號碼給租使用者。 如果相符，來電會遭到拒絕。

此來電封鎖功能僅適用于來自 PSTN 的來電，且僅適用于租使用者全域層級。 個別Teams使用者無法操作此清單。 用戶端Teams允許個別使用者封鎖 PSTN 通話。 有關您的使用者如何實行通話封鎖的資訊，請參閱在 Teams 中[管理通話Teams。](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)

>[!NOTE]
> 被封鎖的來電者在遭到封鎖時，可能會遇到稍微不同的行為。 此行為是根據封鎖來電者的電信公司如何處理不允許成功完成通話的通知所決定。 範例可能包括電信公司訊息，指出通話無法以撥號完成，或只是放棄通話。

## <a name="call-blocking-admin-controls-and-information"></a>通話封鎖系統管理員控制項和資訊

封鎖號碼的系統管理員控制項僅使用 PowerShell 提供。 數位區塊模式定義為正則運算式模式。 運算式的順序是不重要的，清單中符合的第一個模式會導致通話遭到封鎖。 在封鎖的來電者清單中新增或移除的新號碼或模式最多可能需要 24 小時，模式才能變成使用中狀態。

## <a name="call-blocking-powershell-commands"></a>封鎖 PowerShell 命令的通話

您可以使用 **New-、Get-、Set-** 和 **Remove-CsInboundBlockedNumberPattern** Cmdlet 來管理數位模式。  您可以使用這些 Cmdlet 來管理一個給定的模式，包括切換啟用給定模式的能力。

- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) 會針對每個清單，會返回新到租使用者清單的所有封鎖數位模式清單，包括名稱、描述、已啟用 (True/False) 和 Pattern。
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) 會新增封鎖的號碼模式至租使用者清單。
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) 會從租使用者清單中移除封鎖的號碼模式。
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) 會修改租使用者清單中封鎖之數位模式的一或多個參數。

檢視及啟用整個通話封鎖功能是由 **Get-** 和 **Set-CsTenantBlockingCallingNumbers** Cmdlet 管理。

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) 會針對全域封鎖的編號清單，會返回輸入區塊編號模式和輸入免稅數位模式參數。 此 Cmdlet 也會將封鎖功能 (True 或 False) 。 除了開啟或關閉功能外，無法手動修改單一全域租使用者策略。
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) 允許修改全域租使用者封鎖的通話，以在租使用者層級開啟和關閉。

### <a name="examples"></a>範例

#### <a name="block-a-number"></a>封鎖數位

在下列範例中，租使用者系統管理員想要封鎖號碼範圍 1 (312) 555-0000 到 1 (312) 555-9999 的所有通話。 數位模式會建立，讓範圍中具有 + 首碼的數位和範圍中不含 + 首碼的數位都相符。 您不需要在電話號碼中包含符號， () ，因為系統會先將符號帶狀，再進行比對。  若要開啟數位模式，Enabled **參數設定** 為 True。 若要停用此特定數位模式，請設定參數為 False。

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockRange1" -Enabled $True -Description "Block Contoso" -Pattern "^\+?1312555\d{4}$"
```

在下一個範例中，租使用者系統管理員想要封鎖號碼 1 (555-1234) 所有來電。 若要開啟數位模式，Enabled **參數設定** 為 True。

```PowerShell
New-CsInboundBlockedNumberPattern -Name "BlockNumber1" -Enabled $True -Description "Block Fabrikam" -Pattern "^\+?14125551234$"
```

建立新模式會將模式預設為啟用。 描述是提供詳細資訊的選擇性欄位。

我們建議您提供有意義的名稱，以便輕鬆瞭解新增模式的原因。 如果只要封鎖垃圾郵件號碼，請考慮將規則命名為符合的數位模式，並根據需要在描述中新增其他資訊。

使用正則運算式和 Regex (模式) 。 詳細資訊，請參閱使用 [Regex](#using-regex)。

在測試和驗證之前，請允許複製時間。 

#### <a name="allow-a-number"></a>允許數位

您可以移除封鎖的號碼模式，允許撥打號碼。 在下列範例中，租使用者系統管理員想要允許 1 (412) 555-1234 再次撥打電話。

```PowerShell
Remove-CsInboundBlockedNumberPattern -Identity "BlockNumber1"
```
 
如果身分識別未知，請使用 **Get-CsInboundBlockedNumberPattern** Cmdlet 來先找出正確的模式，並記下身分識別。 接著，執行 **Remove-CsInboundBlockedNumberPattern** Cmdlet，並傳遞適當的身分識別值。

在測試和驗證之前，請允許複製時間。

#### <a name="view-all-number-patterns"></a>查看所有數位模式

此 Cmdlet 會針對租使用者輸入的所有封鎖號碼清單：

```powershell
Get-CsInboundBlockedNumberPattern
```

使用內建的 PowerShell 篩選功能，以根據需要剖析所返回的值。

## <a name="add-number-exceptions"></a>新增數位例外

您可以使用 **New-、Get-、Set-** 和 **Remove-CsInboundExemptNumberPattern** Cmdlet，為封鎖的編號模式新增例外。  

- [New-CsInboundExemptNumberPattern](/powershell/module/skype/New-CsInboundExemptNumberPattern) 會將數位例外模式新加到租使用者清單中。 
- [Get-CsInboundExemptNumberPattern](/powershell/module/skype/Get-CsInboundExemptNumberPattern) 會返回新加入租使用者清單的所有數位例外模式清單。
- [Set-CsInboundExemptNumberPattern](/powershell/module/skype/Set-CsInboundExemptNumberPattern) 將一或多個參數修改為租使用者清單中的數位例外模式。
- [Remove-CsInboundExemptNumberPattern](/powershell/module/skype/Remove-CsInboundExemptNumberPattern) 會從租使用者清單中移除數位例外模式。

### <a name="examples"></a>範例

#### <a name="add-a-number-exception"></a>新增數位例外

在下列範例中，租使用者系統管理員想要允許電話號碼 1 (312) 555-8882 和 1 (312) 555-8883 撥打電話給租使用者，即使這兩個電話號碼位於上述範例中封鎖的範圍。 若要啟用此功能，會建立一個新的數位例外模式，如下所示：

```PowerShell
New-CsInboundExemptNumberPattern  -Identity "AllowContoso1" -Pattern "^\+?1312555888[2|3]$" -Description "Allow Contoso helpdesk" -Enabled $True
```

若要開啟數位模式，Enabled **參數設定** 為 True。 若要停用此特定數位模式，請設定參數為 False。


#### <a name="view-all-number-exceptions"></a>查看所有數位例外

在此範例中， **身分識別** 參數為選擇性。 如果未指定 **Identity** 參數，此 Cmdlet 會返回為租使用者輸入的所有數位例外模式清單。
 
```powershell
Get-CsInboundExemptNumberPattern -Identity <String>
```
 
```powershell
Get-CsInboundExemptNumberPattern 
```

#### <a name="modify-a-number-exception"></a>修改數位例外

**Set-CsInboundExemptNumberPattern** Cmdlet 可讓您修改指定數位模式身分識別的一或多個參數。 在此範例中， **需要身分** 識別參數。
 
```powershell
Set-CsInboundExemptNumberPattern -Identity <String> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsInboundExemptNumberPattern -Identity "AllowContoso1" -Enabled $False
```

#### <a name="remove-a-number-exception"></a>移除數位例外

**Remove-CsInboundExemptNumberPattern** Cmdlet 會從租使用者清單中移除給定的數位模式。 在此範例中， **需要身分** 識別參數。 

如果身分識別未知，請使用 **Get-CsInboundExemptNumberPattern** Cmdlet 來先找出正確的模式，並記下身分識別。 接著，執行 **Remove-CsInboundExemptNumberPattern** Cmdlet，並傳遞適當的身分識別值。在測試和驗證之前，請允許複製時間。  

```powershell
Remove-CsInboundExemptNumberPattern -Identity <String>
```

```powershell
Remove-CsInboundExemptNumberPattern -Identity "AllowContoso1"
```

## <a name="test-whether-a-number-is-blocked"></a>測試數位是否被封鎖

使用 **Test-CsInboundBlockedNumberPattern** Cmdlet 來驗證是否已封鎖租使用者中的數位。
 
**PhoneNumber** 參數為必填專案，且應為不含任何其他字元的數值字串，例如 +、- 或 () 。 如果租使用者中的數位被封鎖，產生的 **IsNumberBlocked 參數** 會返回 True 的值;如果參數未封鎖，則參數會返回 False。

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

### <a name="examples"></a>範例

在這些範例中，您可以看見電話號碼 1 (312) 555-8884 會因為位於上述封鎖範圍而遭到封鎖，而電話號碼 1 (312) 555-8883 則允許撥打，因為應依據上述所建立之免稅。

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

封鎖來電者的模式比對是使用 Regex 完成。 線上提供多種工具，可協助驗證 Regex 模式相符。 如果您不熟悉 Regex 模式，建議您花一些時間熟悉基本功能。 若要確定您獲得預期的結果，請使用驗證模式比對的工具，再新增封鎖的號碼比對至租使用者。