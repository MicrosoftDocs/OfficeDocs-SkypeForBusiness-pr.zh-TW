---
title: Lync Server 2013：通話駐留所使用的元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64f74161230504ee3f24ed19780e0a62ad4e7d08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976120"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a>Lync Server 2013 中通話駐留所使用的元件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-13_

當您部署企業語音時，會自動安裝通話駐留應用程式。 您可以透過設定語音原則來啟用通話駐留。 下列 Lync Server 2013 元件支援通話駐留應用程式：

  - **應用程式服務**   應用程式服務提供部署、託管及管理整合通訊應用程式（例如通話駐留應用程式）的平臺。 應用程式服務會自動安裝在前端池的每個前端伺服器上，以及每個標準版伺服器上。

  - **通話駐留應用**   程式通話駐留應用程式是由應用程式服務託管的其中一個整合通訊應用程式。 當您部署企業語音時，系統會自動包含此檔案。 通話駐留公園並檢索來電，並管理通話駐留軌道式。

  - **[音樂封存-**   檔案] 如果 [啟用中的音樂]，音樂檔案會在通話暫停時播放。 安裝通話公園應用程式時，會包含預設的音樂檔案。

  - **檔案存放區**   通話駐留應用程式使用檔案存放區來儲存自訂音訊檔案。

  - **Lync server [控制台**   ] 您可以使用 lync server [控制台] 來設定 [通話駐留軌道] 表格，並為使用者啟用通話駐留。

  - **Lync server management shell**   ：您可以使用 lync server 管理命令介面 Cmdlet 來執行所有通話駐留應用程式設定。

</div>

<span> </span>

</div>

</div>

</div>

