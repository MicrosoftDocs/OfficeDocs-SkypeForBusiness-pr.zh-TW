---
title: Lync Server 2013： 綜合交易的特殊設定指示
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
ms.openlocfilehash: c92786b50bc0b29fe5bc7f6b5b8ac978a17085aa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a>Lync Server 2013 中的綜合交易的特殊設定指示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015 年 11-16_

在現有的監看員節點上可執行大多數綜合交易；也就是說，一旦將綜合交易新增至監看員節點組態設定，監看員節點就可在其測試通過期間開始使用綜合交易。不過，並非所有綜合交易皆如此。需要特殊設定指示的綜合交易就是例外， 我們會在後續章節中討論。

<div>

## <a name="dealing-with-server-timeout-errors"></a>因應伺服器逾時錯誤

在某些情況下您可能會發現您的綜合交易的失敗伺服器逾時錯誤 （錯誤代碼 504）。 這些錯誤通常是因為防火牆問題。 綜合交易執行時下 MonitoringHost.exe 程序; 執行交易接著，MonitoringHost.exe 啟動 PowerShell.exe 程序的執行個體。 如果您的防火牆封鎖 MonitoringHost.exe 或 PowerShell.exe 綜合交易會失敗，並將會產生 504 錯誤。

若要解決此問題，您應該手動輸入的防火牆規則 MonitoringHost.exe 和 PowerShell.exe 上建立本機電腦。 這可以透過 Windows 防火牆或協力廠商本機防火牆軟體，視您的伺服器預先存在的組態而定。

如果您正在使用綜合交易主機機器與您在嘗試監視 Lync 伺服器之間的網路防火牆裝置，您應該視為主應用程式的用戶端電腦與觀察者[連接埠和通訊協定適用於 Lync Server 2013 中的內部伺服器](lync-server-2013-ports-and-protocols-for-internal-servers.md)的所有防火牆連接埠需求。

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a>資料會議綜合交易

如果您的監看員節點電腦位於周邊網路外，您可能不會是能夠執行資料會議綜合交易，除非您先停用網路服務帳戶的 Internet Explorer proxy 設定。 若要停用此服務的 Proxy 設定，請完成下列程序：

1.  在監看員節點電腦上，按一下 [**開始]**、 [**所有程式]**、 [**附屬應用程式**、 以滑鼠右鍵按一下 [**命令提示字元處**，，然後按一下**以管理員身分執行**。

2.  在主控台視窗中輸入下列命令，然後按 ENTER 鍵：
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

下列訊息會出現在命令視窗中：

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

此訊息表示您已停用網路服務帳戶的 Internet Explorer proxy 設定。

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a>Exchange 整合通訊綜合交易

Exchange 整合通訊 (UM) 綜合交易會驗證測試使用者可連線的帳戶位於 Exchange 中的語音信箱。 需使用語音信箱帳戶預先設定這些測試使用者之後，他們才可使用 Exchange UM 測試。

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a>常設聊天室綜合交易

若要使用的常設聊天室的綜合交易，系統管理員必須先建立通道，並使用它的使用者權限授與測試。 [Test-cspersistentchatmessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet 可用於適當地設定這些測試使用者：

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

必須從企業內部執行此設定工作：

  - 如果從非伺服器電腦執行，則執行 Cmdlet 的使用者須為角色型存取控制 (RBAC) 的 PersistentChatAdministrators 角色成員。

  - 如果從伺服器本身執行，則執行 Cmdlet 的使用者應為 RTCUniversalServerAdmins 群組的成員。

在上述命令中，已包含設定參數並設為 True ($True)。 如果您包含的安裝程式參數，Test-cspersistentchatmessage 會建立特殊的常設聊天室會議室，並填入該測試使用者的會議室。 這樣可確保確實有聊天室可供測試之用。 請注意，只能從前端伺服器應執行 Setup 參數。

Test-CsPersistentChatMessage 建立的聊天室僅可由系統管理員刪除。

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a>PSTN 對等通話綜合交易

[Test-cspstnpeertopeercall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall)綜合交易會驗證撥出及接聽透過公用交換的電話網路 (PSTN) 通話的能力。

若要執行此綜合交易，系統管理員必須進行下列設定：

  - 兩名測試使用者 （發話者和收件者） 啟用 Enterprise Voice。

  - 每個使用者帳戶的直接內部撥號 (DID) 號碼。

  - 語音原則和語音路由可讓撥打至受話者號碼的通話到達 PSTN 閘道。

  - 接受通話的 PSTN 閘道，與依據撥打的號碼將通話路由傳送回受話者主集區的媒體。

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a>整合連絡人存放區綜合交易

整合連絡人存放區綜合交易會驗證 Lync Server 2013 是能夠從 Microsoft Exchange Server 2013 中擷取代表使用者的連絡人。

若要使用此綜合交易，必須符合下列條件：

  - [管理伺服器對伺服器驗證 (OAuth) 與 Lync Server 2013 中的協力廠商應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)必須設定 Lync Server 2013 和 Exchange 2013 之間。

  - 測試使用者必須具備有效的 Exchange 2013 信箱。

在符合這些條件後，系統管理員可執行下列命令，以確定 SIP 位址為 kenmyer@litwareinc.com 的使用者，可從整合連絡人存放區擷取其連絡人：

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

請注意在上述命令中使用 Setup 參數使用。 如果 Setup 參數時，包含執行 Test-csunifiedcontactstore 然後指定的使用者的連絡人 (在此情況下，sip:kenmyer@litwareinc.com) 將會移至整合連絡人存放區。 （當然，如果使用者的連絡人已經整合連絡人存放區中然後他們沒有要移動。）Setup 參數通常只有一次 （第一次執行 Test-csunifiedcontactstore），並只應使用的測試使用者;亦即，將不會實際登入 Lync Server 的使用者帳戶。 測試使用者已移轉至整合連絡人存放區之後，您可以確認，可以透過呼叫 Test-csunifiedcontactstore 沒有 Setup 參數來擷取使用者的連絡人：

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a>XMPP 綜合交易

使用 XMPP (Extensible Messaging and Presence Protocol，可延伸訊息和目前狀態通訊協定) IM 綜合交易時，需配合一或多個同盟網域來設定 XMPP 功能。

若要啟用 XMPP 綜合交易，須在可路由的 XMPP 網域提供 XmppTestReceiverMailAddress 參數和使用者帳戶。 例如：

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

在這個範例中，Lync Server 2013 規則必須存在，才可將郵件路由傳送至 XMPP 閘道 litwareinc.com。

</div>

</div>

<span> </span>

</div>

</div>

</div>

