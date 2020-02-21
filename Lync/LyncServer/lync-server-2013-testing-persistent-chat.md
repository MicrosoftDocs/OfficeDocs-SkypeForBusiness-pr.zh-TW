---
title: Lync Server 2013： 測試常設聊天室
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2177e4fce4d32bb2dc6c82e1f3fecae367eb2543
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a>在 Lync Server 2013 中進行測試常設聊天室

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-11-03_


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
<p>當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-cspersistentchatmessage</strong> cmdlet 的權限的 RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>說明

**Test-cspersistentchatmessage** cmdlet 會驗證測試使用者的一組可以交換郵件使用的常設聊天室服務。 若要這麼做，指令程式登入 Lync Server 2013 的兩個使用者、 使用者連到常設聊天室、 交換郵件的一組，然後結束聊天室並登出兩位使用者。 如果您沒有建立任何聊天室，或是如果兩個測試使用者帳戶未被指派的常設聊天室原則，可讓其存取常設聊天室服務，請注意，此 cmdlet 會呼叫將會失敗。

</div>

<div>

## <a name="running-the-test"></a>執行測試

下列範例所示的命令會測試的一組使用者的能力 (litwareinc\\pilar 和 litwareinc\\kenmyer) 登入 Lync Server 2013，然後 exchange 郵件使用的常設聊天室服務。 若要這麼做，在範例中的第一個命令會使用**Get-credential**指令程式來建立 Windows PowerShell 命令列介面認證物件，其中包含的名稱和密碼為 Pilar Ackerman 的使用者。 (因為登入名稱中，litwareinc\\pilar，包含做為參數，[Windows PowerShell 認證要求] 對話方塊只需要系統管理員輸入為 Pilar Ackerman 帳戶的密碼。)產生的認證物件然後儲存在名為 $cred1 變數。 第二個命令會執行相同的程序，但這次會傳回 Ken Myer 帳戶的認證物件。

在手中的認證物件，第三個命令會決定這些兩個使用者是否可以登入 Lync Server 2013 和 exchange 使用常設聊天室的郵件。 若要執行這項工作， **Test-cspersistentchatmessage** cmdlet 會呼叫使用下列參數： TargetFqdn (之登錄器集區 FQDN);SenderSipAddress （第一個測試使用者的 SIP 位址）;與 SenderCredential （包含這個相同的使用者認證的 Windows PowerShell 物件）;ReceiverSipAddress （其他測試使用者的 SIP 位址）;並與 ReceiverCredential （包含在其他的測試使用者的認證的 Windows PowerShell 物件）。

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果指定的使用者具有有效的位置原則，您會收到類似，具有標示為 [**成功**結果屬性的輸出：

目標 Fqdn: atl-cs-001.litwareinc.com

結果： 成功

延遲： 00:00:00

錯誤訊息：

診斷：

如果指定的使用者不能交換使用的常設聊天室服務的訊息，結果會顯示為**失敗**，以及其他資訊會記錄在 [錯誤] 和 [診斷屬性：

警告： 無法讀取登錄器的連接埠號碼指定完整

網域名稱 (FQDN)。 使用預設登錄器連接埠號碼。 例外狀況：

System.InvalidOperationException： 拓撲中找不到比對叢集。

在

Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

目標 Fqdn: atl-cs-001.litwareinc.com

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

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能有為何失敗的原因

以下是一些常見的原因為何**Test-cspersistentchatmessage**可能會失敗：

  - 提供不正確的參數值。 需要的測試帳戶可能不存在或已正確建立。

  - 可能有網路問題造成未預期的延遲的逾時測試。

</div>

<div>

## <a name="see-also"></a>另請參閱


[授與 CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[New-cspersistentchatpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[Set-cspersistentchatpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

