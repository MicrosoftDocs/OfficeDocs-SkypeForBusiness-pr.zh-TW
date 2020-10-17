---
title: Lync Server 2013：規劃媒體旁路
description: Lync Server 2013：規劃媒體旁路。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d92a50d9d838b0f13fd6837cbfadee1c48712f0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549439"
---
# <a name="planning-for-media-bypass-in-lync-server-2013"></a>在 Lync Server 2013 中規劃媒體旁路

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

媒體旁路是指當呼叫的轉送伺服器的信號流經轉送伺服器時，從媒體路徑移除轉送伺服器。

媒體旁路可減少延遲、不必要的轉譯、封包遺失的可能性，以及潛在失敗的點數，以改善語音品質。 可提高擴充性，因為消除回避通話的媒體處理會減少轉送伺服器上的負載。 這項負載降低負載，對轉送伺服器控制多個閘道的能力有所補充。

在下列情況下，如果沒有轉送伺服器的分支網站會透過一或多個具有限制頻寬的 WAN 連結連線至中央網站，媒體略過可允許來自分支網站用戶端的媒體，以直接流向其本地閘道，而不需要先透過 WAN 連結傳送至中央網站的轉送伺服器和回復。

透過從媒體處理中免除轉送伺服器，媒體旁路也可以減少企業語音基礎結構所需的轉送伺服器數目。

下圖顯示在具有和不含媒體旁路的拓撲中的基本媒體和信號路徑。

**具有和不含媒體旁路的媒體和信號路徑**

![語音 CAC 媒體旁路連接強制](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "語音 CAC 媒體旁路連接強制")

一般來說，盡可能啟用媒體旁路。

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中的媒體旁路概述](lync-server-2013-overview-of-media-bypass.md)

  - [Lync Server 2013 中的媒體旁路模式](lync-server-2013-media-bypass-modes.md)

  - [Lync Server 2013 中的媒體旁路和通話許可控制](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Lync Server 2013 中媒體旁路的技術需求](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a>相關各節

[在 Lync Server 2013 中部署高級 Enterprise Voice 功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定含媒體旁路的主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Lync Server 2013 中的全域媒體旁路選項](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

