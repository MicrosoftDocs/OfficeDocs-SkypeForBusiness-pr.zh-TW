---
title: 驗證配置設定的複寫
description: 驗證配置設定的複寫。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Validate replication of configuration settings
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205042(v=OCS.15)
ms:contentKeyID: 48184663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26d8e9326da8b865f4e2ca3181975fb899300636
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552599"
---
# <a name="validate-replication-of-configuration-settings"></a><span data-ttu-id="bbb73-103">驗證配置設定的複寫</span><span class="sxs-lookup"><span data-stu-id="bbb73-103">Validate replication of configuration settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbb73-104">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="bbb73-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="bbb73-105">您可以在中央管理存放區所在的內部電腦上，或在安裝 Lync Server 2013 核心元件的任何已加入網域的電腦上執行 Lync Server 2013 **Get-CsManagementStoreReplicationStatus** Cmdlet，以驗證將設定資訊複寫至 Edge server。</span><span class="sxs-lookup"><span data-stu-id="bbb73-105">You can validate the replication of configuration information to the Edge Server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located or any domain joined computer on which Lync Server 2013 Core Components is installed.</span></span>

<span data-ttu-id="bbb73-106">初始結果可能會指出複寫的狀態為 "False"，而非 "True"。</span><span class="sxs-lookup"><span data-stu-id="bbb73-106">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="bbb73-107">若是如此，請執行 **Invoke-CsManagementStoreReplication** Cmdlet，並等候複寫完成，然後再次執行 **Get-CsManagementStoreReplicationStatus** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bbb73-107">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** cmdlet again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

