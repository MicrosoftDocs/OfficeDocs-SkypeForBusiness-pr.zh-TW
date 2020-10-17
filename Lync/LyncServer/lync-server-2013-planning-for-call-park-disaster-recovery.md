---
title: Lync Server 2013：規劃通話駐留災難修復
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f221947975c00eccefe50cb5ca72b264c9596014
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497750"
---
# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="3cf2e-102">在 Lync Server 2013 中規劃通話駐留災難修復</span><span class="sxs-lookup"><span data-stu-id="3cf2e-102">Planning for Call Park disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cf2e-103">_**主題上次修改日期：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="3cf2e-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="3cf2e-104">本節說明一些為災難修復準備通話駐留應用程式的方法，以及有關嚴重損壞修復程式的一些考慮。</span><span class="sxs-lookup"><span data-stu-id="3cf2e-104">This section describes some ways to prepare the Call Park application for disaster recovery and some considerations for the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a><span data-ttu-id="3cf2e-105">準備通話駐留災難修復</span><span class="sxs-lookup"><span data-stu-id="3cf2e-105">Preparing for Call Park Disaster Recovery</span></span>

<span data-ttu-id="3cf2e-106">在準備及執行嚴重損壞復原程式時，請牢記下列幾點。</span><span class="sxs-lookup"><span data-stu-id="3cf2e-106">Keep the following in mind when preparing for and carrying out disaster recovery procedures.</span></span>

  - <span data-ttu-id="3cf2e-107">在進行容量規劃時，請規劃災害復原。</span><span class="sxs-lookup"><span data-stu-id="3cf2e-107">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="3cf2e-108">針對嚴重損壞修復容量，成對集區中的每個集區都應該可以處理兩個集區中通話駐留服務的工作量。</span><span class="sxs-lookup"><span data-stu-id="3cf2e-108">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of the Call Park services in both pools.</span></span> <span data-ttu-id="3cf2e-109">如需通話駐留容量規劃的詳細資訊，請參閱 [Lync Server 2013 中的「通話駐留」的容量規劃](lync-server-2013-capacity-planning-for-call-park.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf2e-109">For details about Call Park capacity planning, see [Capacity planning for Call Park in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span></span>

  - <span data-ttu-id="3cf2e-110">在嚴重損壞復原期間，已被重新導向至備份組區的使用者，在容錯移轉過程中，會使用在備份組區中執行的通話駐留服務。</span><span class="sxs-lookup"><span data-stu-id="3cf2e-110">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park service running in the backup pool.</span></span> <span data-ttu-id="3cf2e-111">因此，在嚴重損壞修復時支援通話駐留應用程式，需要在主要集區和備份組區中部署及啟用通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="3cf2e-111">Therefore, support for Call Park during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

  - <span data-ttu-id="3cf2e-112">每個集區都必須有有效的軌道編號範圍，以供位於該集區中的使用者用來進行停車電話。</span><span class="sxs-lookup"><span data-stu-id="3cf2e-112">Each pool must have a valid range of orbit numbers for users who are homed in that pool to use for parking calls.</span></span>

  - <span data-ttu-id="3cf2e-113">永遠保留為通話駐留上傳的任何自訂音樂保留的個別備份副本。</span><span class="sxs-lookup"><span data-stu-id="3cf2e-113">Always keep a separate backup copy of any customized music on hold that has been uploaded for Call Park.</span></span> <span data-ttu-id="3cf2e-114">當您上傳至集區的檔案損毀、損毀或清除時，不會將這些檔案備份成 Lync Server 2013 災難復原程式的一部分，而且將會遺失。</span><span class="sxs-lookup"><span data-stu-id="3cf2e-114">These files are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a><span data-ttu-id="3cf2e-115">通話駐留災害復原考慮</span><span class="sxs-lookup"><span data-stu-id="3cf2e-115">Call Park Disaster Recovery Considerations</span></span>

<span data-ttu-id="3cf2e-116">您只能為每個集區定義一組通話駐留應用程式設定設定及一個自訂的音樂暫止音訊檔。</span><span class="sxs-lookup"><span data-stu-id="3cf2e-116">You can define only one set of Call Park application configuration settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="3cf2e-117">這些設定包括超時閾值、等候音樂、來電收取次數上限及超時 URI。</span><span class="sxs-lookup"><span data-stu-id="3cf2e-117">These settings include the timeout threshold, music on hold, maximum call pickup attempts, and timeout URI.</span></span> <span data-ttu-id="3cf2e-118">若要查看這些設定設定，請執行 **CsCpsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3cf2e-118">To view these configuration settings, run the **Get-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="3cf2e-119">如需 **CsCpsConfiguration** Cmdlet 的詳細資訊，請參閱 [CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="3cf2e-119">For details about the **Get-CsCpsConfiguration** cmdlet, see [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span></span>

<span data-ttu-id="3cf2e-120">在發生嚴重損壞修復時，通話駐留會使用備份組區中的通話駐留應用程式，因此不會備份主要集區中的設定。</span><span class="sxs-lookup"><span data-stu-id="3cf2e-120">During disaster recovery, Call Park uses the Call Park application in the backup pool, so settings in the primary pool are not backed up.</span></span> <span data-ttu-id="3cf2e-121">如果無法復原主集區，而您部署新集區以取代主要集區，主要集區中的設定會遺失，您必須在新集區中重新設定通話駐留設定和任何自訂的待等候音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="3cf2e-121">If the primary pool can't be recovered and you deploy a new pool to replace the primary pool, the settings from the primary pool are lost, and you need to reconfigure the Call Park settings and any customized music-on-hold audio files in the new pool.</span></span>

<span data-ttu-id="3cf2e-122">如果您使用不同的完整功能變數名稱來部署新集區 (FQDN) 取代主要集區，您必須將與主要集區相關聯的所有通話駐留軌道範圍重新指派給新集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3cf2e-122">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Call Park orbit ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="3cf2e-123">若要將軌道範圍重新指派至新集區，您可以使用 Lync Server 控制台或 **get-cscallparkorbit** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3cf2e-123">To reassign orbit ranges to the new pool, you can use either Lync Server Control Panel or the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="3cf2e-124">如需 **get-cscallparkorbit** Cmdlet 的詳細資訊，請參閱 [set-get-cscallparkorbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)。</span><span class="sxs-lookup"><span data-stu-id="3cf2e-124">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

