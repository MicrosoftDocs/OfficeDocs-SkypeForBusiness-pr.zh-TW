---
title: Lync Server 2013：測試 PSTN 通話路由
description: Lync Server 2013：測試 PSTN 通話路由。
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
ms.openlocfilehash: da931b43176932a9b6781fa27318e83e6994548c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556269"
---
# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a>在 Lync Server 2013 中測試 PSTN 撥打電話路由

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-11-01_


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
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsInterTrunkRouting</strong> Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

**Test-CsInterTrunkRouting** Cmdlet 會驗證通話是否可以從一個 SIP 路由傳送到另一個 SIP。 若要這麼做，指令指令會獲得一個電話號碼和主幹設定。 **Test-CsInterTrunkRouting** 會向後報告指定數目的對應路由和對應 PSTN 使用方式。 請注意，只有當主幹具有符合指定電話號碼的號碼模式，且只有在主幹共用至少一個 PSTN 使用方式時，才可以在主幹之間路由傳送通話。

</div>

<div>

## <a name="running-the-test"></a>執行測試

下列所示的命令會傳回相符的路由和對應的電話使用方式，讓使用者能夠使用 Redmond 網站的主幹設定來呼叫電話號碼1-206-555-1219。

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果呼叫可以從一個 SIP 路由傳送到另一個 SIP，您會收到類似以下的輸出：

FirstMatchingRoute MatchingUsage MatchingRoutes

\------------------ ------------- --------------

RedmondRoute LocalUsage {RedmondRoute}

如果測試失敗，您會收到類似以下的輸出：

Test-CsInterTrunkRouting：無法在參數上處理引數轉換

' TrunkConfiguration '。 TrunkConfigurationsetting (參數) 無效。 指定

有效的設定 (參數) 然後再試一次。

位於：1個字元：79

\+ Test-CsInterTrunkRouting-TargetNumber "電話： + 12065551219"

\-TrunkConfiguration $t

\+

~~

\+ CategoryInfo： InvalidData： (： ) \[ Test-CsInterTrunkRouting \] ，Par

ameterBindingArgumentTransformationException

\+ FullyQualifiedErrorId： ParameterArgumentTransformationError，Microsoft。

Tc。TestOcsInterTrunkRoutingCmdlet 的管理

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 **Test-CsInterTrunkRouting** 可能失敗的常見原因：

  - 您指定的參數無效。 主幹可能尚未正確設定，且指定的目標號碼可能不正確或無效。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

