---
title: 驗證配置設定的複製
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Validate replication of configuration settings
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205042(v=OCS.15)
ms:contentKeyID: 48184663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cde1f3a96f249e98bc4e48c2e6d9c40adaad526
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-replication-of-configuration-settings"></a>驗證配置設定的複製

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

您可以在中央管理儲存所在的內部電腦上執行 Lync Server 2013 **CsManagementStoreReplicationStatus** Cmdlet，或在已安裝 lync Server 2013 核心元件的任何加入網域的電腦上執行 lync server，以驗證將配置資訊複製到 Edge 伺服器。

初始結果可能會指出狀態為「False」，而不是「True」以進行複製。 如果是，請執行**CsManagementStoreReplication** Cmdlet，並允許複製完成時間，然後再次執行**CsManagementStoreReplicationStatus** Cmdlet。

</div>

<span> </span>

</div>

</div>

</div>

