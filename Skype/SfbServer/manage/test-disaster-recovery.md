---
title: 商務用 Skype Server 中的嚴重損壞修復測試
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 為商務用 Skype 伺服器集區伺服器執行系統復原，以測試您已記錄的災難修復程式
ms.openlocfilehash: 92515a59f4ada2589a371cc9384c63a376e96cf8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832813"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a><span data-ttu-id="0c36a-103">商務用 Skype Server 中的嚴重損壞修復測試</span><span class="sxs-lookup"><span data-stu-id="0c36a-103">Disaster recovery testing in Skype for Business Server</span></span>

<span data-ttu-id="0c36a-104">為商務用 Skype 伺服器集區伺服器執行系統復原，以測試您已記錄的嚴重損壞修復程式。</span><span class="sxs-lookup"><span data-stu-id="0c36a-104">Perform a system recovery for a Skype for Business Server pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="0c36a-105">這項測試會模擬一部伺服器的完整硬體故障，並協助保證資源、計畫及資料可用於復原。</span><span class="sxs-lookup"><span data-stu-id="0c36a-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data are available for recovery.</span></span> <span data-ttu-id="0c36a-106">嘗試每月旋轉測試的焦點，使組織每次測試不同伺服器或其他裝置的失敗。</span><span class="sxs-lookup"><span data-stu-id="0c36a-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span> 

<span data-ttu-id="0c36a-107">請注意，組織執行嚴重損壞修復測試的排程會有所不同。</span><span class="sxs-lookup"><span data-stu-id="0c36a-107">Note that the schedule by which organizations perform Disaster Recovery testing will vary.</span></span> <span data-ttu-id="0c36a-108">不會忽視或忽略嚴重損壞修復測試，這一點很重要。</span><span class="sxs-lookup"><span data-stu-id="0c36a-108">It is very important that disaster recovery testing is not ignored or neglected.</span></span> 

<span data-ttu-id="0c36a-109">將商務用 Skype 伺服器拓撲、原則和設定值匯出至檔案。</span><span class="sxs-lookup"><span data-stu-id="0c36a-109">Export your Skype for Business Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="0c36a-110">除此之外，您也可以使用此檔案在升級、硬體故障或其他問題導致資料遺失的情況下，將此資訊還原至中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="0c36a-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="0c36a-111">將商務用 Skype 伺服器拓撲、原則及設定，匯入中央管理存放區或本機電腦（如下列命令所示）：</span><span class="sxs-lookup"><span data-stu-id="0c36a-111">Import your Skype for Business Server topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span> 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

<span data-ttu-id="0c36a-112">若要備份實際執行資料：</span><span class="sxs-lookup"><span data-stu-id="0c36a-112">To back up production data:</span></span>

- <span data-ttu-id="0c36a-113">使用標準 SQL Server 備份程式備份 RTC 和 LCSLog 資料庫，以將資料庫轉儲至檔案或磁帶轉儲裝置。</span><span class="sxs-lookup"><span data-stu-id="0c36a-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>
- <span data-ttu-id="0c36a-114">使用協力廠商備份應用程式將資料備份至檔案或磁帶。</span><span class="sxs-lookup"><span data-stu-id="0c36a-114">Use third-party backup application to back up the data to file or to tape.</span></span>
- <span data-ttu-id="0c36a-115">使用 Export-CsUserData Cmdlet 來建立整個 RTC 資料庫的 XML 匯出。</span><span class="sxs-lookup"><span data-stu-id="0c36a-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>
- <span data-ttu-id="0c36a-116">使用檔案系統備份或協力廠商備份來備份會議內容和合規性記錄。</span><span class="sxs-lookup"><span data-stu-id="0c36a-116">Use the file system backup or third-party backup to back up meeting content and compliance logs.</span></span>
- <span data-ttu-id="0c36a-117">使用 Export-CsConfiguration 命令列工具來備份商務用 Skype 伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="0c36a-117">Use the Export-CsConfiguration command-line tool to back up Skype for Business Server settings.</span></span>

<span data-ttu-id="0c36a-118">容錯移轉程式中的第一個步驟包括將使用者從生產集區強制移至嚴重損壞修復集區。</span><span class="sxs-lookup"><span data-stu-id="0c36a-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span> <span data-ttu-id="0c36a-119">這將會強制移動，因為實際生產集區無法接受使用者重新安置。</span><span class="sxs-lookup"><span data-stu-id="0c36a-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="0c36a-120">商務用 Skype Server 的移動使用者程式，會變更使用者帳戶物件上的屬性，以及 RTC SQL 資料庫上的記錄更新。</span><span class="sxs-lookup"><span data-stu-id="0c36a-120">The Skype for Business Server move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span> <span data-ttu-id="0c36a-121">您可以使用標準的 SQL server 還原程式，或使用協力廠商備份/還原公用程式，從生產 SQL Server 還原原始備份轉儲裝置的資料。</span><span class="sxs-lookup"><span data-stu-id="0c36a-121">This data can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

<span data-ttu-id="0c36a-122">還原此資料之後，使用者就能有效地連接至災害復原集區，並照常運作。</span><span class="sxs-lookup"><span data-stu-id="0c36a-122">After this data is restored, users can effectively connect to the Disaster Recovery pool, and operate as usual.</span></span> <span data-ttu-id="0c36a-123">若要讓使用者能夠連線至災害復原集區，將需要 DNS 記錄變更。</span><span class="sxs-lookup"><span data-stu-id="0c36a-123">To enable users to connect to the Disaster Recovery pool, a DNS record change will be required.</span></span>

<span data-ttu-id="0c36a-124">使用的自動設定和 DNS SRV 記錄，用戶端將會參考生產商務用 Skype 集區：</span><span class="sxs-lookup"><span data-stu-id="0c36a-124">The production Skype for Business pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

- <span data-ttu-id="0c36a-125">SRV： _tls。\<domain></span><span class="sxs-lookup"><span data-stu-id="0c36a-125">SRV: _sip._tls.\<domain></span></span> <span data-ttu-id="0c36a-126">/CNAME： SIP。\<domain></span><span class="sxs-lookup"><span data-stu-id="0c36a-126">/CNAME: SIP.\<domain></span></span>
- <span data-ttu-id="0c36a-127">CNAME： SIP。\<domain></span><span class="sxs-lookup"><span data-stu-id="0c36a-127">CNAME: SIP.\<domain></span></span> <span data-ttu-id="0c36a-128">/cvc-pool-1.\<domain></span><span class="sxs-lookup"><span data-stu-id="0c36a-128">/cvc-pool-1.\<domain></span></span>

<span data-ttu-id="0c36a-129">若要協助容錯移轉，必須更新此 CNAME 記錄，以參考 DROCSPool FQDN：</span><span class="sxs-lookup"><span data-stu-id="0c36a-129">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

- <span data-ttu-id="0c36a-130">CNAME： SIP。<domain></span><span class="sxs-lookup"><span data-stu-id="0c36a-130">CNAME: SIP.<domain></span></span> <span data-ttu-id="0c36a-131">/DROCSPool.\<domain></span><span class="sxs-lookup"><span data-stu-id="0c36a-131">/DROCSPool.\<domain></span></span>
- <span data-ttu-id="0c36a-132">Sip。\<domain></span><span class="sxs-lookup"><span data-stu-id="0c36a-132">Sip.\<domain></span></span>
- <span data-ttu-id="0c36a-133">Av。\<domain></span><span class="sxs-lookup"><span data-stu-id="0c36a-133">AV.\<domain></span></span>
- <span data-ttu-id="0c36a-134">webconf.\<domain></span><span class="sxs-lookup"><span data-stu-id="0c36a-134">webconf.\<domain></span></span>
