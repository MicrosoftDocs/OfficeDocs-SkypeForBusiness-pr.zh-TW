---
title: Lync Server 2013：設定反向 proxy 的憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c7a4e6ede9afe8d521d8dea3bd9350801588b90
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a>在 Lync Server 2013 中設定反向 proxy 的憑證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

每個反向 proxy 伺服器都需要一個網頁伺服器憑證，以供接聽服務使用。 網頁伺服器憑證必須由公用憑證授權單位單位 (CA) 所發行。

如需此和其他憑證需求的詳細資訊，請參閱[Lync Server 2013 中外部使用者存取的憑證需求](lync-server-2013-certificate-requirements-for-external-user-access.md)。

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a>設定反向 proxy 的 Web 服務憑證

  - 您應該已經設定反向 proxy （包括設定 Web 服務憑證）。 如果您在開始部署 Edge Server 之前未執行此動作，請使用[設定 Lync Server 2013 的反向 proxy 伺服器](lync-server-2013-setting-up-reverse-proxy-servers.md)中的程式來建立要求並安裝 web 服務憑證，然後建立每個 web 發佈規則，並將其設定為使用憑證。

</div>

</div>

<span> </span>

</div>

</div>

</div>

