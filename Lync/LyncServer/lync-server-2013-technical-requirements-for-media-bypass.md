---
title: Lync Server 2013：媒體旁路的技術需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ad3ea630a173d0925defcd476e6269b7e14e96e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a>Lync Server 2013 中媒體旁路的技術需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

針對每個 PSTN 呼叫，中繼伺服器會決定是否可以直接將來自 Lync 端點的媒體傳送到中繼伺服器對等，而不需要遍歷轉送伺服器。 對等可以是網際網路電話服務提供者（ITSP）上的 PSTN 閘道、IP PBX 或會話邊界控制器（SBC），與呼叫路由的中繼伺服器之間的主幹產生關聯。

當符合下列需求時，可以使用「媒體旁路」：

  - 中繼伺服器對等必須支援媒體略過所需的功能，最重要的是處理多個分叉回應（稱為「早期對話方塊」）。 請與您的閘道或 PBX 製造商或您的 ITSP，以取得閘道、PBX 或 SBC 可接受的最大早期對話方塊數量詞。

  - 中繼伺服器對等必須直接從 Lync 端點接受媒體流量。 許多 ITSPs 只允許其 SBC 接收來自中繼伺服器的流量。 請與您的 ITSP，以判斷其 SBC 是否直接從 Lync 端點接受媒體流量。

  - Lync 用戶端和中繼伺服器對等都必須有良好的連線，這表示它們要麼位於相同的網路區域，或是在連線到區域的網路網站上，這些連結都沒有頻寬限制

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的媒體旁路模式](lync-server-2013-media-bypass-modes.md)  
[Lync Server 2013 中的媒體旁路和通話許可控制](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

