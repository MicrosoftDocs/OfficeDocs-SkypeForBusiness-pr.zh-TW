---
title: Lync Server 2013 集區容錯回復與集區容錯移轉的復原時間
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Recovery time for pool failover and pool failback
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205079(v=OCS.15)
ms:contentKeyID: 48184786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a746eb96de7b1e22291cf7a147851b313469bed5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a>Lync Server 2013 中的集區容錯回復與集區容錯移轉的復原時間

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-10_

針對池容錯移轉和池回切，「恢復時間目標」（RTO）的工程目標是30分鐘。 這是發生容錯移轉所需的時間，在管理員決定發生災難並啟動容錯移轉程式後。 它不會包含管理員評估情況和作出決定的時間，也不會包含使用者在容錯移轉完成後再次登入的時間。

針對池容錯移轉和池回切，「復原點目標」（RPO）的工程目標是30分鐘。 這代表由於備份服務的複寫延遲，可能會因為災難而遺失的資料時間量。 例如，如果資源庫在 10:00 A.M. 停止，且 RPO 為30分鐘，則在 9:30 A.M. 之間寫入池中的資料 而10:00 可能還沒有複製到備份區，因此會遺失。

本檔中的所有 RTO 與 RPO 數都假設兩個資料中心位於同一個世界區域內，這兩個網站之間的速度較高、低延遲的傳輸。 這些數位是針對40000併發作用中的使用者，以及啟用 Lync 功能的200000使用者（在資料複製中沒有積壓工作的預定義使用者模型）來測量。 根據效能測試和驗證，這些專案可能會變更。

</div>

<span> </span>

</div>

</div>

</div>

