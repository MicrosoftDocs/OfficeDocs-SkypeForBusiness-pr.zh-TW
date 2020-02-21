---
title: Lync Server 2013： 測試 PSTN 電話路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call routing
ms:assetid: 301dd44d-03e9-41cd-9722-54e00365aa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727302(v=OCS.15)
ms:contentKeyID: 63969598
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abdb6796139ddc4be2b8ea24aa9bfeb19f745373
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a>測試 Lync Server 2013 中的 PSTN 電話路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-11-01_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>驗證排程</p></td>
<td><p>每日</p></td>
</tr>
<tr class="even">
<td><p>測試工具</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-csintertrunkrouting</strong> cmdlet 的權限的 RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

**Test-csintertrunkrouting** cmdlet 會驗證通話可以路由從一個 SIP，到另一個。 若要這麼做，指令程式提供的電話號碼及主幹組態。 **Test-csintertrunkrouting**會然後回報相符的路由和相符的 PSTN 使用方式指定數目。 請注意，可以來路由傳送通話主幹間僅有主幹的數字模式符合指定的電話號碼，且只有在主幹共用至少一個 PSTN 使用方式。

</div>

<div>

## <a name="running-the-test"></a>執行測試

如下所示的命令會傳回相符的路由和相符的電話使用方式，讓使用者能夠呼叫的主幹組態設定用於 Redmond 網站的電話號碼 1-206-555-1219。

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果呼叫可以從一個 SIP 路由傳送至另一個，您會收到類似如下的輸出：

FirstMatchingRoute MatchingUsage MatchingRoutes

\------------------ ------------- --------------

RedmondRoute LocalUsage {RedmondRoute}

如果測試失敗，您會收到類似如下的輸出：

Test-csintertrunkrouting： 無法處理上參數的引數轉換

' TrunkConfiguration'。 無效的 TrunkConfigurationsetting （參數）。 指定

有效的設定 （參數），然後再試一次。

在線條： 1 char: 79

\+Test-csintertrunkrouting TargetNumber"tel: + 12065551219 」

\-TrunkConfiguration $t...]

\+

~~

\+CategoryInfo: InvalidData: （:）\[Test-csintertrunkrouting\]、 Par

ameterBindingArgumentTransformationException

\+FullyQualifiedErrorId: ParameterArgumentTransformationError,Microsoft.R

繁體中文。Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能有為何失敗的原因

以下是一些常見的原因為何**Test-csintertrunkrouting**可能會失敗：

  - 您指定無效的參數。 主幹可能尚未被設定不正確，指定的目標數字可能不正確或不正確。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Get-cstrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[Get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

