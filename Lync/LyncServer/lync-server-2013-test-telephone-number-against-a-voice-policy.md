---
title: Lync Server 2013： 測試的語音原則針對電話號碼
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
ms.openlocfilehash: 7670e99fc7ac7688eff360a28be6f7280d6191b1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a>針對 Lync Server 2013 中的語音原則測試電話號碼

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
<p>當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有可執行此測試 CsVoicePolicy cmdlet 的權限的 RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Enterprise Voice 使用者能夠透過公用交換電話網路 (PSTN) 撥出電話電話取決，在大型組件，下列三個動作：

  - 指派給使用者的語音原則。

  - 從 Lync 伺服器用來將通話路由傳送至 PSTN 網路的語音路由。

  - PSTN 使用方式中，按一下 [連線到語音路由的語音原則的 Lync Server 屬性。

PSTN 使用方式，請務必特別是： 它是連線到語音路由的語音原則的屬性。 （語音原則和語音路由稱為有至少一個 PSTN 使用方式共通連接。）可以設定語音原則，但未指定 PSTN 使用方式。 在此情況下，被指派該原則的使用者將無法透過 PSTN 網路撥出電話。 同樣地，語音路由，不需要至少一個指定的 PSTN 使用方式將無法將通話路由傳送至 PSTN 網路。

測試 CsVoicePolicy cmdlet 會驗證指定的語音原則有 PSTN 使用方式和流量由至少一個語音路由共用。 如果驗證執行測試 CsVoicePolicy 成功，cmdlet 會回報它找到的第一個有效的語音路由的名稱以及 PSTN 使用方式路由所連線之原則的名稱。

</div>

<div>

## <a name="running-the-test"></a>執行測試

若要執行測試 CsVoicePolicy 指令程式，您必須先使用 Get-csvoicepolicy cmdlet 擷取執行個體要測試; 的語音原則該執行個體必須接著會以管線傳輸至測試 CsVoicePolicy。 例如：

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

請注意，此命令，它不會使用 Get-csvoicepolicy 擷取語音原則執行個體，將會失敗：

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

如果您想要檢查針對指定的電話號碼的所有語音原則，然後使用類似如下的命令：

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

請注意，必須使用 E.164 格式來指定 TargetNumber。 測試 CsVoicePolicy 不會嘗試正規化的需求，或將電話號碼轉譯成 E.164 格式。

如需詳細資訊，請參閱 < 測試 CsVoicePolicy cmdlet 的說明 」 文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果語音原則可以找到相符的語音路由和相符的 PSTN 使用方式，然後將螢幕上顯示的路由與用法：

FirstMatchingRoute MatchingUsage

\------------------ -------------

RedmondVoiceRoute RedmondPstnUsage

如果適當的語音路由或適當的 PSTN 使用方式找不到然後空白將螢幕上顯示屬性值：

FirstMatchingRoute MatchingUsage

\------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能有為何失敗的原因

如果測試 CsVoicePolicy 不會傳回表示的比對的語音原則不共用 PSTN 使用方式與語音路由。 若要確認，請使用類似下列的指令程式來驗證 PSTN 使用方式指派給語音原則：

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

接著，執行此命令，以決定 PSTN 使用方式將指派給每個語音路由：

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

如果您看到任何符合項目 （亦即，如果您看到您的語音原則和共用至少一個 PSTN 使用方式的一或多個語音路由），您應該再執行測試 CsVoiceRoute cmdlet 確認語音路由可以撥號對應表提供的電話號碼。

</div>

<div>

## <a name="see-also"></a>另請參閱


[測試 CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

