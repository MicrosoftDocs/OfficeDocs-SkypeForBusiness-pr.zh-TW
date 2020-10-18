---
title: 設定監視節點以使用受信任的伺服器驗證
description: 設定監視節點以使用信任的伺服器驗證。
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
ms.openlocfilehash: 247d628f936808a01780c7adc497342baedbbecb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576309"
---
# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a>在 Lync Server 2013 中設定監視節點以使用受信任的伺服器驗證

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

如果您的監看員節點電腦位於周邊網路內，使用受信任的伺服器驗證可大幅減少管理負擔，僅需維護單一憑證即可，不必再維護許多使用者帳戶密碼。

若要設定受信任的伺服器驗證，首先必須建立信任的應用程式集區，以便管理監看員節點電腦。建立信任的應用程式集區後，必須在該監看員節點上設定綜合交易，當作是信任的應用程式來執行。

<div>


> [!NOTE]
> 信任的應用程式是一種具有「信任的狀態」的應用程式，可作為 Lync Server 2013 的一部分來執行，但這不是產品的內建部分。 信任狀態表示每次執行應用程式時，其驗證不會受到質疑。



</div>

若要建立信任的應用程式集區，請開啟 Lync Server 2013 管理命令介面，並執行類似以下的命令：

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> 如需前述命令中所用參數的詳細資訊，請在 Lync Server 管理命令介面提示字元處，輸入下列命令：<BR>Get-Help New-CsTrustedApplicationPool -Full | more



</div>

建立信任的應用程式集區後，請將監看員節點電腦設為以信任的應用程式執行綜合交易。 若要設定，可使用 **New-CsTrustedApplication** Cmdlet 以及與下列類似的命令進行：

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

完成以上命令並建立信任的應用程式後請執行 Enable-CsTopology，確保變更生效：

    Enable-CsTopology

執行 Enable-CsTopology 後，建議重新啟動電腦。

若要確認是否已建立新的受信任應用程式，請在 Lync Server 管理命令介面提示字元處輸入下列命令：

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a>在監看員節點上設定預設憑證

每個監看員節點都必須有使用 Lync Server 部署嚮導指派的預設憑證。

**指派預設憑證**

1.  依序按一下 [ **開始**]、[ **所有程式**]、[ **lync server**]，然後按一下 [ **lync server 部署嚮導]**。

2.  在 [Lync Server 部署嚮導] 中，按一下 [**安裝或更新 Lync Server 系統**]，然後按一下 [標題**要求、安裝或指派憑證**] 底下的 [**執行**]。
    
    <div>
    

    > [!NOTE]
    > 如果 <STRONG>[執行]</STRONG> 按鈕停用，需先按一下 <STRONG>[安裝本機組態存放區]</STRONG> 下方的 <STRONG>[執行]</STRONG>。

    
    </div>

3.  執行下列其中一項作業：
    
      - 如果您擁有的憑證可作為預設憑證，請按一下驗證精靈中的 **[預設]**，然後再按一下 **[指派]**，並遵照驗證指派精靈中的步驟指派該憑證。
    
      - 如果想要求提供憑證作為預設憑證，請按一下 **[要求]** 並遵照憑證要求精靈中的步驟要求提供憑證。如果使用網頁伺服器憑證的預設值，則可獲得一個憑證並將其指派為預設憑證。

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a>安裝與設定監看員節點

重新開機監看員節點電腦及設定憑證之後，您必須執行 Watchernode.msi 的檔案。  (您必須在同時安裝 Operations Manager 代理程式檔案和 Lync Server 2013 核心元件的電腦上執行 Watchernode.msi。 ) 

**安裝與設定監看員節點**

1.  依序按一下 [ **開始**]、[ **所有程式**]、[ **lync server**]，然後按一下 [ **lync server 管理命令**介面]，以開啟 lync server 管理命令介面。

2.  在 Lync Server 管理命令介面中，輸入下列命令，然後按 ENTER (指定 Watchernode.msi) 副本的實際路徑：
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > 您可以從命令視窗執行 Watchernode.msi。若要開啟命令視窗，請按一下 <STRONG>[開始]</STRONG>、在 <STRONG>[命令提示字元]</STRONG> 上按滑鼠右鍵，然後按一下 <STRONG>[以系統管理員身分執行]</STRONG>。待命令視窗開啟後，鍵入以上同一個命令。

    
    </div>

請注意，以上命令 Authentication=TrustedServer 的名稱/值對區分大小寫。必須確實鍵入顯示的內容。下列命令因未使用正確的大小寫字母而導致失敗：

C： \\ Tools \\Watchernode.msi authentication = trustedserver

只有在周邊網路內的電腦上才能使用 TrustedServer 模式。在 TrustedServer 模式下執行監看員節點時，系統管理員便無須維護電腦的測試使用者密碼。

</div>

</div>

<span> </span>

</div>

</div>

</div>

