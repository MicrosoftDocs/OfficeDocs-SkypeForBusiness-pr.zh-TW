---
title: 在伺服器上安裝作業系統和必要軟體
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26a4eed86f12386b10b49d4290a4596b40c1fcc9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a>在伺服器上安裝 Lync Server 2013 的作業系統和必要軟體

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-07-24_

在您設定硬體和系統基礎結構之後，除了您要部署的每個伺服器上的所有其他必備軟體之外，您還需要安裝適當的 Windows 作業系統和更新。 這包括每個 Lync Server 2013 伺服器角色，以及執行部署所需的任何其他結構伺服器或執行 SQL Server 的伺服器。

<div>


> [!NOTE]
> 本節說明內部伺服器的作業系統與必備軟體的安裝。 如果您要部署邊緣伺服器以支援外部使用者存取，您也需要安裝適用于這些伺服器的作業系統和必備軟體，包括邊緣伺服器和反向 proxy 伺服器。 如需準備伺服器以支援外部使用者存取的詳細資料，請參閱部署檔中的<A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Lync Server 2013 周邊網路中的 [準備安裝伺服器</A>]。



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a>在伺服器上安裝 Windows 作業系統

在您要部署的每個伺服器上，安裝適當的 Windows 作業系統，如下所示：

  - **執行 lync server 2013**   的伺服器如需有關執行 lync server 2013 之伺服器之作業系統需求的詳細資料，請參閱支援檔中的[Lync server 2013 中的 [伺服器與工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)]。

  - **資料庫伺服器**   如需資料庫伺服器作業系統需求的詳細資料，包括後端資料庫、封存資料庫及監視資料庫，請參閱 SQL Server 檔。 如需 SQL Server 2012，請參閱 SQL Server 2012 的線上[http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)書籍。

<div>


> [!NOTE]
> 如果您是在 Windows Server&nbsp;2008&nbsp;R2 （含 SP1）上安裝 Lync Server 2013，您必須先安裝 Microsoft 知識庫文章 2646886 "修正：當模組在 IIS 7.5 中呼叫 InsertEntityBody 方法時，發生堆損毀]，at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 2646886</A>。<BR>您也必須修改登錄，如知識庫文章中所述，在<A href="http://go.microsoft.com/fwlink/p/?linkid=506893">Windows Server 2012 R2 中安裝的 Lync Server 2013 前端伺服器上會記錄 [事件識別碼32402，61045</A>]。



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a>在伺服器上安裝 Windows Update

在每個伺服器上從 Windows Update 安裝下列更新：

  - **執行 lync server 2013**   之伺服器的 Windows 更新：如需有關執行 lync server 2013 之伺服器所需之 Windows 更新之更新的詳細資訊，請參閱規劃檔中[Lync Server 2013 的其他軟體需求](lync-server-2013-additional-software-requirements.md)。

  - **資料庫伺服器**   如需來自 Windows Update （包括後端資料庫、封存資料庫及監視資料庫）所需之更新的詳細資訊，請參閱 SQL Server 2012 檔。 如需 SQL Server 2012，請參閱 SQL Server 2012 的線上[http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)書籍。

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a>在伺服器上安裝其他必備軟體

Lync Server 2013 需要在伺服器上安裝下列其他軟體：

  - **執行 lync server 2013**   的伺服器必備軟體需要執行 lync server 2013 之伺服器的其他必備軟體先決條件，取決於要部署的伺服器角色。 如需每個伺服器的特定軟體需求的詳細資訊，請參閱規劃檔中的[Lync server 2013 其他軟體需求](lync-server-2013-additional-software-requirements.md)。

  - **Windows 身分識別基礎**   Lync Server 2013 需要安裝 Windows 身分識別基礎，才能支援伺服器對伺服器驗證案例。 若要確認您的電腦上已安裝該檔案，請移至 [控制台]，按一下 [**程式和功能**]、[**查看已安裝的更新**]，然後在 [ **Microsoft Windows**] 下查看。 如需安裝 Windows 身分識別基礎的詳細[http://go.microsoft.com/fwlink/p/?linkId=204657](http://go.microsoft.com/fwlink/p/?linkid=204657)資料，請參閱。

  - **Microsoft .net Framework 4.5**   Lync Server 2013 需要64位版本的 Microsoft .net Framework 4.5。

  - **資料庫伺服器**   的必備軟體有關資料庫伺服器（包括後端資料庫、封存資料庫及監視資料庫）所需 Windows 更新的詳細資料，請參閱 SQL Server 2012 檔[http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)。
    
    <div>
    

    > [!NOTE]
    > Lync Server 2013 會在每個標準版 server 上自動安裝 Microsoft SQL Server 2012 Express，並在每個伺服器上執行本機配置儲存所在的 Lync Server 2013。

    
    </div>

  - **Windows media 格式運行**   時間所有要部署會議的前端伺服器和標準版伺服器，都必須安裝 Windows Media 執行時間執行時間。 您必須具備 Windows Media 格式執行時間，才能執行通話駐留、宣告及回應群組應用程式的 Windows Media 音訊（.wma）檔案，以便在公告和音樂中播放。
    
    <div>
    

    > [!NOTE]
    > 針對 Windows Server 2012 和 Windows Server 2012 R2，Windows Media 格式執行時間會與 Microsoft 媒體基礎一起安裝。

    
    </div>
    
    <div>
    

    > [!NOTE]
    > 針對 Windows Server&nbsp;2008 和 windows server&nbsp;2008&nbsp;R2，windows Media 格式執行時間會安裝為 windows 桌面體驗的一部分。 建議您先安裝 Windows 桌面體驗，然後再安裝 Lync Server 2013。 如果 Lync Server 2013 在伺服器上找不到這個軟體，系統會提示您安裝它，然後您必須重新開機伺服器才能完成安裝。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

