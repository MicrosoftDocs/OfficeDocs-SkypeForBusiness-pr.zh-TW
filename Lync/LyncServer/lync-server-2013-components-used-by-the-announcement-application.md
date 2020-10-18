---
title: Lync Server 2013：宣告應用程式所使用的元件
description: Lync Server 2013：宣告應用程式所使用的元件。
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
ms.openlocfilehash: e5338ad097c814d5c6435bd89dbf7cfa8680feb8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577689"
---
# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013 的宣告應用程式所使用的元件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-13_

在 Lync Server 2013 中，宣告應用程式是回應群組應用程式的元件。 當您部署企業語音時，會自動安裝宣告應用程式，並隨回應群組應用程式一起啟用。 本節說明支援宣告應用程式的元件。

<div>

## <a name="announcement-application-components"></a>宣告應用程式元件

下列 Lync Server 元件支援宣告應用程式：

  - **應用程式服務**    Application service 提供平臺，用以部署、裝載和管理整合通訊應用程式。 應用程式服務會自動安裝在前端集區和每個 Standard Edition server 上的每一部前端伺服器上。

  - **回應群組應用程式**    回應群組應用程式是由應用程式服務主控的整合通訊應用程式之一。 當未指派的電話號碼範圍設定為路由傳送至宣告時，需要回應群組應用程式，才能將撥打給電話號碼的電話傳送給電話號碼。 如果所有範圍都設定為路由傳送至 Exchange 整合通訊 (UM) ，則不需要 (回應群組應用程式。 ) 

  - **音訊檔**    音訊檔案用於宣告。

  - **檔存放區**    宣告應用程式會使用檔案存放區儲存其音訊檔。

  - **Lync Server 控制台**    您可以使用 Lync Server 控制台設定未指派的號碼表。

  - **Lync Server 管理命令**     介面您可以使用 Lync Server 管理命令介面 Cmdlet 來設定宣告設定及未指派號碼表格。

</div>

</div>

<span> </span>

</div>

</div>

</div>

