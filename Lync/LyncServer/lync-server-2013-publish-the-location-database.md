---
title: Lync Server 2013：發佈位置資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 481a8406eeeec6fce25c19336519c4a9bf19da82
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512370"
---
# <a name="publish-the-location-database-from-lync-server-2013"></a>從 Lync Server 2013 發佈位置資料庫

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-30_

在發佈之前，您新增至位置資料庫的新位置將不會供用戶端使用。

如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：

  - **Export-cslisconfiguration 發佈**

如果您使用緊急位置識別號碼 (ELIN) 閘道，您也必須將 Elin 上傳至您公用交換電話網路 (PSTN) 電信公司的自動位置識別， (阿裡) 資料庫。 您的 PSTN 電信公司可能需要使用特定的 ELIN 記錄格式。 如需詳細資訊，請與您的 PSTN 電信公司聯繫。 您可以匯出位置資訊服務資料庫中的記錄，並視需要進行格式化。

<div>

## <a name="to-publish-the-location-database"></a>發佈位置資料庫

  - 啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

  - 執行下列 Cmdlet 來發佈位置資料庫。
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

