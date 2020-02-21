---
title: Lync Server 2013： 的視訊會議的互通性考量
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
ms.openlocfilehash: 6157b9dc8867b2f458eafb6f0343fd43a19af537
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的視訊會議的互通性考量

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-02_

舊版用戶端和 Lync Server 2013 集區或 Lync Server 2013 用戶端與舊版集區之間的互通性時，本小節會說明在移轉共存階段期間的使用者經驗。

<div>

## <a name="lync-server-2013-pools"></a>Lync Server 2013 集區

Lync Server 2013 集區中使用舊版用戶端時，使用者會遇到下列行為：

  - 若為雙方通話，則視訊解析度和舊版集區中相同。

  - 若為多方會議，則視訊解析度及視訊會議功能和舊版集區中相同。不提供圖庫檢視及高解析度。

</div>

<div>

## <a name="legacy-pools"></a>舊版集區

當舊版集區中使用 Lync Server 2013 用戶端時，使用者會遇到下列行為：

  - 若為雙方通話，Lync Server 2013 用戶端可用的新功能，如下所示：
    
      - 若雙方參與者皆使用 Lync Server 2013 用戶端使用 H.264。
    
      - 因為舊版伺服器不會傳送此資訊與頻內佈建 Lync Server 2013 用戶端會使用 totalreceivevideobitratekb，預設值。

  - 若為多方會議，則視訊解析度及視訊功能和舊版集區中舊版使用者所經歷的相同。

<div>


> [!NOTE]  
> 當舊版伺服器主控的 Lync Server 2013 用戶端時，就可以設定視訊會議的頻寬，以便在集區上的所有使用者接收僅低解析度的視訊] 中，但傳送高解析度的視訊。 此情況的範例即是在媒體組態中將 MaxVideoRateAllowed 設為 CIF-250K，在會議原則中將 VideoBitRateKb 設為 2000 kbps。 此情況所產生的影響就是集區中的使用者無法收到高解析度。<BR>MaxVideoRateAllowed 不再用於 Lync Server 2013 用戶端，因為它無法防止 Lync Server 2013 用戶端要求高解析度的視訊。 改成在會議原則中針對集區的所有使用者，將 VideoBitRateKb 設定為與 MaxVideoRateAllowed 相同的值 (亦即將 CIF 設為 250 kbps，或將 VGA 設為 600 kbps，或將 HD 設為 1500 kbps)。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

