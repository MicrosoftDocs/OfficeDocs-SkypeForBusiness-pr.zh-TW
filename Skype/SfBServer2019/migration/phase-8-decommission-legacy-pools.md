---
title: 階段8解除舊版池的授權
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: httpsfix
description: 下列主題提供更新 DNS 專案、移動內容管理伺服器、解除授權池以及停用與從舊版部署移除伺服器和池的指導方針。 並非本節所列的所有程式都是必要的。 閱讀檔，並判斷要使用的解除授權程式。
ms.openlocfilehash: 2398e9ce681edc2bba9f4f93d54f39d727bdb75e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813101"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="340e9-105">階段 8：解除委任舊版集區</span><span class="sxs-lookup"><span data-stu-id="340e9-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="340e9-106">下列主題提供更新 DNS 專案、移動內容管理伺服器、解除授權池以及停用與從舊版部署移除伺服器和池的指導方針。</span><span class="sxs-lookup"><span data-stu-id="340e9-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="340e9-107">並非本節所列的所有程式都是必要的。</span><span class="sxs-lookup"><span data-stu-id="340e9-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="340e9-108">閱讀檔，並判斷要使用的解除授權程式。</span><span class="sxs-lookup"><span data-stu-id="340e9-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="340e9-109">有關移除伺服器和伺服器角色的已過期但已詳盡的文章，以及如何解除部署的相關逐步指南，請下載[卸載 Microsoft Lync server 並移除伺服器角色](https://go.microsoft.com/fwlink/p/?linkId=246227)。</span><span class="sxs-lookup"><span data-stu-id="340e9-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="340e9-110">如需遷移和升級 Microsoft 整合通訊管理 API （UCMA）應用程式的相關資訊，請參閱解除舊版環境的相關資訊[：共存、遷移和升級案例](https://go.microsoft.com/fwlink/p/?LinkId=269555)。</span><span class="sxs-lookup"><span data-stu-id="340e9-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="340e9-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="340e9-111">In this section</span></span>

> [<span data-ttu-id="340e9-112">更新 DNS SRV 記錄</span><span class="sxs-lookup"><span data-stu-id="340e9-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="340e9-113">將舊版安裝中央管理伺服器移至商務用 Skype Server 2019</span><span class="sxs-lookup"><span data-stu-id="340e9-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="340e9-114">移動會議目錄</span><span class="sxs-lookup"><span data-stu-id="340e9-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="340e9-115">移除封存伺服器關聯</span><span class="sxs-lookup"><span data-stu-id="340e9-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="340e9-116">移除監控伺服器關聯</span><span class="sxs-lookup"><span data-stu-id="340e9-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="340e9-117">移除企業版前端伺服器或標準版前端伺服器</span><span class="sxs-lookup"><span data-stu-id="340e9-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="340e9-118">移除後端伺服器上的 SQL Server 執行個體與資料庫</span><span class="sxs-lookup"><span data-stu-id="340e9-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    

