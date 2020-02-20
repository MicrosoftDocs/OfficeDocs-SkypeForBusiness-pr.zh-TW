---
title: 電話撥入會議的位置型路由的 Lync Server 2013： 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ce41a338f3185f6f051da3df41e91c6b287af20
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的會議位置型路由的需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-07-19_

所需的安裝與設定位置型路由會議應用程式的需求如下：

  - 必須在所有伺服器或集區拓撲中的部署 Lync Server 2013 累計更新 2年。

<div>


> [!NOTE]  
> 如果在 Lync server 或集區拓撲中的不需要 Lync Server 2013 累計更新 2年或更新版本，不能保證的 Lync 會議的位置型路由的強制執行。



</div>

  - Lync Server 2013 位置型路由是依位置路由會議應用程式的必要條件。 如需設定 Lync Server 2013 Location-Based 路由的進一步資訊，請參閱[Configuring Location-Based 路由](lync-server-2013-configuring-location-based-routing.md)。

  - 位置型路由會議應用程式的需求都是 Lync Server 2013 Location-Based 路由的需求相同。 如需詳細資訊，請參閱[Planning for 位置型的路由](lync-server-2013-planning-for-location-based-routing.md)。

<div>

## <a name="supported-servers"></a>支援的伺服器

位置型路由會議應用程式需要上所有的前端集區和 Standard Edition 伺服器，在您的拓撲中已部署了 Lync Server 2013 累計更新 2年。 如果您的拓樸某些 Lync 伺服器上未安裝 Lync Server 2013 累計更新 2年，位置型路由限制無法完全強制在 Lync 會議和諮詢呼叫傳輸。

下表列出伺服器角色和支援位置型路由的版本的組合。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>前端集區版本</p></td>
<td><p>中繼伺服器版本</p></td>
<td><p>支援</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累計更新 2</p></td>
<td><p>Lync Server 2013 累計更新 2</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 累計更新 2</p></td>
<td><p>Lync Server 2013 累計更新 1</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累計更新 2</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 累計更新 2</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累計更新 1</p></td>
<td><p>任何</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010</p></td>
<td><p>任何</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>任何</p></td>
<td><p>否</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a>支援的用戶端

支援的 Lync 會議的位置 Routing Lync 用戶端將相同的用戶端支援 Lync Server 2013 Location-Based 路由。 如需詳細資訊，請參閱[用戶端與伺服器支援位置型的路由](lync-server-2013-client-and-server-support-for-location-based-routing.md)。

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>諮詢轉接的中繼伺服器需求

位置型路由會議應用程式需要以強制執行諮詢轉接的位置型路由限制部署獨立中繼伺服器。

強制執行的諮詢轉接位置型路由，中繼伺服器必須與只有一個中繼伺服器對等網路建立關聯 (亦即 PBX、 SIP 閘道等等) 其中位置型路由是必要的網路地區。 如果其他媒體伺服器對等會部署在相同的網路地區中，將中繼伺服器對等網路必須與不同的中繼伺服器相關聯。 這項需求詳細說明，如下所示：

  - 每個多個中繼伺服器的單一中繼伺服器對等時諮詢的來電轉接會路由傳送到已設定至多個對等 （亦即 Pbx 與閘道） 的多個 SIP 主幹與諮詢中繼伺服器到中繼伺服器對等網路若要防止諮詢的來電轉接為允許通過某些 SIP 主幹，但不允許透過其他 SIP 主幹的 PSTN 通話費略過會阻止來電轉接。
    
    例如，若是單一中繼伺服器 PSTN 閘道中繼伺服器對等和 PBX 中繼伺服器對等服務，將會遵守下列行為：
    
      - 當從指定的網站 （亦即網站 1） Lync 使用者嘗試將來電轉接與 PSTN 端點給 Lync 使用者從不同的網站 (亦即 site 2) 透過諮詢轉接時，通話會不允許若要防止 PSTN 通話費略過。
    
      - 即使它不會造成潛在 PSTN 工具中，當從指定的網站 （亦即網站 1） Lync 使用者嘗試將來電轉接與中相同的網站 （網站 1） 的 PBX 端點給 Lync 使用者從不同的網站 (亦即 site 2) 透過諮詢轉接時，將不允許通話l 略過。

  - 不同每中繼伺服器對等的中繼伺服器
    
    當諮詢轉接財經中繼伺服器對等網路時，針對單一中繼伺服器所服務的中繼伺服器對等會評估諮詢轉接。 將不允許或允許通話總部在其可能會引起不論網站中所有其他 Mediations 伺服器對等的 PSTN 通話費略過，因為它們由不同的中繼伺服器服務。
    
    例如，在不同的中繼伺服器 PSTN 閘道中繼伺服器對等和 PBX 中繼伺服器對等服務，將會遵守下列行為：
    
      - 當從指定的網站 （亦即網站 1） Lync 使用者嘗試將來電轉接與 PSTN 端點給 Lync 使用者從不同的網站 (亦即 site 2) 透過諮詢轉接時，通話會不允許若要防止 PSTN 通話費略過。
    
      - 當從指定的網站 （亦即網站 1） Lync 使用者嘗試將來電轉接與中相同的網站 （網站 1） 的 PBX 端點給 Lync 使用者從不同的網站 (亦即 site 2) 透過諮詢轉接時，通話會允許因為它不會造成潛在的 PSTN 通話費略過在ing。

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>不受支援的位置型路由的會議應用程式的功能

位置型路由會議應用程式不支援下列功能：

  - 電話撥入式會議。 無法針對撥入式會議強制位置型的路由。 即使會議召集人 Lync 使用者啟用位置型的路由，指定會議的任何撥入要求不限制依位置型的路由。

  - 建議您不佈建位置型路由限制要強制執行的區域中的會議存取號碼。

</div>

</div>

<span> </span>

</div>

</div>

</div>

