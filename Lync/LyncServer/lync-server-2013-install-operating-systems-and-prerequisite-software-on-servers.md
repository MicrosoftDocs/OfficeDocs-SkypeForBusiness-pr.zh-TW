---
title: 在伺服器上安裝作業系統和必要軟體
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37cfbf02d379a3003338d4eabc7a5ca3c4b49f15
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498690"
---
# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a>在 Lync Server 2013 的伺服器上安裝作業系統和必要軟體

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-07-24_

在您設定硬體和系統基礎結構之後，除了在您所部署的每一部伺服器上安裝所有必備的軟體以外，您還需要安裝適當的 Windows 作業系統和更新。 這包括每一部 Lync Server 2013 伺服器角色，以及您部署所需的任何其他基礎結構伺服器或執行 SQL Server 的伺服器。

<div>


> [!NOTE]
> 本節說明作業系統的安裝以及內部伺服器的必備軟體。 若要部署 Edge Server 以支援外部使用者存取，您也需要為這些伺服器安裝作業系統和必要軟體，包括 Edge Server 和反向 proxy 伺服器。 如需準備伺服器以支援外部使用者存取的詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">準備 Lync Server 2013 周邊網路中的伺服器安裝</A> 。



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a>在伺服器上安裝 Windows 作業系統

在您要部署的每一部伺服器上，安裝適當的 Windows 作業系統，如下所示：

  - 執行**Lync Server 2013**     的伺服器如需有關執行 Lync Server 2013 之伺服器的作業系統需求的詳細資訊，請參閱支援檔中的[伺服器和工具作業系統支援（Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) ）。

  - **資料庫伺服器**    如需資料庫伺服器（包括後端資料庫、封存資料庫及監控資料庫）的作業系統需求的詳細資訊，請參閱 SQL Server 檔。 如需 SQL Server 2012，請參閱 SQL Server 2012 叢書，網址為 [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) 。

<div>


> [!NOTE]
> 如果您要在 Windows Server 2008 R2 上使用 SP1 來安裝 Lync Server 2013 &nbsp; &nbsp; ，您必須先安裝 Microsoft 知識庫文章2646886中所述的更新：「修正：當模組呼叫 IIS 7.5 中的 InsertEntityBody 方法時，就會發生堆損損毀」，at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp ; 3052&kbid = 2646886</A>。<BR>您也必須修改登錄，如知識庫文章中所述，在 <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">Windows Server 2012 R2 安裝的 Lync Server 2013 前端伺服器中，會記錄事件 IDs 32402，61045</A>。



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a>在伺服器上安裝 Windows 更新

在每一部伺服器上，從 Windows Update 安裝下列更新：

  - **執行 Lync Server 2013**     之伺服器的 Windows 更新如需執行 Lync Server 2013 之伺服器所需之 Windows Update 更新的詳細資訊，請參閱規劃檔中的[Lync Server 2013 其他軟體需求](lync-server-2013-additional-software-requirements.md)。

  - **資料庫伺服器**    如需資料庫伺服器（包括後端資料庫、封存資料庫及監控資料庫）所需之 Windows Update 更新的詳細資訊，請參閱 SQL Server 2012 檔。 如需 SQL Server 2012，請參閱 SQL Server 2012 叢書，網址為 [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) 。

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a>在伺服器上安裝其他必備軟體

Lync Server 2013 需要在伺服器上安裝下列其他軟體：

  - **執行 Lync Server 2013**     之伺服器的必要軟體執行 Lync Server 2013 之伺服器的其他軟體必要條件取決於所要部署的伺服器角色。 如需每個伺服器之特定軟體需求的詳細資訊，請參閱規劃檔中的 [Lync server 2013 其他軟體需求](lync-server-2013-additional-software-requirements.md) 。

  - **Windows Identity Foundation**    Lync Server 2013 需要安裝 Windows Identity Foundation 才能支援伺服器對伺服器驗證案例。 若要確認是否已安裝在電腦上，請移至 [控制台]，按一下 [ **程式和功能**]、[ **查看已安裝的更新**]，然後查看 [ **Microsoft Windows**]。 如需安裝 Windows Identity Foundation 的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) 。

  - **Microsoft .Net Framework 4.5**    Lync Server 2013 需要64位版本的 Microsoft .NET Framework 4.5。

  - **資料庫伺服器**     的必要軟體如需資料庫伺服器（包括後端資料庫、封存資料庫及監控資料庫）所需之 Windows 更新的詳細資訊，請參閱 SQL Server 2012 檔，網址為 [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) 。
    
    <div>
    

    > [!NOTE]
    > Lync Server 2013 會在每個 Standard Edition 伺服器和每一部執行 Lync Server 2013 的伺服器上，自動安裝 Microsoft SQL Server 2012 Express，本機設定存放區位於該伺服器上。

    
    </div>

  - **Windows Media Format Runtime**    所有要部署會議的前端伺服器和 Standard Edition 伺服器都必須安裝 Windows Media Format Runtime。 Windows Media Format Runtime 是執行 Windows Media Audio () 檔案，可讓通話駐留、宣告及回應群組應用程式對宣告和音樂播放。
    
    <div>
    

    > [!NOTE]
    > 若為 Windows Server 2012 和 Windows Server 2012 R2，Windows Media Format Runtime 會隨 Microsoft Media Foundation 一起安裝。

    
    </div>
    
    <div>
    

    > [!NOTE]
    > 若為 Windows Server &nbsp; 2008 和 Windows server &nbsp; 2008 &nbsp; R2，Windows Media Format Runtime 會安裝為 windows 桌面體驗的一部分。 建議您先安裝 Windows 桌面體驗，再安裝 Lync Server 2013。 如果 Lync Server 2013 在伺服器上找不到此軟體，它會提示您安裝它，然後您必須重新開機伺服器以完成安裝。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

