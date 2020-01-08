---
title: Lync Server 2013：媒體旁路模式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a08ec3ae6d985c18e20964a857a74ad40bc7668d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-modes-in-lync-server-2013"></a>Lync Server 2013 中的媒體旁路模式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

您必須針對每個獨立 PSTN 幹線設定全域旁路的媒體。 若要全域啟用媒體，您有兩種選擇：**總是略過**並**使用網站和區域資訊**。

如名稱所示，[**永遠避開**] 表示所有 PSTN 呼叫都會嘗試略過。 **Always 旁路**適用于不需要啟用呼叫許可控制的部署，也不需要指定有關何時嘗試媒體旁路的詳細配置資訊。 此外，在用戶端與 PSTN 閘道之間有完全連線的情況下，也會使用 [**永遠略過**]。 在這個設定中，所有子網都會對應到一個，而且只有一個旁路 ID 是由系統計算。

使用**網站和區域資訊**時，會使用與網站和區域設定關聯的旁路識別碼來進行略過決策。 這項設定可讓您靈活地針對大多數常見拓撲設定略過，因為它不僅支援與通話許可控制（CAC）的互動，也能讓您更精細地控制。 系統會嘗試自動指派旁路識別碼來減輕您的任務，如下所示。

  - 系統會自動為每個區域指派單一唯一的旁路 ID。

  - 在沒有頻寬限制的情況下，通過 WAN 連結連線至某個區域的任何網站，都會繼承與該區域相同的旁路 ID。

  - 在具有有限頻寬的 WAN 連結上，與區域相關聯的網站會指派不同于該區域的旁路 ID。

  - 與每個網站相關聯的子網會繼承該網站的旁路 ID。

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的媒體旁路概覽](lync-server-2013-overview-of-media-bypass.md)  
[Lync Server 2013 中的媒體旁路和通話許可控制](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Lync Server 2013 中媒體旁路的技術需求](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

