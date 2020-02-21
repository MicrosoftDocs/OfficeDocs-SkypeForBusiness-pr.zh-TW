---
title: Lync Server 2013： 測試對語音路由的電話號碼
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
ms.openlocfilehash: 5476d47d0aac550d048e35e617d6d342084ccd75
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a>針對 Lync Server 2013 中的語音路由測試電話號碼

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
<p>當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有可執行此測試 CsVoiceRoute cmdlet 的權限的 RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

語音路由配合語音原則，以協助將 Enterprise Voice 通話路由傳送至 PSTN 網路。 每個語音路由包含規則運算式 （數字模式），識別會路由傳送到特定的語音路由的電話號碼： 路由能夠處理任何符合此規則運算式的電話號碼。 例如，語音路由可能需要規則運算式，可讓它來處理任何 10 位數的數字。 這表示路由就能夠處理的電話號碼，例如此：

  - 2065551219

路由會無法未處理下列兩個數字，其中一種有 10 位數：

  - 5551219

  - 12065551219

測試 CsVoiceRoute cmdlet 會驗證指定的語音路由是否可以路由傳送的指定的電話號碼。

</div>

<div>

## <a name="running-the-test"></a>執行測試

確認語音路由至路由的能力的指定的電話號碼是雙步驟程序。 您必須先使用 Get-csvoiceroute cmdlet 可傳回該語音路由] 中，執行個體，然後您必須使用測試 CsVoiceRoute cmdlet 來確認該路由能夠處理的目標電話號碼。 例如，此命令會驗證 RedmondVoiceRoute 語音路由是否可以路由傳送的電話號碼 2065551219:

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

請注意如您預期使用者撥打該號碼應該輸入的電話號碼。 例如，如果您未預期設為包含國碼/地區碼和區域的程式碼時撥打的使用者，然後使用類似如下的語法：

`-TargetNumber "5551219"`

在此情況下，目標號碼保留延展國碼/地區碼及區域碼。

若要使用單一命令，以測試對指定的目標數字的所有語音路由，使用語法如下所示：

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

如需詳細資訊，請參閱 < 測試 CsVoiceRoute cmdlet 的說明 」 文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果語音路由可以路由傳送的目標電話號碼測試 CsVoiceRoute 指令程式只會傳回值為 True:

MatchesPattern

\--------------

True

這表示該路由可以處理類似的目標號碼的數字。 語音路由時無法處理的目標號碼，然後測試 CsVoiceRoute 傳回的值為 False:

MatchesPattern

\--------------

False

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能有為何失敗的原因

在測試語音路由時，「 失敗 」 是相對的字詞。 在此情況下，它並不表示路由以某種方式將 「 中斷 」; 相反地，這只是路由無法處理的目標號碼。 可能是因為語音路由未正確設定。 它也可能表示路由已永不設計用來處理使用這種模式的數字。 例如，如果您不想以其他國家/地區的電話路由透過指定路由至該路由可能會設定為拒絕所有電話號碼，包含國碼/地區碼。 如果測試 CsVoiceRoute 會傳回 False，當您預期它傳回 True，請確認您正確輸入中的目標數字。 如果您這樣做，然後使用類似以下的命令來檢視 NumberPattern 設定路由：

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a>另請參閱


[測試 CsVoiceRoute](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

