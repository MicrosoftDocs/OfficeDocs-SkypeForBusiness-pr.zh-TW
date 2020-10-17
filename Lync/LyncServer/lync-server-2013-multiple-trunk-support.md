---
title: Lync Server 2013：多個主幹支援
description: Lync Server 2013：多個主幹支援。
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
ms.openlocfilehash: 3bbabb90405b3fdae47a59ba8a0798743943216d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552419"
---
# <a name="multiple-trunk-support-in-lync-server-2013"></a>Lync Server 2013 中的多個主幹支援

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

Lync Server 2013 功能支援閘道和轉送伺服器之間的多重關聯。 這些關聯是透過定義主幹（轉送伺服器集區和公用交換電話網路 (PSTN) 閘道、會話邊界控制器 (SBC) 或 IP-PBX）進行。 使用拓撲產生器，將閘道與轉送伺服器相關聯 (也就是說，主幹) 。

  - 若要在 Lync Server 2013 中指派或移除主幹，您必須先在拓撲產生器中定義主幹。 主幹包含下列關聯：轉送伺服器的完整功能變數名稱 (FQDN) 、轉送伺服器接聽埠、閘道 FQDN 及閘道聆聽埠。

  - 若要設定多個主幹，您可以在同一個閘道和轉送伺服器之間建立多個關聯。 這為企業語音基礎結構提供額外的復原能力，尤其適用于私人分公司 exchange (PBX) interoperational 案例。

定義主幹時，它必須與路由相關聯。 若要將主幹關聯至路由，您可以在拓撲產生器中定義主幹的簡易名稱。 在 Lync Server 控制台中，這個簡易名稱是用來做為主幹名稱，主幹可以與路由相關聯。 簡易主幹名稱是 Lync Server 管理命令介面中使用的閘道名稱。

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

管理員必須選取與轉送伺服器相關聯的預設主幹。 在 [拓撲產生器] 中，以滑鼠右鍵按一下關聯的轉送伺服器，然後按一下 [ **屬性**]。 指定轉送伺服器的預設閘道。

下圖說明為每個轉送伺服器和閘道定義的多個主幹。

**M-N 主幹路由**

![多重主幹指派。](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "多重主幹指派。")

</div>

<span> </span>

</div>

</div>

</div>

