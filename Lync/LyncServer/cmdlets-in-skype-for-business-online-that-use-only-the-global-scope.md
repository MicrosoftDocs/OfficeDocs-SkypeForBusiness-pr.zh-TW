---
title: 商務用 Skype Online 的 Cmdlet 只使用全域範圍
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 5610649295fdf4089372d9c59e4ccb51228c1fc2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728103"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a>商務用 Skype Online 的 Cmdlet 只使用全域範圍

 


許多商務用 Skype Online 設定僅適用于*全域範圍*。 這表示有一個設定集合，這些設定會套用至指派給該租使用者的所有使用者。 （每個租使用者都有自己獨特的全域設定集合）。當您使用限制在全域範圍的 Cmdlet 時，身分識別參數是選擇性的。 例如，若要檢索會議設定，您可以使用此命令：

    Get-CsMeetingConfiguration -Identity "global"

或者，您可以省略身分識別參數並改用這個更簡單的命令：

    Get-CsMeetingConfiguration

因為只有一個全域集合的會議設定，所以這兩個命令會傳回完全相同的資訊。 使用其中一個**設定的 Cs** Cmdlet 時，也可以省略身分識別參數。 這兩個命令完全相同：

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

這兩個命令完全相同，因為如果您不包含身分識別參數，Windows PowerShell 就會修改全域集合。

下列 Cmdlet 只會在全域範圍中運作：

  - [CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))

  - [CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))

  - [CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))

  - [Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))

  - [移除-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))

  - [Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))

  - [Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))

請注意， **CsVoicePolicy** Cmdlet 是一些異常的情況。 首先，這個 Cmdlet 需要您加入身分識別參數：

    Remove-CsVoicePolicy -Identity "global"

其次， **CsVoicePolicy** Cmdlet 不會實際刪除全域語音原則;商務用 Skype Online 不允許您刪除全域原則或配置設定。 Cmdlet 的用途是讓您將全域語音原則中的所有屬性重設為預設值。 例如，根據預設，AllowCallForwarding 屬性會設定為 False。 不過，AllowCallForwarding 可能已修改，且值現在已設定為 True。 當您執行**CsVoicePolicy** Cmdlet 時，AllowCallForwarding 屬性會還原為預設值： False。 下表摘要說明這個案例：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>AllowCallForwarding 值</th>
<th>例子</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>虛假</p></td>
<td><p>預設值</p></td>
</tr>
<tr class="even">
<td><p>滿足</p></td>
<td><p>在修改全域原則之後</p></td>
</tr>
<tr class="odd">
<td><p>虛假</p></td>
<td><p><strong>CsVoicePolicy</strong> Cmdlet 執行之後</p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a>請參閱


[商務用 Skype Online 中的身分識別、範圍和租使用者](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

