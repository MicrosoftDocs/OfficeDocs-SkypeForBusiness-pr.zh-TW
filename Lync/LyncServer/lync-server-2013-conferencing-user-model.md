---
title: Lync Server 2013 會議使用者模型
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f517e6d3ea3a832c4331377fa49ef7e474377de
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a>Lync Server 2013 中的會議使用者模型

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

Lync Server 會議使用者模型的重要部分是會議大小。 從多個資料點收集資料之後（如下一節所述），我們已決定下列事項：

  - 大多數的會議實際上都是小型共同作業會議，平均需要四個到六個參與者

  - 大約80% 的會議人數少於20名參與者。

  - 99.98% 的會議人數少於100個參與者。

除了會議大小以外，會議使用者模型也會考慮多種不同的因素，例如：

  - **同時**在會議上有多少使用者想要同時參與會議？   

  - **媒體混合**   使用哪些類型的媒體，且預期會供會議中的使用者使用？

  - **使用者類型**   是使用者內部使用者、遠端使用者、聯盟使用者或匿名使用者？

  - **會議加速**   會議的所有使用者加入會議需要多少時間？

如需使用者模型的詳細資料，請參閱[Lync Server 2013 中的使用者模型](lync-server-2013-user-models.md)。

若要決定用來測試的會議和使用者數量，我們已執行下列動作：

  - 佔用組織中的使用者總數（例如，80000的使用者），並將其乘以會議併發費率（例如，5% 的所有使用者）來判斷會議中預期的使用者總數（在此範例中為、4000使用者）。

  - 依部署中的 Lync Server 2013、前端伺服器數（例如，8個伺服器），以判斷每個前端伺服器的會議參與者估計人數（在此範例中為每個前端伺服器的500使用者）。

  - 以平均會議大小（例如4個使用者）劃分每個前端伺服器的使用者數目，以判斷每個前臺伺服器估計的平均會議數（在這個範例中，每個前端伺服器的125會議）。

  - 若要在每個前端伺服器上取得每個媒體負載，我們會估計媒體組合。 例如，假設75% 的會議不只需要音訊支援，而這些會議的50% 需要應用程式共用，平均47會議和188使用者都連線到每個前端伺服器以進行應用程式共用。

  - 已測試各種會議大小（根據我們在共用池中最多250個使用者的使用者模型），以確保伺服器的可伸縮性。

</div>

<span> </span>

</div>

</div>

</div>

