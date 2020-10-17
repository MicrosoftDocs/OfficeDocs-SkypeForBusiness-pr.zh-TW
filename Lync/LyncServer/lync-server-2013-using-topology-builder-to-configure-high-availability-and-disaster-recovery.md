---
title: 使用拓撲產生器來設定高可用性和嚴重損壞修復
description: 使用拓撲產生器來設定高可用性和嚴重損壞修復。
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
ms.openlocfilehash: 04764a58ac3ae1bbe0df97aadeabb03158ce8100
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547319"
---
# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中使用拓撲產生器來設定高可用性和嚴重損壞修復

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

在拓撲產生器中執行下列步驟，以設定 Persistent Chat Server 的高可用性和嚴重損壞修復。

1.  新增鏡像資料庫和記錄傳送次要資料庫 SQL Server 儲存區。

2.  編輯 Persistent Chat Server 服務屬性，使其：
    
    1.  啟用主資料庫的鏡像。
    
    2.  新增主要鏡像 SQL Server 儲存區。
    
    3.  啟用 SQL Server 記錄傳送資料庫。
    
    4.  新增 SQL Server 記錄傳送次要 SQL Server 儲存區。
    
    5.  新增次要資料庫的 SQL Server 儲存區鏡像。
    
    6.  發行拓撲。

</div>

<span> </span>

</div>

</div>

</div>

