---
title: Lync Server 2013：混合式和分割網域自動探索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fca0097f6ad0264755dd9d0a80a296e9ebf60b9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a>Lync Server 2013 中的混合式和分割網域自動探索

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-14_

共用 SIP 位址空間（也稱為*分割網域*部署或*混合*式部署）是一種設定，可讓使用者在內部部署部署和線上環境中部署。 想要的結果是讓使用者不論其主伺服器位於何處 (內部部署或線上) ，登入部署並重新導向至其主伺服器位置。 為了達到此目的，Lync Server 2013 的自動探索功能是用來將線上使用者重新導向至線上拓撲。 您可以使用 Lync Server 管理命令介面、 **Get-CsHostingProvider** Cmdlet 和 get-cshostingprovider 指令程式，**設定**自動探索統一資源定位器 (URL) 。

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>分割網域部署的行動性

您需要收集和記錄下列部署的屬性：

  - 從 Lync Server 管理命令介面中，輸入
    
        Get-CsHostingProvider

  - 在結果中尋找具有 **ProxyFQDN** 屬性的線上提供者。 例如，sipfed.online.lync.com。

  - 記錄 ProxyFQDN 的值。

  - 在內部部署的 Lync Server 控制台中啟用同盟，允許與線上提供者同盟。

  - 為線上提供者啟用同盟。 根據預設，所有的線上使用者都會啟用網域同盟，而且可以與所有網域通訊。

  - 如果您會定義封鎖和允許的網域，請決定您要明確允許或明確封鎖的網域。

  - 若要使用線上同盟，您必須規劃防火牆例外狀況、憑證和 DNS 主機 (A 或 AAAA （如果使用 IPv6) 記錄）。 此外，您必須設定同盟原則。 如需詳細資訊，請參閱[規劃 Lync Server 2013 和 Office 通訊伺服器同盟](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

