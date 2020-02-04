---
title: Lync Server 2013：綜合交易的特殊設定指示
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a15177a3c4548b235bf01a10274168e4a830fad3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a>Lync Server 2013 中的綜合交易的特殊設定指示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-11-16_

大多數的綜合交易可以在觀察程式節點上自行執行，也就是說，只要綜合交易已新增至 [觀察程式節點設定]，觀察程式節點就可以在其測試階段中開始使用綜合交易。 不過，所有的綜合交易都不是如此。 例外狀況：需要特殊設定指示的綜合交易，請參閱下列各節。

<div>

## <a name="dealing-with-server-timeout-errors"></a>處理伺服器逾時錯誤

在某些情況下，您可能會發現綜合交易失敗發生伺服器逾時錯誤（錯誤碼504）。 這些錯誤通常是由防火牆問題所造成。 當執行綜合交易時，該事務會在 MonitoringHost 處理常式下執行;接著，MonitoringHost 會啟動 PowerShell .exe 程式的實例。 如果您的防火牆封鎖 MonitoringHost 或 ngen.exe，則綜合交易將會失敗，並會產生504錯誤。

若要解決此問題，您應該在本機電腦上手動建立 MonitoringHost 和 ngen.exe 的入站防火牆規則。 這可以透過 Windows 防火牆或協力廠商的本機防火牆軟體來完成，這要視伺服器預先設定的設定而定。

如果您是在綜合交易主機電腦和您嘗試監視的 Lync 伺服器之間使用網路防火牆裝置，您應該將主機視為用戶端電腦，並[在 Lync Server 2013 中觀察內部伺服器的埠和通訊協定的](lync-server-2013-ports-and-protocols-for-internal-servers.md)所有防火牆埠需求。

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a>資料會議綜合交易

如果您的系統監控程式節點電腦位於周邊網路之外，則您可能無法執行資料會議綜合交易，除非您首先停用網路服務帳戶的 Internet Explorer proxy 設定。 若要停用此服務的 proxy 設定，請完成下列程式：

1.  在觀察程式節點電腦上，按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**附件**]，以滑鼠右鍵按一下**命令提示**字元，然後按一下 [**以系統管理員身分執行**]。

2.  在主控台視窗中，輸入下列命令，然後按 ENTER：
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

下列訊息會出現在命令視窗中：

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

此訊息表示您已停用網路服務帳戶的 Internet Explorer proxy 設定。

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a>Exchange 整合訊息合成交易

Exchange 整合通訊（UM）綜合交易會確認測試使用者可以連線至位於 Exchange 中的語音信箱帳戶。 這些測試使用者將需要使用語音信箱帳戶預先設定，才能使用 Exchange UM 測試。

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a>持續聊天綜合交易

若要使用持續性聊天綜合交易，系統管理員必須先建立一個通道，然後給予測試使用者使用該通道的許可權。 [Test CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) Cmdlet 可用來適當地設定這些測試使用者：

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

此設定任務必須從企業內部執行：

  - 如果從 nonserver 電腦執行，則執行 Cmdlet 的使用者必須是以角色為基礎的存取控制（RBAC）的 PersistentChatAdministrators 角色的成員。

  - 如果從伺服器本身執行，執行 Cmdlet 的使用者應該是 RTCUniversalServerAdmins 群組的成員。

在上述命令中，會包含 Setup 參數並將其設定為 True （$True）。 如果您包含 Setup 參數，CsPersistentChatMessage 將會建立一個特殊的持續聊天室，並將該會議室填入測試使用者。 這有助於確保實際有聊天室可供測試之用。 請注意，只能從前端伺服器執行 Setup 參數。

只有系統管理員才能刪除由測試 CsPersistentChatMessage 所建立的聊天室。

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a>PSTN 對等呼叫綜合交易記錄

[Test CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall)綜合交易會確認透過公用交換電話網絡（PSTN）來撥打和接聽通話的功能。

若要執行此綜合交易，系統管理員必須設定：

  - 針對企業語音啟用的兩個測試使用者（來電者和接收人）。

  - 針對每個使用者帳戶直接撥打（已有）號碼。

  - 語音原則和語音路由，可以呼叫接收器的號碼來到達 PSTN 閘道。

  - 可接受呼叫的 PSTN 閘道，以及根據所撥打的號碼，將呼叫傳送到收件者的主池中的媒介。

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a>整合連絡人商店綜合交易

[整合連絡人商店] 綜合交易記錄會確認 Lync Server 2013 可以代表使用者從 Microsoft Exchange Server 2013 取得連絡人。

若要使用這個綜合交易，必須符合下列條件：

  - [在 lync server 2013 中管理伺服器間驗證（OAuth）與合作夥伴應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)，必須在 lync server 2013 和 Exchange 2013 之間設定。

  - 測試使用者必須具備有效的 Exchange 2013 信箱。

在符合這些條件之後，系統管理員可以執行下列命令，以驗證擁有 SIP 位址 kenmyer@litwareinc.com 的使用者可以從整合連絡人存放區中取得連絡人：

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

請注意，在前面的命令中使用的 Setup 參數。 如果執行 CsUnifiedContactStore 時包含 Setup 參數，則指定使用者的連絡人（在此案例中為 sip:kenmyer@litwareinc.com）將會移至 [整合連絡人] 存放區。 （當然，如果使用者的連絡人已在 [整合連絡人] 存放區中，則不需要移動它們。）Setup 參數通常只會使用一次（第一次執行測試 CsUnifiedContactStore），而且只應與測試使用者搭配使用;也就是說，使用者帳戶永遠不會登入 Lync Server。 當您的測試使用者已遷移至 [整合連絡人存放區] 之後，您可以在不使用 Setup 參數的情況下呼叫 Test CsUnifiedContactStore，以驗證使用者的連絡人是否可以檢索。

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a>XMPP 綜合交易記錄

XMPP （可擴展訊息和目前狀態通訊協定） IM 綜合交易需要使用一或多個聯盟網域來設定 XMPP 功能。

若要啟用 XMPP 綜合交易，必須在可路由的 XMPP 網域中，以使用者帳戶提供 XmppTestReceiverMailAddress 參數。 例如：

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

在這個範例中，Lync Server 2013 規則必須存在，以將 litwareinc.com 的訊息路由至 XMPP 閘道。

</div>

</div>

<span> </span>

</div>

</div>

</div>

