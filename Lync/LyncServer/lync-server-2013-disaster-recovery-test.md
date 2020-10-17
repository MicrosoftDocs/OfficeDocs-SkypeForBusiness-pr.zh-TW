---
title: Lync Server 2013：災難修復測試
description: Lync Server 2013：災難修復測試。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa22abd37f656134c54381d63f29d3160ff85257
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557659"
---
# <a name="disaster-recovery-test-in-lync-server-2013"></a><span data-ttu-id="732fe-103">Lync Server 2013 中的嚴重損壞修復測試</span><span class="sxs-lookup"><span data-stu-id="732fe-103">Disaster recovery test in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="732fe-104">_**主題上次修改日期：** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="732fe-104">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="732fe-105">對 Lync Server 2013 集區伺服器執行系統復原，以測試您已記錄的嚴重損壞修復程式。</span><span class="sxs-lookup"><span data-stu-id="732fe-105">Perform a system recovery for a Lync Server 2013 pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="732fe-106">這項測試會模擬一部伺服器的完整硬體故障，並協助保證資源、計畫及資料可用於復原。</span><span class="sxs-lookup"><span data-stu-id="732fe-106">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data is available for recovery.</span></span> <span data-ttu-id="732fe-107">嘗試每月旋轉測試的焦點，使組織每次測試不同伺服器或其他裝置的失敗。</span><span class="sxs-lookup"><span data-stu-id="732fe-107">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span>

<span data-ttu-id="732fe-108">請注意，組織執行嚴重損壞修復測試的排程會有所不同。</span><span class="sxs-lookup"><span data-stu-id="732fe-108">Note that the schedule by which organizations perform Disaster Recovery testing will vary.</span></span> <span data-ttu-id="732fe-109">不會忽視或忽略嚴重損壞修復測試，這一點很重要。</span><span class="sxs-lookup"><span data-stu-id="732fe-109">It is very important that disaster recovery testing is not ignored or neglected.</span></span>

<div>


<span data-ttu-id="732fe-110">將 Lync Server 2013 拓撲、原則及設定設定匯出至檔案。</span><span class="sxs-lookup"><span data-stu-id="732fe-110">Export your Lync Server 2013 topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="732fe-111">除此之外，您也可以使用此檔案在升級、硬體故障或其他問題導致資料遺失的情況下，將此資訊還原至中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="732fe-111">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="732fe-112">將 Lync Server 2013 拓撲、原則及設定設定匯入中央管理存放區或本機電腦，如下列命令所示：</span><span class="sxs-lookup"><span data-stu-id="732fe-112">Import your Lync Server 2013 topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span>

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

<span data-ttu-id="732fe-113">若要備份 Lync Server 2013 資料，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="732fe-113">To back up production Lync Server 2013 data:</span></span>

  - <span data-ttu-id="732fe-114">使用標準 SQL Server 備份程式備份 RTC 和 LCSLog 資料庫，以將資料庫轉儲至檔案或磁帶轉儲裝置。</span><span class="sxs-lookup"><span data-stu-id="732fe-114">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>

  - <span data-ttu-id="732fe-115">使用協力廠商備份應用程式將資料備份至檔案或磁帶。</span><span class="sxs-lookup"><span data-stu-id="732fe-115">Use third-party backup application to back up the data to file or to tape.</span></span>

  - <span data-ttu-id="732fe-116">使用 Export-CsUserData Cmdlet 來建立整個 RTC 資料庫的 XML 匯出。</span><span class="sxs-lookup"><span data-stu-id="732fe-116">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>

  - <span data-ttu-id="732fe-117">使用檔案系統備份或協力廠商備份會議內容和合規性記錄檔。</span><span class="sxs-lookup"><span data-stu-id="732fe-117">Use the file system backup or third-party to back up meeting content and compliance logs.</span></span>

  - <span data-ttu-id="732fe-118">使用 Export-CsConfiguration 命令列工具備份 Lync Server 2013 設定。</span><span class="sxs-lookup"><span data-stu-id="732fe-118">Use the Export-CsConfiguration command-line tool to back up Lync Server 2013 settings.</span></span>

<span data-ttu-id="732fe-119">容錯移轉程式中的第一個步驟包括將使用者從生產集區強制移至嚴重損壞修復集區。</span><span class="sxs-lookup"><span data-stu-id="732fe-119">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span>

<span data-ttu-id="732fe-120">這將會強制移動，因為實際生產集區無法接受使用者重新安置。</span><span class="sxs-lookup"><span data-stu-id="732fe-120">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="732fe-121">除了 RTC SQL 資料庫上的記錄更新之外，Lync Server 2013 移動使用者程式也會變更使用者帳戶物件上的屬性。</span><span class="sxs-lookup"><span data-stu-id="732fe-121">The Lync Server 2013 move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span>

<span data-ttu-id="732fe-122">您可以透過下列兩個程式還原此資料：</span><span class="sxs-lookup"><span data-stu-id="732fe-122">This data can be restored through the following two processes:</span></span>

  - <span data-ttu-id="732fe-123">使用標準 SQL server 還原程式，或使用協力廠商備份/還原公用程式，可以從生產 SQL Server 從原始備份轉儲裝置還原 RTC 資料庫。</span><span class="sxs-lookup"><span data-stu-id="732fe-123">RTC database can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

  - <span data-ttu-id="732fe-124">您可以使用由實際執行 SQL Server 匯出的 XML 檔案，將使用者連絡人資料還原為 DBIMPEXP.exe 公用程式。</span><span class="sxs-lookup"><span data-stu-id="732fe-124">User contact data can be restored with the DBIMPEXP.exe utility using the XML file that was created from the production SQL Server export.</span></span>

<span data-ttu-id="732fe-125">還原此資料之後，使用者就能有效地連線至嚴重損壞修復 Lync Server 2013 集區，並照常運作。</span><span class="sxs-lookup"><span data-stu-id="732fe-125">After this data is restored, users can effectively connect to the Disaster Recovery Lync Server 2013 pool, and operate as usual.</span></span>

<span data-ttu-id="732fe-126">若要讓使用者能夠連線至嚴重損壞修復 Lync Server 2013 集區，將需要 DNS 記錄變更。</span><span class="sxs-lookup"><span data-stu-id="732fe-126">To enable users to connect to the Disaster Recovery Lync Server 2013 pool, a DNS record change will be required.</span></span>

<span data-ttu-id="732fe-127">使用的自動設定和 DNS SRV 記錄，用戶端將會參考實際執行的 Lync Server 2013 集區：</span><span class="sxs-lookup"><span data-stu-id="732fe-127">The production Lync Server 2013 pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

  - <span data-ttu-id="732fe-128">SRV： \_ sip。 \_Tls。\<domain\></span><span class="sxs-lookup"><span data-stu-id="732fe-128">SRV: \_sip.\_tls.\<domain\></span></span> <span data-ttu-id="732fe-129">/CNAME： SIP。\<domain\></span><span class="sxs-lookup"><span data-stu-id="732fe-129">/CNAME: SIP.\<domain\></span></span>

  - <span data-ttu-id="732fe-130">CNAME： SIP。\<domain\></span><span class="sxs-lookup"><span data-stu-id="732fe-130">CNAME: SIP.\<domain\></span></span> <span data-ttu-id="732fe-131">/cvc-pool-1.\<domain\></span><span class="sxs-lookup"><span data-stu-id="732fe-131">/cvc-pool-1.\<domain\></span></span>

<span data-ttu-id="732fe-132">若要協助容錯移轉，必須更新此 CNAME 記錄，以參考 DROCSPool FQDN：</span><span class="sxs-lookup"><span data-stu-id="732fe-132">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

  - <span data-ttu-id="732fe-133">CNAME： SIP。\<domain\></span><span class="sxs-lookup"><span data-stu-id="732fe-133">CNAME: SIP.\<domain\></span></span> <span data-ttu-id="732fe-134">/DROCSPool.\<domain\></span><span class="sxs-lookup"><span data-stu-id="732fe-134">/DROCSPool.\<domain\></span></span>

  - <span data-ttu-id="732fe-135">Sip。\<domain\></span><span class="sxs-lookup"><span data-stu-id="732fe-135">Sip.\<domain\></span></span>

  - <span data-ttu-id="732fe-136">Av。\<domain\></span><span class="sxs-lookup"><span data-stu-id="732fe-136">AV.\<domain\></span></span>

  - <span data-ttu-id="732fe-137">webconf.\<domain\></span><span class="sxs-lookup"><span data-stu-id="732fe-137">webconf.\<domain\></span></span>

  - <span data-ttu-id="732fe-138">OCSServices.\<domain\></span><span class="sxs-lookup"><span data-stu-id="732fe-138">OCSServices.\<domain\></span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="732fe-139">如需詳細的系統管理和管理程式，請參閱 <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">備份及還原 Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="732fe-139">For detailed administration and management procedures, see <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Backing up and restoring Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="732fe-140">另請參閱</span><span class="sxs-lookup"><span data-stu-id="732fe-140">See Also</span></span>


[<span data-ttu-id="732fe-141">在 Lync Server 2013 中規劃高可用性和嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="732fe-141">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[<span data-ttu-id="732fe-142">Lync Server 2013 中的備份和高可用性 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="732fe-142">Backup and high availability cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[<span data-ttu-id="732fe-143">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="732fe-143">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="732fe-144">備份及還原 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="732fe-144">Backing up and restoring Lync Server 2013</span></span>](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[<span data-ttu-id="732fe-145">管理 Lync Server 2013 災難修復、高可用性及備份服務</span><span class="sxs-lookup"><span data-stu-id="732fe-145">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

