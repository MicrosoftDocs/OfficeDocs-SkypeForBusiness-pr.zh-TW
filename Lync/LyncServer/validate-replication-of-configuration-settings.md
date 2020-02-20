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
ms.openlocfilehash: 0c379ec1d617dcb6920f83f68f857839a8f5439b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validate-replication-of-configuration-settings"></a><span data-ttu-id="0c2ee-102">驗證複製組態設定</span><span class="sxs-lookup"><span data-stu-id="0c2ee-102">Validate replication of configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c2ee-103">_**主題上次修改日期：** 2012年-10-19_</span><span class="sxs-lookup"><span data-stu-id="0c2ee-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="0c2ee-104">您可以藉由在中央管理存放區所在的內部電腦或任何加入的網域電腦安裝 Lync Server 2013 核心元件上執行 Lync Server 2013 **Get-csmanagementstorereplicationstatus** cmdlet 驗證複寫至 Edge Server 的組態資訊。</span><span class="sxs-lookup"><span data-stu-id="0c2ee-104">You can validate the replication of configuration information to the Edge Server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located or any domain joined computer on which Lync Server 2013 Core Components is installed.</span></span>

<span data-ttu-id="0c2ee-105">初始結果可能會指出複寫的狀態為 "False"，而非 "True"。</span><span class="sxs-lookup"><span data-stu-id="0c2ee-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="0c2ee-106">若是如此，請執行 **Invoke-CsManagementStoreReplication** Cmdlet，並等候複寫完成，然後再次執行 **Get-CsManagementStoreReplicationStatus** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0c2ee-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** cmdlet again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

