---
title: Lync Server 2013：驗證音訊/視訊會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0e608f0c765c4dd552645320ec947c7e8a54ac4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a>在 Lync Server 2013 中驗證音訊/視訊會議

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
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>驗證排程</p></td>
<td><p>日常</p></td>
</tr>
<tr class="odd">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="even">
<td><p>需要許可權</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsAVConference Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test CsAVConference Cmdlet 會檢查兩個測試使用者是否可以參與音訊/視頻（A/V）會議。 當 Cmdlet 執行時，兩個使用者會登入系統。 成功登入之後，第一位使用者會建立 A/V 會議，然後等候第二位使用者加入該會議。 在短暫的資料交換之後，該會議即會刪除，而這兩個測試使用者就會登入。

請注意，測試 CsAVConference 不會在兩個測試使用者之間執行實際的 A/V 會議。 相反地，此 Cmdlet 會確認這兩個使用者可以建立進行這類會議所需的所有連線。

您可以在[Test CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)上找到這個命令的進一步範例。

</div>

<div>

## <a name="running-the-test"></a>執行測試

CsAVConference Cmdlet 可以使用一組預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶），或是任何已啟用 Lync Server 的任何兩個使用者的帳戶執行。 若要使用測試帳戶執行此檢查，您只需指定要測試的 Lync 伺服器池的 FQDN 即可。 例如：

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用實際的使用者帳戶執行這項檢查，您必須為每個帳戶建立兩個 Windows PowerShell 認證物件（包含帳戶名稱和密碼的物件）。 然後，在呼叫 Test CsAVConference 時，您必須包含這些認證物件和兩個帳戶的 SIP 位址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

如需詳細資訊，請參閱[Test CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果指定的使用者能夠成功完成 A/V 會議，您將會收到與此類似的輸出，結果屬性標示為**成功：**

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延隔時間：00：00：02.6841765

出錯

自檢

如果使用者無法完成會議，結果就會顯示為失敗，而其他資訊將會記錄在錯誤與診斷屬性中：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤：404，找不到

診斷： ErrorCode = 4005，Source = atl-cs-001.litwareinc.com，

原因 = 無法針對 SIP 啟用目的 URI，或無法

有.

DiagnosticHeader 中的 [Rtc]

例如，由於帳戶不存在，或帳戶尚未啟用 Lync Server，所以先前的輸出指出測試失敗的原因是這兩個使用者帳戶中至少有一個帳戶無效。 您可以執行如下所示的命令，以驗證兩個測試帳戶是否存在，以及是否已啟用 Lync Server 的功能：

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

如果測試 CsAVConference 失敗，您可能會想要重新執行測試，這次包括詳細參數：

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

在包含詳細參數的情況下，CsAVConference 會傳回其在檢查指定使用者要參與 AV 會議的能力時所嘗試的每個動作的逐步帳戶。 例如，假設您的測試失敗，而且您收到下列診斷：

ErrorCode = 1008，來源 = accessproxy，原因 = 無法解析 DNS SRV 記錄

如果您使用詳細的參數重新執行測試，傳回的逐步資訊將會包含類似以下的輸出：

詳細：「註冊」活動已開始。

傳送註冊要求：

目標 Fqdn = atl-cs-001.litwareinc.com

使用者 Sip 位址 = sip:davidlongmire@litwareinc.com

註冊機構埠 = 5061。

已選取 [已信任] 驗證類型。

「註冊」活動已開始。

傳送註冊要求：

目標 Fqdn = atl-cs-001.litwareinc.com

使用者 Sip 位址 = sip:kenmyer@litwareinc.com

註冊機構埠 = 5061。

已選取 [已信任] 驗證類型。

無法註冊端點的例外狀況。 請參閱錯誤的特定原因。 工作流程期間發生

該輸出中的最後一行表示使用者 sip:kenmyer@litwareinc.com 無法使用 Lync Server 進行註冊。 這表示您應該驗證 SIP 位址 sip:kenmyer@litwareinc.com 是否有效，以及是否已針對 Lync Server 啟用相關聯的使用者。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是測試 CsAVConference 可能失敗的一些常見原因：

  - 您指定的使用者帳戶無效。 您可以執行如下的命令來確認使用者帳戶已存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前尚未啟用 Lync Server 的帳戶。 若要確認已啟用 Lync Server 的使用者帳戶，請執行如下所示的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。

</div>

</div>

<span> </span>

</div>

</div>

</div>

