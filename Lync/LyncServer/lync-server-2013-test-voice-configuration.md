---
title: Lync Server 2013：測試語音設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbe9be7e0f7962bbab546822e7ce6cd47e063540
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中測試語音設定

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsVoiceTestConfiguration Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Lync Server 包含數個 Windows PowerShell Cmdlet （例如 Test CsVoiceRoute 和 Test CsVoicePolicy、Test New-cstrunkconfiguration），可讓您驗證企業語音結構的個別元件-語音路線、語音原則，SIP trunks –如期運作。

雖然所有個別元件都能正常運作，但在企業語音都能起作用：您可以使用有效的語音路線、有效的語音原則，以及有效的 SIP 幹線，但仍有使用者無法撥打或接聽電話。 因此，Lync Server 也提供建立語音測試設定的功能。 語音測試設定代表常見的企業語音案例：您可以指定語音路線、語音原則和撥號方案等專案，然後確認這些個別專案能共同作業以提供電話語音。 此外，您也可以在指定案例中驗證您的預期。 例如，假設您預計 [撥入方案 A] 和 [語音原則 B] 的組合會導致呼叫以語音路由 C 路由。您可以輸入語音路由 C 做為 ExpectedRoute。 當您執行測試時，如果沒有使用語音路由 C，則測試將會標示為失敗。

</div>

<div>

## <a name="running-the-test"></a>執行測試

在使用 Windows PowerShell 測試語音組態集合之前，您必須先使用 CsVoiceTestConfiguration Cmdlet 來檢索這些設定設定的實例。 該實例必須接著以管道傳送到測試 CsVoiceTestConfiguration。 例如：

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

若要同時驗證所有的語音測試設定，請改為使用此命令：

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

如需詳細資訊，請參閱 Test CsVoiceTestConfiguration Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

Test CsVoiceTestConfiguration Cmdlet 會報告測試是否失敗或成功，並提供每個成功測試的其他相關資訊，例如翻譯規則、語音路線，以及用來完成工作的 PSTN 使用方式：

結果：成功

TranslatedNumber： + 15551234

MatchingRule： Description =;Pattern = ^ （\\d{4}） $;譯文 = + 1\\d;Name = Test; IsInternalExtension = False

FirstMatchingRoute：網站：雷蒙德

MatchingUsage： Local

如果測試失敗，則會將結果報告為失敗：

結果：失敗

TranslatedNumber:   

FirstMatchingRoute:

MatchingUsage:      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

因為語音測試組態測試會測試數個不同的專案，包括語音原則、撥號方案、語音路由等等，因此可能會造成測試失敗的幾個不同因素。 如果測試失敗，您的第一個步驟就是使用 CsVoiceTestConfiguration Cmdlet 來查看設定設定本身：

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

如果設定正確設定，請重新執行測試，包括詳細參數：

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

詳細的參數將提供由 Test CsVoiceTestConfiguration 所採取的每個動作的逐步帳戶，如下例所示：

詳細：載入撥號方案：「全域」

詳細：載入語音原則： "RedmondDialPlan"

此逐步式帳戶可能會提供有用的線索來指示測試實際失敗的位置。 如果不是，您可以使用其他的 Windows PowerShell Cmdlet （例如 Test-CsVoicePolicy），並系統地開始驗證語音測試設定中所包含的個別元件。

此外，請注意，測試可以傳送通話，但仍會標示為失敗，否則可能會出現問題;如果您輸入 ExpectedRoute、ExpectedTranslatedNumber 和 ExpectedUsage 的值，而且不符合這些預期中的任何一個，就會發生這種情況。 例如，假設您輸入語音路由 C 作為預期的語音路線，但測試實際上是使用語音路由 D 完成通話。在這種情況下，測試將會標示為失敗，因為未使用預期的語音路由。 如果測試失敗，您可以移除 ExpectedRoute、ExpectedTranslatedNumber 和 ExpectedUsage 的值，然後重新執行測試。 這可協助您判斷失敗是因為通話無法完成，或是因為您預期是接聽電話，而實際收到另一個。

</div>

<div>

## <a name="see-also"></a>請參閱


[Test-CsVoiceTestConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

