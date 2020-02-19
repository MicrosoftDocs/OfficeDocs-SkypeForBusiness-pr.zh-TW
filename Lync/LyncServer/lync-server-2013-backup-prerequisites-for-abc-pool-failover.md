---
title: 'Lync Server 2013: ABC 備份先決條件集區容錯移轉'
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
ms.openlocfilehash: 4a23e93741400efe4744e9219a19ca2c0217a33e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a><span data-ttu-id="d4e67-102">Lync Server 2013 中的 ABC 集區容錯移轉備份先決條件</span><span class="sxs-lookup"><span data-stu-id="d4e67-102">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4e67-103">_**上次修改主題：** 2013年-03-26_</span><span class="sxs-lookup"><span data-stu-id="d4e67-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="d4e67-104">若要獲得最大效益使用 ABC 集區容錯移轉程序，您必須執行特定備份之前發生容錯移轉與嚴重損壞：</span><span class="sxs-lookup"><span data-stu-id="d4e67-104">To get the maximum benefit from using the ABC pool failover procedure, you must perform certain backups before the disaster and failover happen:</span></span>

  - <span data-ttu-id="d4e67-105">您必須定期備份位置資訊服務 (LIS) 組態資料從集區的使用**Export-cslisconfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d4e67-105">You must regularly back up the Location Information Service (LIS) configuration data from pool A by using the **Export-CsLISConfiguration** cmdlet.</span></span>
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - <span data-ttu-id="d4e67-106">您必須定期備份集區的回應群組組態資料使用**Export-csrgsconfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d4e67-106">You must regularly back up the Response Group configuration data in pool A by using the **Export-CsRgsConfiguration** cmdlet.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <span data-ttu-id="d4e67-107">一般而言，我們會建議您執行每日備份，但是如果您有大量變更，也許會想要排定更多次的備份。</span><span class="sxs-lookup"><span data-stu-id="d4e67-107">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="d4e67-108">您可能會遺失發生嚴重損壞的資訊數量取決於頻率的備份，以及在頻率與數量變更。</span><span class="sxs-lookup"><span data-stu-id="d4e67-108">The amount of information that you can lose in the event of a disaster depends on the frequency of your backups, as well as on the frequency and volume of changes.</span></span>
    
    <span data-ttu-id="d4e67-109">回應群組應用程式可以儲存只有一組每個集區的應用程式層級設定。</span><span class="sxs-lookup"><span data-stu-id="d4e67-109">The Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="d4e67-110">這些設定可透過**Get-csrgsconfiguration**指令程式。</span><span class="sxs-lookup"><span data-stu-id="d4e67-110">These settings can be accessed through the **Get-CsRgsConfiguration** cmdlets.</span></span> <span data-ttu-id="d4e67-111">設定包括預設的等候音樂上保留設定、 預設的等候音樂上保留音訊檔案、 代理回響鈴的寬限期，以及來電內容設定。</span><span class="sxs-lookup"><span data-stu-id="d4e67-111">The settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ring-back grace period, and the call context configuration.</span></span> <span data-ttu-id="d4e67-112">這些設定可以從一個集區中轉接至另一個透過**Import-csrgsconfiguration** cmdlet，使用**ReplaceExistingSettings**參數，但這項作業將會覆寫目的集區中的任何應用程式層級設定。</span><span class="sxs-lookup"><span data-stu-id="d4e67-112">These settings can be transferred from one pool to another through the **Import-CsRgsConfiguration** cmdlet by using the **ReplaceExistingSettings** parameter, but this operation will override any application-level settings in the destination pool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="d4e67-113">在不同的位置，保留所有的原始音訊檔案已用來設定回應群組應用程式 （亦即，任何錄製或在保留音樂檔案） 的備份複本。</span><span class="sxs-lookup"><span data-stu-id="d4e67-113">In a separate location, keep a backup copy of all the original audio files that have been used to configure the Response Group application (that is, any recordings or music-on-hold files).</span></span>

    
    </div>
    
    <span data-ttu-id="d4e67-114">如果您有任何自訂等候音樂上保留檔案已上載的通話駐留的集區中，您應保留一份這些在另一個位置。</span><span class="sxs-lookup"><span data-stu-id="d4e67-114">If you have any customized music-on-hold files that have been uploaded for Call Park in a pool, you should keep a copy of these in another location.</span></span> <span data-ttu-id="d4e67-115">這些檔案不會備份 Lync Server 2013 災害復原程序的一部分，他們將會遺失如果損毀、 損毀，或清除上傳至集區的檔案。</span><span class="sxs-lookup"><span data-stu-id="d4e67-115">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d4e67-116">通話駐留應用程式可以儲存只有一組設定與一個自訂等候音樂上保留音訊檔案每個集區。</span><span class="sxs-lookup"><span data-stu-id="d4e67-116">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="d4e67-117">這些設定可透過<STRONG>取得 CsCpsConfiguration</STRONG>指令程式。</span><span class="sxs-lookup"><span data-stu-id="d4e67-117">These settings can be accessed through the <STRONG>Get-CsCpsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="d4e67-118">通話駐留災害復原機制取決於備份集區的通話駐留應用程式，因為主要集區的設定不會備份或保留如果發生損毀。</span><span class="sxs-lookup"><span data-stu-id="d4e67-118">Because the disaster recovery mechanism for Call Park relies on the Call Park application of the backup pool, the settings of the primary pool are not backed up or preserved if a disaster occurs.</span></span> <span data-ttu-id="d4e67-119">如果主要集區是遺失，不能復原這些設定，以及新集區部署來取代主要集區]、 [通話駐留設定和 [任何自訂等候音樂-上-保留音訊檔案就必須重新設定。</span><span class="sxs-lookup"><span data-stu-id="d4e67-119">If the primary pool is lost, these settings cannot be recovered, and when a new pool is deployed to replace the primary pool, the Call Park settings and any customized music-on-hold audio file would need to be reconfigured.</span></span>

    
    </div>

  - <span data-ttu-id="d4e67-120">如果您未指派的號碼語音功能的一部分設定任何宣告，我們建議您保留在另一個位置的初始設定期間使用任何原始音訊檔案的複本。</span><span class="sxs-lookup"><span data-stu-id="d4e67-120">If you configure any announcements as part of the Unassigned Number Voice Feature, we recommend that you keep in another location a copy of any original audio file used during the initial configuration.</span></span> <span data-ttu-id="d4e67-121">如果您沒有這樣做，您可以取得一份伺服器或集區的音訊檔案都已匯入的檔案存放區中設定的音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="d4e67-121">If you did not do that, you can get a copy of the configured audio files in the file store of the server or pool to which the audio files were imported.</span></span> <span data-ttu-id="d4e67-122">這些檔案不會備份 Lync Server 2013 災害復原程序的一部分，他們將會遺失如果損毀、 損毀，或清除上傳至集區的檔案。</span><span class="sxs-lookup"><span data-stu-id="d4e67-122">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="d4e67-123">若要複製用來設定未指派號碼語音功能，從伺服器或集區的檔案存放區的所有音訊檔案，請使用：</span><span class="sxs-lookup"><span data-stu-id="d4e67-123">To copy all the audio files used to configure the Unassigned Number Voice Feature from the file store of a server or a pool, use:</span></span>
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - <span data-ttu-id="d4e67-124">如果您有監控和封存的集區中的資料庫，您應將其備份使用 SQL Server 管理工具。</span><span class="sxs-lookup"><span data-stu-id="d4e67-124">If you have Monitoring and Archiving databases in a pool, you should use SQL Server management tools to back them up.</span></span> <span data-ttu-id="d4e67-125">ABC 容錯移轉程序中，監控和封存資料庫不會保留如果他們組合在集區 A，因為這些資料庫不會備份透過 Lync Server 備份服務。</span><span class="sxs-lookup"><span data-stu-id="d4e67-125">In the ABC failover procedure, Monitoring and Archiving databases are not preserved if they are collocated in pool A, because these databases are not backed up through Lync Server Backup Service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

