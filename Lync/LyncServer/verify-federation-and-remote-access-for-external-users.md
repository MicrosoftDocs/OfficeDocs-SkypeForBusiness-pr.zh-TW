---
title: 驗證同盟及外部使用者的遠端存取
description: 驗證外部使用者的同盟及遠端存取。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ac36f2e1b6c5ddfd889810ba2a3ab4d82b7ae33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555069"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>驗證同盟及外部使用者的遠端存取

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-18_

將同盟路由轉換至 Lync Server 2013 Edge Server 之後，您應該執行一些功能測試，以確認同盟如預期般執行。 外部使用者存取的測試應該包含組織支援的每種外部使用者類型，包括下列任一項或所有項目。

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>測試外部使用者與外部存取連線能力

  - 至少一個同盟網域中的使用者、Lync Server 2013 上的內部使用者，以及 Lync Server 2010 上的使用者。 測試立即訊息 (IM)、目前狀態、音訊/視訊 (A/V) 及桌面共用。

  - 您的組織所支援的每個公用 IM 服務提供者的使用者， (及已完成的布建) 與 Lync server 2013 上的使用者進行通訊，以及在 Lync Server 2010 上的使用者進行通訊。

  - 確認匿名使用者可以加入會議。

  - 在 Lync Server 2010 上主控的使用者，使用遠端使用者存取 (從內部網路外部登入 Lync Server 2010，但沒有與 Lync server 2013 上的使用者搭配 VPN) ，以及 Lync Server 2010 上的使用者。 測試 IM、目前狀態、A/V 及桌面共用。

  - 在 Lync Server 2013 上主控的使用者，使用遠端使用者存取 (從內部網路外部登入 Lync Server 2013，但沒有與 Lync server 2013 上的使用者搭配 VPN) ，以及 Lync Server 2010 上的使用者。 測試 IM、目前狀態、A/V 及桌面共用。

</div>

</div>

<span> </span>

</div>

</div>

</div>

