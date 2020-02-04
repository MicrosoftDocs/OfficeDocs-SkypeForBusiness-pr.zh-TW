---
title: Lync Server 2013：測試撥號計畫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e0e39b88d7b6c90a55d236038d03cc4cc717319
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a>在 Lync Server 2013 中測試撥號方案

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-06-05_


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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsDialPlan Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

CsDialPlan Cmdlet 可讓您查看將撥號方案套用到指定電話號碼的結果。 撥號方案提供資訊（例如如何套用正常化規則），而必要的做法是讓企業語音使用者撥打電話。 考慮撥入號碼和撥號方案，這個 Cmdlet 會確認將套用撥號計畫中的哪個正常化規則，以及翻譯後的數位。

您可以使用這個 Cmdlet 來排查數位翻譯的問題，或驗證如何將規則套用至特定的數位。

</div>

<div>

## <a name="running-the-test"></a>執行測試

CsDialPlan Cmdlet 需要您執行兩項操作。 首先，您必須取得正在測試的撥號方案實例;使用 CsDialPlan Cmdlet 即可完成。 其次，您必須指定必須正常化的電話號碼。 電話號碼所用的格式，必須符合使用者撥打電話/輸入的數位。 例如，這個命令會檢索撥號計畫的實例、RedmondDialPlan，並檢查電話號碼12065551219是否可以正常化：

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

如果您有會自動新增國家/地區代碼（在此範例中為1）和區號（206）的正常化規則，您可能會想要檢查電話號碼5551219，如下所示：

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

如需詳細資訊，請參閱[Test CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

Test-CsDialPlan 不同于許多 Lync Server 測試 Cmdlet，因為它只會間接指示測試是否成功或失敗。 使用 Test CsDialPlan 時，您不會收到類似以下所示的輸出結果，並清楚標示結果：

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延隔時間：00：00：06.8630376

出錯

自檢

相反地，如果 Test CsDialPlan 成功，則您會收到可成功翻譯並使用指定電話號碼的正常化規則資訊：

TranslatedNumber： + 12065551219

MatchingRule： Description =;Pattern = ^ （\\d （11）） $;譯文 = + $ 1;

Name = Prefix All;IsInternalExtension = False

如果 CsDialPlan 測試失敗（也就是，如果撥號方案沒有可翻譯指定之電話號碼的正常化規則），您就會收到如下所示的「空白」輸出：

TranslatedNumber :

MatchingRule :

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是測試 CsDialPlan 可能失敗的一些常見原因：

  - 指定電話號碼時，可能使用了不正確的格式。 撥號方案包括啟用 Lync Server 來轉譯使用者撥打電話或輸入之電話號碼的正常化規則。 因此，您的撥號方案應該有符合使用者可能撥號的數位的正常化規則。 例如，如果使用者可能先撥打國家/地區代碼、區號，然後撥打電話號碼本身，那表示您的撥號方案應該有一個標準化規則來處理電話號碼，例如：
    
    12065551219
    
    不過，如果您輸入不正確的電話號碼（例如，離開最後一個數位），則 Test-CsDialPlan 將會失敗。 這不是因為撥號方案有問題，但因為您輸入的是無法轉譯的電話號碼。

</div>

</div>

<span> </span>

</div>

</div>

</div>

