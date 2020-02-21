---
title: Lync Server 2013： 的元件和拓撲內部部署整合通訊
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
ms.openlocfilehash: a21f24e87f889213a92123886a871dd1f5209ed1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208099"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a>Lync Server 2013 中整合通訊的內部部署的元件和拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-25_

本主題說明提供 Lync Server 2013 部署的 Exchange 整合通訊 (UM) 功能所需的 Microsoft Exchange Server 2013 元件。 它也說明內部部署 Exchange UM 整合支援的拓撲。

<div>

## <a name="exchange-server-components"></a>Exchange Server 元件

若要提供給您組織中的 Enterprise Voice 使用者所述[的整合式 Unified Messaging 和 Lync Server 2013 功能](lync-server-2013-features-of-integrated-unified-messaging.md)服務與 Exchange UM 功能，您必須部署 Microsoft Exchange 信箱伺服器和用戶端存取伺服器，裝載使用者信箱，並提供單一的儲存位置的電子郵件及語音信箱。 Exchange UM 以服務方式執行 Exchange 信箱與用戶端存取伺服器上。

如需 Microsoft Exchange Server 2007 與 Microsoft Exchange Server 2010 中 Exchange UM 元件的詳細資訊，請參閱部署文件中的[部署內部部署 Exchange UM 以提供 Lync Server 2013 語音信箱](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)。

</div>

<div>

## <a name="supported-topologies"></a>支援的拓撲

您可以部署 Lync Server 2013 和 Exchange 整合通訊 (UM) 在相同的樹系或多個樹系中。 如果部署跨越多個樹系，您必須針對每個 Exchange UM 樹系執行 Exchange 整合步驟。 此外，您必須設定為信任的 Lync Server 2013 樹系的每個 Microsoft Exchange 樹系和 Lync Server 2013 樹系信任每個 Exchange UM 樹系。 除了此樹系信任，必須在 Lync Server 2013 樹系中的使用者物件上設定的所有使用者的 Exchange UM 設定。

Lync Server 2013 的 Exchange UM 整合支援下列拓撲：

  - 單一樹系

  - 單一網域 (亦即單一樹系搭配單一網域)。 Lync Server 2013、 Microsoft Exchange 和位於相同網域中所有的使用者。

  - 多重網域 (亦即，一個根網域搭配一或多個子網域)。 從您在其中建立使用者的網域不同網域中部署 Lync Server 2013 和 Microsoft Exchange 伺服器。 可以從其所支援的 Lync Server 2013 集區不同網域中部署 Exchange UM 伺服器。

  - 多重樹系 (亦即資源樹系)。 Lync Server 2013 部署在單一樹系中，並再將使用者分配到多個樹系。 Exchange UM 使用者的屬性必須透過複寫到 Lync Server 2013 的樹系。
    
    <div>
    

    > [!NOTE]  
    > Exchange 可以部署在多個樹系中。 每個 Exchange 組織可以 Exchange UM 提供給其使用者，或 Exchange UM 可以在 Lync Server 2013 相同的樹系中部署。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

