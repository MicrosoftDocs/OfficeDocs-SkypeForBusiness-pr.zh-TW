---
title: Lync Server 2013：必要任務
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
ms.openlocfilehash: 98b4323374c9801ec07930941a0daa3635b04e43
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529540"
---
# <a name="as-needed-tasks-in-lync-server-2013"></a><span data-ttu-id="4cd9e-102">Lync Server 2013 中的必要工作</span><span class="sxs-lookup"><span data-stu-id="4cd9e-102">As-needed tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4cd9e-103">_**主題上次修改日期：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="4cd9e-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="4cd9e-104">請視需要執行下列工作。</span><span class="sxs-lookup"><span data-stu-id="4cd9e-104">Perform the following tasks as necessary.</span></span> <span data-ttu-id="4cd9e-105">它們經常也包含在標準程式中：</span><span class="sxs-lookup"><span data-stu-id="4cd9e-105">They are frequently also covered by standard procedures:</span></span>

  - <span data-ttu-id="4cd9e-106">**完整安全性審核   **您可以定期執行此審核，以回應郵件系統的升級或重新設計，或是回應嘗試的 (或成功的) 安全性破壞。</span><span class="sxs-lookup"><span data-stu-id="4cd9e-106">**Full Security Auditing   **You can perform this audit regularly, in response to an upgrade or redesign of the messaging system, or in response to an attempted (or successful) security breach.</span></span> <span data-ttu-id="4cd9e-107">此程式可能會包含伺服器及防火牆上的埠掃描、安全性修正程式的核查，以及協力廠商的滲透測試。</span><span class="sxs-lookup"><span data-stu-id="4cd9e-107">The procedure may involve port scans on servers and firewalls, audits of security fixes, and third-party penetration tests.</span></span>

  - <span data-ttu-id="4cd9e-108">**取代憑證，使其到期**    檢查 Lync Server 憑證是一項正常的周任務，也就是管理員應該有所有憑證到期日記錄的步驟。</span><span class="sxs-lookup"><span data-stu-id="4cd9e-108">**Replace Certificates about to Expire**   Checking Lync Server Certificates is one of regular weekly tasks, and as part of the procedure an administrator should have a record of all certificates’ expiry dates.</span></span> <span data-ttu-id="4cd9e-109">這筆記錄可讓系統管理員在特定憑證到期時建立通知，並視需要更換。</span><span class="sxs-lookup"><span data-stu-id="4cd9e-109">This record enables an administrator to create a notification when a particular certificate is about to be expired and replaced as needed.</span></span>

  - <span data-ttu-id="4cd9e-110">**更新效能基準**    在升級或設定變更之後更新效能基準。</span><span class="sxs-lookup"><span data-stu-id="4cd9e-110">**Updating Performance Baselines**   Update performance baselines after an upgrade or configuration change.</span></span> <span data-ttu-id="4cd9e-111">您的組織可以使用基準來測量效能變更，並偵測影響系統效能的問題。</span><span class="sxs-lookup"><span data-stu-id="4cd9e-111">Your organization can use baselines to measure performance changes and to detect issues that affect system performance.</span></span>

  - <span data-ttu-id="4cd9e-112">**管理企業版集**     區部署個別的伺服器時，已完成組織環境中的 Enterprise pool、Standard Edition 伺服器及其他任何伺服器的初始設定。</span><span class="sxs-lookup"><span data-stu-id="4cd9e-112">**Managing Enterprise Pool**   Initial configuration of Enterprise pools, Standard Edition servers, and any other servers in your organization's environment were done during deployment of the individual servers.</span></span> <span data-ttu-id="4cd9e-113">Standard Edition server 和 Enterprise pool 的伺服器及集區的部署後管理包括下列工作：</span><span class="sxs-lookup"><span data-stu-id="4cd9e-113">Post-deployment management of servers and pools for Standard Edition servers and Enterprise pools includes the following tasks:</span></span>
    
      - <span data-ttu-id="4cd9e-114">管理前端伺服器</span><span class="sxs-lookup"><span data-stu-id="4cd9e-114">Managing Front End Servers</span></span>
    
      - <span data-ttu-id="4cd9e-115">管理 Web 會議</span><span class="sxs-lookup"><span data-stu-id="4cd9e-115">Managing Web Conferencing</span></span>
    
      - <span data-ttu-id="4cd9e-116">管理會議</span><span class="sxs-lookup"><span data-stu-id="4cd9e-116">Managing Conferencing</span></span>
    
      - <span data-ttu-id="4cd9e-117">變更服務帳戶認證</span><span class="sxs-lookup"><span data-stu-id="4cd9e-117">Changing Service Account Credentials</span></span>
    
      - <span data-ttu-id="4cd9e-118">管理資料庫</span><span class="sxs-lookup"><span data-stu-id="4cd9e-118">Managing Databases</span></span>
    
      - <span data-ttu-id="4cd9e-119">啟動和停止服務以及停用伺服器角色</span><span class="sxs-lookup"><span data-stu-id="4cd9e-119">Starting and Stopping Services and Deactivating Server Roles</span></span>
    
      - <span data-ttu-id="4cd9e-120">移除伺服器和伺服器角色、移除集區，以及解除委任伺服器與集區</span><span class="sxs-lookup"><span data-stu-id="4cd9e-120">Removing Servers and Server Roles, Removing Pools, and Decommissioning Servers and Pools</span></span>

  - <span data-ttu-id="4cd9e-121">**管理使用量**    您可以設定 Lync Server 2013，以提供最適合貴組織的功能。</span><span class="sxs-lookup"><span data-stu-id="4cd9e-121">**Managing Usage**   You can configure Lync Server 2013 to provide the features and functionality that are most appropriate for your organization.</span></span> <span data-ttu-id="4cd9e-122">其中包括下列項目：</span><span class="sxs-lookup"><span data-stu-id="4cd9e-122">This includes the following:</span></span>
    
      - <span data-ttu-id="4cd9e-123">管理內部部署 Web 會議會議的支援</span><span class="sxs-lookup"><span data-stu-id="4cd9e-123">Managing Support for On-Premise Web Conferencing Meetings</span></span>
    
      - <span data-ttu-id="4cd9e-124">管理通訊群組的使用以傳送立即訊息</span><span class="sxs-lookup"><span data-stu-id="4cd9e-124">Managing the Use of Distribution Groups to Send Instant Messages</span></span>
    
      - <span data-ttu-id="4cd9e-125">管理連絡人、目前狀態及查詢</span><span class="sxs-lookup"><span data-stu-id="4cd9e-125">Managing Contacts, Presence, and Queries</span></span>
    
      - <span data-ttu-id="4cd9e-126">設定用戶端版本篩選</span><span class="sxs-lookup"><span data-stu-id="4cd9e-126">Configuring Client Version Filtering</span></span>
    
      - <span data-ttu-id="4cd9e-127">設定智慧 IM 篩選</span><span class="sxs-lookup"><span data-stu-id="4cd9e-127">Configuring Intelligent IM Filtering</span></span>
    
      - <span data-ttu-id="4cd9e-128">設定封存、詳細通話記錄和會議規範</span><span class="sxs-lookup"><span data-stu-id="4cd9e-128">Configuring Archiving, Call Detail Recording, and Meeting Compliance</span></span>

  - <span data-ttu-id="4cd9e-129">**管理 Edge Server 連線能力**    持續管理提供外部連線所需的伺服器及設定包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="4cd9e-129">**Managing Edge Server Connectivity**   Ongoing management of the servers and settings required to provide external connectivity includes the following:</span></span>
    
      - <span data-ttu-id="4cd9e-130">管理內部伺服器和 Edge Server 之間的連線</span><span class="sxs-lookup"><span data-stu-id="4cd9e-130">Managing Connectivity between Internal Servers and Edge Servers</span></span>
    
      - <span data-ttu-id="4cd9e-131">設定 Edge Server 的內部及外部介面和憑證</span><span class="sxs-lookup"><span data-stu-id="4cd9e-131">Configuring Internal and External Interfaces and Certificates for Edge Servers</span></span>
    
      - <span data-ttu-id="4cd9e-132">管理同盟合作夥伴存取</span><span class="sxs-lookup"><span data-stu-id="4cd9e-132">Managing Federated Partner Access</span></span>

  - <span data-ttu-id="4cd9e-133">**管理通訊錄**    管理通訊錄服務器包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="4cd9e-133">**Administering the Address Book**   Administering Address Book Servers includes the following:</span></span>
    
      - <span data-ttu-id="4cd9e-134">設定通訊錄服務器電話正常化</span><span class="sxs-lookup"><span data-stu-id="4cd9e-134">Configuring Address Book Server phone normalization</span></span>
    
      - <span data-ttu-id="4cd9e-135">從命令列管理通訊錄服務器</span><span class="sxs-lookup"><span data-stu-id="4cd9e-135">Managing the Address Book Server from the command line</span></span>

  - <span data-ttu-id="4cd9e-136">**管理使用者帳戶**    管理使用者帳戶包括下列專案：</span><span class="sxs-lookup"><span data-stu-id="4cd9e-136">**Managing User Accounts**   Management of user accounts includes the following:</span></span>
    
      - <span data-ttu-id="4cd9e-137">啟用 Lync Server 的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="4cd9e-137">Enabling User Accounts for Lync Server</span></span>
    
      - <span data-ttu-id="4cd9e-138">使用嚮導設定 Lync Server 使用者</span><span class="sxs-lookup"><span data-stu-id="4cd9e-138">Configuring Lync Server Users using the Wizard</span></span>
    
      - <span data-ttu-id="4cd9e-139">設定個別的 Lync Server 使用者帳戶屬性</span><span class="sxs-lookup"><span data-stu-id="4cd9e-139">Configuring Individual Lync Server User Account Properties</span></span>
    
      - <span data-ttu-id="4cd9e-140">搜尋 Lync Server 使用者</span><span class="sxs-lookup"><span data-stu-id="4cd9e-140">Searching for Lync Server Users</span></span>
    
      - <span data-ttu-id="4cd9e-141">移動 Lync Server 使用者</span><span class="sxs-lookup"><span data-stu-id="4cd9e-141">Moving Lync Server Users</span></span>
    
      - <span data-ttu-id="4cd9e-142">刪除 Lync Server 使用者</span><span class="sxs-lookup"><span data-stu-id="4cd9e-142">Deleting Lync Server Users</span></span>

  - <span data-ttu-id="4cd9e-143">**分析 Lync Server 2013 記錄**     檔一種非常有用的工具（一般用於疑難排解）是「lync Server 2013 記錄」工具，詳細資訊請參閱[使用 Lync server 2013 記錄工具](https://technet.microsoft.com/library/gg558599.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4cd9e-143">**Analyzing Lync Server 2013 Log Files**   One very helpful tool, generally used for troubleshooting, is the Lync Server 2013 Logging Tool described in detail in [Using Lync Server 2013 Logging Tool](https://technet.microsoft.com/library/gg558599.aspx).</span></span>

<span data-ttu-id="4cd9e-144">因為「記錄」工具會以每個伺服器為基礎來產生記錄檔 () ，如果電腦上已安裝 Microsoft Office Server 12 資源套件工具，則可以使用 Snooper 工具來查看及分析這些記錄檔。</span><span class="sxs-lookup"><span data-stu-id="4cd9e-144">Because the Logging Tool generates log files (on a per-server basis), these log files can be viewed and analyzed by using the Snooper tool, if the Microsoft Office Server 12 Resource Kit Tools are installed on the computer.</span></span> <span data-ttu-id="4cd9e-145">否則，也可以使用文字編輯器來分析記錄檔，此編輯器的透明度不如使用 Snooper 實用程式複雜。</span><span class="sxs-lookup"><span data-stu-id="4cd9e-145">Otherwise, logs can also be analyzed by using a text editor, which is much less transparent and more complex than using the Snooper utility.</span></span>

<span data-ttu-id="4cd9e-146">若要查看及分析通訊協定訊息</span><span class="sxs-lookup"><span data-stu-id="4cd9e-146">To View and Analyze Protocol Messages</span></span>

<span data-ttu-id="4cd9e-147">在記錄工具中，當您結束調試會話時，請按一下 [分析記錄檔] 以使用 Snooper 工具來查看記錄檔。</span><span class="sxs-lookup"><span data-stu-id="4cd9e-147">In the Logging Tool, when you have ended the debug session, click Analyze Log Files to view the log files by using the Snooper tool.</span></span> <span data-ttu-id="4cd9e-148">您可以分析下列元件的通訊協定記錄：</span><span class="sxs-lookup"><span data-stu-id="4cd9e-148">You can analyze protocol logs for the following components:</span></span>

  - <span data-ttu-id="4cd9e-149">Lync Server SipStack (SIP) </span><span class="sxs-lookup"><span data-stu-id="4cd9e-149">Lync Server SipStack (SIP)</span></span>

  - <span data-ttu-id="4cd9e-150">Lync Server S4 (SIP) </span><span class="sxs-lookup"><span data-stu-id="4cd9e-150">Lync Server S4 (SIP)</span></span>

  - <span data-ttu-id="4cd9e-151">Lync Server 會議信號流量 (C3P) （包括 MCU 基礎 C3P 和 Focus C3P）</span><span class="sxs-lookup"><span data-stu-id="4cd9e-151">Lync Server Conferencing signaling traffic (C3P), including MCU Infra C3P and Focus C3P</span></span>

  - <span data-ttu-id="4cd9e-152">Lync Server Web 會議流量 (PSOM) </span><span class="sxs-lookup"><span data-stu-id="4cd9e-152">Lync Server Web conferencing traffic (PSOM)</span></span>

  - <span data-ttu-id="4cd9e-153">Lync Server 整合通訊用戶端平臺用戶端 (UCCP) </span><span class="sxs-lookup"><span data-stu-id="4cd9e-153">Lync Server Unified Communications Client Platform client (UCCP)</span></span>

  - <span data-ttu-id="4cd9e-154">封存資料庫的錯誤報表</span><span class="sxs-lookup"><span data-stu-id="4cd9e-154">Error reports from the archiving database</span></span>

<span data-ttu-id="4cd9e-155">若要協助組織所需任務的效能，請參閱 As-Needed 作業檢查清單。</span><span class="sxs-lookup"><span data-stu-id="4cd9e-155">To help organize the performance of as-needed tasks, see As-Needed Operations Checklist.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4cd9e-156">如需詳細的系統管理和管理程式，請參閱 Microsoft Lync Server 2013 管理指南。</span><span class="sxs-lookup"><span data-stu-id="4cd9e-156">For detailed administration and management procedures, see the Microsoft Lync Server 2013 Administration Guide.</span></span>



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a><span data-ttu-id="4cd9e-157">備份 (及還原) 原則或配置設定</span><span class="sxs-lookup"><span data-stu-id="4cd9e-157">Backup (and restore) policies or configuration settings</span></span>

<span data-ttu-id="4cd9e-158">Lync Server 2013 可讓您備份及還原整個系統。</span><span class="sxs-lookup"><span data-stu-id="4cd9e-158">Lync Server 2013 lets you back up and restore the whole system.</span></span> <span data-ttu-id="4cd9e-159">Iif 您要備份 (，然後可能是天的還原) 單一原則或單一的設定集集合、檢索適當的原則，然後將該物件以管道傳送至 Export-Clixml Cmdlet，該物件會將原則資訊儲存為 XML 檔案：</span><span class="sxs-lookup"><span data-stu-id="4cd9e-159">Iif you want to back up (and then maybe someday restore) a single policy or a single collection of configuration settings, retrieve the appropriate policy, and then pipe that object to the Export-Clixml cmdlet, which saves the policy information as an XML file:</span></span>

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

<span data-ttu-id="4cd9e-160">您現在可以試驗 RedmondClientPolicy，並變更許多設定。</span><span class="sxs-lookup"><span data-stu-id="4cd9e-160">You may now experiment with RedmondClientPolicy and change lots of the settings.</span></span> <span data-ttu-id="4cd9e-161">如果您決定改為還原舊的原則，請輸入：</span><span class="sxs-lookup"><span data-stu-id="4cd9e-161">If you decide instead to restore the old policy, enter:</span></span>

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

<span data-ttu-id="4cd9e-162">請注意，此方法適用于大部分的原則及設定，但不會使用某些較複雜的專案（包含多個子物件的專案） (例如路由設定設定，其中包含許多不同的語音路由) 。</span><span class="sxs-lookup"><span data-stu-id="4cd9e-162">Note that this approach will work for most policies and settings but it won't work with some of the more complex items—items that contain multiple sub-objects (like routing configuration settings, which contain many separate voice routes).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

