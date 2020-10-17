---
title: Lync Server 2013：對照語音原則測試電話號碼
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
ms.openlocfilehash: f2ac10938dbbc2810e5b43aae85711bf8413ad27
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519160"
---
# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a>在 Lync Server 2013 中對照語音原則測試電話號碼

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsVoicePolicy Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

企業語音使用者透過公用交換電話網路撥打撥出電話的能力 (PSTN) 樞，在很大的情況下，有三種情況：

  - 指派給使用者的語音原則。

  - 用於將呼叫從 Lync Server 路由傳送至 PSTN 網路的語音路由。

  - PSTN 使用方式，即將語音原則連線至語音路由的 Lync Server 屬性。

PSTN 使用方式尤為重要：它是將語音原則連線到語音路由的屬性。  (語音原則和語音路由稱為已連接，但其共有至少一個 PSTN 使用情形。 ) 語音原則可以設定，但不指定 PSTN 使用方式。 在此情況下，已獲指派該原則的使用者將無法透過 PSTN 網路撥出電話。 同樣地，沒有至少一個指定 PSTN 使用方式的語音路由，也無法將通話路由傳送至 PSTN 網路。

Test-CsVoicePolicy Cmdlet 會驗證指定的語音原則是否有 PSTN 使用狀況，以及其使用方式是否至少由一個語音路由所共用。 如果 Test-CsVoicePolicy 成功執行驗證，指令程式會傳回找到的第一個有效語音路由的名稱，也會傳回將原則連接至路由的 PSTN 使用名稱。

</div>

<div>

## <a name="running-the-test"></a>執行測試

若要執行 Test-CsVoicePolicy 指令程式，您必須先使用 Get-CsVoicePolicy Cmdlet，以找回要測試之語音原則的實例;然後，必須將該實例管線傳送至 Test-Set-csvoicepolicy。 例如：

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

請注意，此命令不會使用 Get-CsVoicePolicy 來取得語音原則實例，否則會失敗：

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

如果您想要根據指定的電話號碼檢查所有語音原則，請使用類似下列的命令：

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

請注意，必須使用 e.164 格式來指定 TargetNumber。 Test-CsVoicePolicy 不會嘗試將電話號碼正常化或轉譯為 e.164 格式。

如需詳細資訊，請參閱 Test-CsVoicePolicy Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

若語音原則可以找到相符的語音路由和相符的 PSTN 使用，則會在螢幕上顯示路由和使用狀況：

FirstMatchingRoute MatchingUsage

\------------------ -------------

RedmondVoiceRoute RedmondPstnUsage

如果找不到適當的語音路由或適當的 PSTN 使用方式，將會在螢幕上顯示空白的屬性值：

FirstMatchingRoute MatchingUsage

\------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

如果 Test-CsVoicePolicy 未傳回可能表示語音原則與語音路由不共用 PSTN 使用狀況的相符。 若要驗證，請使用類似下列的指令程式，以驗證指派給語音原則的 PSTN 使用方式：

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

接下來，執行此命令以判斷 PSTN 使用方式指派給每個語音路由：

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

如果您看到任何相符 (，也就是，如果您看到一或多個語音路由，其至少共用一個 PSTN 使用方式與您的語音原則) ，則應該執行 Test-CsVoiceRoute Cmdlet，以確認語音路由可以撥打所提供的電話號碼。

</div>

<div>

## <a name="see-also"></a>另請參閱


[測試-Set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

