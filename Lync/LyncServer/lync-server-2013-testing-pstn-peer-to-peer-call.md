---
title: Lync Server 2013：測試 PSTN 對等通話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5857e979b48dd3fee5f19016a7109eb15584b83f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193946"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a>在 Lync Server 2013 中測試 PSTN 對等通話

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsPstnPeerToPeerCall Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-CsPstnPeerToPeerCall Cmdlet 會驗證一組使用者必須透過公用交換電話網路 (PSTN) 閘道進行對等呼叫的能力。 當您呼叫 Test-CsPstnPeerToPeerCall 時，Cmdlet 會先嘗試將兩個測試使用者登入 Lync Server。 假設登入成功，則 Cmdlet 會讓使用者1嘗試透過 PSTN 閘道呼叫使用者2。 Test-CsPstnPeerToPeerCall 會使用撥號對應表、語音原則，以及指派給測試使用者的其他原則和設定設定進行呼叫。 如果測試為已計畫，指令程式會驗證使用者2是否可以接聽通話，然後從系統中登出這兩個測試帳戶。

Test-CsPstnPeerToPeerCall 會撥打實際電話，一部驗證可以進行連線，也可透過網路傳輸 DTMF 碼，以判斷媒體是否可以透過連線傳送。 此呼叫是由 Cmdlet 本身所接聽，且不需要手動結束通話。  (也就是說，任何人都必須回答，然後掛斷呼叫的電話。 ) 

</div>

<div>

## <a name="running-the-test"></a>執行測試

您可以使用一對預先設定的測試帳戶來執行 Test-CsPstnPeerToPeerCall Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何兩個已啟用 Lync Server 之使用者的帳戶。 若要使用測試帳戶執行此檢查，您只需要指定所測試之 Lync Server 集區的 FQDN。 例如：

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

若要使用實際使用者帳戶執行這項檢查，您必須建立兩個 Windows PowerShell 認證物件 (包含每個帳戶之帳戶名稱和密碼) 的物件。 當您呼叫 Test-CsPstnPeerToPeerCall 時，您必須包含這兩個帳戶的認證物件和 SIP 位址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

如需詳細資訊，請參閱[Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果指定的使用者可以完成對等通話，您會收到類似以下的輸出，其 Result 屬性標示為「**成功」：**

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00：00：06.8630376

錯誤：

診斷：

如果指定的使用者無法完成對等通話，則結果會顯示為 [失敗]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:0182361

錯誤：403，已禁止

診斷： ErrorCode = 12001、Source = atl-cs-001.litwareinc.com、

原因 = 使用者原則不含電話路由使用方式

先前的輸出表明測試失敗，因為指派給至少一個指定使用者的語音原則不包含電話使用狀況。  (電話使用方式會將語音原則與語音路由進行結合。 若未使用語音原則和對應的語音路由，則無法透過 PSTN 進行通話。 ) 

如果 Test-CsPstnPeerToPeerCall 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

包含 Verbose 參數時，Test-CsPstnPeerToPeerCall 會傳回每個動作的逐步帳戶，檢查所嘗試的每一項動作時，檢查指定的使用者登入 Lync 伺服器的能力。 例如，此輸出表示網路問題阻礙使用 PSTN 進行連線：

建立音訊影片通話至 ' sip： + 12065551219@litwareinc .com; user = phone '。

無法找到例外狀況 ' A 404 () 回應是從網路接收，而且操作失敗。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 Test-CsPstnPeerToPeerCall 可能失敗的常見原因：

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

