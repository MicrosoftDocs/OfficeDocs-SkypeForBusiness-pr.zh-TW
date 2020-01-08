---
title: Lync Server 2013：還原資料和設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring data and settings
ms:assetid: b07f5dd7-7bed-4819-8cb5-617f5acd478e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202185(v=OCS.15)
ms:contentKeyID: 51541503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7562e0899a5129832ef4651c041b8c7daf545e7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="4c0b6-102">在 Lync Server 2013 中還原資料和設定</span><span class="sxs-lookup"><span data-stu-id="4c0b6-102">Restoring data and settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c0b6-103">_**主題上次修改日期：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="4c0b6-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="4c0b6-104">如果您已使用配對的池子來實施災害復原拓朴，且其中一個前端池已關閉，而您需要將服務快速還原給您的使用者，請參閱[在 Lync Server 2013 中轉移池失敗](lync-server-2013-failing-over-a-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="4c0b6-104">If you have implemented a disaster recovery topology with paired pools, and one of those Front End pools has gone down and you need to quickly restore service to your users, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="4c0b6-105">否則，請使用下列主題中的資訊，以及[Lync server 2013 備份和還原工作](lync-server-2013-backup-and-restoration-worksheets.md)表中的工作表，在發生故障或停機後還原 lync server。</span><span class="sxs-lookup"><span data-stu-id="4c0b6-105">Otherwise, use the information in the following topics, along with the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md), to restore Lync Server after a failure or outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4c0b6-106">若要減少停機時間和可能的資料遺失，請只有在疑難排解程式無法有效識別及修正問題時，才能執行本檔中所述的還原程式。</span><span class="sxs-lookup"><span data-stu-id="4c0b6-106">To reduce downtime and potential data loss, perform the restoration procedures described in this document only if troubleshooting procedures are not effective in identifying and correcting the problem.</span></span> <span data-ttu-id="4c0b6-107">在疑難排解期間，請嘗試在關閉並重新啟動伺服器時，將對其他伺服器和元件的影響降至最低。</span><span class="sxs-lookup"><span data-stu-id="4c0b6-107">During troubleshooting, try to minimize the impact on other servers and components as you shut down and restart servers.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4c0b6-108">本節內容</span><span class="sxs-lookup"><span data-stu-id="4c0b6-108">In This Section</span></span>

  - [<span data-ttu-id="4c0b6-109">準備還原 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c0b6-109">Preparing to restore Lync Server 2013</span></span>](lync-server-2013-preparing-to-restore-lync-server.md)

  - [<span data-ttu-id="4c0b6-110">在 Lync Server 2013 中還原標準版伺服器</span><span class="sxs-lookup"><span data-stu-id="4c0b6-110">Restoring a Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-restoring-a-standard-edition-server.md)

  - [<span data-ttu-id="4c0b6-111">在 Lync Server 2013 中還原託管中央管理儲存區的伺服器</span><span class="sxs-lookup"><span data-stu-id="4c0b6-111">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)

  - [<span data-ttu-id="4c0b6-112">在 Lync Server 2013 中還原企業版後端伺服器</span><span class="sxs-lookup"><span data-stu-id="4c0b6-112">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)

  - [<span data-ttu-id="4c0b6-113">在 Lync Server 2013 中還原企業版成員伺服器</span><span class="sxs-lookup"><span data-stu-id="4c0b6-113">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-member-server.md)

  - [<span data-ttu-id="4c0b6-114">在 Lync Server 2013 中還原 Lync Server 文件庫</span><span class="sxs-lookup"><span data-stu-id="4c0b6-114">Restoring a Lync Server pool in Lync Server 2013</span></span>](lync-server-2013-restoring-a-lync-server-pool.md)

  - [<span data-ttu-id="4c0b6-115">在 Lync Server 2013 中執行 ABC 前端池容錯移轉</span><span class="sxs-lookup"><span data-stu-id="4c0b6-115">Performing an ABC Front End pool failover in Lync Server 2013</span></span>](lync-server-2013-performing-an-abc-front-end-pool-failover.md)

  - [<span data-ttu-id="4c0b6-116">在 Lync Server 2013 中還原檔案存放區</span><span class="sxs-lookup"><span data-stu-id="4c0b6-116">Restoring a file store in Lync Server 2013</span></span>](lync-server-2013-restoring-a-file-store.md)

  - [<span data-ttu-id="4c0b6-117">在 Lync Server 2013 中還原監視或封存資料</span><span class="sxs-lookup"><span data-stu-id="4c0b6-117">Restoring monitoring or archiving data in Lync Server 2013</span></span>](lync-server-2013-restoring-monitoring-or-archiving-data.md)

  - [<span data-ttu-id="4c0b6-118">在 Lync Server 2013 中還原持續聊天資料</span><span class="sxs-lookup"><span data-stu-id="4c0b6-118">Restoring Persistent Chat data in Lync Server 2013</span></span>](lync-server-2013-restoring-persistent-chat-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

