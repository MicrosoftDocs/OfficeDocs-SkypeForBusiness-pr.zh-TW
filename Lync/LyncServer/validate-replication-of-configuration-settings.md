---
title: 驗證複製組態設定
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Validate replication of configuration settings
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205042(v=OCS.15)
ms:contentKeyID: 48184663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65620e07227581f35e5760e8665e615c6976bde2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048267"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-replication-of-configuration-settings"></a>驗證複製組態設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-19_

您可以藉由在中央管理存放區所在的內部電腦或任何加入的網域電腦安裝 Lync Server 2013 核心元件上執行 Lync Server 2013 **Get-csmanagementstorereplicationstatus** cmdlet 驗證複寫至 Edge Server 的組態資訊。

初始結果可能會指出複寫的狀態為 "False"，而非 "True"。 若是如此，請執行 **Invoke-CsManagementStoreReplication** Cmdlet，並等候複寫完成，然後再次執行 **Get-CsManagementStoreReplicationStatus** Cmdlet。

</div>

<span> </span>

</div>

</div>

</div>

