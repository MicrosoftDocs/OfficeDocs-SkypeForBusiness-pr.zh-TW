---
title: Lync Server 2013：檔案共用高可用性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b61a4980c854b6cb79bedbe482bec204a541879f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a><span data-ttu-id="cf4dd-102">Lync Server 2013 中的檔案共用高可用性</span><span class="sxs-lookup"><span data-stu-id="cf4dd-102">File sharing high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf4dd-103">_**主題上次修改日期：** 2012-03-30_</span><span class="sxs-lookup"><span data-stu-id="cf4dd-103">_**Topic Last Modified:** 2012-03-30_</span></span>

<span data-ttu-id="cf4dd-104">若要確保在單一資料中心內進行 Lync Server 檔案共用的高可用性，您可以使用 [分散式檔案系統（DFS）]。</span><span class="sxs-lookup"><span data-stu-id="cf4dd-104">To ensure high availability for Lync Server file sharing within a single data center, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="cf4dd-105">DFS 支援從一個檔案伺服器到同一資料中心內的另一個檔案伺服器進行容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="cf4dd-105">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="cf4dd-106">針對大型部署，我們建議您使用使用 DFS 配對的專用檔案伺服器。</span><span class="sxs-lookup"><span data-stu-id="cf4dd-106">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span>

<span data-ttu-id="cf4dd-107">視您的網路大小及您想要的復原數量而定，您可以使用一組伺服器來裝載網站中的所有檔案共用，或在每個前端池中使用一對。</span><span class="sxs-lookup"><span data-stu-id="cf4dd-107">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>

<span data-ttu-id="cf4dd-108">DFS 是一種最佳的檔案複製機制，不含發佈的恢復時間目標（RTO）或復原點目標（RPO）承諾。</span><span class="sxs-lookup"><span data-stu-id="cf4dd-108">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="cf4dd-109">DFS 伺服器之間的容錯移轉應該會快速完成，但資料複寫延遲可能會讓使用者無法在進行容錯移轉時繼續進行工作。</span><span class="sxs-lookup"><span data-stu-id="cf4dd-109">The failover between the DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>

<span data-ttu-id="cf4dd-110">如果您在檔共用中使用 DFS 和資料存放區，您應該經常備份檔案共用，例如每4到8個小時。</span><span class="sxs-lookup"><span data-stu-id="cf4dd-110">If you use DFS and data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="cf4dd-111">當某個檔案共用停機且複製不是最新時，您可以使用備份將失敗伺服器上的內容還原到與目前無法使用的伺服器配對的其他伺服器上。</span><span class="sxs-lookup"><span data-stu-id="cf4dd-111">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

