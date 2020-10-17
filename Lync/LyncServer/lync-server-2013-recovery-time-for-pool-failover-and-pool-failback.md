---
title: Lync Server 2013 集區容錯移轉及集區容錯移轉的復原時間
description: Lync Server 2013 集區容錯移轉及集區回切的復原時間。
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
ms.openlocfilehash: 1bb09c32ac4d062358a511464dc21aa7346ee034
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559169"
---
# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a><span data-ttu-id="4792f-103">Lync Server 2013 的集區容錯移轉及集區回復器恢復時間</span><span class="sxs-lookup"><span data-stu-id="4792f-103">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4792f-104">_**主題上次修改日期：** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="4792f-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="4792f-105">針對集區容錯移轉及集區容錯移轉，「恢復時間目標」的工程目標 (RTO) 30 分鐘。</span><span class="sxs-lookup"><span data-stu-id="4792f-105">For pool failover and pool failback, the engineering target for recovery time objective (RTO) is 30 minutes.</span></span> <span data-ttu-id="4792f-106">這是容錯移轉所需的時間，在管理員決定發生災難並初始化容錯移轉程式之後。</span><span class="sxs-lookup"><span data-stu-id="4792f-106">This is the time required for the failover to happen, after administrators have determined there was a disaster and initiated the failover procedures.</span></span> <span data-ttu-id="4792f-107">它不包括管理員評估情況和作出決定的時間，也不包括使用者在容錯移轉完成後再次登入的時間。</span><span class="sxs-lookup"><span data-stu-id="4792f-107">It does not include the time for administrators to assess the situation and make a decision, nor does it include the time for users to sign in again after failover is complete.</span></span>

<span data-ttu-id="4792f-108">針對集區容錯移轉及集區回復，復原點目標的工程目標 (RPO) 為30分鐘。</span><span class="sxs-lookup"><span data-stu-id="4792f-108">For pool failover and pool failback, the engineering target for recovery point objective (RPO) is 30 minutes.</span></span> <span data-ttu-id="4792f-109">這代表由於備份服務的複寫延遲而因災難而遺失的資料時間量。</span><span class="sxs-lookup"><span data-stu-id="4792f-109">This represents the time measure of data that could be lost due to the disaster, due to replication latency of the Backup Service.</span></span> <span data-ttu-id="4792f-110">例如，如果集區在 10:00 A.M. 時停機，RPO 為30分鐘，將資料寫入至集區的 9:30 A.M.。</span><span class="sxs-lookup"><span data-stu-id="4792f-110">For example, if a pool goes down at 10:00 A.M., and the RPO is 30 minutes, data written to the pool between 9:30 A.M.</span></span> <span data-ttu-id="4792f-111">和 10:00 A.M。可能尚未複製到備份組區，將會遺失。</span><span class="sxs-lookup"><span data-stu-id="4792f-111">and 10:00 A.M.might not have replicated to the backup pool, and would be lost.</span></span>

<span data-ttu-id="4792f-112">本檔中的所有 RTO 和 RPO 都是以兩個網站之間的高速度、低延遲傳輸的方式，假設兩個資料中心位於相同的世界地區內。</span><span class="sxs-lookup"><span data-stu-id="4792f-112">All RTO and RPO numbers in this document assume that the two data centers are located within the same world region with high-speed, low-latency transport between the two sites.</span></span> <span data-ttu-id="4792f-113">這些數位是針對包含40000個同時作用中使用者的集區200000，以及在資料複寫中未進行待辦事項的預先定義使用者模型啟用 Lync 的使用者。</span><span class="sxs-lookup"><span data-stu-id="4792f-113">These numbers are measured for a pool with 40,000 concurrently active users and 200,000 users enabled for Lync with respect to a pre-defined user model where there is no backlog in data replication.</span></span> <span data-ttu-id="4792f-114">它們可能會根據效能測試和驗證而變更。</span><span class="sxs-lookup"><span data-stu-id="4792f-114">They are subject to change based on performance testing and validation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

