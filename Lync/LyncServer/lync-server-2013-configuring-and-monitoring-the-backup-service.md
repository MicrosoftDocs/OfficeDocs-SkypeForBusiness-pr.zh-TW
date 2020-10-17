---
title: Lync Server 2013：設定及監視備份服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3df8f2208566ed89feda0a06c4cce8f699d130d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517560"
---
# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="0af07-102">在 Lync Server 2013 中設定及監視備份服務</span><span class="sxs-lookup"><span data-stu-id="0af07-102">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0af07-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0af07-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0af07-104">您可以使用下列 Lync Server 管理命令介面命令來設定及監視備份服務。</span><span class="sxs-lookup"><span data-stu-id="0af07-104">You can use the following Lync Server Management Shell commands to configure and monitor the Backup Service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0af07-105">根據預設，RTCUniversalServerAdmins 群組是具有執行 <STRONG>Get-CsBackupServiceStatus</STRONG> 許可權的唯一群組。</span><span class="sxs-lookup"><span data-stu-id="0af07-105">The RTCUniversalServerAdmins group is the only group that has permissions to run <STRONG>Get-CsBackupServiceStatus</STRONG> by default.</span></span> <span data-ttu-id="0af07-106">若要使用此 Cmdlet，請以此群組的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="0af07-106">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="0af07-107">或者，您可以將此命令的存取權授與其他群組 (例如，使用 <STRONG>Set-CsBackupServiceConfiguration</STRONG> 指令程式 CSAdministrator) 。</span><span class="sxs-lookup"><span data-stu-id="0af07-107">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the <STRONG>Set-CsBackupServiceConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="0af07-108">若要查看備份服務設定</span><span class="sxs-lookup"><span data-stu-id="0af07-108">To see the Backup Service configuration</span></span>

<span data-ttu-id="0af07-109">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="0af07-109">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="0af07-110">SyncInterval 的預設值是兩分鐘。</span><span class="sxs-lookup"><span data-stu-id="0af07-110">The default for SyncInterval is two minutes.</span></span>

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="0af07-111">設定備份服務同步處理間隔</span><span class="sxs-lookup"><span data-stu-id="0af07-111">To set the Backup Service sync interval</span></span>

<span data-ttu-id="0af07-112">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="0af07-112">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="0af07-113">例如，下列會將間隔設定為3分鐘。</span><span class="sxs-lookup"><span data-stu-id="0af07-113">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0af07-114">雖然您可以使用此 Cmdlet 變更備份服務的預設同步處理間隔，但除非完全必要，否則不應這麼做，因為同步處理間隔對備份服務效能具有極大的影響，而且復原點目標 (RPO) 。</span><span class="sxs-lookup"><span data-stu-id="0af07-114">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="0af07-115">取得特定集區的備份服務狀態</span><span class="sxs-lookup"><span data-stu-id="0af07-115">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="0af07-116">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="0af07-116">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> <span data-ttu-id="0af07-117">備份服務同步處理狀態是從 (P1) 集區 unidirectionally 至其備份組區 (P2) 所定義。</span><span class="sxs-lookup"><span data-stu-id="0af07-117">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="0af07-118">從 P1 到 P2 的同步處理狀態可能不同于從 P2 到 P1 的狀態。</span><span class="sxs-lookup"><span data-stu-id="0af07-118">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="0af07-119">若為 P1，當 P1 中所做的所有變更都會在同步處理間隔內完全複寫至 P2 時，備份服務處於「穩定」狀態。</span><span class="sxs-lookup"><span data-stu-id="0af07-119">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="0af07-120">如果沒有其他要從 P1 同步處理的變更，則為 "final" 狀態。</span><span class="sxs-lookup"><span data-stu-id="0af07-120">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="0af07-121">這兩種狀態都會指出執行 Cmdlet 時備份服務的快照。</span><span class="sxs-lookup"><span data-stu-id="0af07-121">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="0af07-122">這並不表示傳回的狀態會在此後保留。</span><span class="sxs-lookup"><span data-stu-id="0af07-122">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="0af07-123">特別是，當執行 Cmdlet 後，如果 P1 不會產生任何變更，則 "final" 狀態會繼續保留。</span><span class="sxs-lookup"><span data-stu-id="0af07-123">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="0af07-124">當 p1 成為 <STRONG>CsPoolfailover</STRONG> 執行邏輯的一部分時，p1 被置於唯讀模式後，就會發生失敗的情況。</span><span class="sxs-lookup"><span data-stu-id="0af07-124">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the <STRONG>Invoke-CsPoolfailover</STRONG> execution logic.</span></span>



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="0af07-125">若要取得特定集區之備份關係的相關資訊</span><span class="sxs-lookup"><span data-stu-id="0af07-125">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="0af07-126">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="0af07-126">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="0af07-127">強制執行備份服務同步處理</span><span class="sxs-lookup"><span data-stu-id="0af07-127">To force a Backup Service sync</span></span>

<span data-ttu-id="0af07-128">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="0af07-128">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

