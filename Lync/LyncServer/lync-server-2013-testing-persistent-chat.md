---
title: Lync Server 2013：測試持久聊天
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4f805984382388fd44904db746d818decb8871a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a>在 Lync Server 2013 中測試持續式聊天

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-11-03_


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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行<strong>CsPersistentChatMessage</strong> Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

**Test CsPersistentChatMessage** Cmdlet 會確認一組測試使用者可以使用持續聊天服務來交換郵件。 若要這樣做，此 Cmdlet 會將這兩個使用者記錄在 Lync Server 2013、將使用者連線至持續聊天室、交換一對訊息，然後退出聊天室並登出兩個使用者。 請注意，如果您未建立任何聊天室，或者沒有為兩個測試使用者帳戶指派永久聊天原則，且該策略可讓使用者存取持續聊天服務，則呼叫此 Cmdlet 將會失敗。

</div>

<div>

## <a name="running-the-test"></a>執行測試

下列範例中所示的命令會測試一對使用者（litwareinc\\pilar 和 litwareinc\\kenmyer）的功能，以登入 Lync Server 2013，然後使用持續聊天服務進行 exchange 郵件。 若要這樣做，範例中的第一個命令會使用**取得認證**Cmdlet 來建立 Windows PowerShell 命令列介面身分憑證物件，該物件包含使用者 Pilar 方的名稱和密碼。 （因為登入名稱（litwareinc\\pilar）是以參數的形式提供，所以 [Windows PowerShell 認證要求] 對話方塊只需要管理員輸入 pilar 方帳戶的密碼。）接著會將產生的認證物件儲存在名為 $cred 1 的變數中。 第二個命令會執行相同的動作，這次會傳回 Ken Myer 帳戶的認證物件。

使用認證物件時，第三個命令會判斷這兩個使用者是否可以使用持續聊天來登入 Lync Server 2013 和 exchange 郵件。 若要執行這項工作，請使用下列參數來呼叫**CsPersistentChatMessage** Cmdlet： TargetFqdn （註冊機構池的 FQDN）;SenderSipAddress （第一個測試使用者的 SIP 位址）;SenderCredential （包含此相同使用者認證的 Windows PowerShell 物件）;ReceiverSipAddress （其他測試使用者的 SIP 位址）;與 ReceiverCredential （包含其他測試使用者認證的 Windows PowerShell 物件）。

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果指定的使用者有有效的位置原則，您將會收到類似這樣的輸出，結果屬性標示為**成功**：

目標 Fqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00:00:00

錯誤訊息：

自檢

如果指定的使用者無法使用 Persistent 聊天服務來交換郵件，則會將結果顯示為**失敗**，而且會在錯誤與診斷屬性中記錄其他資訊：

警告：無法讀取指定之完全限定的註冊機構埠號碼

網功能變數名稱稱（FQDN）。 使用預設的註冊器埠號碼。 引發

InvalidOperationException：在拓撲中找不到相符的群集。

的

TryRetri 的 SyntheticTransactions。 SipSyntheticTransaction

eveRegistrarPortFromTopology （Int32& registrarPortNumber）

目標 Fqdn： atl-cs-001.litwareinc.com

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

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是**測試 CsPersistentChatMessage**可能失敗的一些常見原因：

  - 提供不正確的參數值。 所需的測試帳戶可能不存在，或已正確建立。

  - 可能發生網路問題，造成測試超時的意外延遲。

</div>

<div>

## <a name="see-also"></a>請參閱


[授與 CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[New-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[Set-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

