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
ms.openlocfilehash: 8692e01ed9691f69da7be78a2e0437e7829594cb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a>集區容錯移轉和集區容錯回復 Lync Server 2013 中的復原時間

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-10_

集區容錯移轉和集區容錯回復，工程目標復原時間目標 (RTO) 會是 30 分鐘。 這是發生容錯移轉所需的時間，系統管理員已決定那里之後已損毀，並將起始容錯移轉程序。 它不包含評估這種情況，並進行決策，系統管理員的時間，也不會包含使用者重新登入容錯移轉完成後的時間。

集區容錯移轉和集區容錯回復，復原點目標 (RPO) 的工程目標會是 30 分鐘。 這表示可能會由於災害時，因為備份服務的複寫延遲而遺失資料的時間量值。 例如，如果集區失效 10:00 a.m.，而 RPO 是 30 分鐘，資料寫入到 9:30 A.M.之間的集區 和 10:00 A.M.might 不具有複寫至備份集區]，並可能會遺失。

本文件中的所有 RTO 和 RPO 號碼假設兩個資料中心位於高速、 低延遲傳輸的兩個站台之間的相同世界區域內。 這些數字的計算單位是集區 40000 同時作用中的使用者與 200000 位使用者啟用 lync 有關預先定義的使用者模型中的資料複寫是沒有待處理項目。 他們受限於根據效能測試和驗證變更。

</div>

<span> </span>

</div>

</div>

</div>

