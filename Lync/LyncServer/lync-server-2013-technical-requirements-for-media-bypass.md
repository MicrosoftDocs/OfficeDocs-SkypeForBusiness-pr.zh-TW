---
title: Lync Server 2013： 略過媒體的技術需求
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
ms.openlocfilehash: 5ad685e59616f7f2a90cc8a9d3feb5f4ea669587
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a>Lync Server 2013 中略過媒體的技術需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-21_

中繼伺服器 PSTN 每次呼叫，決定是否可以透過從原點的 Lync 端點的媒體直接到中繼伺服器對等網路傳送而周遊中繼伺服器。 對等可以是 PSTN 閘道、IP-PBX 或網際網路電話服務提供者 (ITSP) 上的工作階段邊界控制器 (SBC) 與路由通話之中繼伺服器之間的主幹關聯。

符合下列需求時，可以使用媒體旁路：

  - 中繼伺服器對等網路必須支援媒體旁路，最重要的是能夠處理 （又稱為 「 早期對話 」） 的多個 invite 的分支回應的必要功能。 請連絡閘道或 PBX 製造商或是 ITSP，以取得閘道、PBX 或 SBC 可以接受的早期對話數上限值。

  - 中繼伺服器對等網路必須接受直接從 Lync 端點的媒體流量。 許多 ITSPs 允許他們只從中繼伺服器接收流量的 SBC。 請連絡 ITSP 來判斷其 SBC 是否接受直接從 Lync 端點的媒體流量。

  - Lync 用戶端和對等網路連線必須良好，這表示他們可以都位於相同的網路地區，或在網路透過 WAN 連線到該區域的站台連結的中繼伺服器有無頻寬限制

<div>

## <a name="see-also"></a>另請參閱


[媒體旁路模式的 Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[媒體旁路和 Lync Server 2013 中的通話許可控制](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

