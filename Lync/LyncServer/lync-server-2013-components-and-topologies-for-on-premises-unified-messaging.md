---
title: Lync Server 2013：內部部署 Unified Messaging 的元件和拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdaf33a230f2663e9fc8b541aafb47c362d0ac97
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a>Lync Server 2013 中內部部署 Unified Messaging 的元件和拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-25_

本主題說明將 Exchange 整合通訊（UM）功能提供給 Lync Server 2013 部署所需的 Microsoft Exchange Server 2013 元件。 它也會說明內部部署 Exchange UM 整合所支援的拓撲。

<div>

## <a name="exchange-server-components"></a>Exchange Server 元件

若要提供整合式整合[訊息和 Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md)在您組織中的企業語音使用者所描述的 Exchange UM 功能與服務，您必須部署 Microsoft Exchange 信箱伺服器和用戶端存取伺服器（其主機使用者信箱），並提供電子郵件和語音信箱的單一儲存位置。 Exchange UM 在 Exchange 信箱和用戶端存取伺服器上以服務的方式執行。

如需 Microsoft Exchange Server 2007 和 Microsoft Exchange Server 2010 中 Exchange UM 元件的詳細資訊，請參閱[部署內部部署 EXCHANGE UM，以在部署檔中提供 Lync Server 2013 語音信箱](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)。

</div>

<div>

## <a name="supported-topologies"></a>支援的拓撲

您可以在同一個目錄林中或多個目錄林中部署 Lync Server 2013 和 Exchange 整合通訊（UM）。 如果部署跨越多個目錄林，您必須針對每個 Exchange UM 目錄林執行 Exchange 整合步驟。 此外，您必須將每個 Microsoft Exchange 林設定為信任 Lync Server 2013 林以及 Lync Server 2013 林，以信任每個 Exchange UM 目錄林。 除了此目錄林信任之外，所有使用者的 Exchange UM 設定都必須在 Lync Server 2013 林中的使用者物件上設定。

Lync Server 2013 支援適用于 Exchange UM 整合的下列拓朴：

  - 單一目錄林

  - 單一網域（也就是單一網域的單一林）。 Lync Server 2013、Microsoft Exchange 和使用者都位於同一個網域中。

  - 多個網域（也就是包含一或多個子域的根網域）。 Lync Server 2013 和 Microsoft Exchange 伺服器會從您建立使用者的網域部署在不同的網域中。 Exchange UM 伺服器可從其支援的 Lync Server 2013 池部署到不同的網域。

  - 多個目錄林（也就是資原始目錄林）。 Lync Server 2013 是在單一目錄林中部署，而使用者則是跨多個目錄林分佈。 使用者的 Exchange UM 屬性必須複製到 Lync Server 2013 林。
    
    <div>
    

    > [!NOTE]  
    > Exchange 可以在多個林中部署。 每個 Exchange 組織都可以為其使用者提供 Exchange UM，或者 Exchange UM 可以部署在 Lync Server 2013 所在的林中。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

