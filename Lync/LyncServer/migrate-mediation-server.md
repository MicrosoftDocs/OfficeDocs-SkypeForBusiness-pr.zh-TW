---
title: 移轉中繼伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 581ce96b0c0a6ad0e4edd68eddbfacb160bf13f1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a>移轉中繼伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-28_

中繼伺服器已合併到 Lync Server 2013 試驗拓撲，當您執行合併列印精靈。 您設定 Lync Server 2013 中繼伺服器，不過之後所有的使用者完成移轉，因為 Office Communications Server 2007 R2 集區無法與 Lync Server 2013 中繼伺服器進行通訊。 並排顯示在移轉期間，與 Office Communications Server 2007 R2 中繼伺服器進行通訊的 Lync Server 2013 集區。

當您設定您的 Lync Server 2013 中繼伺服器時，您也必須升級，或取代 Office Communications Server 2007 R2 閘道。 Office Communications Server 2007 R2 閘道不支援 Lync Server 2013 中繼伺服器。 您必須部署 Lync Server 2013 的認證，並與 Lync Server 2013 中繼伺服器產生關聯的閘道。 您可以完全解除委任 Office Communications Server 2007 R2 部署之前，則需要此步驟。

本節主題說明您需要執行完成之後，您的 Lync Server 2013 中繼伺服器移轉的組態工作。 轉換成獨立中繼伺服器組合的中繼伺服器是選用的工作。

  - [設定中繼伺服器](configure-mediation-server.md)

  - [變更語音路由以使用新的 Lync Server 2013 中繼伺服器](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [組合式的中繼伺服器轉換成獨立中繼伺服器 （選用）](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

