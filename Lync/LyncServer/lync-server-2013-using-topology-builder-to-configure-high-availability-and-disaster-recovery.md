---
title: 使用拓撲產生器設定高可用性和災害復原
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73bcd2c2892e4e121512ae852d5920d600af91ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中使用拓撲產生器設定高可用性和災害復原

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

在拓撲建立器中執行下列步驟，以設定持久聊天伺服器的高可用性和災害復原。

1.  新增鏡像資料庫與記錄傳送次要資料庫 SQL Server 書店。

2.  編輯持續聊天伺服器的服務屬性至：
    
    1.  針對主要資料庫啟用鏡像。
    
    2.  新增主鏡像 SQL Server 存放區。
    
    3.  啟用 SQL Server 記錄傳送資料庫。
    
    4.  新增 SQL Server 記錄傳送的次要 SQL Server store。
    
    5.  為次要資料庫新增 SQL Server store 鏡像。
    
    6.  發佈拓撲。

</div>

<span> </span>

</div>

</div>

</div>

