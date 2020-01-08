---
title: Lync Server 2013：測試對等音訊/視頻通話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43fc4da7619dcc4cfd88417b52543dc23c447883
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a>在 Lync Server 2013 中測試對等音訊/視頻通話

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsP2PAV Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-CsP2PAV 是用來判斷一組測試使用者是否可以參與對等 A/V 交談。 若要測試這種情況，請將兩位使用者登入 Lync Server，然後啟動 Cmdlet。 假設兩次登錄成功，則第一個使用者接著邀請第二位使用者加入 A/V 通話。 第二個使用者接受通話，兩個使用者之間的連線就會得到測試，然後通話就會結束，並從系統登出測試使用者。

測試 CsP2PAV 並不會實際執行 A/V 通話。 不會在測試使用者之間交換多媒體資訊。 相反地，此 Cmdlet 只會驗證是否可以建立適當的連線，以及兩位使用者可以進行這類通話。

如需詳細資訊，請參閱[Test CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) Cmdlet 的說明文件。

</div>

<div>

## <a name="running-the-test"></a>執行測試

CsP2PAV Cmdlet 可以使用一組預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶），或是任何已啟用 Lync Server 的任何兩個使用者的帳戶執行。 若要使用測試帳戶執行此檢查，您只需指定要測試的 Lync 伺服器池的 FQDN 即可。 例如：

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用實際的使用者帳戶執行這項檢查，您必須為每個帳戶建立兩個 Lync Server 認證物件（包含帳戶名稱和密碼的物件）。 當您呼叫 Test CsP2PAV 時，您必須包含這些認證物件和兩個帳戶的 SIP 位址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果兩個測試使用者可以完成對等 A/V 通話，您就會收到類似以下的輸出，並將 Result 屬性標示為**成功：**

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延隔時間：00：00：06.8630376

出錯

自檢

如果測試使用者無法完成通話，結果就會顯示為失敗，而其他資訊將會記錄在錯誤與診斷屬性中：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤：480，暫時無法使用

診斷： ErrorCode = 15030，Source = atl-cs-001. litwareinc，原因 = 失敗

傳送到 Exchange Server

DiagnosticHeader 中的 [Rtc]

例如，由於無法連絡 Microsoft Exchange Server，所以先前的輸出指出測試失敗。 此錯誤訊息通常表示 Exchange 整合訊息設定的問題。

如果測試 CsP2PAV 失敗，您可能會想要重新執行測試，這次包括詳細參數：

Test-CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com"-詳細資訊

在包含詳細參數時，測試 CsP2PAV 會傳回其在檢查指定使用者登入 Lync Server 的能力時所嘗試的每個動作的逐步帳戶。 例如，假設您的測試由於下列診斷而失敗：

ErrorCode = 6003，Source = atl-ws-01 = cs-001. litwareinc，Reason = 不支援的對話方塊要求

如果您重新執行 Test CsP2PAV 並包含 Verbose 參數，就會收到類似以下的輸出：

詳細：「註冊」活動已開始。

傳送註冊要求：

目標 Fqdn = atl-cs-011.litwareinc.com

使用者 Sip 位址 = sip:kenmyer@litwareinc.com

註冊機構埠 = 5062。

已選取 Auth 類型 ' IWA」。

無法註冊端點的例外狀況。 請參閱錯誤的特定原因。 在工作流程 SyntheticTransactions STP2PAVWorkflow 執行期間發生。

雖然這可能不會立即明顯，但如果您仔細檢查輸出，您會看到指定的註冊埠（埠5062）不正確。 進而導致測試失敗。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是測試 CsP2PAV 可能失敗的一些常見原因：

  - 您指定的使用者帳戶無效。 您可以執行如下的命令來確認使用者帳戶已存在：
    
    Move-csuser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前尚未啟用 Lync Server 的帳戶。 若要確認已啟用 Lync Server 的使用者帳戶，請執行如下所示的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。

</div>

</div>

<span> </span>

</div>

</div>

</div>

