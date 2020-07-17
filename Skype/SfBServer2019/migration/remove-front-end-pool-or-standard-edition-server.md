---
title: 移除前端集區或 Standard Edition Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本主題將引導您完成移除前端集區或 Standard Edition 前端伺服器的程式。 當您移除前端集區時，會移除屬於集區的所有前端伺服器，作為集區移除程式的一部分。 當您移除 Standard Edition 前端伺服器時，必須從拓撲產生器移除 SQL 存放區定義。
ms.openlocfilehash: 305a353ced45fe7e21ba479c0c3571df236aa09b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752275"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="47f65-105">移除前端集區或 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="47f65-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="47f65-106">本文將引導您完成移除前端集區或 Standard Edition 前端伺服器的程式。</span><span class="sxs-lookup"><span data-stu-id="47f65-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="47f65-107">當您移除前端集區時，會移除屬於集區的所有前端伺服器，作為集區移除程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="47f65-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="47f65-108">當您移除 Standard Edition 前端伺服器時，必須從拓撲產生器移除 SQL 存放區定義。</span><span class="sxs-lookup"><span data-stu-id="47f65-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="47f65-109">移除前端伺服器集區</span><span class="sxs-lookup"><span data-stu-id="47f65-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="47f65-110">開啟拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="47f65-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="47f65-111">流覽至 [舊版] 節點。</span><span class="sxs-lookup"><span data-stu-id="47f65-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="47f65-112">展開 [ **Enterprise Edition 前端**集區]，展開前端集區，以滑鼠右鍵按一下您要移除的前端集區，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="47f65-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="47f65-113">發佈拓撲，檢查複寫狀態，然後視需要執行舊版部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="47f65-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="47f65-114">移除 Standard Edition 前端伺服器</span><span class="sxs-lookup"><span data-stu-id="47f65-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="47f65-115">開啟拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="47f65-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="47f65-116">流覽至 [舊版安裝] 節點。</span><span class="sxs-lookup"><span data-stu-id="47f65-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="47f65-117">展開 [ **Standard Edition 前端伺服器**]，以滑鼠右鍵按一下您要移除的前端伺服器，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="47f65-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="47f65-118">展開 **[SQL 存放區**]，以滑鼠右鍵按一下與 Standard Edition 前端伺服器相關聯的 SQL Server 資料庫，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="47f65-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="47f65-119">您必須從 Standard Edition 前端伺服器移除組合 SQL Server 資料庫的定義。</span><span class="sxs-lookup"><span data-stu-id="47f65-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="47f65-120">發佈拓撲，檢查複寫狀態，然後視需要執行部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="47f65-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

