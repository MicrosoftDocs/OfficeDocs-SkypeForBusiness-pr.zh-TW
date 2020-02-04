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
ms.openlocfilehash: 8a3e64dcfd16212e618a8ebe152bd2516a25b26d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a>Lync Server 2013 中的萬用字元憑證支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-21_

Lync Server 2013 使用憑證來提供通訊加密和伺服器身分識別驗證。 在某些情況下（例如透過反向 proxy 的 web 發佈），強主題替換名稱（SAN）專案與提供服務之伺服器的完整功能變數名稱（FQDN）不需要。 在這些情況下，您可以使用包含萬用字元 SAN 專案的憑證（通常稱為 "萬用字元"）來降低從公用憑證授權單位申請之憑證的成本，以及減少憑證規劃程式的複雜性.

<div>


> [!WARNING]  
> 若要保留整合通訊（UC）裝置（例如，辦公桌電話）的功能，您應該仔細測試已部署的憑證，以確保在您執行萬用字元憑證後裝置正常運作。



</div>

在任何角色中，都不支援萬用字元專案作為 subject 名稱（也稱為「公用名」或「CN」）。 使用 SAN 中的萬用字元專案時，支援下列伺服器角色：

  - <span></span>  
    **反向 proxy。**   對於簡單的 URL （達到及撥入）發行憑證，支援萬用字元 SAN 專案。

  - <span></span>  
    **反向 proxy。**   LyncDiscover 發佈憑證上的 san 專案支援萬用字元 san 專案。

  - <span></span>  
    **導演。**   對於簡單的 url （達到及撥入），以及適用于 LyncDiscover 和 LyncDiscoverInternal 網頁元件的 SAN 專案，都支援萬用字元 san 專案。

  - <span></span>  
    **前端伺服器（標準版）和前端池（企業版）。** 對於簡單的 Url （達到及撥入），以及適用于 LyncDiscover 和 LyncDiscoverInternal （在前端網頁元件中）的 SAN 專案，都支援萬用字元 SAN 專案。

  - <span></span>  
    **Exchange 整合通訊（UM）。**   在部署成獨立伺服器時，伺服器不會使用 SAN 專案。

  - <span></span>  
    **Microsoft Exchange Server 用戶端存取伺服器。**   內部和外部用戶端支援 SAN 中的萬用字元專案。

  - <span></span>  
    **Exchange 整合通訊（UM）與相同伺服器上的 Microsoft Exchange Server 用戶端存取伺服器。**   支援萬用字元 SAN 專案。

在本主題中未解決的伺服器角色：

  - 內部伺服器角色（包括但不限於中繼伺服器、封存及監視伺服器、Survivable 分支裝置或 Survivable 分支伺服器）

  - 外部邊緣伺服器介面

  - 內部邊緣伺服器
    
    <div>
    

    > [!NOTE]  
    > 針對內部邊緣伺服器介面，您可以將萬用字元專案指派給 SAN，而且受支援。 不會查詢內部邊緣伺服器上的 SAN，且萬用字元 SAN 專案的值有限。

    
    </div>

如需憑證設定的詳細資料，包括在憑證中使用萬用字元，請參閱下列主題：

  - [Lync Server 2013 中內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Lync Server 2013 中的外部使用者存取的憑證需求](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Lync Server 2013 中的憑證摘要 - DNS 與 HLB 負載平衡](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Lync Server 2013 中的憑證摘要 - 單一 Director](lync-server-2013-certificate-summary-single-director.md)

  - [Lync Server 2013 中的憑證摘要 - 調整式 Director 集區 (硬體負載平衡器)](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Lync Server 2013 中的憑證摘要 - 反向 Proxy](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [整合內部部署 Unified Messaging 和 Lync Server 2013 的指導方針](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

如需針對 Exchange 設定憑證的詳細資料，包括萬用字元的使用，請參閱 Exchange 2013 產品檔。

</div>

<span> </span>

</div>

</div>

</div>

