---
title: 移除前端池或標準版伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本主題將引導您完成移除前端池或標準版前端伺服器的程式。 當您移除 [前端] 池時, 您會將屬於該池的每個前端伺服器移除為 [池移除] 程式的一部分。 當您移除標準版前端伺服器時, 必須從拓撲建立器移除 SQL Store 定義。
ms.openlocfilehash: fd43682fca67b961ac93c01813ca6ea9e702b644
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193282"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="6d670-105">移除前端池或標準版伺服器</span><span class="sxs-lookup"><span data-stu-id="6d670-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="6d670-106">本文將引導您完成移除前端池或標準版前端伺服器的程式。</span><span class="sxs-lookup"><span data-stu-id="6d670-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="6d670-107">當您移除 [前端] 池時, 您會將屬於該池的每個前端伺服器移除為 [池移除] 程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="6d670-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="6d670-108">當您移除標準版前端伺服器時, 必須從拓撲建立器移除 SQL Store 定義。</span><span class="sxs-lookup"><span data-stu-id="6d670-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="6d670-109">移除前端伺服器池</span><span class="sxs-lookup"><span data-stu-id="6d670-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="6d670-110">開啟拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="6d670-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="6d670-111">流覽至 [舊版] 節點。</span><span class="sxs-lookup"><span data-stu-id="6d670-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="6d670-112">展開 [**企業版前端] 池**、展開 [前端] 池、以滑鼠右鍵按一下您要移除的 [前端] 池, 然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="6d670-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="6d670-113">發佈拓撲、檢查複製狀態, 然後視需要執行舊版部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="6d670-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="6d670-114">移除標準版前端伺服器</span><span class="sxs-lookup"><span data-stu-id="6d670-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="6d670-115">開啟拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="6d670-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="6d670-116">流覽至 [舊版安裝] 節點。</span><span class="sxs-lookup"><span data-stu-id="6d670-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="6d670-117">展開 [**標準版前端伺服器**], 以滑鼠右鍵按一下您要移除的前端伺服器, 然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="6d670-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="6d670-118">展開 **[SQL] 商店**, 以滑鼠右鍵按一下與標準版前端伺服器相關聯的 SQL Server 資料庫, 然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="6d670-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6d670-119">您必須從標準版前端伺服器移除 collocated SQL Server 資料庫的定義。</span><span class="sxs-lookup"><span data-stu-id="6d670-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="6d670-120">發佈拓撲, 檢查複製狀態, 然後視需要執行部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="6d670-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

