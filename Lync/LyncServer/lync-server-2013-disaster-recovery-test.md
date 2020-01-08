---
title: Lync Server 2013：災害復原測試
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9b17f5841cad96cb83399082f61c00194ec4828
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a><span data-ttu-id="aebc4-102">Lync Server 2013 中的災害復原測試</span><span class="sxs-lookup"><span data-stu-id="aebc4-102">Disaster recovery test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aebc4-103">_**主題上次修改日期：** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="aebc4-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="aebc4-104">針對 Lync Server 2013 pool server 執行系統復原，以測試您已記錄的災害復原程式。</span><span class="sxs-lookup"><span data-stu-id="aebc4-104">Perform a system recovery for a Lync Server 2013 pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="aebc4-105">本測試將會模擬一台伺服器的完整硬體故障狀況，並將協助保證各項資源、計畫和資料都可復原。</span><span class="sxs-lookup"><span data-stu-id="aebc4-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data is available for recovery.</span></span> <span data-ttu-id="aebc4-106">請嘗試每月變換測試重點，以便您組織每次都能測試不同伺服器的故障狀況或設備的其他部件。</span><span class="sxs-lookup"><span data-stu-id="aebc4-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span>

<span data-ttu-id="aebc4-p102">請注意，組織執行災害復原測試的排程各不相同，切勿忽略或疏於進行災害復原測試。</span><span class="sxs-lookup"><span data-stu-id="aebc4-p102">Note that the schedule by which organizations perform Disaster Recovery testing will vary. It is very important that disaster recovery testing is not ignored or neglected.</span></span>

<div>


<span data-ttu-id="aebc4-109">將您的 Lync Server 2013 拓撲、原則和配置設定匯出至檔案。</span><span class="sxs-lookup"><span data-stu-id="aebc4-109">Export your Lync Server 2013 topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="aebc4-110">除此之外，在升級、發生硬體故障或某些其他問題而造成資料遺失之後，此檔案還可在用於將此資訊還原至中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="aebc4-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="aebc4-111">將您的 Lync Server 2013 拓撲、原則和設定設定匯入中央管理儲存體或本機電腦，如下列命令所示：</span><span class="sxs-lookup"><span data-stu-id="aebc4-111">Import your Lync Server 2013 topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span>

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

<span data-ttu-id="aebc4-112">若要備份 Lync Server 2013 的資料：</span><span class="sxs-lookup"><span data-stu-id="aebc4-112">To back up production Lync Server 2013 data:</span></span>

  - <span data-ttu-id="aebc4-113">使用標準的 SQL Server 備份程式將資料庫轉儲至檔案或磁帶轉儲裝置，以備份 RTC 及 LCSLog 資料庫。</span><span class="sxs-lookup"><span data-stu-id="aebc4-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>

  - <span data-ttu-id="aebc4-114">使用協力廠商備份應用程式，將資料備份至檔案或磁帶。</span><span class="sxs-lookup"><span data-stu-id="aebc4-114">Use third-party backup application to back up the data to file or to tape.</span></span>

  - <span data-ttu-id="aebc4-115">使用 Export-CsUserData cmdlet 來建立整個 RTC 資料庫的 XML 匯出。</span><span class="sxs-lookup"><span data-stu-id="aebc4-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>

  - <span data-ttu-id="aebc4-116">使用檔案系統備份或協力廠商來備份會議內容和規範記錄。</span><span class="sxs-lookup"><span data-stu-id="aebc4-116">Use the file system backup or third-party to back up meeting content and compliance logs.</span></span>

  - <span data-ttu-id="aebc4-117">使用 Export CsConfiguration 命令列工具來備份 Lync Server 2013 設定。</span><span class="sxs-lookup"><span data-stu-id="aebc4-117">Use the Export-CsConfiguration command-line tool to back up Lync Server 2013 settings.</span></span>

<span data-ttu-id="aebc4-118">容錯移轉程序的第一步驟包含將使用者從生產集區強制移至災害復原集區。</span><span class="sxs-lookup"><span data-stu-id="aebc4-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span>

<span data-ttu-id="aebc4-119">此一步驟將為強制移動，因為生產集區將無法接受使用者遷移。</span><span class="sxs-lookup"><span data-stu-id="aebc4-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="aebc4-120">除了 RTC SQL 資料庫上的記錄更新之外，Lync Server 2013 移動使用者程式也會對使用者帳戶物件上的屬性有實際的變更。</span><span class="sxs-lookup"><span data-stu-id="aebc4-120">The Lync Server 2013 move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span>

<span data-ttu-id="aebc4-121">這項資料可透過下列兩項程序還原：</span><span class="sxs-lookup"><span data-stu-id="aebc4-121">This data can be restored through the following two processes:</span></span>

  - <span data-ttu-id="aebc4-122">您可以使用標準的 SQL Server 還原程式，或使用協力廠商的備份/還原公用程式，從生產 SQL Server 上的原始備份轉儲裝置還原 RTC 資料庫。</span><span class="sxs-lookup"><span data-stu-id="aebc4-122">RTC database can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

  - <span data-ttu-id="aebc4-123">使用從生產 SQL Server 匯出建立的 XML 檔案便可透過 DBIMPEXP.exe 公用程式還原使用者聯絡資料。</span><span class="sxs-lookup"><span data-stu-id="aebc4-123">User contact data can be restored with the DBIMPEXP.exe utility using the XML file that was created from the production SQL Server export.</span></span>

<span data-ttu-id="aebc4-124">還原此資料之後，使用者就能有效地連線至災害復原 Lync Server 2013 池，並照常運作。</span><span class="sxs-lookup"><span data-stu-id="aebc4-124">After this data is restored, users can effectively connect to the Disaster Recovery Lync Server 2013 pool, and operate as usual.</span></span>

<span data-ttu-id="aebc4-125">若要讓使用者能夠連線到災害復原 Lync Server 2013 池，必須變更 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="aebc4-125">To enable users to connect to the Disaster Recovery Lync Server 2013 pool, a DNS record change will be required.</span></span>

<span data-ttu-id="aebc4-126">用戶端將會使用自動設定和 DNS SRV 記錄來參照生產 Lync Server 2013 池：</span><span class="sxs-lookup"><span data-stu-id="aebc4-126">The production Lync Server 2013 pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

  - <span data-ttu-id="aebc4-127">SRV： \_sip。\_tls。\<網域\> /CNAME： SIP。\<網域\></span><span class="sxs-lookup"><span data-stu-id="aebc4-127">SRV: \_sip.\_tls.\<domain\> /CNAME: SIP.\<domain\></span></span>

  - <span data-ttu-id="aebc4-128">CNAME： SIP。\<網域\> /cvc-pool-1。\<網域\></span><span class="sxs-lookup"><span data-stu-id="aebc4-128">CNAME: SIP.\<domain\> /cvc-pool-1.\<domain\></span></span>

<span data-ttu-id="aebc4-129">若要輔助容錯移轉，必須更新這項 CNAME 記錄才能參考 DROCSPool FQDN：</span><span class="sxs-lookup"><span data-stu-id="aebc4-129">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

  - <span data-ttu-id="aebc4-130">CNAME： SIP。\<網域\> /DROCSPool。\<網域\></span><span class="sxs-lookup"><span data-stu-id="aebc4-130">CNAME: SIP.\<domain\> /DROCSPool.\<domain\></span></span>

  - <span data-ttu-id="aebc4-131">呼吸.\<網域\></span><span class="sxs-lookup"><span data-stu-id="aebc4-131">Sip.\<domain\></span></span>

  - <span data-ttu-id="aebc4-132">AV.\<網域\></span><span class="sxs-lookup"><span data-stu-id="aebc4-132">AV.\<domain\></span></span>

  - <span data-ttu-id="aebc4-133">webconf.\<網域\></span><span class="sxs-lookup"><span data-stu-id="aebc4-133">webconf.\<domain\></span></span>

  - <span data-ttu-id="aebc4-134">OCSServices.\<網域\></span><span class="sxs-lookup"><span data-stu-id="aebc4-134">OCSServices.\<domain\></span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aebc4-135">如需詳細的管理與管理程式，請參閱<A href="lync-server-2013-backing-up-and-restoring-lync-server.md">備份和還原 Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="aebc4-135">For detailed administration and management procedures, see <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Backing up and restoring Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aebc4-136">請參閱</span><span class="sxs-lookup"><span data-stu-id="aebc4-136">See Also</span></span>


[<span data-ttu-id="aebc4-137">在 Lync Server 2013 中規劃高可用性和災害復原</span><span class="sxs-lookup"><span data-stu-id="aebc4-137">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[<span data-ttu-id="aebc4-138">Lync Server 2013 中的備份和高可用性 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="aebc4-138">Backup and high availability cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[<span data-ttu-id="aebc4-139">匯入-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="aebc4-139">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="aebc4-140">備份和還原 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aebc4-140">Backing up and restoring Lync Server 2013</span></span>](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[<span data-ttu-id="aebc4-141">管理 Lync Server 2013 災害復原、高可用性及備份服務</span><span class="sxs-lookup"><span data-stu-id="aebc4-141">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

