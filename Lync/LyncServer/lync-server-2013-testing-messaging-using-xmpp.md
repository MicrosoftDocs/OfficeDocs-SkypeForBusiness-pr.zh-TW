---
title: Lync Server 2013： 測試通訊使用 XMPP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94841a3ec17878258b26fd945aa60123ac76a9c7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a>測試通訊使用 Lync Server 2013 中的 XMPP

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
<p>當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-csxmppim</strong> cmdlet 的權限的 RBAC 角色。 若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Extensible Messaging and Presence Protocol (XMPP) 是標準的通訊協定 (XML 格式)，可用於在網際網路上傳送訊息。 XMPP 原本命名為 Jabber，並且受到數個網際網路通訊及通訊應用程式，例如 Google Talk 和 Facebook 聊天室。 **Test-csxmppim** cmdlet 會確認使用者可以與 XMPP 網路上的使用者交換立即訊息。 請注意，這項測試順利完成，您必須具備有效的 SIP 位址的 XMPP 使用者，和的 SIP 位址必須與已設定為允許的 XMPP 協力廠商的網路上。

</div>

<div>

## <a name="running-the-test"></a>執行測試

下列範例會驗證 XMPP 立即集區 atl-cs-001.litwareinc.com 的郵件功能。 這個命令將會執行只有當測試使用者所定義的集區 atl-cs-001.litwareinc.com。 如果他們有此命令會決定是否第一個測試使用者可以傳送 XMPP 立即訊息給 SIP 位址 adelaney@contoso.com 的使用者。

如果沒有定義的測試使用者，然後將會失敗命令，因為它不會知道哪些使用者身分登入。 如果您還沒有定義的集區的測試使用者，就必須納入 UserSipAddress 參數，此命令應使用時，嘗試登入使用者的認證。

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

下一個範例所示的命令會測試特定使用者的能力 (litwareinc\\pilar) 登入傳送到使用者 adelaney@contoso.com XMPP 立即訊息。 若要這麼做，在範例中的第一個命令會使用 Get-credential 指令程式來建立 Windows PowerShell 命令列介面認證物件，其中包含的名稱和密碼為 Pilar Ackerman 的使用者。 (因為登入名稱 litwareinc\\pilar 包含做為參數中，[Windows PowerShell 認證要求] 對話方塊只需要系統管理員輸入為 Pilar Ackerman 帳戶的密碼。)產生的認證物件然後儲存在名為 $cred1 變數。

此使用者是否可以登入集區 atl-cs-001.litwareinc.com 並傳送 XMPP 立即訊息，然後會檢查第二個命令。 若要執行這項工作， **Test-csxmppim** cmdlet 會呼叫，以及四個參數： TargetFqdn (之登錄器集區 FQDN);接收者 （郵件使用者的 SIP 地址所寄送至）;UserCredential （包含為 Pilar Ackerman 的使用者認證的 Windows PowerShell 物件）;和 UserSipAddress （會對應至提供的使用者認證的 SIP 位址）。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果正確設定 XMPP 立即訊息，您會收到類似，具有標示為 Result 屬性的輸出**成功：**

目標 Fqdn: atl-cs-001.litwareinc.com

結果： 成功

延遲： 00:00:02.5361946

錯誤訊息：

診斷：

如果指定的使用者無法使用 XMPP 立即訊息，結果會顯示為**失敗**，以及其他資訊會記錄在 [錯誤] 和 [診斷屬性：

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

失敗回應 10.188.116.96:5061

內部的例外狀況： 的連線嘗試失敗，因為

連線對象正確後沒有回應一段

時間，或已建立的連線失敗，因為連線的主機

失敗回應 10.188.116.96:5061

診斷：

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能有為何失敗的原因

以下是一些常見的原因為何**Test-csxmppim**可能會失敗：

  - 提供不正確的參數值。 如果使用，必須正確設定選用的參數或測試將會失敗。 重新執行此命令不含選擇性參數，並查看是否成功。

  - 如果設定錯誤或尚未部署 XMPP 閘道設定，此命令將會失敗。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Set-csxmppgatewayconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

