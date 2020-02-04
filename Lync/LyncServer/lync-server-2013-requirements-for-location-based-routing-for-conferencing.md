---
title: Lync Server 2013：適用于會議的位置路由需求
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
ms.openlocfilehash: ac57a32476d80ab1aca5d2ad0928e2862a4c8558
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 中針對位置路由的會議需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-19_

以下是安裝與設定以位置為基礎的路由會議應用程式所需的需求：

  - Lync Server 2013 累計更新2必須部署在您拓撲中的所有伺服器或池上。

<div>


> [!NOTE]  
> 如果您拓撲中的 Lync server 或 pool 沒有安裝 Lync Server 2013 累積更新2或更新版本，則無法保證 Lync 會議的位置路由。



</div>

  - Lync Server 2013 以位置為基礎的路由是位置路由會議應用程式的先決條件。 如需有關設定 Lync Server 2013 位置路由的進一步資訊，請參閱設定以[位置為基礎的路由](lync-server-2013-configuring-location-based-routing.md)。

  - 以位置為基礎的路由會議應用程式的需求與 Lync Server 2013 位置路由的需求相同。 如需詳細資訊，請參閱[規劃以位置為基礎的路由](lync-server-2013-planning-for-location-based-routing.md)。

<div>

## <a name="supported-servers"></a>支援的伺服器

以位置為基礎的路由會議應用程式要求 Lync Server 2013 累計更新2部署在您拓撲中的所有前端池和標準版伺服器上。 如果您在拓撲中的部分 Lync 伺服器上沒有安裝 Lync Server 2013 累積更新2，則無法在 Lync 會議和諮詢式來電轉接上完全強制執行以位置為基礎的路由限制。

下表列出支援位置路由的伺服器角色與版本組合。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>前端池版本</p></td>
<td><p>中繼伺服器版本</p></td>
<td><p>受</p></td>
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
<td><p>Office 通訊伺服器 2007 R2</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 累計更新1</p></td>
<td><p>每</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010</p></td>
<td><p>每</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>Office 通訊伺服器 2007 R2</p></td>
<td><p>每</p></td>
<td><p>否</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a>支援的用戶端

支援 lync 會議以位置為基礎路由的 Lync 用戶端，是支援 Lync Server 2013 位置路由的相同用戶端。 如需詳細資訊，請參閱[用戶端與伺服器支援的位置路由](lync-server-2013-client-and-server-support-for-location-based-routing.md)。

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a>針對諮詢式來電轉接的中繼伺服器需求

以位置為基礎的路由會議應用程式需要部署獨立的中繼伺服器，才能在諮詢式來電轉接上強制執行以位置為基礎的路由限制。

若要強制進行依位置路由的諮詢式來電轉接，中繼伺服器必須與網路區域中的一個中繼伺服器對等（亦即 PBX、SIP 閘道等）建立關聯，且需要以位置為基礎的路由。 如果有其他的轉送伺服器對等部署在相同的網路區域中，則必須將中繼伺服器對等專案與不同的中繼伺服器產生關聯。 此需求如下所述：

  - 在每個多個中繼伺服器對等的情況下，如果將諮詢式來電轉接傳送給中繼伺服器對多個對等（例如 Pbx 和閘道）所設定的轉送伺服器，請諮詢如果允許透過某些 SIP trunks 進行諮詢式來電轉接，但不允許透過其他 SIP trunks，通話轉移遭到封鎖，以避免 PSTN 長途電話旁路。
    
    例如，如果單一中繼伺服器提供服務于 PSTN 閘道伺服器對等與 PBX 轉送伺服器對等，則會觀察到下列行為：
    
      - 當來自特定網站的 Lync 使用者（亦即網站1）嘗試透過諮詢式轉接從不同的網站（亦即 site 2），從另一個網站（亦稱為 site 2）的 PSTN 端點轉接來電時，該呼叫將不能避免 PSTN 免付費旁路。
    
      - 當來自特定網站的 Lync 使用者（亦即網站1）嘗試從另一個網站（網站1）的 PBX 端點將來電轉接至 Lync 使用者（亦即 site 2）從顧問式轉接傳送時，即使該通話不會出現在潛在的 PSTN tol 中，也不允許呼叫。l 略過。

  - 針對每個中繼伺服器對等不同的中繼伺服器
    
    當導向式轉接以中繼伺服器對等為目標時，會針對中繼伺服器所服務的單一中繼伺服器對等來評估諮詢式轉移。 如果網站中的所有其他 Mediations 伺服器對都是由個別的中繼伺服器提供服務，則會禁止或允許呼叫（根據其在 PSTN 免付費旁路中的可能性）。
    
    例如，在個別的中繼伺服器為 PSTN 閘道轉送伺服器對等，以及 PBX 轉送伺服器對等時，系統會觀察到下列行為：
    
      - 當來自特定網站的 Lync 使用者（亦即網站1）嘗試透過諮詢式轉接從不同的網站（亦即 site 2），從另一個網站（亦稱為 site 2）的 PSTN 端點轉接來電時，該呼叫將不能避免 PSTN 免付費旁路。
    
      - 當來自特定網站的 Lync 使用者（亦即網站1）嘗試從另一個網站（網站1）的 PBX 端點將來電轉接至 Lync 使用者（亦即網站2）透過顧問式轉接傳送時，會允許通話，因為在潛在的 PSTN 免付費旁路中不會發生這種情況。運算.

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a>以位置為基礎的路由會議應用程式不支援的功能

以位置為基礎的路由會議應用程式不支援下列功能：

  - 電話撥入式會議。 在電話撥入式會議中不能強制執行以位置為基礎的路由。 即使會議召集人是啟用位置路由的 Lync 使用者，任何對指定會議的撥入要求不會受到依位置路由的限制。

  - 建議您不要在需要強制執行位置式路由限制的區域中，設定會議存取號碼。

</div>

</div>

<span> </span>

</div>

</div>

</div>

