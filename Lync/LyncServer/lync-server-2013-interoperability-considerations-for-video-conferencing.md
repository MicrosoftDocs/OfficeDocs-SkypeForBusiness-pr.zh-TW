---
title: Lync Server 2013：視訊會議的互通性考慮
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 880b2e41a1ea92b3d6da9cd29153695b474e88f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的視訊會議的互通性考慮

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

本節說明當舊版用戶端與 Lync server 2013 池或 Lync Server 2013 用戶端與舊版池之間的互通性時，在遷移共存階段中的使用者體驗。

<div>

## <a name="lync-server-2013-pools"></a>Lync Server 2013 池

當舊版用戶端用於 Lync Server 2013 池中時，使用者會遇到下列行為：

  - 對於雙方通話，影片解析度就與舊版池中的相同。

  - 對於多方會議，影片解析度和視訊會議功能與舊版池中相同。 [庫視圖] 和 [高解析度] 無法使用。

</div>

<div>

## <a name="legacy-pools"></a>舊版池

在舊版池中使用 Lync Server 2013 用戶端時，使用者會遇到下列行為：

  - 對於雙方通話，Lync Server 2013 用戶端可以使用下列新功能：
    
      - 如果兩個參與者都使用 Lync Server 2013 用戶端，則可以使用 h-p。
    
      - Lync Server 2013 用戶端會使用 TotalReceiveVideoBitRateKb 的預設值，因為舊版伺服器不會以帶外的置備傳送此資訊。

  - 對於多方會議，影片解析度和視訊會議功能與舊版池中的舊版用戶端所體驗。

<div>


> [!NOTE]  
> 當舊版伺服器承載 Lync Server 2013 用戶端時，您可以設定視訊會議頻寬，讓該文件庫上的所有使用者只收到低解析度的影片，但傳送高解析度的影片。 例如，當您在媒體設定中將 MaxVideoRateAllowed 設定為 CIF-250K，且 VideoBitRateKb 在會議原則中設定為 2000 kbps 時會發生這種情況。 此情況的實際效果是，不可能針對該池使用者提供高解析度。<BR>因為 MaxVideoRateAllowed 已不再用於 Lync Server 2013 用戶端，所以無法防止 Lync Server 2013 用戶端要求高解析度的影片。 相反地，請將所有使用者在會議原則中的 [VideoBitRateKb] 設定為與 MaxVideoRateAllowed 相同的值（即，CIF 設定為 250 kbps，或將 600 VGA 設定為 1500 kbps）。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

