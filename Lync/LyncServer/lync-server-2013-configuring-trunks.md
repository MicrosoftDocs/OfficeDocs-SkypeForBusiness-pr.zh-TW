---
title: Lync Server 2013： 設定主幹
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09151bf1e5fab592f8051878bcd8218690583309
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a>在 Lync Server 2013 中設定主幹

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

Enterprise Voice 部署的一部分，您可以設定中繼伺服器與一或多個下列同儕 Enterprise Voice 用戶端和組織中的裝置提供公用交換的電話網路 (PSTN) 連線能力之間的主幹：

  - 網際網路電話語音服務提供者 (ITSP) 的 SIP 主幹連線

  - PSTN 閘道

  - 專用交換機 (Private branch exchange，PBX)

如需詳細資訊，請參閱規劃文件中的[Planning for Lync Server 2013 中的 PSTN 連線能力](lync-server-2013-planning-for-pstn-connectivity.md)。

<div>


> [!IMPORTANT]  
> 在您開始進行主幹設定之前，請確認已建立拓撲，而且中繼伺服器及其對等已設定好，並彼此產生關聯。 如需詳細資訊，請參閱部署文件中的<A href="lync-server-2013-define-a-gateway-in-topology-builder.md">定義在 Lync Server 2013 中的拓撲產生器的閘道</A>。



</div>

<div>


> [!NOTE]  
> 主幹組態的一部分，您可以啟用 Lync Server 2013 媒體旁路功能，可讓媒體略過中繼伺服器。 不論是否啟用媒體旁路功能，都可以設定主幹，但強烈建議您啟用該功能。 如需詳細資訊，請參閱<A href="lync-server-2013-planning-for-media-bypass.md">Planning for 媒體旁路 Lync Server 2013 中規劃文件。</A>



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中的多個主幹支援](lync-server-2013-multiple-trunk-support.md)

  - [Lync Server 2013 中的主幹間路由](lync-server-2013-inter-trunk-routing.md)

  - [Lync Server 2013 中檢視主幹組態資訊](lync-server-2013-view-trunk-configuration-information.md)

  - [設定與 Lync Server 2013 中的媒體旁路的主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [沒有媒體旁路 Lync Server 2013 中設定主幹](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [在 Lync Server 2013 中建立新的主幹集合組態設定](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [刪除現有的 Lync Server 2013 中的 SIP 主幹組態設定集合](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [修改 Lync Server 2013 中的 SIP 主幹組態設定](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [在 Lync Server 2013 中測試 SIP 主幹組態設定](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [檢視 Lync Server 2013 中的個別 SIP 主幹的相關資訊](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中的拓撲產生器中定義閘道](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[規劃 Lync Server 2013 中的 PSTN 連線](lync-server-2013-planning-for-pstn-connectivity.md)  
[規劃 Lync Server 2013 中的媒體旁路](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

