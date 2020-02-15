---
title: Lync Server 2013： 測試協力廠商音訊會議
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
ms.openlocfilehash: d2897e085ea35e17d65719874ecf103ed7f1475d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中進行測試協力廠商音訊會議

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-11-01_


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
<td><p>測試工具</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行 Test-csaudioconferencingprovider cmdlet 的權限的 RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

音訊會議提供者是組織可利用會議服務的協力廠商公司。 除此之外，音訊會議提供者可讓使用者位於關閉網站，而未連線至公司網路或網際網路，參與會議或會議的音訊部分。 音訊會議提供者通常會提供高階服務，例如即時翻譯，轉譯，和 live 每個會議的操作員協助。

**Test-csaudioconferencingprovider** cmdlet 用來確認使用者能夠連線至他/她音訊會議提供者。 請注意，此指令程式可以執行下列兩種方式之一。 許多系統管理員會使用 CsHealthMonitoringConfiguration Cmdlet 來設定其每個登錄器集區的測試使用者。 這些測試使用者代表一組已經與綜合交易搭配使用預先設定的使用者帳戶。 （通常是這些是測試帳戶並不屬於實際使用者的帳戶）。如果測試使用者已為集區，系統管理員可以執行**Test-csaudioconferencingprovider** cmdlet，針對該集區不必指定的身分識別 （和提供的認證） 測試中所涉及的使用者帳戶。

或者，系統管理員可以執行**Test-csaudioconferencingprovider**指令程式使用的實際使用者帳戶。 如果您決定要進行測試使用的實際使用者帳戶必須提供登入名稱與該帳戶的密碼。

</div>

<div>

## <a name="running-the-test"></a>執行測試

範例 1 會檢查以查看所定義的集區 atl-cs-001.litwareinc.com 的測試使用者是否能夠連線至他/她音訊會議提供者。 此命令需要至少一個測試使用者定義的集區。 如果沒有任何測試使用者已定義為 atl-cs-001.litwareinc.com，命令將會失敗;這是因為**Test-csaudioconferencingprovider**指令程式不會知道哪些使用者可運用在測試。 如果您還沒有定義的集區的測試使用者，就必須納入 UserSipAddress 參數，並驗證與音訊會議提供者的連線時，此命令應採用的使用者帳戶的認證。

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

範例 2 所示的命令會測試特定使用者的能力 (litwareinc\\kenmyer) 連線至其音訊會議提供者。 若要這麼做，在範例中的第一個命令會使用 Get-credential 指令程式來建立包含其名稱和密碼的使用者： Ken Myer 的 Windows PowerShell 命令列介面認證物件。 (因為登入名稱 litwareinc\\kenmyer 已經包含做為參數，[Windows PowerShell 認證要求] 對話方塊只需要系統管理員輸入 Ken myer 的使用者帳戶的密碼。)產生的認證物件儲存在名為 $credential 的變數。

第二個命令會接著檢查看看是否這個使用者可以連線至其音訊會議提供者。 若要執行這項工作，Test-csaudioconferencingprovider 呼叫 cmdlet 時，以及三個參數： TargetFqdn (之登錄器集區 FQDN);UserCredential （包含 Ken Myer 的使用者認證的 Windows PowerShell 物件）;和 UserSipAddress （對應至提供的使用者認證的 SIP 位址）。

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果已正確設定音訊會議提供者，您會收到類似，具有標示為 Result 屬性的輸出**成功：**

目標 Fqdn: atl-cs-sql-001.litwareinc.com

結果： 成功

延遲： 00:00:00

錯誤訊息：

診斷：

如果指定的使用者無法登入或登出，結果會顯示為**失敗**，以及其他資訊會記錄在 [錯誤] 和 [診斷屬性：

目標 Fqdn: atl-cs-sql-001.litwareinc.com

結果： 失敗

延遲： 00:00:00

錯誤訊息： 10060 的連線嘗試失敗，因為連線對象

正常後沒有回應一段時間，或

已建立的連線失敗，因為已連線的主機

失敗回應\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]: 5061

內部的例外狀況： 的連線嘗試失敗，因為

連線對象正確後沒有回應一段

時間，或已建立的連線失敗，因為連線的主機

失敗回應

\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]: 5061

診斷：

例如，先前的輸出包含 「 連線的對象並未正確回應 「 附註這通常表示 Edge Server 的問題。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能有為何失敗的原因

以下是一些常見的原因為何**Test-csaudioconferencingprovider**可能會失敗：

  - 提供不正確的參數值。 上述範例所示，必須正確設定選用的參數或測試將會失敗。 重新執行此命令不含選擇性參數，並查看是否成功。

  - 請注意，如果**Test-csaudioconferencingprovider**指令程式所採用的使用者尚未指派音訊會議提供者，則測試會失敗。

  - 如果設定錯誤或尚未部署 Edge Server，此命令將會失敗。

</div>

</div>

<span> </span>

</div>

</div>

</div>

