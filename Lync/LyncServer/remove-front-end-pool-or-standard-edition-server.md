---
title: 移除前端集區或 Standard Edition Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b004426c65157ef7ad1120728c9daeea1b68f161
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="95cbb-102">移除前端集區或 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="95cbb-102">Remove Front End pool or Standard Edition server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95cbb-103">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="95cbb-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="95cbb-104">本主題將引導您完成移除前端集區或 Standard Edition 前端伺服器的程式。</span><span class="sxs-lookup"><span data-stu-id="95cbb-104">This topic guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="95cbb-105">當您移除前端集區時，會移除屬於集區的所有前端伺服器，作為集區移除程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="95cbb-105">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="95cbb-106">當您移除 Standard Edition 前端伺服器時，必須從拓撲產生器移除 SQL 存放區定義。</span><span class="sxs-lookup"><span data-stu-id="95cbb-106">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>

<div>

## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="95cbb-107">移除前端伺服器集區</span><span class="sxs-lookup"><span data-stu-id="95cbb-107">To remove a Front End Server pool</span></span>

1.  <span data-ttu-id="95cbb-108">開啟拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="95cbb-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="95cbb-109">流覽至 [Lync Server 2010] 節點。</span><span class="sxs-lookup"><span data-stu-id="95cbb-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="95cbb-110">展開 [ **Enterprise Edition 前端**集區]，展開前端集區，以滑鼠右鍵按一下您要移除的前端集區，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="95cbb-110">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="95cbb-111">發佈拓撲，檢查複寫狀態，然後視需要執行 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="95cbb-111">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="95cbb-112">移除 Standard Edition 前端伺服器</span><span class="sxs-lookup"><span data-stu-id="95cbb-112">To remove a Standard Edition Front End server</span></span>

1.  <span data-ttu-id="95cbb-113">開啟拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="95cbb-113">Open Topology Builder.</span></span>

2.  <span data-ttu-id="95cbb-114">流覽至 [Lync Server 2010] 節點。</span><span class="sxs-lookup"><span data-stu-id="95cbb-114">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="95cbb-115">展開 [ **Standard Edition 前端伺服器**]，以滑鼠右鍵按一下您要移除的前端伺服器，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="95cbb-115">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="95cbb-116">展開 **[SQL 存放區**]，以滑鼠右鍵按一下與 Standard Edition 前端伺服器相關聯的 SQL Server 資料庫，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="95cbb-116">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="95cbb-117">您必須從 Standard Edition 前端伺服器移除組合 SQL Server 資料庫的定義。</span><span class="sxs-lookup"><span data-stu-id="95cbb-117">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="95cbb-118">發佈拓撲，檢查複寫狀態，然後視需要執行 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="95cbb-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

