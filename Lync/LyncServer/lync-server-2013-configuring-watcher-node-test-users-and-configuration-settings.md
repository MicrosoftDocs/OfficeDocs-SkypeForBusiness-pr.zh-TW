---
title: 設定監視器節點測試使用者和設定設定
description: 設定監視器節點測試使用者和設定設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e39a35d3db6ed80c715c706f4b5766e4b684e39e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542179"
---
# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中設定監視節點測試使用者和設定設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-29_

在設定將充當監視節點的電腦之後，您必須：

1.  建立這些觀察器節點要使用的測試帳戶。 如果您使用 Negotiate 驗證方法，您也必須使用 [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) Cmdlet 來啟用這些測試帳戶，以在監看員節點上使用。

2.  更新監視節點的設定。

本節涵蓋：

  - 設定測試使用者帳戶

  - 使用預設的綜合交易，設定基本的監看員節點

  - 設定擴充測試

  - 新增及移除綜合交易

  - 查看及測試監視節點設定

<div>

## <a name="configuring-test-user-accounts"></a>設定測試使用者帳戶

測試使用者不需要表示實際人員，但必須是有效的 Active Directory 網域服務帳戶;此外，必須對 Lync Server 2013 啟用這些帳戶，他們必須具有有效的 SIP 位址，而且應為 Enterprise Voice (啟用這些帳戶，才能使用 Test-CsPstnPeerToPeerCall 綜合交易) 。 如果您使用 TrustedServer 驗證方法，則您需要做的全部工作是確定這些帳戶都存在，且已依照這裡所指定的方式進行設定。 您應為每個要測試的集區至少指派三個測試使用者。

如果您使用 Negotiate 驗證方法，您也必須使用 **Set-CsTestUserCredential** Cmdlet 和 Lync Server 管理命令介面，讓這些測試帳戶能夠搭配綜合交易。 您可以執行類似如下的命令來執行此動作。  (這些命令會假設已建立三個 Active Directory 使用者帳戶，且已啟用這些帳戶的 Lync Server 2013。 ) ：

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

請注意，您不僅必須包含 SIP 位址，也必須包含使用者名稱和密碼。 如果您未加入密碼 Set-CsTestUserCredential 會提示您輸入該資訊。 您可以使用 \\ 如上所示的功能變數名稱使用者名稱格式指定使用者名稱，或使用 format user name@domain name; 例如：

    -UserName "watcher3@litwareinc.com"

若要確認已建立測試使用者認證，請在 Lync Server 管理命令介面中執行下列命令：

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

針對每位使用者應傳回類似以下的資訊：

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>使用預設的綜合交易，設定基本的監看員節點

在建立測試使用者之後，您可以使用類似下列的命令來建立監看員節點：

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

這個命令會建立新的監看員節點，使用預設設定，並執行預設的綜合交易集合。 新的監看員節點也會使用 test 使用者 watcher1@litwareinc.com、watcher2@litwareinc.com 及 watcher3@litwareinc.com。 如果監看員節點使用的是 TrustedServer 驗證，則三個測試帳戶可以是為 Active Directory 和 Lync Server 啟用的任何有效使用者帳戶。 如果監看員節點使用 Negotiate 驗證方法，您也必須使用 **Set-CsTestUserCredential** Cmdlet 來啟用監看員節點的使用者帳戶。

</div>

<div>

## <a name="configuring-extended-tests"></a>設定擴充測試

如果您想要啟用公用交換電話網路 (PSTN 測試) ，它會驗證與公用交換電話網路的連線，您必須在設定監看員節點時執行一些其他設定。 首先，您必須將測試使用者與 PSTN 測試類型產生關聯。 若要這麼做，請在 Lync Server 管理命令介面中執行類似以下的命令：

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

請注意，此命令的結果必須儲存在變數中。 在此範例中，這是一個名為 $pstnTest 的變數。

此時，您可以使用 **New-CsWatcherNodeConfiguration** Cmdlet，將 $pstnTest) 中儲存的測試類型 (關聯至 Lync Server 2013 集區。 例如，下列命令會為集區 atl-cs-001.litwareinc.com 建立新的監看員節點設定，加入先前建立的三個測試使用者，也新增 PSTN 測試類型：

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

請注意，如果您尚未在監看員節點電腦上安裝 Lync Server 核心檔案和 RTCLocal 資料庫，上述命令將會失敗。

若要測試多種語音原則，您必須使用 **New-CsExtendedTest** Cmdlet，為每個原則建立擴充測試。 指派給此測試的使用者應以所需的語音原則加以設定。 然後，您可以使用類似下列的命令，將延伸的測試傳遞至 **New-CsWatcherNodeConfiguration** Cmdlet：

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

如果不使用 [測試] 參數呼叫 New-CsWatcherNodeConfiguration，表示只有預設的綜合交易 (，且會為新的監看員節點啟用指定的延伸綜合交易) 。 這表示觀察程式節點會測試下列元件：

  - 註冊

  - 我

  - GroupIM

  - P2PAV (對等音訊/視頻會話) 

  - AvConference (音訊/會議) 

  - 目前狀態

  - ABS (通訊錄服務) 

  - ABWQ (通訊錄 web 服務) 

  - PSTN (PSTN 閘道通話，指定為延伸測試。 預設會停用 PSTN。 在此情況下會啟用測試，只是因為命令已使用 ExtendedTests 參數啟用 PSTN。 ) 

這也意味著預設不會測試下列元件：

  - AVEdgeConnectivity

  - MCXP2PIM (行動裝置立即訊息) 

  - ExumConnectivity (Exchange 整合通訊) 

  - JoinLauncher

  - PersistentChatMessage

  - DataConference

  - XmppIM

  - UnifiedContactStore

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a>新增及移除綜合交易

在設定了監看員節點之後，您可以使用 **Set-CsWatcherNodeConfiguration** Cmdlet 來新增或移除節點中的綜合交易。 例如，若要將 PersistentChatMessage 測試新增至監看員節點，請使用 Add 方法及類似如下的命令：

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

若要新增多個測試，您可以使用逗號分隔測試名稱。 例如：

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

請注意，如果其中一或多個測試 (例如，DataConference) 已經在監看員節點上啟用，就會發生錯誤。 在此情況下，您會收到類似下列的錯誤訊息：

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

發生此錯誤時，將不會套用任何變更。 在移除重複的測試時，應重新執行該命令。

若要移除來自觀察者節點的綜合交易，請使用 Remove 方法，而不要使用 Add 方法。 例如，下列命令會從監看員節點中移除 ABWQ 測試：

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

您也可以使用 Replace 方法，將所有目前啟用的測試取代為一或多個新的測試。 例如，如果您只想要在監看員節點上執行 IM 測試，您可以使用下列命令來設定該測試：

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

當您執行上述命令時，將會停用指定的監看員節點上的所有綜合交易，但 IM 除外。

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a>查看及測試監視節點設定

如果您想要查看已指派給觀察者節點的測試，請使用類似下列的命令：

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

上述命令會根據指派給節點的綜合交易，傳回類似以下的資訊：

    Registration
    IM
    GroupIM
    P2PAV
    AvConference
    Presence
    PersistentChatMessage
    DataConference

<div>


> [!TIP]
> 若要依字母順序查看綜合交易，請改為使用此命令：<BR>Get-CsWatcherNodeConfiguration –身分識別 "atl-cs-001.litwareinc.com" |Select-Object –ExpandProperty 測試 |Sort-Object



</div>

若要確認已建立監看員節點，請在 Lync Server 管理命令介面內輸入下列命令：

    Get-CsWatcherNodeConfiguration

您將會收到類似以下的資訊：

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

若要確認是否已正確設定觀察程式節點，請在 Lync Server 管理命令介面中輸入下列命令：

    Test-CsWatcherNodeConfiguration

上述命令會測試您部署中的每個監看員節點，並告訴您資訊，例如：

  - 已安裝必要的註冊器角色。

  - 當您執行 Set-CsWatcherNodeConfiguration 時，會為您建立必要的登錄機碼。

  - 您的伺服器正在執行正確版本的 Lync Server。

  - 您的埠已正確設定。

  - 您指派的測試使用者具備必要的認證。

</div>

</div>

<span> </span>

</div>

</div>

</div>

