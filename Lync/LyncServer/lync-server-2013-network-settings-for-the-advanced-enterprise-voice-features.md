---
title: Lync Server 2013： [高級企業語音功能] 的網路設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ce4983f7744158c9c9ff56cdfdde818fdc8e14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a>Lync Server 2013 中的 [高級企業語音功能] 的網路設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-10_

Lync Server 有三個高級企業語音功能： [呼叫許可控制] （CAC）、緊急服務（E9-1-1），以及 [媒體旁路]。 這些功能會在 Lync 伺服器拓撲中與網路網站共用網路區域、網路網站和每個子閘道聯的特定設定需求。 如需規劃部署這些功能的詳細資訊，請參閱：

  - [在 Lync Server 2013 中規劃通話許可控制](lync-server-2013-planning-for-call-admission-control.md)

  - [在 Lync Server 2013 中規劃緊急服務 (E9-1-1)](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [在 Lync Server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)

如需有關部署這些功能的詳細資訊，請參閱部署檔中的[Lync Server 2013 中的 [部署高級企業語音功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)]。

本主題概述所有三個高級企業語音功能通用的配置需求。

<div>

## <a name="network-regions"></a>網路區域

網路區域是網路中樞或網路骨幹，只能在通話許可控制（CAC）、E9-1 及媒體旁路設定中使用。

<div>


> [!NOTE]  
> 網路區域與 Lync Server 電話撥入式會議區域不同，必須將電話撥入式會議存取號碼與一或多個 Lync Server 撥號方案建立關聯。 如需電話撥入式會議區域的詳細資料，請參閱規劃檔中的<A href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013 中的電話撥入式會議需求</A>。



</div>

CAC 需要每個網路區域都有一個相關聯的 Lync Server 中央網站，可管理該區域內的媒體流量（亦即根據已設定的原則作出決策，關於是否有即時音訊或視頻會話可以建立）。 Lync Server 中央網站不代表地理位置，而是設定為一個池或一組池的邏輯伺服器群組。 如需中心網站的詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的參考拓撲](lync-server-2013-reference-topologies.md)。 另請參閱可支援性檔中的[Lync Server 2013 支援的拓撲](lync-server-2013-supported-topologies.md)。

若要設定網路區域，您可以使用 Lync Server [控制台] 的 [**網路**設定] 區段上的 [**區域**] 索引標籤，或執行**新的 CsNetworkRegion**或**CsNetworkRegion 的**Lync server 管理命令介面 Cmdlet。 如需相關指示，請參閱在部署檔中的[Lync server 2013 中建立或修改網路區域](lync-server-2013-create-or-modify-a-network-region.md)，或參閱 Lync Server 管理命令介面檔。

所有三個高級企業語音功能都將共用相同的網路區域定義。 如果您已經為一個功能建立了網路區域，就不需要為其他功能建立新的網路區域。 不過，您可能需要修改現有的網路區域定義，才能套用特定功能的設定。 例如，如果您已建立 E9 的網路區域（不需要關聯的中央網站），且稍後您要部署 [呼叫許可控制]，則您必須修改每個網路區域定義，才能指定中央網站。

若要將 Lync Server 中央網站與網路區域建立關聯，您可以指定中心網站名稱，方法是使用 Lync Server [控制台] 的 [**網路**設定] 區段，或執行**新的 CsNetworkRegion**或**CsNetworkRegion** Lync server 管理命令介面 Cmdlet。 如需相關指示，請參閱在部署檔中的[Lync server 2013 中建立或修改網路區域](lync-server-2013-create-or-modify-a-network-region.md)，或參閱 Lync Server 管理命令介面檔。

</div>

<div>

## <a name="network-sites"></a>網路網站

Network 網站代表地理位置，例如分支機搆、地區辦事處或主辦公室。 每個網路網站都必須與特定的網路區域建立關聯。

<div>


> [!NOTE]  
> 網路網站只能由高級企業語音功能使用。 它們與您在 Lync Server 拓撲結構中設定的分支網站不同。 如需分支網站的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-reference-topologies.md">Lync Server 2013 中的參考拓撲</A>。 另請參閱可支援性檔中的<A href="lync-server-2013-supported-topologies.md">Lync Server 2013 支援的拓撲</A>。



</div>

若要設定網路網站並將它與網路區域建立關聯，您可以使用 Lync Server [控制台] 的 [**網路**設定] 區段，或執行 Lync Server Management Shell **CsNetworkSite**或**CsNetworkSite** Cmdlet。 如需詳細資訊，請參閱在部署檔中的[Lync server 2013 中建立或修改網路網站](lync-server-2013-create-or-modify-a-network-site.md)，或參閱 Lync Server 管理命令介面檔。

</div>

<div>

## <a name="identify-ip-subnets"></a>識別 IP 子網

針對每個網路網站，您必須與您的網路系統管理員合作，以判斷指派給每個網路網站的 IP 子網。 如果您的網路系統管理員已經將 IP 子網組織到網路區域和網路網站，您的工作會明顯簡化。

例如，您可以將下列 IP 子網指派給北美地區的紐約網站： 172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。 如果 Bob 通常是在底特律中運作，在紐約辦公室進行訓練，然後開啟他的電腦並聯機到網路上，他的電腦將會取得 IP 位址，並在為紐約所指派的四個範圍中的其中一個，例如172.29.80.103。

<div>


> [!WARNING]  
> 在伺服器的網路設定期間指定的 IP 子網必須符合用戶端電腦所提供的格式，才能正確地用於媒體旁路。 Lync 用戶端會採用其本機 IP 位址，並使用相關聯的子網路遮罩來遮罩 IP 位址。 在判斷與每個用戶端相關的旁路識別碼時，註冊機構會將與每個網路網站相關聯的 IP 子網清單與用戶端提供的子網進行比較，以取得完全相符的專案。 基於這個原因，在伺服器的網路設定期間輸入的子網很重要，而不是虛擬子網。 （如果您部署 [呼叫許可控制]，但無法使用 [媒體旁路]，即使您設定虛擬子網，也能正常使用通話許可控制功能。）<BR>例如，如果 Lync 用戶端在 IP 位址為172.29.81.57 且 IP 子網路遮罩為255.255.255.0 的電腦上登入，則會要求與子網172.29.81.0 相關聯的旁路 ID。 如果子網是定義為 172.29.0.0/16，雖然用戶端屬於虛擬子網，但註冊機構不會認為這個相符，因為註冊機構特別想要尋找子網172.29.81.0。 因此，系統管理員必須完全按照 Lync 用戶端所提供的方式輸入子網（無論是靜態或由動態主機設定通訊協定（DHCP），都能在網路設定期間由子網進行設定。）



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a>將子網與網路網站建立關聯

商業網路中的每個子網都必須與網路網站相關聯（也就是說，每個子網上都需要與地理位置相關聯）。 這個子網的關聯性能讓 [高級企業語音] 功能在地理位置找到端點。 例如，找出端點可讓 CAC 從網路網站傳送即時音訊及視頻資料的流程。

若要將子網與網路網站建立關聯，您可以使用 Lync Server [控制台] 的 [**網路**設定] 區段，或者您可以使用 Lync Server 管理命令介面。 如需相關指示，請參閱在部署檔中[將子網與 Lync server 2013 中的網路網站建立關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)，或參閱 Lync Server 管理命令介面檔。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中規劃通話許可控制](lync-server-2013-planning-for-call-admission-control.md)  
[在 Lync Server 2013 中規劃緊急服務 (E9-1-1)](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[在 Lync Server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

