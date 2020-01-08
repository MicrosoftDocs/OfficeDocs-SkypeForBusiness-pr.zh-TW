---
title: Lync Server 2013：視需要工作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e96fd6e73e043c5ea7c476f939b3a3e06eadbdfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a><span data-ttu-id="a4fc9-102">Lync Server 2013 中的必要工作</span><span class="sxs-lookup"><span data-stu-id="a4fc9-102">As-needed tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4fc9-103">_**主題上次修改日期：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="a4fc9-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="a4fc9-104">視需要執行下列工作。</span><span class="sxs-lookup"><span data-stu-id="a4fc9-104">Perform the following tasks as necessary.</span></span> <span data-ttu-id="a4fc9-105">標準程式通常也會涵蓋它們：</span><span class="sxs-lookup"><span data-stu-id="a4fc9-105">They are frequently also covered by standard procedures:</span></span>

  - <span data-ttu-id="a4fc9-106">**完整的安全性審核   **您可以定期執行此審核，以回應郵件系統的升級或重新設計，或是回應企圖的（或成功）安全性破壞。</span><span class="sxs-lookup"><span data-stu-id="a4fc9-106">**Full Security Auditing   **You can perform this audit regularly, in response to an upgrade or redesign of the messaging system, or in response to an attempted (or successful) security breach.</span></span> <span data-ttu-id="a4fc9-107">程式可能會涉及伺服器和防火牆上的埠掃描、安全性修正程式的審核，以及協力廠商的滲透測試。</span><span class="sxs-lookup"><span data-stu-id="a4fc9-107">The procedure may involve port scans on servers and firewalls, audits of security fixes, and third-party penetration tests.</span></span>

  - <span data-ttu-id="a4fc9-108">**[取代到期**   的憑證] 來檢查 Lync Server 憑證是一般的每週工作，而且是作為系統管理員應記錄所有憑證到期日期的程式。</span><span class="sxs-lookup"><span data-stu-id="a4fc9-108">**Replace Certificates about to Expire**   Checking Lync Server Certificates is one of regular weekly tasks, and as part of the procedure an administrator should have a record of all certificates’ expiry dates.</span></span> <span data-ttu-id="a4fc9-109">此記錄可讓系統管理員在特定憑證即將到期並視需要更換時，建立通知。</span><span class="sxs-lookup"><span data-stu-id="a4fc9-109">This record enables an administrator to create a notification when a particular certificate is about to be expired and replaced as needed.</span></span>

  - <span data-ttu-id="a4fc9-110">**更新效能基線**   在升級或設定變更後更新效能基線。</span><span class="sxs-lookup"><span data-stu-id="a4fc9-110">**Updating Performance Baselines**   Update performance baselines after an upgrade or configuration change.</span></span> <span data-ttu-id="a4fc9-111">貴組織可以使用比較基準來測量效能變更，並偵測出會影響系統效能的問題。</span><span class="sxs-lookup"><span data-stu-id="a4fc9-111">Your organization can use baselines to measure performance changes and to detect issues that affect system performance.</span></span>

  - <span data-ttu-id="a4fc9-112">**管理**   企業版池初始配置企業版池、標準版伺服器以及貴組織環境中的任何其他伺服器都是在部署個別伺服器期間完成。</span><span class="sxs-lookup"><span data-stu-id="a4fc9-112">**Managing Enterprise Pool**   Initial configuration of Enterprise pools, Standard Edition servers, and any other servers in your organization's environment were done during deployment of the individual servers.</span></span> <span data-ttu-id="a4fc9-113">針對標準版伺服器與企業版池的伺服器和池進行部署後的管理，包括下列任務：</span><span class="sxs-lookup"><span data-stu-id="a4fc9-113">Post-deployment management of servers and pools for Standard Edition servers and Enterprise pools includes the following tasks:</span></span>
    
      - <span data-ttu-id="a4fc9-114">管理前端伺服器</span><span class="sxs-lookup"><span data-stu-id="a4fc9-114">Managing Front End Servers</span></span>
    
      - <span data-ttu-id="a4fc9-115">管理網路會議</span><span class="sxs-lookup"><span data-stu-id="a4fc9-115">Managing Web Conferencing</span></span>
    
      - <span data-ttu-id="a4fc9-116">管理會議</span><span class="sxs-lookup"><span data-stu-id="a4fc9-116">Managing Conferencing</span></span>
    
      - <span data-ttu-id="a4fc9-117">變更服務帳戶認證</span><span class="sxs-lookup"><span data-stu-id="a4fc9-117">Changing Service Account Credentials</span></span>
    
      - <span data-ttu-id="a4fc9-118">管理資料庫</span><span class="sxs-lookup"><span data-stu-id="a4fc9-118">Managing Databases</span></span>
    
      - <span data-ttu-id="a4fc9-119">啟動和停止服務及停用伺服器角色</span><span class="sxs-lookup"><span data-stu-id="a4fc9-119">Starting and Stopping Services and Deactivating Server Roles</span></span>
    
      - <span data-ttu-id="a4fc9-120">移除伺服器和伺服器角色、移除池，以及解除伺服器和池的授權</span><span class="sxs-lookup"><span data-stu-id="a4fc9-120">Removing Servers and Server Roles, Removing Pools, and Decommissioning Servers and Pools</span></span>

  - <span data-ttu-id="a4fc9-121">**管理使用量**   您可以設定 Lync Server 2013，以提供最適合您組織的功能和功能。</span><span class="sxs-lookup"><span data-stu-id="a4fc9-121">**Managing Usage**   You can configure Lync Server 2013 to provide the features and functionality that are most appropriate for your organization.</span></span> <span data-ttu-id="a4fc9-122">這包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="a4fc9-122">This includes the following:</span></span>
    
      - <span data-ttu-id="a4fc9-123">管理內部部署的網路會議會議支援</span><span class="sxs-lookup"><span data-stu-id="a4fc9-123">Managing Support for On-Premise Web Conferencing Meetings</span></span>
    
      - <span data-ttu-id="a4fc9-124">管理通訊群組的使用來傳送立即訊息</span><span class="sxs-lookup"><span data-stu-id="a4fc9-124">Managing the Use of Distribution Groups to Send Instant Messages</span></span>
    
      - <span data-ttu-id="a4fc9-125">管理連絡人、目前狀態和查詢</span><span class="sxs-lookup"><span data-stu-id="a4fc9-125">Managing Contacts, Presence, and Queries</span></span>
    
      - <span data-ttu-id="a4fc9-126">設定用戶端版本篩選</span><span class="sxs-lookup"><span data-stu-id="a4fc9-126">Configuring Client Version Filtering</span></span>
    
      - <span data-ttu-id="a4fc9-127">設定智慧 IM 篩選</span><span class="sxs-lookup"><span data-stu-id="a4fc9-127">Configuring Intelligent IM Filtering</span></span>
    
      - <span data-ttu-id="a4fc9-128">設定封存、通話詳細資料錄製，以及符合會議規範</span><span class="sxs-lookup"><span data-stu-id="a4fc9-128">Configuring Archiving, Call Detail Recording, and Meeting Compliance</span></span>

  - <span data-ttu-id="a4fc9-129">**管理邊緣伺服器**   連線日常管理需要提供外部連線的伺服器和設定包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="a4fc9-129">**Managing Edge Server Connectivity**   Ongoing management of the servers and settings required to provide external connectivity includes the following:</span></span>
    
      - <span data-ttu-id="a4fc9-130">管理內部伺服器與邊緣伺服器之間的連線性</span><span class="sxs-lookup"><span data-stu-id="a4fc9-130">Managing Connectivity between Internal Servers and Edge Servers</span></span>
    
      - <span data-ttu-id="a4fc9-131">為邊緣伺服器設定內部與外部介面與憑證</span><span class="sxs-lookup"><span data-stu-id="a4fc9-131">Configuring Internal and External Interfaces and Certificates for Edge Servers</span></span>
    
      - <span data-ttu-id="a4fc9-132">管理聯盟夥伴存取</span><span class="sxs-lookup"><span data-stu-id="a4fc9-132">Managing Federated Partner Access</span></span>

  - <span data-ttu-id="a4fc9-133">**管理通訊錄**   管理通訊錄服務器包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="a4fc9-133">**Administering the Address Book**   Administering Address Book Servers includes the following:</span></span>
    
      - <span data-ttu-id="a4fc9-134">設定通訊錄服務器電話正常化</span><span class="sxs-lookup"><span data-stu-id="a4fc9-134">Configuring Address Book Server phone normalization</span></span>
    
      - <span data-ttu-id="a4fc9-135">從命令列管理通訊錄服務器</span><span class="sxs-lookup"><span data-stu-id="a4fc9-135">Managing the Address Book Server from the command line</span></span>

  - <span data-ttu-id="a4fc9-136">**管理**   使用者帳戶的使用者帳戶管理包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="a4fc9-136">**Managing User Accounts**   Management of user accounts includes the following:</span></span>
    
      - <span data-ttu-id="a4fc9-137">啟用 Lync Server 的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="a4fc9-137">Enabling User Accounts for Lync Server</span></span>
    
      - <span data-ttu-id="a4fc9-138">使用嚮導來設定 Lync Server 使用者</span><span class="sxs-lookup"><span data-stu-id="a4fc9-138">Configuring Lync Server Users using the Wizard</span></span>
    
      - <span data-ttu-id="a4fc9-139">配置個別的 Lync Server 使用者帳戶屬性</span><span class="sxs-lookup"><span data-stu-id="a4fc9-139">Configuring Individual Lync Server User Account Properties</span></span>
    
      - <span data-ttu-id="a4fc9-140">搜尋 Lync Server 使用者</span><span class="sxs-lookup"><span data-stu-id="a4fc9-140">Searching for Lync Server Users</span></span>
    
      - <span data-ttu-id="a4fc9-141">移動 Lync Server 使用者</span><span class="sxs-lookup"><span data-stu-id="a4fc9-141">Moving Lync Server Users</span></span>
    
      - <span data-ttu-id="a4fc9-142">刪除 Lync Server 使用者</span><span class="sxs-lookup"><span data-stu-id="a4fc9-142">Deleting Lync Server Users</span></span>

  - <span data-ttu-id="a4fc9-143">**分析 Lync server 2013 記錄**   檔一個非常實用的工具（通常用於疑難排解）是在[使用 lync server 2013 記錄工具](http://technet.microsoft.com/en-us/library/gg558599.aspx)中詳細說明的 lync server 2013 記錄工具。</span><span class="sxs-lookup"><span data-stu-id="a4fc9-143">**Analyzing Lync Server 2013 Log Files**   One very helpful tool, generally used for troubleshooting, is the Lync Server 2013 Logging Tool described in detail in [Using Lync Server 2013 Logging Tool](http://technet.microsoft.com/en-us/library/gg558599.aspx).</span></span>

<span data-ttu-id="a4fc9-144">由於記錄工具會產生記錄檔（在每個伺服器的基礎上），如果電腦上已安裝 Microsoft Office Server 12 資源套件工具，就可以使用 Snooper 工具來查看並分析這些記錄檔。</span><span class="sxs-lookup"><span data-stu-id="a4fc9-144">Because the Logging Tool generates log files (on a per-server basis), these log files can be viewed and analyzed by using the Snooper tool, if the Microsoft Office Server 12 Resource Kit Tools are installed on the computer.</span></span> <span data-ttu-id="a4fc9-145">否則，您也可以使用文字編輯器來分析記錄，這比使用 Snooper 實用程式更不透明且更複雜。</span><span class="sxs-lookup"><span data-stu-id="a4fc9-145">Otherwise, logs can also be analyzed by using a text editor, which is much less transparent and more complex than using the Snooper utility.</span></span>

<span data-ttu-id="a4fc9-146">若要查看及分析通訊協定訊息</span><span class="sxs-lookup"><span data-stu-id="a4fc9-146">To View and Analyze Protocol Messages</span></span>

<span data-ttu-id="a4fc9-147">在記錄工具中，當您結束調試會話時，請按一下 [分析記錄檔]，透過使用 Snooper 工具來查看記錄檔。</span><span class="sxs-lookup"><span data-stu-id="a4fc9-147">In the Logging Tool, when you have ended the debug session, click Analyze Log Files to view the log files by using the Snooper tool.</span></span> <span data-ttu-id="a4fc9-148">您可以分析通訊協定記錄，以取得下列元件：</span><span class="sxs-lookup"><span data-stu-id="a4fc9-148">You can analyze protocol logs for the following components:</span></span>

  - <span data-ttu-id="a4fc9-149">Lync Server SipStack （SIP）</span><span class="sxs-lookup"><span data-stu-id="a4fc9-149">Lync Server SipStack (SIP)</span></span>

  - <span data-ttu-id="a4fc9-150">Lync Server S4 （SIP）</span><span class="sxs-lookup"><span data-stu-id="a4fc9-150">Lync Server S4 (SIP)</span></span>

  - <span data-ttu-id="a4fc9-151">Lync Server 會議信號流量（C3P），包括 MCU 基礎 C3P 和焦點 C3P</span><span class="sxs-lookup"><span data-stu-id="a4fc9-151">Lync Server Conferencing signaling traffic (C3P), including MCU Infra C3P and Focus C3P</span></span>

  - <span data-ttu-id="a4fc9-152">Lync Server Web 會議流量（PSOM）</span><span class="sxs-lookup"><span data-stu-id="a4fc9-152">Lync Server Web conferencing traffic (PSOM)</span></span>

  - <span data-ttu-id="a4fc9-153">Lync Server 整合通訊用戶端平臺用戶端（UCCP）</span><span class="sxs-lookup"><span data-stu-id="a4fc9-153">Lync Server Unified Communications Client Platform client (UCCP)</span></span>

  - <span data-ttu-id="a4fc9-154">來自存檔資料庫的錯誤報表</span><span class="sxs-lookup"><span data-stu-id="a4fc9-154">Error reports from the archiving database</span></span>

<span data-ttu-id="a4fc9-155">若要協助組織所需任務的效能，請參閱視需要作業檢查清單。</span><span class="sxs-lookup"><span data-stu-id="a4fc9-155">To help organize the performance of as-needed tasks, see As-Needed Operations Checklist.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a4fc9-156">如需詳細的管理與管理程式，請參閱 Microsoft Lync Server 2013 管理指南。</span><span class="sxs-lookup"><span data-stu-id="a4fc9-156">For detailed administration and management procedures, see the Microsoft Lync Server 2013 Administration Guide.</span></span>



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a><span data-ttu-id="a4fc9-157">備份（及還原）原則或配置設定</span><span class="sxs-lookup"><span data-stu-id="a4fc9-157">Backup (and restore) policies or configuration settings</span></span>

<span data-ttu-id="a4fc9-158">Lync Server 2013 可讓您備份及還原整個系統。</span><span class="sxs-lookup"><span data-stu-id="a4fc9-158">Lync Server 2013 lets you back up and restore the whole system.</span></span> <span data-ttu-id="a4fc9-159">您想要備份的 Iif （可能是天還原）單一原則或單一的配置設定集合、檢索適當的原則，然後將該物件輸送至 Export Clixml Cmdlet，這會將原則資訊儲存為 XML 檔：</span><span class="sxs-lookup"><span data-stu-id="a4fc9-159">Iif you want to back up (and then maybe someday restore) a single policy or a single collection of configuration settings, retrieve the appropriate policy, and then pipe that object to the Export-Clixml cmdlet, which saves the policy information as an XML file:</span></span>

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

<span data-ttu-id="a4fc9-160">您現在可以嘗試 RedmondClientPolicy 並變更許多設定。</span><span class="sxs-lookup"><span data-stu-id="a4fc9-160">You may now experiment with RedmondClientPolicy and change lots of the settings.</span></span> <span data-ttu-id="a4fc9-161">如果您決定要還原舊原則，請輸入：</span><span class="sxs-lookup"><span data-stu-id="a4fc9-161">If you decide instead to restore the old policy, enter:</span></span>

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

<span data-ttu-id="a4fc9-162">請注意，這個方法適用于大部分的原則和設定，但它不會搭配一些較複雜的專案（例如包含多個不同語音路由的路由設定設定）來運作。</span><span class="sxs-lookup"><span data-stu-id="a4fc9-162">Note that this approach will work for most policies and settings but it won't work with some of the more complex items—items that contain multiple sub-objects (like routing configuration settings, which contain many separate voice routes).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

