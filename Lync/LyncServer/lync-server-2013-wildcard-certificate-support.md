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
ms.openlocfilehash: d639ba422bde7b936bd58ff58abae47ea365bb70
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508520"
---
# <a name="wildcard-certificate-support-in-lync-server-2013"></a>Lync Server 2013 中的萬用字元憑證支援

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-21_

Lync Server 2013 使用憑證來提供通訊加密和伺服器身分識別驗證。 某些情況下，例如透過反向 Proxy 的 Web 發佈，不需要與代表服務之伺服器完整網域名稱 (FQDN) 相符的強式主體替代名稱 (SAN) 項目。 在這些情況下，您可以使用含萬用字元 SAN 項目的憑證 (一般稱為「萬用字元憑證」) 來降低從公用憑證授權單位要求憑證的成本，並能降低憑證的規劃程序複雜度。

<div>


> [!WARNING]  
> 若要保留整合通訊 (UC) 裝置 (例如，電話機) 的功能，您應該仔細測試部署的憑證，確定實作萬用字元憑證之後，裝置的功能正常運作。



</div>

不支援將萬用字元項目做為任何角色的主體名稱 (又稱為一般名稱或 CN)。在 SAN 中使用萬用字元項目時，支援下列伺服器角色：

  - <span></span>  
    **反向 proxy。**    萬用字元 SAN 專案支援簡單 URL (符合和撥入) 發行憑證。

  - <span></span>  
    **反向 proxy。**    LyncDiscover 發佈憑證上的 SAN 專案支援萬用字元 SAN 專案。

  - <span></span>  
    **Director。**    在簡單的 URLs 中支援萬用字元 SAN 專案， (會在 [Director] 網頁元件中符合和撥出) 和 LyncDiscover 及 LyncDiscoverInternal 的 SAN 專案。

  - <span></span>  
    **前端伺服器 (Standard Edition) 和前端集區 (Enterprise Edition) 。** 針對簡易 URLs，可支援萬用字元 SAN 專案， (在) 和撥入前端 web 元件中的 LyncDiscover 和 LyncDiscoverInternal 的 SAN 專案。

  - <span></span>  
    **Exchange 整合通訊 (UM) 。**    伺服器在部署為獨立伺服器時，不會使用 SAN 專案。

  - <span></span>  
    **Microsoft Exchange Server Client Access Server。**    內部和外部用戶端支援 SAN 中的萬用字元專案。

  - <span></span>  
    **Exchange 整合通訊 (UM) 與同一部伺服器上的 Microsoft Exchange Server Client Access server。**    支援萬用字元 SAN 專案。

本主題中未介紹的伺服器角色：

  - 內部伺服器角色 (包括（但不限於）轉送伺服器、封存和監控伺服器、Survivable 分支裝置或 Survivable Branch 伺服器) 

  - 外部 Edge Server 介面

  - 內部 Edge Server
    
    <div>
    

    > [!NOTE]  
    > 針對內部 Edge Server 介面，可以將萬用字元專案指派給 SAN，而且支援此專案。 不會查詢內部 Edge Server 上的 SAN，而且萬用字元 SAN 專案的值有限。

    
    </div>

如需憑證設定的詳細資料，包括憑證中的萬用字元使用，請參閱下列主題：

  - [Lync Server 2013 中內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Lync Server 2013 中外部使用者存取的憑證需求](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Lync Server 2013 的憑證摘要-DNS 與 HLB 負載平衡](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Lync Server 2013 中的憑證摘要-單一 Director](lync-server-2013-certificate-summary-single-director.md)

  - [Lync Server 2013 中的憑證摘要-調整式 Director 集區（硬體負載平衡器）](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Lync Server 2013 的憑證摘要-反向 proxy](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [整合內部部署整合通訊和 Lync Server 2013 的指導方針](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

如需有關為 Exchange 設定憑證的詳細資訊，包括使用萬用字元，請參閱 Exchange 2013 產品檔。

</div>

<span> </span>

</div>

</div>

</div>

