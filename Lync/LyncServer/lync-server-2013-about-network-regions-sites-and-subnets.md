---
title: Lync Server 2013：關於網路地區、網站及子網
description: Lync Server 2013：關於網路地區、網站及子網。
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
ms.openlocfilehash: a3c7f660f3c72003527e0721c3f9702865e9b9b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568929"
---
# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a>關於 Lync Server 2013 中的網路地區、網站和子網

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

本節所說明的進階 Enterprise Voice 功能共用網路地區、網站及子網路的特定設定需求。例如，這三個進階功能都需要拓撲中的每個子網路與特定 *「網站」* 相關聯，而且每個網站都必須與 *「網路地區」* 相關聯。

<div>


> [!IMPORTANT]  
> 在您開始進行通話許可控制、E9-1-1 或媒體旁路的網路設定之前，請確定您已在規劃檔中的「 <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013</A> 」主題中查看有關網路設定的其他資訊。 如需主要關於通話許可控制之網路設定的詳細資訊，請參閱規劃檔中的在 <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013 中定義通話許可控制的需求</A> 。



</div>

通話許可控制及 E9-1-1 具有其他的網站設定需求：

  - 通話許可控制需要指定透過 WAN 頻寬限制所限制之每個網站的 *「頻寬原則設定檔」*。 如果您打算部署通話許可控制，您必須先 [在 Lync Server 2013 中建立頻寬原則設定檔](lync-server-2013-create-bandwidth-policy-profiles.md) ，再設定網路網站。

  - E9-1-1 需要指定每個網站的 *「位置原則」*。 如果您打算部署 E9-1-1，您必須先 [在 Lync Server 2013 中建立位置原則](lync-server-2013-create-location-policies.md) ，再設定網站。

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a>建立或修改網路地區、網站及子網路

下列主題提供網路地區及網站的建立或修改步驟，以及將子網路與網站相關聯的步驟。這些不是任何特定進階 Enterprise Voice 功能特有的主題。

  - [在 Lync Server 2013 中建立或修改網路地區](lync-server-2013-create-or-modify-a-network-region.md)

  - [在 Lync Server 2013 中建立或修改網路網站](lync-server-2013-create-or-modify-a-network-site.md)

  - [在 Lync Server 2013 中建立子網與網路網站的關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

