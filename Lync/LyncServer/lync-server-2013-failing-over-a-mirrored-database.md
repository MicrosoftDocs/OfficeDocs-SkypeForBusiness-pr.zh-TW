---
title: Lync Server 2013：容錯移轉鏡像資料庫
description: Lync Server 2013：容錯移轉鏡像資料庫。
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
ms.openlocfilehash: fc7c401157c79762f674721ca717296c0fe502db
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567689"
---
# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a><span data-ttu-id="4456b-103">在 Lync Server 2013 中容錯移轉鏡像資料庫</span><span class="sxs-lookup"><span data-stu-id="4456b-103">Failing over a mirrored database in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4456b-104">_**主題上次修改日期：** 2014-03-14_</span><span class="sxs-lookup"><span data-stu-id="4456b-104">_**Topic Last Modified:** 2014-03-14_</span></span>

<span data-ttu-id="4456b-p101">若您已設定後端資料庫以使用具有見證的同步鏡像，將自動進行容錯移轉。若您已經設定不具見證的同步鏡像，則可以使用以下程序，針對資料庫進行容錯移轉與容錯回復。即使您已經設定見證，也可以使用這些程序對資料庫進行手動容錯移轉與容錯回復。</span><span class="sxs-lookup"><span data-stu-id="4456b-p101">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic. If you have configured synchronized mirroring without a witness, you can use the following procedures to failover and failback your database. You can also use these procedures to manually failover and failback your databases even if you have configured a witness.</span></span>

<div>

## <a name="to-fail-over-your-back-end-database"></a><span data-ttu-id="4456b-108">針對您的後端資料庫進行容錯移轉</span><span class="sxs-lookup"><span data-stu-id="4456b-108">To fail over your back-end database</span></span>

1.  <span data-ttu-id="4456b-109">進行容錯移轉前，請鍵入下列 Cmdlet，以決定後端資料庫何者為主體以及何者為鏡像：</span><span class="sxs-lookup"><span data-stu-id="4456b-109">Before failing over, determine which back-end database is the principal and which is the mirror by typing the following cmdlet:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  <span data-ttu-id="4456b-110">若中央管理存放區裝載于此集區中，請輸入下列 Cmdlet，以判斷哪個是主體，也就是中央管理存放區的鏡像：</span><span class="sxs-lookup"><span data-stu-id="4456b-110">If the Central Management store is hosted in this pool, type the following cmdlet to determine which is the principal and which is the mirror for the Central Management store:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  <span data-ttu-id="4456b-111">執行使用者資料庫容錯移轉：</span><span class="sxs-lookup"><span data-stu-id="4456b-111">Perform the failover of the user database:</span></span>
    
      - <span data-ttu-id="4456b-112">如果主要作業失敗，而您正在進行鏡像容錯移轉，請鍵入：</span><span class="sxs-lookup"><span data-stu-id="4456b-112">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="4456b-113">如果鏡像失敗而您正在進行主要作業的容錯移轉，請鍵入：</span><span class="sxs-lookup"><span data-stu-id="4456b-113">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  <span data-ttu-id="4456b-114">如果集區主控中央管理伺服器，請執行中央管理存放區的容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="4456b-114">If the pool hosts the Central Management Server, perform the failover of the Central Management store.</span></span>
    
      - <span data-ttu-id="4456b-115">如果主要作業失敗，而您正在進行鏡像容錯移轉，請鍵入：</span><span class="sxs-lookup"><span data-stu-id="4456b-115">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="4456b-116">如果鏡像失敗而您正在進行主要作業的容錯移轉，請鍵入：</span><span class="sxs-lookup"><span data-stu-id="4456b-116">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

