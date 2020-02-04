---
title: Lync Server 2013：根據語音原則測試電話號碼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37d0c9ae6512cb7755c7ef73e4cfd3e37b92884d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a>在 Lync Server 2013 中根據語音原則測試電話號碼

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsVoicePolicy Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

企業語音使用者在公用交換電話網絡（PSTN）樞軸上撥打電話的能力，主要是在三個方面進行：

  - 指派給使用者的語音原則。

  - 用來從 Lync 伺服器將呼叫路由至 PSTN 網路的語音路由。

  - PSTN 使用量，即將語音原則連線到語音路由的 Lync Server 屬性。

PSTN 使用量特別重要：它是將語音原則連接至語音路線的屬性。 （語音原則和語音路線是在有至少一個 PSTN 用法的情況中說是連線）。語音原則無需指定 PSTN 用法即可加以設定。 在這種情況下，指派該原則的使用者將無法透過 PSTN 網路撥出通話。 同樣地，沒有指定 PSTN 使用的語音路由也無法將呼叫路由至 PSTN 網路。

CsVoicePolicy Cmdlet 會驗證指定的語音原則是否有 PSTN 使用狀況，以及此用法是由至少一個語音路由所共用。 如果由 Test CsVoicePolicy 的驗證執行成功，則 Cmdlet 會傳回所找到的第一個有效語音路由的名稱，以及將原則連接到路線的 PSTN 使用的名稱。

</div>

<div>

## <a name="running-the-test"></a>執行測試

若要執行 Test CsVoicePolicy Cmdlet，您必須先使用 CsVoicePolicy Cmdlet 來檢索要測試的語音原則實例;然後必須將該實例以管道傳送給 Test CsVoicePolicy。 例如：

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

請注意，這個命令不會使用 CsVoicePolicy 來檢索語音原則實例，將會失敗：

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

如果您想要根據指定的電話號碼來檢查所有語音原則，請使用類似以下的命令：

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

請注意，您必須使用 E.i 格式來指定 TargetNumber。 CsVoicePolicy 不會嘗試將電話號碼標準化或轉換為 e. 164 格式。

如需詳細資訊，請參閱 Test CsVoicePolicy Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果語音原則可以找到相符的語音路由及相符的 PSTN 使用，則會在螢幕上顯示路由與使用方式：

FirstMatchingRoute MatchingUsage

\------------------ -------------

RedmondVoiceRoute RedmondPstnUsage

如果找不到合適的語音路線或適當的 PSTN 使用量，螢幕上就會顯示空白屬性值：

FirstMatchingRoute MatchingUsage

\------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

如果 Test CsVoicePolicy 沒有傳回一個相符的值，這可能表示語音原則不會與語音路線共用 PSTN 使用方式。 若要驗證，請使用類似下列的 Cmdlet 來驗證指派給語音原則的 PSTN 用法：

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

接著，執行這個命令來判斷 PSTN 用法指派給每個語音路由：

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

如果您看到任何相符的專案（也就是，如果您看到一個或多個與您的語音原則共用至少一個 PSTN 的語音路由），您就應該執行 CsVoiceRoute Cmdlet，以確認語音路由可以撥打所提供的電話號碼。

</div>

<div>

## <a name="see-also"></a>請參閱


[Test-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

