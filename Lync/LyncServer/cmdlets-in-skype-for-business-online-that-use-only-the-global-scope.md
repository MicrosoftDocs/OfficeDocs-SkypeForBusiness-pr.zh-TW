---
title: Skype 商務 Online 中使用全域範圍的指令程式
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
ms.openlocfilehash: f4a894c4a9c6e2913abb003c49094bc6d6868483
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001248"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a>Skype 商務 Online 中使用全域範圍的指令程式

 


有多個的 Skype for Business Online 設定只會在*全域範圍*。 這表示套用至指派給該租用戶的所有使用者設定的單一集合。 （每個租用戶都有通用設定其專屬唯一集合）。當您使用全域範圍僅限於的指令程式時，Identity 參數是選擇性的。 例如，若要擷取會議組態設定，您可以使用此命令：

    Get-CsMeetingConfiguration -Identity "global"

或者，您可以省略 Identity 參數，並改為使用這個簡單的命令：

    Get-CsMeetingConfiguration

因為只有一個全域的會議組態設定集合，兩個命令會傳回完全相同的資訊。 使用下列其中一個**設定 Cs**指令程式時，也可以省略 Identity 參數。 這兩個命令是相同的：

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

兩個命令皆相同，因為根據預設，Windows PowerShell 將會修改全域集合如果您未包含 Identity 參數。

下列指令程式作業只會在全域範圍：

  - [Get-csimfilterconfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))

  - [Get-csmeetingconfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))

  - [Get-csprivacyconfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))

  - [取得 CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))

  - [取得 CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))

  - [取得 CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))

  - [取得 CsTenantPublicProvider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))

  - [移除 CsVoicePolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))

  - [Set-csmeetingconfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))

  - [Set-csprivacyconfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))

請注意，**移除 CsVoicePolicy**指令程式的異常的某個項目。 首先，此 cmdlet 會要求您加入 Identity 參數：

    Remove-CsVoicePolicy -Identity "global"

其次，**移除 CsVoicePolicy**指令程式不會實際刪除全域語音原則;Skype 商務 Online 不允許您刪除全域原則或設定值。 此 cmdlet 的作用為何是可讓您的全域語音原則中的所有屬性重都設為其預設值。 例如，根據預設，AllowCallForwarding 屬性設為 False。 不過，AllowCallForwarding 可能已修改，值立即設定為 True。 當您執行**移除 CsVoicePolicy**指令程式時，AllowCallForwarding 屬性就會還原成其預設值： False。 下表摘要說明此案例：


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
<td><p>之後已修改全域原則</p></td>
</tr>
<tr class="odd">
<td><p>False</p></td>
<td><p>已<strong>移除 CsVoicePolicy</strong>之後執行指令程式</p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a>另請參閱


[身分識別、 範圍與 skype for Business Online 租用戶](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Skype 商務 Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

