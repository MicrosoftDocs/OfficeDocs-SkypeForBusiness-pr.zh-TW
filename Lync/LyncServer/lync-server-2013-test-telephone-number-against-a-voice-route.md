---
title: Lync Server 2013：對照語音路由測試電話號碼
description: Lync Server 2013：對照語音路由測試電話號碼。
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
ms.openlocfilehash: 789f4a538a992a72abf61f4c1fbdb98370f2e643
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563389"
---
# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a>在 Lync Server 2013 中對照語音路由測試電話號碼

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsVoiceRoute Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

語音路由可搭配語音原則搭配使用，以協助將 Enterprise Voice 通話路由傳送至 PSTN 網路。 每個語音路由都包含一個正則運算式 (數位模式) ，用以識別將透過指定之語音路由路由傳送的電話號碼：此路由將可以處理符合此正則運算式的任何電話號碼。 例如，語音路由可能有一個正則運算式，可讓它處理任何10位數的數位。 這表示路由可以處理如下的電話號碼：

  - 2065551219

路由將無法處理下列兩個數字中的任何一個，兩者都沒有10位數：

  - 5551219

  - 12065551219

Test-CsVoiceRoute Cmdlet 會驗證指定的語音路由是否可以路由指定的電話號碼。

</div>

<div>

## <a name="running-the-test"></a>執行測試

驗證語音路由路由指定之電話號碼的功能是兩步驟的處理常式。 首先，您必須使用 Get-CsVoiceRoute Cmdlet 傳回該語音路由的實例，然後必須使用 Test-CsVoiceRoute Cmdlet 來驗證該路由的功能，以處理目標電話號碼。 例如，此命令會驗證 RedmondVoiceRoute voice 路由是否可以路由傳送電話號碼2065551219：

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

請注意，應輸入的電話號碼應為您期望的使用者撥打該號碼。 例如，如果您不想讓使用者在撥號時包含國家代碼和區號，請使用類似下列的語法：

`-TargetNumber "5551219"`

在此情況下，目標號碼會同時留下國家/地區代碼和區號。

若要使用單一命令來測試指定目標號碼的所有語音路由，請使用下列語法：

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

如需詳細資訊，請參閱 Test-CsVoiceRoute Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果語音路由可路由傳送目標電話號碼 Test-CsVoiceRoute Cmdlet 只會傳回值 True：

MatchesPattern

\--------------

是

這表示路由可以處理類似于目標號碼的數位。 如果語音路由無法處理目標號碼，則 Test-CsVoiceRoute 會傳回值 False：

MatchesPattern

\--------------

False

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

測試語音路由時，"失敗" 為相對字詞。 在此情況下，並不表示路由是以「中斷」，而是表示路由無法處理目標號碼。 這可能是因為語音路由設定不正確。 也可能表示路由絕對不打算使用此模式來處理數位。 例如，如果您不想要透過指定的路由將來電路由傳送至其他國家/地區，該路由可能會設定為拒絕所有包含國家/地區代碼的電話號碼。 如果 Test-CsVoiceRoute 傳回 False，當您期望它傳回 True 時，請確認您已正確輸入目標號碼。 如果您這麼做，請使用類似下列的命令，以查看為路由設定的 NumberPattern：

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a>另請參閱


[測試-Get-csvoiceroute](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

