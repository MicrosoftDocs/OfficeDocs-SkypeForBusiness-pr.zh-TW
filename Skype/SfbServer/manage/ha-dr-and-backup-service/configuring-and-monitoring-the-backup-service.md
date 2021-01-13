---
title: 設定及監視備份服務
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 您可以使用商務用 Skype Server 管理命令介面命令來設定及監視備份服務。
ms.openlocfilehash: d38c9d0b0261fb7e1da89b3422496d94307a791d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817193"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="48944-103">在商務用 Skype Server 中設定及監視備份服務</span><span class="sxs-lookup"><span data-stu-id="48944-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="48944-104">您可以使用下列商務用 Skype Server 管理命令介面命令來設定及監視備份服務。</span><span class="sxs-lookup"><span data-stu-id="48944-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="48944-105">若要還原儲存在前端集區之檔案存放區中的會議資訊，請參閱下面 [的使用備份服務還原會議內容](#restore-conference-contents-using-the-backup-service)。</span><span class="sxs-lookup"><span data-stu-id="48944-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="48944-106">根據預設，RTCUniversalServerAdmins 群組是具有執行 **Get-CsBackupServiceStatus** 許可權的唯一群組。</span><span class="sxs-lookup"><span data-stu-id="48944-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="48944-107">若要使用此 Cmdlet，請以此群組的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="48944-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="48944-108">或者，您可以將此命令的存取權授與其他群組 (例如，使用 **Set-CsBackupServiceConfiguration** 指令程式 CSAdministrator) 。</span><span class="sxs-lookup"><span data-stu-id="48944-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="48944-109">若要查看備份服務設定</span><span class="sxs-lookup"><span data-stu-id="48944-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="48944-110">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="48944-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="48944-111">SyncInterval 的預設值是兩分鐘。</span><span class="sxs-lookup"><span data-stu-id="48944-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="48944-112">設定備份服務同步處理間隔</span><span class="sxs-lookup"><span data-stu-id="48944-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="48944-113">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="48944-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="48944-114">例如，下列會將間隔設定為3分鐘。</span><span class="sxs-lookup"><span data-stu-id="48944-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="48944-115">雖然您可以使用此 Cmdlet 變更備份服務的預設同步處理間隔，但除非完全必要，否則不應這麼做，因為同步處理間隔對備份服務效能具有極大的影響，而且復原點目標 (RPO) 。</span><span class="sxs-lookup"><span data-stu-id="48944-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="48944-116">取得特定集區的備份服務狀態</span><span class="sxs-lookup"><span data-stu-id="48944-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="48944-117">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="48944-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="48944-118">備份服務同步處理狀態是從 (P1) 集區 unidirectionally 至其備份組區 (P2) 所定義。</span><span class="sxs-lookup"><span data-stu-id="48944-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="48944-119">從 P1 到 P2 的同步處理狀態可能不同于從 P2 到 P1 的狀態。</span><span class="sxs-lookup"><span data-stu-id="48944-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="48944-120">若為 P1，當 P1 中所做的所有變更都會在同步處理間隔內完全複寫至 P2 時，備份服務處於「穩定」狀態。</span><span class="sxs-lookup"><span data-stu-id="48944-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="48944-121">如果沒有其他要從 P1 同步處理的變更，則為 "final" 狀態。</span><span class="sxs-lookup"><span data-stu-id="48944-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="48944-122">這兩種狀態都會指出執行 Cmdlet 時備份服務的快照。</span><span class="sxs-lookup"><span data-stu-id="48944-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="48944-123">這並不表示傳回的狀態會在此後保留。</span><span class="sxs-lookup"><span data-stu-id="48944-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="48944-124">特別是，當執行 Cmdlet 後，如果 P1 不會產生任何變更，則 "final" 狀態會繼續保留。</span><span class="sxs-lookup"><span data-stu-id="48944-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="48944-125">當 p1 成為 **CsPoolfailover** 執行邏輯的一部分時，p1 被置於唯讀模式後，就會發生失敗的情況。</span><span class="sxs-lookup"><span data-stu-id="48944-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="48944-126">若要取得特定集區之備份關係的相關資訊</span><span class="sxs-lookup"><span data-stu-id="48944-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="48944-127">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="48944-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="48944-128">強制執行備份服務同步處理</span><span class="sxs-lookup"><span data-stu-id="48944-128">To force a Backup Service sync</span></span>

<span data-ttu-id="48944-129">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="48944-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="48944-130">使用備份服務還原會議內容</span><span class="sxs-lookup"><span data-stu-id="48944-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="48944-131">如果在前端集區的檔案存放區中儲存的會議資訊無法使用，則必須還原此資訊，以便集區中的使用者保留其會議資料。</span><span class="sxs-lookup"><span data-stu-id="48944-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="48944-132">如果已遺失會議資料的前端集區與另一個前端集區成對，您可以使用備份服務還原資料。</span><span class="sxs-lookup"><span data-stu-id="48944-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="48944-p105">如果整個集區失敗，而必須將使用者容錯移轉至備份集區，也必須執行此工作。當這些使用者容錯移轉回原始集區時，也必須使用此程序，將會議內容複製回原始集區。</span><span class="sxs-lookup"><span data-stu-id="48944-p105">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool. When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="48944-135">假設 Pool1 與 Pool2 配對，而 Pool1 中的會議資料遺失。</span><span class="sxs-lookup"><span data-stu-id="48944-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="48944-136">您可以使用下列 Cmdlet 來調用備份服務，以還原內容：</span><span class="sxs-lookup"><span data-stu-id="48944-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="48944-p107">視會議內容的大小而定，還原會議內容可能需要一些時間。可以使用下列 Cmdlet 檢查處理狀態：</span><span class="sxs-lookup"><span data-stu-id="48944-p107">Restoring the conference contents may take some time, depending on their size. You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="48944-139">當此 Cmdlet 傳回資料會議模組的「穩定狀態」值時，處理就已完成。</span><span class="sxs-lookup"><span data-stu-id="48944-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
