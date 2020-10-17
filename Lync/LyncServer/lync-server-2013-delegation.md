---
title: Lync Server 2013：委派
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b31224228a4f2fbdad879e43bab61292852e009c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516301"
---
# <a name="delegation-in-lync-server-2013"></a>Lync Server 2013 中的委派

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-09_

Lync 的委派功能會受到以下列方式 Location-Based 路由的影響：

  - 啟用 Location-Based 路由的代理人代表管理員撥打電話時，代理人的語音原則會用來授權通話，並使用代理人的網站語音路由原則路由傳送通話

  - 針對主管的內送 PSTN 電話，可依照通話轉接及轉接及同時響鈴的主題所述，套用適用于來電轉接或同時振鈴的相同規則。

  - 當代理人將 PSTN 端點設定為同時振鈴目標時，如果是對管理員的來電，就會使用與傳入主幹相關聯之網站的語音路由原則，將通話路由傳送至代理人的 PSTN 端點。

  - 為了進行委派，建議管理員和其相關聯的代理人通常位於相同的網路網站。

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的 Location-Based 路由案例](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

