---
title: Lync Server 2013：部署轉送伺服器及定義對等專案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b22a232bd304d4db3faae168f42dae11cea8fc4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507380"
---
# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a>在 Lync Server 2013 中部署轉送伺服器及定義對等專案

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

「企業語音工作負載」、電話撥入式會議和高級 Enterprise Voice 應用程式 (回應群組應用程式、通話駐留應用程式、通話許可控制 (CAC) ) 等）都可用於前端集區。 在 Lync Server 2013 中，轉送伺服器的功能會建入前端伺服器。 不再需要個別的獨立轉送伺服器。 前端集區可以直接與支援的閘道進行通訊 (公用交換電話網路 (PSTN) 閘道或 IP-PBX) ，移除轉送伺服器做為仲介的需求。

唯一例外情況是設定 SIP 主幹以連接至網際網路電話語音服務提供者的會話邊界控制器。 若要將您的企業語音基礎結構連線至 SIP 主幹提供者，則必須部署個別的轉送伺服器。

Lync Server (前端集區或獨立轉送伺服器上的轉送伺服器元件之間的連線) ，且閘道是定義為稱為 *主幹*的邏輯關聯。 本節中的主題說明如何定義主幹及如何在連接至 SIP 主幹時，部署獨立的轉送伺服器。

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 的拓撲產生器中定義轉送伺服器](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [在 Lync Server 2013 中的拓撲產生器中定義閘道](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [在 Lync Server 2013 中安裝轉送伺服器的檔案](lync-server-2013-install-the-files-for-mediation-server.md)

  - [在 Lync Server 2013 中的拓撲產生器中定義其他主幹](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a>相關各節

[在 Lync Server 2013 中設定電話撥入式會議](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

