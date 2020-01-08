---
title: Lync Server 2013：Exchange Unified Messaging (UM) 支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8c952ed8aa407e2a4cbc836372c9238d4888572
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40973984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a>Lync Server 2013 中的 Exchange Unified Messaging (UM) 支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

Lync Server 2013 支援與 Exchange 整合通訊（UM）整合，以將語音訊息和電子郵件訊息結合到單一訊息基礎結構。 在 Exchange 2013 中，Exchange UM 是由 Exchange UM 服務（在信箱伺服器上安裝並執行），以及在用戶端存取伺服器上安裝並執行的 UM 呼叫路由器所組成。 針對 Lync Server 2013 企業版語音部署，Exchange UM 將語音訊息和電子郵件訊息結合成可從電話（也就是 Outlook 語音存取）或電腦存取的單一商店。 Exchange UM 和 Lync Server 2013 共同合作，為企業語音的使用者提供呼叫應答、Outlook 語音存取及自動語音應答服務。

除了支援與 Exchange UM 內部部署的整合之外，Lync Server 2013 還支援與託管 Exchange UM 的整合。 這可讓您在將部分或所有專案遷移至託管 Exchange 服務供應商（例如 Microsoft Exchange Online）時提供語音訊息給您的使用者。

Lync Server 2013 支援下列版本：

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 （必要）或最新 service pack （建議使用）

  - Microsoft Exchange Server 2007 Service Pack 1 （SP1）（必要）或最新的 service pack （建議使用）

您無法 collocate 與 Lync Server 2013 或 Lync Server 2013 資料庫的 Exchange UM。 您可以在不同的林中安裝 Exchange UM 和 Lync Server 2013。

<div>


> [!NOTE]  
> Exchange UM 可能不是部署 PBX 之企業語音部署所需的，因為 PBX 可以繼續為所有使用者提供語音信箱和相關服務。 如果您最後是淘汰 PBX （例如，如果您要為公用交換電話網絡（PSTN）連線）部署 SIP 中繼，您必須重新設定 Exchange UM，才能向先前使用 PBX 語音信箱系統的使用者提供語音信箱。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [Lync Server 2013 中內部部署 Unified Messaging 的元件和拓撲](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [Lync Server 2013 中的主控 Exchange UM 整合支援](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

