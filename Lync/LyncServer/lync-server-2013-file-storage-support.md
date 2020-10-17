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
ms.openlocfilehash: 1c424693b71f516b1fcb27523fbcb27b3a514176
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507276"
---
# <a name="file-storage-support-in-lync-server-2013"></a><span data-ttu-id="8daac-102">Lync Server 2013 中的檔案儲存支援</span><span class="sxs-lookup"><span data-stu-id="8daac-102">File storage support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8daac-103">_**主題上次修改日期：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="8daac-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="8daac-104">Lync Server 2013 使用相同的檔案存放區存放所有的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="8daac-104">Lync Server 2013 uses the same file store for all file storage.</span></span> <span data-ttu-id="8daac-105">檔案儲存支援包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="8daac-105">File storage support includes the following:</span></span>

  - <span data-ttu-id="8daac-106">直接連接儲存區上的檔案共用 (DAS) 或存放區域網路 (SAN) （包括分散式檔案系統 (DFS) ，以及獨立磁碟容錯陣列 (RAID) 為檔案存放區）。</span><span class="sxs-lookup"><span data-stu-id="8daac-106">A file share on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS), and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="8daac-107">如需儲存需求的詳細資訊，請參閱規劃檔中的 [前端伺服器、立即訊息及顯示狀態的 lync server 2013 中的技術需求](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) ，以及 [lync Server 2013 中 Director 的硬體和軟體需求](lync-server-2013-hardware-and-software-requirements-for-the-director.md) 。</span><span class="sxs-lookup"><span data-stu-id="8daac-107">For details about storage requirements, see [Technical requirements for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) and [Hardware and software requirements for the Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) in the Planning documentation.</span></span> <span data-ttu-id="8daac-108">如需有關 Windows Server 2008 作業系統之 DFS 的詳細資訊，請參閱 Windows Server 2008 的 DFS 逐步指南 [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835) 。</span><span class="sxs-lookup"><span data-stu-id="8daac-108">For details about DFS for Windows Server 2008 operating system, see the DFS Step-by-Step Guide for Windows Server 2008 at [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835).</span></span>

  - <span data-ttu-id="8daac-109">檔案共用的共用叢集。</span><span class="sxs-lookup"><span data-stu-id="8daac-109">A shared cluster for the file share.</span></span> <span data-ttu-id="8daac-110">如果您使用共用叢集，您應該使用執行 Windows Server 2008 或 Windows Server 2008 R2 的叢集服務器。</span><span class="sxs-lookup"><span data-stu-id="8daac-110">If you use a shared cluster, you should use cluster servers running Windows Server 2008 or Windows Server 2008 R2.</span></span> <span data-ttu-id="8daac-111">使用執行舊版本 Windows 的叢集服務器可能會導致許可權問題，使某些功能無法使用。</span><span class="sxs-lookup"><span data-stu-id="8daac-111">Using cluster servers running an older version of Windows may result in permission issues that prevent some features from being available.</span></span> <span data-ttu-id="8daac-112">使用聚簇管理員來建立檔案共用。</span><span class="sxs-lookup"><span data-stu-id="8daac-112">Use the Cluster Administrator to create the file shares.</span></span> <span data-ttu-id="8daac-113">如需使用 [叢集管理員] 的詳細資訊，請參閱 Microsoft 知識庫文章284838：如何使用 Cluster.exe 建立伺服器叢集檔案共用」 [https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899) 。</span><span class="sxs-lookup"><span data-stu-id="8daac-113">For details about using the Cluster Administrator, see Microsoft Knowledge Base article 284838, "How to Create a Server Cluster File Share with Cluster.exe" at [https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

