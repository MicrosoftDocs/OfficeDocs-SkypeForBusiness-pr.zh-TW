---
title: Lync Server 2013： 語音路由
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
ms.openlocfilehash: 434f7cc92fd6a6bc284074cce476f4bc3b2eca01
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="voice-routes-in-lync-server-2013"></a>Lync Server 2013 中的語音路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-22_

電話路由指定 Lync Server 處理由 Enterprise Voice 使用者的撥出電話的方式。 當使用者撥號碼時，前端伺服器撥號對應表將字串標準化為 E.164 格式，如有必要，並嘗試將使其符合 SIP URI。 如果伺服器無法進行比對，它會套用撥出電話路由邏輯數為基礎。 定義該邏輯的最後一個步驟是建立個別的具名的呼叫路由目的地電話號碼中每個撥號對應表所列的每一組。

您定義撥出電話路由之前，您應該完成下列步驟：

  - 部署一或多個主幹。

  - 視需要針對網站、 個人和連絡人物件，請建立撥號對應表。

  - 建立公用交換的電話網路 (PSTN) 使用方式記錄。

此外，若要啟用撥出電話路由，您必須建立並指派一或多個語音原則。 之前或之後您定義撥出電話路由，您可以這麼做。

針對每個路徑，您必須指定：

  - 依據路由可以輕易識別名稱。

  - 在其中用名稱表達可能不足以描述該路由的情況下選用描述。

  - 規則運算式比對模式，以識別要路由套用，以及要比對的模式為不套用的例外狀況的目標電話號碼。

  - 您想要指派至路由的一或多個主幹。

  - 使用者必須要有為了撥打符合目標電話號碼 PSTN 使用方式記錄號碼規則運算式。

您可以在 Lync Server Control Panel 指定電話路由。 這些路由填入伺服器路由表，Lync Server 用以將通話路由傳送目的地為 PSTN 通話。

<div>

## <a name="mn-trunk-support"></a>M:N 主幹支援

Lync Server 提供彈性方式來電會路由傳送至 PSTN。 語音路由會指定一組可用於特定的語音通話 pstn 主幹。 主幹關聯至中繼伺服器及連接埠號碼的 PSTN 閘道及接聽連接埠號碼。 此邏輯關聯可讓多個閘道器相關聯並擁有多個連線到相同的閘道中繼伺服器。 定義通話路由傳送，當您指定該路由，相關聯的主幹，但未指定的中繼伺服器與路由相關聯的。 若要建立主幹藉由定義中繼伺服器和 PSTN 閘道、 IP Pbx 和工作階段邊界控制器 (Sbc) 之間的關係使用拓撲產生器]。

</div>

<div>

## <a name="least-cost-routing"></a>成本最低的路由

若要指定不同的數字會路由傳送主幹功能可讓您判斷哪些路由的最低成本可能會形成和據以實作它們。 中選取主幹的一般規則是為了減少長途電話選擇位置的目的號碼最接近的閘道主幹。 例如，如果您是在紐約並呼叫羅馬中的數字，您會延續通話的閘道主幹 IP 網路羅馬 office，因而產生僅適用於本機通話的費用。

如可能使用方式的最低成本路由的範例，請考慮下列： Fabrikam 決定，來啟用德文使用美國主幹撥打美國號碼給使用者。 Fabrikam 也想要設定系統，以便從美國 Lync Server 使用者對德國和相鄰的國家/地區的所有呼叫都終止上主幹，且在德國的閘道。 此路由會節省金錢，，因為奧地利，從 Germany 呼叫，例如美國奧地利呼叫成本低於。

</div>

<div>

## <a name="translating-outbound-dial-strings"></a>轉譯撥出撥號字串

Lync Server 2013 中，其立即的前置任務，像需要所有撥號對應表被正規化為 E.164 格式目的執行反向號碼查閱 (RNL) 的字串。 主幹與閘道或專用交換機 (Pbx) 需要本機撥號格式轉譯的數字，Lync Server 2013 可讓您建立一或多個規則，協助操作尚未所撥的號碼 (亦即要求 URI) 路由傳送至主幹。 例如，您可以撰寫 + 44 移除標頭的撥號對應表的字串，並取代為 0144年的規則。

搭配 Lync Server 2013，就可以建立一或多個規則，協助操作尚未路由傳送至主幹的來電號碼。

在規劃可與中繼伺服器： 連接埠 」 配對建立關聯閘道： 連接埠 」 配對，可能會很有用群組主幹類似區域撥號要求，從而減少必需的轉譯規則和撰寫它們所花費的時間的數目。

</div>

<div>

## <a name="configuring-caller-id"></a>設定來電者識別碼

Lync Server 提供方法來處理撥出電話的來電者識別碼。 例如，如果組織想要遮罩員工直接撥分機，並取代一般公司或部門的數字，系統管理員可以這麼做來隱藏來電者識別碼，並取代以使用 Lync Server Control Panel指定替代來電者識別碼。 在規劃您的路由邏輯，請考慮哪些個人、 群組、 您會想為此選項的網站，甚至，是為所有員工。

<div>


> [!NOTE]  
> 透過 PSTN 重新路由傳送的通話，一般的來電者識別碼將會出現而不是原始的來電者識別碼。 這可能會導致呼叫略過 [請勿打擾或隱私權受話者可能已經設定的設定。



</div>

</div>

<div>

## <a name="additional-routing-logic"></a>其他路由邏輯

在建立撥出電話路由時，您應該注意下列可能影響路由邏輯的因素：

  - 透過同盟界限建立通話後 URI 的網域部分用來透過將電話路由傳送到負責套用輸出路由邏輯的企業。

  - 如果要求 URI 的網域部分不包含企業支援的網域，在伺服器上的輸出路由元件不會處理通話。

  - 如果使用者未啟用 Enterprise voice，伺服器就會套用其他路由邏輯，視。

  - 如果來電會路由傳送至完全佔據閘道 （所有長途電話線都是忙碌中），閘道拒絕來電，並輸出路由邏輯會重新導向至下一步] 最低成本路由通話。 授與此仔細考量，因為調整大小的小型辦公室載運到海外 (例如，Zurich) 的閘道可能實際執行大量的錢瑞士國際呼叫流量。 如果閘道會不正確的此額外的流量調整大小，可能會被路由傳送呼叫瑞士透過閘道在德國，導致較大的費用。

</div>

</div>

<span> </span>

</div>

</div>

</div>

