---
title: 確認組態設定
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48184111
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5055f9ce77c5f1ad8b717af50ea621f37392ce0d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a><span data-ttu-id="1b8c8-102">確認組態設定</span><span class="sxs-lookup"><span data-stu-id="1b8c8-102">Verify configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b8c8-103">_**主題上次修改日期：** 2012年-09-06_</span><span class="sxs-lookup"><span data-stu-id="1b8c8-103">_**Topic Last Modified:** 2012-09-06_</span></span>

<span data-ttu-id="1b8c8-104">您可以藉由其中央管理存放區位於，或任何加入網域電腦安裝 Lync Server 2013 核心元件 (OcsCore.msi) 上的內部電腦上，執行 Lync Server 2013 **Get-csmanagementstorereplicationstatus** cmdlet 驗證對 Edge server 的組態資訊複寫。</span><span class="sxs-lookup"><span data-stu-id="1b8c8-104">You can validate the replication of configuration information to the Edge server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span>

<span data-ttu-id="1b8c8-105">初始結果可能會指出複寫的狀態為 "False"，而非 "True"。</span><span class="sxs-lookup"><span data-stu-id="1b8c8-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="1b8c8-106">若是如此，請執行 **Invoke-CsManagementStoreReplication** Cmdlet，等候複寫完成，然後再次執行 **Get-CsManagementStoreReplicationStatus**。</span><span class="sxs-lookup"><span data-stu-id="1b8c8-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

