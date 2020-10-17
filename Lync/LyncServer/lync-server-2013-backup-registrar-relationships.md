---
title: Lync Server 2013 備份註冊機構關係
description: Lync Server 2013 備份註冊器關聯。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b0bfce6444ae78c2fb792a6d63dba4bf36b1791
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552310"
---
# <a name="backup-registrar-relationships-in-lync-server-2013"></a>Lync Server 2013 中的備份註冊器關聯

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-28_

除了提供災害復原能力之外，兩個配對的集區也可作為彼此的備份登錄器。 在 Lync Server 2013 中，前端集區之間的備份註冊器關聯性永遠都是1:1 和互惠。 這表示，如果 P1 是 P2 的備份，則 P2 必須是 P1 的備份，而且兩者之中的任一個不可成為其他任何前端集區的備份。 這是 Lync Server 2010 所做的變更，前端集區的備份關係可能會是多達一個。

即使兩個前端集區之間的備份關係必須是1:1 及對稱式，每個前端集區也仍然可以是任何數目的 Survivable 分支裝置的備份註冊機構，就像在 Lync Server 2010 中一樣。

請注意，Lync Server 2013 不會將嚴重損壞修復支援擴充至位於 Survivable 分支裝置的使用者。 如果充當 Survivable 分支裝置備份的前端集區中斷，即使在前端集區上的使用者已容錯移轉至備份前端集區之後，登入 Survivable Branch 裝置的使用者也會進入復原模式。

</div>

<span> </span>

</div>

</div>

</div>

