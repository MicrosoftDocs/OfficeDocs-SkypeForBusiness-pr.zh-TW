---
title: Lync Server 2013：規劃媒體旁路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa60b6658eca7a73e509a7f6c707c3cf48c7f16e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a>在 Lync Server 2013 中規劃媒體旁路

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

「媒體旁路」是指當信號流經中繼伺服器時，從媒體路徑中移除轉送伺服器。

媒體旁路可減少延遲、不必要的轉換、資料包遺失的可能性，以及可能失敗的點數，以改善語音品質。 可提高可伸縮性，因為取消繞過呼叫的媒體處理減少了中繼伺服器上的負載。 這個負載的減少是補充了轉送伺服器控制多個閘道的能力。

如果不含轉送伺服器的分支網站是透過受限制頻寬的一個或多個 WAN 連結連線到中央網站，媒體略過減少頻寬需求，只要允許分支網站的用戶端媒體直接流向本機閘道，而不首先，必須在中央網站和返回轉送伺服器的 WAN 連結之間流動。

透過從媒體處理中免除轉送伺服器，媒體旁路也可能會減少企業語音結構所需的中繼伺服器數目。

下圖顯示拓撲中的基本媒體與信號路徑，以及不使用媒體旁路的情況。

**媒體與信號路徑，以及不使用媒體旁路**

![語音 Cac 媒體旁路連接強制](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "語音 Cac 媒體旁路連接強制")

一般來說，只要有可能就啟用媒體旁路。

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中的媒體旁路概覽](lync-server-2013-overview-of-media-bypass.md)

  - [Lync Server 2013 中的媒體旁路模式](lync-server-2013-media-bypass-modes.md)

  - [Lync Server 2013 中的媒體旁路和通話許可控制](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Lync Server 2013 中媒體旁路的技術需求](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a>相關各節

[在 Lync Server 2013 中部署高級企業語音功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中使用 [旁路媒體] 設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Lync Server 2013 中的全域媒體旁路選項](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

