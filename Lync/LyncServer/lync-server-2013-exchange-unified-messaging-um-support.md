---
title: Lync Server 2013： Exchange 整合通訊 (UM) 支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac42e46bf92e7fa170ee3dff059edc1b5871aafd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533120"
---
# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a>Lync Server 2013 中的 Exchange 整合通訊 (UM) 支援

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

Lync Server 2013 支援與 Exchange 整合通訊 (UM) 整合，以結合語音訊息與電子郵件訊息到單一郵件基礎結構。 在 Exchange 2013 中，Exchange UM 包含在信箱伺服器上安裝和執行的 Exchange UM 服務，以及在用戶端存取伺服器上安裝並執行的 UM 呼叫路由器。 針對 Lync Server 2013 Enterprise Voice 部署，Exchange UM 會將語音訊息與電子郵件合併到單一存放區，而該儲存體可以從電話 (，也就是 Outlook Voice Access) 或電腦。 Exchange UM 和 Lync Server 2013 共同合作，為 Enterprise Voice 的使用者提供呼叫回應、Outlook Voice Access 和自動語音應答服務。

除了支援與 Exchange UM 內部部署的整合之外，Lync Server 2013 也支援與主控 Exchange UM 的整合。 如果您將部分或所有的使用者移轉至裝載的 Exchange 服務提供者 (如 Microsoft Exchange Online)，這項支援可讓您提供語音訊息給使用者。

Lync Server 2013 支援下列版本：

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 (必要) 或 (建議的最新 service pack) 

  - Microsoft Exchange Server 2007 Service Pack 1 (SP1) 所需 () 或最新的 service pack (建議) 

您無法組合 Exchange UM 與 Lync Server 2013 或 Lync Server 2013 資料庫。 您可以在不同的樹系中安裝 Exchange UM 和 Lync Server 2013。

<div>


> [!NOTE]  
> Exchange UM 可能不需要部署 PBX 的 Enterprise Voice 部署，因為 PBX 可以繼續為所有使用者提供語音信箱和相關服務。 如果您最後淘汰 PBX (例如，如果您在部署公用交換電話網路的 SIP 主幹 (PSTN) 連線) ，您必須重新設定 Exchange UM，以將語音信箱提供給先前使用 PBX 語音信箱系統的使用者。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中內部部署整合通訊的元件和拓撲](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [Lync Server 2013 中的主控 Exchange UM 整合支援](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

