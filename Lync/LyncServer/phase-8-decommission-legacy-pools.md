---
title: 第 8 階段： 解除委任舊版的集區
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 8: Decommission legacy pools'
ms:assetid: 1c68e5d8-fb5f-45e6-b6e3-27f5e830c966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204724(v=OCS.15)
ms:contentKeyID: 48183557
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58ec7d07725ee75e5f20897894f465ac9fb269a4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="3c86e-102">第 8 階段： 解除委任舊版的集區</span><span class="sxs-lookup"><span data-stu-id="3c86e-102">Phase 8: Decommission legacy pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c86e-103">_**主題上次修改日期：** 2016年-12-08_</span><span class="sxs-lookup"><span data-stu-id="3c86e-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="3c86e-104">下列主題提供更新 DNS 項目、 移動 Content Management Server、 解除委任集區]，並停用和移除舊版部署的 Lync Server 2010 中的伺服器和集區中的指引。</span><span class="sxs-lookup"><span data-stu-id="3c86e-104">The following topic provides guidance in updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Lync Server 2010.</span></span> <span data-ttu-id="3c86e-105">本節所列的程序並非全為必要程序。</span><span class="sxs-lookup"><span data-stu-id="3c86e-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="3c86e-106">請閱讀文件並判斷應使用哪些解除委任程序。</span><span class="sxs-lookup"><span data-stu-id="3c86e-106">Read the documentation and determine which decommissioning procedure to use.</span></span>

<span data-ttu-id="3c86e-107">移除 Lync Server 2010 伺服器和伺服器角色，以及解除委任 Lync Server 2010 部署的逐步指南的詳盡的涵蓋範圍，請參閱 「 解除安裝 Microsoft Lync Server 2010 及移除伺服器角色，「 可以下載在[https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)。</span><span class="sxs-lookup"><span data-stu-id="3c86e-107">For exhaustive coverage of removing Lync Server 2010 servers and server roles, and a step-by-step guide to decommissioning a Lync Server 2010 deployment, see "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3c86e-108">如需移轉與升級 Microsoft Unified Communications Managed API (UCMA) 應用程式]，再解除委任舊版環境，請參閱<A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="3c86e-108">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3c86e-109">本章節內容</span><span class="sxs-lookup"><span data-stu-id="3c86e-109">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="3c86e-110">更新 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="3c86e-110">Update DNS SRV records</span></span>](update-dns-srv-records.md)

  - <span></span>  
    [<span data-ttu-id="3c86e-111">將 Lync Server 2010 中央管理伺服器移至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c86e-111">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>](move-the-lync-server-2010-central-management-server-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="3c86e-112">移動會議目錄</span><span class="sxs-lookup"><span data-stu-id="3c86e-112">Move Conference Directories</span></span>](move-lync-server-2010-conference-directories-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="3c86e-113">移除封存伺服器關聯</span><span class="sxs-lookup"><span data-stu-id="3c86e-113">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)

  - <span></span>  
    [<span data-ttu-id="3c86e-114">移除監控伺服器關聯</span><span class="sxs-lookup"><span data-stu-id="3c86e-114">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)

  - <span></span>  
    [<span data-ttu-id="3c86e-115">移除 Enterprise Edition 前端伺服器或 Standard Edition 前端伺服器</span><span class="sxs-lookup"><span data-stu-id="3c86e-115">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-enterprise-edition-front-end-server-or-standard-edition-front-end-server.md)

  - <span></span>  
    [<span data-ttu-id="3c86e-116">移除 SQL Server 執行個體和後端伺服器上的資料庫</span><span class="sxs-lookup"><span data-stu-id="3c86e-116">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

