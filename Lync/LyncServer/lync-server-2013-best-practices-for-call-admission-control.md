---
title: Lync Server 2013：通話許可控制的最佳做法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for call admission control
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398770(v=OCS.15)
ms:contentKeyID: 48184913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b89be654a01615c750ce4f49f866e9339bc7e261
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 中通話許可控制的最佳做法

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-22_

若要增強效能並簡化部署，請在部署 [通話許可控制] 時套用下列最佳做法：

  - 確定 Wan 已充分為目前與預期媒體流量提供適當的配置。
    
    <div>
    

    > [!NOTE]  
    > 我們建議您將緩衝區中的頻寬限制為 [頻寬限制]。 在某些情況下，會影響頻寬限制所使用的總頻寬，並可能導致超出頻寬限制的情況。 例如，如果兩個來電嘗試在媒體流量接近頻寬限制時開始，可能是其中一個呼叫被拒絕，因為另一個管理的專案會先開始。

    
    </div>

  - 監控網路使用量和通話詳細資料記錄，讓您可以選擇最佳的 CAC 設定，並在網路使用量變更時更新 CAC 設定。

  - 使用 CAC 頻寬原則來補充 QoS 設定。

  - 如果您想要將封鎖的通話重新路由到 PSTN，請驗證 PSTN 功能和容量。 如需詳細資訊，請參閱[在 Lync Server 2013 中規劃出站語音路由](lync-server-2013-planning-outbound-voice-routing.md)。
    
    <div>
    

    > [!NOTE]  
    > [容量] 指的是您需要開啟以支援 PSTN 重新路由的埠數。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

