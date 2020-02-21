---
title: 集區容錯移轉和集區容錯回復 Lync Server 2013 復原時間
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
ms.openlocfilehash: fb165fa762b23bd271dde56c0846ccb18adfbf7f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a><span data-ttu-id="2bf6d-102">集區容錯移轉和集區容錯回復 Lync Server 2013 中的復原時間</span><span class="sxs-lookup"><span data-stu-id="2bf6d-102">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bf6d-103">_**主題上次修改日期：** 2012年-09-10_</span><span class="sxs-lookup"><span data-stu-id="2bf6d-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="2bf6d-104">集區容錯移轉和集區容錯回復，工程目標復原時間目標 (RTO) 會是 30 分鐘。</span><span class="sxs-lookup"><span data-stu-id="2bf6d-104">For pool failover and pool failback, the engineering target for recovery time objective (RTO) is 30 minutes.</span></span> <span data-ttu-id="2bf6d-105">這是發生容錯移轉所需的時間，系統管理員已決定那里之後已損毀，並將起始容錯移轉程序。</span><span class="sxs-lookup"><span data-stu-id="2bf6d-105">This is the time required for the failover to happen, after administrators have determined there was a disaster and initiated the failover procedures.</span></span> <span data-ttu-id="2bf6d-106">它不包含評估這種情況，並進行決策，系統管理員的時間，也不會包含使用者重新登入容錯移轉完成後的時間。</span><span class="sxs-lookup"><span data-stu-id="2bf6d-106">It does not include the time for administrators to assess the situation and make a decision, nor does it include the time for users to sign in again after failover is complete.</span></span>

<span data-ttu-id="2bf6d-107">集區容錯移轉和集區容錯回復，復原點目標 (RPO) 的工程目標會是 30 分鐘。</span><span class="sxs-lookup"><span data-stu-id="2bf6d-107">For pool failover and pool failback, the engineering target for recovery point objective (RPO) is 30 minutes.</span></span> <span data-ttu-id="2bf6d-108">這表示可能會由於災害時，因為備份服務的複寫延遲而遺失資料的時間量值。</span><span class="sxs-lookup"><span data-stu-id="2bf6d-108">This represents the time measure of data that could be lost due to the disaster, due to replication latency of the Backup Service.</span></span> <span data-ttu-id="2bf6d-109">例如，如果集區失效 10:00 a.m.，而 RPO 是 30 分鐘，資料寫入到 9:30 A.M.之間的集區</span><span class="sxs-lookup"><span data-stu-id="2bf6d-109">For example, if a pool goes down at 10:00 A.M., and the RPO is 30 minutes, data written to the pool between 9:30 A.M.</span></span> <span data-ttu-id="2bf6d-110">和 10:00 A.M.might 不具有複寫至備份集區]，並可能會遺失。</span><span class="sxs-lookup"><span data-stu-id="2bf6d-110">and 10:00 A.M.might not have replicated to the backup pool, and would be lost.</span></span>

<span data-ttu-id="2bf6d-111">本文件中的所有 RTO 和 RPO 號碼假設兩個資料中心位於高速、 低延遲傳輸的兩個站台之間的相同世界區域內。</span><span class="sxs-lookup"><span data-stu-id="2bf6d-111">All RTO and RPO numbers in this document assume that the two data centers are located within the same world region with high-speed, low-latency transport between the two sites.</span></span> <span data-ttu-id="2bf6d-112">這些數字的計算單位是集區 40000 同時作用中的使用者與 200000 位使用者啟用 lync 有關預先定義的使用者模型中的資料複寫是沒有待處理項目。</span><span class="sxs-lookup"><span data-stu-id="2bf6d-112">These numbers are measured for a pool with 40,000 concurrently active users and 200,000 users enabled for Lync with respect to a pre-defined user model where there is no backlog in data replication.</span></span> <span data-ttu-id="2bf6d-113">他們受限於根據效能測試和驗證變更。</span><span class="sxs-lookup"><span data-stu-id="2bf6d-113">They are subject to change based on performance testing and validation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

