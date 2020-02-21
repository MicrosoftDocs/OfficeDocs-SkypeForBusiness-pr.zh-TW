---
title: Lync Server 2013： 媒體旁路模式
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
ms.openlocfilehash: 56e3c70e8bfc1a475436df97e4f2e3a5b4f32689
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-bypass-modes-in-lync-server-2013"></a>媒體旁路模式的 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-05_

您必須設定全域媒體旁路，並針對每個個別 PSTN 主幹設定媒體旁路。啟用全域媒體旁路時，有兩個選項：**[永遠略過]** 和 **[使用站台和區域資訊]**。

顧名思義，略過的**始終略過**表示將會嘗試所有 PSTN 通話。 **永遠略過**用於部署其中沒有啟用通話許可控制，不需要也不會那里必須指定關於何時嘗試媒體的詳細的組態資訊略過。 此外，完整用戶端與 PSTN 閘道之間的連線能力時，會使用**永遠略過**。 在此組態中，所有的子網路會對應至其中一個，唯一的旁路 ID，這由系統計算。

**使用網站與地區資訊**，與網站和地區設定相關聯的旁路識別碼用來決定旁路。 此組態提供的彈性來設定最常見的拓撲，略過，因為它可讓您微調控制旁路的發生時，除了支援通話許可控制 (CAC) 之間的互動。 系統嘗試自動指派簡化您的工作，如下所示旁路識別碼。

  - 系統會自動指派單一的唯一旁路 ID 給每個區域。

  - 沒有頻寬限制繼承相同透過 WAN 連結連線至區域任何網站的旁路識別碼的區域。

  - 網站與地區相關透過 WAN 頻寬限制的連結從區域指派不同的旁路 ID。

  - 每個站台相關聯的子網路會繼承該網站的旁路識別碼。

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的媒體旁路概觀](lync-server-2013-overview-of-media-bypass.md)  
[媒體旁路和 Lync Server 2013 中的通話許可控制](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Lync Server 2013 中略過媒體的技術需求](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

