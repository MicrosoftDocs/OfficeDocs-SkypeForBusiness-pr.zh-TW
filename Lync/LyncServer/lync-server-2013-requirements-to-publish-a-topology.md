---
title: Lync Server 2013：發行拓撲的需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02e90604315732d9e9bfe4c45968ff0bcf5fbd2e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a><span data-ttu-id="973c8-102">在 Lync Server 2013 中發行拓撲的需求</span><span class="sxs-lookup"><span data-stu-id="973c8-102">Requirements to publish a topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="973c8-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="973c8-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="973c8-104">本主題描述發佈拓撲（無論是使用拓撲建立器還是 Lync Server 2013 管理命令列介面）所專用的基礎結構和軟體需求。</span><span class="sxs-lookup"><span data-stu-id="973c8-104">This topic describes the infrastructure and software requirements that are specific to publishing a topology, whether by using Topology Builder or the Lync Server 2013 Management Shell command-line interface.</span></span> <span data-ttu-id="973c8-105">這些需求除了適用于所有 Lync Server 2013 系統管理工具的一般作業系統、軟體和許可權需求之外。</span><span class="sxs-lookup"><span data-stu-id="973c8-105">These requirements are in addition to the general operating system, software, and permissions requirements applicable to all Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="973c8-106">在發佈拓撲前，請務必先滿足所有管理工具的需求。</span><span class="sxs-lookup"><span data-stu-id="973c8-106">Make sure that you satisfy all administrative tools requirements before you publish a topology.</span></span>

  - <span data-ttu-id="973c8-107">您必須在已加入 Lync Server 2013 部署之相同網域或林中的電腦上執行拓撲建立器，讓 Active Directory 網域服務準備步驟已完成，讓您可以使用系統管理工具該電腦成功發佈您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="973c8-107">You must run Topology Builder on a computer that is joined to the same domain or forest of the Lync Server 2013 deployment you are creating so that Active Directory Domain Services preparation steps are already completed, enabling you to use the administrative tools on that computer to successfully publish your topology.</span></span>

  - <span data-ttu-id="973c8-108">在拓撲中定義的電腦，必須加入網域，但邊緣伺服器和 AD DS 中的電腦除外。</span><span class="sxs-lookup"><span data-stu-id="973c8-108">The computers defined in the topology must be joined to the domain, except for Edge Servers, and in AD DS.</span></span> <span data-ttu-id="973c8-109">不過，當您發佈拓朴時，電腦不需要是線上的。</span><span class="sxs-lookup"><span data-stu-id="973c8-109">However, the computers do not need to be online when you publish the topology.</span></span>

  - <span data-ttu-id="973c8-110">您必須建立該池的檔案共用，才能供遠端使用者使用。</span><span class="sxs-lookup"><span data-stu-id="973c8-110">The file share for the pool must be created and available to remote users.</span></span>

  - <span data-ttu-id="973c8-111">若要發佈企業版的 [前端] 池，必須將 SQL Server 的後端伺服器連接至您要部署伺服器的網域、線上，並以適當的防火牆規則加以設定，以便讓遠端使用者使用。</span><span class="sxs-lookup"><span data-stu-id="973c8-111">In order to publish an Enterprise Edition Front End pool, the SQL Server-based Back End Server must be joined to the domain in which you are deploying the servers, online, and configured with the appropriate firewall rules to make it available to remote users.</span></span> <span data-ttu-id="973c8-112">如需指定防火牆例外狀況的詳細資料，請參閱[瞭解使用 Lync Server 2013 的 SQL Server 防火牆需求](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="973c8-112">For details about specifying firewall exceptions, see [Understanding firewall requirements for SQL Server with Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span></span> <span data-ttu-id="973c8-113">如需有關設定 SQL Server 的其他詳細資料，請參閱[設定 Lync server 2013 的 SQL Server](lync-server-2013-configure-sql-server-for-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="973c8-113">For other details about configuring SQL Server, see [Configure SQL Server for Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="973c8-114">標準版伺服器具有可接受已發佈設定的 collocated 資料庫。</span><span class="sxs-lookup"><span data-stu-id="973c8-114">Standard Edition server has a collocated database that will accept the published configuration.</span></span> <span data-ttu-id="973c8-115">您必須先在 Lync Server 部署嚮導中執行 [<STRONG>準備第一個標準版伺服器</STRONG>設定] 工作。</span><span class="sxs-lookup"><span data-stu-id="973c8-115">You must first run the <STRONG>Prepare first Standard Edition server</STRONG> setup task in the Lync Server Deployment Wizard.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="973c8-116">請參閱</span><span class="sxs-lookup"><span data-stu-id="973c8-116">See Also</span></span>


[<span data-ttu-id="973c8-117">在 Lync Server 2013 中發行拓撲</span><span class="sxs-lookup"><span data-stu-id="973c8-117">Publish the topology in Lync Server 2013</span></span>](lync-server-2013-publish-the-topology.md)  
[<span data-ttu-id="973c8-118">在 Lync Server 2013 中委派設定權限</span><span class="sxs-lookup"><span data-stu-id="973c8-118">Delegate setup permissions in Lync Server 2013</span></span>](lync-server-2013-delegate-setup-permissions.md)  


[<span data-ttu-id="973c8-119">Lync Server 2013 中的系統管理工具軟體需求</span><span class="sxs-lookup"><span data-stu-id="973c8-119">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
[<span data-ttu-id="973c8-120">Lync Server 2013 中的伺服器及工具作業系統支援</span><span class="sxs-lookup"><span data-stu-id="973c8-120">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="973c8-121">設定和管理 Lync Server 2013 所需的系統管理員權限</span><span class="sxs-lookup"><span data-stu-id="973c8-121">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

