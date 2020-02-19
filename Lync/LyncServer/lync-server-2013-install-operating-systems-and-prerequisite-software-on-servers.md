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
ms.openlocfilehash: 69ad97d578073e2b0f9ed08d929007c33e59b8fd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a><span data-ttu-id="d64bf-102">Lync Server 2013 伺服器上安裝作業系統和必要軟體</span><span class="sxs-lookup"><span data-stu-id="d64bf-102">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d64bf-103">_**上次修改主題：** 2014年-07-24_</span><span class="sxs-lookup"><span data-stu-id="d64bf-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="d64bf-104">在您設定硬體和系統基礎結構之後，除了在您所部署的每一部伺服器上安裝所有必備的軟體以外，您還需要安裝適當的 Windows 作業系統和更新。</span><span class="sxs-lookup"><span data-stu-id="d64bf-104">After you have set up the hardware and system infrastructure, you need to install the appropriate Windows operating systems and updates, in addition to all other prerequisite software on each server that you are deploying.</span></span> <span data-ttu-id="d64bf-105">這包括每個 Lync Server 2013 伺服器角色，以及任何其他基礎結構伺服器或執行 SQL Server 的伺服器所需的部署。</span><span class="sxs-lookup"><span data-stu-id="d64bf-105">This includes each Lync Server 2013 server role and any additional infrastructure servers or servers running SQL Server that are required for your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d64bf-106">本節說明作業系統的安裝以及內部伺服器的必備軟體。</span><span class="sxs-lookup"><span data-stu-id="d64bf-106">This section describes installation of operating systems and prerequisite software for internal servers.</span></span> <span data-ttu-id="d64bf-107">如果您要部署 Edge Server，以便支援外部使用者存取，您也需要安裝作業系統，以及針對這些伺服器，包括 Edge Server 和反向 proxy 伺服器的必要軟體。</span><span class="sxs-lookup"><span data-stu-id="d64bf-107">If you are deploying Edge Servers to support external user access, you also need to install operating systems and prerequisite software for those servers, including Edge Servers and reverse proxy servers.</span></span> <span data-ttu-id="d64bf-108">如需準備伺服器來支援外部使用者存取的詳細資訊，請參閱部署文件中的<A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">準備安裝 Lync Server 2013 的周邊網路中的伺服器</A>。</span><span class="sxs-lookup"><span data-stu-id="d64bf-108">For details about preparing servers to support external user access, see <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a><span data-ttu-id="d64bf-109">在伺服器上安裝 Windows 作業系統</span><span class="sxs-lookup"><span data-stu-id="d64bf-109">Install Windows Operating Systems on Servers</span></span>

<span data-ttu-id="d64bf-110">在您要部署的每部伺服器，安裝適當的 Windows 作業系統，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d64bf-110">On each server that you are deploying, install the appropriate Windows operating system as follows:</span></span>

  - <span data-ttu-id="d64bf-111">**執行 Lync Server 2013 伺服器**   如需執行 Lync Server 2013 伺服器的作業系統需求的詳細資訊，請參閱[Lync Server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)支援文件中。</span><span class="sxs-lookup"><span data-stu-id="d64bf-111">**Servers running Lync Server 2013**   For details about the operating system requirements for servers running Lync Server 2013, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="d64bf-112">**資料庫伺服器**   如需資料庫伺服器的作業系統需求的詳細資訊，包括後端資料庫、 封存資料庫和監控資料庫，請參閱 SQL Server 文件。</span><span class="sxs-lookup"><span data-stu-id="d64bf-112">**Database servers**   For details about operating system requirements for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server documentation.</span></span> <span data-ttu-id="d64bf-113">SQL Server 2012，請參閱 SQL Server 2012 線上叢書在[https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)。</span><span class="sxs-lookup"><span data-stu-id="d64bf-113">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d64bf-114">如果您 Windows Server 上安裝 Lync Server 2013&nbsp;2008年&nbsp;R2 sp1，您必須先安裝 Microsoft 知識庫文章 2646886，所述的更新 「 修正： 當模組在 IIS 7.5 中呼叫 InsertEntityBody 方法時發生堆積損毀 」，在<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886">https://go.microsoft.com/fwlink/p/?linkid=3052&amp; 3052&kbid = 2646886</A>。</span><span class="sxs-lookup"><span data-stu-id="d64bf-114">If you are installing Lync Server 2013 on Windows Server&nbsp;2008&nbsp;R2 with SP1, you must first install the update described in the Microsoft Knowledge Based article 2646886, “FIX: Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5”, at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2646886</A>.</span></span><BR><span data-ttu-id="d64bf-115"><A href="https://go.microsoft.com/fwlink/p/?linkid=506893">事件識別碼 32402，61045 登入 Lync Server 2013 前端伺服器，安裝在 Windows Server 2012 R2</A>的知識庫文件中所述，您也必須修改登錄。</span><span class="sxs-lookup"><span data-stu-id="d64bf-115">You must also modify the registry as described in the KB article, <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">Event IDs 32402, 61045 are logged in Lync Server 2013 Front End servers that are installed in Windows Server 2012 R2</A>.</span></span>



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a><span data-ttu-id="d64bf-116">在伺服器上安裝 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="d64bf-116">Install Windows Update on Servers</span></span>

<span data-ttu-id="d64bf-117">每部伺服器上，從 Windows Update 安裝下列更新：</span><span class="sxs-lookup"><span data-stu-id="d64bf-117">Install the following updates from Windows Update on each server:</span></span>

  - <span data-ttu-id="d64bf-118">**執行 Lync Server 2013 的伺服器的 Windows 更新**   如需所需的伺服器執行 Lync Server 2013 中，從 Windows Update 更新的詳細資訊請參閱規劃文件中的[Lync Server 2013 的其他軟體需求](lync-server-2013-additional-software-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d64bf-118">**Windows Update for servers running Lync Server 2013**   For details about the updates from Windows Update that are required for servers running Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="d64bf-119">**資料庫伺服器**   如需從 Windows Update 更新所需的資料庫伺服器的詳細資訊，包括後端資料庫、 封存資料庫和監控資料庫，請參閱 SQL Server 2012 文件。</span><span class="sxs-lookup"><span data-stu-id="d64bf-119">**Database servers**   For details about the updates from Windows Update that are required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation.</span></span> <span data-ttu-id="d64bf-120">SQL Server 2012，請參閱 SQL Server 2012 線上叢書在[https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)。</span><span class="sxs-lookup"><span data-stu-id="d64bf-120">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a><span data-ttu-id="d64bf-121">在伺服器上安裝其他必備軟體</span><span class="sxs-lookup"><span data-stu-id="d64bf-121">Install Other Prerequisite Software on Servers</span></span>

<span data-ttu-id="d64bf-122">Lync Server 2013 需要安裝在伺服器上的下列其他軟體：</span><span class="sxs-lookup"><span data-stu-id="d64bf-122">Lync Server 2013 requires the installation of the following additional software on servers:</span></span>

  - <span data-ttu-id="d64bf-123">**執行 Lync Server 2013 的伺服器的必要軟體**   執行 Lync Server 2013 伺服器的其他軟體先決條件取決於要部署的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="d64bf-123">**Prerequisite software for servers running Lync Server 2013**   The additional software prerequisites for servers running Lync Server 2013 depend on the server role being deployed.</span></span> <span data-ttu-id="d64bf-124">如需每個伺服器的特定的軟體需求的詳細資訊，請參閱規劃文件中的[Lync Server 2013 的其他軟體需求](lync-server-2013-additional-software-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d64bf-124">For details about the specific software requirements for each server, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="d64bf-125">**Windows Identity Foundation**   Lync Server 2013 為了支援伺服器對伺服器驗證案例所需的 Windows Identity Foundation 安裝。</span><span class="sxs-lookup"><span data-stu-id="d64bf-125">**Windows Identity Foundation**   Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server-to-server authentication scenarios.</span></span> <span data-ttu-id="d64bf-126">若要確認，它已安裝在電腦上，移至 [控制台]，按一下 [**程式和功能**]**檢視安裝的更新**，並尋找在**Microsoft Windows**底下。</span><span class="sxs-lookup"><span data-stu-id="d64bf-126">To verify that it has already been installed on your computer, go to Control Panel, click **Programs and Features**, **View installed updates**, and look under **Microsoft Windows**.</span></span> <span data-ttu-id="d64bf-127">如需安裝 Windows Identity Foundation 的詳細資訊，請參閱[https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)。</span><span class="sxs-lookup"><span data-stu-id="d64bf-127">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="d64bf-128">**Microsoft.NET Framework 4.5**   64 位元版本的 Microsoft.NET Framework 4.5 所需的 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="d64bf-128">**Microsoft .NET Framework 4.5**   The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

  - <span data-ttu-id="d64bf-129">**資料庫伺服器的必要軟體**   如需有關所需的資料庫伺服器的 Windows 更新的詳細資訊，包括後端資料庫、 封存資料庫和監控資料庫，請參閱 SQL Server 2012 文件[https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)。</span><span class="sxs-lookup"><span data-stu-id="d64bf-129">**Prerequisite software for database servers**   For details about the Windows Update required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d64bf-130">Lync Server 2013 會自動安裝 Microsoft SQL Server 2012 Express 每一部 Standard Edition 伺服器和執行 Lync Server 2013 本機設定存放區所在的每部伺服器上。</span><span class="sxs-lookup"><span data-stu-id="d64bf-130">Lync Server 2013 automatically installs Microsoft SQL Server 2012 Express on each Standard Edition server and each server running Lync Server 2013 on which the local configuration store is located.</span></span>

    
    </div>

  - <span data-ttu-id="d64bf-131">**Windows Media Format Runtime**   要部署會議的所有前端伺服器和 Standard Edition 伺服器必須已安裝 Windows Media Format Runtime。</span><span class="sxs-lookup"><span data-stu-id="d64bf-131">**Windows Media Format Runtime**   All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed.</span></span> <span data-ttu-id="d64bf-132">Windows Media Format Runtime，才能執行宣告和音樂播放的通話駐留、 總機，以及回應群組應用程式的 Windows Media Audio (.wma) 檔案。</span><span class="sxs-lookup"><span data-stu-id="d64bf-132">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d64bf-133">Windows Server 2012 和 Windows Server 2012 R2 Windows Media Format Runtime 會安裝 Microsoft 媒體 Foundation。</span><span class="sxs-lookup"><span data-stu-id="d64bf-133">For Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d64bf-134">Windows server&nbsp;2008年和 Windows Server&nbsp;2008年&nbsp;R2 Windows Media Format Runtime 安裝 Windows 桌面體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="d64bf-134">For Windows Server&nbsp;2008 and Windows Server&nbsp;2008&nbsp;R2 the Windows Media Format Runtime installs as part of the Windows Desktop Experience.</span></span> <span data-ttu-id="d64bf-135">建議您安裝 Windows 桌面體驗，才能安裝 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="d64bf-135">It is recommended that you install Windows Desktop Experience before you install Lync Server 2013.</span></span> <span data-ttu-id="d64bf-136">如果 Lync Server 2013 伺服器上找不到此軟體，它會提示您進行安裝，並接著您必須重新啟動伺服器，以完成安裝。</span><span class="sxs-lookup"><span data-stu-id="d64bf-136">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

