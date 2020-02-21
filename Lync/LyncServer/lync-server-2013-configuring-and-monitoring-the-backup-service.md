---
title: Lync Server 2013： 設定和監控備份服務
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
ms.openlocfilehash: a14e7a451b6d28df2663498e64cf2fb85c818352
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="73ade-102">設定和監控 Lync Server 2013 中備份服務</span><span class="sxs-lookup"><span data-stu-id="73ade-102">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73ade-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="73ade-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="73ade-104">您可以使用下列的 Lync Server 管理命令介面命令來設定和監控備份服務。</span><span class="sxs-lookup"><span data-stu-id="73ade-104">You can use the following Lync Server Management Shell commands to configure and monitor the Backup Service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="73ade-105">以 RTCUniversalServerAdmins 群組是具有執行<STRONG>Get-csbackupservicestatus</STRONG>預設權限的唯一群組。</span><span class="sxs-lookup"><span data-stu-id="73ade-105">The RTCUniversalServerAdmins group is the only group that has permissions to run <STRONG>Get-CsBackupServiceStatus</STRONG> by default.</span></span> <span data-ttu-id="73ade-106">若要使用此指令程式，此群組的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="73ade-106">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="73ade-107">或者，您可以存取權授與此命令 (例如，CSAdministrator) 的其他群組使用<STRONG>Set-csbackupserviceconfiguration</STRONG> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="73ade-107">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the <STRONG>Set-CsBackupServiceConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="73ade-108">若要查看備份服務組態</span><span class="sxs-lookup"><span data-stu-id="73ade-108">To see the Backup Service configuration</span></span>

<span data-ttu-id="73ade-109">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="73ade-109">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="73ade-110">SyncInterval 的預設值為 2 分鐘。</span><span class="sxs-lookup"><span data-stu-id="73ade-110">The default for SyncInterval is two minutes.</span></span>

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="73ade-111">若要設定的備份服務同步處理間隔</span><span class="sxs-lookup"><span data-stu-id="73ade-111">To set the Backup Service sync interval</span></span>

<span data-ttu-id="73ade-112">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="73ade-112">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="73ade-113">例如，下列設定的間隔為 3 分鐘。</span><span class="sxs-lookup"><span data-stu-id="73ade-113">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> <span data-ttu-id="73ade-114">雖然您可以使用此 cmdlet 變更備份服務的預設同步間隔，您不應執行因此若非絕對必要，因為同步間隔具有極大影響備份服務的效能和復原點目標 (RPO)。</span><span class="sxs-lookup"><span data-stu-id="73ade-114">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="73ade-115">若要取得特定集區的備份服務狀態</span><span class="sxs-lookup"><span data-stu-id="73ade-115">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="73ade-116">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="73ade-116">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> <span data-ttu-id="73ade-117">備份服務同步處理的狀態定義 unidirectionally 從集區 (P1) 至其備份集區 (P2)。</span><span class="sxs-lookup"><span data-stu-id="73ade-117">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="73ade-118">可以不同於另一條從 P2 到 P1 P2 從 P1 同步處理狀態。</span><span class="sxs-lookup"><span data-stu-id="73ade-118">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="73ade-119">P1 至 P2，備份服務處於 「 穩定 」 狀態如果所有 P1 所做的變更會完全透過都複寫至 P2 內的同步處理間隔。</span><span class="sxs-lookup"><span data-stu-id="73ade-119">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="73ade-120">它是在 「 最終 」 狀態有必須從 P1 同步處理至 P2 沒有更多的變更。</span><span class="sxs-lookup"><span data-stu-id="73ade-120">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="73ade-121">這兩種狀態指出備份服務的快照集在執行指令程式時的時間。</span><span class="sxs-lookup"><span data-stu-id="73ade-121">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="73ade-122">並不表示傳回的狀態會保持為先。</span><span class="sxs-lookup"><span data-stu-id="73ade-122">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="73ade-123">特別是，「 最終 」 狀態會繼續保留如果 P1 不會產生任何變更之後執行指令程式。</span><span class="sxs-lookup"><span data-stu-id="73ade-123">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="73ade-124">這是在容錯 P1 移轉，至 P2 P1 一部分<STRONG>Invoke-cspoolfailover</STRONG>執行邏輯放入唯讀模式之後的情況下，則為 true。</span><span class="sxs-lookup"><span data-stu-id="73ade-124">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the <STRONG>Invoke-CsPoolfailover</STRONG> execution logic.</span></span>



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="73ade-125">若要取得特定集區的備份關係的相關資訊</span><span class="sxs-lookup"><span data-stu-id="73ade-125">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="73ade-126">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="73ade-126">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="73ade-127">若要強制備份服務同步處理</span><span class="sxs-lookup"><span data-stu-id="73ade-127">To force a Backup Service sync</span></span>

<span data-ttu-id="73ade-128">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="73ade-128">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

