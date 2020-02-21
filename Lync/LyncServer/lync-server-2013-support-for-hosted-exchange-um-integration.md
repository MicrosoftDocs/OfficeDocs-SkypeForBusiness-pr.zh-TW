---
title: 主控 Exchange UM 整合的 Lync Server 2013 支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89c87de9c57abaf4938b350aa40e8deea1150d22
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a>主控 Exchange UM 整合的 Lync Server 2013 中的支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-21_

Lync Server 2013 ExUM Routing 應用程式在內部部署環境中，Lync Server 2013 與 Exchange UM 已同時安裝在本機上您企業內或使用 [Exchange UM 所主控支援整合與 Exchange 整合通訊 (UM)服務提供者，如下圖所示。

![內部部署 Lync Server Exchange UM 部署](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "內部部署 Lync Server Exchange UM 部署")

支援下列模式：

  - **內部模式**   Lync Server 2013 和 Exchange UM 都部署於您企業內的本機伺服器上。

  - **跨部署模式**   Lync Server 2013 部署在您企業內的本機伺服器上，而 Exchange UM 裝載於線上服務提供者的設備，例如 Microsoft Exchange 線上資料中心。

  - **使用混合模式**   您的 Lync Server 2013 部署中，有一些使用者信箱位於執行 Microsoft Exchange Server，在您的企業和部分信箱位於託管式 Exchange 服務資料中心的本機伺服器。
    
    <div>
    

    > [!NOTE]  
    > 混合的模式可當作過渡時期解決方案期間評估及逐步移轉使用者至裝載的 Exchange UM，或當作永久解決方案如果您選擇將某些使用者的 Exchange UM 服務內部之後移轉其他人。

    
    </div>

若要與裝載 Exchange UM 整合 Lync Server 2013，您必須設定*共用的 SIP 位址空間*（也稱為*分割網域*）。 在此組態中，Lync Server 2013 和協力廠商主控的 Exchange UM 服務提供者可以存取相同的 SIP 網域位址空間。 如需詳細資訊，請參閱[主控 Exchange UM 整合架構 Lync Server 2013 中的](lync-server-2013-hosted-exchange-um-integration-architecture.md)規劃文件。

</div>

<span> </span>

</div>

</div>

</div>

