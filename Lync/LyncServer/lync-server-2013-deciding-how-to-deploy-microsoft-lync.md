---
title: Lync Server 2013：決定如何部署 Microsoft Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f31a765d6b682e504839aa24962356f5524801d0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516520"
---
# <a name="deciding-how-to-deploy-lync-server-2013"></a>決定如何部署 Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

在規劃 Lync 時，第一個主要決定是如何部署 Microsoft Lync：在內部部署上使用 Lync Server 2013，或在雲端使用 Microsoft 365 或 Office 365 的 Lync Online。

  - **Lync Server 2013 內部部署** ：此選擇提供完整的 Lync 功能集，並提供設定、自訂及作業部署的最佳靈活性。 所有伺服器皆安裝於現場，且由您的組織來維護。 內部部署部署提供 Lync Server 功能的完整範圍。

  - **雲端中的 Lync Online** Lync Online 是專為需要雲端式立即訊息、目前狀態和會議的成本和靈活性優勢所設計的組織，而不會犧牲 Lync Server 的商務類別功能。 在 Lync Online 中，Microsoft 會部署及維護必要的伺服器基礎結構，並處理即時維護、修補程式和升級。 Lync Online 中無法使用內部部署中所提供的部分功能。

您最適合的部署類型取決於您想要部署的工作負載，及組織的地理位置和業務狀態。

<div>

## <a name="lync-server"></a>Lync Server

內部部署的 Lync Server 部署最適合下列案例：

  - **完整的 Enterprise Voice 功能**    如果您計畫部署完整的企業語音解決方案以取代 PBX 或使用高級通話功能，則需要內部部署 Lync Server 部署。 內部部署支援與 PBX 系統和主幹的直接連線能力，以及高級電話功能（如回應群組和通話駐留）。 Lync Online 目前不支援這些功能。

  - **媒體質量控制**    如果您想要完整範圍的媒體品質保證功能（例如通話許可控制） (CAC) 和服務品質 (QoS) 功能，則會需要內部部署。

  - **Persistent 聊天**    如果您需要為組織部署持續性聊天，您必須選擇內部部署。

  - **協力廠商伺服器應用程式**    只有內部部署可以搭配使用 Microsoft 整合通訊 Managed API (UCMA) 的受信任協力廠商應用程式。

  - **需要區域支援的多國/多地區性公司**    如果您有多個國家或地區的資料中心，且需要以地區性為基礎部署和管理伺服器，則內部部署的部署最佳，因為它會提供這種類型的區域管理功能。

  - **完全控制原則、報告和升級**    使用內部部署 Lync Server 部署，您可以存取完整的伺服器和用戶端原則集合、監控和其他報告，以及升級的時間。 Lync Online 提供原則設定與報告的子集，並提供有限但有意義的視窗，可接受升級。

</div>

<div>

## <a name="lync-online"></a>Lync Online

如果對您而言，前述清單中沒有任何重要因素，則您可能會想要選擇 Lync Online 以擁有部署和管理上的簡易性。 Lync Online 可提供強健的 IM、顯示狀態和會議功能集，也可讓您組織中使用者間的語音和影片通話。

</div>

</div>

<span> </span>

</div>

</div>

</div>
