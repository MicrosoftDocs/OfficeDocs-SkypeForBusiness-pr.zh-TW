---
title: Lync Server 2013：媒體旁路和轉送伺服器
description: Lync Server 2013：媒體旁路和轉送伺服器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebb005d3d52fa9e5a38fdf56a65dfcbd73616d87
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556429"
---
# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a>Lync Server 2013 中的媒體旁路和轉送伺服器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

媒體旁路是一種 Lync Server 功能，可讓系統管理員設定通話路由，以直接在使用者端點和公用交換電話網路 (PSTN) 閘道之間流動，而不需遍歷轉送伺服器。 媒體旁路可減少延遲、不必要的轉譯、封包遺失的可能性，以及潛在的失敗點數量，以提升通話品質。 當一或多個具有限制頻寬的 WAN 連結將沒有轉送伺服器的遠端網站連線到中央網站時，媒體略過可讓來自遠端網站用戶端的媒體直接流向其本機閘道，而不需要先跨 WAN 連結傳送至中央網站和封底的轉送伺服器。這種媒體處理的減少也會補充轉送伺服器控制多個閘道的能力。

媒體旁路和通話許可控制 (CAC) 相互排斥。 如果為通話使用媒體旁路，則不會對該通話執行 CAC。 假設通話中沒有與受限制的頻寬相關的連結。

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的通話許可控制和轉送伺服器](lync-server-2013-call-admission-control-and-mediation-server.md)  


[在 Lync Server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

