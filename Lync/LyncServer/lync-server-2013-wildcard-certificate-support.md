---
title: Lync Server 2013 萬用字元憑證支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d48ba92ffd18e385be95d6218357303a67f892c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a>Lync Server 2013 中的萬用字元憑證支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-03-21_

Lync Server 2013 使用憑證來提供通訊加密] 及 [server 身分識別驗證。 某些情況下，例如透過反向 Proxy 的 Web 發佈，不需要與代表服務之伺服器完整網域名稱 (FQDN) 相符的強式主體替代名稱 (SAN) 項目。 在這些情況下，您可以使用含萬用字元 SAN 項目的憑證 (一般稱為「萬用字元憑證」) 來降低從公用憑證授權單位要求憑證的成本，並能降低憑證的規劃程序複雜度。

<div>


> [!WARNING]  
> 若要保留整合通訊 (UC) 裝置 (例如，電話機) 的功能，您應該仔細測試部署的憑證，確定實作萬用字元憑證之後，裝置的功能正常運作。



</div>

不支援將萬用字元項目做為任何角色的主體名稱 (又稱為一般名稱或 CN)。在 SAN 中使用萬用字元項目時，支援下列伺服器角色：

  - <span></span>  
    **反向 proxy。**   簡單 URL （meet 和 dialin） 發行的憑證可支援萬用字元 SAN 項目。

  - <span></span>  
    **反向 proxy。**   萬用字元 SAN 項目都支援 SAN 項目中的 LyncDiscover 發行的憑證。

  - <span></span>  
    **Director。**   萬用字元 SAN 項目支援簡單 Url （meet 和 dialin） 和 SAN 項目 LyncDiscover 和 LyncDiscoverInternal Director web 元件。

  - <span></span>  
    **前端伺服器 (Standard Edition) 及前端集區 (Enterprise Edition)。** 萬用字元 SAN 項目支援簡單 url （meet 和 dialin），和 SAN 項目 LyncDiscover 和 LyncDiscoverInternal 前方結束 web 元件。

  - <span></span>  
    **Exchange 整合通訊 (UM)。**   伺服器不會使用 SAN 項目部署為獨立伺服器時。

  - <span></span>  
    **Microsoft Exchange Server 用戶端存取伺服器。**   內部和外部用戶端支援在 SAN 中的萬用字元項目。

  - <span></span>  
    **在同一部伺服器上的 Exchange 整合通訊 (UM) 及 Microsoft Exchange Server 用戶端存取伺服器。**   支援萬用字元 SAN 項目。

本主題中未介紹的伺服器角色：

  - 內部伺服器角色 （包括，但不是限於中繼伺服器、 封存和監控伺服器、 Survivable Branch Appliance 或 Survivable Branch 伺服器）

  - 外部 Edge Server 介面

  - 內部 Edge Server
    
    <div>
    

    > [!NOTE]  
    > 內部的 Edge Server 介面的萬用字元項目可以指派給 SAN (英文），並支援。 SAN (英文） 內部 Edge Server 上不在查詢中，而且萬用字元 SAN 項目時限制的值。

    
    </div>

如需詳細資訊的憑證組態，包括萬用字元的使用中的憑證，請參閱下列主題：

  - [適用於 Lync Server 2013 中的內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Lync Server 2013 中的外部使用者存取的憑證需求](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [憑證摘要-DNS 與 HLB 負載平衡 Lync Server 2013 中](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [憑證摘要-Lync Server 2013 中的單一 Director](lync-server-2013-certificate-summary-single-director.md)

  - [憑證摘要-調整式 Director 集區、 Lync Server 2013 中的硬體負載平衡器](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [憑證摘要-Lync Server 2013 中的反向 proxy](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [指導方針整合內部 Unified Messaging 和 Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

如需設定 Exchange，包括萬用字元，請使用憑證的詳細資訊請參閱 < Exchange 2013 產品的說明文件。

</div>

<span> </span>

</div>

</div>

</div>

