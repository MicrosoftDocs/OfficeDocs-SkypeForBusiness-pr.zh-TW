---
title: Lync Server 2013：通話許可控制的概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of call admission control
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48184474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df9d65a56a8e2ed398dc5277045efeaaf68b8f58
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 中的通話許可控制概覽

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-22_

即時通訊最在意壅塞網路上可能發生的延遲和封包遺失。 通話許可控制服務 (CAC) 會根據可用的網路頻寬，判斷是否允許建立即時通訊工作階段 (如語音或視訊通話)。 Lync Server 2013 中的 CAC 設計提供四個主要屬性：

  - 部署及管理簡單，並不需要其他設備 (如特別設定的路由器)。

  - 解決重要整合通訊使用案例 (如漫遊使用者及多點出席)。根據端點所在位置，而非使用者所在位置，來強制執行 CAC 原則。

  - 除了語音電話之外，這也適用於其他流量 (如視訊通話及音訊/視訊會議工作階段)。

  - 提供啟用呈現各種網路拓撲的彈性。 如需有關範例，請參閱[Lync Server 2013 中的 CAC 的元件與拓撲](lync-server-2013-components-and-topologies-for-cac.md)。

如果新的語音或視訊工作階段超出針對 WAN 連結所設定的頻寬限制，則會封鎖工作階段，或將它重新路由傳送至 PSTN (僅限電話)。

CAC 僅控制語音及視訊的即時流量。並不控制資料流量。

管理員會定義 CAC 原則，這些原則是由隨每個前端集區一起安裝的頻寬原則服務所強制執行。 CAC 設定會自動傳播至您網路中的所有 Lync Server 前端伺服器。

針對因 CAC 原則而失敗的通話，重新路由傳送通話的優先順序如下：

1.  網際網路

2.  Pstn

3.  語音信箱

詳細通話記錄 (CDR) 可擷取重新路由傳送至 PSTN 或語音信箱之通話的資訊。CDR 不會擷取重新路由傳送至網際網路之通話的資訊，因為網際網路是視為替代路徑，而非次要選項。

<div>


> [!NOTE]  
> 因為頻寬條件約束，所以不會拒絕語音信箱儲放。



</div>

頻寬原則服務會產生兩種類型的記錄檔，其格式為逗點分隔值 (CSV)。**check failures** 記錄檔會擷取拒絕頻寬要求時的資訊。**link utilization** 記錄檔會擷取網路拓撲及 WAN 連結頻寬使用的快照集。這兩種記錄檔可以協助您根據使用率來微調 CAC 原則。

<div>

## <a name="call-admission-control-considerations"></a>通話許可控制考量

系統管理員可選取在設定於中央網站的第一個集區來安裝頻寬原則服務。 由於每個網路地區只有單一中央網站，所以每個網路地區僅有一項頻寬原則服務，負責管理該區域的頻寬原則和其相關聯的網站以及與這些網站的連結。 頻寬原則服務會作為前端伺服器的一部分來執行，因此在該集區中內建高可用性。 在每一部前端伺服器上執行的頻寬原則服務會每隔15秒同步處理。 如果前端集區失敗，則不會再對該網站執行 CAC 原則，直到前端集區，因此頻寬原則服務也會再次運作。 這表示在頻寬原則服務停止運作期間，所有通話將會通過。 因此在這段期間，您的連結可能會發生頻寬超額的情況

頻寬原則服務可提供前端集區中的高可用性;不過，它不提供跨前端集區的冗余。 頻寬原則服務無法從一個前端集區容錯移轉至另一個前端集區。 在還原前端集區的服務後，會繼續執行頻寬原則服務，並可重新執行頻寬原則檢查。

<div>

## <a name="network-considerations"></a>網路考量

雖然 Lync Server 2013 中的頻寬原則服務會強制執行音訊和影片的頻寬限制，但此限制不會在網路路由器上強制執行 (layer 2 和 3) 。 Lync Server 2010 CAC 無法防止資料應用程式，例如，在 WAN 連結上消耗整個網路頻寬，包括您的 CAC 原則為音訊和影片保留的頻寬。 若要在網路上保護必要的頻寬，您可以將服務品質 (QoS) 通訊協定（如差異服務 (DiffServ) ）。 因此，最佳作法是將您定義的 CAC 頻寬原則與您可能部署的任何 QoS 設定進行協調。

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a>透過 VPN 的媒體及訊號路徑

如果您的企業支援透過 VPN 的媒體，請確定媒體串流及訊號串流通過 VPN，或是兩者都是透過網際網路進行路由傳送。媒體及訊號串流預設會通過 VPN 通道。

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a>外部使用者的通話許可控制

針對網路流量流過網際網路的遠端使用者，不會強制執行通話許可控制服務。 因為媒體流量是透過網際網路進行，而不是由 Lync Server 管理，所以無法套用 CAC。 不過，會針對流過企業網路的通話部分執行 CAC 檢查。

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a>PSTN 連線的通話許可控制

「通話許可控制」會在轉送伺服器上強制實施，不論它是連接至 IP/PBX、PSTN 閘道或 SIP 主幹。 由於轉送伺服器是 back to back user agent (B2BUA) ，因此會終止媒體。 有兩個連線方：一種連接至 Lync Server 的一面，以及連接到 PSTN 閘道、IP/PBXs 或 SIP 主幹的閘道端。 如需 PSTN 連線的詳細資訊，請參閱[在 Lync Server 2013 中規劃 PSTN](lync-server-2013-planning-for-pstn-connectivity.md)連線。

除非啟用媒體旁路，否則可在轉送伺服器的兩側強制 CAC。 如果啟用媒體旁路，媒體流量不會遍歷轉送伺服器，而是直接在 Lync 用戶端和閘道之間流動。 在此情況下，不需要 CAC。 如需詳細資訊，請參閱[在 Lync Server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)。

下圖說明如何在啟用或未啟用媒體旁路的情況下於 PSTN 連線上強制執行 CAC。

**PSTN 連線的通話許可控制強制執行**

![語音 CAC 媒體旁路連接強制](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "語音 CAC 媒體旁路連接強制")

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a>通話許可控制與舊版 Office Communications Server 的相容性

只能在啟用 Lync Server 2010 和更新版本的端點上啟用通話許可控制。

無法在執行 Office Communicator 2007 R2 或更早版本的端點上啟用通話許可控制。

**不同 Lync Server 版本上的 CAC 應用**

![語音 CAC 版本比較圖表](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "語音 CAC 版本比較圖表")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

