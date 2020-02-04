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
ms.openlocfilehash: 8c41147d33dce792f88b30f72b36201ddb6c7d62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a><span data-ttu-id="0527c-102">在伺服器上安裝 Lync Server 2013 的作業系統和必要軟體</span><span class="sxs-lookup"><span data-stu-id="0527c-102">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0527c-103">_**主題上次修改日期：** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="0527c-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="0527c-104">在您設定硬體和系統基礎結構之後，除了您要部署的每個伺服器上的所有其他必備軟體之外，您還需要安裝適當的 Windows 作業系統和更新。</span><span class="sxs-lookup"><span data-stu-id="0527c-104">After you have set up the hardware and system infrastructure, you need to install the appropriate Windows operating systems and updates, in addition to all other prerequisite software on each server that you are deploying.</span></span> <span data-ttu-id="0527c-105">這包括每個 Lync Server 2013 伺服器角色，以及執行部署所需的任何其他結構伺服器或執行 SQL Server 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="0527c-105">This includes each Lync Server 2013 server role and any additional infrastructure servers or servers running SQL Server that are required for your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="0527c-106">本節說明內部伺服器的作業系統與必備軟體的安裝。</span><span class="sxs-lookup"><span data-stu-id="0527c-106">This section describes installation of operating systems and prerequisite software for internal servers.</span></span> <span data-ttu-id="0527c-107">如果您要部署邊緣伺服器以支援外部使用者存取，您也需要安裝適用于這些伺服器的作業系統和必備軟體，包括邊緣伺服器和反向 proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="0527c-107">If you are deploying Edge Servers to support external user access, you also need to install operating systems and prerequisite software for those servers, including Edge Servers and reverse proxy servers.</span></span> <span data-ttu-id="0527c-108">如需準備伺服器以支援外部使用者存取的詳細資料，請參閱部署檔中的<A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Lync Server 2013 周邊網路中的 [準備安裝伺服器</A>]。</span><span class="sxs-lookup"><span data-stu-id="0527c-108">For details about preparing servers to support external user access, see <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a><span data-ttu-id="0527c-109">在伺服器上安裝 Windows 作業系統</span><span class="sxs-lookup"><span data-stu-id="0527c-109">Install Windows Operating Systems on Servers</span></span>

<span data-ttu-id="0527c-110">在您要部署的每個伺服器上，安裝適當的 Windows 作業系統，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0527c-110">On each server that you are deploying, install the appropriate Windows operating system as follows:</span></span>

  - <span data-ttu-id="0527c-111">**執行 lync server 2013**   的伺服器如需有關執行 lync server 2013 之伺服器之作業系統需求的詳細資料，請參閱支援檔中的[Lync server 2013 中的 [伺服器與工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)]。</span><span class="sxs-lookup"><span data-stu-id="0527c-111">**Servers running Lync Server 2013**   For details about the operating system requirements for servers running Lync Server 2013, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="0527c-112">**資料庫伺服器**   如需資料庫伺服器作業系統需求的詳細資料，包括後端資料庫、封存資料庫及監視資料庫，請參閱 SQL Server 檔。</span><span class="sxs-lookup"><span data-stu-id="0527c-112">**Database servers**   For details about operating system requirements for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server documentation.</span></span> <span data-ttu-id="0527c-113">如需 SQL Server 2012，請參閱 SQL Server 2012 的線上[http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)書籍。</span><span class="sxs-lookup"><span data-stu-id="0527c-113">For SQL Server 2012, see the SQL Server 2012 Books Online at [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="0527c-114">如果您是在 Windows Server&nbsp;2008&nbsp;R2 （含 SP1）上安裝 Lync Server 2013，您必須先安裝 Microsoft 知識庫文章 2646886 "修正：當模組在 IIS 7.5 中呼叫 InsertEntityBody 方法時，發生堆損毀]，at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> http://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 2646886</A>。</span><span class="sxs-lookup"><span data-stu-id="0527c-114">If you are installing Lync Server 2013 on Windows Server&nbsp;2008&nbsp;R2 with SP1, you must first install the update described in the Microsoft Knowledge Based article 2646886, “FIX: Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5”, at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886">http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2646886</A>.</span></span><BR><span data-ttu-id="0527c-115">您也必須修改登錄，如知識庫文章中所述，在<A href="http://go.microsoft.com/fwlink/p/?linkid=506893">Windows Server 2012 R2 中安裝的 Lync Server 2013 前端伺服器上會記錄 [事件識別碼32402，61045</A>]。</span><span class="sxs-lookup"><span data-stu-id="0527c-115">You must also modify the registry as described in the KB article, <A href="http://go.microsoft.com/fwlink/p/?linkid=506893">Event IDs 32402, 61045 are logged in Lync Server 2013 Front End servers that are installed in Windows Server 2012 R2</A>.</span></span>



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a><span data-ttu-id="0527c-116">在伺服器上安裝 Windows Update</span><span class="sxs-lookup"><span data-stu-id="0527c-116">Install Windows Update on Servers</span></span>

<span data-ttu-id="0527c-117">在每個伺服器上從 Windows Update 安裝下列更新：</span><span class="sxs-lookup"><span data-stu-id="0527c-117">Install the following updates from Windows Update on each server:</span></span>

  - <span data-ttu-id="0527c-118">**執行 lync server 2013**   之伺服器的 Windows 更新：如需有關執行 lync server 2013 之伺服器所需之 Windows 更新之更新的詳細資訊，請參閱規劃檔中[Lync Server 2013 的其他軟體需求](lync-server-2013-additional-software-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0527c-118">**Windows Update for servers running Lync Server 2013**   For details about the updates from Windows Update that are required for servers running Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="0527c-119">**資料庫伺服器**   如需來自 Windows Update （包括後端資料庫、封存資料庫及監視資料庫）所需之更新的詳細資訊，請參閱 SQL Server 2012 檔。</span><span class="sxs-lookup"><span data-stu-id="0527c-119">**Database servers**   For details about the updates from Windows Update that are required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation.</span></span> <span data-ttu-id="0527c-120">如需 SQL Server 2012，請參閱 SQL Server 2012 的線上[http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)書籍。</span><span class="sxs-lookup"><span data-stu-id="0527c-120">For SQL Server 2012, see the SQL Server 2012 Books Online at [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a><span data-ttu-id="0527c-121">在伺服器上安裝其他必備軟體</span><span class="sxs-lookup"><span data-stu-id="0527c-121">Install Other Prerequisite Software on Servers</span></span>

<span data-ttu-id="0527c-122">Lync Server 2013 需要在伺服器上安裝下列其他軟體：</span><span class="sxs-lookup"><span data-stu-id="0527c-122">Lync Server 2013 requires the installation of the following additional software on servers:</span></span>

  - <span data-ttu-id="0527c-123">**執行 lync server 2013**   的伺服器必備軟體需要執行 lync server 2013 之伺服器的其他必備軟體先決條件，取決於要部署的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="0527c-123">**Prerequisite software for servers running Lync Server 2013**   The additional software prerequisites for servers running Lync Server 2013 depend on the server role being deployed.</span></span> <span data-ttu-id="0527c-124">如需每個伺服器的特定軟體需求的詳細資訊，請參閱規劃檔中的[Lync server 2013 其他軟體需求](lync-server-2013-additional-software-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0527c-124">For details about the specific software requirements for each server, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="0527c-125">**Windows 身分識別基礎**   Lync Server 2013 需要安裝 Windows 身分識別基礎，才能支援伺服器對伺服器驗證案例。</span><span class="sxs-lookup"><span data-stu-id="0527c-125">**Windows Identity Foundation**   Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server-to-server authentication scenarios.</span></span> <span data-ttu-id="0527c-126">若要確認您的電腦上已安裝該檔案，請移至 [控制台]，按一下 [**程式和功能**]、[**查看已安裝的更新**]，然後在 [ **Microsoft Windows**] 下查看。</span><span class="sxs-lookup"><span data-stu-id="0527c-126">To verify that it has already been installed on your computer, go to Control Panel, click **Programs and Features**, **View installed updates**, and look under **Microsoft Windows**.</span></span> <span data-ttu-id="0527c-127">如需安裝 Windows 身分識別基礎的詳細[http://go.microsoft.com/fwlink/p/?linkId=204657](http://go.microsoft.com/fwlink/p/?linkid=204657)資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="0527c-127">For details about installing Windows Identity Foundation, see [http://go.microsoft.com/fwlink/p/?linkId=204657](http://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="0527c-128">**Microsoft .net Framework 4.5**   Lync Server 2013 需要64位版本的 Microsoft .net Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="0527c-128">**Microsoft .NET Framework 4.5**   The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

  - <span data-ttu-id="0527c-129">**資料庫伺服器**   的必備軟體有關資料庫伺服器（包括後端資料庫、封存資料庫及監視資料庫）所需 Windows 更新的詳細資料，請參閱 SQL Server 2012 檔[http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015)。</span><span class="sxs-lookup"><span data-stu-id="0527c-129">**Prerequisite software for database servers**   For details about the Windows Update required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation at [http://go.microsoft.com/fwlink/p/?linkId=218015](http://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="0527c-130">Lync Server 2013 會在每個標準版 server 上自動安裝 Microsoft SQL Server 2012 Express，並在每個伺服器上執行本機配置儲存所在的 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="0527c-130">Lync Server 2013 automatically installs Microsoft SQL Server 2012 Express on each Standard Edition server and each server running Lync Server 2013 on which the local configuration store is located.</span></span>

    
    </div>

  - <span data-ttu-id="0527c-131">**Windows media 格式運行**   時間所有要部署會議的前端伺服器和標準版伺服器，都必須安裝 Windows Media 執行時間執行時間。</span><span class="sxs-lookup"><span data-stu-id="0527c-131">**Windows Media Format Runtime**   All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed.</span></span> <span data-ttu-id="0527c-132">您必須具備 Windows Media 格式執行時間，才能執行通話駐留、宣告及回應群組應用程式的 Windows Media 音訊（.wma）檔案，以便在公告和音樂中播放。</span><span class="sxs-lookup"><span data-stu-id="0527c-132">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="0527c-133">針對 Windows Server 2012 和 Windows Server 2012 R2，Windows Media 格式執行時間會與 Microsoft 媒體基礎一起安裝。</span><span class="sxs-lookup"><span data-stu-id="0527c-133">For Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="0527c-134">針對 Windows Server&nbsp;2008 和 windows server&nbsp;2008&nbsp;R2，windows Media 格式執行時間會安裝為 windows 桌面體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="0527c-134">For Windows Server&nbsp;2008 and Windows Server&nbsp;2008&nbsp;R2 the Windows Media Format Runtime installs as part of the Windows Desktop Experience.</span></span> <span data-ttu-id="0527c-135">建議您先安裝 Windows 桌面體驗，然後再安裝 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="0527c-135">It is recommended that you install Windows Desktop Experience before you install Lync Server 2013.</span></span> <span data-ttu-id="0527c-136">如果 Lync Server 2013 在伺服器上找不到這個軟體，系統會提示您安裝它，然後您必須重新開機伺服器才能完成安裝。</span><span class="sxs-lookup"><span data-stu-id="0527c-136">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

