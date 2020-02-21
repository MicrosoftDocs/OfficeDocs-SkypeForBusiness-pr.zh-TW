---
title: 將 Survivable Branch Appliance 連接到 Lync Server 2013 前端集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a148b63438710c5faf599b6053dcaf4cce7d0bad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a>將 Survivable Branch Appliance 連接到 Lync Server 2013 前端集區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-05_

每個 Survivable Branch Appliance (SBA) 相關聯的前端集區，其作為備份登錄器 SBA。 當 to Lync Server 2013 升級的前端集區時，SBA 必須分離從前端集區，而升級前端集區。 前端集區將會在升級之後，SBA 可以再重新關聯與前端集區。 這牽涉到在拓撲產生器中從拓撲刪除 SBA，然後再新增 SBA 到拓撲產生器。 使用者位於 SBA 必須移至另一個前端集區從拓撲移除 SBA 之前。 將 SBA 新增回拓撲之後，可以再將使用者移回 SBA。

這些步驟的摘要如下：

1.  移至另一個前端集區隸屬於 SBA 的分支使用者。

2.  移除 SBA 從拓撲，以作為備份登錄器，切斷現有前端集區的關聯。

3.  升級至 Microsoft Lync Server 2013 的前端集區。

4.  將 SBA 新增回拓撲。

5.  將 SBA 的新前端集區產生關聯作為備份登錄器。

6.  將分支使用者移回 SBA。

<div>

## <a name="in-this-section"></a>本章節內容

  - [將 Lync Server 2013 Survivable Branch Appliance 分支網站新增至您的拓撲](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [將 Lync Server 2010 Survivable Branch Appliance 分支網站新增至您的拓撲](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

