---
title: Lync Server 2013：使用 XMPP 測試通訊
description: Lync Server 2013：使用 XMPP 測試通訊。
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
ms.openlocfilehash: 06faeae0a6104351f9102de31c76b2424a140deb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556299"
---
# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a>在 Lync Server 2013 中使用 XMPP 測試郵件

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
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsXmppIM</strong> Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

Extensible Messaging and Presence Protocol (XMPP) 是標準的通訊協定 (XML 格式)，可用於在網際網路上傳送訊息。 XMPP 最初命名為 Jabber) ，且由數個網際網路郵件和通訊應用程式（如 Google 交談及 Facebook 聊天）所支援。 **Test-CsXmppIM** Cmdlet 會驗證使用者是否可以與 XMPP 網路上的使用者交換立即訊息。 請注意，若要讓此測試成功，您必須具備 XMPP 使用者的有效 SIP 位址，而且該 SIP 位址必須位於設定為「允許的 XMPP」夥伴的網路上。

</div>

<div>

## <a name="running-the-test"></a>執行測試

下列範例會驗證集區 atl-cs-001.litwareinc.com 的 XMPP 立即訊息功能。 只有針對集區 atl-cs-001.litwareinc.com 定義測試使用者時，此命令才會運作。 如果有的話，此命令會判斷第一個測試使用者是否可以傳送 XMPP 立即訊息給具有 SIP 位址 adelaney@contoso.com 的使用者。

若未定義測試使用者，命令將會失敗，因為它不會知道哪個使用者登入。 若尚未定義集區的測試使用者，則必須包括 UserSipAddress 參數，以及在嘗試登入時應使用命令的使用者認證。

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

下一個範例中所示的命令會測試特定使用者 (litwareinc pilar 的功能 \\ 。) 登入以傳送 XMPP 立即訊息給使用者 adelaney@contoso.com。 為做到這一點，範例中的第一個命令會使用 Get-Credential Cmdlet 來建立 Windows PowerShell 命令列介面身分介面，該物件包含使用者 Pilar Ackerman 的名稱和密碼。  (因為登入名稱 litwareinc \\ pilar 已包含為參數，所以 Windows PowerShell 認證要求] 對話方塊只要求系統管理員輸入 Pilar Ackerman 帳戶的密碼。 ) 所產生的身分憑證物件會儲存在名為 $cred 1 的變數中。

然後，第二個命令會檢查此使用者是否可以登入集區 atl-cs-001.litwareinc.com 並傳送 XMPP 立即訊息。 若要執行此工作， **CsXmppIm** 指令程式會與四個參數一起呼叫： TargetFqdn (註冊區集區的 FQDN) ;收件者 (要傳送郵件給) 的使用者 SIP 位址。UserCredential (包含 Pilar Ackerman 使用者認證) 的 Windows PowerShell 物件。和 UserSipAddress (與所提供使用者認證) 相對應的 SIP 位址。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果 XMPP 立即訊息設定正確，您會收到類似以下的輸出，並將 Result 屬性標示為 **成功：**

目標 Fqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00：00：02.5361946

錯誤訊息：

診斷：

如果指定的使用者無法使用 XMPP 立即訊息，結果將會顯示為 [ **失敗**]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：

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

無法回應10.188.116.96：5061

內部例外狀況：連接嘗試失敗，因為

在一段時間後，連接的通訊錄未正確回應

時間或已建立的連線失敗，因為連接的主機

無法回應10.188.116.96：5061

診斷：

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 **Test-CsXmppIM** 可能失敗的常見原因：

  - 提供的參數值不正確。 如果使用，必須正確設定選用參數，否則測試將會失敗。 請重新執行不含選用參數的命令，然後查看是否成功。

  - 如果 XMPP 閘道設定設定不當或尚未部署，此命令將會失敗。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Set-CsXmppGatewayConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

