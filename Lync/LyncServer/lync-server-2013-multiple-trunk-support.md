---
title: Lync Server 2013：支援多個主幹
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 156db04ceb26809c7043f30e9e01ea0071e0a31d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="multiple-trunk-support-in-lync-server-2013"></a>Lync Server 2013 中有多個中繼支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

Lync Server 2013 功能支援閘道與中繼伺服器之間的多個關聯性。 這些關聯是透過定義幹線來建立的，這是中繼伺服器池與公用交換式電話網絡（PSTN）閘道、會話邊界控制器（SBC）或 IP PBX 之間的邏輯關聯。 使用 [拓撲建立器]，將閘道與中繼伺服器（也就是 trunks）建立關聯。

  - 若要在 Lync Server 2013 中指派或移除主幹，您必須先在拓撲建立器中定義主幹。 主幹包含下列關聯：中繼伺服器的完整功能變數名稱（FQDN）、中繼伺服器偵聽埠、閘道 FQDN，以及閘道偵聽埠。

  - 若要設定多個 trunks，您可以在同一個閘道與中繼伺服器之間建立多個關聯性。 這可為企業語音結構提供額外的復原能力，這在私人分支 exchange （PBX） interoperational 案例中特別有用。

定義主幹時，必須與路由建立關聯。 若要將主幹與路線建立關聯，您可以在 [拓撲建立器] 中定義主幹的簡單名稱。 這個簡單的名稱是在 Lync Server [控制台] 中用來做為幹線名稱，其中 trunks 可以與路由建立關聯。 簡單的主幹名稱是從 Lync Server 管理命令介面的閘道名稱使用。

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

系統管理員必須選取與中繼伺服器相關聯的預設主幹。 從拓撲建立器，以滑鼠右鍵按一下關聯的中繼伺服器，然後按一下 [**屬性**]。 指定中繼伺服器的預設閘道。

下圖說明針對每個中繼伺服器和閘道定義的多個 trunks。

**M-N 幹線路由**

![多個幹線作業。](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "多個幹線作業。")

</div>

<span> </span>

</div>

</div>

</div>

