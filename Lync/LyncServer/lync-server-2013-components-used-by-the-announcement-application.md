---
title: 宣告應用程式所使用的 Lync Server 2013： 元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a888ca21e26a21103d1c45e74518c3d224d18a7b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013 中的宣告應用程式所使用的元件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-13_

在 Lync Server 2013 中，宣告應用程式是回應群組應用程式的元件。 當您部署企業語音時，宣告應用程式會自動安裝及啟動以及回應群組應用程式。 本節說明支援宣告應用程式的元件。

<div>

## <a name="announcement-application-components"></a>宣告應用程式元件

宣告應用程式支援下列的 Lync Server 元件：

  - **應用程式服務**   應用程式服務提供的平台的部署，裝載，及管理整合通訊應用程式。 在每個前端伺服器上的前端集區中，每個 Standard Edition server 上，會自動安裝應用程式服務。

  - **回應群組應用程式**   回應群組應用程式是下列其中一個裝載的應用程式服務的整合的通訊應用程式。 當設定未指派的電話號碼範圍來路由傳送的通知，回應群組應用程式，才能路由傳送至電話號碼所進行的呼叫。 (如果已設定所有的範圍，不需要回應群組應用程式來路由傳送至 Exchange 整合通訊 (UM)。)

  - **音訊檔案**   音訊檔案用於宣告。

  - **檔案存放區**   宣告應用程式使用檔案存放區儲存其音訊檔。

  - **Lync Server Control Panel**   您可以使用 Lync Server 控制台來設定未指派號碼表。

  - **Lync Server 管理命令介面**   您可以使用 Lync Server 管理命令介面 cmdlet 來設定宣告設定和未指派號碼表。

</div>

</div>

<span> </span>

</div>

</div>

</div>

