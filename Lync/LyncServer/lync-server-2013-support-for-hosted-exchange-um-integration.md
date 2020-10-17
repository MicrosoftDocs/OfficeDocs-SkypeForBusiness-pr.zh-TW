---
title: Lync Server 2013 支援主控 Exchange UM 整合
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
ms.openlocfilehash: 3ebc49336712e96bca428132f3ccad631817208d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524170"
---
# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a>Lync Server 2013 中的主控 Exchange UM 整合支援

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

Lync Server 2013 ExUM 路由應用程式可在內部部署環境中與 Exchange 整合通訊 (UM) 進行整合，其中，Lync Server 2013 和 Exchange UM 皆安裝于您企業內的本機，或 Exchange UM 是由服務提供者所主控，如下圖所示。

![內部部署 Lync Server Exchange UM 部署](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "內部部署 Lync Server Exchange UM 部署")

支援下列模式：

  - **內部部署模式**    Lync Server 2013 和 Exchange UM 都部署于您企業內的本機伺服器上。

  - **跨部署模式**    Lync Server 2013 部署于您企業內的本機伺服器上，而 Exchange UM 是以線上服務提供者的功能（例如 Microsoft Exchange Online 資料中心）主控。

  - **混合模式**    您的 Lync Server 2013 部署中有一些使用者信箱位於執行 Microsoft Exchange Server 內部的本機伺服器上，而部分信箱位於裝載的 Exchange 服務資料中心。
    
    <div>
    

    > [!NOTE]  
    > 混合模式可以做為進行評估和逐步遷移至主控 Exchange UM 時的過渡方案，如果您選擇在遷移其他使用者後，將某些使用者的 Exchange UM 服務保留在內部部署，則可以做為永久解決方案。

    
    </div>

若要整合 Lync Server 2013 與主控 Exchange UM，您必須設定 *共用 SIP 位址空間* ， (也稱為 *分割網域*) 。 在此設定中，Lync Server 2013 和協力廠商託管的 Exchange UM 服務提供者可以存取相同的 SIP 網域位址空間。 如需詳細資訊，請參閱規劃檔中的 [主控 EXCHANGE UM 整合架構（Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) ）。

</div>

<span> </span>

</div>

</div>

</div>

