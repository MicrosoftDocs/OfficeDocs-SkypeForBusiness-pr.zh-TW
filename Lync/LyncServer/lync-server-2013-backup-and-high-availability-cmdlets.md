---
title: Lync Server 2013：備份與高可用性 Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and high availability cmdlets
ms:assetid: 5aff41a3-7a0e-4c51-9d5f-7f08e36bf046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204925(v=OCS.15)
ms:contentKeyID: 48184236
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b730d265d32341b329bf5ba3a1055b37bd240a55
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-high-availability-cmdlets-in-lync-server-2013"></a><span data-ttu-id="42128-102">Lync Server 2013 中的備份和高可用性 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="42128-102">Backup and high availability cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42128-103">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="42128-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="42128-104">[備份] 和 [高可用性] Cmdlet 可讓系統管理員管理 Microsoft Lync Server 2013 中所引進的 [池備份]、[還原] 和 [高可用性] 功能。</span><span class="sxs-lookup"><span data-stu-id="42128-104">The backup and high availability cmdlets enable administrators to manage the pool backup, restore, and high availability capabilities introduced in Microsoft Lync Server 2013.</span></span>

<div>

## <a name="backup-and-high-availability-cmdlets"></a><span data-ttu-id="42128-105">備份和高可用性 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="42128-105">Backup and High Availability Cmdlets</span></span>

<span data-ttu-id="42128-106">以下是直接相關的 Cmdlet 清單，可與備份及設定 Lync Server 拓撲的可用性進行關聯：</span><span class="sxs-lookup"><span data-stu-id="42128-106">The following is a list of cmdlets that relate directly to backing up and configuring the availability of your Lync Server topology:</span></span>

<span data-ttu-id="42128-107">**備份和高可用性 Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="42128-107">**Backup and High Availability Cmdlets**</span></span>

  - <span data-ttu-id="42128-108">[CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205087(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="42128-108">[Get-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205087(v=OCS.15))</span></span>

  - <span data-ttu-id="42128-109">[移除-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ204903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="42128-109">[Remove-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ204903(v=OCS.15))</span></span>

  - <span data-ttu-id="42128-110">[Set-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205006(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="42128-110">[Set-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205006(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="42128-111">[CsBackupServiceStatus](https://technet.microsoft.com/en-us/library/JJ205032(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="42128-111">[Get-CsBackupServiceStatus](https://technet.microsoft.com/en-us/library/JJ205032(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="42128-112">[Invoke-CsBackupServiceSync](https://technet.microsoft.com/en-us/library/JJ205374(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="42128-112">[Invoke-CsBackupServiceSync](https://technet.microsoft.com/en-us/library/JJ205374(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="42128-113">[Debug-CsIntraPoolReplication](https://technet.microsoft.com/en-us/library/JJ205103(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="42128-113">[Debug-CsIntraPoolReplication](https://technet.microsoft.com/en-us/library/JJ205103(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="42128-114">[備份-CsPool](https://technet.microsoft.com/en-us/library/JJ204955(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="42128-114">[Backup-CsPool](https://technet.microsoft.com/en-us/library/JJ204955(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="42128-115">[CsPoolBackupRelationship](https://technet.microsoft.com/en-us/library/JJ204745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="42128-115">[Get-CsPoolBackupRelationship](https://technet.microsoft.com/en-us/library/JJ204745(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="42128-116">[Get-CsPoolFabricState](https://technet.microsoft.com/en-us/library/JJ619188(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="42128-116">[Get-CsPoolFabricState](https://technet.microsoft.com/en-us/library/JJ619188(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="42128-117">[Invoke-CsPoolFailBack](https://technet.microsoft.com/en-us/library/JJ204873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="42128-117">[Invoke-CsPoolFailBack](https://technet.microsoft.com/en-us/library/JJ204873(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="42128-118">[Invoke-CsPoolFailOver](https://technet.microsoft.com/en-us/library/JJ205189(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="42128-118">[Invoke-CsPoolFailOver](https://technet.microsoft.com/en-us/library/JJ205189(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="42128-119">[Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/en-us/library/JJ204689(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="42128-119">[Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/en-us/library/JJ204689(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="42128-120">[Invoke-CsStorageServiceFlush](https://technet.microsoft.com/en-us/library/JJ619175(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="42128-120">[Invoke-CsStorageServiceFlush](https://technet.microsoft.com/en-us/library/JJ619175(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="42128-121">[同步處理-CsUserData](https://technet.microsoft.com/en-us/library/JJ205242(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="42128-121">[Sync-CsUserData](https://technet.microsoft.com/en-us/library/JJ205242(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="42128-122">[移除-CsUserStoreBackupData](https://technet.microsoft.com/en-us/library/JJ205003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="42128-122">[Remove-CsUserStoreBackupData](https://technet.microsoft.com/en-us/library/JJ205003(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

