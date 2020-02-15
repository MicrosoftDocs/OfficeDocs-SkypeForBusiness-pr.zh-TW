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
ms.openlocfilehash: 24441af263d9ebd73f61d350f898e26fa89e6f48
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a>Lync Server 2013 伺服器上安裝作業系統和必要軟體

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-07-24_

在您設定硬體和系統基礎結構之後，除了在您所部署的每一部伺服器上安裝所有必備的軟體以外，您還需要安裝適當的 Windows 作業系統和更新。 這包括每個 Lync Server 2013 伺服器角色，以及任何其他基礎結構伺服器或執行 SQL Server 的伺服器所需的部署。

<div>


> [!NOTE]
> 本節說明作業系統的安裝以及內部伺服器的必備軟體。 如果您要部署 Edge Server，以便支援外部使用者存取，您也需要安裝作業系統，以及針對這些伺服器，包括 Edge Server 和反向 proxy 伺服器的必要軟體。 如需準備伺服器來支援外部使用者存取的詳細資訊，請參閱部署文件中的<A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">準備安裝 Lync Server 2013 的周邊網路中的伺服器</A>。



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a>在伺服器上安裝 Windows 作業系統

在您要部署的每部伺服器，安裝適當的 Windows 作業系統，如下所示：

  - **執行 Lync Server 2013 伺服器**   如需執行 Lync Server 2013 伺服器的作業系統需求的詳細資訊，請參閱[Lync Server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)支援文件中。

  - **資料庫伺服器**   如需資料庫伺服器的作業系統需求的詳細資訊，包括後端資料庫、 封存資料庫和監控資料庫，請參閱 SQL Server 文件。 SQL Server 2012，請參閱 SQL Server 2012 線上叢書在[http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)。

<div>


> [!NOTE]
> 如果您 Windows Server 上安裝 Lync Server 2013&nbsp;2008年&nbsp;R2 sp1，您必須先安裝 Microsoft 知識庫文章 2646886，所述的更新 「 修正： 當模組在 IIS 7.5 中呼叫 InsertEntityBody 方法時發生堆積損毀 」，在<A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886">http://go.microsoft.com/fwlink/p/?linkid=3052&amp; 3052&kbid = 2646886</A>。<BR><A href="http://go.microsoft.com/fwlink/p/?linkid=506893">事件識別碼 32402，61045 登入 Lync Server 2013 前端伺服器，安裝在 Windows Server 2012 R2</A>的知識庫文件中所述，您也必須修改登錄。



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a>在伺服器上安裝 Windows 更新

每部伺服器上，從 Windows Update 安裝下列更新：

  - **執行 Lync Server 2013 的伺服器的 Windows 更新**   如需所需的伺服器執行 Lync Server 2013 中，從 Windows Update 更新的詳細資訊請參閱規劃文件中的[Lync Server 2013 的其他軟體需求](lync-server-2013-additional-software-requirements.md)。

  - **資料庫伺服器**   如需從 Windows Update 更新所需的資料庫伺服器的詳細資訊，包括後端資料庫、 封存資料庫和監控資料庫，請參閱 SQL Server 2012 文件。 SQL Server 2012，請參閱 SQL Server 2012 線上叢書在[http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)。

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a>在伺服器上安裝其他必備軟體

Lync Server 2013 需要安裝在伺服器上的下列其他軟體：

  - **執行 Lync Server 2013 的伺服器的必要軟體**   執行 Lync Server 2013 伺服器的其他軟體先決條件取決於要部署的伺服器角色。 如需每個伺服器的特定的軟體需求的詳細資訊，請參閱規劃文件中的[Lync Server 2013 的其他軟體需求](lync-server-2013-additional-software-requirements.md)。

  - **Windows Identity Foundation**   Lync Server 2013 為了支援伺服器對伺服器驗證案例所需的 Windows Identity Foundation 安裝。 若要確認，它已安裝在電腦上，移至 [控制台]，按一下 [**程式和功能**]**檢視安裝的更新**，並尋找在**Microsoft Windows**底下。 如需安裝 Windows Identity Foundation 的詳細資訊，請參閱[http://go.microsoft.com/fwlink/p/?linkId=204657](http://go.microsoft.com/fwlink/p/?linkid=204657)。

  - **Microsoft.NET Framework 4.5**   64 位元版本的 Microsoft.NET Framework 4.5 所需的 Lync Server 2013。

  - **資料庫伺服器的必要軟體**   如需有關所需的資料庫伺服器的 Windows 更新的詳細資訊，包括後端資料庫、 封存資料庫和監控資料庫，請參閱 SQL Server 2012 文件[http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)。
    
    <div>
    

    > [!NOTE]
    > Lync Server 2013 會自動安裝 Microsoft SQL Server 2012 Express 每一部 Standard Edition 伺服器和執行 Lync Server 2013 本機設定存放區所在的每部伺服器上。

    
    </div>

  - **Windows Media Format Runtime**   要部署會議的所有前端伺服器和 Standard Edition 伺服器必須已安裝 Windows Media Format Runtime。 Windows Media Format Runtime，才能執行宣告和音樂播放的通話駐留、 總機，以及回應群組應用程式的 Windows Media Audio (.wma) 檔案。
    
    <div>
    

    > [!NOTE]
    > Windows Server 2012 和 Windows Server 2012 R2 Windows Media Format Runtime 會安裝 Microsoft 媒體 Foundation。

    
    </div>
    
    <div>
    

    > [!NOTE]
    > Windows server&nbsp;2008年和 Windows Server&nbsp;2008年&nbsp;R2 Windows Media Format Runtime 安裝 Windows 桌面體驗的一部分。 建議您安裝 Windows 桌面體驗，才能安裝 Lync Server 2013。 如果 Lync Server 2013 伺服器上找不到此軟體，它會提示您進行安裝，並接著您必須重新啟動伺服器，以完成安裝。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

