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
ms.openlocfilehash: 8095b4b0bb6aa4e6920d291c3fde3885ae6bfb03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-in-lync-server-2013"></a>在 Lync Server 2013 中測試 PSTN 電話通話

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsRegistration Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

CsPstnOutboundCall Cmdlet 會測試使用者撥打電話給 PSTN 上電話號碼的功能。 當您執行 Test CsPstnOutboundCall 時，此 Cmdlet 會先嘗試將測試使用者記錄到 Lync Server。 如果登入成功，則 Cmdlet 會嘗試撥打 PSTN 閘道的電話撥打電話。 這個電話將會使用撥號計畫、語音原則，以及指派給測試帳戶的其他原則和設定來撥打。 接聽來電時，Cmdlet 會在網路上傳送雙音調多頻率（DTMF）碼，以驗證媒體連線性。

進行測試時，測試 CsPstnOutboundCall 將撥打實際電話： [目標電話] 會響鈴，而且必須接聽才能成功測試。 系統管理員也必須手動結束此通話。

</div>

<div>

## <a name="running-the-test"></a>執行測試

CsPstnOutboundCall Cmdlet 可以使用預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶）或任何已啟用 Lync Server 的使用者帳戶執行。 若要使用測試帳戶執行這項檢查，您只需指定要測試的 Lync 伺服器池 FQDN，並呼叫 PSTN 電話號碼。 例如：

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

若要使用實際的使用者帳戶執行此檢查，您必須先建立包含帳戶名稱和密碼的 Windows PowerShell 認證物件。 當您呼叫 Test CsPstnOutboundCall 時，您必須包含該認證物件以及指派給該帳戶的 SIP 位址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

如需詳細資訊，請參閱[Test CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果指定的使用者可以進行通話，而且接聽通話，您會收到類似以下的輸出，結果屬性標示為**成功：**

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延隔時間：00：00：06.8630376

出錯

自檢

如果指定的使用者無法撥打電話或通話沒有回應，則結果會顯示為失敗，而其他資訊將會記錄在錯誤與診斷屬性中：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:0987365

錯誤：403，已禁止

診斷： ErrorCode = 12001，Source = atl-cs-001. litwareinc，原因 = User

原則不包含電話路線使用量

由於指派給指定使用者的語音原則不包含電話使用方式，因此先前的輸出指出測試失敗。 （電話使用方式會將語音原則與語音路線聯繫在一起。 若沒有語音原則和相對應的語音路線，就無法透過 PSTN 撥打通話。

如果測試 CsPstnOutboundCall 失敗，您可能會想要重新執行測試，這次包括詳細參數：

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

包含詳細參數時，當您檢查指定的使用者是否已登入 Lync Server 的功能時，測試 CsPstnOutboundCall 會傳回其嘗試的每個動作的逐步帳戶。 例如，此輸出表示網路問題妨礙與 PSTN 連線：

建立音訊視頻通話至「sip： + 12065551219@litwareinc .com; 使用者 = 電話」。

從網路接收到 [404 （找不到）回應] 的例外狀況，且操作失敗。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是測試 CsPstnOutboundCall 可能失敗的一些常見原因：

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

