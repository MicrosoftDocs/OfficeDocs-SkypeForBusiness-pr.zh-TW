---
title: 移轉中繼伺服器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87d1e9eaee83f4db6c1ca30cd143d62d45852988
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527520"
---
# <a name="migrate-mediation-server"></a>移轉中繼伺服器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

當您執行 [合併] 嚮導時，您的轉送伺服器會合並至您的 Lync Server 2013 試驗拓撲。 您可以設定 Lync Server 2013 轉送伺服器，但在遷移所有使用者之後，因為 Office 通訊伺服器 2007 R2 集區無法與 Lync Server 2013 轉送伺服器進行通訊。 在並列遷移期間，Lync Server 2013 集區會與 Office 通訊伺服器 2007 R2 轉送伺服器進行通訊。

當您設定 Lync Server 2013 轉送伺服器時，您也必須升級或取代您的 Office 通訊伺服器 2007 R2 閘道。 Office 通訊伺服器 2007 R2 閘道不支援 Lync Server 2013 轉送伺服器。 您需要部署已驗證 Lync Server 2013 的閘道，並與 Lync Server 2013 轉送伺服器建立關聯。 您必須先執行此步驟，才能完全解除您的 Office 通訊伺服器 2007 R2 部署。

本節中的主題說明在完成 Lync Server 2013 轉送伺服器的遷移後，需要執行的設定工作。 將組合的轉送伺服器轉換成獨立的轉送伺服器是選用的任務。

  - [設定轉送伺服器](configure-mediation-server.md)

  - [變更語音路由以使用新的 Lync Server 2013 轉送伺服器](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [將組合的轉送伺服器轉換成獨立轉送伺服器 (選用) ](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

