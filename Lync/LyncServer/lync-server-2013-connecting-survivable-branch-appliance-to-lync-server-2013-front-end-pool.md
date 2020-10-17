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
ms.openlocfilehash: b7a637716f1e5b1a2082f694554951d42f36978f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502020"
---
# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a>將 Survivable Branch Appliance 連接到 Lync Server 2013 前端集區

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

每個 Survivable Branch 裝置 (SBA) 都與前端集區相關聯，以充當 SBA 的備份註冊機。 當前端集區升級至 Lync Server 2013 時，當前端集區升級時，SBA 必須與前端集區解除關聯。 在升級前端集區之後，即可使用前端集區 reassociated SBA。 這牽涉到在拓撲產生器中從拓撲刪除 SBA，然後再新增 SBA 到拓撲產生器。 位於 SBA 上的使用者必須先移至另一個前端集區，然後才能從拓撲中移除 SBA。 將 SBA 新增回拓撲之後，可以再將使用者移回 SBA。

這些步驟的摘要如下：

1.  將位於 SBA 的分支使用者移至另一個前端集區。

2.  從拓撲移除 SBA，以解除現有前端集區與備份註冊機的關聯。

3.  將前端集區升級至 Microsoft Lync Server 2013。

4.  將 SBA 新增回拓撲。

5.  將新的前端集區與 SBA 做為備份註冊機關聯。

6.  將分支使用者移回 SBA。

<div>

## <a name="in-this-section"></a>本章節內容

  - [將 Lync Server 2013 Survivable 分支裝置分支網站新增至您的拓撲](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [將 Lync Server 2010 Survivable 分支裝置分支網站新增至您的拓撲](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

