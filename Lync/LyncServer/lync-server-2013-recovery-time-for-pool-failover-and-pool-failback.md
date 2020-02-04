---
title: Lync Server 2013 集區容錯回復與集區容錯移轉的復原時間
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Recovery time for pool failover and pool failback
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205079(v=OCS.15)
ms:contentKeyID: 48184786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fff6f74b5d486c05d01bcd3a911ae674b4f0708
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a><span data-ttu-id="091d9-102">Lync Server 2013 中的集區容錯回復與集區容錯移轉的復原時間</span><span class="sxs-lookup"><span data-stu-id="091d9-102">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="091d9-103">_**主題上次修改日期：** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="091d9-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="091d9-104">針對池容錯移轉和池回切，「恢復時間目標」（RTO）的工程目標是30分鐘。</span><span class="sxs-lookup"><span data-stu-id="091d9-104">For pool failover and pool failback, the engineering target for recovery time objective (RTO) is 30 minutes.</span></span> <span data-ttu-id="091d9-105">這是發生容錯移轉所需的時間，在管理員決定發生災難並啟動容錯移轉程式後。</span><span class="sxs-lookup"><span data-stu-id="091d9-105">This is the time required for the failover to happen, after administrators have determined there was a disaster and initiated the failover procedures.</span></span> <span data-ttu-id="091d9-106">它不會包含管理員評估情況和作出決定的時間，也不會包含使用者在容錯移轉完成後再次登入的時間。</span><span class="sxs-lookup"><span data-stu-id="091d9-106">It does not include the time for administrators to assess the situation and make a decision, nor does it include the time for users to sign in again after failover is complete.</span></span>

<span data-ttu-id="091d9-107">針對池容錯移轉和池回切，「復原點目標」（RPO）的工程目標是30分鐘。</span><span class="sxs-lookup"><span data-stu-id="091d9-107">For pool failover and pool failback, the engineering target for recovery point objective (RPO) is 30 minutes.</span></span> <span data-ttu-id="091d9-108">這代表由於備份服務的複寫延遲，可能會因為災難而遺失的資料時間量。</span><span class="sxs-lookup"><span data-stu-id="091d9-108">This represents the time measure of data that could be lost due to the disaster, due to replication latency of the Backup Service.</span></span> <span data-ttu-id="091d9-109">例如，如果資源庫在 10:00 A.M. 停止，且 RPO 為30分鐘，則在 9:30 A.M. 之間寫入池中的資料</span><span class="sxs-lookup"><span data-stu-id="091d9-109">For example, if a pool goes down at 10:00 A.M., and the RPO is 30 minutes, data written to the pool between 9:30 A.M.</span></span> <span data-ttu-id="091d9-110">而10:00 可能還沒有複製到備份區，因此會遺失。</span><span class="sxs-lookup"><span data-stu-id="091d9-110">and 10:00 A.M.might not have replicated to the backup pool, and would be lost.</span></span>

<span data-ttu-id="091d9-111">本檔中的所有 RTO 與 RPO 數都假設兩個資料中心位於同一個世界區域內，這兩個網站之間的速度較高、低延遲的傳輸。</span><span class="sxs-lookup"><span data-stu-id="091d9-111">All RTO and RPO numbers in this document assume that the two data centers are located within the same world region with high-speed, low-latency transport between the two sites.</span></span> <span data-ttu-id="091d9-112">這些數位是針對40000併發作用中的使用者，以及啟用 Lync 功能的200000使用者（在資料複製中沒有積壓工作的預定義使用者模型）來測量。</span><span class="sxs-lookup"><span data-stu-id="091d9-112">These numbers are measured for a pool with 40,000 concurrently active users and 200,000 users enabled for Lync with respect to a pre-defined user model where there is no backlog in data replication.</span></span> <span data-ttu-id="091d9-113">根據效能測試和驗證，這些專案可能會變更。</span><span class="sxs-lookup"><span data-stu-id="091d9-113">They are subject to change based on performance testing and validation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

