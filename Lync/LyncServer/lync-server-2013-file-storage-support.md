---
title: Lync Server 2013 檔案儲存支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 000f3357c8b30b83a2d2cecf74bdbec44d867d96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a><span data-ttu-id="c2d30-102">Lync Server 2013 中的檔案儲存支援</span><span class="sxs-lookup"><span data-stu-id="c2d30-102">File storage support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2d30-103">_**主題上次修改日期：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="c2d30-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="c2d30-104">Lync Server 2013 在所有檔案儲存空間中使用相同的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="c2d30-104">Lync Server 2013 uses the same file store for all file storage.</span></span> <span data-ttu-id="c2d30-105">檔案儲存支援包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="c2d30-105">File storage support includes the following:</span></span>

  - <span data-ttu-id="c2d30-106">直連儲存空間（DAS）或儲存區域網路（SAN）上的檔案共用，包括分散式檔案系統（DFS），以及檔案存放區的獨立磁碟容錯陣列（RAID）。</span><span class="sxs-lookup"><span data-stu-id="c2d30-106">A file share on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS), and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="c2d30-107">如需有關儲存需求的詳細資訊，請參閱規劃檔中的 lync server [2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md)中[前端伺服器、立即訊息和目前2013狀態的技術需求](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="c2d30-107">For details about storage requirements, see [Technical requirements for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) and [Hardware and software requirements for the Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) in the Planning documentation.</span></span> <span data-ttu-id="c2d30-108">如需有關 Windows server 2008 作業系統的 DFS 的詳細資訊，請參閱 Windows Server 2008 的 DFS 逐步指南[http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)。</span><span class="sxs-lookup"><span data-stu-id="c2d30-108">For details about DFS for Windows Server 2008 operating system, see the DFS Step-by-Step Guide for Windows Server 2008 at [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).</span></span>

  - <span data-ttu-id="c2d30-109">檔案共用的共用群集。</span><span class="sxs-lookup"><span data-stu-id="c2d30-109">A shared cluster for the file share.</span></span> <span data-ttu-id="c2d30-110">如果您使用的是共用群集，您應該使用執行 Windows Server 2008 或 Windows Server 2008 R2 的叢集服務器。</span><span class="sxs-lookup"><span data-stu-id="c2d30-110">If you use a shared cluster, you should use cluster servers running Windows Server 2008 or Windows Server 2008 R2.</span></span> <span data-ttu-id="c2d30-111">如果使用叢集服務器執行舊版的 Windows，可能會導致許可權問題，避免某些功能可供使用。</span><span class="sxs-lookup"><span data-stu-id="c2d30-111">Using cluster servers running an older version of Windows may result in permission issues that prevent some features from being available.</span></span> <span data-ttu-id="c2d30-112">使用 [群集管理員] 來建立檔案共用。</span><span class="sxs-lookup"><span data-stu-id="c2d30-112">Use the Cluster Administrator to create the file shares.</span></span> <span data-ttu-id="c2d30-113">如需使用 [群集管理員] 的詳細資料，請參閱 Microsoft 知識庫文章284838：「如何在[http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899)群集中建立伺服器叢集檔案共用」。</span><span class="sxs-lookup"><span data-stu-id="c2d30-113">For details about using the Cluster Administrator, see Microsoft Knowledge Base article 284838, "How to Create a Server Cluster File Share with Cluster.exe" at [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

