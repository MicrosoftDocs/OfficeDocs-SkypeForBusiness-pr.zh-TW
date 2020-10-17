---
title: Lync Server 2013：通話駐留使用的元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21335597f0910e18a5afe36898c7d0eff6c1a338
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502390"
---
# <a name="components-used-by-call-park-in-lync-server-2013"></a>Lync Server 2013 中通話駐留所使用的元件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-13_

當您部署企業語音時，會自動安裝通話駐留應用程式。 您可以透過設定語音原則來啟用通話駐留。 下列 Lync Server 2013 元件支援通話駐留應用程式：

  - **應用程式服務**    Application service 提供平臺，用來部署、裝載和管理整合通訊應用程式，例如通話駐留應用程式。 應用程式服務會自動安裝在前端集區和每個 Standard Edition server 上的每一部前端伺服器上。

  - **通話駐留應用程式**    通話駐留應用程式是由應用程式服務主控的整合通訊應用程式之一。 當您部署企業語音時，會自動包含它。 通話駐留公園和檢索來電，並管理通話駐留軌道。

  - 以**音樂為開啟狀態的**     檔案如果啟用音樂，便會在停用通話時播放音樂檔。 安裝通話駐留應用程式時，會包含預設的音樂檔。

  - **檔存放區**    通話駐留應用程式會使用檔案存放區存放自訂音訊檔案。

  - **Lync Server 控制台**    您可以使用 Lync Server 控制台設定通話駐留軌道表格，並為使用者啟用通話駐留。

  - **Lync Server 管理命令**     介面您可以使用 Lync Server 管理命令介面 Cmdlet 來執行所有通話駐留應用程式設定。

</div>

<span> </span>

</div>

</div>

</div>

