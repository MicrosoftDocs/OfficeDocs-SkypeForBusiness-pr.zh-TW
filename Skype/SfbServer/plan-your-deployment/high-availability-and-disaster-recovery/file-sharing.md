---
title: 商務用 Skype Server 中的檔共用高可用性
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: 瞭解如何在商務用 Skype Server 中使用 DFS，以確保檔案共用的高可用性。
ms.openlocfilehash: 4d443425f453d63694511d13c6d3a84893058daa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802893"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a><span data-ttu-id="625f1-103">商務用 Skype Server 中的檔共用高可用性</span><span class="sxs-lookup"><span data-stu-id="625f1-103">File sharing high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="625f1-104">瞭解如何在商務用 Skype Server 中使用 DFS，以確保檔案共用的高可用性。</span><span class="sxs-lookup"><span data-stu-id="625f1-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="625f1-105">為了確保商務用 Skype Server 部署中的檔案共用具有高可用性，您可以使用分散式檔案系統 (DFS) 。</span><span class="sxs-lookup"><span data-stu-id="625f1-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="625f1-106">DFS 支援在相同的資料中心內，從一個檔案伺服器到另一個檔案伺服器的容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="625f1-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="625f1-107">在大規模部署中，建議您使用使用 DFS 成對的專用檔案伺服器。</span><span class="sxs-lookup"><span data-stu-id="625f1-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="625f1-108">如需有關 Windows Server 2012 中 DFS 的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384) 。</span><span class="sxs-lookup"><span data-stu-id="625f1-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span></span> <span data-ttu-id="625f1-109">如需有關 Windows Server 2008 上之 DFS 的資訊，請參閱 [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385) 。</span><span class="sxs-lookup"><span data-stu-id="625f1-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span></span>
  
<span data-ttu-id="625f1-110">根據您的網路規模和您想要的復原數量，您可以使用一組伺服器來裝載網站中的所有檔案共用，或在前端集區中使用一對。</span><span class="sxs-lookup"><span data-stu-id="625f1-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="625f1-111">DFS 是一種最佳的檔複寫方式，沒有發佈的復原時間目標 (RTO) 或復原點目標 (RPO) 承諾。</span><span class="sxs-lookup"><span data-stu-id="625f1-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="625f1-112">DFS 伺服器之間的容錯移轉應該會很快完成，但是資料複寫延遲可能會讓使用者無法繼續進行容錯移轉時進行中的工作。</span><span class="sxs-lookup"><span data-stu-id="625f1-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="625f1-113">如果您使用 DFS 和檔共用上的資料存放區很重要，您應該經常備份檔案共用，例如每4到8個小時。</span><span class="sxs-lookup"><span data-stu-id="625f1-113">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="625f1-114">當一個檔案共用停機且複寫不是最新時，您可以使用備份將失敗伺服器上的內容還原至與目前無法使用之伺服器配對的另一部伺服器。</span><span class="sxs-lookup"><span data-stu-id="625f1-114">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
  

