---
title: Lync Server 2013：高級 Enterprise Voice 功能的網路設定
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
ms.openlocfilehash: 340a1902137b6c675b154ef9ccf3d9fbcc882e88
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a>Lync Server 2013 中的高級 Enterprise Voice 功能的網路設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-10_

Lync Server 具有三個高級 Enterprise Voice 功能：通話許可控制 (CAC) 、緊急服務 (E9-1-1) 和媒體旁路。 這些功能會在 Lync Server 拓撲中，共用網路地區、網路網站及每個子網與網路網站關聯的特定設定需求。 如需這些功能之部署規劃的詳細資訊，請參閱：

  - [在 Lync Server 2013 中規劃通話許可控制](lync-server-2013-planning-for-call-admission-control.md)

  - [在 Lync Server 2013 中規劃緊急服務 (E9-1-1) ](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [在 Lync Server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)

如需有關部署上述各項功能的詳細資訊，請參閱部署檔中的在[Lync Server 2013 中部署 Advanced Enterprise Voice 功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)。

本主題概要說明所有三種高級 Enterprise Voice 功能的常見設定需求。

<div>

## <a name="network-regions"></a>網路地區

網路地區是一種網路中樞或網路骨幹，只有在通話許可控制 (CAC)、E9-1-1 和媒體旁路的組態中才會使用。

<div>


> [!NOTE]  
> 網路地區與 Lync Server 電話撥入式會議地區不同，後者與一或多部 Lync Server 撥號對應表建立電話撥入式會議存取號碼的要求。 如需電話撥入式會議區域的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013 中的電話撥入式會議需求</A>。



</div>

CAC 需要每個網路地區都有相關聯的 Lync Server 中央網站，它會管理地區內的媒體流量 (也就是說，它會根據您設定的原則進行決策，有關是否可以) 建立即時音訊或視頻會話。 Lync Server 中央網站不代表地理位置，而是設定為集區或集區集區的邏輯群組。 如需中央網站的詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的參考拓撲](lync-server-2013-reference-topologies.md)。 另請參閱支援檔中的[Lync Server 2013 中支援的拓撲](lync-server-2013-supported-topologies.md)。

若要設定網路地區，您可以使用 Lync Server 控制台的 [**網路**設定] 區段中的 [**區域**] 索引標籤，或執行**New-CsNetworkRegion**或**Set-CsNetworkRegion** Lync server 管理命令介面 Cmdlet。 如需相關指示，請參閱部署檔中的在[Lync server 2013 中建立或修改網路地區](lync-server-2013-create-or-modify-a-network-region.md)，或參考 Lync Server 管理命令介面檔。

所有三個高級 Enterprise Voice 功能都會共用相同的網路地區定義。 如果您已為其中一項功能建立網路地區，即無須再為其他功能建立新的網路地區。 但您可能需要修改現有的網路地區定義，以套用功能特有的設定。 例如，如果您為 E9-1-1 (不需要有相關聯的中央網站) 建立網路地區後，又部署了通話許可控制，則必須修改每個網路地區定義以指定中央網站。

若要將 Lync Server 中央網站與網路地區產生關聯，您可以使用 Lync Server 控制台的 [**網路**設定] 區段，或是執行**New-CsNetworkRegion**或**Set-CsNetworkRegion** Lync server 管理命令介面 Cmdlet 來指定中央網站名稱。 如需相關指示，請參閱部署檔中的在[Lync server 2013 中建立或修改網路地區](lync-server-2013-create-or-modify-a-network-region.md)，或參考 Lync Server 管理命令介面檔。

</div>

<div>

## <a name="network-sites"></a>網站

網路網站代表地理位置，例如分公司、地區辦事處或總公司。每個網路網站都必須與某個網路地區相關聯。

<div>


> [!NOTE]  
> 只有「高級 Enterprise Voice」功能才能使用網路網站。 它們不同于您在 Lync Server 拓撲中設定的分支網站。 如需有關分支網站的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-reference-topologies.md">Lync Server 2013 中的參考拓撲</A>。 另請參閱支援檔中的<A href="lync-server-2013-supported-topologies.md">Lync Server 2013 中支援的拓撲</A>。



</div>

若要設定網路網站，並將其與網路地區產生關聯，您可以使用 Lync Server 控制台的 [**網路**設定] 區段，或執行 Lync Server 管理命令介面**New-CsNetworkSite**或**Set-CsNetworkSite** Cmdlet。 如需詳細資訊，請參閱部署檔中的[建立或修改 Lync server 2013](lync-server-2013-create-or-modify-a-network-site.md)中的網站，或參考 Lync Server 管理命令介面檔。

</div>

<div>

## <a name="identify-ip-subnets"></a>識別 IP 子網路

對於每一個網站，您需要和網路管理員一同決定要指派給每一個網站的 IP 子網路。如果您的網路管理員已經整理好各個網路地區與網站的 IP 子網路，您的工作將會大幅簡化。

例如，可以將指派以下 IP 子網路給北美洲區域內的紐約網站：172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. 假設平常在 Detroit 工作的 Bob 要到 New York 分公司受訓。當他開啟自己的電腦並連線至網路時，他的電腦會取得分配給紐約的四個範圍內的其中一個 IP 位址，例如，172.29.80.103。

<div>


> [!WARNING]  
> 在伺服器上的網路設定期間指定的 IP 子網必須符合用戶端電腦所提供的格式，才能正確用於媒體旁路。 Lync 用戶端會採用其本機 IP 位址，並以關聯的子網路遮罩遮罩 IP 位址。 決定與每一位用戶端相關聯的旁路識別碼時，註冊機構會比較與用戶端所提供之子網相關聯的 IP 子網清單，以取得完全相符的專案。 因此，在伺服器上的網路設定期間輸入的子網，必須是實際的子網，而不是虛擬子網，這一點很重要。  (如果您部署通話許可控制，但沒有媒體旁路，則即使您設定虛擬子網，通話許可控制也會正常運作。 ) <BR>例如，如果 Lync 用戶端在其 IP 位址為172.29.81.57 且 IP 子網路遮罩為255.255.255.0 的電腦上登入，則會要求與子網172.29.81.0 相關聯的旁路識別碼。 如果子網路定義為 172.29.0.0/16，則儘管用戶端屬於虛擬子網路，登錄器仍舊不會將其視為完全相符，因為登錄器所尋找的是真正的子網路 172.29.81.0。 因此，管理員必須嚴格依照 Lync 用戶端所提供的方式輸入子網， (會在網路設定期間（靜態或透過動態主機設定通訊協定 (DHCP) ）輸入子網。 ) 



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a>建立子網路與網路網站的關聯

企業網路中的每個子網路都必須與某個網路網站相關聯 (亦即，每個子網路都必須與某個地理位置相關聯)。 這個子閘道聯可讓高級 Enterprise Voice 功能找到地理位置的端點。 例如，找出端點位置後，CAC 可以調節進出該網路網站的即時音訊與視訊資料流量。

若要將子網與網站產生關聯，您可以使用 Lync Server 控制台的 [**網路**設定] 區段，也可以使用 Lync Server 管理命令介面。 如需相關指示，請參閱部署檔中的在[Lync server 2013 中建立子網與網站的關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)，或參考 Lync Server 管理命令介面檔。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中規劃通話許可控制](lync-server-2013-planning-for-call-admission-control.md)  
[在 Lync Server 2013 中規劃緊急服務 (E9-1-1) ](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[在 Lync Server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

