---
title: 設定和監控備份服務
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 您可以使用商務用 Skype Server Management Shell 命令來設定及監視備份服務。
ms.openlocfilehash: 2170f58fcc60a648788934048f3d0e6bbfac9c77
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193589"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="675a2-103">在商務用 Skype Server 中設定及監視備份服務</span><span class="sxs-lookup"><span data-stu-id="675a2-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="675a2-104">您可以使用下列商務用 Skype Server Management Shell 命令來設定及監視備份服務。</span><span class="sxs-lookup"><span data-stu-id="675a2-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="675a2-105">若要還原儲存在前端文件庫檔案存放區中的會議資訊, 請參閱下方的[使用備份服務還原會議內容](#restore-conference-contents-using-the-backup-service)。</span><span class="sxs-lookup"><span data-stu-id="675a2-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="675a2-106">RTCUniversalServerAdmins 群組是唯一具有執行**CsBackupServiceStatus**預設許可權的群組。</span><span class="sxs-lookup"><span data-stu-id="675a2-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="675a2-107">若要使用這個 Cmdlet, 請以這個群組的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="675a2-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="675a2-108">或者, 您可以使用**CsBackupServiceConfiguration** Cmdlet, 將此命令的存取權授與其他群組 (例如, CSAdministrator)。</span><span class="sxs-lookup"><span data-stu-id="675a2-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="675a2-109">若要查看備份服務設定</span><span class="sxs-lookup"><span data-stu-id="675a2-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="675a2-110">執行下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="675a2-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="675a2-111">SyncInterval 的預設值是兩分鐘。</span><span class="sxs-lookup"><span data-stu-id="675a2-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="675a2-112">設定備份服務同步處理間隔</span><span class="sxs-lookup"><span data-stu-id="675a2-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="675a2-113">執行下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="675a2-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="675a2-114">例如, 下列會將間隔設定為三分鐘。</span><span class="sxs-lookup"><span data-stu-id="675a2-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="675a2-115">雖然您可以使用這個 Cmdlet 來變更備份服務的預設同步處理間隔, 但除非是絕對必要, 否則您不應該這麼做, 因為同步處理間隔對備份服務效能和復原點目標 (RPO) 有很大的影響。</span><span class="sxs-lookup"><span data-stu-id="675a2-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="675a2-116">取得特定文件庫的備份服務狀態</span><span class="sxs-lookup"><span data-stu-id="675a2-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="675a2-117">執行下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="675a2-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="675a2-118">備份服務同步處理狀態是從池 (P1) 定義 unidirectionally 到其備份池 (P2)。</span><span class="sxs-lookup"><span data-stu-id="675a2-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="675a2-119">從 P1 到 P2 的同步處理狀態, 可能與 P2 與 P1 不同。</span><span class="sxs-lookup"><span data-stu-id="675a2-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="675a2-120">針對 P1 到 P2, 如果在 P1 中所做的所有變更都會在同步處理間隔內完全複製到 P2, 則備份服務處於「穩定」狀態。</span><span class="sxs-lookup"><span data-stu-id="675a2-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="675a2-121">如果沒有其他變更要從 P1 同步處理到 P2, 則會處於 [最終] 狀態。</span><span class="sxs-lookup"><span data-stu-id="675a2-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="675a2-122">這兩種狀態表示執行 Cmdlet 時備份服務的快照。</span><span class="sxs-lookup"><span data-stu-id="675a2-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="675a2-123">這並不表示傳回的狀態將會持續保持不變。</span><span class="sxs-lookup"><span data-stu-id="675a2-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="675a2-124">特別是, 只有在執行 Cmdlet 之後, P1 不會產生任何變更時, 才會繼續保留 [最終] 狀態。</span><span class="sxs-lookup"><span data-stu-id="675a2-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="675a2-125">在 P1 成為**CsPoolfailover**執行邏輯的一部分之後, p1 被置於唯讀模式之後, 就會發生失敗情況。</span><span class="sxs-lookup"><span data-stu-id="675a2-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="675a2-126">若要取得特定資源庫之備份關聯的相關資訊</span><span class="sxs-lookup"><span data-stu-id="675a2-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="675a2-127">執行下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="675a2-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="675a2-128">強制備份服務同步處理</span><span class="sxs-lookup"><span data-stu-id="675a2-128">To force a Backup Service sync</span></span>

<span data-ttu-id="675a2-129">執行下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="675a2-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="675a2-130">使用備份服務還原會議內容</span><span class="sxs-lookup"><span data-stu-id="675a2-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="675a2-131">如果在 [前端] 池的 [檔案存放區] 中儲存的會議資訊無法使用, 您必須還原此資訊, 讓駐留在該池中的使用者保留其會議資料。</span><span class="sxs-lookup"><span data-stu-id="675a2-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="675a2-132">如果有遺失會議資料的前端池是與另一個前端池進行配對, 您可以使用 [備份服務] 來還原資料。</span><span class="sxs-lookup"><span data-stu-id="675a2-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="675a2-133">如果整個池失敗, 而且您必須將其使用者容錯移轉至備份池, 也必須執行此工作。</span><span class="sxs-lookup"><span data-stu-id="675a2-133">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="675a2-134">當這些使用者傳回容錯移轉至原始池時, 您必須使用此程式將其會議內容複寫回其原始池。</span><span class="sxs-lookup"><span data-stu-id="675a2-134">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="675a2-135">假設 Pool1 與 Pool2 成對, 而 Pool1 中的會議資料遺失。</span><span class="sxs-lookup"><span data-stu-id="675a2-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="675a2-136">您可以使用下列 Cmdlet 來喚醒呼叫備份服務來還原內容:</span><span class="sxs-lookup"><span data-stu-id="675a2-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="675a2-137">還原會議內容可能需要一些時間, 視其大小而定。</span><span class="sxs-lookup"><span data-stu-id="675a2-137">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="675a2-138">您可以使用下列 Cmdlet 來檢查進程狀態:</span><span class="sxs-lookup"><span data-stu-id="675a2-138">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="675a2-139">此程式會在此 Cmdlet 針對資料會議模組傳回穩定狀態的值時完成。</span><span class="sxs-lookup"><span data-stu-id="675a2-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
