---
title: Lync Server 2013 主控 Exchange UM 整合支援
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
ms.openlocfilehash: 24139ad5294bf908a85b797300397fa8b2ac9140
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a>Lync Server 2013 中的主控 Exchange UM 整合支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

Lync Server 2013 ExUM 路由應用程式支援在內部部署環境中與 Exchange 整合通訊（UM）整合，其中 Lync Server 2013 與 Exchange UM 都安裝在您的企業內部，或由 a 託管的 Exchange UM服務提供者，如下圖所示。

![內部部署 Lync Server Exchange UM 部署](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "內部部署 Lync Server Exchange UM 部署")

支援下列模式：

  - **[內部部署模式]**   Lync Server 2013 和 Exchange UM 都部署在企業中的本機伺服器上。

  - **[跨內部部署模式]**   Lync Server 2013 是在企業內部的本機伺服器上部署，Exchange UM 是在線上服務提供者的功能（例如 Microsoft Exchange online 資料中心）中託管。

  - **混合模式**   您的 Lync Server 2013 部署會有一些使用者信箱駐留在您企業內部的本機伺服器上，而某些信箱則駐留在託管 Exchange 服務資料中心。
    
    <div>
    

    > [!NOTE]  
    > 您可以在評估與 stepwise 使用者遷移至託管 Exchange UM 的過程中，將混合模式做為過渡式解決方案，或者，如果您選擇在遷移其他使用者的 Exchange UM 服務之後，就將它保留為永久方案。

    
    </div>

若要整合 Lync Server 2013 與託管 Exchange UM，您必須設定*共用的 SIP 位址空間*（也稱為*分割網域*）。 在此設定中，Lync Server 2013 和協力廠商託管的 Exchange UM 服務提供者都可以存取相同的 SIP 網域位址空間。 如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中託管 EXCHANGE UM 整合架構](lync-server-2013-hosted-exchange-um-integration-architecture.md)。

</div>

<span> </span>

</div>

</div>

</div>

