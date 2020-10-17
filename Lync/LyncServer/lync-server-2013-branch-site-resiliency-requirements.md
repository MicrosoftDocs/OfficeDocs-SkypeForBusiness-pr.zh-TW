---
title: Lync Server 2013：分支網站恢復需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d76107fc419891561b8c98cf0989bbb0cbddbee4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504840"
---
# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a>Lync Server 2013 的分支網站恢復需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-25_

本主題將協助您為使用者準備分支網站恢復功能及語音信箱留存性，也會指定相關的硬體和軟體需求。

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a>準備分支使用者 Branch-Site 恢復功能

將其註冊機構集區設為 Survivable Branch 裝置 (SBA) 或 Survivable Branch Server），為使用者準備分支網站恢復功能。

<div>

## <a name="registrar-assignments-for-branch-users"></a>分支使用者的註冊機構指派

不論您選擇哪一個分支網站恢復解決方案，您都必須將主要註冊器指派給每個使用者。 分支網站使用者應始終向分支網站上的註冊機構註冊，不論該報名者是位於 Survivable Branch 裝置、Survivable Branch Server，還是獨立的 Lync Server 2013 Standard 或 Enterprise Edition server。 網域名稱系統 (DNS) 服務 (SRV) 資源記錄是必要的，讓用戶端能夠探索其註冊區集區。 如果 Survivable 分支裝置無法使用，這就是分支網站用戶端將如何自動探索備份註冊機。

如果分支網站沒有 DNS 伺服器，有兩種方法可用於設定 Survivable 分支裝置或 Survivable Branch 伺服器的探索：

  - 在分支網站的動態主機設定通訊協定上，設定 DHCP 選項120。 (DHCP) 伺服器指向 Survivable Branch 裝置或 Survivable Branch 伺服器的完整功能變數名稱 (FQDN) 。

  - 設定 Survivable 分支裝置或 Survivable 分支伺服器以回應 DHCP 120 查詢。

</div>

<div>

## <a name="voice-routing-for-branch-users"></a>分支使用者的語音路由

建議您建立個別的使用者層級語音 over 網際網路通訊協定 (VoIP 分支網站中使用者的) 原則。 這個原則應包含使用 Survivable Branch 裝置或 Branch server 閘道的主要路由，以及一個或多個在中央網站上使用具有公用電話 (交換網之公用電話) 閘道的主幹的備份路由。 如果主要路由無法使用，則改為使用使用一或多部中央網站閘道的備份路由。 這種方式不論登錄使用者的位置為何（位於中央網站的分支網站註冊機構或備份註冊機構集區），使用者的 VoIP 原則都是有效的。 這是容錯移轉案例的重要考慮。 例如，如果您需要重新命名 Survivable 分支裝置，或重新設定 Survivable Branch 裝置以連線至中央網站的備份註冊機構集區，則必須將分支網站使用者移至中央網站的持續時間。  (如需重新命名或重新配置 Survivable 分支裝置的詳細資訊，請參閱部署檔中的 [附錄 B：管理 Lync Server 2013 中的 Survivable Branch 裝置](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) 。 ) 如果這些使用者沒有使用者層級 VoIP 原則或使用者層級撥號對應表，當使用者移至另一個網站時，中心網站的網站層級 VoIP 原則和網站層級撥號對應表預設會套用至使用者，而不是分支網站網站層級 VoIP 原則及撥號對應表。 在此情況下，除非備份註冊機構集區所使用的網站層級 VoIP 原則和網站層級撥號對應表也可以套用至分支網站使用者，否則他們的呼叫將會失敗。 例如，如果位於日本的分支網站中的使用者已移至 Redmond 中的中央網站，則在其上預置 + 1425 至所有7位數通話的正規化規則的撥號對應表，將不會適當地為這些使用者轉譯來電。

<div>


> [!IMPORTANT]  
> 當您建立分支辦公室備份路由時，建議您將兩個 PSTN 電話使用方式記錄新增至分支 office 使用者原則，並將個別的路由指派給每個。 第一個或 [主要] 路由會直接呼叫與 Survivable Branch 裝置相關聯的閘道 (SBA) 或分支伺服器;第二個或 [備份] 路由會將呼叫直接呼叫至中央網站的閘道。 在接聽來電中，SBA 或 branch 伺服器會先嘗試所有指派給第一個 PSTN 使用方式記錄的路由，再嘗試第二個使用方式記錄。



</div>

若要協助確定分支網站使用者的來電網關或 Survivable 分支裝置網站的 Windows 元件無法使用時，是否會到達這些使用者， (會發生此情況。例如，如果 Survivable 分支裝置或分支閘道停機以進行維護) ，請在閘道上建立容錯移轉路由 (或使用直接向內撥號 (已) 提供者) 將來電重新導向至中央網站的備份註冊機構集區。 在此，來電會透過 WAN 連結路由傳送至分支使用者。 請確定路由會轉譯數位，使其符合 PSTN 閘道或其他主幹對等公認的電話號碼格式。 如需建立容錯移轉路由的詳細資訊，請參閱 [在 Lync Server 2013 中設定容錯移轉路由](lync-server-2013-configuring-a-failover-route.md)。 另外，也為分支網站上與閘道相關聯的主幹建立服務層級撥號對應表，以正常化來電。 如果您有兩個 Survivable 分支裝置在分支網站上，您可以為這兩種方案建立一個網站層級撥號對應表，除非每個必要都要有個別的服務層級計畫。

<div>


> [!NOTE]  
> 若要使用依賴中央網站以進行顯示狀態、會議或容錯移轉的任何分支網站使用者，針對中央網站資源的消費，建議您考慮每個分支網站使用者，就像使用者已向中央網站註冊。 分支網站使用者數目（包括註冊 Survivable Branch 裝置的使用者）目前沒有任何限制。



</div>

此外，我們也建議您建立使用者層級撥號對應表和語音原則，然後將其指派給分支網站使用者。 如需詳細資訊，請參閱部署檔中的在 lync server [2013 中建立撥號](lync-server-2013-create-a-dial-plan.md) 對應表，並在 [lync Server 2013 中建立分支使用者的 VoIP 路由原則](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) 。

<div>

## <a name="routing-extension-numbers"></a>路由分機號碼

為分支網站使用者準備撥號對應表和語音原則時，請務必包含符合 msRTCSIP-line (或 Line URI) 屬性中所用之字串及數位格式的正規化規則和轉譯規則，如此一來，在分支網站使用者與中央網站使用者之間啟用的 Lync 2013 通話才能正確路由傳送，尤其是當由於 WAN 連結無法使用時，必須以 PSTN 重新路由傳送。 此外，撥打號碼的特殊考慮（包括分機號碼），而不只是電話號碼。

包含分機號碼之行 URIs 的正規化規則和轉譯規則，不論是獨佔還是除了完整的 e.164 電話號碼，都有額外的需求。 本節說明使用分機號碼來路由傳送電話 URIs 的幾個範例案例。

如果您的組織沒有直接向內撥號 () 為個別使用者設定的電話號碼，且每位使用者的線路 URI *只* 會以分機號碼來設定，則內部使用者可以只撥打分機號碼撥打一個分機號碼。 不過，您必須設定標準化規則，以套用至分支網站使用者的呼叫與分機號碼相符的中央網站使用者。

在分支網站與中央網站之間的 WAN 連結可供使用的情況下，分支網站使用者對中央網站使用者的呼叫不需要符合的正規化規則來轉譯號碼，因為通話不會透過 PSTN 路由傳送。 例如：


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
<th>號碼模式</th>
<th>Translation</th>
<th>範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtensions</p></td>
<td><p>不轉譯5位數的數位</p></td>
<td><p>^ ( \d {5}) $</p></td>
<td><p>$1</p></td>
<td><p>未轉譯10001</p></td>
</tr>
</tbody>
</table>


您也必須在特定案例中容納分機號碼，例如在分支網站與中央網站之間的 WAN 連結無法使用，以及必須透過 PSTN 路由傳送分支網站的電話時。 在 WAN 中斷期間，如果分支網站使用者只會撥打中央網站使用者的分機呼叫中央網站使用者，您必須有一個輸出轉譯規則，以加入中央網站使用者的完整電話號碼。 如果使用者的列 URI 包含您組織的完整電話號碼和使用者的唯一分機號碼，而不是使用者特有的完整電話號碼，則您必須有一個輸出轉譯規則，可改為新增組織的完整電話號碼。 例如：


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
<th>符合模式</th>
<th>Translation</th>
<th>範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>將5位數號碼轉譯為使用者的電話號碼和分機號碼</p></td>
<td><p>^ ( \d {5}) $</p></td>
<td><p>+ 14255550123; ext = $ 1</p></td>
<td><p>10001會轉譯為 + 14255550123; ext = 10001</p></td>
</tr>
<tr class="even">
<td><p>將5位數號碼轉譯為您組織的電話號碼和使用者的分機號碼</p></td>
<td><p>^ ( \d {5}) $</p></td>
<td><p>+ 14255550100; ext = $ 1</p></td>
<td><p>10001會轉譯為 + 14255550100; ext = 10001</p></td>
</tr>
</tbody>
</table>


在此案例中，如果處理與 PSTN 間重新路由的主幹對等動作不支援分機號碼，則輸出轉譯規則也必須移除分機號碼。 例如：


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
<th>符合模式</th>
<th>Translation</th>
<th>範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>從具有分機號碼的電話號碼中移除分機號碼</p></td>
<td><p>^\+ ( \d *) ; ext = ( \d*) $</p></td>
<td><p>+ $1</p></td>
<td><p>+ 14255550123; ext = 10001 會轉譯成 + 14255550123</p></td>
</tr>
</tbody>
</table>


WAN 連結是否可供使用時，如果您的組織未針對個別使用者設定號碼，且使用者的線路 URI 中包含組織的電話號碼和使用者的唯一分機號碼，則您必須使用分支網站上的主幹對等或 PSTN 閘道可存取的號碼，設定組織的電話號碼行 URI。 您也必須設定組織的電話號碼行 URI，以包含其專屬的唯一分機，以路由傳送至該號碼。

如需網站間的 WAN 連結無法使用時，從中央網站使用者呼叫至分支網站使用者的詳細資訊，請參閱本主題稍後的「準備語音信箱留存功能」。 如需撥號對應表及正規化規則（包括其他範例規則）的詳細資訊，請參閱部署檔中的規劃檔及設定[Lync server 2013](lync-server-2013-configuring-dial-plans.md)中的撥號對應表中的撥號對應表[和正常化2013規則](lync-server-2013-dial-plans-and-normalization-rules.md)。 如需輸出轉譯規則的詳細資訊，請參閱部署檔中的規劃檔及[定義轉譯2013規則](lync-server-2013-defining-translation-rules.md)中的 lync server 2013 中的[轉譯規則](lync-server-2013-translation-rules.md)。

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a>準備語音信箱留存能力

Exchange 整合通訊 (UM) 通常只安裝在中央網站，而非位於分支網站。 即使分支網站與中央網站之間的 WAN 連結無法使用，來電者還是可以留下語音信箱訊息。 因此，設定 Exchange UM 自動語音應答電話號碼（為分支網站使用者提供語音信箱）的行 URI 時，除了語音原則、撥號對應表，以及適用于該語音信箱號碼的正規化規則之外，還需要特別考慮。

Survivable 分支裝置 (Sba) 和 Survivable 分支伺服器在 WAN 中斷期間為分支使用者提供語音信箱留存能力。 具體說來，如果您是使用 Survivable 分支裝置或 Survivable 分支伺服器，而 WAN 變成無法使用，則 SBA 或 Survivable Branch 伺服器會透過 PSTN 將未接聽的電話重新連接到中央網站的 Exchange UM。 透過 SBA 或 Survivable Branch 伺服器，使用者也可以透過 PSTN 在 WAN 中斷期間取回語音信箱訊息。 最後，在 WAN 中斷期間，Survivable Branch 裝置或 Survivable Branch 伺服器會將未接來電通知排入佇列，然後在 WAN 還原時，將其上傳至 Exchange UM 伺服器。 若要協助確保語音信箱重新路由可復原，請確定您已將中央網站集區的 FQDN 和 Edge Server FQDN 專案的專案新增至 Survivable 分支伺服器上的主機檔案。 否則，如果您在分支網站上沒有 DNS 伺服器，則 DNS 解析可能會超時。

我們建議分支網站使用者的語音信箱留存能力的下列設定：

  - Microsoft Exchange 管理員應該設定 Exchange UM 自動語音應答 (AA) 只接受郵件。 此設定會停用所有其他一般功能，例如轉接至使用者或轉接至操作員，並且限制 AA 只接受郵件。 此外，Exchange 系統管理員可以使用一般 AA 或自訂的 AA，將通話路由傳送至操作員。

  - Lync Server 管理員應該取得 AA 電話號碼，並使用該電話號碼做為 Survivable 分支裝置或分支伺服器之語音信箱重新路由設定中的 **exchange um 自動** 語音應答編號。

  - Lync Server 系統管理員應取得 Exchange UM 訂戶存取電話號碼，並使用該號碼做為 Survivable Branch 裝置或 Survivable Branch 伺服器之語音信箱重新路由設定中的 **訂戶訪問** 號碼。

  - Lync Server 管理員應該設定 Exchange UM，以便在 WAN 中斷期間，只有一個撥號對應表與需要存取語音信箱的所有分支使用者相關聯。

  - 當 WAN 連結無法使用時，可將分支網站使用者的通話路由傳送至使用者的 Exchange 整合通訊 (UM) 語音信箱，但只有在套用至通話的語音原則指定了唯一且不含分機號碼的語音信箱電話號碼時。

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Branch-Site 恢復功能的硬體和軟體需求

硬體和軟體需求會根據您的恢復解決方案而有所不同。

<div>

## <a name="requirements-for-survivable-branch-appliances"></a>Survivable 分支裝置的需求

必要的硬體和軟體已內置於 Survivable 分支裝置中。 不過，我們也建議每個分支網站部署 DHCP 伺服器以取得用戶端 IP 位址;否則，當 DHCP 租用到期時，用戶端將不會有 IP 連線能力。

如果企業 DNS 伺服器僅位於中央網站，分支網站使用者將無法在 WAN 中斷期間與其連線，因此使用 DNS SRV (服務 (SRV) 資源記錄) 的 Lync Server 探索會失敗。 為了確保 WAN 中斷期間的提示重新路由，必須在分支網站上快取 DNS 記錄。 如果分支路由器支援，請開啟 DNS 快取。 或者，您可以在分支部署 DNS 伺服器。 這可以是獨立的伺服器，也可以是支援 DNS 功能的 Survivable 分支裝置版本。 如需詳細資訊，請與您的 Survivable 分支裝置提供者聯繫。

<div>


> [!NOTE]  
> 不需要有分支網站的網域控制站。 Survivable 分支裝置會使用特殊的憑證來驗證用戶端，以回應用戶端的憑證要求登入。



</div>

Lync 用戶端可以使用 DHCP 選項 120 (SIP 註冊器選項) 探索 Lync Server。 這可以採用下列其中一種方式進行設定：

  - 在分支網站上設定 DHCP 伺服器以回復 DHCP 120 查詢，傳回 Survivable Branch 裝置或 Survivable Branch Server 上之註冊機的 FQDN。

  - 開啟 Lync Server DHCP。 當此功能開啟時，Lync Server 註冊機構會回應 DHCP 選項120查詢。 請注意，註冊機構不會回應 DHCP 選項120以外的任何 DHCP 查詢。

此外，針對具有多個子網的大型分支網站，應啟用 DHCP 轉送代理程式，以將 DHCP 選項120查詢轉寄至 DHCP 伺服器 (設定 1) 或註冊機 (設定 2) 。

最後，分支網站使用者必須針對 Enterprise Voice 進行設定，並使用適當的整合通訊端點進行布建。

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a>Survivable 分支伺服器的需求

Survivable 分支伺服器的需求與前端伺服器的需求相同。 如需詳細資訊，請參閱規劃檔中的 [Lync server 2013 伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md) 。

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a>Full-Scale Lync Server Branch-Site 部署的需求

如需詳細資訊，請參閱規劃檔中的 [判斷您的 Lync Server 2013 基礎結構需求](lync-server-2013-determining-your-infrastructure-requirements.md) 。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

