---
title: Lync Server 2013：分支網站復原需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ff969638f8c46abdd0ebcc8d11821a6a31b3c76
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a>Lync Server 2013 的分支網站復原需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-25_

本主題將協助您準備使用者以進行分支網站復原及語音信箱留存，同時也會指定相關的硬體和軟體需求。

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a>準備分支使用者以進行分支網站復原

將自己的註冊機構池設定為 Survivable 分支機搆（SBA）或 Survivable 分支伺服器，以準備使用者以進行分支網站復原。

<div>

## <a name="registrar-assignments-for-branch-users"></a>分支使用者的註冊機構指派

不論您選擇哪一個分支網站復原解決方案，您都必須將主要註冊機構指派給每個使用者。 分支網站使用者無論是在 Survivable 分支裝置、Survivable 分支伺服器或獨立的 Lync Server 2013 標準版或 Enterprise Edition 伺服器中，都必須在分支網站上註冊註冊機構。 必須具備網域名稱系統（DNS）服務（SRV）資源記錄，才能讓用戶端探索其註冊機構池。 如果 Survivable 分支裝置無法使用，這就是分支網站用戶端將如何自動探索備份註冊機構。

如果分支網站沒有 DNS 伺服器，有兩種方法可讓您設定發現 Survivable 分支裝置或 Survivable 分支伺服器的兩種方式：

  - 在分支網站的動態主機設定通訊協定（DHCP）伺服器上，設定 DHCP 選項120，以指向 Survivable 分支裝置或 Survivable 分支伺服器的完整功能變數名稱（FQDN）。

  - 將 Survivable 分支裝置或 Survivable 分支伺服器設定為回應 DHCP 120 查詢。

</div>

<div>

## <a name="voice-routing-for-branch-users"></a>分支使用者的語音路由

我們建議您針對分支網站中的使用者，建立個別的使用者層級語音透過網際網路通訊協定（VoIP）原則。 此原則應該包含使用 Survivable 分支裝置或分支伺服器閘道的主要路由，以及使用主幹與中央網站上的公用交換電話網絡（PSTN）閘道的一或多個備份路由。 如果主要路線無法使用，則會改用使用一或多個中央網站閘道的備份路由。 如此一來，不論使用者的登錄位置為何（在分支網站註冊機構或中央網站的 [備份註冊機構] 池中），使用者的 VoIP 原則都將會生效。 在容錯移轉案例中，這是一個重要的考慮。 例如，如果您需要重新命名 Survivable 分支裝置，或重新設定 Survivable 分支裝置以連線到中央網站上的備份註冊機構池，則您必須將分支網站使用者移至中心網站中的持續時間。 （如需重新命名或重新配置 Survivable 分支裝置的詳細資料，請參閱附錄 B：在部署檔中的[Lync Server 2013 中管理 Survivable 分支裝置](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md)。）如果這些使用者沒有使用者層級 VoIP 原則或使用者層級的撥號方案，當使用者移至另一個網站時，中心網站的網站層級 VoIP 原則和網站層級撥號方案預設會套用至使用者，而不是分支網站網站層級 VoIP 原則和撥號方案。 在這種情況下，除非 [備份註冊器] 池所使用的網站層級 VoIP 原則和網站層級撥號方案也會套用至分支網站使用者，否則他們的呼叫將會失敗。 例如，如果將位於日本的分支網站的使用者移至雷蒙德中的中央網站，則會將適用于所有7位數通話的正常化規則（含1425此標準），不可能針對這些使用者適當地翻譯通話。

<div>


> [!IMPORTANT]  
> 當您建立分支辦公室備份路線時，建議您將兩個 PSTN 手機使用量記錄新增至分支機搆使用者原則，並將不同的路由指派給每一個。 第一個或 [主要] 路由會直接呼叫與 Survivable 分支裝置（SBA）或分支伺服器關聯的閘道;第二個或 [備份] 路由會直接呼叫中央網站上的閘道。 在定向呼叫中，SBA 或分支伺服器會在嘗試第二筆使用記錄之前，先嘗試指派給第一個 PSTN 使用狀況記錄的所有路由。



</div>

若要確保當分支機搆或 Survivable 分支裝置網站的 Windows 元件無法使用（例如，如果 Survivable 分支裝置或分支）時，對分支網站使用者的撥入呼叫將會達到這些使用者的要求（例如，可能會發生這種情況）。閘道已關閉維護），請在閘道建立容錯移轉路由（或使用您的直接向內撥號（已執行）提供者），將來電重新導向到中央網站上的備份註冊機構池。 從這裡開始，通話會透過 WAN 連結路由至分支使用者。 請確定路由會將數位轉換成符合 PSTN 閘道或其他中繼對等的已接受電話號碼格式。 如需建立容錯移轉路由的詳細資料，請參閱[在 Lync Server 2013 中設定容錯移轉路由](lync-server-2013-configuring-a-failover-route.md)。 同時為與分支網站上的閘道相關聯的主幹建立服務層級撥號方案，以正常化來電。 如果您在分支網站上有兩個 Survivable 分支裝置，您可以為這兩者建立一個網站層級撥號方案，除非有任何需要的不同服務層級方案。

<div>


> [!NOTE]  
> 若要考慮由任何分支網站使用者使用中心網站資源來進行目前狀態、會議或容錯移轉，我們建議您考慮每個分支網站使用者，就像該使用者已在中央網站註冊一樣。 分支網站使用者的數目目前沒有限制，包括向 Survivable 分支裝置註冊的使用者。



</div>

我們也建議您建立使用者層級撥號方案和語音原則，然後將它指派給分支網站使用者。 如需詳細資訊，請參閱[在 Lync server 2013 中建立撥號方案](lync-server-2013-create-a-dial-plan.md)，並在部署檔中[為 Lync server 2013 中的分支使用者建立 VoIP 路由策略](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md)。

<div>

## <a name="routing-extension-numbers"></a>路由分機號碼

當您為分支網站使用者準備撥號方案和語音原則時，請務必包含符合在 msRTCSIP 行（或 Line URI）屬性中使用之字串和數位格式的正常化規則和翻譯規則，以便在分支之間啟用 Lync 2013 通話網站使用者和中央網站使用者將會正確路由，特別是在由於 WAN 連結無法使用時，必須將呼叫重新路由到 PSTN。 此外，撥打號碼時也有特殊考慮，包括分機號碼，而不只是電話號碼。

正常化規則與包含副檔名的行 Uri 相符，不論是獨佔或除了完整的 E. 164 電話號碼，還有其他需求。 本節將說明幾個範例案例，以使用分機號碼來路由行 Uri 通話。

如果您的組織沒有為個別使用者設定直接撥出電話號碼，且每個使用者的 Line URI 都*只*使用分機號碼進行設定，則內部使用者可以撥打電話給對方，只撥打分機號碼。 不過，您必須設定正常化規則，才能套用到分支網站使用者的呼叫與分機號碼相符的中心網站使用者。

在分支網站與中央網站之間提供 WAN 連結的情況下，分支網站使用者對中央網站使用者的呼叫不需要搭配的正常化規則來轉譯數位，因為通話不是透過 PSTN 路由。 例如：


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>規則名稱</th>
<th>描述</th>
<th>數位模式</th>
<th>翻譯</th>
<th>範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtensions</p></td>
<td><p>不會轉譯5位數的數位</p></td>
<td><p>^ （\d{5}） $</p></td>
<td><p>$1</p></td>
<td><p>未翻譯10001</p></td>
</tr>
</tbody>
</table>


您也必須針對特定案例（例如當分支網站與中央網站之間的 WAN 連結無法使用，且必須透過 PSTN 路由來自分支網站的呼叫），才能容納延伸號碼。 在 WAN 中斷期間，如果分支網站使用者只是透過撥入中央網站使用者的副檔名話務中心網站使用者，您必須有一個加入中心網站使用者的完整電話號碼的輸出轉換規則。 如果使用者的行 URI 包含貴組織的完整電話號碼和使用者的唯一分機號碼，而不是使用者唯一的電話號碼，則您必須有一個輸出翻譯規則，以將貴組織的完整電話號碼改為. 例如：


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>描述</th>
<th>相符的模式</th>
<th>翻譯</th>
<th>範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>將5位數的數位轉換為使用者的電話號碼和分機</p></td>
<td><p>^ （\d{5}） $</p></td>
<td><p>+ 14255550123; ext = $ 1</p></td>
<td><p>10001已轉譯為 + 14255550123; ext = 10001</p></td>
</tr>
<tr class="even">
<td><p>將5位數的數位轉換為貴組織的電話號碼和使用者的分機</p></td>
<td><p>^ （\d{5}） $</p></td>
<td><p>+ 14255550100; ext = $ 1</p></td>
<td><p>10001已轉譯為 + 14255550100; ext = 10001</p></td>
</tr>
</tbody>
</table>


在這種情況下，如果處理對 PSTN 重新路由的幹線對等，不支援分機號碼，則輸出轉換規則也必須移除延伸號碼。 例如：


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>描述</th>
<th>相符的模式</th>
<th>翻譯</th>
<th>範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>從電話號碼中移除副檔名</p></td>
<td><p>^\+（\d *）; ext = （\d*） $</p></td>
<td><p>+ $1</p></td>
<td><p>+ 14255550123; ext = 10001 已轉譯為 + 14255550123</p></td>
</tr>
</tbody>
</table>


無論是否有提供 WAN 連結，如果您的組織沒有為個別使用者設定號碼，且使用者的行 URI 包含貴組織的電話號碼和使用者的唯一分機號碼，則您必須設定組織的電話號碼行 URI，且分支網站上的幹線對等或 PSTN 閘道可達到該號碼。 您也必須設定貴組織的電話號碼行 URI，以包含自己的唯一分機，讓呼叫路由到該號碼。

如需網站之間的 WAN 連結無法使用，請參閱本主題稍後的「準備語音信箱的準備工作] 使用者。 如需撥號方案和正常化規則的詳細資料（包括其他範例規則），請參閱在 lync server 2013 中的[撥號方案和正常化規則](lync-server-2013-dial-plans-and-normalization-rules.md)，並在 [部署] 檔中的 [ [lync server 2013](lync-server-2013-configuring-dial-plans.md) ] 中設定撥號方案。 如需輸出轉換規則的詳細資料，請參閱在 lync server 2013 中的 [[翻譯] 規則](lync-server-2013-translation-rules.md)，並在 [部署] 檔中的 [ [lync server 2013] 中定義翻譯規則](lync-server-2013-defining-translation-rules.md)。

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a>準備語音信箱的留存能力

Exchange 整合通訊（UM）通常只會安裝在中央網站，而不是分支網站上。 即使分支網站與中央網站之間的 WAN 連結無法使用，來電者仍能留下語音信箱訊息。 因此，針對為分支網站使用者提供語音信箱的 Exchange UM 自動語音應答電話號碼設定行 URI，除了語音原則、撥號方案，以及適用于該語音信箱的正常化規則以外，還需要考慮的事項。電話.

Survivable 分支裝置（SBAs）和 Survivable 分支伺服器會在 WAN 停機期間為分支使用者提供語音信箱留存。 特別是，如果您使用的是 Survivable 分支裝置或 Survivable 分支伺服器，且 WAN 無法使用，則 SBA 或 Survivable 分支伺服器會在中央網站將未接聽的電話重新連接到 Exchange UM。 在 SBA 或 Survivable 分支伺服器中，使用者也可以在 WAN 中斷期間透過 PSTN 檢索語音信箱訊息。 最後，在 WAN 中斷期間，Survivable 分支裝置或 Survivable 分支伺服器會列隊未接來電通知，然後在 WAN 還原時，將其上傳到 Exchange UM 伺服器。 若要確保語音信箱重新路由有復原能力，請務必將中央網站池的 FQDN 和 Edge 伺服器 FQDN 的專案新增至 Survivable 分支伺服器上的 hosts 檔案。 否則，如果您在分支網站上沒有 DNS 伺服器，則 DNS 解析可能會超時。

我們建議針對分支網站使用者的語音信箱留存功能進行下列設定：

  - Microsoft Exchange 管理員應該將 Exchange UM 自動語音應答（AA）設定為僅接受郵件。 這個設定會停用所有其他的一般功能，例如轉接給使用者或傳送到操作員，並限制 AA 只接受訊息。 或者，Exchange 管理員可以使用一般 AA 或自訂的 AA，將呼叫路由至接線員。

  - Lync Server 管理員應採用 AA 電話號碼，並使用該電話號碼作為 Survivable 分支裝置或分支伺服器的語音信箱重新路由設定中的**exchange um 自動**語音應答號碼。

  - Lync Server 管理員應該取得 Exchange UM 訂閱者存取電話號碼，並在 Survivable 分支裝置或 Survivable 分支伺服器的語音信箱重新路由設定中，使用該號碼作為**訂閱者存取**號碼。

  - Lync Server 管理員應該設定 Exchange UM，以便在 WAN 停機期間，只有一個撥號方案會與需要存取語音信箱的所有分支使用者產生關聯。

  - 當 WAN 連結無法使用時，分支網站使用者的呼叫可以傳送到使用者的 Exchange 整合通訊（UM）語音信箱，但只有當套用到通話的語音原則指定了唯一且不含延伸的語音信箱電話號碼時電話.

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>分支網站復原的硬體和軟體需求

硬體和軟體需求會根據您的復原方案而有所不同。

<div>

## <a name="requirements-for-survivable-branch-appliances"></a>Survivable 分支裝置的需求

Survivable 分支裝置內建了必要的硬體和軟體。 不過，我們也建議每個分支網站都要部署 DHCP 伺服器來取得用戶端 IP 位址;否則，當 DHCP 租約到期時，用戶端將沒有 IP 連線能力。

如果企業 DNS 伺服器只位於中央網站，分支網站使用者將無法在 WAN 中斷期間連線至這些使用者，因此使用 DNS SRV （服務（SRV）資源記錄）的 Lync Server 探索將會失敗。 為了確保 WAN 停機期間的提示重新路由，DNS 記錄必須在分支網站上緩存。 如果分支路由器支援它，請開啟 DNS 快取。 或者，您可以在分支部署 DNS 伺服器。 這可以是獨立伺服器或支援 DNS 功能的 Survivable 分支裝置版本。 如需詳細資訊，請與您的 Survivable 分支裝置提供者聯繫。

<div>


> [!NOTE]  
> 在分支網站上不需要有網網域控制站。 Survivable 分支裝置會使用特殊憑證來驗證用戶端，讓用戶端在登入時回應用戶端的憑證要求。



</div>

Lync 用戶端可以使用 DHCP 選項120（SIP 註冊器選項）來探索 Lync 伺服器。 這可以使用下列兩種方法的其中一種來設定：

  - 在分支網站設定 DHCP 伺服器，以回復 DHCP 120 查詢，這會傳回 Survivable 分支裝置或 Survivable 分支伺服器上的註冊機 FQDN。

  - 開啟 Lync Server DHCP。 開啟此功能時，Lync Server 註冊機構會回應 DHCP 選項120查詢。 請注意，註冊機構不會回應 DHCP 選項120以外的任何 DHCP 查詢。

此外，對於有多個子網的大型分支網站，必須啟用 DHCP 中繼代理程式，才能將 DHCP 選項120查詢轉寄至 DHCP 伺服器（設定1）或註冊機（配置2）。

最後，分支網站使用者必須針對企業語音進行設定，並使用適當的整合通訊端點進行設定。

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a>Survivable 分支伺服器的需求

Survivable 分支伺服器的需求與前端伺服器的需求相同。 如需詳細資訊，請參閱規劃檔中的[Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)。

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a>全式 Lync Server 分支網站部署的需求

如需詳細資訊，請參閱在規劃檔中[判斷 Lync Server 2013 的基礎結構需求](lync-server-2013-determining-your-infrastructure-requirements.md)。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

