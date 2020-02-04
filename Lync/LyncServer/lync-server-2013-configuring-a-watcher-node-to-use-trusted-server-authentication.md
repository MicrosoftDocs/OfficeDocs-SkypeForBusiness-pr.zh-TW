---
title: 將觀察程式節點設定為使用信任的伺服器驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7279e18c73ecca9340f57d40794a3e9eb2dd160b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a>在 Lync Server 2013 中設定 [觀察程式] 節點，以使用信任的伺服器驗證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

如果您的觀察程式節點電腦位於周邊網路內，使用受信任的伺服器驗證可大大減少管理稅款，以維護單一憑證，而不是多個使用者帳戶密碼。

設定信任伺服器驗證的第一個步驟是建立信任的應用程式池來託管觀察程式節點電腦。 在已建立受信任的應用程式池之後，您必須接著在該觀察程式節點上設定綜合交易，以作為受信任的應用程式執行。

<div>


> [!NOTE]
> 受信任的應用程式是一種受信任的狀態，可作為 Lync Server 2013 的一部分執行的應用程式，但這不是產品內建的元件。 [受信任的狀態] 表示應用程式在每次執行時不會受到驗證的挑戰。



</div>

若要建立信任的應用程式池，請開啟 Lync Server 2013 管理命令介面，並執行如下所示的命令：

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> 如需有關上述命令中所使用之參數的詳細資訊，請在 Lync Server 管理命令介面提示字元輸入下列內容：<BR>取得-說明新-CsTrustedApplicationPool-全 |等



</div>

建立受信任的應用程式池之後，請將觀察程式節點電腦設定為將綜合交易作為受信任的應用程式執行。 這是使用**新的 CsTrustedApplication** Cmdlet 和類似以下的命令來完成：

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

當上述命令完成且已建立受信任的應用程式時，請執行 Enable-CsTopology，以確保變更生效：

    Enable-CsTopology

執行 Enable-CsTopology 之後，建議您重新開機電腦。

若要確認已建立新的受信任應用程式，請在 Lync Server 管理命令介面提示字元輸入下列內容：

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a>在 [觀察程式] 節點上設定預設憑證

每個觀察程式節點必須有使用 Lync Server 部署嚮導指派的預設憑證。

**指派預設憑證**

1.  按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **lync server**]，然後按一下 [ **lync server 部署嚮導]**。

2.  在 Lync Server 部署嚮導中，按一下 [**安裝或更新 Lync Server System** ]，然後按一下標題**要求、安裝或指派憑證**底下的 [**執行**]。
    
    <div>
    

    > [!NOTE]
    > 如果停用 [<STRONG>執行</STRONG>] 按鈕，您可能需要先按一下 [<STRONG>安裝本機設定儲存區</STRONG>] 下的 [<STRONG>執行</STRONG>]。

    
    </div>

3.  請執行下列其中一項操作：
    
      - 如果您已有可用作預設憑證的憑證，請按一下 [憑證] 嚮導中的 [**預設**]，然後按一下 [**指派**]。 遵循 [證書指派] 嚮導中的步驟，將該憑證指派給您。
    
      - 如果您需要要求使用預設憑證的憑證，請按一下 [**要求**]，然後依照 [證書申請] 嚮導中的步驟要求認證。 如果您使用的是 Web 服務器憑證的預設值，您會取得可指派為預設憑證的憑證。

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a>安裝和設定觀察程式節點

重新開機觀察程式節點電腦並設定憑證之後，您必須執行檔案 Watchernode。 （您必須在同時安裝 Operations Manager 代理程式檔案和 Lync Server 2013 核心元件的電腦上執行 Watchernode）。

**安裝和設定觀察程式節點**

1.  按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **lync server**]，然後按一下 [ **lync Server Management Shell**]，以開啟 Lync Server 管理命令介面。

2.  在 Lync Server 管理命令介面中，輸入下列命令，然後按 ENTER 鍵（指定您 Watchernode 複本的實際路徑）：
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > 您也可以從命令視窗執行 Watchernode。 若要開啟命令視窗，請按一下 [<STRONG>開始</STRONG>]，以滑鼠右鍵按一下 [<STRONG>命令提示</STRONG>字元]，然後按一下 [<STRONG>以系統管理員身分執行</STRONG>]。 當命令視窗開啟時，請輸入相同的前述命令。

    
    </div>

請注意，前面命令驗證 = TrustedServer 中的名稱/值對是區分大小寫的。 您必須完全按照所示輸入。 下列命令無法使用正確的字母大小寫：

C：\\Tools\\Watchernode （msi）驗證 = trustedserver

您只能在位於周邊網路中的電腦上使用 TrustedServer 模式。 當觀察程式節點在 TrustedServer 模式中執行時，系統管理員不需要維護電腦上的測試使用者密碼。

</div>

</div>

<span> </span>

</div>

</div>

</div>

