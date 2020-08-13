---
title: Lync Server 2013：測試撥號對應表
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
ms.openlocfilehash: a83f8058dd761386329c3c0bc58a50c4aef7bdb2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a>在 Lync Server 2013 中測試撥號對應表

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
<td><p>每日</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsDialPlan Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-CsDialPlan Cmdlet 可讓您查看將撥號對應表套用至指定電話號碼的結果。 撥號對應表提供的資訊（例如，如何套用正規化規則），讓企業語音使用者撥打電話是必要的。 根據撥打的號碼和撥號對應表，此 Cmdlet 將會確認套用撥號對應表內的哪個正規化規則，以及翻譯後的號碼將是什麼。

您可以使用此 Cmdlet 來疑難排解數位翻譯的問題，或驗證如何套用規則的特定數位。

</div>

<div>

## <a name="running-the-test"></a>執行測試

Test-CsDialPlan 指令指令需要您執行兩項作業。 首先，您必須取得所測試之撥號對應表的實例;可以使用 Get-CsDialPlan Cmdlet 來完成。 其次，您必須指定必須正規化的電話號碼。 電話號碼所用的格式應符合使用者撥打/輸入的號碼。 例如，此命令會檢索撥號對應表的實例，RedmondDialPlan，並檢查電話號碼12065551219是否可以正規化：

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

如果您有一個會自動在此範例中新增 country 代碼 (的正規化規則，則會有1個) 和區號 (206) ，您可能想要檢查電話號碼5551219，如下所示：

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

如需詳細資訊，請參閱[Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

Test-CsDialPlan 與許多 Lync Server 測試 Cmdlet 不同，因為它只會間接指出測試是否成功或失敗。 使用 Test-CsDialPlan 時，您不會收到類似如下的輸出結果，並以明確標示的結果：

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00：00：06.8630376

錯誤：

診斷：

相反地，如果 Test-CsDialPlan 成功，則會收到可順利翻譯和使用指定電話號碼之正規化規則的相關資訊：

TranslatedNumber： + 12065551219

MatchingRule： Description =;Pattern = ^ (\\ d (11) # B3 $;轉譯 = + $ 1;

Name = Prefix 全部;IsInternalExtension = False

如果 Test-CsDialPlan 失敗 (也就是說，如果撥號對應表沒有可轉譯指定電話號碼的正規化規則) ，您只會收到「空白」輸出，如下所示：

TranslatedNumber :

MatchingRule :

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 Test-CsDialPlan 可能失敗的常見原因：

  - 指定電話號碼時，您可能使用了不正確的格式。 撥號對應表包含正常化規則，可讓 Lync Server 轉譯使用者撥打或輸入的電話號碼。 因此，您的撥號對應表應該會有符合使用者可能會撥號的數量的正規化規則。 例如，如果使用者可能撥打國家/地區代碼、區號，然後輸入電話號碼，則表示您的撥號對應表應具有標準化規則來處理電話號碼，如下所示：
    
    12065551219
    
    不過，如果您輸入不正確的電話號碼 (例如，保留最後一位數) ，Test-CsDialPlan 將會失敗。 這不是因為撥號對應表有問題，但您輸入的電話號碼無法轉譯。

</div>

</div>

<span> </span>

</div>

</div>

</div>

