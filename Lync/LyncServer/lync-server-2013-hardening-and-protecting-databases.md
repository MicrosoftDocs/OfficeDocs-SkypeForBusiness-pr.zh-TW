---
title: Lync Server 2013：強化及保護資料庫
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
ms.openlocfilehash: 0254c77bb276add6f55ccff623c1fc2bec590102
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536910"
---
# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a><span data-ttu-id="b5521-102">強化及保護 Lync Server 2013 的資料庫</span><span class="sxs-lookup"><span data-stu-id="b5521-102">Hardening and protecting the databases of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5521-103">_**主題上次修改日期：** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="b5521-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="b5521-104">Microsoft Lync Server 2013 也取決於 SQL Server 資料庫，以儲存使用者資訊、會議狀態、封存資料，以及 (Cdr) 的詳細通話記錄。</span><span class="sxs-lookup"><span data-stu-id="b5521-104">Microsoft Lync Server 2013 also depends on SQL Server databases for storing user information, conference state, archiving data, and Call Detail Records (CDRs).</span></span> <span data-ttu-id="b5521-105">您可以透過分割應用程式資料的方式，以提升容錯和簡化疑難排解的方式，以最大化 lync server 後端資料庫上的 Lync Server 2013 資料的可用性。</span><span class="sxs-lookup"><span data-stu-id="b5521-105">You can maximize the availability of Lync Server 2013 data on Lync Server back-end databases, by partitioning the application data in a way that improves fault tolerance and simplifies troubleshooting.</span></span> <span data-ttu-id="b5521-106">若要達到這些目標，請依下列方式分割應用程式資料：</span><span class="sxs-lookup"><span data-stu-id="b5521-106">To achieve these goals, partition the application data by:</span></span>

  - <span data-ttu-id="b5521-107">**使用伺服器分割最佳作法**    從資料檔案中分隔您的作業系統、應用程式和程式檔案。</span><span class="sxs-lookup"><span data-stu-id="b5521-107">**Using server partitioning best practices**   Separate your operating system, application, and program files from your data files.</span></span>

  - <span data-ttu-id="b5521-108">**儲存交易記錄檔和資料庫檔案**    請分開儲存這些檔案，以提升容錯能力及優化復原，並將其儲存在加密的磁片或磁片區。</span><span class="sxs-lookup"><span data-stu-id="b5521-108">**Storing transaction log files and database files**   Store these files separately to increase fault tolerance and optimize recovery, and store them on an encrypted disk or volume.</span></span>

  - <span data-ttu-id="b5521-109">**使用伺服器集群**    將後端伺服器集群集中，以優化 Lync Server 2013 系統可用性。</span><span class="sxs-lookup"><span data-stu-id="b5521-109">**Using server clustering**   Cluster the back-end servers to optimize Lync Server 2013 system availability.</span></span>

  - <span data-ttu-id="b5521-110">**確定所有資料備份已加密且已正確處理**    遺失、捨棄或錯放備份媒體可能會對 Lync Server 2013 部署的資料安全性造成重大威脅。</span><span class="sxs-lookup"><span data-stu-id="b5521-110">**Ensure that all data backups are encrypted and properly handled**   Lost, discarded, or misplaced backup media can pose a significant threat to data security for Lync Server 2013 deployments</span></span>

<span data-ttu-id="b5521-111">在任何 Lync Server 2013 Server 上，除了 Standard Edition server 之外，無法從遠端存取 RTCLOCAL 實例) 的 SQL Server Express (實例，也不會建立本機防火牆例外狀況，但在 Standard Edition Server 上的 SQL Server Express 除外。</span><span class="sxs-lookup"><span data-stu-id="b5521-111">On any Lync Server 2013 server except Standard Edition server, the SQL Server Express instance (RTCLOCAL instance) is not remotely accessible, and no local firewall exceptions are created, except for SQL Server Express on a Standard Edition server.</span></span> <span data-ttu-id="b5521-112">在 Standard Edition server 上，後端資料庫與中央管理存放區 (CMS) 會設定為可遠端存取。</span><span class="sxs-lookup"><span data-stu-id="b5521-112">On a Standard Edition server, both the back-end database and the Central Management store (CMS) are set up to be remotely accessible.</span></span> <span data-ttu-id="b5521-113">若要強化 SQL Server 資料庫，您可以執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="b5521-113">To harden SQL Server databases, you can do the following:</span></span>

  - <span data-ttu-id="b5521-114">自訂 Standard Edition server 上的 SQL Server Express 防火牆，以限制可遠端存取資料庫的伺服器範圍。</span><span class="sxs-lookup"><span data-stu-id="b5521-114">Customize the SQL Server Express firewall on Standard Edition servers, limiting the scope of servers that can remotely access the database.</span></span> <span data-ttu-id="b5521-115">根據預設，任何 IP 位址都可以遠端存取資料庫。</span><span class="sxs-lookup"><span data-stu-id="b5521-115">By default, any IP address can remotely access the database.</span></span>

  - <span data-ttu-id="b5521-116">使用 SQL Server Configuration Manager 指定 SQL Server 遠端存取的通訊協定、IP 位址及埠：</span><span class="sxs-lookup"><span data-stu-id="b5521-116">Use SQL Server Configuration Manager to specify the protocols, IP addresses, and ports for SQL Server remote access:</span></span>
    
      - <span data-ttu-id="b5521-117">Lync Server 2013 使用 TCP/IP 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="b5521-117">Lync Server 2013 uses the TCP/IP protocol.</span></span> <span data-ttu-id="b5521-118">它支援 IP 版本 4 (IPv4) ，但不支援 IP 版本 6 (IPv6) 。</span><span class="sxs-lookup"><span data-stu-id="b5521-118">It supports IP version 4 (IPv4), but not IP version 6 (IPv6).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b5521-119">在啟用雙重 IP 堆疊的網路中，Lync Server 2013 可以運作。</span><span class="sxs-lookup"><span data-stu-id="b5521-119">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

        
        </div>
    
      - <span data-ttu-id="b5521-120">Lync Server 2013 支援多個 IP 位址 (多穴網路位址卡) 。</span><span class="sxs-lookup"><span data-stu-id="b5521-120">Lync Server 2013 supports multiple IP address (multi-homed network address cards).</span></span> <span data-ttu-id="b5521-121">您可以指定 SQL Server 只聽取特定的 IP 位址 (個別的位址或子網) ，只使用特定的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="b5521-121">You can specify that SQL Server listen only to specific IP addresses (individual address or by subnet) and only use specific protocols.</span></span>
    
      - <span data-ttu-id="b5521-122">Lync Server 2013 支援靜態和動態 SQL Server 埠。</span><span class="sxs-lookup"><span data-stu-id="b5521-122">Lync Server 2013 supports static and dynamic SQL Server ports.</span></span>

  - <span data-ttu-id="b5521-123">在靜態 (非預設) 埠上執行 SQL Server，但不要執行 SQL Server 瀏覽器 (使其無法向用戶端) 報告聆聽埠。</span><span class="sxs-lookup"><span data-stu-id="b5521-123">Run SQL Server on a static (non-default) port, and do not run SQL Server Browser (so it cannot report the listening port to the client).</span></span> <span data-ttu-id="b5521-124">這需要在每個 SQL Server 用戶端上進行自訂設定，包括前端伺服器、監控伺服器、封存伺服器和管理主控台 (執行 Lync Server 管理命令介面、Lync Server 控制台或拓撲產生器) ，以及其他執行 Lync Server 資料庫) 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="b5521-124">This requires a custom configuration on each SQL Server client, including Front End Servers, Monitoring Server, Archiving Server, and administrative consoles (running Lync Server Management Shell, Lync Server Control Panel, or Topology Builder), and all other servers running Lync Server databases).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b5521-125">資料庫的存取權必須限制為受信任的資料庫管理員。</span><span class="sxs-lookup"><span data-stu-id="b5521-125">Access to databases must be limited to trusted database administrators.</span></span> <span data-ttu-id="b5521-126">惡意資料庫管理員可以插入或修改資料庫中的資料，以取得 Lync Server 2013 伺服器的許可權，或從服務取得機密資訊，即使資料庫管理員尚未授與 Lync Server 2013 伺服器的直接存取權或控制權。</span><span class="sxs-lookup"><span data-stu-id="b5521-126">A malicious database administrator could insert or modify data into the databases to acquire privileges over the Lync Server 2013 servers or obtain sensitive information from the services, even if the database administrator has not been granted direct access or control of the Lync Server 2013 servers.</span></span>



</div>

<span data-ttu-id="b5521-127">如需自訂設定及強化 SQL Server 資料庫的詳細資訊，請參閱 NextHop 的博客文章：「使用 Lync Server 2010 搭配自訂 SQL Server 網路設定」 [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008) 。</span><span class="sxs-lookup"><span data-stu-id="b5521-127">For details about custom configurations and hardening SQL Server databases, see the NextHop blog article, "Using Lync Server 2010 with a Custom SQL Server Network Configuration," at [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b5521-128">您也可以強化作業系統與應用程式伺服器，也可以使用群組原則，在 Lync Server 部署中實施安全性鎖定。</span><span class="sxs-lookup"><span data-stu-id="b5521-128">You can also harden operating systems and applications servers, and you can use Group Policy to implement security lockdowns in your Lync Server deployment.</span></span> <span data-ttu-id="b5521-129">如需詳細資訊，請參閱 <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">強化及保護 Lync Server 2013 的伺服器和應用程式</A>。</span><span class="sxs-lookup"><span data-stu-id="b5521-129">For details, see <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Hardening and protecting servers and applications for Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

