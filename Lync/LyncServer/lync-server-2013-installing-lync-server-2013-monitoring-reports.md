---
title: Lync Server 2013：安裝 Lync Server 2013 監視報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing Lync Server 2013 Monitoring Reports
ms:assetid: 6f417569-b100-442c-ad48-fdd794626cf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204989(v=OCS.15)
ms:contentKeyID: 48184445
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5908e4eb8f18ef464a4c69cc31bffdc33a10416
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980367"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-server-2013-monitoring-reports"></a><span data-ttu-id="a77b1-102">安裝 Lync Server 2013 監視報告</span><span class="sxs-lookup"><span data-stu-id="a77b1-102">Installing Lync Server 2013 Monitoring Reports</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a77b1-103">_**主題上次修改日期：** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="a77b1-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="a77b1-104">Microsoft Lync Server 2013 監控報告提供大量有關貴組織中所發生之通訊會話品質和數量的資訊。</span><span class="sxs-lookup"><span data-stu-id="a77b1-104">Microsoft Lync Server 2013 Monitoring Reports provide you with a wealth of information about the quality and quantity of the communication sessions that take place in your organization.</span></span> <span data-ttu-id="a77b1-105">不過，當您安裝 Lync Server 2013 時，系統不會自動安裝監視報告;相反地，您必須單獨安裝監視報告，而且只有在電腦上安裝 Lync Server 之後才能安裝。</span><span class="sxs-lookup"><span data-stu-id="a77b1-105">However, Monitoring Reports are not automatically installed when you install Lync Server 2013; instead, you must install Monitoring Reports separately, and only after Lync Server has been installed on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a77b1-106">建議您在安裝監視資料庫的同一部電腦上安裝監視報告。</span><span class="sxs-lookup"><span data-stu-id="a77b1-106">It is recommended that you install Monitoring Reports on the same computer where the monitoring database is installed.</span></span> <span data-ttu-id="a77b1-107">這簡化了指派許可權以存取報表的程式：在託管監視存放區的電腦上安裝監視報表，意味著您不需要設定允許一部電腦上的資料庫互動的許可權在另一部電腦上執行 Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="a77b1-107">This simplifies the process of assigning permissions for accessing the reports: installing Monitoring Reports on the computer that hosts the monitoring store means that you will not have to configure permissions that allow a database on one computer to interact with Reporting Services running on a second computer.</span></span>



</div>

<span data-ttu-id="a77b1-108">Lync Server 監視報告包含30個以上的報告，旨在提供會議、對等 IM 會話、使用者註冊、回應群組應用程式的詳細資訊，以及更多相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a77b1-108">Lync Server Monitoring Reports include over 30 reports designed to provide detailed information about conferences, peer-to-peer IM sessions, user registrations, the Response Group application, and much more.</span></span> <span data-ttu-id="a77b1-109">針對2013版本，Lync Server Monitoring 報表包含許多增強功能：</span><span class="sxs-lookup"><span data-stu-id="a77b1-109">For the 2013 version, Lync Server Monitoring Reports include a number of enhancements:</span></span>

  - <span data-ttu-id="a77b1-110">**新的語音品質報告**。</span><span class="sxs-lookup"><span data-stu-id="a77b1-110">**New voice quality reports**.</span></span> <span data-ttu-id="a77b1-111">這些新報告包括[Lync Server 2013 中的 [媒體質量比較] 報告](lync-server-2013-media-quality-comparison-report.md)，可比較不同類型的呼叫（例如，有線通話與無線通話之間）之間的品質。[Lync Server 2013 中的 [會議加入時間] 報告](lync-server-2013-conference-join-time-report.md)，可提供使用者加入會議所需的時間量資訊。</span><span class="sxs-lookup"><span data-stu-id="a77b1-111">These new reports include the [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), which compares quality between different types of calls (for example, between wired calls and wireless calls); and the [Conference Join Time Report in Lync Server 2013](lync-server-2013-conference-join-time-report.md), which provides information regarding the amount of time requires for users to join a conference.</span></span>

  - <span data-ttu-id="a77b1-112">**改善了分析和疑難排解影片與應用程式共用會話的報表。**</span><span class="sxs-lookup"><span data-stu-id="a77b1-112">**Improved reports for analyzing and troubleshooting both video and application sharing sessions.**</span></span> <span data-ttu-id="a77b1-113">[Lync server 2013 中的 [媒體質量摘要] 報告](lync-server-2013-media-quality-summary-report.md)提供一種分析視頻與應用程式共用通話的方式，而[lync server 2013 中的 [伺服器效能] 報告](lync-server-2013-server-performance-report.md)則會詳細說明產生這些呼叫的伺服器效能。</span><span class="sxs-lookup"><span data-stu-id="a77b1-113">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) provides a way to analyze video and application sharing calls, while the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) details the performance of servers generating these calls.</span></span> <span data-ttu-id="a77b1-114">[在 Lync server 2013 的點對點工作階段詳細資料包告](lync-server-2013-peer-to-peer-session-detail-report.md)以及[lync server 2013](lync-server-2013-conference-detail-report.md)中的 [會議詳細資料] 報告，現在也會報告影片和應用程式共用度量。</span><span class="sxs-lookup"><span data-stu-id="a77b1-114">Video and application sharing metrics are also now reported by the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) and the [Conference Detail Report in Lync Server 2013](lync-server-2013-conference-detail-report.md).</span></span>

  - <span data-ttu-id="a77b1-115">**改善報表效能**。</span><span class="sxs-lookup"><span data-stu-id="a77b1-115">**Improved report performance**.</span></span> <span data-ttu-id="a77b1-116">這包括更快速的回應與資料檢索時間，以及更快速且更輕鬆地流覽報表的功能。</span><span class="sxs-lookup"><span data-stu-id="a77b1-116">This includes faster response and data retrieval time, as well as faster and easier navigation through the reports.</span></span>

<span data-ttu-id="a77b1-117">您可以在 [監視報告] 檔中找到個別報告的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a77b1-117">More information on the individual reports can be found in the Monitoring Reports documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a77b1-118">在 Lync Server 2013 中包含另一個新的報表-QoE 通話詳細資料子報表。</span><span class="sxs-lookup"><span data-stu-id="a77b1-118">There is another new report – QoE Call Detail Subreport – included in Lync Server 2013.</span></span> <span data-ttu-id="a77b1-119">不過，此報告主要供內部使用，且不應直接存取。</span><span class="sxs-lookup"><span data-stu-id="a77b1-119">However, this report is primarily for internal use, and is not intended to be directly accessed.</span></span>



</div>

<span data-ttu-id="a77b1-120">有兩種方式可以安裝 Lync Server Monitoring 報告：您可以使用 Lync Server 部署嚮導，也可以使用 Lync Server 2013 安裝檔案隨附的 Windows PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="a77b1-120">There are two ways to install Lync Server Monitoring Reports: you can use the Lync Server Deployment Wizard or you can use a Windows PowerShell script included with the Lync Server 2013 installation files.</span></span> <span data-ttu-id="a77b1-121">無論您使用何種方法來安裝報表，您必須先確定：</span><span class="sxs-lookup"><span data-stu-id="a77b1-121">Regardless of the method you use to install the reports you must first make sure that you:</span></span>

  - <span data-ttu-id="a77b1-122">有權將資料庫角色新增到監視資料庫中的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="a77b1-122">Have the right to add a database role to a user account in the monitoring database.</span></span>

  - <span data-ttu-id="a77b1-123">在 SQL Server Reporting Services 中保留內容管理員角色。</span><span class="sxs-lookup"><span data-stu-id="a77b1-123">Hold the Content Manager role in SQL Server Reporting Services.</span></span> <span data-ttu-id="a77b1-124">這個角色提供將報表部署至 SQL Server Reporting Services 的權利。</span><span class="sxs-lookup"><span data-stu-id="a77b1-124">This role gives you the right to deploy reports to SQL Server Reporting Services.</span></span>

<span data-ttu-id="a77b1-125">若要使用 [部署嚮導] 安裝監視報告，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a77b1-125">To install the Monitoring Reports by using the Deployment Wizard, complete the following steps:</span></span>

1.  <span data-ttu-id="a77b1-126">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 部署嚮導]**。</span><span class="sxs-lookup"><span data-stu-id="a77b1-126">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="a77b1-127">在 [部署嚮導] 中，按一下 [**部署監視報表**]，以啟動 [部署監視報表] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="a77b1-127">In the Deployment Wizard, click **Deploy Monitoring Reports** in order to start the Deploy Monitoring Reports wizard.</span></span>

3.  <span data-ttu-id="a77b1-128">在 [部署監視報表] 嚮導中的 [**指定監視資料庫**] 頁面上，確認 [**監視資料庫**] 下拉式清單中顯示的是託管監視存放區之電腦的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="a77b1-128">In the Deploy Monitoring Reports wizard, on the **Specify Monitoring Database** page, make sure that the fully qualified domain name of the computer hosting your monitoring store appears in the **Monitoring database** dropdown list.</span></span> <span data-ttu-id="a77b1-129">（如果您有多個監視儲存區，您將需要從下拉式清單中選取適當的伺服器）。確認**Sql Server Reporting Services （SSRS） [實例**] 方塊（例如**atl-sql-001.litwareinc.com/archinst**）中出現正確的 sql server 實例，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a77b1-129">(If you have multiple monitoring stores you will need to select the appropriate server from the dropdown list.) Verify that the correct SQL Server instance appears in the **SQL Server Reporting Services (SSRS) instance** box (for example, **atl-sql-001.litwareinc.com/archinst**) and then click **Next**.</span></span>

4.  <span data-ttu-id="a77b1-130">在 [**指定認證**] 頁面上的 [**使用者名稱**] 方塊中，輸入存取監視報告時要使用之帳戶的功能變數名稱和使用者名稱（例如， \*\* \\litwareinc kenmyer\*\*）。</span><span class="sxs-lookup"><span data-stu-id="a77b1-130">On the **Specify Credentials** page, in the **User name** box, type the domain name and user name of the account to be used when accessing the Monitoring Reports (for example, **litwareinc\\kenmyer**).</span></span> <span data-ttu-id="a77b1-131">如果您不使用此格式（網域\\使用者名稱），就會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="a77b1-131">If you do not use this format (domain\\user name) an error will occur.</span></span>
    
    <span data-ttu-id="a77b1-132">在 [**密碼**] 方塊中輸入使用者帳戶密碼，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a77b1-132">Type the user account password in the **Password** box, and then click **Next**.</span></span> <span data-ttu-id="a77b1-133">請注意，此帳戶不需要特殊許可權。</span><span class="sxs-lookup"><span data-stu-id="a77b1-133">Note that no special rights are required for this account.</span></span> <span data-ttu-id="a77b1-134">安裝程式完成時，系統會自動授與帳戶所需的登入和資料庫許可權。</span><span class="sxs-lookup"><span data-stu-id="a77b1-134">The account will automatically be granted the required logon and database permissions when setup completes.</span></span>

5.  <span data-ttu-id="a77b1-135">在 [**指定唯讀群組**] 頁面上，在 [使用者群組] 方塊中，輸入將被授與 SQL Server Reporting Services 唯讀存取權的安全性群組名稱。</span><span class="sxs-lookup"><span data-stu-id="a77b1-135">On the **Specify Read-Only Group** page enter the name of a security group that will be granted read-only access to the SQL Server Reporting Services in the User group box.</span></span> <span data-ttu-id="a77b1-136">例如，若要賦予唯讀管理員對報表的存取權，請輸入**RTCUniversalReadOnlyAdmins**。</span><span class="sxs-lookup"><span data-stu-id="a77b1-136">For example, to give read-only administrators access to the reports enter **RTCUniversalReadOnlyAdmins**.</span></span> <span data-ttu-id="a77b1-137">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a77b1-137">Click **Next**.</span></span>

6.  <span data-ttu-id="a77b1-138">在 [**執行命令**] 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="a77b1-138">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="a77b1-139">您也可以透過執行腳本 DeployReports. ps1; 來從 Lync Server 管理命令介面安裝監視報告。這個 Windows PowerShell 腳本可在 Lync Server 安裝媒體的 [ \\設定\\ReportingSetup] 資料夾中找到。</span><span class="sxs-lookup"><span data-stu-id="a77b1-139">Monitoring Reports can also be installed from the Lync Server Management Shell by running the script DeployReports.ps1; this Windows PowerShell script can be found on the Lync Server installation media in the \\Setup\\ReportingSetup folder.</span></span> <span data-ttu-id="a77b1-140">若要使用 DeployReports 安裝監視報表，請在管理命令介面提示處輸入類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="a77b1-140">To install Monitoring Reports using DeployReports.ps1, type a command similar to the following at the Management Shell prompt:</span></span>

    C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

<span data-ttu-id="a77b1-141">下表說明前面命令中使用的參數：</span><span class="sxs-lookup"><span data-stu-id="a77b1-141">The parameters used in the preceding command are described in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a77b1-142">參數名稱</span><span class="sxs-lookup"><span data-stu-id="a77b1-142">Parameter Name</span></span></th>
<th><span data-ttu-id="a77b1-143">必要</span><span class="sxs-lookup"><span data-stu-id="a77b1-143">Required</span></span></th>
<th><span data-ttu-id="a77b1-144">描述</span><span class="sxs-lookup"><span data-stu-id="a77b1-144">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a77b1-145">storedUserName</span><span class="sxs-lookup"><span data-stu-id="a77b1-145">storedUserName</span></span></p></td>
<td><p><span data-ttu-id="a77b1-146">是</span><span class="sxs-lookup"><span data-stu-id="a77b1-146">Yes</span></span></p></td>
<td><p><span data-ttu-id="a77b1-147">用來存取監視存放區之使用者帳戶（格式為 [域 \ 使用者名]）;例如：</span><span class="sxs-lookup"><span data-stu-id="a77b1-147">User account (in the format domain\username) used to access the monitoring store; for example:</span></span></p>
<pre><code>-storedUserName &quot;litwareinc\kenmyer&quot;</code></pre>
<p><span data-ttu-id="a77b1-148">這個帳戶必須擁有先前指定的 SQL Server 和 SQL Server Reporting Services 許可權，否則腳本將會失敗。</span><span class="sxs-lookup"><span data-stu-id="a77b1-148">This account must have the previously-specified SQL Server and SQL Server Reporting Services permissions or the script will fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b1-149">storedPassword</span><span class="sxs-lookup"><span data-stu-id="a77b1-149">storedPassword</span></span></p></td>
<td><p><span data-ttu-id="a77b1-150">是</span><span class="sxs-lookup"><span data-stu-id="a77b1-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="a77b1-151">用來存取監視存放區之使用者帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="a77b1-151">Password for the user account used to access the monitoring store.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b1-152">readOnlyGroupName</span><span class="sxs-lookup"><span data-stu-id="a77b1-152">readOnlyGroupName</span></span></p></td>
<td><p><span data-ttu-id="a77b1-153">否</span><span class="sxs-lookup"><span data-stu-id="a77b1-153">No</span></span></p></td>
<td><p><span data-ttu-id="a77b1-154">網域或本機安全性群組，其成員將被授與監控報告的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="a77b1-154">Domain or local security group whose members will be granted read-only access to the Monitoring Reports.</span></span> <span data-ttu-id="a77b1-155">請注意，如果指定的群組不存在，腳本將會失敗。</span><span class="sxs-lookup"><span data-stu-id="a77b1-155">Note that the script will fail if the specified group does not exist.</span></span> <span data-ttu-id="a77b1-156">如果您稍後決定要撤銷這些許可權，或者如果您決定要授與其他使用者或其他群組的存取權限，您可以使用 SQL 服務 Reporting Services 報表管理員來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="a77b1-156">If you later decide to revoke these permissions, or if you decide to grant other users or other groups access permissions, you can do so using the SQL Service Reporting Services Report Manager.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b1-157">reportSqlServerInstance</span><span class="sxs-lookup"><span data-stu-id="a77b1-157">reportSqlServerInstance</span></span></p></td>
<td><p><span data-ttu-id="a77b1-158">否</span><span class="sxs-lookup"><span data-stu-id="a77b1-158">No</span></span></p></td>
<td><p><span data-ttu-id="a77b1-159">託管報表服務的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="a77b1-159">SQL Server instance that hosts the Reporting Service.</span></span> <span data-ttu-id="a77b1-160">報告實例必須使用報表伺服器的完整功能變數名稱來指定;例如：</span><span class="sxs-lookup"><span data-stu-id="a77b1-160">The Reporting instance must be specified using the fully qualified domain name of the Report Server; for example:</span></span></p>
<pre><code>-reportServerSqlInstance atl-sql-001.litwareinc.com</code></pre>
<p><span data-ttu-id="a77b1-161">如果此參數未包含，腳本將假設報表服務是由託管監視資料庫的相同 SQL Server 實例所託管。</span><span class="sxs-lookup"><span data-stu-id="a77b1-161">If this parameter is not included the script will assume that the reporting services are hosted by the same SQL Server instance that hosts the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b1-162">monitoringDatabaseId</span><span class="sxs-lookup"><span data-stu-id="a77b1-162">monitoringDatabaseId</span></span></p></td>
<td><p><span data-ttu-id="a77b1-163">否</span><span class="sxs-lookup"><span data-stu-id="a77b1-163">No</span></span></p></td>
<td><p><span data-ttu-id="a77b1-164">監視資料庫的服務身分識別。</span><span class="sxs-lookup"><span data-stu-id="a77b1-164">Service Identity for the monitoring database.</span></span> <span data-ttu-id="a77b1-165">您可以執行下列命令，以傳回監視資料庫的身分識別：</span><span class="sxs-lookup"><span data-stu-id="a77b1-165">You can return the Identities for your monitoring databases by running this command:</span></span></p>
<pre><code>Get-CsService -MonitoringDatabase</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a77b1-166">在已安裝監視報告之後，您必須使用 CsReportingConfiguration Cmdlet 來設定用來存取這些報告的 URL。</span><span class="sxs-lookup"><span data-stu-id="a77b1-166">After the Monitoring Reports have been installed you must then use the Set-CsReportingConfiguration cmdlet to configure the URL used to access these reports.</span></span> <span data-ttu-id="a77b1-167">您可以執行下列 Windows PowerShell 命令，從 Lync Server Management Shell 執行此工作。</span><span class="sxs-lookup"><span data-stu-id="a77b1-167">This task can be carried out from the Lync Server Management Shell by running the following Windows PowerShell command.</span></span> <span data-ttu-id="a77b1-168">請注意，建議您在設定報表 URL 時，使用 HTTPS 通訊協定，但這不是必要的。</span><span class="sxs-lookup"><span data-stu-id="a77b1-168">Note that it is recommended, but not required, that you use the HTTPS protocol when configuring the reporting URL:</span></span>

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

<span data-ttu-id="a77b1-169">在上述命令中，ReportingUrl 屬性應該設定為 SQL Server 2008 R2 Reporting Services 所使用的報表管理員 URL。</span><span class="sxs-lookup"><span data-stu-id="a77b1-169">In the preceding command, the ReportingUrl property should be set to the Report Manager URL used by SQL Server 2008 R2 Reporting Services.</span></span> <span data-ttu-id="a77b1-170">您可以在已安裝 SQL Server Reporting Services 的電腦上完成下列步驟，以判斷報表管理員 URL：</span><span class="sxs-lookup"><span data-stu-id="a77b1-170">You can determine the Report Manager URL by completing the following steps on the computer where SQL Server Reporting Services has been installed:</span></span>

1.  <span data-ttu-id="a77b1-171">按一下 [開始]，按一下 [所有程式]，按一下 [Microsoft SQL Server 2008 R2]，按一下 [設定工具]，然後按一下 [Reporting Services Configuration Manager]。</span><span class="sxs-lookup"><span data-stu-id="a77b1-171">Click Start, click All Programs, click Microsoft SQL Server 2008 R2, click Configuration Tools, and then click Reporting Services Configuration Manager.</span></span>

2.  <span data-ttu-id="a77b1-172">在 [Reporting Services 配置連線] 對話方塊中，確認 [伺服器名稱] 方塊中出現 [報表服務] 電腦的名稱。</span><span class="sxs-lookup"><span data-stu-id="a77b1-172">In the Reporting Services Configuration Connection dialog box, make sure that the name of the Reporting Services computer appears in the Server Name box.</span></span> <span data-ttu-id="a77b1-173">從 [報表伺服器實例] 下拉式清單中選取 [SQL Server 實例]，然後按一下 [連線]。</span><span class="sxs-lookup"><span data-stu-id="a77b1-173">Select the SQL Server instance from the Report Server Instance dropdown list and then click Connect.</span></span>

3.  <span data-ttu-id="a77b1-174">在 Reporting Services 組態管理員中，按一下 [報表管理員 URL]。</span><span class="sxs-lookup"><span data-stu-id="a77b1-174">In Reporting Services Configuration Manager, click Report Manager URL.</span></span> <span data-ttu-id="a77b1-175">一個或多個 Url 應該出現在 [報表管理員 URL] 窗格中。</span><span class="sxs-lookup"><span data-stu-id="a77b1-175">One or more URLs should appear in the Report Manager URL pane.</span></span> <span data-ttu-id="a77b1-176">您也可以將這些 Url 作為報告 URL 使用，但建議您再次使用 HTTPS 通訊協定 ReportingUrl。</span><span class="sxs-lookup"><span data-stu-id="a77b1-176">Any of these URLs can be used as the Reporting URL although, again, it is recommended that the ReportingUrl use the HTTPS protocol.</span></span>

<span data-ttu-id="a77b1-177">如果您已為監視資料庫設定鏡像資料庫，您也必須將監視報告與鏡像資料庫建立關聯。</span><span class="sxs-lookup"><span data-stu-id="a77b1-177">If you have set up a mirror database for your monitoring database then you must also associate the Monitoring Reports with the mirror database.</span></span> <span data-ttu-id="a77b1-178">如需詳細資訊，請參閱將 [[監視報告] 與 [Lync Server 2013] 中的鏡像資料庫相關聯](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md)。</span><span class="sxs-lookup"><span data-stu-id="a77b1-178">See the article [Associating Monitoring Reports with a mirror database in Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) for details.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

