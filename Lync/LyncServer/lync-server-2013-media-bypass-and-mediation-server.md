---
title: Lync Server 2013： 媒體旁路和中繼伺服器
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
ms.openlocfilehash: a33ed2c9b3494e9c67e8ac4a658b6aee75ff7649
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a>媒體旁路和 Lync Server 2013 中的中繼伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-21_

媒體旁路的 Lync Server 功能，可讓系統管理員設定通話路由傳送至使用者的端點與公用交換的電話網路 (PSTN) 閘道之間的直接流通而周遊中繼伺服器。 媒體旁路能改善通話品質以減少延遲、 不需要轉譯、 封包遺失的可能性和潛在的失敗點的數目。 媒體旁路其中沒有中繼伺服器的遠端網站透過一或多個與頻寬限制的 WAN 連結連接至中央網站，以啟用媒體直接流向本地閘道不在遠端站台的用戶端降低頻寬需求第一次不必流程跨 WAN 連結至中央網站中繼伺服器和備份。此減少的媒體處理也補充控制多個閘道中繼伺服器的能力。

媒體旁路和通話許可控制 (CAC) 都是互斥的。 如果採用媒體旁路的通話，則不會該通話的執行 CAC。 假設是沒有頻寬限制連結參與通話。

<div>

## <a name="see-also"></a>另請參閱


[通話許可控制和 Lync Server 2013 中的中繼伺服器](lync-server-2013-call-admission-control-and-mediation-server.md)  


[規劃 Lync Server 2013 中的媒體旁路](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

