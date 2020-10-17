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
ms.openlocfilehash: 853dfdd6786b4e30513cb57be219edff8d8c1b9b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530970"
---
# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a>在 Lync Server 2013 中容錯移轉鏡像資料庫

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-03-14_

若您已設定後端資料庫以使用具有見證的同步鏡像，將自動進行容錯移轉。若您已經設定不具見證的同步鏡像，則可以使用以下程序，針對資料庫進行容錯移轉與容錯回復。即使您已經設定見證，也可以使用這些程序對資料庫進行手動容錯移轉與容錯回復。

<div>

## <a name="to-fail-over-your-back-end-database"></a>針對您的後端資料庫進行容錯移轉

1.  進行容錯移轉前，請鍵入下列 Cmdlet，以決定後端資料庫何者為主體以及何者為鏡像：
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  若中央管理存放區裝載于此集區中，請輸入下列 Cmdlet，以判斷哪個是主體，也就是中央管理存放區的鏡像：
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  執行使用者資料庫容錯移轉：
    
      - 如果主要作業失敗，而您正在進行鏡像容錯移轉，請鍵入：
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - 如果鏡像失敗而您正在進行主要作業的容錯移轉，請鍵入：
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  如果集區主控中央管理伺服器，請執行中央管理存放區的容錯移轉。
    
      - 如果主要作業失敗，而您正在進行鏡像容錯移轉，請鍵入：
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - 如果鏡像失敗而您正在進行主要作業的容錯移轉，請鍵入：
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

