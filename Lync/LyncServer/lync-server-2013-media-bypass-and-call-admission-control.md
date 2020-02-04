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
ms.openlocfilehash: 2034a58f686d62ab8e755c0e2c624a9a8994961e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 中的媒體旁路和通話許可控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

[媒體旁路] 和 [呼叫許可控制（CAC）] 共同合作，管理通話媒體的頻寬控制。 [媒體旁路] 有利於在連線的連結上使用媒體流程;CAC 會管理頻寬限制連結的通信量。 因為媒體旁路和 CAC 是互斥的，所以在規劃另一個時，您必須注意到一個。 支援下列組合：

  - 已啟用 CAC 和媒體旁路。 必須將媒體旁路設定為**使用網站和區域資訊**。 此網站和區域資訊與用於 CAC 的資訊相同。
    
    如果您啟用 CAC，您就無法選取 [**永遠略過**]，反之亦然，因為這兩個設定是互相排斥的。 也就是說，只有其中一個是適用于任何已知的 PSTN 通話。 首先，會進行檢查，以判斷媒體旁路是否適用于通話。 如果有的話，則不使用 CAC。 這麼做很有意義，因為如果通話符合旁路，就是使用不需要 CAC 的連線來進行定義。 如果旁路無法套用到通話（也就是用戶端和閘道的旁路識別碼不相符），則會將 CAC 套用到通話。

  - 未啟用 CAC，且媒體旁路設定為 [**總是略過**]。
    
    在這個設定中，用戶端和中繼子網都對應到一個，而且只有一個旁路 ID 是由系統計算。

  - 未啟用 CAC，且媒體旁路設定為**使用網站和區域資訊**。
    
    在啟用 [**使用網站和區域資訊**] 的情況下，旁路判斷的運作方式基本相同，不論是否已啟用 CAC。 也就是說，對於任何已知的 PSTN 呼叫，客戶的子網會對應到特定的網站，而該子網上的旁路識別碼則會被抽取。 同樣地，閘道的子網會對應到特定的網站，而該子網上的旁路識別碼則會解壓縮。 只有當兩個旁路 Id 完全相同時，才會繞過呼叫的情況。 如果兩者不完全相同，則不會發生媒體略過。
    
    即使是全域停用的 CAC，也必須針對每個網站和連結定義頻寬原則，如果您想要使用網站和區域設定來控制旁路決策。 頻寬限制或其模態的實際值並不重要。 最終的目標是讓系統自動計算不同的旁路識別碼，以與沒有良好連接的不同區域設定建立關聯。 依定義定義頻寬限制表示連結未正確連接。

  - 已啟用 CAC，且未啟用媒體旁路功能。 這僅適用于所有閘道與 IP Pbx 沒有正確連接或不符合其他媒體旁路需求的情況。 如需媒體旁路需求的詳細資訊，請參閱[Lync Server 2013 中媒體旁路的技術需求](lync-server-2013-technical-requirements-for-media-bypass.md)。

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的媒體旁路概覽](lync-server-2013-overview-of-media-bypass.md)  
[Lync Server 2013 中的媒體旁路模式](lync-server-2013-media-bypass-modes.md)  
[Lync Server 2013 中媒體旁路的技術需求](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

