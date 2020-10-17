---
title: Lync Server 2013：測試 PSTN 通話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abc46703118d27533ac2afd2b4b448ad9516bdd6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503970"
---
# <a name="testing-pstn-phone-call-in-lync-server-2013"></a>在 Lync Server 2013 中測試 PSTN 通話

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsRegistration Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-CsPstnOutboundCall Cmdlet 會測試使用者撥打位於 PSTN 之電話號碼的能力。 當您執行 Test-CsPstnOutboundCall 時，指令 Cmdlet 會先嘗試將測試使用者記錄到 Lync Server。 如果登入成功，則 Cmdlet 會嘗試撥打跨越 PSTN 閘道的電話。 這會使用撥號對應表、語音原則，以及指派給測試帳戶的其他原則和設定進行通話。 當接聽來電時，Cmdlet 會透過網路傳送雙音多重頻率 (DTMF) 碼，以驗證媒體的連線能力。

進行測試時，Test-CsPstnOutboundCall 會撥打實際的電話：目標電話會振鈴，必須回答才能成功測試。 此通話也必須由系統管理員手動結束。

</div>

<div>

## <a name="running-the-test"></a>執行測試

您可以使用預先設定的測試帳戶執行 Test-CsPstnOutboundCall Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何啟用 Lync Server 之使用者的帳戶。 若要使用測試帳戶執行這項檢查，您只需要指定所測試之 Lync 伺服器集區的 FQDN，以及呼叫 PSTN 電話號碼。 例如：

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

若要使用實際使用者帳戶執行這種檢查，您必須先建立 Windows PowerShell 身分憑證物件，其中包含帳戶名稱和密碼。 接著，當您呼叫 Test-CsPstnOutboundCall 時，必須包含該認證物件和指派給該帳戶的 SIP 位址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

如需詳細資訊，請參閱 [Test-CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果指定的使用者可以撥打電話，且接聽來電，您會收到類似以下的輸出，並將 Result 屬性標示為 [ **成功]：**

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00：00：06.8630376

錯誤：

診斷：

如果指定的使用者無法撥打來電或來電未接聽，則結果會顯示為 [失敗]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:0987365

錯誤：403，已禁止

診斷： ErrorCode = 12001，Source = atl-ws-01 = cs，Reason = User

原則不含電話路由使用方式

先前的輸出規定測試失敗，因為指派給指定使用者的語音原則並未包含電話使用狀況。  (電話使用方式會將語音原則與語音路由進行結合。 若未使用語音原則和對應的語音路由，則無法透過 PSTN 撥打通話。 ) 

如果 Test-CsPstnOutboundCall 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

包含 Verbose 參數時，Test-CsPstnOutboundCall 會傳回每個動作的逐步帳戶，檢查所嘗試的每一項動作時，檢查指定的使用者登入 Lync 伺服器的能力。 例如，此輸出表示網路問題阻礙使用 PSTN 進行連線：

建立音訊影片通話至 ' sip： + 12065551219@litwareinc .com; user = phone '。

無法找到例外狀況 ' A 404 () 回應是從網路接收，而且操作失敗。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 Test-CsPstnOutboundCall 可能失敗的常見原因：

  - 您指定的使用者帳戶無效。 您可以執行類似如下的命令，以確認使用者帳戶是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。 若要確認是否已為 Lync Server 啟用使用者帳戶，請執行類似下列的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 屬性設定為 False，表示目前未啟用 Lync Server 的使用者。

  - 指派給指定使用者的語音原則沒有有效的 PSTN 使用方式。 您可以使用類似下列的命令，判斷指派給使用者的語音原則：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    然後，您可以使用類似下列的命令，在指派給該原則的任何) 中判斷 PSTN 使用方式 (，該命令會檢索每一使用者語音原則 RedmondVoicePolicy 的相關資訊：
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

