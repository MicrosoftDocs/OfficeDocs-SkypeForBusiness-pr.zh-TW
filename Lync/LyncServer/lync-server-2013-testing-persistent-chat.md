---
title: Lync Server 2013：測試持續性聊天
description: Lync Server 2013：測試持續性聊天。
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
ms.openlocfilehash: a8b1dc4eef1870f1287dacdc1852ab1e24edd169
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556279"
---
# <a name="testing-persistent-chat-in-lync-server-2013"></a>在 Lync Server 2013 中測試持續性聊天

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<td><p>每日</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsPersistentChatMessage</strong> Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

**Test-CsPersistentChatMessage** Cmdlet 會驗證一對測試使用者是否可以使用 Persistent Chat service 來交換郵件。 為做到這一點，指令指令會將兩位使用者記錄到 Lync Server 2013，將使用者連線到 persistent 聊天室，交換一對郵件，然後結束聊天室，並登出兩位使用者。 請注意，如果您未建立任何聊天室或沒有為這兩個測試使用者帳戶指派可存取 Persistent Chat service 的持續性聊天原則，則呼叫此 Cmdlet 將會失敗。

</div>

<div>

## <a name="running-the-test"></a>執行測試

下列範例所示的命令會測試一組使用者 (litwareinc \\ pilar and litwareinc \\ kenmyer) 登入 Lync Server 2013，然後使用 Persistent Chat service 進行 exchange 郵件的功能。 為做到這一點，範例中的第一個命令會使用 **Get-Credential** Cmdlet 來建立 Windows PowerShell 命令列介面身分介面，該物件包含使用者 Pilar Ackerman 的名稱和密碼。  (由於登入名稱 litwareinc \\ pilar 已包含為參數，所以 [Windows PowerShell 認證要求] 對話方塊只要求系統管理員輸入 Pilar Ackerman 帳戶的密碼。 ) 產生的認證物件會儲存在名為 $cred 1 的變數中。 第二個命令會執行相同的程序，但這次會傳回 Ken Myer 帳戶的認證物件。

使用 credential 物件，第三個命令會判斷是否這兩位使用者可以使用持續聊天登入 Lync Server 2013 和 exchange 郵件。 若要執行這項工作， **Test-CsPersistentChatMessage** Cmdlet 會使用下列參數呼叫： TargetFqdn (註冊機構集區的 FQDN) ;SenderSipAddress (第一個測試使用者的 SIP 位址) ;SenderCredential (包含此相同使用者之認證的 Windows PowerShell 物件) ;ReceiverSipAddress (其他測試使用者) 的 SIP 位址;和 ReceiverCredential (包含其他測試使用者) 之認證的 Windows PowerShell 物件。

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果指定的使用者有有效的位置原則，則會收到類似下列的輸出，並將 Result 屬性標示為 [ **成功**]：

目標 Fqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00:00:00

錯誤訊息：

診斷：

如果指定的使用者無法使用 Persistent Chat service 來交換郵件，則結果會顯示為 [ **失敗**]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：

警告：無法讀取指定之完全限定的註冊器通訊埠號碼

功能變數名稱 (FQDN) 。 使用預設的註冊器埠號碼。 例外：

InvalidOperationException：在拓撲中找不到相符的群集。

在

SipSyntheticTransaction TryRetri （SyntheticTransactions）

eveRegistrarPortFromTopology (Int32& registrarPortNumber) 

目標 Fqdn： atl-cs-001.litwareinc.com

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

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 **Test-CsPersistentChatMessage** 可能失敗的常見原因：

  - 提供的參數值不正確。 必要的測試帳戶可能不存在，或已正確建立。

  - 可能發生網路問題，造成測試超時，造成未預期的延遲。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Grant-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[New-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[Set-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

