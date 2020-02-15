---
title: Lync Server 2013： 測試語音組態
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
ms.openlocfilehash: 2894d61a4dabd174315e24a225392bde7a893300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a>Lync Server 2013 中的測試語音組態

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-05-20 個_


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
<td><p>測試工具</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有可執行此測試 Test-csvoicetestconfiguration cmdlet 的權限的 RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Lync Server 包含數個 Windows PowerShell cmdlet （如測試 CsVoiceRoute 和測試 CsVoicePolicy、 測試 Test-cstrunkconfiguration），可讓您確認 Enterprise Voice 基礎結構 – 語音路由、 語音個別原則，SIP 主幹 – 如預期般運作。

時請務必與所有的個別工作的企業語音： 很可能具有有效的語音路由、 有效的語音原則，以及有效的 SIP 主幹，但仍有使用者無法撥打或接聽電話。 因此，Lync Server 也會提供建立語音測試組態的能力。 語音測試組態代表 Enterprise Voice 的常見案例： 您可以為語音路由、 語音原則和撥號對應表，指定下列項目，然後驗證這些個別項目是否能夠一起運作，以提供電話服務的工作。 此外，您可以驗證在指定的案例中您預期。 例如，假設您所預期的撥號對應表 A 和 B 的語音原則組合會導致來電路由傳送透過語音路由 c。您可以輸入語音路由 C 作為 ExpectedRoute。 當您執行測試，如果語音路由 C 不採用然後測試會被標示為具有失敗。

</div>

<div>

## <a name="running-the-test"></a>執行測試

之前測試使用 Windows PowerShell 的語音組態集合，您必須先使用 Get-Test-csvoicetestconfiguration cmdlet 來擷取這些組態設定執行個體。 該執行個體必須接著會以管線傳輸至測試 Test-csvoicetestconfiguration。 例如：

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

若要在同一時間驗證所有語音測試組態設定，請改為使用此命令：

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

如需詳細資訊，請參閱 < 測試 Test-csvoicetestconfiguration cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

測試 Test-csvoicetestconfiguration cmdlet 會報告測試失敗，或已成功完成，並提供每個成功的測試，例如轉譯規則、 語音路由]，以及用來完成工作的 PSTN 使用方式相關的其他資訊：

結果： 成功

TranslatedNumber: +15551234

MatchingRule: Description =;圖樣 = ^ (\\d{4}) $;翻譯 = + 1\\d;名稱 = 測試; IsInternalExtension = False

FirstMatchingRoute： 為 site: Redmond

MatchingUsage： 本機

如果測試失敗結果是會回報為失敗：

結果： 失敗

TranslatedNumber:   

FirstMatchingRoute:

MatchingUsage:      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能有為何失敗的原因

因為語音測試組態測試測試數個不同的項目 – 包括語音原則、 撥號對應表計劃、 語音路由、 等等 – 有幾個不同的因素，可能會導致測試失敗。 如果測試失敗，您必須先應該使用 Get-Test-csvoicetestconfiguration cmdlet 來檢閱本身的組態設定：

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

如果設定正確，重新執行測試時包括 Verbose 參數：

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

Verbose 參數會提供每個所採取的動作測試 Test-csvoicetestconfiguration 在這個範例所示的逐步帳戶：

VERBOSE： 載入撥號對應表:"Global"

VERBOSE： 載入語音原則: 「 RedmondDialPlan 」

此逐步帳戶可能會提供測試實際失敗的有用線索。 如果沒有，您可以再使用其他的 Windows PowerShell cmdlet （如測試 CsVoicePolicy)，並有條不紊開始驗證個別元件所隨附的語音測試組態設定。

所，請注意，它可能會用於測試，若要能夠將通話路由傳送並仍尚未被標示為失敗;如果 ExpectedRoute、 ExpectedTranslatedNumber，及 ExpectedUsage，輸入值，並不符合任何這些期望，可能發生的項目。 例如，假設為您預期的語音路由] 中，輸入語音路由 C，但測試實際完成的呼叫中使用語音路由 d。在此情況下測試將會被標示為 「 失敗因為不使用預期的語音路由。 如果測試失敗，您可能 ExpectedRoute、 ExpectedTranslatedNumber，及 ExpectedUsage 移除值，然後再重新執行測試。 可協助您決定是否失敗是因為無法完成電話，或是您預期一件事，以及實際接收到另一個。

</div>

<div>

## <a name="see-also"></a>另請參閱


[測試 Test-csvoicetestconfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

