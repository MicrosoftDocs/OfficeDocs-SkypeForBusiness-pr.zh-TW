---
title: Lync Server 2013：規劃通話駐留災害復原
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
ms.openlocfilehash: a76052297e527e24fd3daf0c03d02661c7ddc255
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41754453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="65bbc-102">在 Lync Server 2013 中規劃通話駐留災害復原</span><span class="sxs-lookup"><span data-stu-id="65bbc-102">Planning for Call Park disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65bbc-103">_**主題上次修改日期：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="65bbc-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="65bbc-104">本節說明準備通話駐留應用程式以進行災害復原的一些方法，以及災害復原程式的一些考慮。</span><span class="sxs-lookup"><span data-stu-id="65bbc-104">This section describes some ways to prepare the Call Park application for disaster recovery and some considerations for the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a><span data-ttu-id="65bbc-105">準備通話駐留災害復原</span><span class="sxs-lookup"><span data-stu-id="65bbc-105">Preparing for Call Park Disaster Recovery</span></span>

<span data-ttu-id="65bbc-106">在準備及執行災害復原程式時，請記住下列事項。</span><span class="sxs-lookup"><span data-stu-id="65bbc-106">Keep the following in mind when preparing for and carrying out disaster recovery procedures.</span></span>

  - <span data-ttu-id="65bbc-107">在您進行容量規劃時規劃災害復原。</span><span class="sxs-lookup"><span data-stu-id="65bbc-107">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="65bbc-108">針對災害復原容量，成對的池中的每個池都應該能夠處理兩個池中的通話駐留服務工作負荷。</span><span class="sxs-lookup"><span data-stu-id="65bbc-108">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of the Call Park services in both pools.</span></span> <span data-ttu-id="65bbc-109">如需通話寄存容量規劃的詳細資料，請參閱[Lync Server 2013 中的通話駐留的容量規劃](lync-server-2013-capacity-planning-for-call-park.md)。</span><span class="sxs-lookup"><span data-stu-id="65bbc-109">For details about Call Park capacity planning, see [Capacity planning for Call Park in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span></span>

  - <span data-ttu-id="65bbc-110">在災害復原期間，已重新導向至備份池的使用者，如果是作為容錯移轉程式的一部分，則會使用在備份池中執行的通話駐留服務。</span><span class="sxs-lookup"><span data-stu-id="65bbc-110">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park service running in the backup pool.</span></span> <span data-ttu-id="65bbc-111">因此，在災害復原期間對通話駐留的支援，必須在主要池和備份池中部署並啟用呼叫駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="65bbc-111">Therefore, support for Call Park during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

  - <span data-ttu-id="65bbc-112">針對駐留在該池中的使用者，每個泳池必須有有效的軌道編號範圍，才能用於停車通話。</span><span class="sxs-lookup"><span data-stu-id="65bbc-112">Each pool must have a valid range of orbit numbers for users who are homed in that pool to use for parking calls.</span></span>

  - <span data-ttu-id="65bbc-113">保留已針對通話駐留上傳的任何自訂音樂保留的個別備份複本。</span><span class="sxs-lookup"><span data-stu-id="65bbc-113">Always keep a separate backup copy of any customized music on hold that has been uploaded for Call Park.</span></span> <span data-ttu-id="65bbc-114">這些檔案不會作為 Lync Server 2013 災害復原程式的一部分進行備份，如果上傳到該池的檔案遭到損毀、損毀或清除，就會遺失。</span><span class="sxs-lookup"><span data-stu-id="65bbc-114">These files are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a><span data-ttu-id="65bbc-115">通話駐留災害復原考慮</span><span class="sxs-lookup"><span data-stu-id="65bbc-115">Call Park Disaster Recovery Considerations</span></span>

<span data-ttu-id="65bbc-116">您只能定義一組通話寄存應用程式設定的設定，以及每個池中的一個自訂音樂保留音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="65bbc-116">You can define only one set of Call Park application configuration settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="65bbc-117">這些設定包括超時閾值、暫停的音樂、最大的呼叫挑選嘗試，以及超時 URI。</span><span class="sxs-lookup"><span data-stu-id="65bbc-117">These settings include the timeout threshold, music on hold, maximum call pickup attempts, and timeout URI.</span></span> <span data-ttu-id="65bbc-118">若要查看這些設定，請執行**CsCpsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="65bbc-118">To view these configuration settings, run the **Get-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="65bbc-119">如需**CsCpsConfiguration** Cmdlet 的詳細資訊，請參閱[CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="65bbc-119">For details about the **Get-CsCpsConfiguration** cmdlet, see [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span></span>

<span data-ttu-id="65bbc-120">在災害復原期間，通話駐留會使用備份池中的通話駐留應用程式，因此不會備份主要池中的設定。</span><span class="sxs-lookup"><span data-stu-id="65bbc-120">During disaster recovery, Call Park uses the Call Park application in the backup pool, so settings in the primary pool are not backed up.</span></span> <span data-ttu-id="65bbc-121">如果無法復原主要池，且您要部署新的池來取代主要池，主要池中的設定會遺失，您需要在新的池中重新設定通話寄存設定及任何自訂的音樂保留音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="65bbc-121">If the primary pool can't be recovered and you deploy a new pool to replace the primary pool, the settings from the primary pool are lost, and you need to reconfigure the Call Park settings and any customized music-on-hold audio files in the new pool.</span></span>

<span data-ttu-id="65bbc-122">如果您使用不同的完整功能變數名稱（FQDN）部署新的資料庫池來取代主要池，您需要將與主要池相關聯的所有通話駐留軌道的範圍重新指派給新的池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="65bbc-122">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Call Park orbit ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="65bbc-123">若要將軌道範圍重新指派給新的池子，您可以使用 Lync Server [控制台] 或**CsCallParkOrbit** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="65bbc-123">To reassign orbit ranges to the new pool, you can use either Lync Server Control Panel or the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="65bbc-124">如需**CsCallParkOrbit** Cmdlet 的詳細資訊，請參閱[設定 CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)。</span><span class="sxs-lookup"><span data-stu-id="65bbc-124">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

