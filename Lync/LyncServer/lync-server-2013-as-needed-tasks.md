---
title: Lync Server 2013： 視工作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67a0355d32e5e704d6609335c82f8cfe1fe7aa86
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a><span data-ttu-id="282df-102">視需要在 Lync Server 2013 中的工作</span><span class="sxs-lookup"><span data-stu-id="282df-102">As-needed tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="282df-103">_**上次修改主題：** 2014年-08-18_</span><span class="sxs-lookup"><span data-stu-id="282df-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="282df-104">執行下列工作，為必要。</span><span class="sxs-lookup"><span data-stu-id="282df-104">Perform the following tasks as necessary.</span></span> <span data-ttu-id="282df-105">它們通常已涵蓋在標準程序：</span><span class="sxs-lookup"><span data-stu-id="282df-105">They are frequently also covered by standard procedures:</span></span>

  - <span data-ttu-id="282df-106">**完整安全性稽核   **定期，以回應升級或重新設計的郵件系統，或嘗試 （或成功） 的安全性資料外洩回應，您可以執行這項稽核。</span><span class="sxs-lookup"><span data-stu-id="282df-106">**Full Security Auditing   **You can perform this audit regularly, in response to an upgrade or redesign of the messaging system, or in response to an attempted (or successful) security breach.</span></span> <span data-ttu-id="282df-107">程序可能包括伺服器和防火牆、 稽核安全性修正程式上的連接埠掃描，以及協力程式侵入測試。</span><span class="sxs-lookup"><span data-stu-id="282df-107">The procedure may involve port scans on servers and firewalls, audits of security fixes, and third-party penetration tests.</span></span>

  - <span data-ttu-id="282df-108">**關於取代憑證到期至**   檢查 Lync 伺服器憑證是其中一個規則的每週工作，且程序的系統管理員應該有一筆記錄的所有憑證的到期日期。</span><span class="sxs-lookup"><span data-stu-id="282df-108">**Replace Certificates about to Expire**   Checking Lync Server Certificates is one of regular weekly tasks, and as part of the procedure an administrator should have a record of all certificates’ expiry dates.</span></span> <span data-ttu-id="282df-109">此記錄可讓系統管理員建立通知，當特定憑證即將過期並取代視。</span><span class="sxs-lookup"><span data-stu-id="282df-109">This record enables an administrator to create a notification when a particular certificate is about to be expired and replaced as needed.</span></span>

  - <span data-ttu-id="282df-110">**更新效能基準**   更新效能基準在升級或組態變更之後。</span><span class="sxs-lookup"><span data-stu-id="282df-110">**Updating Performance Baselines**   Update performance baselines after an upgrade or configuration change.</span></span> <span data-ttu-id="282df-111">您的組織可以使用基準線來測量效能變更，以及偵測會影響系統效能的問題。</span><span class="sxs-lookup"><span data-stu-id="282df-111">Your organization can use baselines to measure performance changes and to detect issues that affect system performance.</span></span>

  - <span data-ttu-id="282df-112">**管理企業資料庫**   Enterprise 集區、 Standard Edition server 和貴組織的環境中的任何其他伺服器的初始設定已完成的個別伺服器的部署期間。</span><span class="sxs-lookup"><span data-stu-id="282df-112">**Managing Enterprise Pool**   Initial configuration of Enterprise pools, Standard Edition servers, and any other servers in your organization's environment were done during deployment of the individual servers.</span></span> <span data-ttu-id="282df-113">部署後管理伺服器和 Standard Edition server 的集區和 Enterprise 集區包括下列工作：</span><span class="sxs-lookup"><span data-stu-id="282df-113">Post-deployment management of servers and pools for Standard Edition servers and Enterprise pools includes the following tasks:</span></span>
    
      - <span data-ttu-id="282df-114">管理前端伺服器</span><span class="sxs-lookup"><span data-stu-id="282df-114">Managing Front End Servers</span></span>
    
      - <span data-ttu-id="282df-115">管理 Web 會議</span><span class="sxs-lookup"><span data-stu-id="282df-115">Managing Web Conferencing</span></span>
    
      - <span data-ttu-id="282df-116">管理會議</span><span class="sxs-lookup"><span data-stu-id="282df-116">Managing Conferencing</span></span>
    
      - <span data-ttu-id="282df-117">變更服務帳戶認證</span><span class="sxs-lookup"><span data-stu-id="282df-117">Changing Service Account Credentials</span></span>
    
      - <span data-ttu-id="282df-118">管理資料庫</span><span class="sxs-lookup"><span data-stu-id="282df-118">Managing Databases</span></span>
    
      - <span data-ttu-id="282df-119">啟動和停止服務，以及停用伺服器角色</span><span class="sxs-lookup"><span data-stu-id="282df-119">Starting and Stopping Services and Deactivating Server Roles</span></span>
    
      - <span data-ttu-id="282df-120">移除伺服器及伺服器角色、 移除集區]，和解除委任伺服器和集區</span><span class="sxs-lookup"><span data-stu-id="282df-120">Removing Servers and Server Roles, Removing Pools, and Decommissioning Servers and Pools</span></span>

  - <span data-ttu-id="282df-121">**管理流量**   您可以設定 Lync Server 2013 提供最適合貴組織的功能。</span><span class="sxs-lookup"><span data-stu-id="282df-121">**Managing Usage**   You can configure Lync Server 2013 to provide the features and functionality that are most appropriate for your organization.</span></span> <span data-ttu-id="282df-122">其中包括下列項目：</span><span class="sxs-lookup"><span data-stu-id="282df-122">This includes the following:</span></span>
    
      - <span data-ttu-id="282df-123">管理內部部署 Web 會議會議的支援</span><span class="sxs-lookup"><span data-stu-id="282df-123">Managing Support for On-Premise Web Conferencing Meetings</span></span>
    
      - <span data-ttu-id="282df-124">管理通訊群組，以傳送立即訊息使用</span><span class="sxs-lookup"><span data-stu-id="282df-124">Managing the Use of Distribution Groups to Send Instant Messages</span></span>
    
      - <span data-ttu-id="282df-125">管理連絡人、 目前狀態，以及查詢</span><span class="sxs-lookup"><span data-stu-id="282df-125">Managing Contacts, Presence, and Queries</span></span>
    
      - <span data-ttu-id="282df-126">設定用戶端版本篩選</span><span class="sxs-lookup"><span data-stu-id="282df-126">Configuring Client Version Filtering</span></span>
    
      - <span data-ttu-id="282df-127">設定智慧型 IM 篩選</span><span class="sxs-lookup"><span data-stu-id="282df-127">Configuring Intelligent IM Filtering</span></span>
    
      - <span data-ttu-id="282df-128">設定封存，請呼叫錄製，以及符合規範的詳細資料</span><span class="sxs-lookup"><span data-stu-id="282df-128">Configuring Archiving, Call Detail Recording, and Meeting Compliance</span></span>

  - <span data-ttu-id="282df-129">**管理 Edge 伺服器連線**   持續管理伺服器和提供外部連線所需的設定包括下列：</span><span class="sxs-lookup"><span data-stu-id="282df-129">**Managing Edge Server Connectivity**   Ongoing management of the servers and settings required to provide external connectivity includes the following:</span></span>
    
      - <span data-ttu-id="282df-130">管理內部伺服器和 Edge Server 之間的連線</span><span class="sxs-lookup"><span data-stu-id="282df-130">Managing Connectivity between Internal Servers and Edge Servers</span></span>
    
      - <span data-ttu-id="282df-131">設定 Edge Server 的內部和外部介面及憑證</span><span class="sxs-lookup"><span data-stu-id="282df-131">Configuring Internal and External Interfaces and Certificates for Edge Servers</span></span>
    
      - <span data-ttu-id="282df-132">管理同盟協力廠商存取</span><span class="sxs-lookup"><span data-stu-id="282df-132">Managing Federated Partner Access</span></span>

  - <span data-ttu-id="282df-133">**管理通訊錄**   管理 Address Book 伺服器包括下列：</span><span class="sxs-lookup"><span data-stu-id="282df-133">**Administering the Address Book**   Administering Address Book Servers includes the following:</span></span>
    
      - <span data-ttu-id="282df-134">設定 Address Book Server 電話正規化</span><span class="sxs-lookup"><span data-stu-id="282df-134">Configuring Address Book Server phone normalization</span></span>
    
      - <span data-ttu-id="282df-135">從命令列管理 Address Book Server</span><span class="sxs-lookup"><span data-stu-id="282df-135">Managing the Address Book Server from the command line</span></span>

  - <span data-ttu-id="282df-136">**管理使用者帳戶**   管理使用者帳戶包含下列：</span><span class="sxs-lookup"><span data-stu-id="282df-136">**Managing User Accounts**   Management of user accounts includes the following:</span></span>
    
      - <span data-ttu-id="282df-137">Lync Server 啟用使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="282df-137">Enabling User Accounts for Lync Server</span></span>
    
      - <span data-ttu-id="282df-138">使用精靈設定 Lync Server 使用者</span><span class="sxs-lookup"><span data-stu-id="282df-138">Configuring Lync Server Users using the Wizard</span></span>
    
      - <span data-ttu-id="282df-139">設定個別的 Lync Server 使用者帳戶內容</span><span class="sxs-lookup"><span data-stu-id="282df-139">Configuring Individual Lync Server User Account Properties</span></span>
    
      - <span data-ttu-id="282df-140">Lync Server 使用者搜尋</span><span class="sxs-lookup"><span data-stu-id="282df-140">Searching for Lync Server Users</span></span>
    
      - <span data-ttu-id="282df-141">移動 Lync Server 使用者</span><span class="sxs-lookup"><span data-stu-id="282df-141">Moving Lync Server Users</span></span>
    
      - <span data-ttu-id="282df-142">刪除 Lync Server 使用者</span><span class="sxs-lookup"><span data-stu-id="282df-142">Deleting Lync Server Users</span></span>

  - <span data-ttu-id="282df-143">**分析 Lync Server 2013 記錄檔**   一種非常有用的工具，通常用於疑難排解的方式，是[使用 Lync Server 2013 記錄工具](http://technet.microsoft.com/library/gg558599.aspx)的詳細說明 Lync Server 2013 記錄工具。</span><span class="sxs-lookup"><span data-stu-id="282df-143">**Analyzing Lync Server 2013 Log Files**   One very helpful tool, generally used for troubleshooting, is the Lync Server 2013 Logging Tool described in detail in [Using Lync Server 2013 Logging Tool](http://technet.microsoft.com/library/gg558599.aspx).</span></span>

<span data-ttu-id="282df-144">因為記錄工具會產生記錄檔 （根據每個伺服器），可以檢視這些記錄檔，且分析使用 Snooper 工具，如果電腦上安裝 Microsoft Office Server 12 Resource Kit 工具。</span><span class="sxs-lookup"><span data-stu-id="282df-144">Because the Logging Tool generates log files (on a per-server basis), these log files can be viewed and analyzed by using the Snooper tool, if the Microsoft Office Server 12 Resource Kit Tools are installed on the computer.</span></span> <span data-ttu-id="282df-145">否則，記錄檔也可以使用文字編輯器，也就是遠低於透明、 更複雜比使用 Snooper 公用程式進行分析。</span><span class="sxs-lookup"><span data-stu-id="282df-145">Otherwise, logs can also be analyzed by using a text editor, which is much less transparent and more complex than using the Snooper utility.</span></span>

<span data-ttu-id="282df-146">若要檢視並分析通訊協定的郵件</span><span class="sxs-lookup"><span data-stu-id="282df-146">To View and Analyze Protocol Messages</span></span>

<span data-ttu-id="282df-147">在 [記錄] 工具中，當您結束偵錯工作階段，按一下 [分析記錄檔，以使用 Snooper 工具檢視記錄檔。</span><span class="sxs-lookup"><span data-stu-id="282df-147">In the Logging Tool, when you have ended the debug session, click Analyze Log Files to view the log files by using the Snooper tool.</span></span> <span data-ttu-id="282df-148">您可以分析通訊協定記錄中的下列元件：</span><span class="sxs-lookup"><span data-stu-id="282df-148">You can analyze protocol logs for the following components:</span></span>

  - <span data-ttu-id="282df-149">Lync Server 裡包含 SipStack (SIP)</span><span class="sxs-lookup"><span data-stu-id="282df-149">Lync Server SipStack (SIP)</span></span>

  - <span data-ttu-id="282df-150">Lync Server S4 (SIP)</span><span class="sxs-lookup"><span data-stu-id="282df-150">Lync Server S4 (SIP)</span></span>

  - <span data-ttu-id="282df-151">Lync Server 會議訊號流量 (C3P)，包括基礎 MCU C3P 和焦點 C3P</span><span class="sxs-lookup"><span data-stu-id="282df-151">Lync Server Conferencing signaling traffic (C3P), including MCU Infra C3P and Focus C3P</span></span>

  - <span data-ttu-id="282df-152">Lync Server Web 會議流量 (PSOM)</span><span class="sxs-lookup"><span data-stu-id="282df-152">Lync Server Web conferencing traffic (PSOM)</span></span>

  - <span data-ttu-id="282df-153">Lync Server 整合通訊用戶端平台用戶端 (UCCP)</span><span class="sxs-lookup"><span data-stu-id="282df-153">Lync Server Unified Communications Client Platform client (UCCP)</span></span>

  - <span data-ttu-id="282df-154">從封存資料庫的錯誤報告</span><span class="sxs-lookup"><span data-stu-id="282df-154">Error reports from the archiving database</span></span>

<span data-ttu-id="282df-155">若要協助您組織所需的工作的效能，請參閱 As-Needed Operations Checklist。</span><span class="sxs-lookup"><span data-stu-id="282df-155">To help organize the performance of as-needed tasks, see As-Needed Operations Checklist.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="282df-156">如需詳細的系統管理與管理程序，請參閱 < Microsoft Lync Server 2013 系統管理指南。</span><span class="sxs-lookup"><span data-stu-id="282df-156">For detailed administration and management procedures, see the Microsoft Lync Server 2013 Administration Guide.</span></span>



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a><span data-ttu-id="282df-157">備份 （與還原） 的原則或組態設定</span><span class="sxs-lookup"><span data-stu-id="282df-157">Backup (and restore) policies or configuration settings</span></span>

<span data-ttu-id="282df-158">Lync Server 2013 可讓您備份及還原整個系統。</span><span class="sxs-lookup"><span data-stu-id="282df-158">Lync Server 2013 lets you back up and restore the whole system.</span></span> <span data-ttu-id="282df-159">Iif 您想要備份伺服器陣列 （，然後也許有一天還原） 的單一原則或組態設定的單一集合擷取適當的原則，並再將以管線傳輸至 Export-clixml 指令程式，將原則資訊儲存為 XML 檔案的物件：</span><span class="sxs-lookup"><span data-stu-id="282df-159">Iif you want to back up (and then maybe someday restore) a single policy or a single collection of configuration settings, retrieve the appropriate policy, and then pipe that object to the Export-Clixml cmdlet, which saves the policy information as an XML file:</span></span>

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

<span data-ttu-id="282df-160">您現在可能試驗 RedmondClientPolicy，並變更大量的設定。</span><span class="sxs-lookup"><span data-stu-id="282df-160">You may now experiment with RedmondClientPolicy and change lots of the settings.</span></span> <span data-ttu-id="282df-161">如果您改為決定要還原舊的原則，請輸入：</span><span class="sxs-lookup"><span data-stu-id="282df-161">If you decide instead to restore the old policy, enter:</span></span>

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

<span data-ttu-id="282df-162">請注意，此方法適用於大部分的原則和設定，但它不會使用一些更複雜的項目-包含多個的子物件 （例如路由組態設定，其中包含許多不同的語音路由） 的項目。</span><span class="sxs-lookup"><span data-stu-id="282df-162">Note that this approach will work for most policies and settings but it won't work with some of the more complex items—items that contain multiple sub-objects (like routing configuration settings, which contain many separate voice routes).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

