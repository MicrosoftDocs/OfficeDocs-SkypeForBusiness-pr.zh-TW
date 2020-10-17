---
title: Lync Server 2013：語音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice routes
ms:assetid: a2ddf327-2ec4-407b-af0f-276f2b13eefd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412757(v=OCS.15)
ms:contentKeyID: 48185038
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0f457fc96981927ea2b6cb4d4177488dc3f5231
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535490"
---
# <a name="voice-routes-in-lync-server-2013"></a>Lync Server 2013 中的語音路由

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

通話路由會指定 Lync Server 如何處理 Enterprise Voice 使用者撥出的電話。 當使用者撥打號碼時，前端伺服器會將撥號字串正常化為 e.164 格式（如有必要），並嘗試將它與 SIP URI 進行比對。 如果伺服器無法進行相符，它會根據數目來套用傳出的呼叫路由邏輯。 定義該邏輯的最後一個步驟，就是針對每一組每個撥號對應表中所列的目的地電話號碼建立個別命名的呼叫路由。

在您定義撥出電話路由之前，您應該完成下列步驟：

  - 部署一或多個主幹。

  - 視需要建立網站、個人和連絡人物件的撥號對應表。

  - 建立公用交換電話網路 (PSTN) 使用方式記錄。

此外，若要啟用撥出電話路由，您必須建立並指派一或多個語音原則。 您可以在定義撥出電話路由之前或之後執行此動作。

您必須為每個路由指定下列專案：

  - 可輕鬆識別路由的名稱。

  - 選用的描述，在僅限名稱可能不足以描述路由的情況。

  - 正則運算式比對模式，用來識別路由所套用的目的地電話號碼，以及不會套用對應模式的例外狀況。

  - 您想要指派給路由的一或多個主幹。

  - 使用者必須具備的 PSTN 使用方式記錄，才能呼叫符合目的地電話號碼正則運算式的號碼。

您可以在 Lync Server 控制台中指定通話路由。 這些呼叫路由會填入伺服器路由表，Lync Server 會使用該表格路由傳送目的地為 PSTN 的電話。

<div>

## <a name="mn-trunk-support"></a>M:N 主幹支援

Lync Server 提供如何將通話路由傳送至 PSTN 的彈性。 語音路由會為 PSTN 指定一組主幹，以供特定語音通話使用。 主幹會將轉送伺服器與埠號碼與 PSTN 閘道和聆聽埠號碼產生關聯。 這個邏輯關聯可讓轉送伺服器與多個閘道產生關聯，並有多個連線到同一個閘道。 在定義呼叫路由時，您會指定與該路由相關聯的主幹，但不會指定哪些轉送伺服器與路由相關聯。 若要透過定義轉送伺服器和 PSTN 閘道、IP PBXs 及會話邊界控制器之間的關係來建立主幹 (SBCs) ，請使用拓撲產生器。

</div>

<div>

## <a name="least-cost-routing"></a>Least-Cost 路由

指定傳送不同數位之主幹的功能，可讓您判斷哪個路由會產生最低的成本，並據此加以實施。 選取主幹的一般規則是選擇與目的地編號最接近之閘道的主幹，以最小化長途話費。 例如，如果您在紐約撥打的電話號碼，您可以使用羅馬 office 中的閘道來傳送 IP 網路的電話，因此只會對本機通話收取費用。

如需如何使用最低成本路由的範例，請考慮下列各項： Fabrikam 決定讓德文使用者使用 U.S. 主幹來撥打 U.S. 號碼。 Fabrikam 也會想要設定系統，使來自美國 Lync Server 使用者的所有呼叫都使用德國的閘道，以德國的主幹和連續的國家/地區終止。 這種路由會省錢，因為從德國到奧地利的呼叫的費用低於從美國到奧地利的呼叫成本。

</div>

<div>

## <a name="translating-outbound-dial-strings"></a>轉換輸出撥號字串

Lync Server 2013 （如它的直屬前置任務）需要將所有撥號字串正常化為 e.164 格式，以執行反向號碼查閱 (RNL) 。 針對使用閘道或私人分支交換的主幹 (PBXs) 需要以本機撥號格式轉譯的數位，Lync Server 2013 可讓您建立一或多個規則，協助操縱所撥打的號碼 (例如，在將它路由傳送至主幹之前要求 URI) 。 例如，您可以撰寫規則，以從撥號字串的 head 移除 + 44，並以0144取代。

使用 Lync Server 2013，可以建立一或多個規則，協助您在將通話號碼路由傳送至主幹之前操縱通話號碼。

在規劃主幹以關聯閘道：埠組與轉送伺服器：埠組，使用類似的本機撥號需求群組主幹可能會非常實用，因此可減少所需的轉譯規則數量，以及寫入其所需的時間。

</div>

<div>

## <a name="configuring-caller-id"></a>設定來電者識別碼

Lync Server 提供一種方法，用來操縱撥出電話的來電者識別碼。 例如，如果組織想要掩蓋員工的直接撥號分機，並以一般公司或部門號碼取代它們，系統管理員可以使用 Lync Server 控制台來抑制來電者識別碼，並以指定的替代來電者識別碼取代它。 在規劃您的路由規則時，請考慮您要為其選擇此選項的個人、群組、網站（甚至是針對所有員工）。

<div>


> [!NOTE]  
> 如果是透過 PSTN 重新路由傳送的通話，將會呈現一般來電者識別碼，而不是原始的來電者識別碼。 這可能會導致來電繞過來電者可能已設定的 [打擾] 或 [隱私權] 設定。



</div>

</div>

<div>

## <a name="additional-routing-logic"></a>其他路由邏輯

在建立撥出電話路由時，您應該注意下列可能會影響路由邏輯的因素：

  - 在透過同盟界限建立通話的情況下，URI 的網域部分是用來將通話路由傳送到負責應用輸出路由邏輯的企業。

  - 如果要求 URI 的網域部分不包含企業所支援的網域，則伺服器上的輸出路由元件不會處理通話。

  - 如果使用者未啟用 Enterprise Voice，則伺服器會依照適當方式套用其他路由邏輯。

  - 如果呼叫路由傳送至已完全佔用的閘道 (所有的骨幹路都會忙碌) 中，閘道會拒絕通話，而輸出路由邏輯會將呼叫重新導向至下一個最低成本的路由。 請特別注意，由於小型辦公室海外的閘道大小 (例如，蘇黎世) 實際上可能會攜帶大量非使用中的流量，以供瑞士撥打國際電話。 如果此額外流量的閘道大小不正確，則通話的電話會透過德國的閘道來路由傳送，進而產生較大的計費。

</div>

</div>

<span> </span>

</div>

</div>

</div>

