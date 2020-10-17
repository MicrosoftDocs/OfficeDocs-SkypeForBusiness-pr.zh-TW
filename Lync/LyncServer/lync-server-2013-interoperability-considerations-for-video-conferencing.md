---
title: Lync Server 2013：視訊會議的互通性考慮
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f71977dc1909fa6993bc21f7944e821276dd86d6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498390"
---
# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的視訊會議的互通性考慮

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

本節說明舊版用戶端與 Lync Server 2013 集區或 Lync Server 2013 用戶端和舊版集區間的互通性時，使用者在遷移共存階段的體驗。

<div>

## <a name="lync-server-2013-pools"></a>Lync Server 2013 集區

當 Lync Server 2013 集區中使用舊版用戶端時，使用者會遇到下列行為：

  - 若為雙方通話，則視訊解析度和舊版集區中相同。

  - 若為多方會議，則視訊解析度及視訊會議功能和舊版集區中相同。不提供圖庫檢視及高解析度。

</div>

<div>

## <a name="legacy-pools"></a>舊版集區

當舊版集區中使用 Lync Server 2013 用戶端時，使用者會遇到下列行為：

  - 如果是兩方通話，Lync Server 2013 用戶端可以使用下列新功能：
    
      - 如果兩位參與者都使用 Lync Server 2013 用戶端，則可以使用264。
    
      - Lync Server 2013 用戶端使用 TotalReceiveVideoBitRateKb 的預設值，因為舊版伺服器不會以帶內布建方式傳送此資訊。

  - 若為多方會議，則視訊解析度及視訊功能和舊版集區中舊版使用者所經歷的相同。

<div>


> [!NOTE]  
> 當舊版伺服器主控 Lync Server 2013 用戶端時，可以設定影片會議頻寬，讓集區中的所有使用者只收到低解析度的影片，但傳送高解析度的影片。 此情況的範例即是在媒體組態中將 MaxVideoRateAllowed 設為 CIF-250K，在會議原則中將 VideoBitRateKb 設為 2000 kbps。 此情況所產生的影響就是集區中的使用者無法收到高解析度。<BR>因為 MaxVideoRateAllowed 已不再用於 Lync Server 2013 用戶端，所以無法防止 Lync Server 2013 用戶端要求高解析度的影片。 改成在會議原則中針對集區的所有使用者，將 VideoBitRateKb 設定為與 MaxVideoRateAllowed 相同的值 (亦即將 CIF 設為 250 kbps，或將 VGA 設為 600 kbps，或將 HD 設為 1500 kbps)。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

