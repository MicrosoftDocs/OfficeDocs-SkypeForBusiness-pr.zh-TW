---
title: 階段 8：解除委任舊版集區
description: 階段8：解除委任舊版集區。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: 'Phase 8: Decommission legacy pools'
ms:assetid: 1c68e5d8-fb5f-45e6-b6e3-27f5e830c966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204724(v=OCS.15)
ms:contentKeyID: 48183557
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6414fe97b54ed1b487ff722c6b02d4904443841
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563749"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="4ee5b-103">階段 8：解除委任舊版集區</span><span class="sxs-lookup"><span data-stu-id="4ee5b-103">Phase 8: Decommission legacy pools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ee5b-104">_**主題上次修改日期：** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="4ee5b-104">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="4ee5b-105">下列主題提供更新 DNS 專案、移動內容管理伺服器、解除委任集區，以及停用 Lync Server 2010 之舊版部署中的伺服器及集區的指導方針。</span><span class="sxs-lookup"><span data-stu-id="4ee5b-105">The following topic provides guidance in updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Lync Server 2010.</span></span> <span data-ttu-id="4ee5b-106">本節所列的程序並非全為必要程序。</span><span class="sxs-lookup"><span data-stu-id="4ee5b-106">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="4ee5b-107">請閱讀文件並判斷應使用哪些解除委任程序。</span><span class="sxs-lookup"><span data-stu-id="4ee5b-107">Read the documentation and determine which decommissioning procedure to use.</span></span>

<span data-ttu-id="4ee5b-108">如需移除 Lync Server 2010 伺服器和伺服器角色的完整覆蓋範圍，以及解除委任 Lync Server 2010 部署的逐步指南，請參閱「卸載 Microsoft Lync Server 2010 及移除伺服器角色」（可以從該位置下載） [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227) 。</span><span class="sxs-lookup"><span data-stu-id="4ee5b-108">For exhaustive coverage of removing Lync Server 2010 servers and server roles, and a step-by-step guide to decommissioning a Lync Server 2010 deployment, see "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4ee5b-109">如需遷移和升級 Microsoft 整合通訊 Managed API (UCMA) 應用程式的資訊，在解除委任舊版環境之前，請參閱 <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="4ee5b-109">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4ee5b-110">本章節內容</span><span class="sxs-lookup"><span data-stu-id="4ee5b-110">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="4ee5b-111">更新 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="4ee5b-111">Update DNS SRV records</span></span>](update-dns-srv-records.md)

  - <span></span>  
    [<span data-ttu-id="4ee5b-112">將 Lync Server 2010 中央管理伺服器移至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ee5b-112">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>](move-the-lync-server-2010-central-management-server-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="4ee5b-113">移動會議目錄</span><span class="sxs-lookup"><span data-stu-id="4ee5b-113">Move Conference Directories</span></span>](move-lync-server-2010-conference-directories-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="4ee5b-114">移除封存伺服器關聯</span><span class="sxs-lookup"><span data-stu-id="4ee5b-114">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)

  - <span></span>  
    [<span data-ttu-id="4ee5b-115">移除監控伺服器關聯</span><span class="sxs-lookup"><span data-stu-id="4ee5b-115">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)

  - <span></span>  
    [<span data-ttu-id="4ee5b-116">移除 Enterprise Edition 前端伺服器或 Standard Edition 前端伺服器</span><span class="sxs-lookup"><span data-stu-id="4ee5b-116">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-enterprise-edition-front-end-server-or-standard-edition-front-end-server.md)

  - <span></span>  
    [<span data-ttu-id="4ee5b-117">移除後端伺服器上的 SQL Server 執行個體與資料庫</span><span class="sxs-lookup"><span data-stu-id="4ee5b-117">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

