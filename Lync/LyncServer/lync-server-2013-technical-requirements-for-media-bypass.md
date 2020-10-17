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
ms.openlocfilehash: 2789ecc6f72babf2b0267f70705fd41ecd1a7aaf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533790"
---
# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a>Lync Server 2013 中媒體旁路的技術需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

在每次呼叫 PSTN 時，轉送伺服器會判斷從來源的 Lync 端點媒體是否可以直接傳送給轉送伺服器對等，而不需遍歷轉送伺服器。 對等可以是 PSTN 閘道、IP-PBX 或網際網路電話服務提供者 (ITSP) 上的工作階段邊界控制器 (SBC) 與路由通話之中繼伺服器之間的主幹關聯。

符合下列需求時，可以使用媒體旁路：

  - 轉送伺服器對等必須支援媒體旁路所需的功能，最重要的是處理多個分叉回應 (稱為「早期對話方塊」 ) 。 請連絡閘道或 PBX 製造商或是 ITSP，以取得閘道、PBX 或 SBC 可以接受的早期對話數上限值。

  - 轉送伺服器對等必須直接接受來自 Lync 端點的媒體流量。 許多 ITSPs 都允許其 SBC 只從轉送伺服器接收流量。 請與您的 ITSP 聯繫，以判斷其 SBC 是否直接接受來自 Lync 端點的媒體流量。

  - Lync 用戶端和轉送伺服器對等必須已正確連接，這表示它們位於相同網路地區或網路網站，這些連結是以沒有頻寬限制的 WAN 連結連線至區域。

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的媒體旁路模式](lync-server-2013-media-bypass-modes.md)  
[Lync Server 2013 中的媒體旁路和通話許可控制](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

