---
title: Lync Server 2013：規劃共用線外觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 755bff84b8902e346135139d1c8c5b26c55605c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a>在 Lync Server 2013 中規劃共用線外觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-03-21_

請閱讀本主題，瞭解如何在 Lync Server 2013 中規劃共用線路外觀（SLA），累積更新4月2016。

[共用線外觀] 是 Lync Server 2013 中的一項功能，累加更新4月2016，用來處理特定號碼的多個通話，稱為共用電話號碼。 SLA 可將任何企業語音啟用的 Lync 使用者設定為含多個線路的共用號碼，以回應多個通話。 通話不會在共用電話號碼上實際接收，而是將其轉寄給充當共用號碼代理人的使用者。 任何一個代理人都可以接聽通話，而其餘的代理人會在他們的電話上收到通知，告知他們接聽通話的人，以及哪個線路變得占線。 您可以在 SLA 中，將行數和代理人都設定為共用的號碼。 此外，高級選項（例如 BusyOption （所有線路都忙的情況下會發生什麼情況）和 MissedCallOption （沒有任何代理人都能接聽通話的情況），也可以設定共用的電話號碼。

只有下列電話裝置支援 SLA （電腦、行動電話或其他裝置不支援 Lync 用戶端）：

  - 含固件更新5.4.1 的 Polycom VVX300

  - 含固件更新5.4.1 的 Polycom VVX400

  - 含固件更新5.4.1 的 Polycom VVX500

  - 含固件更新5.4.1 的 Polycom VVX600

SLA 是 Lync Server 2013 中的新功能，累積更新4月2016。

如需部署 SLA 的相關資訊，請參閱[在 Lync Server 2013 中部署共用線條外觀](lync-server-2013-deploy-shared-line-appearance.md)。

<div>

## <a name="feature-list"></a>功能清單

設定 SLA 群組可啟用下列功能：

  - 群組中的所有代理人都可以將來電應答給相同的共用號碼。 通話可以是 PSTN 或以 SIP 為基礎。

  - 代理人可以保留並挑選通話。

  - 代理人可以將來電轉接到 SLA 群組以外的號碼。

  - 代理人可以查看共用電話號碼目前有多少來電，以及每個通話的狀態。

  - 您可以設定共用電話號碼的最大併發通話數。 您也可以設定在達到此上限之後，您想要處理其他通話的方式。 過多的通話可能會受到占線、轉寄至備用號碼，或轉接至語音信箱。

  - 您可以設定要處理的未接來電（在某個時間之後未拾取來電）。 如果您啟用 [群組身分識別] 的語音信箱，未接來電會自動移至 [語音信箱]。 如果您沒有為群組身分識別（共用電話號碼）啟用語音信箱，您可以選擇讓未接來電遭到使用占線信號，轉寄到備用號碼或中斷連線。

</div>

</div>

<span> </span>

</div>

</div>

</div>

