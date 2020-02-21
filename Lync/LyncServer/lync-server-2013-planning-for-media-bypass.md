---
title: Lync Server 2013： 規劃媒體旁路
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
ms.openlocfilehash: de3d5132d7307f48de905f5bb6d28e53cbec14a6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a>規劃 Lync Server 2013 中的媒體旁路

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-21_

媒體旁路指的是移除媒體路徑儘通話訊號周遊中繼伺服器移除中繼伺服器。

媒體旁路可以改善語音品質以減少延遲、 不必要的轉譯、 封包遺失的可能性和潛在的失敗點的數目。 延展性可以改良，因為抵銷的媒體略過通話處理會減少中繼伺服器上的負載。 載入此減少補充控制多個閘道中繼伺服器的能力。

媒體旁路其中分支網站沒有中繼伺服器會連線至中央網站透過一或多個頻寬限制的 WAN 連結，以允許媒體直接流向本地閘道不在分支網站的用戶端降低頻寬需求第一次不必流程跨 WAN 連結至中央網站中繼伺服器和備份。

藉由減輕中繼伺服器的媒體處理，媒體旁路還能減少需要 Enterprise Voice 基礎結構的中繼伺服器的數目。

下圖顯示基本媒體和訊號路徑在拓撲中使用及沒有媒體旁路。

**媒體和訊號路徑包含和不含媒體旁路**

![語音 CAC 媒體旁路連線強制執行](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "語音 CAC 媒體旁路連線強制執行")

作為一般規則，請盡可能啟用媒體旁路。

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中的媒體旁路概觀](lync-server-2013-overview-of-media-bypass.md)

  - [媒體旁路模式的 Lync Server 2013](lync-server-2013-media-bypass-modes.md)

  - [媒體旁路和 Lync Server 2013 中的通話許可控制](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Lync Server 2013 中略過媒體的技術需求](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a>相關各節

[部署 Lync Server 2013 中的進階的 Enterprise Voice 功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[設定與 Lync Server 2013 中的媒體旁路的主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[通用媒體旁路 Lync Server 2013 中的選項](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

