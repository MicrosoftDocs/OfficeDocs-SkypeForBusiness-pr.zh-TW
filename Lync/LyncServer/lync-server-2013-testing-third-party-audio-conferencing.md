---
title: Lync Server 2013：測試協力廠商音訊會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1c23f65015dd34f5efbaafa8472466394caa52c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中測試協力廠商音訊會議

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsAudioConferencingProvider Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

音訊會議提供者是協力廠商的公司，提供含會議服務的組織。 除了其他事項之外，音訊會議提供者還能讓使用者離開網站，而且未連線至公司網路或網際網路，以參與會議或會議的音訊部分。 音訊會議提供者通常會提供高端服務，例如即時翻譯、操作，以及每個會議的即時操作員協助。

**CsAudioConferencingProvider** Cmdlet 可用來驗證使用者是否能夠連線到他的音訊會議提供者。 請注意，這個 Cmdlet 可以使用兩種方法的其中一種執行。 許多系統管理員會使用 CsHealthMonitoringConfiguration Cmdlet 來針對其每個註冊機構池設定測試使用者。 這些測試使用者代表一組預配置的使用者帳戶，可與綜合交易搭配使用。 （通常，這些是測試帳戶，而不是屬於實際使用者的帳戶。）如果測試使用者是針對某個池進行設定，系統管理員可以針對該池執行**Test CsAudioConferencingProvider** Cmdlet，而不需指定測試中所涉及之使用者帳戶的身分識別（並提供認證）。

或者，管理員可以使用實際的使用者帳戶來執行**Test CsAudioConferencingProvider** Cmdlet。 如果您決定使用實際的使用者帳戶進行測試，您將需要提供該帳戶的登入名稱和密碼。

</div>

<div>

## <a name="running-the-test"></a>執行測試

範例1會檢查是否可連線至其音訊會議提供者，以查看為 [池 atl-cs-001.litwareinc.com] 定義的測試使用者是否能夠連線。 這個命令要求至少為池子定義一個測試使用者。 如果沒有為 atl-cs-001.litwareinc.com 定義測試使用者，則命令會失敗;這是因為**CsAudioConferencingProvider** Cmdlet 不會知道要在測試中使用哪個使用者。 如果您沒有為某個池定義測試使用者，則您必須在驗證與音訊會議提供者的連線時，加入 UserSipAddress 參數以及該命令應使用的使用者帳號憑證。

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

範例2所示的命令會測試特定使用者（litwareinc\\kenmyer）的功能，以連接到他的音訊會議提供者。 若要這樣做，範例中的第一個命令會使用 [取得認證 Cmdlet] 來建立 Windows PowerShell 命令列介面認證物件，包含使用者 Ken Myer 的名稱和密碼。 （因為登入名稱 litwareinc\\kenmyer 已包含為參數，所以 [Windows PowerShell 認證要求] 對話方塊只需要系統管理員輸入 Ken Myer 帳戶的密碼）。產生的認證物件會儲存在名為 $credential 的變數中。

然後，第二個命令會檢查此使用者是否可以連線到他的音訊會議提供者。 若要執行這項工作，請呼叫 CsAudioConferencingProvider Cmdlet，以及三個參數： TargetFqdn （註冊機構池的 FQDN）;UserCredential （包含 Ken Myer 使用者認證的 Windows PowerShell 物件）;與 UserSipAddress （與提供的使用者認證相對應的 SIP 位址）。

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果音訊會議提供者設定正確，您將會收到與此類似的輸出，結果屬性標示為**成功：**

目標 Fqdn： atl-sql-001.litwareinc.com

結果：成功

延遲：00:00:00

錯誤訊息：

自檢

如果指定的使用者無法登入或登出，結果就會顯示為**失敗**，而其他資訊將會記錄在錯誤與診斷屬性中：

目標 Fqdn： atl-sql-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤訊息：10060，連線嘗試失敗，因為已連接的方

在一段時間後沒有正確回應，或

已建立的連線失敗，因為連接的主機有

無法回應\[2001：4898： e8： f39e：5c9a： ad83：81b3： 9944\]：5061

內部例外狀況：連接嘗試失敗，因為

已連接的參與方在一段時間後沒有正確回應

時間或已建立的連線失敗，因為已連接主機

無法回應

\[2001：4898： e8： f39e：5c9a： ad83：81b3： 9944\]：5061

自檢

例如，前一個輸出包含「已連接的一方沒有正確回應」的筆記，這通常表示邊緣伺服器發生問題。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是**測試 CsAudioConferencingProvider**可能失敗的一些常見原因：

  - 提供不正確的參數值。 如上一個範例所示，必須正確設定選用的參數，否則測試將會失敗。 重新執行不含選用參數的命令，並查看是否成功。

  - 請注意，如果**CsAudioConferencingProvider** Cmdlet 所使用的使用者尚未獲指派音訊會議提供者，測試就會失敗。

  - 如果 Edge 伺服器未正確設定或尚未部署，此命令就會失敗。

</div>

</div>

<span> </span>

</div>

</div>

</div>

