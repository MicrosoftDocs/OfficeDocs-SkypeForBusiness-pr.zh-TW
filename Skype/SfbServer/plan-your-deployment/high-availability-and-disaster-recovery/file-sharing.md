---
title: 商務用 Skype Server 的檔案共用高可用性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: 瞭解如何在商務用 Skype Server (使用 DFS) 中, 確保檔案共用的可用性高。
ms.openlocfilehash: 56a6e1008935bc0d38d65e2355826634709aed27
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192996"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a><span data-ttu-id="0b648-103">商務用 Skype Server 的檔案共用高可用性</span><span class="sxs-lookup"><span data-stu-id="0b648-103">File sharing high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="0b648-104">瞭解如何在商務用 Skype Server (使用 DFS) 中, 確保檔案共用的可用性高。</span><span class="sxs-lookup"><span data-stu-id="0b648-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="0b648-105">為了確保您在商務用 Skype Server 部署中的檔案共用具有高可用性, 您可以使用分散式檔案系統 (DFS)。</span><span class="sxs-lookup"><span data-stu-id="0b648-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="0b648-106">DFS 支援從一個檔案伺服器到同一資料中心內的另一個檔案伺服器進行容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="0b648-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="0b648-107">針對大型部署, 我們建議您使用使用 DFS 配對的專用檔案伺服器。</span><span class="sxs-lookup"><span data-stu-id="0b648-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="0b648-108">如需有關 Windows Server 2012 中 DFS 的詳細資訊[https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384), 請參閱。</span><span class="sxs-lookup"><span data-stu-id="0b648-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span></span> <span data-ttu-id="0b648-109">如需有關 Windows Server 2008 上 DFS 的詳細[https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385)資訊, 請參閱。</span><span class="sxs-lookup"><span data-stu-id="0b648-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span></span>
  
<span data-ttu-id="0b648-110">視您的網路大小及您想要的復原數量而定, 您可以使用一組伺服器來裝載網站中的所有檔案共用, 或在每個前端池中使用一對。</span><span class="sxs-lookup"><span data-stu-id="0b648-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="0b648-111">DFS 是一種最佳的檔案複製機制, 不含發佈的恢復時間目標 (RTO) 或復原點目標 (RPO) 承諾。</span><span class="sxs-lookup"><span data-stu-id="0b648-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="0b648-112">DFS 伺服器之間的容錯移轉應該會很快完成, 但資料複寫延遲可能會讓使用者無法在進行容錯移轉時繼續進行工作。</span><span class="sxs-lookup"><span data-stu-id="0b648-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="0b648-113">如果您使用的是 DFS, 且檔案儲存在檔中的資料存放區是重要的, 您應該經常備份檔案共用, 例如每4到8小時。</span><span class="sxs-lookup"><span data-stu-id="0b648-113">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="0b648-114">當某個檔案共用停機且複製不是最新時, 您可以使用備份將失敗伺服器上的內容還原到與目前無法使用的伺服器配對的其他伺服器上。</span><span class="sxs-lookup"><span data-stu-id="0b648-114">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
  

