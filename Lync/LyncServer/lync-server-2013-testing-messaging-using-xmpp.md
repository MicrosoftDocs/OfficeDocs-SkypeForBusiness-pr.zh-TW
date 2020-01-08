---
title: Lync Server 2013：使用 XMPP 測試訊息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acd03cdf2a5215c980b788dbaffafc5936fe5b5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a>使用 Lync Server 2013 中的 XMPP 測試訊息

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行<strong>CsXmppIM</strong> Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

[可擴展訊息與目前狀態通訊協定（XMPP）] 是標準通訊通訊協定（根據 XML），用於透過網際網路傳送郵件。 XMPP 最初已命名為 Jabber，且受到數個網際網路訊息與通訊應用程式（例如 Google 交談和 Facebook 聊天）支援。 **CsXmppIM** Cmdlet 會確認使用者可以與 XMPP 網路上的使用者交換立即訊息。 請注意，若要讓此測試成功，您必須具備 XMPP 使用者的有效 SIP 位址，且該 SIP 位址必須位於已設定為允許 XMPP 合作夥伴的網路上。

</div>

<div>

## <a name="running-the-test"></a>執行測試

下列範例會驗證 pool atl-cs-001.litwareinc.com 的 XMPP 立即訊息功能。 只有針對 [pool atl-cs-001.litwareinc.com] 定義測試使用者時，才能使用此命令。 如果有的話，命令會判斷第一個測試使用者是否可以傳送 XMPP 立即訊息給擁有 SIP 位址 adelaney@contoso.com 的使用者。

如果沒有定義測試使用者，命令將會失敗，因為它不會知道哪個使用者登入。 如果您沒有為某個池定義測試使用者，則您必須加入 UserSipAddress 參數以及在嘗試登入時應該使用該命令的使用者認證。

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

下一個範例中所示的命令會測試特定使用者（litwareinc\\pilar）登入的能力，以傳送 XMPP 立即訊息給使用者 adelaney@contoso.com。 若要這樣做，範例中的第一個命令會使用取得認證 Cmdlet 來建立 Windows PowerShell 命令列介面身分憑證物件，該物件包含使用者 Pilar 方的名稱和密碼。 （因為登入名稱 litwareinc\\pilar 是以參數形式提供，所以 [Windows PowerShell 認證要求] 對話方塊只需要管理員輸入 pilar 方帳戶的密碼。）接著會將產生的認證物件儲存在名為 $cred 1 的變數中。

然後，第二個命令會檢查此使用者是否可以登入 [pool atl-cs-001.litwareinc.com]，並傳送 XMPP 的立即訊息。 若要執行這項工作，請使用四個參數： TargetFqdn （註冊機構池的 FQDN）來呼叫**CsXmppIm** Cmdlet;收件者（傳送訊息的使用者的 SIP 位址）;UserCredential （包含 Pilar 方使用者認證的 Windows PowerShell 物件）;與 UserSipAddress （與提供的使用者認證相對應的 SIP 位址）。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果 XMPP 立即訊息設定正確，您將會收到類似以下的輸出，結果屬性標示為**成功：**

目標 Fqdn： atl-cs-001.litwareinc.com

結果：成功

延隔時間：00：00：02.5361946

錯誤訊息：

自檢

如果指定的使用者無法使用 XMPP 立即訊息，結果就會顯示為**失敗**，而其他資訊將會記錄在錯誤與診斷屬性中：

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

無法回應10.188.116.96：5061

內部例外狀況：連接嘗試失敗，因為

已連接的參與方在一段時間後沒有正確回應

時間或已建立的連線失敗，因為已連接主機

無法回應10.188.116.96：5061

自檢

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是**測試 CsXmppIM**可能失敗的一些常見原因：

  - 提供不正確的參數值。 如果使用，必須正確設定選用的參數，否則測試將會失敗。 重新執行不含選用參數的命令，並查看是否成功。

  - 如果 XMPP 閘道設定配置錯誤或尚未部署，此命令就會失敗。

</div>

<div>

## <a name="see-also"></a>請參閱


[Set-CsXmppGatewayConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

