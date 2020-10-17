---
title: Lync Server 2013：驗證音訊/視訊會議
description: Lync Server 2013：驗證音訊/視訊會議。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad12611e928a64b934252ec21c18b98366e0912b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547199"
---
# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a>在 Lync Server 2013 中驗證音訊/視訊會議

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
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>驗證排程</p></td>
<td><p>每日</p></td>
</tr>
<tr class="odd">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="even">
<td><p>必要的權限</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsAVConference Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-CsAVConference Cmdlet 會檢查是否有兩個測試使用者可以參與音訊/視頻 (A/V) 會議。 執行 Cmdlet 時，會將兩位使用者登入系統。 在他們成功登入後，第一個使用者會建立 A/V 會議，然後等候第二位使用者加入該會議。 資料一開始短暫的交換後，就會刪除會議，而這兩個測試使用者已登出。

請注意，Test-CsAVConference 不會在兩個測試使用者之間進行實際的 A/V 會議。 相反地，指令程式會驗證這兩個使用者是否可以進行所有必要的連線，以進行這類會議。

您可以在 [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)找到此命令的進一步範例。

</div>

<div>

## <a name="running-the-test"></a>執行測試

您可以使用一對預先設定的測試帳戶來執行 Test-CsAVConference Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何兩個已啟用 Lync Server 之使用者的帳戶。 若要使用測試帳戶執行此檢查，您只需要指定所測試之 Lync Server 集區的 FQDN。 例如：

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用實際使用者帳戶執行這項檢查，您必須建立兩個 Windows PowerShell 認證物件 (包含每個帳戶之帳戶名稱和密碼) 的物件。 然後，您必須在呼叫 Test-CsAVConference 時，包含這兩個帳戶的認證物件和 SIP 位址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

如需詳細資訊，請參閱 [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果指定的使用者可以成功完成 A/V 會議，您會收到類似下列的輸出，並將 Result 屬性標示為 [ **成功]：**

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00：00：02.6841765

錯誤：

診斷：

如果使用者無法完成會議，則結果會顯示為 [失敗]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤：404，未找到

診斷： ErrorCode = 4005、Source = atl-cs-001.litwareinc.com、

原因 = 未啟用 SIP 的目的 URI 或不是

存在。

DiagnosticHeader。

例如，上一個輸出會指出測試失敗的原因是，至少有兩個使用者帳戶之一無效，原因是該帳戶不存在，或是尚未對 Lync Server 啟用該帳戶。 您可以執行類似如下的命令，確認兩個測試帳戶是否存在，以及是否已為 Lync Server 啟用：

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

如果 Test-CsAVConference 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

包含 Verbose 參數時 Test-CsAVConference 會傳回每個動作的逐步帳戶，檢查它在檢查指定的使用者是否有權參加 AV 會議時所嘗試的每一個動作。 例如，假設您的測試失敗，且您收到下列診斷：

ErrorCode = 1008，Source = accessproxy = litwareinc，Reason = 無法解析 DNS SRV 記錄

如果您使用 Verbose 參數重新執行測試，傳回的逐步資訊將會包含類似以下的輸出：

詳細：「註冊」活動已開始。

傳送註冊要求：

目標 Fqdn = atl-cs-001.litwareinc.com

使用者 Sip 位址 = sip:davidlongmire@litwareinc.com

註冊機構埠 = 5061。

已選取 Auth Type ' Trusted」。

「註冊」活動已開始。

傳送註冊要求：

目標 Fqdn = atl-cs-001.litwareinc.com

使用者 Sip 位址 = sip:kenmyer@litwareinc.com

註冊機構埠 = 5061。

已選取 Auth Type ' Trusted」。

無法註冊端點的例外狀況。 如需特定原因，請參閱 ErrorCode。 ' 工作流程期間發生

該輸出的最後一行指出使用者 sip:kenmyer@litwareinc.com 無法向 Lync Server 註冊。 這表示您應該確認 SIP 位址 sip:kenmyer@litwareinc.com 是否有效，以及是否已為 Lync Server 啟用相關聯的使用者。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 Test-CsAVConference 可能失敗的常見原因：

  - 您指定的使用者帳戶無效。 您可以執行類似如下的命令，以確認使用者帳戶是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。 若要確認是否已為 Lync Server 啟用使用者帳戶，請執行類似下列的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 屬性設定為 False，表示目前未啟用 Lync Server 的使用者。

</div>

</div>

<span> </span>

</div>

</div>

</div>

