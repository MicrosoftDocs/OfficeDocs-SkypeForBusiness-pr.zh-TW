---
title: Lync Server 2013：發行拓撲的需求
description: Lync Server 2013：發行拓撲的需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5699657e680b78587b8ba354e9dc538f2e280c56
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577859"
---
# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a><span data-ttu-id="dd905-103">在 Lync Server 2013 中發行拓撲的需求</span><span class="sxs-lookup"><span data-stu-id="dd905-103">Requirements to publish a topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd905-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="dd905-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="dd905-105">本主題說明使用拓撲產生器或 Lync Server 2013 管理命令介面命令列介面，發佈拓撲特有的基礎結構和軟體需求。</span><span class="sxs-lookup"><span data-stu-id="dd905-105">This topic describes the infrastructure and software requirements that are specific to publishing a topology, whether by using Topology Builder or the Lync Server 2013 Management Shell command-line interface.</span></span> <span data-ttu-id="dd905-106">這些需求是除了適用于所有 Lync Server 2013 系統管理工具的一般作業系統、軟體和許可權要求之外。</span><span class="sxs-lookup"><span data-stu-id="dd905-106">These requirements are in addition to the general operating system, software, and permissions requirements applicable to all Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="dd905-107">在發行拓撲之前，請務必先滿足所有的系統管理工具需求。</span><span class="sxs-lookup"><span data-stu-id="dd905-107">Make sure that you satisfy all administrative tools requirements before you publish a topology.</span></span>

  - <span data-ttu-id="dd905-108">您必須在已加入的電腦上，執行拓撲產生器，以加入您所建立之 Lync Server 2013 部署的相同網域或樹系，以便 Active Directory 網域服務準備步驟已經完成，讓您能夠在該電腦上使用系統管理工具，以順利發行您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="dd905-108">You must run Topology Builder on a computer that is joined to the same domain or forest of the Lync Server 2013 deployment you are creating so that Active Directory Domain Services preparation steps are already completed, enabling you to use the administrative tools on that computer to successfully publish your topology.</span></span>

  - <span data-ttu-id="dd905-109">拓撲中定義的電腦必須加入網域，而不是 Edge Server 和 AD DS 中。</span><span class="sxs-lookup"><span data-stu-id="dd905-109">The computers defined in the topology must be joined to the domain, except for Edge Servers, and in AD DS.</span></span> <span data-ttu-id="dd905-110">不過，當您發佈拓撲時，電腦不需要線上。</span><span class="sxs-lookup"><span data-stu-id="dd905-110">However, the computers do not need to be online when you publish the topology.</span></span>

  - <span data-ttu-id="dd905-111">您必須建立集區的檔案共用，並可供遠端使用者使用。</span><span class="sxs-lookup"><span data-stu-id="dd905-111">The file share for the pool must be created and available to remote users.</span></span>

  - <span data-ttu-id="dd905-112">為了發佈 Enterprise Edition 前端集區，SQL Server 型後端伺服器必須加入您要在其中部署伺服器的網域，線上，並以適當的防火牆規則加以設定，讓遠端使用者可以使用該伺服器。</span><span class="sxs-lookup"><span data-stu-id="dd905-112">In order to publish an Enterprise Edition Front End pool, the SQL Server-based Back End Server must be joined to the domain in which you are deploying the servers, online, and configured with the appropriate firewall rules to make it available to remote users.</span></span> <span data-ttu-id="dd905-113">如需指定防火牆例外狀況的詳細資訊，請參閱 [瞭解 SQL Server 的防火牆需求（含 Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)）。</span><span class="sxs-lookup"><span data-stu-id="dd905-113">For details about specifying firewall exceptions, see [Understanding firewall requirements for SQL Server with Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span></span> <span data-ttu-id="dd905-114">如需有關設定 SQL Server 的其他詳細資訊，請參閱 [CONFIGURE Sql Server For Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="dd905-114">For other details about configuring SQL Server, see [Configure SQL Server for Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dd905-115">Standard Edition server 具有可接受發佈設定的組合資料庫。</span><span class="sxs-lookup"><span data-stu-id="dd905-115">Standard Edition server has a collocated database that will accept the published configuration.</span></span> <span data-ttu-id="dd905-116">您必須先在 Lync Server 部署嚮導中執行 [ <STRONG>準備第一個 Standard Edition server</STRONG> 安裝程式] 工作。</span><span class="sxs-lookup"><span data-stu-id="dd905-116">You must first run the <STRONG>Prepare first Standard Edition server</STRONG> setup task in the Lync Server Deployment Wizard.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="dd905-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="dd905-117">See Also</span></span>


[<span data-ttu-id="dd905-118">在 Lync Server 2013 中發佈拓撲</span><span class="sxs-lookup"><span data-stu-id="dd905-118">Publish the topology in Lync Server 2013</span></span>](lync-server-2013-publish-the-topology.md)  
[<span data-ttu-id="dd905-119">在 Lync Server 2013 中委派設定許可權</span><span class="sxs-lookup"><span data-stu-id="dd905-119">Delegate setup permissions in Lync Server 2013</span></span>](lync-server-2013-delegate-setup-permissions.md)  


[<span data-ttu-id="dd905-120">Lync Server 2013 中的系統管理工具軟體需求</span><span class="sxs-lookup"><span data-stu-id="dd905-120">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
[<span data-ttu-id="dd905-121">Lync Server 2013 中的伺服器和工具作業系統支援</span><span class="sxs-lookup"><span data-stu-id="dd905-121">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="dd905-122">安裝和管理 Lync Server 2013 時所需的系統管理員許可權</span><span class="sxs-lookup"><span data-stu-id="dd905-122">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

