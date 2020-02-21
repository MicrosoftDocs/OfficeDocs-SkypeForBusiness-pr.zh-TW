---
title: Lync Server 2013： 安裝 Lync Server 2013 監控報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync Server 2013 Monitoring Reports
ms:assetid: 6f417569-b100-442c-ad48-fdd794626cf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204989(v=OCS.15)
ms:contentKeyID: 48184445
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1a2694aaef4845b776b09f6c57fec65ca77b77b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-lync-server-2013-monitoring-reports"></a><span data-ttu-id="f9d3f-102">安裝 Lync Server 2013 監控報告</span><span class="sxs-lookup"><span data-stu-id="f9d3f-102">Installing Lync Server 2013 Monitoring Reports</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9d3f-103">_**主題上次修改日期：** 2015 年 02 月 27 日_</span><span class="sxs-lookup"><span data-stu-id="f9d3f-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="f9d3f-104">Microsoft Lync Server 2013 Monitoring Reports 為您提供豐富的組織中進行通訊工作階段的數量和品質的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-104">Microsoft Lync Server 2013 Monitoring Reports provide you with a wealth of information about the quality and quantity of the communication sessions that take place in your organization.</span></span> <span data-ttu-id="f9d3f-105">不過，監控報告不會自動安裝當您安裝 Lync Server 2013;相反地，您必須安裝監控報告分開，而且只有事後 Lync 伺服器已安裝在電腦上。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-105">However, Monitoring Reports are not automatically installed when you install Lync Server 2013; instead, you must install Monitoring Reports separately, and only after Lync Server has been installed on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f9d3f-p102">建議您將監控報告安裝在已安裝監控資料庫之相同電腦上，如此可簡化存取報告的指派權限程序：將監控報告安裝在裝載監控存放區的電腦上，表示您不需要設定權限以允許某一台電腦上的資料庫與在第二台電腦執行的 Reporting Services 進行互動。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-p102">It is recommended that you install Monitoring Reports on the same computer where the monitoring database is installed. This simplifies the process of assigning permissions for accessing the reports: installing Monitoring Reports on the computer that hosts the monitoring store means that you will not have to configure permissions that allow a database on one computer to interact with Reporting Services running on a second computer.</span></span>



</div>

<span data-ttu-id="f9d3f-108">Lync Server 監控報告包含超過 30 設計用來提供會議、 對等 IM 工作階段、 使用者註冊、 回應群組應用程式，以及執行更多功能的詳細的資訊的報表。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-108">Lync Server Monitoring Reports include over 30 reports designed to provide detailed information about conferences, peer-to-peer IM sessions, user registrations, the Response Group application, and much more.</span></span> <span data-ttu-id="f9d3f-109">Proplus 2013 版，Lync Server 監控報告包含多項增強功能：</span><span class="sxs-lookup"><span data-stu-id="f9d3f-109">For the 2013 version, Lync Server Monitoring Reports include a number of enhancements:</span></span>

  - <span data-ttu-id="f9d3f-110">**新的語音品質報告**。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-110">**New voice quality reports**.</span></span> <span data-ttu-id="f9d3f-111">這些新報告包含[Lync Server 2013 中的媒體品質比較報表](lync-server-2013-media-quality-comparison-report.md)，其比較品質之間的不同類型通話 （例如，之間有線的通話和無線通話）;與[Lync Server 2013 中的會議加入時間報表](lync-server-2013-conference-join-time-report.md)，其會提供關於的時間資訊需要加入會議的使用者。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-111">These new reports include the [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md), which compares quality between different types of calls (for example, between wired calls and wireless calls); and the [Conference Join Time Report in Lync Server 2013](lync-server-2013-conference-join-time-report.md), which provides information regarding the amount of time requires for users to join a conference.</span></span>

  - <span data-ttu-id="f9d3f-112">**針對視訊與應用程式共用工作階段進行分析和疑難排解的改善報告。**</span><span class="sxs-lookup"><span data-stu-id="f9d3f-112">**Improved reports for analyzing and troubleshooting both video and application sharing sessions.**</span></span> <span data-ttu-id="f9d3f-113">[Lync Server 2013 中的媒體品質摘要報告](lync-server-2013-media-quality-summary-report.md)提供的方法來分析視訊及應用程式共用通話時[在 Lync Server 2013 中的伺服器效能報告](lync-server-2013-server-performance-report.md)詳述產生這些通話的伺服器的效能。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-113">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) provides a way to analyze video and application sharing calls, while the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) details the performance of servers generating these calls.</span></span> <span data-ttu-id="f9d3f-114">現在還可以[在 Lync Server 2013 中的端對端工作階段詳細資料報告](lync-server-2013-peer-to-peer-session-detail-report.md)和[Lync Server 2013 中的會議詳細資料報告](lync-server-2013-conference-detail-report.md)所回報視訊及應用程式共用計量。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-114">Video and application sharing metrics are also now reported by the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) and the [Conference Detail Report in Lync Server 2013](lync-server-2013-conference-detail-report.md).</span></span>

  - <span data-ttu-id="f9d3f-p106">**改善報告效能**。包括加速回應與資料擷取時間，以及更迅速而簡便瀏覽報告。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-p106">**Improved report performance**. This includes faster response and data retrieval time, as well as faster and easier navigation through the reports.</span></span>

<span data-ttu-id="f9d3f-117">有關個別報告的詳細資訊，可在監控報告文件中取得。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-117">More information on the individual reports can be found in the Monitoring Reports documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f9d3f-118">還有另一個新報表 – QoE 通話詳細資料子報表 – 包含 Lync Server 2013 中。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-118">There is another new report – QoE Call Detail Subreport – included in Lync Server 2013.</span></span> <span data-ttu-id="f9d3f-119">但是，此報告主要用於內部，無法直接存取。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-119">However, this report is primarily for internal use, and is not intended to be directly accessed.</span></span>



</div>

<span data-ttu-id="f9d3f-120">若要安裝 Lync Server Monitoring Reports 的兩種方式： 您可以使用 Lync Server 部署精靈，或您可以使用 Windows PowerShell 指令碼隨附的 Lync Server 2013 安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-120">There are two ways to install Lync Server Monitoring Reports: you can use the Lync Server Deployment Wizard or you can use a Windows PowerShell script included with the Lync Server 2013 installation files.</span></span> <span data-ttu-id="f9d3f-121">無論您使用哪一種方法安裝報告，都必須先確認您具備下列條件：</span><span class="sxs-lookup"><span data-stu-id="f9d3f-121">Regardless of the method you use to install the reports you must first make sure that you:</span></span>

  - <span data-ttu-id="f9d3f-122">具備將資料庫角色新增至監控資料庫中使用者帳戶的權限。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-122">Have the right to add a database role to a user account in the monitoring database.</span></span>

  - <span data-ttu-id="f9d3f-p109">在 SQL Server Reporting Services 中具有「內容管理員」角色。這個角色會賦予您將報告部署至 SQL Server Reporting Services 的權限。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-p109">Hold the Content Manager role in SQL Server Reporting Services. This role gives you the right to deploy reports to SQL Server Reporting Services.</span></span>

<span data-ttu-id="f9d3f-125">若要使用部署精靈安裝監控報告，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f9d3f-125">To install the Monitoring Reports by using the Deployment Wizard, complete the following steps:</span></span>

1.  <span data-ttu-id="f9d3f-126">按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 部署精靈**。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-126">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="f9d3f-127">在部署精靈中按一下 **[部署監控報告]** 以啟動「部署監控報告」精靈。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-127">In the Deployment Wizard, click **Deploy Monitoring Reports** in order to start the Deploy Monitoring Reports wizard.</span></span>

3.  <span data-ttu-id="f9d3f-p110">在部署監控報告精靈中的 **[指定監控資料庫]** 頁面上，請確認裝載您監控存放區之電腦的完整網域名稱顯示於 **[監控資料庫]** 下拉式清單中。(如果您有多個監控存放區，則必須從下拉式清單選取適當的伺服器。) 確認正確的 SQL Server 執行個體顯示於 **[SQL Server Reporting Services (SSRS) 執行個體]** 方塊中 (例如 **atl-sql-001.litwareinc.com/archinst**)，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-p110">In the Deploy Monitoring Reports wizard, on the **Specify Monitoring Database** page, make sure that the fully qualified domain name of the computer hosting your monitoring store appears in the **Monitoring database** dropdown list. (If you have multiple monitoring stores you will need to select the appropriate server from the dropdown list.) Verify that the correct SQL Server instance appears in the **SQL Server Reporting Services (SSRS) instance** box (for example, **atl-sql-001.litwareinc.com/archinst**) and then click **Next**.</span></span>

4.  <span data-ttu-id="f9d3f-130">在 [**指定認證**] 頁面上，在 [**使用者名稱**] 方塊中，輸入要用來存取監控報告之帳戶的使用者名稱與網域名稱 (例如， **litwareinc\\kenmyer**)。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-130">On the **Specify Credentials** page, in the **User name** box, type the domain name and user name of the account to be used when accessing the Monitoring Reports (for example, **litwareinc\\kenmyer**).</span></span> <span data-ttu-id="f9d3f-131">如果您不使用此格式 (網域\\使用者名稱) 會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-131">If you do not use this format (domain\\user name) an error will occur.</span></span>
    
    <span data-ttu-id="f9d3f-132">在 **[密碼]** 方塊中輸入使用者帳戶密碼，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-132">Type the user account password in the **Password** box, and then click **Next**.</span></span> <span data-ttu-id="f9d3f-133">請注意沒有特殊權限所需的此帳戶。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-133">Note that no special rights are required for this account.</span></span> <span data-ttu-id="f9d3f-134">將會自動授與帳戶所需的登入名稱與資料庫權限安裝程式完成時。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-134">The account will automatically be granted the required logon and database permissions when setup completes.</span></span>

5.  <span data-ttu-id="f9d3f-p113">在 **[指定唯讀群組]** 頁面上的使用者群組方塊中，輸入將授與 SQL Server Reporting Services 唯讀存取權的安全性群組名稱。例如，若要指定唯讀系統管理員存取報告，請輸入 **RTCUniversalReadOnlyAdmins**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-p113">On the **Specify Read-Only Group** page enter the name of a security group that will be granted read-only access to the SQL Server Reporting Services in the User group box. For example, to give read-only administrators access to the reports enter **RTCUniversalReadOnlyAdmins**. Click **Next**.</span></span>

6.  <span data-ttu-id="f9d3f-138">在 **[執行命令]** 頁面上按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-138">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="f9d3f-139">監控報告也可以安裝 Lync Server 管理命令介面中執行指令碼 DeployReports.ps1;這個 Windows PowerShell 指令碼可以在 Lync Server 安裝媒體上找到\\安裝\\ReportingSetup 資料夾。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-139">Monitoring Reports can also be installed from the Lync Server Management Shell by running the script DeployReports.ps1; this Windows PowerShell script can be found on the Lync Server installation media in the \\Setup\\ReportingSetup folder.</span></span> <span data-ttu-id="f9d3f-140">若要使用 DeployReports.ps1 安裝監控報告，請在管理介面提示中輸入類似下列命令：</span><span class="sxs-lookup"><span data-stu-id="f9d3f-140">To install Monitoring Reports using DeployReports.ps1, type a command similar to the following at the Management Shell prompt:</span></span>

    C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

<span data-ttu-id="f9d3f-141">用於以上命令的參數會在下表加以說明：</span><span class="sxs-lookup"><span data-stu-id="f9d3f-141">The parameters used in the preceding command are described in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9d3f-142">參數名稱</span><span class="sxs-lookup"><span data-stu-id="f9d3f-142">Parameter Name</span></span></th>
<th><span data-ttu-id="f9d3f-143">必要</span><span class="sxs-lookup"><span data-stu-id="f9d3f-143">Required</span></span></th>
<th><span data-ttu-id="f9d3f-144">描述</span><span class="sxs-lookup"><span data-stu-id="f9d3f-144">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9d3f-145">storedUserName</span><span class="sxs-lookup"><span data-stu-id="f9d3f-145">storedUserName</span></span></p></td>
<td><p><span data-ttu-id="f9d3f-146">是</span><span class="sxs-lookup"><span data-stu-id="f9d3f-146">Yes</span></span></p></td>
<td><p><span data-ttu-id="f9d3f-147">用於存取監控存放區的使用者帳戶 (格式為網域\使用者名稱)；例如：</span><span class="sxs-lookup"><span data-stu-id="f9d3f-147">User account (in the format domain\username) used to access the monitoring store; for example:</span></span></p>
<pre><code>-storedUserName &quot;litwareinc\kenmyer&quot;</code></pre>
<p><span data-ttu-id="f9d3f-148">此帳戶必須具有先前指定的 SQL Server 及 SQL Server Reporting Services 權限，否則指令碼將會失敗。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-148">This account must have the previously-specified SQL Server and SQL Server Reporting Services permissions or the script will fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9d3f-149">storedPassword</span><span class="sxs-lookup"><span data-stu-id="f9d3f-149">storedPassword</span></span></p></td>
<td><p><span data-ttu-id="f9d3f-150">是</span><span class="sxs-lookup"><span data-stu-id="f9d3f-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="f9d3f-151">用於存取監控存放區的使用者帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-151">Password for the user account used to access the monitoring store.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9d3f-152">readOnlyGroupName</span><span class="sxs-lookup"><span data-stu-id="f9d3f-152">readOnlyGroupName</span></span></p></td>
<td><p><span data-ttu-id="f9d3f-153">否</span><span class="sxs-lookup"><span data-stu-id="f9d3f-153">No</span></span></p></td>
<td><p><span data-ttu-id="f9d3f-154">授與成員監控報告唯讀權限的網域或本機安全性群組。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-154">Domain or local security group whose members will be granted read-only access to the Monitoring Reports.</span></span> <span data-ttu-id="f9d3f-155">請注意，如果指定的群組不存在，指令碼就會失效。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-155">Note that the script will fail if the specified group does not exist.</span></span> <span data-ttu-id="f9d3f-156">如果您稍後決定撤銷這些權限，或是決定將權限授與其他使用者或群組，可使用 SQL Service Reporting Services 報表管理員執行這些動作。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-156">If you later decide to revoke these permissions, or if you decide to grant other users or other groups access permissions, you can do so using the SQL Service Reporting Services Report Manager.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9d3f-157">reportSqlServerInstance</span><span class="sxs-lookup"><span data-stu-id="f9d3f-157">reportSqlServerInstance</span></span></p></td>
<td><p><span data-ttu-id="f9d3f-158">否</span><span class="sxs-lookup"><span data-stu-id="f9d3f-158">No</span></span></p></td>
<td><p><span data-ttu-id="f9d3f-p116">託管 Reporting Service 的 SQL Server 執行個體。必須使用 Report Server 的完整網域名稱指定報告執行個體；例如：</span><span class="sxs-lookup"><span data-stu-id="f9d3f-p116">SQL Server instance that hosts the Reporting Service. The Reporting instance must be specified using the fully qualified domain name of the Report Server; for example:</span></span></p>
<pre><code>-reportServerSqlInstance atl-sql-001.litwareinc.com</code></pre>
<p><span data-ttu-id="f9d3f-161">如果不包含此參數，指令碼會假定 Reporting Services 由託管監控資料庫之相同的 SQL Server 執行個體託管。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-161">If this parameter is not included the script will assume that the reporting services are hosted by the same SQL Server instance that hosts the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9d3f-162">monitoringDatabaseId</span><span class="sxs-lookup"><span data-stu-id="f9d3f-162">monitoringDatabaseId</span></span></p></td>
<td><p><span data-ttu-id="f9d3f-163">否</span><span class="sxs-lookup"><span data-stu-id="f9d3f-163">No</span></span></p></td>
<td><p><span data-ttu-id="f9d3f-p117">監控資料庫的服務識別。您可執行此命令返回監控資料庫的識別：</span><span class="sxs-lookup"><span data-stu-id="f9d3f-p117">Service Identity for the monitoring database. You can return the Identities for your monitoring databases by running this command:</span></span></p>
<pre><code>Get-CsService -MonitoringDatabase</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f9d3f-166">安裝監控報告之後，您必須接著使用 Set-CsReportingConfiguration Cmdlet 以設定用於存取這些報告的 URL。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-166">After the Monitoring Reports have been installed you must then use the Set-CsReportingConfiguration cmdlet to configure the URL used to access these reports.</span></span> <span data-ttu-id="f9d3f-167">這項工作須先從 Lync Server 管理命令介面執行下列 Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-167">This task can be carried out from the Lync Server Management Shell by running the following Windows PowerShell command.</span></span> <span data-ttu-id="f9d3f-168">請注意，建議您在設定報告 URL 時使用 HTTPS 通訊協定 (非必要)：</span><span class="sxs-lookup"><span data-stu-id="f9d3f-168">Note that it is recommended, but not required, that you use the HTTPS protocol when configuring the reporting URL:</span></span>

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

<span data-ttu-id="f9d3f-p119">以上的命令中，ReportingUrl 屬性應設為 SQL Server 2008 R2 Reporting Services 所使用的報表管理員 URL。您可在已安裝 SQL Server Reporting Services 的電腦上透過完成下列步驟來決定報表管理員 URL：</span><span class="sxs-lookup"><span data-stu-id="f9d3f-p119">In the preceding command, the ReportingUrl property should be set to the Report Manager URL used by SQL Server 2008 R2 Reporting Services. You can determine the Report Manager URL by completing the following steps on the computer where SQL Server Reporting Services has been installed:</span></span>

1.  <span data-ttu-id="f9d3f-171">依序按一下 [開始]、[所有程式]、[Microsoft SQL Server 2008 R2]、[組態工具]，然後按一下 [Reporting Services 組態管理員]。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-171">Click Start, click All Programs, click Microsoft SQL Server 2008 R2, click Configuration Tools, and then click Reporting Services Configuration Manager.</span></span>

2.  <span data-ttu-id="f9d3f-p120">在 [Reporting Services 組態連接] 對話方塊中，請確定 Reporting Services 電腦名稱顯示於 [伺服器名稱] 對話方塊中。從 [報告伺服器執行個體] 下拉式清單中選取 SQL Server 執行個體，然後按一下 [連線]。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-p120">In the Reporting Services Configuration Connection dialog box, make sure that the name of the Reporting Services computer appears in the Server Name box. Select the SQL Server instance from the Report Server Instance dropdown list and then click Connect.</span></span>

3.  <span data-ttu-id="f9d3f-p121">在 [Reporting Services 組態管理員] 中，按一下 [報表管理員 URL]，[報表管理員 URL] 窗格應該會顯示一個以上的 URL。雖然其中任何 URL 皆可作為報告 URL 之用，再一次申明，建議您採用使用 HTTPS 通訊協定的 ReportingUrl 。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-p121">In Reporting Services Configuration Manager, click Report Manager URL. One or more URLs should appear in the Report Manager URL pane. Any of these URLs can be used as the Reporting URL although, again, it is recommended that the ReportingUrl use the HTTPS protocol.</span></span>

<span data-ttu-id="f9d3f-177">如果您已設定鏡像資料庫的監控資料庫然後您必須也關聯監控報告之鏡像資料庫。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-177">If you have set up a mirror database for your monitoring database then you must also associate the Monitoring Reports with the mirror database.</span></span> <span data-ttu-id="f9d3f-178">請參閱如需詳細資訊的文件[關聯監控報告與 Lync Server 2013 的鏡像資料庫](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md)。</span><span class="sxs-lookup"><span data-stu-id="f9d3f-178">See the article [Associating Monitoring Reports with a mirror database in Lync Server 2013](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) for details.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

