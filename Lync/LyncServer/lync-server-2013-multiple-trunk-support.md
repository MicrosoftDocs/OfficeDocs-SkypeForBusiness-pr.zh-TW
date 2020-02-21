---
title: Lync Server 2013： 多個主幹支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 273ab81fc0ab3fce9daae56abc6dc68b89489371
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="multiple-trunk-support-in-lync-server-2013"></a>Lync Server 2013 中的多個主幹支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

Lync Server 2013 功能可支援多個閘道與中繼伺服器之間的關聯。 這些關聯中所定義的主幹，也就是邏輯關聯的中繼伺服器集區與公用交換的電話網路 (PSTN) 閘道、 工作階段邊界控制器 (SBC) 或 IP PBX 之間進行。 使用拓撲產生器來使閘道與中繼伺服器 （也就是主幹） 產生關聯。

  - 若要指派或移除 Lync Server 2013 中的主幹，您必須先在拓撲產生器中定義主幹。 主幹所組成的下列關聯： 中繼伺服器的完整網域名稱 (FQDN)，中繼伺服器的聆聽連接埠、 閘道的 FQDN、 閘道聆聽連接埠。

  - 若要設定多個主幹，您可以建立多個相同的閘道與中繼伺服器之間的關聯。 這可提供其他企業語音基礎結構，也就是在專用交換機 (pbx) interoperational 案例特別有用。

定義主幹時，它必須與路由相關聯。 若要建立關聯的主幹路由，請您可以定義主幹的簡單名稱在拓撲產生器。 Lync Server Control Panel，其中主幹可以與路由相關聯的主幹名稱使用這個簡單的名稱。 簡單的主幹名稱會當做 Lync Server 管理命令介面的閘道名稱。

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

系統管理員必須先選取預設主幹相關聯的中繼伺服器。 從 [拓撲產生器相關聯的中繼伺服器，以滑鼠右鍵按一下，然後按一下 [**內容**。 指定中繼伺服器的預設閘道。

下圖說明針對每個中繼伺服器和閘道定義的多個主幹。

**M-N 主幹路由**

![多個主幹工作分派。](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "多個主幹工作分派。")

</div>

<span> </span>

</div>

</div>

</div>

