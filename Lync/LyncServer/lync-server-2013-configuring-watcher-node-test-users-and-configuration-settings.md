---
title: 設定觀察程式節點測試使用者和配置設定
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
ms.openlocfilehash: a3713844d5d2364459a28c5919bb1d32d421d706
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中設定觀察程式節點測試使用者和配置設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-29_

在設定將充當監視者節點的電腦之後，您必須：

1.  建立這些觀察程式節點要使用的測試帳戶。 如果您使用的是 Negotiate 驗證方法，您也必須使用[CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)) Cmdlet 來啟用這些測試帳戶，以便在 [觀察程式] 節點上使用。

2.  更新觀察程式節點設定。

本節涵蓋：

  - 設定測試使用者帳戶

  - 使用預設的綜合交易設定基本的觀察程式節點

  - 設定延伸測試

  - 新增及移除綜合交易

  - 查看及測試觀察程式節點設定

<div>

## <a name="configuring-test-user-accounts"></a>設定測試使用者帳戶

測試使用者不需要代表實際的人員，但必須是有效的 Active Directory 網域服務帳戶;此外，您必須為 Lync Server 2013 啟用這些帳戶，他們必須擁有有效的 SIP 位址，而且應該為企業語音啟用它們（以使用測試 CsPstnPeerToPeerCall 綜合交易）。 如果您使用的是 TrustedServer 驗證方法，則您只需確認這些帳戶存在，且已設定為在此加以指定即可。 您應該為您要測試的每個池指派至少三個測試使用者。

如果您使用的是 Negotiate 驗證方法，您也必須使用**CsTestUserCredential** Cmdlet 和 Lync Server 管理命令介面，以啟用這些測試帳戶來處理綜合交易。 您可以執行如下所示的命令來執行此動作。 （這些命令假設三個 Active Directory 使用者帳戶已建立，且已啟用這些帳戶的 Lync Server 2013）：

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

請注意，您不僅必須包含 SIP 位址，還要包括使用者名稱和密碼。 如果您不包含密碼集，CsTestUserCredential 會提示您輸入該資訊。 使用者名稱可以使用上面顯示的功能變數名稱\\使用者名稱格式來指定，或使用 [使用者格式] name@domain 名稱;例如：

    -UserName "watcher3@litwareinc.com"

若要確認已建立測試使用者認證，請在 Lync Server 管理命令介面中執行下列命令：

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

針對每個使用者應傳回類似以下內容的資訊：

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>使用預設的綜合交易設定基本的觀察程式節點

在測試使用者建立之後，您就可以使用類似以下的命令來建立觀察程式節點：

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

這個命令會建立使用預設設定的新的觀察程式節點，並執行預設的綜合交易集合。 新的 [觀察程式] 節點也會使用 test 使用者 watcher1@litwareinc.com、watcher2@litwareinc.com 和 watcher3@litwareinc.com。 如果 [觀察程式] 節點是使用 TrustedServer 驗證，則三個測試帳戶可以是啟用 Active Directory 和 Lync Server 的任何有效使用者帳戶。 如果觀察程式節點使用 Negotiate 驗證方法，您也必須使用**CsTestUserCredential** Cmdlet 來為觀察程式節點啟用這些使用者帳戶。

</div>

<div>

## <a name="configuring-extended-tests"></a>設定延伸測試

如果您想要啟用公用交換電話網絡（PSTN 測試），它會驗證與公用交換電話網絡的連線，您必須在設定觀察程式節點時，進行一些額外的配置。 首先，您需要將測試使用者與 PSTN 測試類型建立關聯。 若要執行此動作，請在 Lync Server 管理命令介面中執行如下所示的命令：

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

請注意，此命令的結果必須儲存在變數中。 在這個範例中，這是一個名為 $pstnTest 的變數。

此時，您可以使用**新的 CsWatcherNodeConfiguration** Cmdlet，將測試類型（儲存在變數 $pstnTest 中）與 Lync Server 2013 池產生關聯。 例如，下列命令會針對 [池 atl-cs-001.litwareinc.com] 建立新的觀察程式節點設定，並新增前面建立的三個測試使用者，同時也新增 PSTN 測試類型：

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

請注意，如果您沒有在監視程式節點電腦上安裝 Lync Server core 檔案和 RTCLocal 資料庫，上述命令就會失敗。

若要測試多個語音原則，您必須使用**CsExtendedTest** Cmdlet，為每個原則建立延伸測試。 指派給此測試的使用者應該使用所需的語音原則進行設定。 接著，您可以使用類似下列的命令，將延伸測試傳遞到**新的 CsWatcherNodeConfiguration** Cmdlet：

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

如果不使用 [測試] 參數呼叫 New-CsWatcherNodeConfiguration，則表示將只會針對新的觀察程式節點啟用預設的綜合交易（以及指定的延伸綜合交易）。 這表示觀察程式節點會測試下列元件：

  - 註冊

  - IM

  - GroupIM

  - P2PAV （對等音訊/視頻會話）

  - AvConference （音訊/會議）

  - 目前狀態

  - ABS （通訊錄服務）

  - ABWQ （通訊錄 web 服務）

  - PSTN （PSTN 閘道通話，指定為延伸測試。 根據預設，PSTN 是停用的。 此測試只會在此情況下啟用，因為命令是使用 ExtendedTests 參數啟用 PSTN）。

這也表示預設不會測試下列元件：

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

## <a name="adding-and-removing-synthetic-transactions"></a>新增及移除綜合交易

在已設定觀察程式節點之後，您可以使用**CsWatcherNodeConfiguration** Cmdlet 來新增或移除節點中的綜合交易。 例如，若要將 PersistentChatMessage 測試新增至 [觀察程式] 節點，請使用如下所示的 Add 方法和命令：

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

您可以使用逗號分隔測試名稱來新增多個測試。 例如：

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

請注意，如果已在 [觀察程式] 節點上啟用其中一個或多個測試（例如，DataConference），就會發生錯誤。 在這種情況下，您會收到類似以下的錯誤訊息：

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

發生此錯誤時，將不會套用任何變更。 必須重新執行該命令，並移除重複的測試。

若要從觀察程式節點移除綜合交易，請使用 Remove 方法，而不是 Add 方法。 例如，此命令會從觀察程式節點中移除 ABWQ 測試：

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

您也可以使用 Replace 方法，以一或多個新的測試取代所有目前啟用的測試。 例如，如果您只想要觀察程式節點執行 IM 測試，您可以使用此命令來設定：

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

當您執行上述命令時，除了 IM 之外，指定的觀察程式節點上的所有綜合交易都將停用。

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a>查看及測試觀察程式節點設定

如果您想要查看已指派給觀察程式節點的測試，請使用類似以下的命令：

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

根據已指派給節點的綜合交易，上述命令會傳回類似這個內容的資訊：

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
> 若要依字母順序查看綜合交易，請改為使用此命令：<BR>CsWatcherNodeConfiguration –身分識別 "atl-cs-001.litwareinc.com" |選取物件– ExpandProperty [測試] |排序物件



</div>

若要確認已建立觀察程式節點，請在 Lync Server 管理命令介面中輸入下列命令：

    Get-CsWatcherNodeConfiguration

您會收到如下所示的資訊：

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

若要確認已正確設定觀察程式節點，請在 Lync Server 管理命令介面中輸入下列命令：

    Test-CsWatcherNodeConfiguration

上述命令會在您的部署中測試每個觀察程式節點，並告訴您資訊，例如：

  - 已安裝所需的註冊機構角色。

  - 當您執行 CsWatcherNodeConfiguration 時，會為您建立所需的登錄機碼。

  - 您的伺服器正在執行正確版本的 Lync Server。

  - 您的埠已正確設定。

  - 您指派的測試使用者具有所需的認證。

</div>

</div>

<span> </span>

</div>

</div>

</div>

