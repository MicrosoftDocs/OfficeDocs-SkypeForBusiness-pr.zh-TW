---
title: Lync Server 2013： 增強及保護資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e1ef045253f6733ea3356baa6254a6c90926762
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a><span data-ttu-id="277f3-102">增強及保護 Lync Server 2013 的資料庫</span><span class="sxs-lookup"><span data-stu-id="277f3-102">Hardening and protecting the databases of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="277f3-103">_**上次修改主題：** 2013年-12-05_</span><span class="sxs-lookup"><span data-stu-id="277f3-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="277f3-104">Microsoft Lync Server 2013 也取決於用來儲存使用者資訊、 會議狀態，封存資料和詳細通話記錄 (Cdr) 的 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="277f3-104">Microsoft Lync Server 2013 also depends on SQL Server databases for storing user information, conference state, archiving data, and Call Detail Records (CDRs).</span></span> <span data-ttu-id="277f3-105">您可以藉由分割應用程式資料的方式，提高容錯性及簡化疑難排解最大化 Lync Server 後端資料庫上的 Lync Server 2013 資料的可用性。</span><span class="sxs-lookup"><span data-stu-id="277f3-105">You can maximize the availability of Lync Server 2013 data on Lync Server back-end databases, by partitioning the application data in a way that improves fault tolerance and simplifies troubleshooting.</span></span> <span data-ttu-id="277f3-106">若要達到這些目標，分割應用程式資料：</span><span class="sxs-lookup"><span data-stu-id="277f3-106">To achieve these goals, partition the application data by:</span></span>

  - <span data-ttu-id="277f3-107">**使用伺服器分割最佳做法**   分隔您的作業系統、 應用程式及程式檔案與資料檔案。</span><span class="sxs-lookup"><span data-stu-id="277f3-107">**Using server partitioning best practices**   Separate your operating system, application, and program files from your data files.</span></span>

  - <span data-ttu-id="277f3-108">**儲存交易記錄檔和資料庫檔案**   儲存這些檔案分開以提高容錯性及復原，並將它們儲存到加密的磁碟或磁碟區上。</span><span class="sxs-lookup"><span data-stu-id="277f3-108">**Storing transaction log files and database files**   Store these files separately to increase fault tolerance and optimize recovery, and store them on an encrypted disk or volume.</span></span>

  - <span data-ttu-id="277f3-109">**使用伺服器叢集**   叢集以最佳化 Lync Server 2013 系統的可用性的後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="277f3-109">**Using server clustering**   Cluster the back-end servers to optimize Lync Server 2013 system availability.</span></span>

  - <span data-ttu-id="277f3-110">**確定所有資料備份會加密及正確地處理**   遺失，已捨棄，或找不到備份媒體可能會造成重大威脅 Lync Server 2013 部署的資料安全性</span><span class="sxs-lookup"><span data-stu-id="277f3-110">**Ensure that all data backups are encrypted and properly handled**   Lost, discarded, or misplaced backup media can pose a significant threat to data security for Lync Server 2013 deployments</span></span>

<span data-ttu-id="277f3-111">任何 Lync Server 2013 伺服器上除了 Standard Edition server，SQL Server Express 的執行個體 （RTCLOCAL 執行個體） 從遠端存取，並不會建立沒有本機防火牆例外狀況，但不包括在 Standard Edition server 上的 SQL Server Express。</span><span class="sxs-lookup"><span data-stu-id="277f3-111">On any Lync Server 2013 server except Standard Edition server, the SQL Server Express instance (RTCLOCAL instance) is not remotely accessible, and no local firewall exceptions are created, except for SQL Server Express on a Standard Edition server.</span></span> <span data-ttu-id="277f3-112">在 Standard Edition server、 後端資料庫及中央管理存放區 (CMS) 設為可從遠端存取。</span><span class="sxs-lookup"><span data-stu-id="277f3-112">On a Standard Edition server, both the back-end database and the Central Management store (CMS) are set up to be remotely accessible.</span></span> <span data-ttu-id="277f3-113">若要強化 SQL Server 資料庫，您可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="277f3-113">To harden SQL Server databases, you can do the following:</span></span>

  - <span data-ttu-id="277f3-114">自訂 Standard Edition 伺服器，限制的範圍可以從遠端存取資料庫的伺服器上的 SQL Server Express 防火牆。</span><span class="sxs-lookup"><span data-stu-id="277f3-114">Customize the SQL Server Express firewall on Standard Edition servers, limiting the scope of servers that can remotely access the database.</span></span> <span data-ttu-id="277f3-115">根據預設，任何 IP 位址可以從遠端存取資料庫。</span><span class="sxs-lookup"><span data-stu-id="277f3-115">By default, any IP address can remotely access the database.</span></span>

  - <span data-ttu-id="277f3-116">使用 SQL Server 組態管理員指定的通訊協定、 IP 位址和 SQL Server 遠端存取的連接埠：</span><span class="sxs-lookup"><span data-stu-id="277f3-116">Use SQL Server Configuration Manager to specify the protocols, IP addresses, and ports for SQL Server remote access:</span></span>
    
      - <span data-ttu-id="277f3-117">Lync Server 2013 使用 TCP/IP 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="277f3-117">Lync Server 2013 uses the TCP/IP protocol.</span></span> <span data-ttu-id="277f3-118">它支援 IP 版本 4 (IPv4)，而非 IP 第 6 版 (IPv6)。</span><span class="sxs-lookup"><span data-stu-id="277f3-118">It supports IP version 4 (IPv4), but not IP version 6 (IPv6).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="277f3-119">Lync Server 2013 可以在啟用雙重 IP 堆疊的網路中運作。</span><span class="sxs-lookup"><span data-stu-id="277f3-119">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

        
        </div>
    
      - <span data-ttu-id="277f3-120">Lync Server 2013 支援多個 IP 位址 （多重網路地址卡）。</span><span class="sxs-lookup"><span data-stu-id="277f3-120">Lync Server 2013 supports multiple IP address (multi-homed network address cards).</span></span> <span data-ttu-id="277f3-121">您可以指定特定 IP 位址只有該 SQL Server 接聽 (個別的地址或子網路)，並只使用特定的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="277f3-121">You can specify that SQL Server listen only to specific IP addresses (individual address or by subnet) and only use specific protocols.</span></span>
    
      - <span data-ttu-id="277f3-122">Lync Server 2013 支援靜態及動態的 SQL Server 連接埠。</span><span class="sxs-lookup"><span data-stu-id="277f3-122">Lync Server 2013 supports static and dynamic SQL Server ports.</span></span>

  - <span data-ttu-id="277f3-123">靜態 （非預設值） 連接埠上執行 SQL Server，但不要執行 SQL Server Browser （讓它不能用戶端報告的聆聽連接埠）。</span><span class="sxs-lookup"><span data-stu-id="277f3-123">Run SQL Server on a static (non-default) port, and do not run SQL Server Browser (so it cannot report the listening port to the client).</span></span> <span data-ttu-id="277f3-124">這需要在每個 SQL Server 用戶端，其中包括前端伺服器、 監控伺服器、 封存伺服器，以及系統管理主控台 （執行 Lync Server 管理命令介面，Lync Server Control Panel 或拓撲產生器]），和所有其他自訂設定伺服器執行 Lync Server 資料庫）。</span><span class="sxs-lookup"><span data-stu-id="277f3-124">This requires a custom configuration on each SQL Server client, including Front End Servers, Monitoring Server, Archiving Server, and administrative consoles (running Lync Server Management Shell, Lync Server Control Panel, or Topology Builder), and all other servers running Lync Server databases).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="277f3-125">存取資料庫必須受限於受信任的資料庫管理員。</span><span class="sxs-lookup"><span data-stu-id="277f3-125">Access to databases must be limited to trusted database administrators.</span></span> <span data-ttu-id="277f3-126">惡意資料庫管理員無法插入或修改資料到以取得權限在 Lync Server 2013 伺服器上或從服務，取得敏感資訊的資料庫，即使不已直接存取授與資料庫系統管理員或Lync Server 2013 伺服器的控制項。</span><span class="sxs-lookup"><span data-stu-id="277f3-126">A malicious database administrator could insert or modify data into the databases to acquire privileges over the Lync Server 2013 servers or obtain sensitive information from the services, even if the database administrator has not been granted direct access or control of the Lync Server 2013 servers.</span></span>



</div>

<span data-ttu-id="277f3-127">如需自訂設定及強化 SQL Server 資料庫的詳細資訊，請參閱 NextHop 部落格文章，「 使用 Lync Server 2010 搭配自訂 SQL Server 網路組態，「 在[http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008)。</span><span class="sxs-lookup"><span data-stu-id="277f3-127">For details about custom configurations and hardening SQL Server databases, see the NextHop blog article, "Using Lync Server 2010 with a Custom SQL Server Network Configuration," at [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="277f3-128">您也可以強化作業系統與應用程式伺服器，您可以使用群組原則實作安全性鎖定 Lync Server 部署中。</span><span class="sxs-lookup"><span data-stu-id="277f3-128">You can also harden operating systems and applications servers, and you can use Group Policy to implement security lockdowns in your Lync Server deployment.</span></span> <span data-ttu-id="277f3-129">如需詳細資訊，請參閱<A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">強化和保護伺服器及 Lync Server 2013 的應用程式</A>。</span><span class="sxs-lookup"><span data-stu-id="277f3-129">For details, see <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Hardening and protecting servers and applications for Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

