---
title: Lync Server 2013：容錯移轉鏡像資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a mirrored database
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204991(v=OCS.15)
ms:contentKeyID: 48184450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 822a7a2fa13ce444bbaf590ee0d8ba2144debcc7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a><span data-ttu-id="edbc9-102">在 Lync Server 2013 中容錯移轉鏡像資料庫</span><span class="sxs-lookup"><span data-stu-id="edbc9-102">Failing over a mirrored database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edbc9-103">_**主題上次修改日期：** 2014-03-14_</span><span class="sxs-lookup"><span data-stu-id="edbc9-103">_**Topic Last Modified:** 2014-03-14_</span></span>

<span data-ttu-id="edbc9-104">如果您已將後端資料庫設定為使用與見證的同步處理鏡像，則會自動進行容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="edbc9-104">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span> <span data-ttu-id="edbc9-105">如果您已設定不含見證的同步處理鏡像，您可以使用下列程式來容錯移轉及回切您的資料庫。</span><span class="sxs-lookup"><span data-stu-id="edbc9-105">If you have configured synchronized mirroring without a witness, you can use the following procedures to failover and failback your database.</span></span> <span data-ttu-id="edbc9-106">您也可以使用這些程式，即使您已設定見證，也能手動容錯移轉及回切至您的資料庫。</span><span class="sxs-lookup"><span data-stu-id="edbc9-106">You can also use these procedures to manually failover and failback your databases even if you have configured a witness.</span></span>

<div>

## <a name="to-fail-over-your-back-end-database"></a><span data-ttu-id="edbc9-107">容錯移轉後端資料庫</span><span class="sxs-lookup"><span data-stu-id="edbc9-107">To fail over your back-end database</span></span>

1.  <span data-ttu-id="edbc9-108">在進行容錯移轉之前，請輸入以下 Cmdlet 來判斷哪個後端資料庫是主體，哪個是鏡像：</span><span class="sxs-lookup"><span data-stu-id="edbc9-108">Before failing over, determine which back-end database is the principal and which is the mirror by typing the following cmdlet:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  <span data-ttu-id="edbc9-109">如果中央管理儲存區託管于此池中，請輸入下列 Cmdlet 來判斷哪個是 principal，哪個是中央管理存儲的鏡像：</span><span class="sxs-lookup"><span data-stu-id="edbc9-109">If the Central Management store is hosted in this pool, type the following cmdlet to determine which is the principal and which is the mirror for the Central Management store:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  <span data-ttu-id="edbc9-110">執行使用者資料庫的容錯移轉：</span><span class="sxs-lookup"><span data-stu-id="edbc9-110">Perform the failover of the user database:</span></span>
    
      - <span data-ttu-id="edbc9-111">如果主要使用者失敗且您已容錯移轉到鏡像，請輸入：</span><span class="sxs-lookup"><span data-stu-id="edbc9-111">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="edbc9-112">如果鏡像失敗且您要容錯移轉到主要使用者，請輸入：</span><span class="sxs-lookup"><span data-stu-id="edbc9-112">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  <span data-ttu-id="edbc9-113">如果該池託管中央管理伺服器，請執行中央管理存儲的容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="edbc9-113">If the pool hosts the Central Management Server, perform the failover of the Central Management store.</span></span>
    
      - <span data-ttu-id="edbc9-114">如果主要使用者失敗且您已容錯移轉到鏡像，請輸入：</span><span class="sxs-lookup"><span data-stu-id="edbc9-114">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="edbc9-115">如果鏡像失敗且您要容錯移轉到主要使用者，請輸入：</span><span class="sxs-lookup"><span data-stu-id="edbc9-115">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

