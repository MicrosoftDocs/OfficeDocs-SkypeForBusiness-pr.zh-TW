---
title: Lync Server 2013： 關於網路地區、 網站及子網路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2f6de7a39b3029f1edc1252b90ec264d774632f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a>關於網路地區、 網站及 Lync Server 2013 中的子網路

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-24_

本節所說明的進階 Enterprise Voice 功能共用網路地區、網站及子網路的特定設定需求。例如，這三個進階功能都需要拓撲中的每個子網路與特定 *「網站」* 相關聯，而且每個網站都必須與 *「網路地區」* 相關聯。

<div>


> [!IMPORTANT]  
> 開始網路組態的通話許可控制之前，請 E9-1-1 或媒體旁路，請確定您已檢閱規劃文件中的<A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 中的進階 Enterprise Voice 功能的網路設定</A>主題中的網路設定的其他資訊。 如需主要有關通話許可控制的網路組態的詳細資訊，也請參閱<A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">定義 Lync Server 2013 中的通話許可控制需求</A>規劃文件。



</div>

通話許可控制及 E9-1-1 具有其他的網站設定需求：

  - 通話許可控制需要指定透過 WAN 頻寬限制所限制之每個網站的 *「頻寬原則設定檔」*。 如果您打算部署通話許可控制，您之前，必須[建立頻寬原則設定檔，在 Lync Server 2013 中的](lync-server-2013-create-bandwidth-policy-profiles.md)設定您的網路網站。

  - E9-1-1 需要指定每個網站的 *「位置原則」*。 如果您打算部署 E9-1-1，您必須[Lync Server 2013 中的建立位置原則](lync-server-2013-create-location-policies.md)，再設定您的網路網站。

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a>建立或修改網路地區、網站及子網路

下列主題提供網路地區及網站的建立或修改步驟，以及將子網路與網站相關聯的步驟。這些不是任何特定進階 Enterprise Voice 功能特有的主題。

  - [建立或修改 Lync Server 2013 中的網路區域](lync-server-2013-create-or-modify-a-network-region.md)

  - [建立或修改 Lync Server 2013 中的網路網站](lync-server-2013-create-or-modify-a-network-site.md)

  - [關聯子網路與 Lync Server 2013 中的網路網站](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

