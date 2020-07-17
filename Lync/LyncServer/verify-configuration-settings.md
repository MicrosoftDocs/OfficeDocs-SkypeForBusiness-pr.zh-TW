---
title: 確認組態設定
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48184111
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c98ec6387353e60890653a0369107c126f8eeb4
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a><span data-ttu-id="e90d2-102">確認組態設定</span><span class="sxs-lookup"><span data-stu-id="e90d2-102">Verify configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e90d2-103">_**主題上次修改日期：** 2012-09-06_</span><span class="sxs-lookup"><span data-stu-id="e90d2-103">_**Topic Last Modified:** 2012-09-06_</span></span>

<span data-ttu-id="e90d2-104">您可以在中央管理存放區所在的內部電腦上執行 Lync Server 2013 Get-CsManagementStoreReplicationStatus Cmdlet，或在安裝 Lync Server 2013 核心元件（OcsCore.msi）的任何已加入網域的電腦上執行 Lync Server **Get-CsManagementStoreReplicationStatus** Cmdlet，以驗證將設定資訊複寫至 Edge server。</span><span class="sxs-lookup"><span data-stu-id="e90d2-104">You can validate the replication of configuration information to the Edge server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span>

<span data-ttu-id="e90d2-105">初始結果可能會指出複寫的狀態為 "False"，而非 "True"。</span><span class="sxs-lookup"><span data-stu-id="e90d2-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="e90d2-106">若是如此，請執行 **Invoke-CsManagementStoreReplication** Cmdlet，等候複寫完成，然後再次執行 **Get-CsManagementStoreReplicationStatus**。</span><span class="sxs-lookup"><span data-stu-id="e90d2-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

