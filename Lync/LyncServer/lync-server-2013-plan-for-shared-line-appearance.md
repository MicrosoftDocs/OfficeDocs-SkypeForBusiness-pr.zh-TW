---
title: Lync Server 2013：規劃共用行外觀
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
ms.openlocfilehash: ef6bb768ca892aa684613d1261d88266237ab111
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a>在 Lync Server 2013 中規劃共用行外觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-03-21_

閱讀此主題以瞭解如何在 Lync Server 2013 中規劃共用行外觀 (SLA) （累計更新四月2016）。

共用線外觀是 Lync Server 2013 中的一項功能，累積更新4月2016，用來處理特定號碼（稱為共用號碼）上的多個通話。 SLA 可將任何企業語音啟用的 Lync 使用者設定為具有多行的共用號碼，以回應多個通話。 呼叫並未實際接收共用號碼，而是轉寄給充當共用號碼代理人的使用者。 任何一位代理人都可以接聽來電，而其餘的代理人會在他們的電話上取得通知，告知已收取通話的人員，以及哪些線路已變得忙碌的結果。 您可以設定 SLA 中共用號碼的行數和代理人。 此外，高級選項（例如 BusyOption (所有線路忙碌) 和 MissedCallOption 時，會發生什麼情況）。 (所有代理人都不會拾取來電) 的情況，也可以設定共用號碼。

僅在下列電話裝置上支援 SLA，但電腦、行動電話或其他裝置上的 Lync 用戶端不支援 () ：

  - 含固件更新5.4.1 的 Polycom VVX300

  - 含固件更新5.4.1 的 Polycom VVX400

  - 含固件更新5.4.1 的 Polycom VVX500

  - 含固件更新5.4.1 的 Polycom VVX600

SLA 是 Lync Server 2013 中的新功能，累積更新4月2016。

如需部署 SLA 的相關資訊，請參閱[在 Lync Server 2013 中部署共用線路外觀](lync-server-2013-deploy-shared-line-appearance.md)。

<div>

## <a name="feature-list"></a>功能清單

設定 SLA 群組可啟用下列專案：

  - 群組中的所有代理人都可以接聽撥入呼叫相同共用號碼。 通話可以是以 PSTN 為基礎或以 SIP 為基礎。

  - 代理人可以保留及挑選通話。

  - 代理人可將來電轉接至 SLA 群組以外的號碼。

  - 代理人可以查看共用號碼目前有多少通話，並查看每個通話的狀態。

  - 您可以設定共用號碼的並行通話數目上限。 您也可以設定達到上限之後，要如何處理其他呼叫。 過度通話可能會遭到忙碌，但會轉接至備用號碼，或轉接至語音信箱。

  - 您可以設定在特定時間) 進行處理時，要如何撥打未接來電 (通話的方式。 如果您為群組識別碼啟用語音信箱，未接來電會自動移至語音信箱。 如果您未啟用群組身分識別的「 (共用號碼」) 的語音信箱，您可以選擇將未接來電拒絕為繁忙的信號、轉寄至備用號碼，或中斷連線。

</div>

</div>

<span> </span>

</div>

</div>

</div>

