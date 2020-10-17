---
title: Lync Server 2013：測試協力廠商音訊會議
description: Lync Server 2013：測試協力廠商音訊會議。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f009d95834768d8a4e6619a79ff1f3be0a2b92bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556099"
---
# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中測試協力廠商音訊會議

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsAudioConferencingProvider Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

音訊會議提供者是協力廠商公司，為組織提供會議服務。 除了其他事項之外，音訊會議提供者也可讓使用者進入離站網站，而不是連線至公司網路或網際網路，以參與會議或會議的音訊部分。 音訊會議提供者通常會提供高端服務，例如即時翻譯、會議和即時的每一會議操作員協助。

**Test-CsAudioConferencingProvider** Cmdlet 是用來確認使用者是否可以連線到其音訊會議提供者。 請注意，此 Cmdlet 可以以兩種方式之一執行。 許多系統管理員會使用 CsHealthMonitoringConfiguration Cmdlet 來設定其每個登錄器集區的測試使用者。 這些測試使用者代表一組已預先設定為搭配綜合交易的使用者帳戶。  (通常是測試帳戶，而不是屬於實際使用者的帳戶。 ) 如果針對集區設定測試使用者，系統管理員可以對該集區執行 **Test-CsAudioConferencingProvider** Cmdlet，而不需要指定 (的身分識別，並為) 所涉及的使用者帳戶提供認證。

管理員也可以使用實際的使用者帳戶來執行 **Test-CsAudioConferencingProvider** Cmdlet。 如果您決定使用實際的使用者帳戶進行測試，則需要提供該帳戶的登入名稱和密碼。

</div>

<div>

## <a name="running-the-test"></a>執行測試

範例1會檢查是否為集區 atl-cs-001.litwareinc.com 定義的測試使用者能夠連線到其音訊會議提供者。 這個命令要求為集區至少定義一個測試使用者。 若尚未定義 atl-cs-001.litwareinc.com 的測試使用者，命令將會失敗。這是因為 **Test-CsAudioConferencingProvider** Cmdlet 不會知道要在測試中使用哪個使用者。 若尚未定義集區的測試使用者，您必須加入 UserSipAddress 參數，以及在使用音訊會議提供者驗證連線時，應使用該命令的使用者帳號憑證。

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

範例2所示的命令會測試特定使用者 (litwareinc \\ kenmyer) 的功能，以連接到他的音訊會議提供者。 為做到這一點，範例中的第一個命令會使用 Get-Credential Cmdlet 來建立 Windows PowerShell 命令列介面認證物件，該物件包含使用者 Ken Myer 的名稱和密碼。  (因為登入名稱 litwareinc \\ kenmyer 已包含為參數，所以 [Windows PowerShell 認證要求] 對話方塊只要求系統管理員輸入 Ken Myer 帳戶的密碼。 ) 產生的認證物件會儲存在名為 $credential 的變數中。

然後，第二個命令會檢查此使用者是否可以連接到其音訊會議提供者。 若要執行此工作，會呼叫 Test-CsAudioConferencingProvider Cmdlet 及三個參數： TargetFqdn (註冊機構集區的 FQDN) ;UserCredential (包含 Ken Myer 之使用者認證) 的 Windows PowerShell 物件。和 UserSipAddress (與所提供使用者認證) 相對應的 SIP 位址。

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果已正確設定音訊會議提供者，則會收到類似下列的輸出，並將 Result 屬性標示為 [ **成功]：**

目標 Fqdn： atl-sql-001.litwareinc.com

結果：成功

延遲：00:00:00

錯誤訊息：

診斷：

如果指定的使用者無法登入或登出，結果將會顯示為 **失敗**，而且會在錯誤和診斷屬性中記錄其他資訊：

目標 Fqdn： atl-sql-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤訊息：10060，連接嘗試失敗，因為連接的方

在一段時間後沒有正確回應，或

已建立連線失敗，因為連接的主機已

無法回應 \[ 2001：4898： e8： f39e：5c9a： ad83：81b3： 9944 \] ：5061

內部例外狀況：連接嘗試失敗，因為

在一段時間後，連接的通訊錄未正確回應

時間或已建立的連線失敗，因為連接的主機

回應失敗

\[2001：4898： e8： f39e：5c9a： ad83：81b3： 9944 \] ：5061

診斷：

例如，上一個輸出包含的附注「連接的團體沒有正確回應」，這通常表示 Edge Server 發生問題。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 **Test-CsAudioConferencingProvider** 可能失敗的常見原因：

  - 提供的參數值不正確。 如先前的範例所示，必須正確設定選用參數，否則測試將會失敗。 請重新執行不含選用參數的命令，然後查看是否成功。

  - 請注意，如果 **Test-CsAudioConferencingProvider** Cmdlet 所採用的使用者尚未獲指派音訊會議提供者，則測試會失敗。

  - 如果 Edge Server 設定不當或尚未部署，此命令將會失敗。

</div>

</div>

<span> </span>

</div>

</div>

</div>

