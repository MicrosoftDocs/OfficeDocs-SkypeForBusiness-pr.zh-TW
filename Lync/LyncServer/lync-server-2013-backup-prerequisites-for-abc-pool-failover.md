---
title: Lync Server 2013： ABC 池容錯移轉的備份先決條件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37a6b5694d8eaa9467fafa8923bb97423fd6e33f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a><span data-ttu-id="8d60c-102">Lync Server 2013 中 ABC 池容錯移轉的備份先決條件</span><span class="sxs-lookup"><span data-stu-id="8d60c-102">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d60c-103">_**主題上次修改日期：** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="8d60c-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="8d60c-104">若要利用 ABC pool 容錯移轉程式來充分發揮最大益處，您必須先執行特定備份，然後才能發生災難及容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="8d60c-104">To get the maximum benefit from using the ABC pool failover procedure, you must perform certain backups before the disaster and failover happen:</span></span>

  - <span data-ttu-id="8d60c-105">您必須使用**Export CsLISConfiguration** Cmdlet，定期備份來自 pool A 的位置資訊服務（.lis）配置資料。</span><span class="sxs-lookup"><span data-stu-id="8d60c-105">You must regularly back up the Location Information Service (LIS) configuration data from pool A by using the **Export-CsLISConfiguration** cmdlet.</span></span>
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - <span data-ttu-id="8d60c-106">您必須定期使用**Export CsRgsConfiguration** Cmdlet 來備份 [pool A] 中的回應群組設定資料。</span><span class="sxs-lookup"><span data-stu-id="8d60c-106">You must regularly back up the Response Group configuration data in pool A by using the **Export-CsRgsConfiguration** cmdlet.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <span data-ttu-id="8d60c-107">一般來說，我們建議您執行每日備份，但如果您有大量的變更，您可能會想要排程更頻繁的備份。</span><span class="sxs-lookup"><span data-stu-id="8d60c-107">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="8d60c-108">災難事件中可能會遺失的資訊量，取決於您的備份頻率，以及變更的頻率與數量。</span><span class="sxs-lookup"><span data-stu-id="8d60c-108">The amount of information that you can lose in the event of a disaster depends on the frequency of your backups, as well as on the frequency and volume of changes.</span></span>
    
    <span data-ttu-id="8d60c-109">回應群組應用程式只能儲存一組每個池的應用層級設定。</span><span class="sxs-lookup"><span data-stu-id="8d60c-109">The Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="8d60c-110">您可以透過**CsRgsConfiguration** Cmdlet 來存取這些設定。</span><span class="sxs-lookup"><span data-stu-id="8d60c-110">These settings can be accessed through the **Get-CsRgsConfiguration** cmdlets.</span></span> <span data-ttu-id="8d60c-111">這些設定包括預設的 [隨用音樂保留] 設定、預設的 [音樂保留中] 音訊檔案、代理程式震鈴-回寬期間，以及通話內容配置。</span><span class="sxs-lookup"><span data-stu-id="8d60c-111">The settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ring-back grace period, and the call context configuration.</span></span> <span data-ttu-id="8d60c-112">透過**Import CsRgsConfiguration** Cmdlet，您可以使用**ReplaceExistingSettings**參數，將這些設定從一個池中轉移到另一個池中，但此操作會覆寫目的地池中的任何應用程式層級設定。</span><span class="sxs-lookup"><span data-stu-id="8d60c-112">These settings can be transferred from one pool to another through the **Import-CsRgsConfiguration** cmdlet by using the **ReplaceExistingSettings** parameter, but this operation will override any application-level settings in the destination pool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="8d60c-113">在個別位置，保留已用來設定回應群組應用程式的所有原始音訊檔案（也就是任何錄製或音樂保留盤案檔案）的備份複本。</span><span class="sxs-lookup"><span data-stu-id="8d60c-113">In a separate location, keep a backup copy of all the original audio files that have been used to configure the Response Group application (that is, any recordings or music-on-hold files).</span></span>

    
    </div>
    
    <span data-ttu-id="8d60c-114">如果您有任何自訂的已封存檔案，且已針對某個池中的通話駐留程式上傳，您應該在其他位置保留這些檔案的複本。</span><span class="sxs-lookup"><span data-stu-id="8d60c-114">If you have any customized music-on-hold files that have been uploaded for Call Park in a pool, you should keep a copy of these in another location.</span></span> <span data-ttu-id="8d60c-115">這些檔案不會作為 Lync Server 2013 災害復原程式的一部分進行備份，如果上傳到該池的檔案遭到損毀、損毀或清除，這些檔案就會遺失。</span><span class="sxs-lookup"><span data-stu-id="8d60c-115">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8d60c-116">通話駐留應用程式只能儲存一組設定，以及每個池中有一個自訂的音樂保留音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="8d60c-116">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="8d60c-117">您可以透過<STRONG>CsCpsConfiguration</STRONG> Cmdlet 來存取這些設定。</span><span class="sxs-lookup"><span data-stu-id="8d60c-117">These settings can be accessed through the <STRONG>Get-CsCpsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="8d60c-118">因為通話駐留的災害復原機制依賴于備份池的通話駐留應用程式，所以如果發生災難，主要池的設定就不會備份或保留。</span><span class="sxs-lookup"><span data-stu-id="8d60c-118">Because the disaster recovery mechanism for Call Park relies on the Call Park application of the backup pool, the settings of the primary pool are not backed up or preserved if a disaster occurs.</span></span> <span data-ttu-id="8d60c-119">如果主要的池遺失，則無法復原這些設定，而且當部署新的池來取代主要池時，通話寄存設定及任何自訂的音樂保留音訊檔案都必須重新設定。</span><span class="sxs-lookup"><span data-stu-id="8d60c-119">If the primary pool is lost, these settings cannot be recovered, and when a new pool is deployed to replace the primary pool, the Call Park settings and any customized music-on-hold audio file would need to be reconfigured.</span></span>

    
    </div>

  - <span data-ttu-id="8d60c-120">如果您將任何宣告設定為「未指派的數位語音」功能的一部分，我們建議您在初始配置期間，將任何原始音訊檔案的複本保留在其他位置。</span><span class="sxs-lookup"><span data-stu-id="8d60c-120">If you configure any announcements as part of the Unassigned Number Voice Feature, we recommend that you keep in another location a copy of any original audio file used during the initial configuration.</span></span> <span data-ttu-id="8d60c-121">如果您未執行此動作，您可以在已匯入音訊檔案的伺服器或池的檔案存放區中取得已設定音訊檔案的複本。</span><span class="sxs-lookup"><span data-stu-id="8d60c-121">If you did not do that, you can get a copy of the configured audio files in the file store of the server or pool to which the audio files were imported.</span></span> <span data-ttu-id="8d60c-122">這些檔案不會作為 Lync Server 2013 災害復原程式的一部分進行備份，如果上傳到該池的檔案遭到損毀、損毀或清除，這些檔案就會遺失。</span><span class="sxs-lookup"><span data-stu-id="8d60c-122">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="8d60c-123">若要從伺服器或文件庫的檔案存放區中複製所有用來設定 [未指派數位語音] 功能的音訊檔案，請使用：</span><span class="sxs-lookup"><span data-stu-id="8d60c-123">To copy all the audio files used to configure the Unassigned Number Voice Feature from the file store of a server or a pool, use:</span></span>
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - <span data-ttu-id="8d60c-124">如果您已在池中監視及封存資料庫，您應該使用 SQL Server 管理工具將其備份。</span><span class="sxs-lookup"><span data-stu-id="8d60c-124">If you have Monitoring and Archiving databases in a pool, you should use SQL Server management tools to back them up.</span></span> <span data-ttu-id="8d60c-125">在 ABC 容錯移轉程式中，如果 collocated 在 pool A 中，系統不會保留監視和封存資料庫，因為這些資料庫不是透過 Lync Server 備份服務來備份。</span><span class="sxs-lookup"><span data-stu-id="8d60c-125">In the ABC failover procedure, Monitoring and Archiving databases are not preserved if they are collocated in pool A, because these databases are not backed up through Lync Server Backup Service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

