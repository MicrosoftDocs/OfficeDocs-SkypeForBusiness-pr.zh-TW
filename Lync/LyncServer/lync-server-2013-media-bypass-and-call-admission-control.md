---
title: Lync Server 2013：媒體旁路和通話許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and call admission control
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48183454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10915a298fe2e50abdef09dc5acf92927a43cc65
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 中的媒體旁路和通話許可控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

媒體旁路與通話許可控制 (CAC) 可一起運作，管理通話媒體的頻寬控制。媒體旁路有助於媒體在連線良好的連結上流通；CAD 則可管理具有頻寬限制的連結流量。由於媒體旁路與 CAC 會互相排斥，因此規劃時請務必小心。支援下列組合：

  - CAC 與媒體旁路同時啟用。媒體旁路必須設為 **[使用網站與地區資訊]**。該網站與地區資訊必須與 CAC 所使用的網站與地區資訊相同。
    
    若您啟用了 CAC，則您無法選取 **[永遠略過]**，反之亦然，因為兩者的組態會互相排斥。亦即，任何特定的 PSTN 通話一次只能適用其中一種組態。首先，系統會檢查並判斷通話是否可套用媒體旁路。如果是的話，就不會使用 CAC。這麼做是有道理的，因為如果通話適用旁路的話，依據定義會使用不需要 CAC 的連線。如果通話不適用旁路 (亦即，如果用戶端與閘道的旁路 ID 不相符)，則通話會套用 CAC。

  - CAC 未啟用且媒體旁路設為 **[永遠略過]**。
    
    在此組態中，用戶端與主幹子網路會對應至唯一的旁路 ID (由系統計算而來)。

  - CAC 未啟用且媒體旁路設為 **[使用網站與地區資訊]**。
    
    一旦啟用 **[使用網站與地區資訊]**，旁路判斷工作基本上會以相同模式運作，不管 CAC 是否已啟用都沒有影響。亦即，針對任何特定的 PSTN 通話，用戶端的子網路會對應至特定網站，並擷取該子網路的旁路 ID。同理，閘道的子網路會對應至特定網站，並擷取該子網路的旁路 ID。只有兩組旁路 ID 都一模一樣時，通話才會套用旁路。如果沒有一模一樣，將不會套用媒體旁路。
    
    即便 CAC 已經全域停用，如果您想要使用網站與地區組態來控制旁路決策時，還是需要針對每個網站與連結定義頻寬原則。頻寬限制或其模式的實際值並沒有影響。最終目標是讓系統自動計算不同的旁路 ID 以便和未能順利連接的不同區域產生關聯。依據定義，定義頻寬限制代表某個連結並未順利連接。

  - CAC 已啟用而媒體旁路未啟用。 只有當所有閘道與 IP-PBX 並未順利連接，或是不符合其他媒體旁路需求時，才會套用此設定。 如需媒體旁路需求的詳細資訊，請參閱[Lync Server 2013 中媒體旁路的技術需求](lync-server-2013-technical-requirements-for-media-bypass.md)。

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的媒體旁路概述](lync-server-2013-overview-of-media-bypass.md)  
[Lync Server 2013 中的媒體旁路模式](lync-server-2013-media-bypass-modes.md)  
[Lync Server 2013 中媒體旁路的技術需求](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

