---
title: Lync Server 2013： 嚴重損壞修復測試
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
ms.openlocfilehash: 4fc04381e315375fe0d5858c9a12ad577f6c8baf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a><span data-ttu-id="048db-102">Lync Server 2013 中的嚴重損壞修復測試</span><span class="sxs-lookup"><span data-stu-id="048db-102">Disaster recovery test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="048db-103">_**主題上次修改日期：** 2015年-01-26_</span><span class="sxs-lookup"><span data-stu-id="048db-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="048db-104">執行系統修復 Lync Server 2013 集區伺服器來測試您所記錄的災害復原程序。</span><span class="sxs-lookup"><span data-stu-id="048db-104">Perform a system recovery for a Lync Server 2013 pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="048db-105">這項測試將模擬一部伺服器，完整的硬體失敗，並可協助確保資源、 計劃及資料都可用於復原。</span><span class="sxs-lookup"><span data-stu-id="048db-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data is available for recovery.</span></span> <span data-ttu-id="048db-106">請試著旋轉測試每個月的焦點，以便您的組織測試不同伺服器或其他設備每次失敗。</span><span class="sxs-lookup"><span data-stu-id="048db-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span>

<span data-ttu-id="048db-107">請注意，依據組織執行嚴重損壞修復測試排程而有所不同。</span><span class="sxs-lookup"><span data-stu-id="048db-107">Note that the schedule by which organizations perform Disaster Recovery testing will vary.</span></span> <span data-ttu-id="048db-108">它是非常重要的嚴重損壞修復測試不會略過或是忽略。</span><span class="sxs-lookup"><span data-stu-id="048db-108">It is very important that disaster recovery testing is not ignored or neglected.</span></span>

<div>


<span data-ttu-id="048db-109">將 Lync Server 2013 拓撲、 原則和設定匯出至檔案。</span><span class="sxs-lookup"><span data-stu-id="048db-109">Export your Lync Server 2013 topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="048db-110">除此之外，這個檔案然後可以用來還原中央管理存放區的這項資訊之後升級、 硬體故障、 或某些其他問題，會導致資料遺失。</span><span class="sxs-lookup"><span data-stu-id="048db-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="048db-111">匯入您的 Lync Server 2013 拓撲、 原則和設定中央管理存放區，或本機電腦的下列命令所示：</span><span class="sxs-lookup"><span data-stu-id="048db-111">Import your Lync Server 2013 topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span>

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

<span data-ttu-id="048db-112">若要備份實際執行 Lync Server 2013 資料：</span><span class="sxs-lookup"><span data-stu-id="048db-112">To back up production Lync Server 2013 data:</span></span>

  - <span data-ttu-id="048db-113">備份 RTC 和 LCSLog 資料庫使用標準的 SQL Server 備份程序，以將資料庫檔案或磁帶時付出的傾印裝置傾印。</span><span class="sxs-lookup"><span data-stu-id="048db-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>

  - <span data-ttu-id="048db-114">使用協力廠商備份應用程式備份資料，檔案或到磁帶。</span><span class="sxs-lookup"><span data-stu-id="048db-114">Use third-party backup application to back up the data to file or to tape.</span></span>

  - <span data-ttu-id="048db-115">使用 Export-csuserdata cmdlet 來建立 XML 匯出的整個 RTC 資料庫。</span><span class="sxs-lookup"><span data-stu-id="048db-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>

  - <span data-ttu-id="048db-116">使用檔案系統備份或協力廠商備份會議內容及規範的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="048db-116">Use the file system backup or third-party to back up meeting content and compliance logs.</span></span>

  - <span data-ttu-id="048db-117">使用 Export-csconfiguration 命令列工具來備份 Lync Server 2013 設定。</span><span class="sxs-lookup"><span data-stu-id="048db-117">Use the Export-CsConfiguration command-line tool to back up Lync Server 2013 settings.</span></span>

<span data-ttu-id="048db-118">容錯移轉程序的第一個步驟包含實際執行集區的災害復原集區的使用者以強制的移動。</span><span class="sxs-lookup"><span data-stu-id="048db-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span>

<span data-ttu-id="048db-119">這將會以強制的移動，因為實際執行集區無法使用接受使用者重新配置。</span><span class="sxs-lookup"><span data-stu-id="048db-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="048db-120">使用 Lync Server 2013 移動使用者程序實際上就是使用者帳戶物件上的 RTC SQL 資料庫的記錄更新除了屬性的變更。</span><span class="sxs-lookup"><span data-stu-id="048db-120">The Lync Server 2013 move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span>

<span data-ttu-id="048db-121">此資料可透過下列兩個程序還原：</span><span class="sxs-lookup"><span data-stu-id="048db-121">This data can be restored through the following two processes:</span></span>

  - <span data-ttu-id="048db-122">可以還原 RTC 資料庫從原始備份傾印裝置從實際執行環境使用標準的 SQL Server 還原程序，或使用協力廠商的 SQL Server 備份/還原公用程式。</span><span class="sxs-lookup"><span data-stu-id="048db-122">RTC database can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

  - <span data-ttu-id="048db-123">使用當初用來建立實際執行 SQL Server 匯出的 XML 檔案 DBIMPEXP.exe 公用程式可以還原使用者連絡人資料。</span><span class="sxs-lookup"><span data-stu-id="048db-123">User contact data can be restored with the DBIMPEXP.exe utility using the XML file that was created from the production SQL Server export.</span></span>

<span data-ttu-id="048db-124">此資料還原之後，使用者可以有效地連線至災害復原 Lync Server 2013 集區，及操作像平常一樣。</span><span class="sxs-lookup"><span data-stu-id="048db-124">After this data is restored, users can effectively connect to the Disaster Recovery Lync Server 2013 pool, and operate as usual.</span></span>

<span data-ttu-id="048db-125">若要讓使用者能夠連線至災害復原 Lync Server 2013 集區，DNS 記錄變更將會是必要。</span><span class="sxs-lookup"><span data-stu-id="048db-125">To enable users to connect to the Disaster Recovery Lync Server 2013 pool, a DNS record change will be required.</span></span>

<span data-ttu-id="048db-126">實際執行 Lync Server 2013 集區將用戶端使用自動設定資料庫和 DNS SRV 記錄的參照：</span><span class="sxs-lookup"><span data-stu-id="048db-126">The production Lync Server 2013 pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

  - <span data-ttu-id="048db-127">SRV: \_sip。\_tls。\<網域\>/CNAME: SIP。\<網域\></span><span class="sxs-lookup"><span data-stu-id="048db-127">SRV: \_sip.\_tls.\<domain\> /CNAME: SIP.\<domain\></span></span>

  - <span data-ttu-id="048db-128">CNAME: SIP。\<網域\>/cvc-pool-1。\<網域\></span><span class="sxs-lookup"><span data-stu-id="048db-128">CNAME: SIP.\<domain\> /cvc-pool-1.\<domain\></span></span>

<span data-ttu-id="048db-129">若要加速容錯移轉，您必須更新此 CNAME 記錄，以參照 DROCSPool FQDN:</span><span class="sxs-lookup"><span data-stu-id="048db-129">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

  - <span data-ttu-id="048db-130">CNAME: SIP。\<網域\>/DROCSPool。\<網域\></span><span class="sxs-lookup"><span data-stu-id="048db-130">CNAME: SIP.\<domain\> /DROCSPool.\<domain\></span></span>

  - <span data-ttu-id="048db-131">Sip。\<網域\></span><span class="sxs-lookup"><span data-stu-id="048db-131">Sip.\<domain\></span></span>

  - <span data-ttu-id="048db-132">AV.\<網域\></span><span class="sxs-lookup"><span data-stu-id="048db-132">AV.\<domain\></span></span>

  - <span data-ttu-id="048db-133">fea-webconf-service。\<網域\></span><span class="sxs-lookup"><span data-stu-id="048db-133">webconf.\<domain\></span></span>

  - <span data-ttu-id="048db-134">OCSServices。\<網域\></span><span class="sxs-lookup"><span data-stu-id="048db-134">OCSServices.\<domain\></span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="048db-135">如需詳細的系統管理與管理程序，請參閱<A href="lync-server-2013-backing-up-and-restoring-lync-server.md">備份和還原 Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="048db-135">For detailed administration and management procedures, see <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Backing up and restoring Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="048db-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="048db-136">See Also</span></span>


[<span data-ttu-id="048db-137">規劃 Lync Server 2013 中的高可用性和災害復原</span><span class="sxs-lookup"><span data-stu-id="048db-137">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[<span data-ttu-id="048db-138">備份與 Lync Server 2013 中的高可用性 cmdlet</span><span class="sxs-lookup"><span data-stu-id="048db-138">Backup and high availability cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[<span data-ttu-id="048db-139">Import-csconfiguration</span><span class="sxs-lookup"><span data-stu-id="048db-139">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="048db-140">備份及還原 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="048db-140">Backing up and restoring Lync Server 2013</span></span>](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[<span data-ttu-id="048db-141">管理 Lync Server 2013 災害復原、 高可用性及備份服務</span><span class="sxs-lookup"><span data-stu-id="048db-141">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

