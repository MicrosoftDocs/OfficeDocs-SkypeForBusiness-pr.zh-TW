---
title: Lync Server 2013：設定主幹
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
ms.openlocfilehash: f1021295b375e4f28294ffb1ca5738d651f9ced2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a>在 Lync Server 2013 中設定主幹

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

在企業語音部署中，您可以設定在中繼伺服器與一或多個下列對等之間的幹線，為貴組織中的企業語音用戶端和裝置提供公用交換電話網絡（PSTN）連線：

  - 網際網路電話服務提供者（ITSP）的 SIP 中繼連線

  - PSTN 閘道

  - 私人分支 exchange （PBX）

如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 規劃 PSTN](lync-server-2013-planning-for-pstn-connectivity.md)連線。

<div>


> [!IMPORTANT]  
> 開始中繼設定前，請確認已建立拓撲，且已設定並與其他中繼伺服器及其對等專案相關聯。 如需詳細資訊，請參閱部署檔中的<A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Lync Server 2013 [拓撲</A>建立器] 中的 [定義閘道]。



</div>

<div>


> [!NOTE]  
> 您可以在主幹設定中啟用 Lync Server 2013 媒體旁路功能，這可讓媒體略過中繼伺服器。 Trunks 可以使用或不啟用媒體旁路進行設定，但我們強烈建議您啟用它。 如需詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-planning-for-media-bypass.md">Lync Server 2013 中的媒體旁路規劃</A>。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中有多個中繼支援](lync-server-2013-multiple-trunk-support.md)

  - [Lync Server 2013 中的中繼間路由](lync-server-2013-inter-trunk-routing.md)

  - [在 Lync Server 2013 中查看幹線設定資訊](lync-server-2013-view-trunk-configuration-information.md)

  - [在 Lync Server 2013 中使用 [旁路媒體] 設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [在 Lync Server 2013 中設定沒有媒體旁路的主幹](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [在 Lync Server 2013 中建立中繼設定的新集合](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [刪除 Lync Server 2013 中現有的 SIP 幹線配置設定集合](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [在 Lync Server 2013 中修改 SIP 幹線配置設定](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [在 Lync Server 2013 中測試 SIP 幹線配置設定](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [在 Lync Server 2013 中查看個別 SIP trunks 的相關資訊](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 的拓撲產生器中定義閘道](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[在 Lync Server 2013 規劃 PSTN 連線能力](lync-server-2013-planning-for-pstn-connectivity.md)  
[在 Lync Server 2013 中規劃媒體旁路](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

