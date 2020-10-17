---
title: Lync Server 2013 會議使用者模型
description: Lync Server 2013 會議使用者模型。
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
ms.openlocfilehash: 699f41303b82f4d8fd2864cbf1b29a1c601b826e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555979"
---
# <a name="the-conferencing-user-model-in-lync-server-2013"></a>Lync Server 2013 中的會議使用者模型

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

Lync Server 會議使用者模型的重要部分是會議大小。 從多個資料點收集資料之後 (如上一節) 所述，我們決定下列專案：

  - 大多數的會議實際上是小型共同作業會議，平均有四位參與者

  - 大約80% 的會議人數少於20位參與者。

  - 99.98% 的會議人數少於100位參與者。

除了會議大小之外，會議使用者模型也會考慮各種因素，例如：

  - **並行會議**    預計會議中的使用者人數為何？

  - **媒體組合**    哪些類型的媒體可供會議中的使用者使用？

  - **使用者類型**    使用者是內部使用者、遠端使用者、同盟使用者還是匿名使用者？

  - **會議斜接時間**    會議的所有使用者加入會議所需的時間多久？

如需使用者模型的詳細資訊，請參閱 [Lync Server 2013 中的使用者模型](lync-server-2013-user-models.md)。

若要決定用於測試的會議和使用者數目，請執行下列操作：

  - 使用組織中的使用者總數 (例如，80000使用者) 並乘以會議並行比率 (例如，所有使用者的 5%) ，以判斷預計在會議中的使用者總數 (在此範例中，4000使用者) 。

  - 將使用者總數乘以「部署 (中的 Lync Server 2013，前端伺服器數目（例如，8部伺服器) ，以判斷每一部前端伺服器的會議參與者預估數目 (在此範例中，每個前端伺服器的500使用者) 。

  - 依平均會議大小分割每一前端伺服器的使用者數目 (例如，4位使用者) 以判斷每個前端伺服器的估計平均會議數目 (本範例中，每個前端伺服器) 125 個會議。

  - 若要在每一部前端伺服器上取得每個媒體負載，我們預估介質組合。 例如，假設75% 的會議只需要音訊支援，而這些會議的50% 需要應用程式共用，平均47會議和188使用者同時連線到每個前端伺服器以進行應用程式共用。

  - 根據在共用集區中的最高250使用者的使用者模型，測試各種會議大小 () ，以確保伺服器的可擴充性。

</div>

<span> </span>

</div>

</div>

</div>

