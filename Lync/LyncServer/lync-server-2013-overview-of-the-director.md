---
title: Director 的 Lync Server 2013： 概觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ac09f5ca7ed67b078b3d5313982cff4af38e835
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a>Lync Server 2013 中 Director 概觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-08_

Director 是執行 Lync Server 2013 的驗證使用者要求，但不會主控任何使用者帳戶的伺服器。 （選用） 可以部署 Director 下列兩種案例：

  - 如果您藉由部署 Edge Server 啟用外部使用者存取，您也應該部署 Director。 在此案例中，Director 驗證外部使用者，並接著將傳遞它們登入內部伺服器的流量。 Director 來驗證外部使用者使用時，它會減輕前端集區伺服器執行驗證這些使用者的額外負荷。 它也可協助將內部前端集區隔離惡意流量，例如拒絕服務攻擊。 無效的外部流量，在這類攻擊大量湧入網路時，此流量結束 Director。

  - 如果您將部署在中央網站的多個前端集區，藉由將 Director 新增至該網站可以簡化驗證要求，並改善效能。 在此案例中，所有要求都前往第一個 Director，然後將它們路由傳送至正確的前端集區。

</div>

<span> </span>

</div>

</div>

</div>

