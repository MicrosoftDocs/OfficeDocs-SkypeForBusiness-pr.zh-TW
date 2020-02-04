---
title: Lync Server 2013：測試 PSTN 手機通話路由
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
ms.openlocfilehash: 2dabe54fb2ba4df864d172015efb62ef161c77cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a>在 Lync Server 2013 中測試 PSTN 手機通話路由

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
<td><p>日常</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>需要許可權</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行<strong>CsInterTrunkRouting</strong> Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

**CsInterTrunkRouting** Cmdlet 會確認呼叫可以從一個 SIP 路由到另一個 SIP。 若要這樣做，就會將 Cmdlet 提供給電話號碼和幹線設定。 然後，**測試 CsInterTrunkRouting**接著會針對指定的數位報告返回相符的路線及相符的 PSTN 使用方式。 請注意，只有當 trunks 的數位模式符合指定的電話號碼，且只有 trunks 共用至少一個 PSTN 使用量時，才可以在 trunks 之間路由通話。

</div>

<div>

## <a name="running-the-test"></a>執行測試

下列所示的命令會傳回相符的路線及相符的電話用法，讓使用者使用雷德蒙者網站的幹線設定設定撥打電話號碼1-206-555-1219。

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果可以將呼叫從一個 SIP 路由到另一個 SIP，您會收到類似以下的輸出：

FirstMatchingRoute MatchingUsage MatchingRoutes

\------------------ ------------- --------------

RedmondRoute LocalUsage {RedmondRoute}

如果測試沒有成功，您會收到類似以下的輸出：

測試-CsInterTrunkRouting：無法處理參數上的引數轉換

'TrunkConfiguration'. 不正確 TrunkConfigurationsetting （參數）。 指定

有效的設定（參數），然後再試一次。

在第一行：1個字元：79

\+Test-CsInterTrunkRouting-TargetNumber "電話： + 12065551219"

\-TrunkConfiguration $t .。。

\+

~~

\+CategoryInfo： InvalidData：（:)\[Test-CsInterTrunkRouting\]，Par

ameterBindingArgumentTransformationException

\+FullyQualifiedErrorId： ParameterArgumentTransformationError，Microsoft. R

目錄.TestOcsInterTrunkRoutingCmdlet 的管理

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是**測試 CsInterTrunkRouting**可能失敗的一些常見原因：

  - 您指定的參數無效。 主幹可能尚未正確設定，且指定的目標號碼可能不正確或無效。

</div>

<div>

## <a name="see-also"></a>請參閱


[CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

