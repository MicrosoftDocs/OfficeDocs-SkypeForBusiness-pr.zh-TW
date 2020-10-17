---
title: Lync Server 2013： ABC 集區容錯移轉的備份必要條件
description: Lync Server 2013： ABC 集區容錯移轉的備份必要條件。
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
ms.openlocfilehash: 05eb0d2ad50f1ed4f04964158fb5d22d079f3b50
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552329"
---
# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a><span data-ttu-id="b3f73-103">Lync Server 2013 中的 ABC 集區容錯移轉的備份必要條件</span><span class="sxs-lookup"><span data-stu-id="b3f73-103">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3f73-104">_**主題上次修改日期：** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="b3f73-104">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="b3f73-105">若要取得使用 ABC 集區容錯移轉程式的最大好處，您必須先執行某些備份，然後才會發生災難和容錯移轉：</span><span class="sxs-lookup"><span data-stu-id="b3f73-105">To get the maximum benefit from using the ABC pool failover procedure, you must perform certain backups before the disaster and failover happen:</span></span>

  - <span data-ttu-id="b3f73-106">您必須使用 **export-cslisconfiguration 指令程式** ，定期備份組區 A 中 (.lis) 設定資料的位置資訊服務。</span><span class="sxs-lookup"><span data-stu-id="b3f73-106">You must regularly back up the Location Information Service (LIS) configuration data from pool A by using the **Export-CsLISConfiguration** cmdlet.</span></span>
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - <span data-ttu-id="b3f73-107">您必須使用 **Export-CsRgsConfiguration** Cmdlet，定期備份組區 A 中的回應群組設定資料。</span><span class="sxs-lookup"><span data-stu-id="b3f73-107">You must regularly back up the Response Group configuration data in pool A by using the **Export-CsRgsConfiguration** cmdlet.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <span data-ttu-id="b3f73-108">一般而言，我們會建議您執行每日備份，但是如果您有大量變更，也許會想要排定更多次的備份。</span><span class="sxs-lookup"><span data-stu-id="b3f73-108">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="b3f73-109">發生嚴重損壞時，您可能會遺失的資訊量取決於備份頻率，以及變更的頻率與數量。</span><span class="sxs-lookup"><span data-stu-id="b3f73-109">The amount of information that you can lose in the event of a disaster depends on the frequency of your backups, as well as on the frequency and volume of changes.</span></span>
    
    <span data-ttu-id="b3f73-110">回應群組應用程式只能為每個集區儲存一組應用層級設定。</span><span class="sxs-lookup"><span data-stu-id="b3f73-110">The Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="b3f73-111">您可以透過 **Get-CsRgsConfiguration** Cmdlet 來存取這些設定。</span><span class="sxs-lookup"><span data-stu-id="b3f73-111">These settings can be accessed through the **Get-CsRgsConfiguration** cmdlets.</span></span> <span data-ttu-id="b3f73-112">這些設定包含預設的等候音樂設定、預設的等候音樂音訊檔、代理程式的環回寬限期及呼叫內容設定。</span><span class="sxs-lookup"><span data-stu-id="b3f73-112">The settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ring-back grace period, and the call context configuration.</span></span> <span data-ttu-id="b3f73-113">您可以使用**ReplaceExistingSettings**參數，透過**Import-CsRgsConfiguration** Cmdlet 從一個集區轉接至另一個集區，但此作業將會覆寫目的地集區中的任何應用層級設定。</span><span class="sxs-lookup"><span data-stu-id="b3f73-113">These settings can be transferred from one pool to another through the **Import-CsRgsConfiguration** cmdlet by using the **ReplaceExistingSettings** parameter, but this operation will override any application-level settings in the destination pool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="b3f73-114">在不同的位置，保留已用來設定回應群組應用程式之所有原始音訊檔案的備份副本， (也就是說，任何錄製或暫止的音樂檔案) 。</span><span class="sxs-lookup"><span data-stu-id="b3f73-114">In a separate location, keep a backup copy of all the original audio files that have been used to configure the Response Group application (that is, any recordings or music-on-hold files).</span></span>

    
    </div>
    
    <span data-ttu-id="b3f73-115">如果您有任何已針對集區中的通話駐留上傳的任何自訂已等候音樂檔案，您應該將這些檔案複本保留在其他位置。</span><span class="sxs-lookup"><span data-stu-id="b3f73-115">If you have any customized music-on-hold files that have been uploaded for Call Park in a pool, you should keep a copy of these in another location.</span></span> <span data-ttu-id="b3f73-116">這些檔案不會作為 Lync Server 2013 嚴重損壞修復程式的一部分進行備份，如果上傳至集區的檔案損毀、損毀或已被清除，將會遺失。</span><span class="sxs-lookup"><span data-stu-id="b3f73-116">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b3f73-117">通話駐留應用程式只能為每個集區儲存一組設定及一個自訂的等候音樂音訊檔。</span><span class="sxs-lookup"><span data-stu-id="b3f73-117">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="b3f73-118">您可以透過 <STRONG>CsCpsConfiguration</STRONG> Cmdlet 來存取這些設定。</span><span class="sxs-lookup"><span data-stu-id="b3f73-118">These settings can be accessed through the <STRONG>Get-CsCpsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="b3f73-119">由於通話駐留的嚴重損壞復原機制取決於備份組區的通話駐留應用程式，因此當發生災難時，不會備份或保留主要集區的設定。</span><span class="sxs-lookup"><span data-stu-id="b3f73-119">Because the disaster recovery mechanism for Call Park relies on the Call Park application of the backup pool, the settings of the primary pool are not backed up or preserved if a disaster occurs.</span></span> <span data-ttu-id="b3f73-120">如果丟失主要集區，將無法復原這些設定，而且當部署新集區以取代主要集區時，必須重新設定通話駐留設定和任何自訂的等候音樂音訊檔。</span><span class="sxs-lookup"><span data-stu-id="b3f73-120">If the primary pool is lost, these settings cannot be recovered, and when a new pool is deployed to replace the primary pool, the Call Park settings and any customized music-on-hold audio file would need to be reconfigured.</span></span>

    
    </div>

  - <span data-ttu-id="b3f73-121">如果您將任何宣告設定為「未指派的號碼語音」功能的一部分，我們建議您保留另一個位置，以供初始設定期間使用的任何原始音訊檔的副本。</span><span class="sxs-lookup"><span data-stu-id="b3f73-121">If you configure any announcements as part of the Unassigned Number Voice Feature, we recommend that you keep in another location a copy of any original audio file used during the initial configuration.</span></span> <span data-ttu-id="b3f73-122">如果您未這麼做，您可以在匯入音訊檔的伺服器或集區的檔案存放區中取得所設定的音訊檔複本。</span><span class="sxs-lookup"><span data-stu-id="b3f73-122">If you did not do that, you can get a copy of the configured audio files in the file store of the server or pool to which the audio files were imported.</span></span> <span data-ttu-id="b3f73-123">這些檔案不會作為 Lync Server 2013 嚴重損壞修復程式的一部分進行備份，如果上傳至集區的檔案損毀、損毀或已被清除，將會遺失。</span><span class="sxs-lookup"><span data-stu-id="b3f73-123">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="b3f73-124">若要從伺服器或集區的檔案存放區中複製所有用來設定未指派號碼語音功能的音訊檔，請使用：</span><span class="sxs-lookup"><span data-stu-id="b3f73-124">To copy all the audio files used to configure the Unassigned Number Voice Feature from the file store of a server or a pool, use:</span></span>
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - <span data-ttu-id="b3f73-125">如果您在集區中有監控和封存資料庫，您應該使用 SQL Server 管理工具來備份資料庫。</span><span class="sxs-lookup"><span data-stu-id="b3f73-125">If you have Monitoring and Archiving databases in a pool, you should use SQL Server management tools to back them up.</span></span> <span data-ttu-id="b3f73-126">在 ABC 容錯移轉程式中，如果在集區 A 中組合這些資料庫，則不會保留監控和封存資料庫，因為這些資料庫不是透過 Lync Server 備份服務來備份。</span><span class="sxs-lookup"><span data-stu-id="b3f73-126">In the ABC failover procedure, Monitoring and Archiving databases are not preserved if they are collocated in pool A, because these databases are not backed up through Lync Server Backup Service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

