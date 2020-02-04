---
title: 階段 8：解除委任舊版集區
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
ms.openlocfilehash: a9c21aa29f2e98aacd3ec68076a21ba2b4d2a76e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="502a7-102">階段 8：解除委任舊版集區</span><span class="sxs-lookup"><span data-stu-id="502a7-102">Phase 8: Decommission legacy pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="502a7-103">_**主題上次修改日期：** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="502a7-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="502a7-104">下列主題提供更新 DNS 專案、移動內容管理伺服器、解除授權池以及停用和移除 Lync Server 2010 傳統部署中的伺服器和池的指導方針。</span><span class="sxs-lookup"><span data-stu-id="502a7-104">The following topic provides guidance in updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Lync Server 2010.</span></span> <span data-ttu-id="502a7-105">並非本節所列的所有程式都是必要的。</span><span class="sxs-lookup"><span data-stu-id="502a7-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="502a7-106">閱讀檔，並判斷要使用的解除授權程式。</span><span class="sxs-lookup"><span data-stu-id="502a7-106">Read the documentation and determine which decommissioning procedure to use.</span></span>

<span data-ttu-id="502a7-107">若要全面瞭解移除 Lync Server 2010 伺服器和伺服器角色，以及解除 Lync Server 2010 部署的逐步指南，請參閱「卸載 Microsoft Lync Server 2010 及移除伺服器角色」（可在[https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)此下載）。</span><span class="sxs-lookup"><span data-stu-id="502a7-107">For exhaustive coverage of removing Lync Server 2010 servers and server roles, and a step-by-step guide to decommissioning a Lync Server 2010 deployment, see "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="502a7-108">如需遷移和升級 Microsoft 整合通訊管理 API （UCMA）應用程式的相關資訊，請參閱在解除舊版環境的授權之前，請參閱<A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="502a7-108">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="502a7-109">本節內容</span><span class="sxs-lookup"><span data-stu-id="502a7-109">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="502a7-110">更新 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="502a7-110">Update DNS SRV records</span></span>](update-dns-srv-records.md)

  - <span></span>  
    [<span data-ttu-id="502a7-111">將 Lync Server 2010 中央管理伺服器移至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="502a7-111">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>](move-the-lync-server-2010-central-management-server-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="502a7-112">移動會議目錄</span><span class="sxs-lookup"><span data-stu-id="502a7-112">Move Conference Directories</span></span>](move-lync-server-2010-conference-directories-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="502a7-113">移除封存伺服器關聯</span><span class="sxs-lookup"><span data-stu-id="502a7-113">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)

  - <span></span>  
    [<span data-ttu-id="502a7-114">移除監控伺服器關聯</span><span class="sxs-lookup"><span data-stu-id="502a7-114">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)

  - <span></span>  
    [<span data-ttu-id="502a7-115">移除企業版前端伺服器或標準版前端伺服器</span><span class="sxs-lookup"><span data-stu-id="502a7-115">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-enterprise-edition-front-end-server-or-standard-edition-front-end-server.md)

  - <span></span>  
    [<span data-ttu-id="502a7-116">移除後端伺服器上的 SQL Server 執行個體與資料庫</span><span class="sxs-lookup"><span data-stu-id="502a7-116">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

