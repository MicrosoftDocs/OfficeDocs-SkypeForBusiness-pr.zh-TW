---
title: Lync Server 2013：對照電話號碼檢查幹線設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b667f43e430b5047f72e2d8352f57337f0849055
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a>在 Lync Server 2013 中檢查 [中繼] 設定與電話號碼

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-20_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>驗證排程</p></td>
<td><p>次</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>需要許可權</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 New-cstrunkconfiguration Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

SIP trunks 將 Lync Server 內部企業語音網路連線至下列任何一項：

  - 公用交換電話網絡（PSTN）。

  - IP 公用分支交換（PBX）。

  - 會話邊界控制器（SBC）。

New-cstrunkconfiguration Cmdlet 會驗證電話號碼（由使用者撥打電話）可以轉換成 E. 164 網路，並透過指定的 SIP 幹線路由。

</div>

<div>

## <a name="running-the-test"></a>執行測試

若要執行 Test New-cstrunkconfiguration Cmdlet，您必須先使用 New-cstrunkconfiguration Cmdlet 來檢索 SIP 幹線設定的實例;然後，該實例會以管道的方法傳送給 Test New-cstrunkconfiguration：

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

執行測試-New-cstrunkconfiguration，而不事先執行 New-cstrunkconfiguration 將無法運作。 例如，此命令將會失敗，而不會傳回任何資料：

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

如果您有多個 SIP 幹線設定的集合，您可以使用類似下列的命令來針對相同的電話號碼測試每個集合：

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

如需詳細資訊，請參閱 Test New-cstrunkconfiguration Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果測試 New-cstrunkconfiguration 可以撥打電話給撥打的號碼，則已翻譯的電話號碼（以 E 為格式），而用來翻譯該電話號碼的規則將會顯示在螢幕上：

TranslatedNumber MatchingRule

\---------------- ------------

\+12065551219全球/雷蒙德

如果測試失敗，測試 New-cstrunkconfiguration 會傳回空屬性值：

TranslatedNumber MatchingRule

\---------------- ------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

如果 Test New-cstrunkconfiguration 沒有傳回 match，通常表示測試的幹線設定設定沒有撥出電話號碼轉換規則，可將撥打的號碼轉換為 e. 164 格式。 若要取得指派給主幹設定設定集合的翻譯規則，您可以使用類似以下的語法：

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

針對每個翻譯規則傳回如下所示的資訊：

描述：不含國家/地區代碼或區號的電話號碼。

模式： ^\\+ （\\d\*） $

`Translation : $1`

名稱： NoAreaCode

此時，您會檢查 Pattern 屬性的值（這是一個[正則運算式](http://go.microsoft.com/fwlink/?linkid=400464)字串），以查看是否有任何翻譯規則設定為處理撥號號碼。 如果不是，您必須變更其中一個現有規則（CsOutboundTranslationRule），或使用新的-CsOutboundTranslationRule Cmdlet，才能在集合中新增規則。

</div>

<div>

## <a name="see-also"></a>請參閱


[Test-New-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

