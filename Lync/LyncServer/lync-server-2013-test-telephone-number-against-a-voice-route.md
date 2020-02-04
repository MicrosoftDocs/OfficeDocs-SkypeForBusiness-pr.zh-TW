---
title: Lync Server 2013：根據語音路線測試電話號碼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d4105b54c7d5b745efddeeb961960c402aaa349
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a>在 Lync Server 2013 中根據語音路線測試電話號碼

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsVoiceRoute Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

語音路由可搭配語音原則共同作業，協助將企業語音通話路由至 PSTN 網路。 每個語音路線都包含一個正則運算式（數位模式），可識別將透過特定語音路線路由的電話號碼：路線將能夠處理符合此正則運算式的任何電話號碼。 例如，語音路由可能有一個正則運算式，可讓它處理任何10位數的數位。 這表示路由可以處理如下所示的電話號碼：

  - 2065551219

此路線將無法處理下列兩個數字中的任一個，兩者都沒有10位數：

  - 5551219

  - 12065551219

CsVoiceRoute Cmdlet 會驗證指定的語音路線是否可以傳送指定的電話號碼。

</div>

<div>

## <a name="running-the-test"></a>執行測試

驗證語音路線路由指定電話號碼的能力有兩個步驟。 首先，您必須使用 CsVoiceRoute Cmdlet 來傳回該語音路由的實例，然後您必須使用 CsVoiceRoute Cmdlet 來驗證該路由處理目標電話號碼的能力。 例如，這個命令會驗證 RedmondVoiceRoute voice 路線是否可以傳送電話號碼2065551219：

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

請注意，電話號碼應該會輸入為您希望使用者撥打該號碼。 例如，如果您不希望使用者在撥入時包含國家/地區代碼和區功能變數代碼，請使用類似以下的語法：

`-TargetNumber "5551219"`

在這種情況下，目標號碼會留下國家/地區代碼和區號。

若要使用單一命令來測試特定目標號碼的所有語音路線，請使用如下所示的語法：

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

如需詳細資訊，請參閱 Test CsVoiceRoute Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果語音路由可以傳送目標電話號碼，CsVoiceRoute Cmdlet 只會傳回值 True：

MatchesPattern

\--------------

滿足

這表示路由可以處理與目標號碼類似的號碼。 如果語音路由無法處理目標號碼，則 Test CsVoiceRoute 會傳回值 False：

MatchesPattern

\--------------

虛假

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

測試語音路由時，「失敗」是相對的詞彙。 在這種情況下，它不表示路由是「中斷;」，而是表示路由無法處理目標號碼。 這可能是因為語音路由設定不正確。 這也可能表示路由決不是使用這種模式來處理數位。 例如，如果您不想將呼叫路由至特定路線上的其他國家/地區，可以將路由設定為拒絕包含國家/地區碼的所有電話號碼。 如果 CsVoiceRoute 在您預期傳回 True 時傳回 False，請確認您輸入的目標號碼正確無誤。 如果您這麼做，請使用類似這個的命令來查看為路線設定的 NumberPattern：

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a>請參閱


[Test-CsVoiceRoute](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

