---
title: Lync Server 2013：還原資料和設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring data and settings
ms:assetid: b07f5dd7-7bed-4819-8cb5-617f5acd478e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202185(v=OCS.15)
ms:contentKeyID: 51541503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 396899d636572e89782112ca7fa445ef1cb255e6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511430"
---
# <a name="restoring-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="59929-102">在 Lync Server 2013 中還原資料和設定</span><span class="sxs-lookup"><span data-stu-id="59929-102">Restoring data and settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59929-103">_**主題上次修改日期：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="59929-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="59929-104">如果您已使用配對集區來執行災難修復拓撲，且其中一個前端集區已停機，且您必須快速將服務還原至使用者，請參閱 [在 Lync Server 2013 中容錯移轉集](lync-server-2013-failing-over-a-pool.md)區。</span><span class="sxs-lookup"><span data-stu-id="59929-104">If you have implemented a disaster recovery topology with paired pools, and one of those Front End pools has gone down and you need to quickly restore service to your users, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="59929-105">否則，使用下列主題中的資訊，以及 [Lync server 2013 備份與還原工作表](lync-server-2013-backup-and-restoration-worksheets.md)中的工作表，在失敗或中斷後還原 Lync server。</span><span class="sxs-lookup"><span data-stu-id="59929-105">Otherwise, use the information in the following topics, along with the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md), to restore Lync Server after a failure or outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="59929-106">若要減少停機時間和潛在的資料遺失，請僅在疑難排解程式無法有效識別和修正問題時，才執行本檔中所述的還原程式。</span><span class="sxs-lookup"><span data-stu-id="59929-106">To reduce downtime and potential data loss, perform the restoration procedures described in this document only if troubleshooting procedures are not effective in identifying and correcting the problem.</span></span> <span data-ttu-id="59929-107">在疑難排解過程中，請嘗試在您關機及重新開機伺服器時，儘量減少對其他伺服器及元件的影響。</span><span class="sxs-lookup"><span data-stu-id="59929-107">During troubleshooting, try to minimize the impact on other servers and components as you shut down and restart servers.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="59929-108">本章節內容</span><span class="sxs-lookup"><span data-stu-id="59929-108">In This Section</span></span>

  - [<span data-ttu-id="59929-109">準備還原 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59929-109">Preparing to restore Lync Server 2013</span></span>](lync-server-2013-preparing-to-restore-lync-server.md)

  - [<span data-ttu-id="59929-110">在 Lync Server 2013 中還原 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="59929-110">Restoring a Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-restoring-a-standard-edition-server.md)

  - [<span data-ttu-id="59929-111">在 Lync Server 2013 中還原主控中央管理存放區的伺服器</span><span class="sxs-lookup"><span data-stu-id="59929-111">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)

  - [<span data-ttu-id="59929-112">在 Lync Server 2013 中還原 Enterprise Edition 後端伺服器</span><span class="sxs-lookup"><span data-stu-id="59929-112">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)

  - [<span data-ttu-id="59929-113">在 Lync Server 2013 中還原 Enterprise Edition 成員伺服器</span><span class="sxs-lookup"><span data-stu-id="59929-113">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-member-server.md)

  - [<span data-ttu-id="59929-114">在 Lync Server 2013 中還原 Lync Server 集區</span><span class="sxs-lookup"><span data-stu-id="59929-114">Restoring a Lync Server pool in Lync Server 2013</span></span>](lync-server-2013-restoring-a-lync-server-pool.md)

  - [<span data-ttu-id="59929-115">在 Lync Server 2013 中執行 ABC 前端集區容錯移轉</span><span class="sxs-lookup"><span data-stu-id="59929-115">Performing an ABC Front End pool failover in Lync Server 2013</span></span>](lync-server-2013-performing-an-abc-front-end-pool-failover.md)

  - [<span data-ttu-id="59929-116">在 Lync Server 2013 中還原檔存放區</span><span class="sxs-lookup"><span data-stu-id="59929-116">Restoring a file store in Lync Server 2013</span></span>](lync-server-2013-restoring-a-file-store.md)

  - [<span data-ttu-id="59929-117">在 Lync Server 2013 中還原監控或封存資料</span><span class="sxs-lookup"><span data-stu-id="59929-117">Restoring monitoring or archiving data in Lync Server 2013</span></span>](lync-server-2013-restoring-monitoring-or-archiving-data.md)

  - [<span data-ttu-id="59929-118">在 Lync Server 2013 中還原 Persistent Chat 資料</span><span class="sxs-lookup"><span data-stu-id="59929-118">Restoring Persistent Chat data in Lync Server 2013</span></span>](lync-server-2013-restoring-persistent-chat-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

