---
title: Lync Server 2013：決定 Microsoft Lync 的部署方式
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
ms.openlocfilehash: aef6ac76b6c0e8a6fb3c0444ab219acf78119ecd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a>決定 Lync Server 2013 的部署方式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

規劃 Lync 時，第一個主要決定是如何部署 Microsoft Lync：在內部部署中使用 Lync Server 2013，或在雲端使用 Microsoft Office 365 的 Lync Online。

  - **Lync Server 2013 內部部署**：此選項提供完整的 Lync 功能集，並提供設定、自訂及操作您的部署的絕佳靈活性。 所有伺服器都安裝在現場，且由您的組織維護。 內部部署部署提供完整的 Lync 伺服器功能。

  - **雲端中的 Lync Online**Lync Online 是專為想要以雲端為基礎的立即訊息、目前狀態及會議帶來成本與靈活性效益而設計，而不會犧牲 Lync Server 的企業級功能。 在 Lync Online 中，Microsoft 會部署並維護所需的伺服器基礎結構，並處理持續進行的維護、修補程式和升級。 在 Lync Online 中，內部部署中提供的部分功能無法使用。

最適合您的部署類型，取決於您要部署的工作負載，以及貴組織的地理位置與業務狀態。

<div>

## <a name="lync-server"></a>Lync Server

內部部署 Lync Server 部署最適合下列案例：

  - **完整的企業語音功能**   如果您打算部署完整的企業語音解決方案來取代 PBX 或使用高級通話功能，則需要內部部署 Lync Server 部署。 內部部署支援與 PBX 系統與 trunks 的直接連線，以及 [回應群組] 和 [通話駐留] 等高級電話功能。 Lync Online 目前不支援這些功能。

  - **媒體質量控制**   如果您想要完整的多媒體品質保證功能（例如 [呼叫許可控制] （CAC）和 [服務品質（QoS）] 功能），您需要內部部署。

  - **持續聊天**   如果您需要為貴組織部署持續聊天，您必須選擇內部部署。

  - **協力廠商伺服器應用程式**   只有內部部署部署才能搭配使用 Microsoft 整合通訊 Managed API （UCMA）的受信任的協力廠商應用程式。

  - ****    如果您在多個國家或地區中有資料中心，且需要在地區性基礎上部署和管理伺服器，則需要地區支援的多國國家/地區公司（內部部署）最佳，因為它提供了這種類型的地區管理功能。

  - **使用內部部署 Lync Server 部署來完全控制原則、報告和升級**   ，您可以存取完整的伺服器和用戶端原則、監控及其他報告，以及升級的時間。 Lync Online 提供原則設定和報告的子集，並提供有限但重要的視窗來接受升級。

</div>

<div>

## <a name="lync-online"></a>Lync Online

如果前面清單中的任何一個要素對您而言都不重要，您可能會想要選擇 Lync Online，以簡化部署和易管理性。 Lync Online 可提供強健的 IM、目前狀態及會議功能集，同時也能在您組織中的使用者之間使用語音和視頻通話。

</div>

</div>

<span> </span>

</div>

</div>

</div>

