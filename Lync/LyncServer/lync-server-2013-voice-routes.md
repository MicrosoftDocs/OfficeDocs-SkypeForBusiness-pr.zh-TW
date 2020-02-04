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
ms.openlocfilehash: 42aa810f40a6c00c7f2779acdf39caf39d7b2f07
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-routes-in-lync-server-2013"></a>Lync Server 2013 中的語音路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

[通話路線] 可指定 Lync Server 處理企業語音使用者所放的出站通話的方式。 當使用者撥打電話號碼時，前端伺服器會根據需要將撥號字串正常化為. 164 格式，並嘗試將它與 SIP URI 相符。 如果伺服器無法進行相符，就會根據數位來套用撥出電話路由邏輯。 定義該邏輯的最後一個步驟，就是針對每一組在每個撥號方案中列出的目的地電話號碼，建立單獨的命名呼叫路由。

在您定義出站呼叫路由前，您應該完成下列步驟：

  - 部署一個或多個 trunks。

  - 視需要為網站、個人和連絡人物件建立撥號方案。

  - 建立公用交換電話網絡（PSTN）使用方式記錄。

此外，若要啟用出站呼叫路由，您必須建立並指派一或多個語音原則。 您可以在定義出站通話路由之前或之後執行此動作。

針對每個路線，您必須指定：

  - 可輕鬆辨識路由的名稱。

  - 在名稱本身可能不足以描述路由的情況下，選用的描述。

  - 標識要套用路線之目的地電話號碼的正則運算式相符模式，以及不要套用相符模式的例外狀況。

  - 您想要指派給路線的一個或多個 trunks。

  - 使用者必須擁有的 PSTN 使用記錄，才能撥打符合目的地電話號碼正則運算式的號碼。

您可以在 Lync Server [控制台] 中指定呼叫路由。 這些呼叫路由會填入伺服器路由表，讓 Lync Server 用來傳送發往 PSTN 的呼叫。

<div>

## <a name="mn-trunk-support"></a>M:N 幹線支援

Lync Server 提供如何將呼叫路由至 PSTN 的靈活性。 語音路由指定 PSTN 的一組 trunks，可用於特定語音通話。 幹線會將中繼伺服器與埠號碼與 PSTN 閘道和偵聽埠號碼建立關聯。 這個邏輯關聯可讓中繼伺服器與多個閘道建立關聯，且有多個連線至同一個閘道。 定義通話路線時，您可以指定與該路線相關聯的 trunks，但不會指定哪些中繼伺服器與路由相關聯。 若要透過定義中繼伺服器與 PSTN 閘道、IP Pbx 及會話邊界控制器（SBCs）之間的關聯來建立 trunks，請使用 [拓撲產生器]。

</div>

<div>

## <a name="least-cost-routing"></a>最低成本的路由

您可以指定要傳送不同數位的 trunks，讓您能夠判斷哪些路線會產生最低的成本並據此進行執行。 選取 [trunks] 中的一般規則是，選擇最接近目的地編號位置的主幹，以將長途費用降至最低。 例如，如果您使用的是位於紐約，且是以羅馬的方式撥打數位，您就會在您的羅馬 office 中，將電話撥入到與閘道的主幹，因此只會在當地電話中承擔費用。

如需如何使用最低成本路由的範例，請考慮下列事項： Fabrikam 決定讓德文使用者使用美國主幹來撥打美制電話號碼。 Fabrikam 也想要設定系統，讓來自美國 Lync 伺服器使用者的所有呼叫在德國，以及在與在德國的閘道的主幹中連續的國家/地區。 這份工藝路線將節省金錢，因為從德國到奧地利的呼叫會比從美國至奧地利通話的費用低。

</div>

<div>

## <a name="translating-outbound-dial-strings"></a>翻譯出站撥號字串

Lync Server 2013 （例如其直屬前置任務）需要將所有撥號字串標準化為 E.i 格式，才能執行反向數位查閱（RNL）。 針對需要以本機撥號格式翻譯數位的閘道或私人分支交換（Pbx），Lync Server 2013 可讓您建立一或多個規則，協助您在將呼叫的號碼傳送到去. 例如，您可以撰寫規則，以從撥號字串的開頭移除 + 44，然後將它取代為0144。

有了 Lync Server 2013，就可以建立一或多個規則，協助您在將通話號碼傳送到主幹之前操作。

在規劃您的 trunks 中，將閘道與中繼伺服器：埠配對進行關聯，將 trunks 設定為類似的本機撥號需求，然後減少所需翻譯規則的數目，以及撰寫它們所需的時間。

</div>

<div>

## <a name="configuring-caller-id"></a>設定本機號碼

Lync Server 提供一種操作本機號碼撥出電話的方式。 例如，如果組織想要遮罩員工的直接撥號延伸，並以一般的公司或部門編號加以取代，系統管理員可以使用 Lync Server [控制台] 來取消本機號碼，並將它取代為指定的替換呼叫者 ID。 在規劃路由邏輯時，請考慮您想要此選項的人員、群組、網站（甚至對於所有員工而言，也是如此）。

<div>


> [!NOTE]  
> 對於在 PSTN 上重新路由的呼叫，將會出現一般本機號碼，而不是原始本機號碼。 這可能會導致呼叫避開受呼叫者所設定的 [請勿打擾] 或 [隱私權設定]。



</div>

</div>

<div>

## <a name="additional-routing-logic"></a>其他路由邏輯

在建立出站通話路線中，您應該注意到下列因素可能會影響路由邏輯：

  - 在聯盟邊界建立通話的位置，URI 的網域部分是用來將呼叫路由到負責套用輸出路由邏輯的企業。

  - 如果要求 URI 的網域部分不包含企業支援的網域，伺服器上的傳出路由元件不會處理通話。

  - 如果使用者未啟用企業語音，伺服器會視需要套用其他路由邏輯。

  - 如果通話路由至完全佔用的閘道（所有幹線線路都繁忙），閘道就會拒絕通話，而輸出路由邏輯則會將呼叫重新導向到下一個最低成本的路線。 請謹慎考慮，因為小型辦公室海外（例如，蘇黎世）的閘道可能會實際攜帶大量非使用中的通訊，以進行國際通話。 如果沒有針對此額外的流量正確地調整閘道大小，就可以透過德國的閘道來傳送對瑞士的呼叫，從而產生較大的付費費用。

</div>

</div>

<span> </span>

</div>

</div>

</div>

