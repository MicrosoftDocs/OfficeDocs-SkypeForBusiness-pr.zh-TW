---
title: Lync Server 2013：通話許可控制的概覽
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of call admission control
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48184474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cba1a83ce64fa575cf5de724d5dd215fcb459c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 中的通話許可控制概覽

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-22_

即時通訊對可能會在擁擠網路上發生的延遲與資料包遺失敏感。 [通話許可控制] （CAC）會根據可用的網路頻寬決定是否允許建立即時通訊會話，例如語音或視頻通話。 Lync Server 2013 中的 CAC 設計提供了四個主要屬性：

  - 您可以輕鬆地部署和管理，不需要額外的裝置，例如特殊設定的路由器。

  - 它解決了重要的整合通訊使用案例，例如漫遊使用者和多個目前狀態點。 系統會根據端點所在的位置強制執行 CAC 原則，而不是使用者的駐留位置。

  - 除了語音通話之外，也可以將它套用到其他流量，例如視頻通話和音訊/視訊會議會話。

  - 提供靈活的方式來啟用各種類型的網路拓撲。 如需範例，請參閱[Lync Server 2013 中的 CAC 元件與拓撲](lync-server-2013-components-and-topologies-for-cac.md)。

如果新的語音或視頻會話超過您在 WAN 連結上設定的頻寬限制，該會話會被封鎖，或（僅限電話撥打電話）重新路由至 PSTN。

CAC 只會控制語音和影片的即時流量。 它不會控制資料流量。

系統管理員會定義 CAC 原則，這些原則是由每個前端池所安裝的頻寬原則服務所強制執行。 CAC 設定會自動傳播至您網路中的所有 Lync Server 前端伺服器。

針對由於 CAC 原則而失敗的呼叫，請依照下列步驟重新路由呼叫的優先順序順序如下：

1.  互聯

2.  PSTN

3.  語音信箱

通話詳細資料錄製（CDR）可捕獲重新路由至 PSTN 或語音信箱之通話的相關資訊。 CDR 不會捕獲重新路由至網際網路之通話的相關資訊，因為網際網路被視為替換路徑，而不是次要選項。

<div>


> [!NOTE]  
> 由於頻寬限制，語音信箱的存款不會遭到拒絕。



</div>

頻寬原則服務會以逗號分隔值（CSV）格式產生兩種類型的記錄檔。 當頻寬要求遭到拒絕時，**檢查失敗**記錄檔案會捕獲資訊。 **連結利用率**記錄檔案會捕獲網路拓撲及 WAN 連結頻寬利用率的快照。 這兩個記錄檔都能根據利用率，協助您微調您的 CAC 原則。

<div>

## <a name="call-admission-control-considerations"></a>通話許可控制考慮

系統管理員選取將頻寬原則服務安裝在中央網站中設定的第一個池上。 由於每個網路區域都有一個中心網站，每個網路區域只有一個頻寬原則服務，可管理該區域的頻寬原則、其關聯的網站，以及這些網站的連結。 頻寬原則服務是作為前端伺服器的一部分執行，因此在該池中內建了高可用性。 每個前端伺服器上執行的頻寬原則服務會每隔15秒進行一次同步處理。 如果前端池失敗，則不會再針對該網站強制執行 CAC 原則，除非是前端池為止，因而頻寬原則服務再次成為正常運作。 這表示所有的呼叫都會在頻寬原則服務不在服務期間完成。 因此，您在此期間可能會有頻寬過度訂閱給您的連結

頻寬原則服務可在前端池中提供高可用性;不過，它不會提供跨前端池的冗余。 頻寬原則服務無法從一個前端池轉移到另一個。 一旦已還原對前端池的服務之後，就會繼續執行頻寬原則服務，並再次強制執行頻寬原則檢查。

<div>

## <a name="network-considerations"></a>網路考慮

雖然 Lync Server 2013 中的頻寬原則服務強制執行音訊與視頻的頻寬限制，但在網路路由器（第2層和第3層）不會強制執行此限制。 Lync Server 2010 CAC 無法防止資料應用程式（例如，在 WAN 連結上佔用整個網路頻寬），包括您的 CAC 原則所保留的音訊和視頻頻寬。 若要保護您網路上的必要頻寬，您可以部署服務品質（QoS）通訊協定（例如差異服務（DiffServ））。 因此，最佳做法是將您定義的 CAC 頻寬原則與您可能部署的任何 QoS 設定進行協調。

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a>VPN 上的媒體與信號路徑

如果您的企業透過 VPN 支援媒體，請確定媒體資料流程和傳送信號資料流程都透過 VPN，或者兩者都是透過網際網路路由。 根據預設，媒體和傳送信號資料流程會透過 VPN 隧道進行。

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a>呼叫外部使用者的許可控制

對於網路流量流經網際網路的遠端使用者，不會強制執行呼叫許可控制。 因為媒體流量是穿越網際網路，而不是由 Lync Server 管理，所以無法套用 CAC。 不過，您可以在通話中的部分，在整個商業網路中執行 CAC 檢查。

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a>呼叫接入控制 PSTN 連接

無論是連接到 IP/PBX、PSTN 閘道或 SIP 幹線，都能在中繼伺服器上強制使用呼叫許可控制。 因為中繼伺服器是一個後端到後端的使用者代理程式（B2BUA），所以它會終止媒體。 它有兩個連接端：連線至 Lync Server 的一端，以及連線至 PSTN 閘道、IP/Pbx 或 SIP trunks 的閘道端。 如需 PSTN 連線的詳細資料，請參閱[在 Lync Server 2013 規劃 PSTN](lync-server-2013-planning-for-pstn-connectivity.md)連線。

除非啟用 [媒體旁路]，否則在中繼伺服器的兩端都可以強制執行 CAC。 如果已啟用媒體旁路，媒體流量就不會穿過中繼伺服器，而是直接在 Lync 用戶端和閘道之間流動。 在此情況下，不需要 CAC。 如需詳細資訊，請參閱[在 Lync Server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)。

下圖說明如何啟用不使用媒體旁路的 PSTN 連線的 CAC。

**在連接至 PSTN 時呼叫許可控制強制**

![語音 Cac 媒體旁路連接強制](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "語音 Cac 媒體旁路連接強制")

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a>與舊版 Office 通訊伺服器的通話許可控制的相容性

只能在已啟用 Lync Server 2010 及更新版本的端點上啟用呼叫許可控制。

在執行 Office Communicator 2007 R2 或更舊版本的端點上無法啟用呼叫許可控制。

**在不同的 Lync Server 版本上應用 CAC**

![語音 Cac 版本比較圖表](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "語音 cac 版本比較圖表")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

