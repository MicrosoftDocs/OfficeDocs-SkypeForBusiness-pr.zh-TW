---
title: 在商務用 Skype Online 中封鎖撥入通話
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: b238d69087c5b29e6d9abc898e91c44fd8053411
ms.sourcegitcommit: bb88ac0c9489bb47957e5ef1074b5df3126b6fdb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266060"
---
# <a name="block-inbound-calls"></a>封鎖撥入通話

商務用 Skype Online 通話方案現在支援封鎖來自公用交換電話網絡（PSTN）的撥入通話。 此功能可讓您針對清單中的每個撥入 PSTN 呼叫，針對其進行檢查，以進行數位模式的租使用者識別碼。 如果進行了相符，就會拒絕來電。

這個輸入呼叫封鎖功能只能在源自 PSTN 的撥入通話中運作，且僅適用于租使用者全域基礎。 在每個使用者的基礎上無法使用。  

此功能尚未提供給直接路由。

>[!NOTE]
> 封鎖的呼叫者可能會在已封鎖的情況中遇到稍有不同的行為。 此行為是根據封鎖的呼叫者的載波如何處理呼叫不允許成功完成的通知而定。 範例中可能會包含一則指示來電無法完成的載波訊息，或只是要放下通話。

## <a name="call-blocking-admin-controls-and-information"></a>呼叫封鎖管理員控制與資訊

封鎖號碼的管理員控制項只使用 PowerShell 提供。 數位區塊模式定義為一般運算式模式。 運算式的順序不重要-清單中第一個符合的模式會導致通話封鎖。 在封鎖的呼叫者清單中新增或移除的新號碼或模式，模式可能需要長達24小時才能生效。

## <a name="call-blocking-powershell-commands"></a>呼叫封鎖 PowerShell 命令

數位模式```CsInboundBlockedNumberPattern```是透過命令```New```、 ```Get```、 ```Set```和```Remove```來管理。 您可以使用這些 Cmdlet 來管理指定的模式，包括切換指定模式啟用的功能。
- [CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/get-csinboundblockednumberpattern)會傳回已加入租使用者清單的所有封鎖數位模式清單，包括名稱、描述、Enabled （True/False），以及每個的模式。
- [[新-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/new-csinboundblockednumberpattern) ] 會將封鎖的數位模式新增至租使用者清單。
- [移除-CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/remove-csinboundblockednumberpattern)會從租使用者清單中移除封鎖的數位模式。
- [[設定] CsInboundBlockedNumberPattern](https://docs.microsoft.com/powershell/module/skype/set-csinboundblockednumberpattern)會修改租使用者清單中封鎖數位模式的一個或多個參數。

查看並啟用整個呼叫封鎖功能是透過```CsTenantBlockingCallingNumbers```命令```Get```和```Set```來管理。

- [CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockedcallingnumbers)會傳回全域封鎖編號清單的參數，包括 [已啟用] （True/False）。 只有在開啟或關閉此功能時，才能手動修改單一全域租使用者原則。
- [Set-CsTenantBlockedCallingNumbers](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockedcallingnumbers)可讓您在租使用者層級開啟和關閉全域租使用者封鎖通話。

### <a name="examples"></a>範例

#### <a name="block-a-number"></a>封鎖數位

在這個範例中， ```-Enabled``` and ```-Description```參數是選擇性的：

```powershell
New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”
```

建立新的模式會將模式新增為 [預設啟用]。 [描述] 是一個可提供詳細資訊的選用欄位。

我們建議您提供有意義的名稱，以輕鬆瞭解新增模式的原因。 在只封鎖垃圾郵件號碼的情況下，請考慮將規則命名為與要相符的數位模式相同，然後根據需要在描述中新增其他資訊。

使用正則運算式（Regex）來配對模式。 在進行測試和驗證前，請先留出時間進行複製。

#### <a name="allow-a-number"></a>允許數位

在這個範例中， ```-Identity```參數是必要的：

```powershell
Remove-CsInboundBlockedNumberPattern -Identity “<identity>”
```
 
如果不知道身分識別，請使用```Get-CsInboundBlockedNumberPattern``` Cmdlet 來先找出適當的模式，並記下身分識別。 然後，執行```Remove-CsTenantBlockedNumberPattern``` Cmdlet 並傳遞適當的身分識別值。

在進行測試和驗證前，請先留出時間進行複製。

#### <a name="view-all-number-patterns"></a>查看所有數位模式

執行此 Cmdlet 會傳回為租使用者輸入的所有封鎖號碼清單：

```powershell
Get-CsInboundBlockedNumberPattern
```

使用內建的 PowerShell 篩選功能，根據需要分析傳回的值。

## <a name="add-number-exceptions"></a>新增數位例外狀況

```CsTenantBlockNumberExceptionPattern```您可以透過命令、、 ```New``` ```Get``` ```Set```、及```Remove```等方式，將例外狀況新增至封鎖的編號模式。

- [新-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/new-cstenantblockednumberexceptionpattern)會將數位例外模式新增至租使用者清單。 
- [CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/get-cstenantblockednumberexceptionpattern)會傳回已新增至租使用者清單的所有數位例外模式清單。
- [[設定] CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/set-cstenantblockednumberexceptionpattern)會將一個或多個參數修改為租使用者清單中的數位例外模式。
- [移除-CsTenantBlockedNumberExceptionPattern](https://docs.microsoft.com/powershell/module/skype/remove-cstenantblockednumberexceptionpattern)會移除租使用者清單中的數位例外模式。

### <a name="examples"></a>範例

#### <a name="add-a-number-exception"></a>新增數位例外狀況

在這個範例中，會建立新的數位例外模式，而且預設會將模式新增為 [啟用]。 And ```-Enabled``` ```-Description```參數是選擇性的。

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Pattern <String> -Enabled <bool> -Description <string>
```

```powershell
New-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930 -Pattern "^011(\d*)$" -Description "Allow international prefix in US"  
```

#### <a name="view-all-number-exceptions"></a>查看所有數位例外狀況

在這個範例中，-身分識別參數是選擇性的。 如果未```-Identity```指定參數，此 Cmdlet 會傳回為租使用者輸入的所有數位例外模式清單。
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```
 
```powershell
Get-CsTenantBlockedNumberExceptionPattern -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

#### <a name="modify-a-number-exception"></a>修改數位例外狀況

在這個範例中，-身分識別參數是強制性的。 這個```Set-CsTenantBlockedNumberExceptionPattern``` Cmdlet 能讓您針對指定的數位模式身分修改一或多個參數。
 
```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID> -Enabled <bool> -Description <string> -Pattern <string> 
```

```powershell
Set-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930  -Pattern "^022(\d*)$" 
```

#### <a name="remove-a-number-exception"></a>移除數位例外狀況

在這個範例中， ```-Identity```參數是必要的。 這個 Cmdlet 會從租使用者清單中移除指定的數位模式。  如果不知道身分識別，請使用```Get-CsInboundBlockedNumberPattern``` Cmdlet 來先找出適當的模式，並記下身分識別。 然後，執行```Remove-CsTenantBlockedNumberExceptionPattern``` Cmdlet 並傳遞適當的身分識別值。在進行測試和驗證前，請先留出時間進行複製。  

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity <XdsGlobalRelativeIdentity> -Tenant <GUID>
```

```powershell
Remove-CsTenantBlockedNumberExceptionPattern -Identity InternationalPrefix -Tenant daacb588-18ef-4f77-8c83-955af9615930
```

### <a name="test-whether-a-number-is-blocked"></a>測試是否已封鎖某個數位

使用```Test-CsInboundBlockedNumberPattern``` Cmdlet 驗證租使用者中是否有某個數位遭到封鎖。
 
在這個範例中， ```-Phonenumber```需要```-Tenant```和參數。 ```-PhoneNumber```參數應該是不含任何其他字元（例如 + 或-）的數值字串。 在 TRPS 中， ```-Tenant parameter```是選擇性的。 如果該```isNumberBlocked```數位在租使用者中遭到封鎖，則結果參數會傳回 True 值，如果未封鎖，則傳回 False。

```powershell
Test-CsInboundBlockedNumberPattern –Tenant <GUID> -PhoneNumber <String>
```

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 4255550101
```

|HTTPResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | 滿足        |         |

```powershell
Test-CsInboundBlockedNumberPattern -Tenant e09ad6bc-1d3c-4650-8cae-02f6c5a04b45 -PhoneNumber 6045550188
```

|HTTPResponseCode  |isNumberBlocked   |errorMessage |
|---------|---------|---------|
|200    | 虛假        |         |

## <a name="a-note-about-regex"></a>關於 Regex 的筆記

如前所述，封鎖式呼叫者的模式相符是使用 Regex 來完成。 有多個工具可供線上使用，以協助驗證 Regex 模式相符。 如果您不熟悉 Regex 模式，建議您花一些時間來熟悉基本概念。 若要確保您取得預期的結果，請在您將封鎖的新數位與您的租使用者加入之前，使用驗證模式相符的工具。 

## <a name="related-topics"></a>相關主題

- [設定您的電腦以使用 Windows PowerShell 管理商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
