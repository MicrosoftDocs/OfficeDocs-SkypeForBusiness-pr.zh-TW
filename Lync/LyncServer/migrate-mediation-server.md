---
title: 遷移轉送伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79fc35a7641b4acb42578ec4e75375e171ae905e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a>遷移轉送伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

當您執行 [合併] 嚮導時，您的中繼伺服器會合並到 Lync Server 2013 試驗拓撲。 您可以設定 Lync Server 2013 轉送伺服器，因為 Office 通訊伺服器 2007 R2 池無法與 Lync Server 2013 轉送伺服器通訊，所以在所有使用者都被遷移後。 在並行遷移期間，Lync Server 2013 pool 會與 Office 通訊伺服器 2007 R2 轉送伺服器通訊。

當您設定 Lync Server 2013 轉送服務伺服器時，您也必須升級或取代您的 Office 通訊伺服器 2007 R2 閘道。 Office 通訊伺服器 2007 R2 閘道不支援 Lync Server 2013 轉送伺服器。 您需要部署認證給 Lync Server 2013 的閘道，並將它們與 Lync Server 2013 轉送伺服器進行關聯。 您必須先執行此步驟，才能完全解除與您的 Office 通訊伺服器 2007 R2 部署。

本節中的主題描述在您完成 Lync Server 2013 轉送伺服器的遷移之後，您需要執行的設定任務。 將 collocated 中繼伺服器轉換成獨立的中繼伺服器是一個選用的工作。

  - [設定中繼伺服器](configure-mediation-server.md)

  - [變更語音路由以使用新的 Lync Server 2013 轉送服務伺服器](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [將 collocated 中繼伺服器轉換成獨立的中繼伺服器（選用）](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

