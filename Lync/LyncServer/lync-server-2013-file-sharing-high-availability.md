---
title: Lync Server 2013：檔案共用高可用性
description: Lync Server 2013：檔案共用高可用性。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29b0a77d2d03460c640c66b8e8ce2a551edf2d73
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543359"
---
# <a name="file-sharing-high-availability-in-lync-server-2013"></a><span data-ttu-id="d51aa-103">Lync Server 2013 中的檔共用高可用性</span><span class="sxs-lookup"><span data-stu-id="d51aa-103">File sharing high availability in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d51aa-104">_**主題上次修改日期：** 2012-03-30_</span><span class="sxs-lookup"><span data-stu-id="d51aa-104">_**Topic Last Modified:** 2012-03-30_</span></span>

<span data-ttu-id="d51aa-105">為了確保單一資料中心內的 Lync Server 檔案共用的高可用性，您可以使用分散式檔案系統 (DFS) 。</span><span class="sxs-lookup"><span data-stu-id="d51aa-105">To ensure high availability for Lync Server file sharing within a single data center, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="d51aa-106">DFS 支援在相同的資料中心內，從一個檔案伺服器到另一個檔案伺服器的容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="d51aa-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="d51aa-107">在大規模部署中，建議您使用使用 DFS 成對的專用檔案伺服器。</span><span class="sxs-lookup"><span data-stu-id="d51aa-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span>

<span data-ttu-id="d51aa-108">根據您的網路規模和您想要的復原數量，您可以使用一組伺服器來裝載網站中的所有檔案共用，或在前端集區中使用一對。</span><span class="sxs-lookup"><span data-stu-id="d51aa-108">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>

<span data-ttu-id="d51aa-109">DFS 是一種最佳的檔複寫方式，沒有發佈的復原時間目標 (RTO) 或復原點目標 (RPO) 承諾。</span><span class="sxs-lookup"><span data-stu-id="d51aa-109">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="d51aa-110">DFS 伺服器之間的容錯移轉應該會很快完成，但是資料複寫延遲可能會讓使用者無法繼續進行容錯移轉時進行中的工作。</span><span class="sxs-lookup"><span data-stu-id="d51aa-110">The failover between the DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>

<span data-ttu-id="d51aa-111">如果您在檔共用上使用 DFS 和資料儲存區是很重要的，您應該經常備份檔案共用，例如每4到8個小時。</span><span class="sxs-lookup"><span data-stu-id="d51aa-111">If you use DFS and data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="d51aa-112">當一個檔案共用停機且複寫不是最新時，您可以使用備份將失敗伺服器上的內容還原至與目前無法使用之伺服器配對的另一部伺服器。</span><span class="sxs-lookup"><span data-stu-id="d51aa-112">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

