---
title: Lync Server 2013：備份核心資料和設定
description: Lync Server 2013：備份核心資料和設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 637eeb950a3b8380f6e756f46a5083f51b5d7e1f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543739"
---
# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="d9ed5-103">在 Lync Server 2013 中備份核心資料和設定</span><span class="sxs-lookup"><span data-stu-id="d9ed5-103">Backing up core data and settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9ed5-104">_**主題上次修改日期：** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="d9ed5-104">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="d9ed5-105">下列程式會使用 Lync Server 管理命令介面 Cmdlet，為核心服務的設定和資料建立備份檔案。</span><span class="sxs-lookup"><span data-stu-id="d9ed5-105">The following procedures use Lync Server Management Shell cmdlets to create backup files for settings and data for core services.</span></span> <span data-ttu-id="d9ed5-106">如需本節所用工具（包括其所在位置）的詳細資訊，請參閱 [Lync Server 2013 中的備份和還原需求：工具和許可權](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="d9ed5-106">For details about the tools used in this section, including where they are located, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span> <span data-ttu-id="d9ed5-107">如需備份封存與監控資料的詳細資訊，請參閱 [在 Lync Server 2013 中備份封存和監控資料庫](lync-server-2013-backing-up-archiving-and-monitoring-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="d9ed5-107">For details about backing up Archiving and Monitoring data, see [Backing up Archiving and Monitoring databases in Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d9ed5-108">本節中備份中央管理存放區的步驟包括設定和設定進行封存及監視。</span><span class="sxs-lookup"><span data-stu-id="d9ed5-108">The step in this section to back up the Central Management store includes the settings and configuration for Archiving and Monitoring.</span></span>



</div>

<span data-ttu-id="d9ed5-109">您可以本機或遠端執行本節中說明的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d9ed5-109">You can run the cmdlets described in this section locally or remotely.</span></span>

<div>

## <a name="to-back-up-core-data-and-settings"></a><span data-ttu-id="d9ed5-110">若要備份核心資料與設定</span><span class="sxs-lookup"><span data-stu-id="d9ed5-110">To back up core data and settings</span></span>

1.  <span data-ttu-id="d9ed5-111">以屬於 RTCUniversalServerAdmins 群組成員身分的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d9ed5-111">From a user account that is a member of the RTCUniversalServerAdmins group, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d9ed5-112">若要儲存您在下列步驟中所建立的備份，請建立新的共用資料夾，並將 **$Backup** 所參照的路徑更新為新的共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="d9ed5-112">To store the backups you create in the following steps, create a new shared folder and update the path referenced by **$Backup** to the new shared folder.</span></span>

3.  <span data-ttu-id="d9ed5-113">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d9ed5-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="d9ed5-114">備份中央管理存放區設定檔。</span><span class="sxs-lookup"><span data-stu-id="d9ed5-114">Back up the Central Management store configuration file.</span></span> <span data-ttu-id="d9ed5-115">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="d9ed5-115">At the command line, type the following:</span></span>
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="d9ed5-116">例如：</span><span class="sxs-lookup"><span data-stu-id="d9ed5-116">For example:</span></span>
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d9ed5-117">這個步驟會將您的 Lync 伺服器拓撲、原則及設定匯出至檔案。</span><span class="sxs-lookup"><span data-stu-id="d9ed5-117">This step exports your Lync Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="d9ed5-118">在備份拓撲資料部分，無需其他步驟。</span><span class="sxs-lookup"><span data-stu-id="d9ed5-118">No other step is required to backup topology data.</span></span>

    
    </div>

5.  <span data-ttu-id="d9ed5-119">將備份的中央管理存放區配置檔案複製到 $Backup \\ 。</span><span class="sxs-lookup"><span data-stu-id="d9ed5-119">Copy the backed-up Central Management store configuration file to $Backup\\.</span></span>

6.  <span data-ttu-id="d9ed5-p104">備份位置資訊服務資料。在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="d9ed5-p104">Back up Location Information service data. At the command line, type the following:</span></span>
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="d9ed5-122">例如：</span><span class="sxs-lookup"><span data-stu-id="d9ed5-122">For example:</span></span>
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  <span data-ttu-id="d9ed5-123">將備份的位置資訊服務配置檔案複製到 $Backup \\ 。</span><span class="sxs-lookup"><span data-stu-id="d9ed5-123">Copy the backed-up Location Information service configuration file to $Backup\\.</span></span>

8.  <span data-ttu-id="d9ed5-124">在每個前端集區和每個 Standard Edition server 的後端資料庫上備份使用者資料。</span><span class="sxs-lookup"><span data-stu-id="d9ed5-124">Back up user data on every back-end database of a Front End pool and every Standard Edition server.</span></span> <span data-ttu-id="d9ed5-125">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="d9ed5-125">At the command line, type the following:</span></span>
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    <span data-ttu-id="d9ed5-126">例如：</span><span class="sxs-lookup"><span data-stu-id="d9ed5-126">For example:</span></span>
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  <span data-ttu-id="d9ed5-127">將備份的使用者檔案複製到 $Backup \\ 。</span><span class="sxs-lookup"><span data-stu-id="d9ed5-127">Copy the backed up user file to $Backup\\.</span></span>

10. <span data-ttu-id="d9ed5-128">在執行回應群組應用程式的每個集區上，備份回應群組設定。</span><span class="sxs-lookup"><span data-stu-id="d9ed5-128">On every pool that runs the Response Group application, back up the Response Group configuration.</span></span> <span data-ttu-id="d9ed5-129">執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d9ed5-129">Do the following:</span></span>
    
    1.  <span data-ttu-id="d9ed5-130">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="d9ed5-130">At the command line, type:</span></span>
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        <span data-ttu-id="d9ed5-131">例如：</span><span class="sxs-lookup"><span data-stu-id="d9ed5-131">For example:</span></span>
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. <span data-ttu-id="d9ed5-132">將備份的回應群組配置檔案複製到 $Backup \\ 。</span><span class="sxs-lookup"><span data-stu-id="d9ed5-132">Copy the backed up Response Group configuration file to $Backup\\.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

