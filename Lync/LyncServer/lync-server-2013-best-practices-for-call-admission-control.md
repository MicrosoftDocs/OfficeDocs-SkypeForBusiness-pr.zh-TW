---
title: Lync Server 2013：通話許可控制的最佳作法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for call admission control
ms:assetid: 97173cca-8175-4ae2-a247-eb7ef809da93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398770(v=OCS.15)
ms:contentKeyID: 48184913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be270859304236b0704bc8cc9e1bc29f3e80fcb9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514820"
---
# <a name="best-practices-for-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 中通話許可控制的最佳作法

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-22_

若要增強效能及協助部署，請在部署通話許可控制時套用下列最佳作法：

  - 確定已針對目前和預期的媒體流量充分佈建 Wan。
    
    <div>
    

    > [!NOTE]  
    > 建議您將緩衝區中的頻寬限制考慮在內。 有些案例會影響使用總頻寬的爭用狀況，而且可能會導致超出頻寬限制的情況。 例如，如果兩次來電嘗試在媒體流量接近頻寬限制時啟動，其中一位可能會遭到拒絕，因為另一個管理的功能會先開始。

    
    </div>

  - 監視網路使用量和詳細通話記錄，以便您可以選擇最優 CAC 設定，並在網路使用量變更時更新 CAC 設定。

  - 使用 CAC 頻寬原則來補充 QoS 設定。

  - 如果您想要將封鎖的來電重新路由至 PSTN，請驗證 PSTN 功能和容量。 如需詳細資訊，請參閱 [規劃 Lync Server 2013 中的外寄語音路由](lync-server-2013-planning-outbound-voice-routing.md)。
    
    <div>
    

    > [!NOTE]  
    > 「容量」指的是您需要開啟以支援潛在 PSTN 重新路由的埠數目。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

