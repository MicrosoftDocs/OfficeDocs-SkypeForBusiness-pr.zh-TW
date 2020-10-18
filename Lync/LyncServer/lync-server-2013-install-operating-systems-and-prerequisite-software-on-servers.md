---
title: 在伺服器上安裝作業系統和必要軟體
description: 在伺服器上安裝作業系統和必要軟體。
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
ms.openlocfilehash: 2bae9e57db9c2f1d3f3bde7ce9cc7071b73aa01d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574129"
---
# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a><span data-ttu-id="be6df-103">在 Lync Server 2013 的伺服器上安裝作業系統和必要軟體</span><span class="sxs-lookup"><span data-stu-id="be6df-103">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be6df-104">_**主題上次修改日期：** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="be6df-104">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="be6df-105">在您設定硬體和系統基礎結構之後，除了在您所部署的每一部伺服器上安裝所有必備的軟體以外，您還需要安裝適當的 Windows 作業系統和更新。</span><span class="sxs-lookup"><span data-stu-id="be6df-105">After you have set up the hardware and system infrastructure, you need to install the appropriate Windows operating systems and updates, in addition to all other prerequisite software on each server that you are deploying.</span></span> <span data-ttu-id="be6df-106">這包括每一部 Lync Server 2013 伺服器角色，以及您部署所需的任何其他基礎結構伺服器或執行 SQL Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="be6df-106">This includes each Lync Server 2013 server role and any additional infrastructure servers or servers running SQL Server that are required for your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="be6df-107">本節說明作業系統的安裝以及內部伺服器的必備軟體。</span><span class="sxs-lookup"><span data-stu-id="be6df-107">This section describes installation of operating systems and prerequisite software for internal servers.</span></span> <span data-ttu-id="be6df-108">若要部署 Edge Server 以支援外部使用者存取，您也需要為這些伺服器安裝作業系統和必要軟體，包括 Edge Server 和反向 proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="be6df-108">If you are deploying Edge Servers to support external user access, you also need to install operating systems and prerequisite software for those servers, including Edge Servers and reverse proxy servers.</span></span> <span data-ttu-id="be6df-109">如需準備伺服器以支援外部使用者存取的詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">準備 Lync Server 2013 周邊網路中的伺服器安裝</A> 。</span><span class="sxs-lookup"><span data-stu-id="be6df-109">For details about preparing servers to support external user access, see <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a><span data-ttu-id="be6df-110">在伺服器上安裝 Windows 作業系統</span><span class="sxs-lookup"><span data-stu-id="be6df-110">Install Windows Operating Systems on Servers</span></span>

<span data-ttu-id="be6df-111">在您要部署的每一部伺服器上，安裝適當的 Windows 作業系統，如下所示：</span><span class="sxs-lookup"><span data-stu-id="be6df-111">On each server that you are deploying, install the appropriate Windows operating system as follows:</span></span>

  - <span data-ttu-id="be6df-112">執行**Lync Server 2013**     的伺服器如需有關執行 Lync Server 2013 之伺服器的作業系統需求的詳細資訊，請參閱支援檔中的[伺服器和工具作業系統支援（Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md) ）。</span><span class="sxs-lookup"><span data-stu-id="be6df-112">**Servers running Lync Server 2013**   For details about the operating system requirements for servers running Lync Server 2013, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="be6df-113">**資料庫伺服器**    如需資料庫伺服器（包括後端資料庫、封存資料庫及監控資料庫）的作業系統需求的詳細資訊，請參閱 SQL Server 檔。</span><span class="sxs-lookup"><span data-stu-id="be6df-113">**Database servers**   For details about operating system requirements for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server documentation.</span></span> <span data-ttu-id="be6df-114">如需 SQL Server 2012，請參閱 SQL Server 2012 叢書，網址為 [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) 。</span><span class="sxs-lookup"><span data-stu-id="be6df-114">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="be6df-115">如果您要在 Windows Server 2008 R2 上使用 SP1 來安裝 Lync Server 2013 &nbsp; &nbsp; ，您必須先安裝 Microsoft 知識庫文章2646886中所述的更新：「修正：當模組呼叫 IIS 7.5 中的 InsertEntityBody 方法時，就會發生堆損損毀」，at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp ; 3052&kbid = 2646886</A>。</span><span class="sxs-lookup"><span data-stu-id="be6df-115">If you are installing Lync Server 2013 on Windows Server&nbsp;2008&nbsp;R2 with SP1, you must first install the update described in the Microsoft Knowledge Based article 2646886, “FIX: Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5”, at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2646886</A>.</span></span><BR><span data-ttu-id="be6df-116">您也必須修改登錄，如知識庫文章中所述，在 <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">Windows Server 2012 R2 安裝的 Lync Server 2013 前端伺服器中，會記錄事件 IDs 32402，61045</A>。</span><span class="sxs-lookup"><span data-stu-id="be6df-116">You must also modify the registry as described in the KB article, <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">Event IDs 32402, 61045 are logged in Lync Server 2013 Front End servers that are installed in Windows Server 2012 R2</A>.</span></span>



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a><span data-ttu-id="be6df-117">在伺服器上安裝 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="be6df-117">Install Windows Update on Servers</span></span>

<span data-ttu-id="be6df-118">在每一部伺服器上，從 Windows Update 安裝下列更新：</span><span class="sxs-lookup"><span data-stu-id="be6df-118">Install the following updates from Windows Update on each server:</span></span>

  - <span data-ttu-id="be6df-119">**執行 Lync Server 2013**     之伺服器的 Windows 更新如需執行 Lync Server 2013 之伺服器所需之 Windows Update 更新的詳細資訊，請參閱規劃檔中的[Lync Server 2013 其他軟體需求](lync-server-2013-additional-software-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="be6df-119">**Windows Update for servers running Lync Server 2013**   For details about the updates from Windows Update that are required for servers running Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="be6df-120">**資料庫伺服器**    如需資料庫伺服器（包括後端資料庫、封存資料庫及監控資料庫）所需之 Windows Update 更新的詳細資訊，請參閱 SQL Server 2012 檔。</span><span class="sxs-lookup"><span data-stu-id="be6df-120">**Database servers**   For details about the updates from Windows Update that are required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation.</span></span> <span data-ttu-id="be6df-121">如需 SQL Server 2012，請參閱 SQL Server 2012 叢書，網址為 [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) 。</span><span class="sxs-lookup"><span data-stu-id="be6df-121">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a><span data-ttu-id="be6df-122">在伺服器上安裝其他必備軟體</span><span class="sxs-lookup"><span data-stu-id="be6df-122">Install Other Prerequisite Software on Servers</span></span>

<span data-ttu-id="be6df-123">Lync Server 2013 需要在伺服器上安裝下列其他軟體：</span><span class="sxs-lookup"><span data-stu-id="be6df-123">Lync Server 2013 requires the installation of the following additional software on servers:</span></span>

  - <span data-ttu-id="be6df-124">**執行 Lync Server 2013**     之伺服器的必要軟體執行 Lync Server 2013 之伺服器的其他軟體必要條件取決於所要部署的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="be6df-124">**Prerequisite software for servers running Lync Server 2013**   The additional software prerequisites for servers running Lync Server 2013 depend on the server role being deployed.</span></span> <span data-ttu-id="be6df-125">如需每個伺服器之特定軟體需求的詳細資訊，請參閱規劃檔中的 [Lync server 2013 其他軟體需求](lync-server-2013-additional-software-requirements.md) 。</span><span class="sxs-lookup"><span data-stu-id="be6df-125">For details about the specific software requirements for each server, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="be6df-126">**Windows Identity Foundation**    Lync Server 2013 需要安裝 Windows Identity Foundation 才能支援伺服器對伺服器驗證案例。</span><span class="sxs-lookup"><span data-stu-id="be6df-126">**Windows Identity Foundation**   Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server-to-server authentication scenarios.</span></span> <span data-ttu-id="be6df-127">若要確認是否已安裝在電腦上，請移至 [控制台]，按一下 [ **程式和功能**]、[ **查看已安裝的更新**]，然後查看 [ **Microsoft Windows**]。</span><span class="sxs-lookup"><span data-stu-id="be6df-127">To verify that it has already been installed on your computer, go to Control Panel, click **Programs and Features**, **View installed updates**, and look under **Microsoft Windows**.</span></span> <span data-ttu-id="be6df-128">如需安裝 Windows Identity Foundation 的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) 。</span><span class="sxs-lookup"><span data-stu-id="be6df-128">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="be6df-129">**Microsoft .Net Framework 4.5**    Lync Server 2013 需要64位版本的 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="be6df-129">**Microsoft .NET Framework 4.5**   The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

  - <span data-ttu-id="be6df-130">**資料庫伺服器**     的必要軟體如需資料庫伺服器（包括後端資料庫、封存資料庫及監控資料庫）所需之 Windows 更新的詳細資訊，請參閱 SQL Server 2012 檔，網址為 [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) 。</span><span class="sxs-lookup"><span data-stu-id="be6df-130">**Prerequisite software for database servers**   For details about the Windows Update required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="be6df-131">Lync Server 2013 會在每個 Standard Edition 伺服器和每一部執行 Lync Server 2013 的伺服器上，自動安裝 Microsoft SQL Server 2012 Express，本機設定存放區位於該伺服器上。</span><span class="sxs-lookup"><span data-stu-id="be6df-131">Lync Server 2013 automatically installs Microsoft SQL Server 2012 Express on each Standard Edition server and each server running Lync Server 2013 on which the local configuration store is located.</span></span>

    
    </div>

  - <span data-ttu-id="be6df-132">**Windows Media Format Runtime**    所有要部署會議的前端伺服器和 Standard Edition 伺服器都必須安裝 Windows Media Format Runtime。</span><span class="sxs-lookup"><span data-stu-id="be6df-132">**Windows Media Format Runtime**   All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed.</span></span> <span data-ttu-id="be6df-133">Windows Media Format Runtime 是執行 Windows Media Audio () 檔案，可讓通話駐留、宣告及回應群組應用程式對宣告和音樂播放。</span><span class="sxs-lookup"><span data-stu-id="be6df-133">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="be6df-134">若為 Windows Server 2012 和 Windows Server 2012 R2，Windows Media Format Runtime 會隨 Microsoft Media Foundation 一起安裝。</span><span class="sxs-lookup"><span data-stu-id="be6df-134">For Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="be6df-135">若為 Windows Server &nbsp; 2008 和 Windows server &nbsp; 2008 &nbsp; R2，Windows Media Format Runtime 會安裝為 windows 桌面體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="be6df-135">For Windows Server&nbsp;2008 and Windows Server&nbsp;2008&nbsp;R2 the Windows Media Format Runtime installs as part of the Windows Desktop Experience.</span></span> <span data-ttu-id="be6df-136">建議您先安裝 Windows 桌面體驗，再安裝 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="be6df-136">It is recommended that you install Windows Desktop Experience before you install Lync Server 2013.</span></span> <span data-ttu-id="be6df-137">如果 Lync Server 2013 在伺服器上找不到此軟體，它會提示您安裝它，然後您必須重新開機伺服器以完成安裝。</span><span class="sxs-lookup"><span data-stu-id="be6df-137">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

