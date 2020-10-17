---
title: Lync Server 2013：容錯回復集區
description: Lync Server 2013：回切集區失敗。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c1fc0ea4514d2f951dd936521590d47b809db38
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567739"
---
# <a name="failing-back-a-pool-in-lync-server-2013"></a><span data-ttu-id="15609-103">在 Lync Server 2013 中回復集區失敗</span><span class="sxs-lookup"><span data-stu-id="15609-103">Failing back a pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15609-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="15609-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="15609-105">在發生災難的集區重新連線後 (如此範例中的 Pool1)，請採取下列步驟將部署還原至正常運作狀態。</span><span class="sxs-lookup"><span data-stu-id="15609-105">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="15609-p101">請注意，容錯回復程序需要數分鐘才能完成。僅供參考：對於有 20,000 個使用者的集區，預計會花上 60 分鐘。</span><span class="sxs-lookup"><span data-stu-id="15609-p101">Note that the failback process takes several minute to complete.  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

1.  <span data-ttu-id="15609-108">若要容錯回復原來位於 Pool1 而容錯移轉至 Pool2 的使用者，請鍵入下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="15609-108">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="15609-109">無需其他步驟。</span><span class="sxs-lookup"><span data-stu-id="15609-109">No other steps are necessary.</span></span> <span data-ttu-id="15609-110">如果您已對中央管理伺服器進行容錯移轉，您可以將它保留在 Pool2 中。</span><span class="sxs-lookup"><span data-stu-id="15609-110">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

