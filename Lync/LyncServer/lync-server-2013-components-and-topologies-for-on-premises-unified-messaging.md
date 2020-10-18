---
title: Lync Server 2013：內部部署整合通訊的元件和拓撲
description: Lync Server 2013：內部部署整合通訊的元件和拓撲。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fe2ca16ec9fbd39e9245fd366e1f7046dd16d42
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576819"
---
# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a>Lync Server 2013 中內部部署整合通訊的元件和拓撲

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-25_

本主題說明將 Exchange 整合通訊 (UM) 功能提供給 Lync Server 2013 部署所需的 Microsoft Exchange Server 2013 元件。 此外，它也會說明內部部署 Exchange UM 整合所支援的拓撲。

<div>

## <a name="exchange-server-components"></a>Exchange Server 元件

若要提供 Exchange UM 功能和服務中所述的 [整合式整合通訊和 Lync Server 2013 的功能](lync-server-2013-features-of-integrated-unified-messaging.md) ，以及組織中的 Enterprise Voice 使用者，您必須部署 Microsoft Exchange 信箱伺服器和用戶端存取伺服器，該伺服器主控使用者信箱，並提供電子郵件及語音信箱的單一儲存位置。 Exchange UM 在 Exchange 信箱和用戶端存取伺服器上以服務的身分執行。

如需 Microsoft Exchange Server 2007 和 Microsoft Exchange Server 2010 中 Exchange UM 元件的詳細資訊，請參閱部署檔中的部署內部部署 [EXCHANGE UM，以提供 Lync Server 2013 語音信箱](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) 。

</div>

<div>

## <a name="supported-topologies"></a>支援的拓撲

您可以在相同樹系或多個樹系中部署 Lync Server 2013 和 Exchange 整合通訊 (UM) 。 如果部署跨越多個樹系，您必須針對每個 Exchange UM 樹系執行 Exchange 整合步驟。 此外，您必須將每個 Microsoft Exchange 樹系設定為信任 Lync Server 2013 樹系和 Lync Server 2013 樹系，以信任每個 Exchange UM 樹系。 除了此樹系信任之外，您必須在 Lync Server 2013 樹系中的使用者物件上設定所有使用者的 Exchange UM 設定。

Lync Server 2013 支援 Exchange UM 整合的下列拓撲：

  - 單一樹系

  - 單一網域 (亦即單一樹系搭配單一網域)。 Lync Server 2013、Microsoft Exchange 和使用者都位於相同的網域。

  - 多重網域 (亦即，一個根網域搭配一或多個子網域)。 Lync Server 2013 和 Microsoft Exchange 伺服器會從您建立使用者的網域部署在不同的網域中。 Exchange UM 伺服器可以從其支援的 Lync Server 2013 集區部署在不同的網域中。

  - 多重樹系 (亦即資源樹系)。 Lync Server 2013 是部署在單一樹系中，然後使用者分散在多個樹系中。 使用者的 Exchange UM 屬性必須複製到 Lync Server 2013 樹系。
    
    <div>
    

    > [!NOTE]  
    > Exchange 可以部署在多個樹系中。 每個 Exchange 組織都可以為其使用者提供 Exchange UM，也可以將 Exchange UM 部署在 Lync Server 2013 所在的相同樹系中。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

