---
title: Lync Server 2013：會議 Location-Based 路由的需求
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
ms.openlocfilehash: 66be7f9dd3faeb167519d9ce815e84f8cf692c22
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511850"
---
# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中 Location-Based 路由進行會議的需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-19_

以下是安裝和設定 Location-Based 路由會議應用程式所需的需求：

  - Lync Server 2013 累計更新2必須部署在拓撲中的所有伺服器或集區上。

<div>


> [!NOTE]  
> 如果您拓撲中的 Lync server 或集區未安裝 Lync Server 2013 累計更新2或更新版本，則無法保證 Lync 會議的 Location-Based 路由的執行。



</div>

  - Lync Server 2013 Location-Based 路由是 Location-Based 路由會議應用程式的必要條件。 如需設定 Lync Server 2013 Location-Based 路由的詳細資訊，請參閱設定 [Location-Based 路由](lync-server-2013-configuring-location-based-routing.md)。

  - Location-Based 路由會議應用程式的需求與 Lync Server 2013 Location-Based 路由的需求相同。 如需詳細資訊，請參閱 [規劃 Location-Based 路由](lync-server-2013-planning-for-location-based-routing.md)。

<div>

## <a name="supported-servers"></a>支援的伺服器

Location-Based 路由會議應用程式要求在拓撲中的所有 Front-End 集區和 Standard Edition Server 上部署 Lync Server 2013 累計更新2。 如果您在拓撲中的某些 Lync Server 上未安裝 Lync Server 2013 累計更新2，則在 Lync 會議和顧問式來電轉接上，無法完全強制執行 Location-Based 路由限制。

下表識別伺服器角色與支援 Location-Based 路由的版本的組合。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Front-End 集區版本</p></td>
<td><p>轉送伺服器版本</p></td>
<td><p>支援</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累計更新2</p></td>
<td><p>Lync Server 2013 累計更新2</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 累計更新2</p></td>
<td><p>Lync Server 2013 累計更新1</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累計更新2</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 累計更新2</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累計更新1</p></td>
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

支援 Lync 會議 Location-Based 路由的 Lync 用戶端，都是支援 Lync Server 2013 Location-Based 路由的相同用戶端。 如需詳細資訊，請參閱 [用戶端和伺服器支援，以取得 Location-Based 路由](lync-server-2013-client-and-server-support-for-location-based-routing.md)。

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>顧問式來電轉接的轉送伺服器需求

Location-Based 路由會議應用程式需要部署獨立的轉送伺服器，才可在顧問式來電轉接上強制執行 Location-Based 路由限制。

若要強制 Location-Based 路由傳送諮詢來電轉接，轉送伺服器必須與網路地區的一個轉送伺服器對等 (（即 PBX、SIP 閘道等) ）相關聯，Location-Based 路由是必要的。 若其他轉送伺服器對等部署在相同的網路地區，則轉送伺服器必須與不同的轉送伺服器產生關聯。 這項需求如下所述：

  - 每個轉送伺服器對等的單一轉送伺服器當諮詢來電轉接透過已設定多個 SIP 主幹至多個對等 (（亦即 PBXs 和閘道) ）的轉送伺服器路由傳送至轉送伺服器對等時，如果允許透過某些 SIP 主幹，但禁止透過其他 SIP 主幹進行諮詢來電轉接，便會封鎖諮詢來電轉接，以防止 PSTN 長途電話旁路。
    
    例如，如果單一轉送伺服器服務于 PSTN 閘道轉送伺服器對等和 PBX 轉送伺服器對等專案，則會觀測下列行為：
    
      - 指定網站的 Lync 使用者 (例如，site 1) 嘗試使用 PSTN 端點將來電轉接至不同網站中的 Lync 使用者 (亦即，site 2) 透過顧問式轉接，將不允許通話，以避免 PSTN 免付費旁路。
    
      - 指定的網站中的 Lync 使用者 (亦即，site 1) 會嘗試在相同網站 (網站 1) 將來電轉接至不同網站的 Lync 使用者 (亦例如，site 2) 透過諮詢轉接，即使不是出現在潛在的 PSTN 長途電話中，也不會允許通話。

  - 每個轉送伺服器對等各有不同的轉送伺服器
    
    當以轉送伺服器對等方式設定諮詢轉移時，系統會根據轉送伺服器所提供的單一轉送伺服器對等方式來評估顧問式轉接。 此呼叫會因其可能導致 PSTN 電話略過的情況而受到允許或允許，不論其他的轉送伺服器服務于網站中的所有其他 Mediations Server 對等專案。
    
    例如，在為 PSTN 閘道轉送伺服器對等和 PBX 轉送伺服器對等的個別轉送伺服器提供服務時，會看到下列行為：
    
      - 指定網站的 Lync 使用者 (例如，site 1) 嘗試使用 PSTN 端點將來電轉接至不同網站中的 Lync 使用者 (亦即，site 2) 透過顧問式轉接，將不允許通話，以避免 PSTN 免付費旁路。
    
      - 指定的網站中的 Lync 使用者 (亦即，site 1) 會嘗試在相同網站 (網站 1) 將來電轉接至不同網站的 Lync 使用者 (亦例如，site 2) 透過顧問式轉接，但會允許通話，但不是在潛在的 PSTN 長途電話略過。

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>Location-Based 路由會議應用程式不支援的功能

Location-Based 路由會議應用程式不支援下列功能：

  - 電話撥入式會議。 無法對電話撥入式會議強制執行 Location-Based 路由。 即使會議召集人是啟用 Location-Based 路由的 Lync 使用者，Location-Based 路由也不會限制任何對指定會議的撥入要求。

  - 建議您不要在需要強制執行 Location-Based 路由限制的區域中布建會議存取號碼。

</div>

</div>

<span> </span>

</div>

</div>

</div>

