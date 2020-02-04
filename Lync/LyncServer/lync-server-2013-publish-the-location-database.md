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
ms.openlocfilehash: d4e42d73a5b7ac36439aca673ff68c03cc13f50f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-location-database-from-lync-server-2013"></a>從 Lync Server 2013 發佈位置資料庫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-30_

您新增至位置資料庫的新位置將不會提供給用戶端，直到它們發佈為止。

如需詳細資訊，請參閱適用于下列 Cmdlet 的 Lync Server 管理命令介面檔：

  - **發佈-CsLisConfiguration**

如果您使用緊急位置身分識別號碼（ELIN）閘道，您也需要將 ELINs 上傳到您的公用交換電話網絡 您的 PSTN 載波可能會要求您針對 ELIN 記錄使用特定的格式。 如需詳細資訊，請與您的 PSTN 運營商聯繫。 您可以從位置資訊服務資料庫匯出記錄，並根據需要設定其格式。

<div>

## <a name="to-publish-the-location-database"></a>發佈位置資料庫

  - 啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

  - 執行下列 Cmdlet 來發佈位置資料庫。
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

