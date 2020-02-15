---
title: Lync Server 2013： 發佈位置資料庫
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
ms.openlocfilehash: d524f8551561a4c7fb61abdaa6ab15bf2c111de9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-location-database-from-lync-server-2013"></a>發佈位置資料庫從 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-30_

您加入至位置資料庫的新位置將不會成為提供給用戶端之前已發佈。

如需詳細資訊，請參閱 < Lync Server 管理命令介面文件的下列 cmdlet:

  - **發佈 CsLisConfiguration**

如果您使用緊急位置識別號碼 (ELIN) 閘道，您也需要將 Elin 上傳至您的公用交換的電話網路 (PSTN) 電信業者的自動位置識別 (ALI) 資料庫。 您 PSTN 電信業者可能需要您使用 ELIN 記錄的特定格式。 如需詳細資訊，請連絡您 PSTN 電信業者。 您可以從位置資訊服務資料庫匯出記錄及它們格式化為必要。

<div>

## <a name="to-publish-the-location-database"></a>若要發佈位置資料庫

  - 啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

  - 執行下列 cmdlet 以發佈位置資料庫。
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

