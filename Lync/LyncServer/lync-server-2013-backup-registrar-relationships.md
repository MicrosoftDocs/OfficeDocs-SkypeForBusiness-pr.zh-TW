---
title: Lync Server 2013 備份登錄器關聯
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a642c8d8872b2c0d1372a209c9c05dac704ee20
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a>Lync Server 2013 中的備份登錄器關聯

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-28_

除了提供災害復原能力之外，有兩個成對的池充當彼此的備份註冊機構。 在 Lync Server 2013 中，前端池之間的備份註冊機構關聯通常是1:1 和互惠。 這表示如果 P1 是 P2 的備份，則 P2 必須是 P1 的備份，而且不可以是任何其他前端池的備份。 這是 Lync Server 2010 所做的變更，在這種情況下，前端池備份關聯可能有多個。

即使兩個前端池之間的備份關聯必須是1:1 和對稱式，每個前端池也可以是任意數量的 Survivable 分支裝置的備份註冊機構，就像在 Lync Server 2010 中一樣。

請注意，Lync Server 2013 不會將災害復原支援延伸至 Survivable 分支裝置上的使用者。 如果前端池是 Survivable 分支裝置的備份，則登入 Survivable 分支裝置的使用者也會進入復原模式，即使使用者駐留在頂層池之後，也會發生容錯移轉到備份前端池。

</div>

<span> </span>

</div>

</div>

</div>

