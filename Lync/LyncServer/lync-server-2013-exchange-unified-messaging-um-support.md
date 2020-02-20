---
title: 'Lync Server 2013: Exchange 整合通訊 (UM) 支援'
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
ms.openlocfilehash: bd46b19ea52b56b70cc5bd4c459f2260a97306d8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a>Lync Server 2013 中的 Exchange 整合通訊 (UM) 支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-21_

Lync Server 2013 支援整合與 Exchange 整合通訊 (UM) 來合併語音訊息與電子郵件訊息到單一郵件基礎結構。 在 Exchange 2013 中，Exchange UM 所組成的 Exchange UM 服務，以安裝以及 Mailbox server 及 UM 呼叫路由器，以安裝，以及用戶端存取伺服器上，執行上執行。 針對 Lync Server 2013 Enterprise Voice 部署，請 Exchange UM 結合了語音訊息與電子郵件訊息到可從電話 （亦即，Outlook 語音存取） 或電腦存取的單一儲存區。 Exchange UM 和 Lync Server 2013 共同運作以提供自動答錄服務，Outlook Voice Access 和自動語音應答服務給 Enterprise Voice 的使用者。

除了以在內部部署 Exchange UM 整合的支援，Lync Server 2013 支援與裝載 Exchange UM 整合。 如果您將部分或所有的使用者移轉至裝載的 Exchange 服務提供者 (如 Microsoft Exchange Online)，這項支援可讓您提供語音訊息給使用者。

Lync Server 2013 支援下列版本：

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 （必要） 或最新的 service pack （建議使用）

  - Microsoft Exchange Server 2007 Service Pack 1 (SP1) （必要） 或最新的 service pack （建議）

您無法在 Exchange UM with Lync Server 2013 或 Lync Server 2013 資料庫組合。 您可以在不同樹系中安裝 Exchange UM 和 Lync Server 2013。

<div>


> [!NOTE]  
> Exchange UM 可能不需要有 PBX 部署，因為 PBX 可以繼續提供語音信箱和相關的服務給所有使用者的 Enterprise Voice 部署。 如果您最終淘汰 PBX （例如，如果您部署的公用交換的電話網路 (PSTN) 連線的 SIP 主幹），必須重新設定 Exchange UM to 先前已使用 PBX 語音信箱系統的使用者提供語音信箱。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 中整合通訊的內部部署的元件和拓撲](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [主控 Exchange UM 整合的 Lync Server 2013 中的支援](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

