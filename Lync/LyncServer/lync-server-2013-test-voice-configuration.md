---
title: Lync Server 2013：測試語音設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1491aa1d28de238bcadd2a024021fabf16e9128a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527900"
---
# <a name="test-voice-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中測試語音設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<td><p>每月</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsVoiceTestConfiguration Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Lync Server 包含數個 Windows PowerShell Cmdlet (例如 Test-CsVoiceRoute 和 Set-csvoicepolicy，Test-CsTrunkConfiguration) ，可讓您驗證企業語音基礎結構的個別元件–語音路由、語音原則、SIP 主幹–如預期般運作。

雖然所有個別片段都運作的 Enterprise Voice 很重要，但仍然可以有有效的語音路由、有效的語音原則和有效的 SIP 主幹，但仍然有使用者無法撥打或接聽電話。 因此，Lync Server 也會提供建立語音測試設定的能力。 語音測試設定代表常見的 Enterprise Voice 案例：您可以指定語音路由、語音原則和撥號對應表等事項，然後驗證各項專案是否可以一起運作，以提供電話語音。 此外，您也可以在特定案例中驗證您的預期。 例如，假設您預期撥號對應表 A 和 voice policy B 的組合會導致通話透過語音路由 C 路由傳送。您可以輸入語音路由 C 做為 ExpectedRoute。 當您執行測試時，如果沒有採用 voice route C，測試就會標示為已失敗。

</div>

<div>

## <a name="running-the-test"></a>執行測試

在使用 Windows PowerShell 測試語音設定集合之前，您必須先使用 Get-CsVoiceTestConfiguration Cmdlet，以取得這些設定設定的實例。 然後，必須將該實例管線傳送至 Test-CsVoiceTestConfiguration。 例如：

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

若要同時驗證所有語音測試設定，請改為使用此命令：

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

如需詳細資訊，請參閱 Test-CsVoiceTestConfiguration Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

Test-CsVoiceTestConfiguration 指令指令會報告測試是否失敗或已成功，並提供每個成功測試的詳細資訊，例如轉譯規則、語音路由，以及用來完成工作的 PSTN 使用方式：

結果：成功

TranslatedNumber： + 15551234

MatchingRule： Description =;Pattern = ^ (\\ d {4}) $;轉譯 = + 1 \\ d;Name = Test; IsInternalExtension = False

FirstMatchingRoute： site： Redmond

MatchingUsage：本機

如果測試失敗，則結果會報告為 [失敗]：

結果：失敗

TranslatedNumber:   

FirstMatchingRoute:

MatchingUsage:      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

因為語音測試設定測試會測試數種不同的專案（包括語音原則、撥號對應表、語音路由等等），所以有許多不同的因素會導致測試失敗。 測試失敗時，您的第一個步驟應該是使用 Get-CsVoiceTestConfiguration Cmdlet，自行複查設定設定：

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

如果設定看似已正確設定，請重新執行測試，包含 Verbose 參數：

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

Verbose 參數會提供 Test-CsVoiceTestConfiguration 所執行之每個動作的逐步帳戶，如下列範例所示：

詳細：載入撥號對應表： "Global"

詳細：載入語音原則： "RedmondDialPlan"

這種逐步執行的帳戶可能會提供有用的線索，以供測試實際失敗的地方使用。 如果不是，您可以使用其他 Windows PowerShell Cmdlet (例如 Test-Set-csvoicepolicy) ，然後開始驗證語音測試設定中所包含的個別元件。

除了這一點，請注意，測試是否可以路由通話，但仍會標示為失敗;當您輸入 ExpectedRoute、ExpectedTranslatedNumber 和 ExpectedUsage 的值時，可能會發生這種情況，而且不會滿足任何預期。 例如，假設您輸入語音路由 C 做為預期的語音路由，但測試實際上是使用語音路由 D 完成通話。在此情況下，測試會標示為「失敗」，因為未使用預期的語音路由。 如果測試失敗，您可以移除 ExpectedRoute、ExpectedTranslatedNumber 和 ExpectedUsage 的值，然後重新執行測試。 這可協助您判斷失敗是否因為無法完成通話，或是因為您想要一件事而真的收到另一個。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Test-CsVoiceTestConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

