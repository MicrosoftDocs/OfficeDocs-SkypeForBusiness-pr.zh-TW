---
title: 設定監看員節點測試使用者及組態設定
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
ms.openlocfilehash: 78d52e6a7eb36ce0f000a9986480d62692d3a33d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中設定監看員節點測試使用者與組態設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-07-29_

設定將作為監看員節點的電腦之後, 您必須：

1.  建立這些監看員節點所使用的測試帳戶。 如果您使用的交涉驗證方法，您也必須使用[Set-cstestusercredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15))指令程式來啟用這些測試監看員節點上使用的帳戶。

2.  更新監看員節點組態設定。

本章節將說明：

  - 設定測試使用者帳戶

  - 使用預設綜合交易設定基本監看員節點

  - 設定擴充的測試

  - 新增與移除綜合交易

  - 檢視與測試監看員節點組態

<div>

## <a name="configuring-test-user-accounts"></a>設定測試使用者帳戶

測試使用者不需要來代表實際的人員，但它們必須是有效的 Active Directory 網域服務帳戶。此外，這些帳戶必須啟用 Lync Server 2013，他們必須具備有效的 SIP 位址，和他們應該啟用 Enterprise voice （以使用 Test-cspstnpeertopeercall 綜合交易）。 如果您使用 TrustedServer 驗證方法，那麼您只需要是確定這些帳戶存在，而且已設定為在這裡指定。 您應該指定您想要測試每個集區，至少有三個測試使用者。

如果您使用的交涉驗證方法，您也必須使用**Set-cstestusercredential** cmdlet 和 Lync Server 管理命令介面來啟用這些測試帳戶來使用綜合交易。 您可以執行類似下列的命令來執行這項操作。 （這些命令假設已經已建立的三個 Active Directory 使用者帳戶，以及這些帳戶，已啟用 Lync Server 2013。）：

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

請注意，您必須包含不只的 SIP 位址，但也的使用者名稱和密碼。 如果未加上密碼 Set-cstestusercredential 會提示您輸入該資訊。 可以使用的網域名稱指定的使用者名稱\\使用者名稱 」 格式顯示上方，或藉由使用格式的使用者 name@domain 名稱;例如：

    -UserName "watcher3@litwareinc.com"

若要確認已建立測試使用者認證，執行這些命令在 Lync Server 管理命令介面：

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

每位使用者，應該會傳回類似如下的資訊：

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>使用預設綜合交易設定基本監看員節點

建立測試使用者之後您然後可以使用類似如下的命令來建立監看員節點：

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

此命令會建立新的監看員節點，會使用預設設定，並執行綜合交易的預設集合。 新的監看員節點也會使用測試使用者 watcher1@litwareinc.com、 watcher2@litwareinc.com 及 watcher3@litwareinc.com。 如果監看員節點要使用 TrustedServer 驗證，三個測試帳戶可以是任何有效的使用者帳戶啟用 Active Directory 與 Lync Server。 如果監看員節點要使用的交涉驗證方法，您也必須使用**Set-cstestusercredential** cmdlet 來啟用監看員節點這些使用者帳戶。

</div>

<div>

## <a name="configuring-extended-tests"></a>設定擴充的測試

如果您想要啟用公用交換的電話網路 （PSTN 測試），這會驗證與公用交換的電話網路的連線，您必須設定監看員節點時進行一些額外的設定。 首先，您必須建立測試使用者與 PSTN 測試類型的關聯。 若要這麼做，請執行 Lync Server 管理命令介面從如下的命令：

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

請注意此命令的結果，必須儲存在變數中。 在這個範例中，是名為 $pstnTest 的變數。

此時，您可以使用**New-cswatchernodeconfiguration** cmdlet 建立測試類型 （儲存在變數 $pstnTest） 至 Lync Server 2013 集區的關聯。 例如，下列命令會建立新的監看員節點組態的集區 atl-cs-001.litwareinc.com，新增的三個測試之前建立的使用者和也新增 PSTN 測試類型：

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

請注意，如果您不具有監看員節點電腦上安裝 Lync Server 核心檔案與 RTCLocal 資料庫，上述命令將會失敗。

若要測試多個語音原則，您需要使用**New-csextendedtest** cmdlet 建立每個原則延伸的測試。 已指派給這項測試使用者應設有所需的語音原則。 擴充的測試然後會使用類似下列的命令傳遞至**New-cswatchernodeconfiguration** cmdlet:

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

如果 New-cswatchernodeconfiguration 會呼叫不含使用 Tests 參數，表示預設綜合交易 （與指定的擴充綜合交易） 將會啟用新的監看員節點。 這表示監看員節點，將會測試下列元件：

  - 註冊

  - IM

  - GroupIM

  - P2PAV （對等音訊/視訊工作階段）

  - AvConference （音訊/會議）

  - 目前狀態

  - ABS （通訊錄服務）

  - ABWQ （通訊錄網頁服務）

  - PSTN （PSTN 閘道的呼叫，指定為擴充的測試。 根據預設，會停用 PSTN。 測試為啟用，在此情況下只因為命令啟用 PSTN 使用 ExtendedTests 參數。）

這也表示不會預設情況下測試下列元件：

  - AVEdgeConnectivity

  - MCXP2PIM （行動裝置立即訊息）

  - ExumConnectivity （Exchange 整合通訊）

  - JoinLauncher

  - PersistentChatMessage

  - DataConference

  - XmppIM

  - UnifiedContactStore

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a>新增與移除綜合交易

在設定監看員節點之後，您可以使用**Set-cswatchernodeconfiguration** cmdlet 來新增或移除之節點的綜合交易。 例如，若要新增的監看員節點 PersistentChatMessage 測試，使用 Add 方法與類似這樣的命令：

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

您可以加入多項測試使用逗號分隔的測試名稱。 例如：

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

請注意，是否一或多個這些測試 (例如，DataConference) 已啟用的監看員節點上，將會發生錯誤。 在此情況下，您會收到類似如下的錯誤訊息：

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

發生此錯誤時，將會不套用任何變更。 移除重複測試與要重新執行命令。

若要從監看員節點移除綜合交易，請使用 Remove 方法而不是 Add 方法。 例如，此命令可移除 ABWQ 測試從監看員節點：

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

您也可以使用 Replace 方法來取代所有目前已啟用測試，以下列一或多新測試。 例如，如果您只想要執行的 IM 測試監看員節點，您可以使用下列命令，設定：

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

當您執行上述命令時，將會停用指定監看員節點上的所有綜合交易除了 IM 之外。

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a>檢視與測試監看員節點組態

如果您想要檢視已指派給監看員節點測試，請使用類似如下的命令：

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

上述命令將傳回的資訊類似，根據已指派給節點的綜合交易：

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
> 若要依字母順序檢視綜合交易，請改為使用此命令：<BR>Get-cswatchernodeconfiguration – Identity"atl-cs-001.litwareinc.com"|Select-object – ExpandProperty 測試 |Sort 物件



</div>

若要確認監看員節點已建立，請輸入從 Lync Server 管理命令介面中的下列命令：

    Get-CsWatcherNodeConfiguration

您會收到類似如下的資訊：

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

若要確認已正確設定監看員節點，請輸入從 Lync Server 管理命令介面中的下列命令：

    Test-CsWatcherNodeConfiguration

上述命令會測試您的部署中的每個監看員節點，並告訴您的資訊，例如是否：

  - 登錄器角色已安裝。

  - 當您執行 Set-cswatchernodeconfiguration 時，會為您建立必要的登錄機碼。

  - 您的伺服器執行正確版本的 Lync Server。

  - 連接埠已正確設定。

  - 指派的測試使用者具有必要的認證。

</div>

</div>

<span> </span>

</div>

</div>

</div>

