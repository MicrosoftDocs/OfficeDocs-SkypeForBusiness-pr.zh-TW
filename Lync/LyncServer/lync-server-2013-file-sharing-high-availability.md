---
title: Lync Server 2013： 檔案共用高可用性
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
ms.openlocfilehash: 453b4c63f58f6153092dae0259155dbfa72b5eca
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a><span data-ttu-id="6502d-102">檔案共用 Lync Server 2013 中的高可用性</span><span class="sxs-lookup"><span data-stu-id="6502d-102">File sharing high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6502d-103">_**主題上次修改日期：** 2012年-03-30_</span><span class="sxs-lookup"><span data-stu-id="6502d-103">_**Topic Last Modified:** 2012-03-30_</span></span>

<span data-ttu-id="6502d-104">若要確保高可用性的 Lync Server 檔案共用單一資料中心內，您可以使用分散式檔案系統 (DFS)。</span><span class="sxs-lookup"><span data-stu-id="6502d-104">To ensure high availability for Lync Server file sharing within a single data center, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="6502d-105">DFS 支援從一個檔案伺服器容錯移轉至另一個相同的資料中心內。</span><span class="sxs-lookup"><span data-stu-id="6502d-105">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="6502d-106">針對大型部署，建議您使用的成對使用 DFS 專用的檔案伺服器。</span><span class="sxs-lookup"><span data-stu-id="6502d-106">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span>

<span data-ttu-id="6502d-107">根據您的網路大小與想要的恢復量，您可以使用一對伺服器來裝載站台中的所有檔案共用，或使用一對每個前端集區。</span><span class="sxs-lookup"><span data-stu-id="6502d-107">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>

<span data-ttu-id="6502d-108">DFS 是最佳投入比檔案複寫機制，任何已發佈的復原時間目標 (RTO) 或復原點目標 (RPO) 承諾。</span><span class="sxs-lookup"><span data-stu-id="6502d-108">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="6502d-109">快速，應該完成 DFS 伺服器之間容錯移轉，但資料複寫延遲可能阻止使用者能夠繼續進行中的工作時，若發生容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="6502d-109">The failover between the DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>

<span data-ttu-id="6502d-110">如果您使用 DFS 和檔案共用上的資料存放區非常重要，您應該先備份的檔案共用常見問題，例如，為每隔 4 到 8 小時。</span><span class="sxs-lookup"><span data-stu-id="6502d-110">If you use DFS and data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="6502d-111">當一個檔案共用下降並複寫不是最新狀態時，您可以使用備份來還原與伺服器現在無法使用的成對的另一部伺服器失敗的伺服器上的內容。</span><span class="sxs-lookup"><span data-stu-id="6502d-111">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

