---
title: Lync Server 2013：部署中繼伺服器並定義對等項目
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
ms.openlocfilehash: b20f5e733dddd34971ca3a5070e99364785e147a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a>在 Lync Server 2013 中部署中繼伺服器並定義對等項目

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

[企業語音工作]、[電話撥入式會議] 和 [高級企業語音應用程式] （回應群組應用程式、通話駐留應用程式、通話許可控制（CAC）等）都可在前端池中使用。 使用 Lync Server 2013，轉送伺服器的功能會內嵌在前端伺服器中。 不再需要個別獨立的中繼伺服器。 前端池可以直接與支援的閘道（公開交換式電話網絡（PSTN）閘道或 IP PBX）通訊，移除要作為仲介的中繼伺服器需求。

唯一的例外是如果您將 SIP 主幹設定為連線至網際網路電話服務提供者的會話框線控制器。 若要將企業語音結構連線至 SIP 中繼提供者，必須部署個別的中繼伺服器。

Lync Server （前端池或獨立中繼伺服器上的中繼伺服器元件）與閘道之間的連線，會定義為稱為*主幹*的邏輯關聯。 本節中的主題描述如何定義主幹，以及如果您連線到 SIP 主幹，如何部署獨立的中繼伺服器。

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 的拓撲產生器中定義中繼伺服器](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [在 Lync Server 2013 的拓撲產生器中定義閘道](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [在 Lync Server 2013 中安裝轉送服務伺服器的檔案](lync-server-2013-install-the-files-for-mediation-server.md)

  - [在 Lync Server 2013 的拓撲產生器中定義其他 trunks](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a>相關各節

[在 Lync Server 2013 中設定撥入會議](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

