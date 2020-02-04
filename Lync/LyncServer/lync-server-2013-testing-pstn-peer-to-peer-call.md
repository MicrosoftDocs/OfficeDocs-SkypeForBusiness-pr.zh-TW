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
ms.openlocfilehash: 9f120747eb50e8c1c52bb14d0a8883db8133022c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

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
<td><p>日常</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>需要許可權</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsPstnPeerToPeerCall Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

CsPstnPeerToPeerCall Cmdlet 會驗證一組使用者必須在公用交換電話網絡（PSTN）閘道上進行對等呼叫的能力。 當您呼叫 Test CsPstnPeerToPeerCall 時，此 Cmdlet 會先嘗試將兩個測試使用者登入 Lync Server。 假設記錄成功，則 Cmdlet 會讓使用者1嘗試使用 PSTN 閘道呼叫 user 2。 CsPstnPeerToPeerCall 將會使用撥號計畫、語音原則以及指派給測試使用者的其他原則和設定設定來撥打此通話。 如果測試是以規劃方式進行，此 Cmdlet 會驗證使用者2是否能夠接聽通話，然後從系統登出測試帳戶。

CsPstnPeerToPeerCall 會撥打實際的電話，其中一個會驗證是否可以建立連線，也可透過網路傳送 DTMF 代碼來判斷媒體是否可透過連線傳送。 呼叫是由 Cmdlet 本身所接聽，且不需要手動終止通話。 （也就是說，沒有人必須回答，然後掛斷來電的電話。）

</div>

<div>

## <a name="running-the-test"></a>執行測試

CsPstnPeerToPeerCall Cmdlet 可以使用一組預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶），或是任何已啟用 Lync Server 的任何兩個使用者的帳戶執行。 若要使用測試帳戶執行此檢查，您只需指定要測試的 Lync 伺服器池的 FQDN 即可。 例如：

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

若要使用實際的使用者帳戶執行這項檢查，您必須為每個帳戶建立兩個 Windows PowerShell 認證物件（包含帳戶名稱和密碼的物件）。 當您呼叫 Test CsPstnPeerToPeerCall 時，您必須包含這些認證物件和兩個帳戶的 SIP 位址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

如需詳細資訊，請參閱[Test CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果指定的使用者可以完成對等呼叫，您將會收到與此類似的輸出，結果屬性標示為**成功：**

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延隔時間：00：00：06.8630376

出錯

自檢

如果指定的使用者無法完成對等呼叫，則會將結果顯示為失敗，而且會在錯誤與診斷屬性中記錄其他資訊：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:0182361

錯誤：403，已禁止

診斷： ErrorCode = 12001，Source = atl-cs-001.litwareinc.com，

原因 = 使用者原則不包含電話路線使用量

由於指派給至少其中一個指定使用者的語音原則不包含電話使用方式，因此先前的輸出指出測試失敗。 （電話使用方式會將語音原則與語音路線聯繫在一起。 如果沒有語音原則及相對應的語音路線，您就無法透過 PSTN 撥打通話。

如果測試 CsPstnPeerToPeerCall 失敗，您可能會想要重新執行測試，這次包括詳細參數：

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

包含詳細參數時，當您檢查指定的使用者是否已登入 Lync Server 的功能時，測試 CsPstnPeerToPeerCall 會傳回其嘗試的每個動作的逐步帳戶。 例如，此輸出表示網路問題妨礙與 PSTN 連線：

建立音訊視頻通話至「sip： + 12065551219@litwareinc .com; 使用者 = 電話」。

從網路接收到 [404 （找不到）回應] 的例外狀況，且操作失敗。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是測試 CsPstnPeerToPeerCall 可能失敗的一些常見原因：

  - 您指定的使用者帳戶無效。 您可以執行如下的命令來確認使用者帳戶已存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前尚未啟用 Lync Server 的帳戶。 若要確認已啟用 Lync Server 的使用者帳戶，請執行如下所示的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。

  - 指派給指定使用者的語音原則沒有有效的 PSTN 使用量。 您可以使用類似以下的命令來判斷指派給使用者的語音原則：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    然後，您可以使用類似下列的命令來判斷指派給該原則的 PSTN 使用方式（如果有的話），這會檢索每個使用者語音原則 RedmondVoicePolicy 的相關資訊：
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

