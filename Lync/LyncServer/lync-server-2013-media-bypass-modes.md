---
title: Lync Server 2013：媒體旁路模式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35aa8e8a5097be8a4cc90922f014d66b2d8fe2aa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524590"
---
# <a name="media-bypass-modes-in-lync-server-2013"></a>Lync Server 2013 中的媒體旁路模式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

您必須設定全域媒體旁路，並針對每個個別 PSTN 主幹設定媒體旁路。啟用全域媒體旁路時，有兩個選項：**[永遠略過]** 和 **[使用站台和區域資訊]**。

顧名思義， **Always 旁路** 表示所有 PSTN 通話都會嘗試略過。 **Always 旁路** 用於無需啟用通話許可控制的部署，也不需要指定有關何時嘗試媒體旁路的詳細設定資訊。 此外，當用戶端與 PSTN 閘道之間有完全連線時，就會使用 **Always 略過** 。 在此設定中，所有子網都會對應至其中一個，而不是由系統所計算的一個旁路識別碼。

使用 **網站與地區資訊**時，與網站與地區設定相關聯的旁路識別碼是用來進行旁路決定。 這項設定可讓您靈活地為大多數常見拓撲設定旁路，因為它可讓您在略過時進行精細的控制，也就是以通話許可控制來支援互動 (CAC) 。 系統會嘗試自動依下列方式指派旁路 IDs，以簡化您的工作。

  - 系統會自動為每個地區指派單一的唯一旁路識別碼。

  - 透過 WAN 連結連線至區域的任何網站，只要沒有頻寬限制，就會繼承該地區的相同旁路識別碼。

  - 在具有限制頻寬的 WAN 連結上，與區域相關聯的網站會被指派不同于該地區的回避識別碼。

  - 與每個網站相關聯的子網會繼承該網站的旁路識別碼。

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的媒體旁路概述](lync-server-2013-overview-of-media-bypass.md)  
[Lync Server 2013 中的媒體旁路和通話許可控制](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Lync Server 2013 中媒體旁路的技術需求](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

