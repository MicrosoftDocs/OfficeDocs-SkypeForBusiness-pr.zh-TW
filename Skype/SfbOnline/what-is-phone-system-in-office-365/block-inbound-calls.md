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
# <a name="block-inbound-calls"></a>封鎖來電

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

商務用 Skype線上通話方案現在支援封鎖從公用交換電話網路或 PSTN (來電) 。 此功能可定義租使用者全域號碼模式清單，以便針對相符專案清單檢查每個傳入 PSTN 呼叫的來電者識別碼。 如果相符，來電會遭到拒絕。

此來電封鎖功能僅適用于來自 PSTN 的來電，且僅適用于租使用者全域。 它無法以每個使用者為基礎使用。  

這項功能尚未用於直接路由。

>[!NOTE]
> 封鎖的來電者在遭到封鎖時，可能會遇到稍有不同的行為。 此行為是根據封鎖來電者的電信公司如何處理不允許成功完成通話的通知所決定。 範例可能包括電信公司訊息，指出通話無法以撥號完成，或只是放棄通話。

## <a name="call-blocking-admin-controls-and-information"></a>通話封鎖系統管理控制項和資訊

封鎖號碼的系統管理員控制項僅使用 PowerShell 提供。 數位區塊模式定義為正則運算式模式。 運算式的順序是不重要的，清單中符合的第一個模式會導致通話遭到封鎖。 在封鎖的來電者清單中新增或移除的新號碼或模式最多可能需要 24 小時，模式才能變成使用中狀態。

## <a name="call-blocking-powershell-commands"></a>封鎖 PowerShell 命令的通話

數位模式會透過 ```CsInboundBlockedNumberPattern``` 命令 ```New``` 、和 ```Get``` 進行管理 ```Set``` ```Remove``` 。 您可以使用這些 Cmdlet 來管理一個給定的模式，包括切換啟用給定模式的能力。
- [Get-CsInboundBlockedNumberPattern](/powershell/module/skype/get-csinboundblockednumberpattern) 會針對每個清單，會返回新到租使用者清單的所有封鎖數位模式清單，包括名稱、描述、已啟用 (True/False) 和 Pattern。
- [New-CsInboundBlockedNumberPattern](/powershell/module/skype/new-csinboundblockednumberpattern) 會新增封鎖的號碼模式至租使用者清單。
- [Remove-CsInboundBlockedNumberPattern](/powershell/module/skype/remove-csinboundblockednumberpattern) 會從租使用者清單中移除封鎖的號碼模式。
- [Set-CsInboundBlockedNumberPattern](/powershell/module/skype/set-csinboundblockednumberpattern) 會修改租使用者清單中封鎖之數位模式的一或多個參數。

檢視及啟用整個通話封鎖功能是由命令 ```CsTenantBlockingCallingNumbers``` 和 ```Get``` 管理 ```Set``` 。

- [Get-CsTenantBlockedCallingNumbers](/powershell/module/skype/get-cstenantblockedcallingnumbers) 會返回全域封鎖數位清單的參數，包括啟用的 (True/False) 。 除了開啟或關閉功能外，無法手動修改單一全域租使用者策略。
- [Set-CsTenantBlockedCallingNumbers](/powershell/module/skype/set-cstenantblockedcallingnumbers) 可讓您修改全域租使用者封鎖的通話，以在租使用者層級開啟和關閉。

### <a name="examples"></a>範例

#### <a name="block-a-number"></a>封鎖數位

在此範例中，and ```-Enabled``` ```-Description``` 參數為選擇性：

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

建立新模式會將模式預設為啟用。 描述是提供詳細資訊的選擇性欄位。

我們建議您提供有意義的名稱，以便輕鬆瞭解新增模式的原因。 如果只要封鎖垃圾郵件號碼，請考慮將規則命名為符合的數位模式，並根據需要在描述中新增其他資訊。

使用正則運算式和 Regex (模式) 。 在測試和驗證之前，請允許複製時間。

#### <a name="allow-a-number"></a>允許數位

在此範例中 ```-Identity``` ，參數為必填項：

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
如果身分識別未知，請使用 Cmdlet 先找出正確的模式，並 ```Get-CsInboundBlockedNumberPattern``` 記下身分識別。 接著，執行 ```Remove-CsTenantBlockedNumberPattern``` Cmdlet 並傳遞適當的身分識別值。

在測試和驗證之前，請允許複製時間。

#### <a name="view-all-number-patterns"></a>查看所有數位模式

此 Cmdlet 會針對租使用者輸入的所有封鎖號碼清單：

```powershell
Get-CsInboundBlockedNumberPattern
```

使用內建的 PowerShell 篩選功能，以根據需要剖析所返回的值。

## <a name="add-number-exceptions"></a>新增數位例外

您可以透過命令、和 來新增例外情形到封鎖的編號 ```CsTenantBlockNumberExceptionPattern``` ```New``` ```Get``` ```Set``` 模式 ```Remove``` 。

- [New-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/new-cstenantblockednumberexceptionpattern) 會將數位例外模式新增到租使用者清單中。 
- [Get-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/get-cstenantblockednumberexceptionpattern) 會返回新加入租使用者清單的所有數位例外模式清單。
- [Set-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/set-cstenantblockednumberexceptionpattern) 會修改一或多個參數至租使用者清單中的數位例外模式。
- [Remove-CsTenantBlockedNumberExceptionPattern](/powershell/module/skype/remove-cstenantblockednumberexceptionpattern) 會從租使用者清單中移除數位例外模式。

### <a name="examples"></a>範例

#### <a name="add-a-number-exception"></a>新增數位例外

在此範例中，會建立新的數位例外模式，且預設會新增為已啟用的模式。 和 ```-Enabled``` ```-Description``` 參數為選擇性。

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>查看所有數位例外

在此範例中，-Identity 參數為選擇性。 如果未指定參數，此 Cmdlet 會返回為租使用者輸入的所有數位例外 ```-Identity``` 模式清單。
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>修改數位例外

在此範例中，-Identity 參數為必填專案。 ```Set-CsTenantBlockedNumberExceptionPattern```Cmdlet 可讓您修改指定數位模式身分識別的一或多個參數。
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>移除數位例外

在此範例中 ```-Identity``` ，參數為必填項。 此 Cmdlet 會移除租使用者清單中的給定數位模式。  如果身分識別未知，請使用 Cmdlet 先找出正確的模式，並 ```Get-CsInboundBlockedNumberPattern``` 記下身分識別。 接著，執行 ```Remove-CsTenantBlockedNumberExceptionPattern``` Cmdlet 並傳遞適當的身分識別值。在測試和驗證之前，請允許複製時間。  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>測試數位是否被封鎖

使用 ```Test-CsInboundBlockedNumberPattern``` Cmdlet 驗證租使用者中是否封鎖數位。
 
在此範例中， ```-Phonenumber``` 需要 ```-Tenant``` and 參數。 參數 ```-PhoneNumber``` 應為不含任何其他字元的數值字串，例如 + 或 -。 在 TRPS 中， ```-Tenant parameter``` 是選擇性的。 如果租使用者中的數位被封鎖，產生的參數會返回 True 的值，如果未封鎖，則會返回 ```isNumberBlocked``` False 值。

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

## <a name="a-note-about-regex"></a>Regex 注意事項

如先前所述，封鎖來電者的模式比對是使用 Regex 完成。 線上提供多種工具，可協助驗證 Regex 模式相符。 如果您不熟悉 Regex 模式，建議您花一些時間熟悉基本功能。 若要確定您獲得預期的結果，請使用驗證模式比對的工具，再新增封鎖的號碼比對至租使用者。 

## <a name="related-topics"></a>相關主題

- [設定您的電腦以使用 商務用 Skype管理線上Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
