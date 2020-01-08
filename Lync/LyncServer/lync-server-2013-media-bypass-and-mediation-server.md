---
title: Lync Server 2013：媒體旁路和中繼伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8524c0f2556eec339b6698f156966ea95538dbaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a>Lync Server 2013 中的媒體旁路和中繼伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

[媒體旁路] 是一種 Lync 伺服器功能，可讓系統管理員將呼叫路由設定為直接在使用者端點與公用交換電話網絡（PSTN）閘道之間流動，而不需要遍歷中繼伺服器。 媒體旁路可減少延遲、不必要的翻譯、資料包遺失的可能性，以及潛在的故障點數，以改善通話品質。 如果不含轉送伺服器的遠端網站是透過受限制頻寬的一個或多個 WAN 連結連線到中央網站，則媒體略過減少頻寬需求，只要從遠端網站上的用戶端啟用媒體，就能直接流向本機閘道，而不需要首先，必須在中央網站和返回轉送伺服器的 WAN 連結之間流動。媒體處理的減少也會補充轉送伺服器控制多個閘道的能力。

[媒體旁路] 和 [通話許可控制] （CAC）是互斥的。 如果在通話中使用媒體旁路，就不會針對該通話執行 CAC。 假設通話中沒有受限制頻寬的連結。

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的通話許可控制和中繼伺服器](lync-server-2013-call-admission-control-and-mediation-server.md)  


[在 Lync Server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

