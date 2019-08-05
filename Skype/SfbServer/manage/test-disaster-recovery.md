---
title: 商務用 Skype Server 中的災害復原測試
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 針對商務用 Skype 伺服器池伺服器執行系統復原, 以測試您已記錄的災害復原程式
ms.openlocfilehash: d65f8bfa512a3954728e09d659b571335d32a379
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188497"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="617d9-103">商務用 Skype Server 中的災害復原測試</span><span class="sxs-lookup"><span data-stu-id="617d9-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="617d9-104">針對商務用 Skype 伺服器池伺服器執行系統復原, 以測試您已記錄的災害復原程式。</span><span class="sxs-lookup"><span data-stu-id="617d9-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="617d9-105">這個測試將會模擬一台伺服器的完整硬體故障, 並將協助保證資源、方案及資料可供恢復使用。</span><span class="sxs-lookup"><span data-stu-id="617d9-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="617d9-106">請嘗試每月變換測試重點，以便您組織每次都能測試不同伺服器的故障狀況或設備的其他部件。</span><span class="sxs-lookup"><span data-stu-id="617d9-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="617d9-p102">請注意，組織執行災害復原測試的排程各不相同，切勿忽略或疏於進行災害復原測試。</span><span class="sxs-lookup"><span data-stu-id="617d9-p102">Note that the schedule by which organizations perform Disaster Recovery testing will vary. It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="617d9-109">將商務用 Skype 伺服器拓撲、原則和設定設定匯出至檔案。</span><span class="sxs-lookup"><span data-stu-id="617d9-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="617d9-110">除此之外，在升級、發生硬體故障或某些其他問題而造成資料遺失之後，此檔案還可在用於將此資訊還原至中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="617d9-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="617d9-111">將商務用 Skype 伺服器拓朴、原則和設定的設定匯入到中央管理商店或本機電腦上, 如下列命令所示:</span><span class="sxs-lookup"><span data-stu-id="617d9-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="617d9-112">若要備份生產資料:</span><span class="sxs-lookup"><span data-stu-id="617d9-112">To back up production data:</span></span>

- <span data-ttu-id="617d9-113">使用標準的 SQL Server 備份程式將資料庫轉儲至檔案或磁帶轉儲裝置, 以備份 RTC 及 LCSLog 資料庫。</span><span class="sxs-lookup"><span data-stu-id="617d9-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="617d9-114">使用協力廠商備份應用程式，將資料備份至檔案或磁帶。</span><span class="sxs-lookup"><span data-stu-id="617d9-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="617d9-115">使用 Export-CsUserData cmdlet 來建立整個 RTC 資料庫的 XML 匯出。</span><span class="sxs-lookup"><span data-stu-id="617d9-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="617d9-116">使用檔案系統備份或協力廠商備份來備份會議內容和合規性記錄。</span><span class="sxs-lookup"><span data-stu-id="617d9-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="617d9-117">使用 Export CsConfiguration 命令列工具來備份商務用 Skype Server 設定。</span><span class="sxs-lookup"><span data-stu-id="617d9-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="617d9-118">容錯移轉程序的第一步驟包含將使用者從生產集區強制移至災害復原集區。</span><span class="sxs-lookup"><span data-stu-id="617d9-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="617d9-119">此一步驟將為強制移動，因為生產集區將無法接受使用者遷移。</span><span class="sxs-lookup"><span data-stu-id="617d9-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="617d9-120">除了 RTC SQL 資料庫上的記錄更新之外, 商務用 Skype Server 移動使用者程式也會對使用者帳戶物件上的屬性有實際的變更。</span><span class="sxs-lookup"><span data-stu-id="617d9-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="617d9-121">您可以使用標準的 SQL Server 還原程式, 或使用協力廠商的備份/還原公用程式, 從生產 SQL Server 上的原始備份轉儲裝置還原此資料。</span><span class="sxs-lookup"><span data-stu-id="617d9-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="617d9-122">還原此資料之後, 使用者就能有效地連線到災害復原池, 並正常運作。</span><span class="sxs-lookup"><span data-stu-id="617d9-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="617d9-123">若要讓使用者能夠連線到災害復原池, 就必須變更 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="617d9-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="617d9-124">用戶端將會使用自動設定和 DNS SRV 記錄來參照商務用 Skype 泳池池:</span><span class="sxs-lookup"><span data-stu-id="617d9-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="617d9-125">SRV: _sip. _tls。\<網域>/CNAME: SIP。\<網域></span><span class="sxs-lookup"><span data-stu-id="617d9-125">SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="617d9-126">CNAME: SIP。\<網域>/cvc-pool-1。\<網域></span><span class="sxs-lookup"><span data-stu-id="617d9-126">CNAME: SIP.\<domain> /cvc-pool-1.\<domain></span></span>

<span data-ttu-id="617d9-127">若要輔助容錯移轉，必須更新這項 CNAME 記錄才能參考 DROCSPool FQDN：</span><span class="sxs-lookup"><span data-stu-id="617d9-127">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="617d9-128">CNAME: SIP。<domain></span><span class="sxs-lookup"><span data-stu-id="617d9-128">CNAME: SIP.<domain></span></span> <span data-ttu-id="617d9-129">/DROCSPool.\<網域></span><span class="sxs-lookup"><span data-stu-id="617d9-129">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="617d9-130">呼吸.\<網域></span><span class="sxs-lookup"><span data-stu-id="617d9-130">Sip.\<domain></span></span>
- <span data-ttu-id="617d9-131">AV.\<網域></span><span class="sxs-lookup"><span data-stu-id="617d9-131">AV.\<domain></span></span>
- <span data-ttu-id="617d9-132">webconf.\<網域></span><span class="sxs-lookup"><span data-stu-id="617d9-132">webconf.\<domain></span></span>
