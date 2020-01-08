---
title: Lync Server 2013：增強及保護資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 265ca1058b4f3b41c5f0dbc4c5b2cdcd631fa911
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40973978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a><span data-ttu-id="ac2b2-102">增強及保護 Lync Server 2013 的資料庫</span><span class="sxs-lookup"><span data-stu-id="ac2b2-102">Hardening and protecting the databases of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac2b2-103">_**主題上次修改日期：** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="ac2b2-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="ac2b2-104">Microsoft Lync Server 2013 也依賴 SQL Server 資料庫來儲存使用者資訊、會議狀態、封存資料，以及通話詳細資料記錄（CDRs）。</span><span class="sxs-lookup"><span data-stu-id="ac2b2-104">Microsoft Lync Server 2013 also depends on SQL Server databases for storing user information, conference state, archiving data, and Call Detail Records (CDRs).</span></span> <span data-ttu-id="ac2b2-105">您可以在 Lync Server 後端資料庫上最大限度地發揮 Lync Server 2013 資料的可用性，方法是將應用程式資料分割成可改善容錯及簡化疑難排解的方式。</span><span class="sxs-lookup"><span data-stu-id="ac2b2-105">You can maximize the availability of Lync Server 2013 data on Lync Server back-end databases, by partitioning the application data in a way that improves fault tolerance and simplifies troubleshooting.</span></span> <span data-ttu-id="ac2b2-106">若要實現這些目標，請依以下方式將應用程式資料分區：</span><span class="sxs-lookup"><span data-stu-id="ac2b2-106">To achieve these goals, partition the application data by:</span></span>

  - <span data-ttu-id="ac2b2-107">**使用伺服器分區最佳做法**   ，將您的作業系統、應用程式和程式檔案與資料檔案分開。</span><span class="sxs-lookup"><span data-stu-id="ac2b2-107">**Using server partitioning best practices**   Separate your operating system, application, and program files from your data files.</span></span>

  - <span data-ttu-id="ac2b2-108">**儲存事務記錄檔檔案和資料庫**   檔案會分別儲存這些檔案，以提升容錯能力並將其儲存在加密的磁片或卷上。</span><span class="sxs-lookup"><span data-stu-id="ac2b2-108">**Storing transaction log files and database files**   Store these files separately to increase fault tolerance and optimize recovery, and store them on an encrypted disk or volume.</span></span>

  - <span data-ttu-id="ac2b2-109">**使用伺服器叢集**   群集後端伺服器來優化 Lync server 2013 系統可用性。</span><span class="sxs-lookup"><span data-stu-id="ac2b2-109">**Using server clustering**   Cluster the back-end servers to optimize Lync Server 2013 system availability.</span></span>

  - <span data-ttu-id="ac2b2-110">**確保所有資料備份都已加密且已正確處理**   遺失、廢棄或放錯位置的備份媒體，可能會對 Lync Server 2013 部署的資料安全性造成重大威脅</span><span class="sxs-lookup"><span data-stu-id="ac2b2-110">**Ensure that all data backups are encrypted and properly handled**   Lost, discarded, or misplaced backup media can pose a significant threat to data security for Lync Server 2013 deployments</span></span>

<span data-ttu-id="ac2b2-111">在任何 Lync Server 2013 Server （標準版 server）之外，不能遠端存取 SQL Server Express 實例（RTCLOCAL 實例），也不會建立任何本機防火牆例外狀況，除了標準版伺服器上的 SQL Server Express 外。</span><span class="sxs-lookup"><span data-stu-id="ac2b2-111">On any Lync Server 2013 server except Standard Edition server, the SQL Server Express instance (RTCLOCAL instance) is not remotely accessible, and no local firewall exceptions are created, except for SQL Server Express on a Standard Edition server.</span></span> <span data-ttu-id="ac2b2-112">在標準版伺服器上，後端資料庫和中央管理商店（CMS）都設定為可供遠端存取。</span><span class="sxs-lookup"><span data-stu-id="ac2b2-112">On a Standard Edition server, both the back-end database and the Central Management store (CMS) are set up to be remotely accessible.</span></span> <span data-ttu-id="ac2b2-113">若要強化 SQL Server 資料庫，您可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ac2b2-113">To harden SQL Server databases, you can do the following:</span></span>

  - <span data-ttu-id="ac2b2-114">在標準版伺服器上自訂 SQL Server Express 防火牆，限制可遠端存取資料庫的伺服器範圍。</span><span class="sxs-lookup"><span data-stu-id="ac2b2-114">Customize the SQL Server Express firewall on Standard Edition servers, limiting the scope of servers that can remotely access the database.</span></span> <span data-ttu-id="ac2b2-115">根據預設，任何 IP 位址都可以遠端存取資料庫。</span><span class="sxs-lookup"><span data-stu-id="ac2b2-115">By default, any IP address can remotely access the database.</span></span>

  - <span data-ttu-id="ac2b2-116">使用 SQL Server Configuration Manager 來指定 SQL Server 遠端存取的通訊協定、IP 位址和埠：</span><span class="sxs-lookup"><span data-stu-id="ac2b2-116">Use SQL Server Configuration Manager to specify the protocols, IP addresses, and ports for SQL Server remote access:</span></span>
    
      - <span data-ttu-id="ac2b2-117">Lync Server 2013 使用 TCP/IP 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="ac2b2-117">Lync Server 2013 uses the TCP/IP protocol.</span></span> <span data-ttu-id="ac2b2-118">它支援 IP 版本4（IPv4），但不支援 IP 版本6（IPv6）。</span><span class="sxs-lookup"><span data-stu-id="ac2b2-118">It supports IP version 4 (IPv4), but not IP version 6 (IPv6).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ac2b2-119">在啟用雙 IP 堆疊的網路中，Lync Server 2013 可以正常運作。</span><span class="sxs-lookup"><span data-stu-id="ac2b2-119">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

        
        </div>
    
      - <span data-ttu-id="ac2b2-120">Lync Server 2013 支援多個 IP 位址（多穴網路位址卡）。</span><span class="sxs-lookup"><span data-stu-id="ac2b2-120">Lync Server 2013 supports multiple IP address (multi-homed network address cards).</span></span> <span data-ttu-id="ac2b2-121">您可以指定 SQL Server 只偵聽特定 IP 位址（個別位址或子網），而只使用特定的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="ac2b2-121">You can specify that SQL Server listen only to specific IP addresses (individual address or by subnet) and only use specific protocols.</span></span>
    
      - <span data-ttu-id="ac2b2-122">Lync Server 2013 支援靜態和動態 SQL Server 埠。</span><span class="sxs-lookup"><span data-stu-id="ac2b2-122">Lync Server 2013 supports static and dynamic SQL Server ports.</span></span>

  - <span data-ttu-id="ac2b2-123">在靜態（非預設）埠上執行 SQL Server，不執行 SQL Server Browser （因此無法將偵聽埠向用戶端報告）。</span><span class="sxs-lookup"><span data-stu-id="ac2b2-123">Run SQL Server on a static (non-default) port, and do not run SQL Server Browser (so it cannot report the listening port to the client).</span></span> <span data-ttu-id="ac2b2-124">這需要每個 SQL Server 用戶端的自訂設定，包括前端伺服器、監視伺服器、封存伺服器以及管理主控台（執行 Lync Server 管理命令介面、Lync Server 控制台或拓撲建立器），以及所有其他運行 Lync Server 資料庫的伺服器）。</span><span class="sxs-lookup"><span data-stu-id="ac2b2-124">This requires a custom configuration on each SQL Server client, including Front End Servers, Monitoring Server, Archiving Server, and administrative consoles (running Lync Server Management Shell, Lync Server Control Panel, or Topology Builder), and all other servers running Lync Server databases).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ac2b2-125">必須將資料庫的存取許可權制為受信任的資料庫系統管理員。</span><span class="sxs-lookup"><span data-stu-id="ac2b2-125">Access to databases must be limited to trusted database administrators.</span></span> <span data-ttu-id="ac2b2-126">惡意資料庫管理員可以將資料插入或修改到資料庫，以透過 Lync Server 2013 伺服器取得許可權，或從服務取得機密資訊，即使資料庫管理員尚未獲授與您的直接存取權或Lync Server 2013 伺服器的控制權。</span><span class="sxs-lookup"><span data-stu-id="ac2b2-126">A malicious database administrator could insert or modify data into the databases to acquire privileges over the Lync Server 2013 servers or obtain sensitive information from the services, even if the database administrator has not been granted direct access or control of the Lync Server 2013 servers.</span></span>



</div>

<span data-ttu-id="ac2b2-127">如需自訂設定及強化 SQL Server 資料庫的詳細資料，請參閱 NextHop 博客文章：「使用 Lync Server 2010 與自訂 SQL Server 網路設定[http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008)」。</span><span class="sxs-lookup"><span data-stu-id="ac2b2-127">For details about custom configurations and hardening SQL Server databases, see the NextHop blog article, "Using Lync Server 2010 with a Custom SQL Server Network Configuration," at [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ac2b2-128">您也可以加強作業系統和應用程式伺服器，而且您可以使用群組原則來在 Lync Server 部署中執行安全性 lockdowns。</span><span class="sxs-lookup"><span data-stu-id="ac2b2-128">You can also harden operating systems and applications servers, and you can use Group Policy to implement security lockdowns in your Lync Server deployment.</span></span> <span data-ttu-id="ac2b2-129">如需詳細資訊，請參閱<A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">強化及保護 Lync Server 2013 的伺服器和應用程式</A>。</span><span class="sxs-lookup"><span data-stu-id="ac2b2-129">For details, see <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Hardening and protecting servers and applications for Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

