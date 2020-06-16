---
title: 僅使用全域範圍之商務用 Skype Online 中的 Cmdlet
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use only the global scope
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56558800
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b97f3c8d9ca7dda0b96db211192350184cbf27b1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755095"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a>僅使用全域範圍之商務用 Skype Online 中的 Cmdlet

 


您可以在*全域範圍內*使用許多商務用 Skype Online 設定。 這表示有單一的設定集合，套用至指派給該租使用者的所有使用者。 （每個租使用者都有自己的唯一全域設定集合。）當您使用限制為全域範圍的指令程式時，Identity 參數是選用的。 例如，若要檢索會議設定設定，您可以使用此命令：

    Get-CsMeetingConfiguration -Identity "global"

或者，您可以省略 Identity 參數，而改為使用這個較簡單的命令：

    Get-CsMeetingConfiguration

因為只有一個全域集合的會議設定，所以這兩個命令會傳回完全相同的資訊。 使用其中一個 a **Cs** Cmdlet 時，也可以省略 Identity 參數。 這兩個命令相同：

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

這兩個命令是相同的，因為根據預設，Windows PowerShell 會在未包含 Identity 參數時修改全域集合。

下列 Cmdlet 只會在全域範圍內運作：

  - [Get-CsImFilterConfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))

  - [Get-CsMeetingConfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))

  - [Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))

  - [CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))

  - [CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))

  - [CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))

  - [CsTenantPublicProvider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))

  - [Remove-Set-csvoicepolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))

  - [Set-CsMeetingConfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))

  - [Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))

請注意， **set-csvoicepolicy** Cmdlet 是一個反常情況。 首先，此 Cmdlet 必須包含 Identity 參數：

    Remove-CsVoicePolicy -Identity "global"

其次， **set-csvoicepolicy 指令程式**實際上不會刪除通用語音原則;商務用 Skype Online 不允許您刪除全域原則或設定設定。 Cmdlet 的作用是讓您將全域語音原則中的所有屬性重設為預設值。 例如，根據預設，AllowCallForwarding 屬性會設定為 False。 不過，AllowCallForwarding 可能已修改，但現在值設定為 True。 當您執行**set-csvoicepolicy** Cmdlet 時，AllowCallForwarding 屬性會回復成其預設值： False。 下表摘要說明此案例：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>AllowCallForwarding 值</th>
<th>案例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>False</p></td>
<td><p>預設值</p></td>
</tr>
<tr class="even">
<td><p>True</p></td>
<td><p>在修改全域原則之後</p></td>
</tr>
<tr class="odd">
<td><p>False</p></td>
<td><p><strong>Set-csvoicepolicy</strong> Cmdlet 已執行之後</p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a>另請參閱


[商務用 Skype Online 中的身分識別、範圍和承租人](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[商務用 Skype Online Cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

