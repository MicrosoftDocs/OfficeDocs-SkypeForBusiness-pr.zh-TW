---
title: Lync Server 2013：測試使用者目前狀態發佈和訂閱
description: Lync Server 2013：測試使用者目前狀態發佈和訂閱。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user presence publishing and subscribing
ms:assetid: 27694c71-8e63-4aa4-b49f-fa06ccb81949
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743832(v=OCS.15)
ms:contentKeyID: 63969587
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90913f270fbd034ca4d2ea7cf3b93c255fc95c66
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541849"
---
# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a>在 Lync Server 2013 中測試使用者的狀態發佈和訂閱

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsPresence Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Test-CsPresence 是用來判斷一組測試使用者是否可以登入 Lync Server，然後再 exchange 顯示狀態資訊。 為達此目的，此 Cmdlet 會先將兩個使用者登入系統。 如果兩者都登入成功，則第一個測試使用者會要求接收第二個使用者的目前狀態資訊。 第二個使用者會發行此資訊，而 Test-CsPresence 會驗證該資訊已成功傳輸給第一個使用者。 在 exchange 顯示狀態資訊之後，這兩個測試使用者便會從 Lync Server 登出。

</div>

<div>

## <a name="running-the-test"></a>執行測試

您可以使用一對預先設定的測試帳戶來執行 Test-CsPresence Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何兩個已啟用 Lync Server 之使用者的帳戶。 若要使用測試帳戶執行此檢查，您只需要指定所測試之 Lync Server 集區的 FQDN。 例如：

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用實際使用者帳戶執行這項檢查，您必須建立兩個 Windows PowerShell 認證物件 (包含每個帳戶之帳戶名稱和密碼) 的物件。 當您呼叫 Test-CsPresence 時，您必須包含這兩個帳戶的認證物件和 SIP 位址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

如需詳細資訊，請參閱 [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) Cmdlet 的說明文件。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果指定的使用者可以交換顯示狀態資訊，則會收到類似以下的輸出，其 Result 屬性標示為 [ **成功]：**

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00：00：06.3280315

錯誤：

診斷：

如果兩位使用者無法交換顯示狀態資訊，則結果會顯示為 [失敗]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：

TargetFqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤：404，未找到

診斷： ErrorCode = 4005、Source = atl-cs-001.litwareinc.com、

原因 = 未啟用 SIP 的目的 URI 或不是

存在。

DiagnosticHeader。

例如，由於至少有兩個使用者帳戶的其中一個無效，所以先前的輸出會指出測試失敗：帳戶不存在，或尚未對 Lync Server 啟用。 您可以執行類似如下的命令，確認帳戶是否存在，並判斷是否已啟用 Lync Server。

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

如果 Test-CsPresence 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

包含 Verbose 參數時，Test-CsPresence 會傳回每個動作的逐步帳戶，檢查所嘗試的每一項動作時，檢查指定的使用者登入 Lync 伺服器的能力。 例如：

註冊要求命中不明

' Register ' activity 在 ' 0.0345791 ' 秒內完成。

' SelfSubscribeActivity ' 活動已開始。

' SelfSubscribeActivity ' activity 在 ' 0.0041174 ' 秒內完成。

' SubscribePresence ' 活動已開始。

' SubscribePresence ' activity 在 ' 0.0038764 ' 秒內完成。

' PublishPresence ' 活動已開始。

在25秒內未收到例外狀況通知。 ' 發生 ruing 工作流程 STPresenceWorkflow 執行 SyntheticTransactions。

在25秒內未收到目前狀態通知這一事實可能表示網路問題阻礙交換資訊。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 Test-CsPresence 可能失敗的常見原因：

  - 您指定了錯誤的使用者帳戶。 您可以執行類似如下的命令，以確認使用者帳戶是否存在：
    
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

