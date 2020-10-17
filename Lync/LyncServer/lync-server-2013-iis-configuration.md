---
title: Lync Server 2013： IIS 設定
description: Lync Server 2013： IIS 設定。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 901aca7bf5ff8824b54e93754569a6ef5defc10e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554869"
---
# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="70ec0-103">Lync Server 2013 中的 IIS 設定</span><span class="sxs-lookup"><span data-stu-id="70ec0-103">IIS configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70ec0-104">_**主題上次修改日期：** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="70ec0-104">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="70ec0-105">若要順利完成此程式，您應該至少登入至本機系統管理員和網域使用者的伺服器。</span><span class="sxs-lookup"><span data-stu-id="70ec0-105">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="70ec0-106">設定及安裝 Lync Server 2013、Standard Edition 或集區中第一部前端伺服器的前端伺服器之前，請先針對 Internet information Services (IIS) 安裝及設定伺服器角色和 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="70ec0-106">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="70ec0-107">如果您的組織需要在系統磁片磁碟機以外的磁片磁碟機上找到 [IIS] 和 [所有 Web 服務]，您可以在初次安裝 Lync Server 2013 系統管理工具時，在 [安裝程式] 對話方塊中，變更 [Lync Server 2013 檔案] 的安裝位置路徑。</span><span class="sxs-lookup"><span data-stu-id="70ec0-107">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="70ec0-108">安裝 IIS 之前，請先安裝系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="70ec0-108">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="70ec0-109">若將安裝檔案安裝至此路徑（包括 OCSCore.msi），則其他的 Lync Server 2013 檔案也會同時部署至此磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="70ec0-109">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="70ec0-110">如需 dtails，請參閱 <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 系統管理工具</A>。</span><span class="sxs-lookup"><span data-stu-id="70ec0-110">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="70ec0-111">如需如何重新置放 Windows Server Manager 在安裝 IIS 時所部署之 INETPUB 的詳細資訊，請參閱 <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> 。</span><span class="sxs-lookup"><span data-stu-id="70ec0-111">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="70ec0-112">下表指出必要的 IIS 7.5 角色服務。</span><span class="sxs-lookup"><span data-stu-id="70ec0-112">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="70ec0-113">IIS 7.5 角色服務</span><span class="sxs-lookup"><span data-stu-id="70ec0-113">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70ec0-114">角色標題</span><span class="sxs-lookup"><span data-stu-id="70ec0-114">Role Heading</span></span></th>
<th><span data-ttu-id="70ec0-115">角色服務</span><span class="sxs-lookup"><span data-stu-id="70ec0-115">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-116">已安裝常見的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="70ec0-116">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="70ec0-117">靜態內容</span><span class="sxs-lookup"><span data-stu-id="70ec0-117">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-118">已安裝常見的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="70ec0-118">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="70ec0-119">預設檔</span><span class="sxs-lookup"><span data-stu-id="70ec0-119">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-120">已安裝常見的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="70ec0-120">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="70ec0-121">HTTP 錯誤</span><span class="sxs-lookup"><span data-stu-id="70ec0-121">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-122">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="70ec0-122">Application development</span></span></p></td>
<td><p><span data-ttu-id="70ec0-123">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="70ec0-123">ASP.NET</span></span></p>
<p><span data-ttu-id="70ec0-124">Windows Server 2012 也需要 ASP。 NET 4。5</span><span class="sxs-lookup"><span data-stu-id="70ec0-124">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-125">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="70ec0-125">Application development</span></span></p></td>
<td><p><span data-ttu-id="70ec0-126">.NET 擴充性</span><span class="sxs-lookup"><span data-stu-id="70ec0-126">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-127">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="70ec0-127">Application development</span></span></p></td>
<td><p><span data-ttu-id="70ec0-128">網際網路伺服器 API (ISAPI) 擴充</span><span class="sxs-lookup"><span data-stu-id="70ec0-128">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-129">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="70ec0-129">Application development</span></span></p></td>
<td><p><span data-ttu-id="70ec0-130">ISAPI 篩選</span><span class="sxs-lookup"><span data-stu-id="70ec0-130">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-131">健康情況及診斷</span><span class="sxs-lookup"><span data-stu-id="70ec0-131">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="70ec0-132">HTTP 記錄</span><span class="sxs-lookup"><span data-stu-id="70ec0-132">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-133">健康情況及診斷</span><span class="sxs-lookup"><span data-stu-id="70ec0-133">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="70ec0-134">記錄工具</span><span class="sxs-lookup"><span data-stu-id="70ec0-134">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-135">健康情況及診斷</span><span class="sxs-lookup"><span data-stu-id="70ec0-135">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="70ec0-136">跟蹤</span><span class="sxs-lookup"><span data-stu-id="70ec0-136">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-137">安全性</span><span class="sxs-lookup"><span data-stu-id="70ec0-137">Security</span></span></p></td>
<td><p><span data-ttu-id="70ec0-138">預設會安裝並啟用匿名驗證 () </span><span class="sxs-lookup"><span data-stu-id="70ec0-138">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-139">安全性</span><span class="sxs-lookup"><span data-stu-id="70ec0-139">Security</span></span></p></td>
<td><p><span data-ttu-id="70ec0-140">Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="70ec0-140">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-141">安全性</span><span class="sxs-lookup"><span data-stu-id="70ec0-141">Security</span></span></p></td>
<td><p><span data-ttu-id="70ec0-142">用戶端憑證對應驗證</span><span class="sxs-lookup"><span data-stu-id="70ec0-142">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-143">安全性</span><span class="sxs-lookup"><span data-stu-id="70ec0-143">Security</span></span></p></td>
<td><p><span data-ttu-id="70ec0-144">要求篩選</span><span class="sxs-lookup"><span data-stu-id="70ec0-144">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-145">效能</span><span class="sxs-lookup"><span data-stu-id="70ec0-145">Performance</span></span></p></td>
<td><p><span data-ttu-id="70ec0-146">靜態內容壓縮</span><span class="sxs-lookup"><span data-stu-id="70ec0-146">Static content compression</span></span></p>
<p><span data-ttu-id="70ec0-147">動態內容壓縮</span><span class="sxs-lookup"><span data-stu-id="70ec0-147">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-148">管理工具</span><span class="sxs-lookup"><span data-stu-id="70ec0-148">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="70ec0-149">IIS 管理主控台</span><span class="sxs-lookup"><span data-stu-id="70ec0-149">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-150">管理工具</span><span class="sxs-lookup"><span data-stu-id="70ec0-150">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="70ec0-151">IIS 管理指令碼及工具</span><span class="sxs-lookup"><span data-stu-id="70ec0-151">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="70ec0-152">在 Windows Server 2008 R2 SP1 x64 作業系統上，您可以使用 Windows PowerShell 2.0。</span><span class="sxs-lookup"><span data-stu-id="70ec0-152">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="70ec0-153">您必須先匯入 ServerManager 模組，然後安裝 IIS 7.5 角色和角色服務。</span><span class="sxs-lookup"><span data-stu-id="70ec0-153">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="70ec0-154">預設會以 IIS 伺服器角色安裝匿名驗證。</span><span class="sxs-lookup"><span data-stu-id="70ec0-154">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="70ec0-155">您可以在安裝 IIS 之後管理匿名驗證。</span><span class="sxs-lookup"><span data-stu-id="70ec0-155">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="70ec0-156">如需詳細資訊，請參閱的「啟用匿名驗證 (IIS 7) 」 <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A> 。</span><span class="sxs-lookup"><span data-stu-id="70ec0-156">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="70ec0-157">下表指出 Windows Server 2012 和 Windows Server 2012 R2 所需的 IIS 8.0 和 IIS 8.5 角色服務。</span><span class="sxs-lookup"><span data-stu-id="70ec0-157">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="70ec0-158">若為 Windows Server 2012 和 Windows Server 2012 R2，Add-WindowsFeature Cmdlet 已由 Install-WindowsFeature Cmdlet 所取代。</span><span class="sxs-lookup"><span data-stu-id="70ec0-158">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="70ec0-159">如需詳細資訊，請參閱 <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>。</span><span class="sxs-lookup"><span data-stu-id="70ec0-159">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="70ec0-160">IIS 8.0 和 IIS 8.5 角色服務</span><span class="sxs-lookup"><span data-stu-id="70ec0-160">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70ec0-161">角色標題</span><span class="sxs-lookup"><span data-stu-id="70ec0-161">Role Heading</span></span></th>
<th><span data-ttu-id="70ec0-162">角色服務</span><span class="sxs-lookup"><span data-stu-id="70ec0-162">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-163">網頁伺服器 (IIS) </span><span class="sxs-lookup"><span data-stu-id="70ec0-163">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="70ec0-164">網頁伺服器</span><span class="sxs-lookup"><span data-stu-id="70ec0-164">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-165">一般 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="70ec0-165">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="70ec0-166">預設文件</span><span class="sxs-lookup"><span data-stu-id="70ec0-166">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-167">一般 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="70ec0-167">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="70ec0-168">瀏覽目錄</span><span class="sxs-lookup"><span data-stu-id="70ec0-168">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-169">一般 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="70ec0-169">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="70ec0-170">HTTP 錯誤</span><span class="sxs-lookup"><span data-stu-id="70ec0-170">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-171">一般 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="70ec0-171">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="70ec0-172">靜態內容</span><span class="sxs-lookup"><span data-stu-id="70ec0-172">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-173">一般 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="70ec0-173">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="70ec0-174">HTTP 重新導向</span><span class="sxs-lookup"><span data-stu-id="70ec0-174">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-175">健康情況及診斷</span><span class="sxs-lookup"><span data-stu-id="70ec0-175">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="70ec0-176">HTTP 記錄</span><span class="sxs-lookup"><span data-stu-id="70ec0-176">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-177">健康情況及診斷</span><span class="sxs-lookup"><span data-stu-id="70ec0-177">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="70ec0-178">記錄工具</span><span class="sxs-lookup"><span data-stu-id="70ec0-178">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-179">健康情況及診斷</span><span class="sxs-lookup"><span data-stu-id="70ec0-179">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="70ec0-180">要求監視器</span><span class="sxs-lookup"><span data-stu-id="70ec0-180">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-181">健康情況及診斷</span><span class="sxs-lookup"><span data-stu-id="70ec0-181">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="70ec0-182">跟蹤</span><span class="sxs-lookup"><span data-stu-id="70ec0-182">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-183">安全性</span><span class="sxs-lookup"><span data-stu-id="70ec0-183">Security</span></span></p></td>
<td><p><span data-ttu-id="70ec0-184">要求篩選</span><span class="sxs-lookup"><span data-stu-id="70ec0-184">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-185">安全性</span><span class="sxs-lookup"><span data-stu-id="70ec0-185">Security</span></span></p></td>
<td><p><span data-ttu-id="70ec0-186">基本驗證</span><span class="sxs-lookup"><span data-stu-id="70ec0-186">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-187">安全性</span><span class="sxs-lookup"><span data-stu-id="70ec0-187">Security</span></span></p></td>
<td><p><span data-ttu-id="70ec0-188">用戶端憑證對應驗證</span><span class="sxs-lookup"><span data-stu-id="70ec0-188">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-189">安全性</span><span class="sxs-lookup"><span data-stu-id="70ec0-189">Security</span></span></p></td>
<td><p><span data-ttu-id="70ec0-190">Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="70ec0-190">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-191">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="70ec0-191">Application Development</span></span></p></td>
<td><p><span data-ttu-id="70ec0-192">.Net 擴充性3。5</span><span class="sxs-lookup"><span data-stu-id="70ec0-192">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-193">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="70ec0-193">Application Development</span></span></p></td>
<td><p><span data-ttu-id="70ec0-194">.Net 擴充性4。5</span><span class="sxs-lookup"><span data-stu-id="70ec0-194">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-195">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="70ec0-195">Application Development</span></span></p></td>
<td><p><span data-ttu-id="70ec0-196">ASP.Net 3。5</span><span class="sxs-lookup"><span data-stu-id="70ec0-196">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-197">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="70ec0-197">Application Development</span></span></p></td>
<td><p><span data-ttu-id="70ec0-198">ASP.Net 4。5</span><span class="sxs-lookup"><span data-stu-id="70ec0-198">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-199">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="70ec0-199">Application Development</span></span></p></td>
<td><p><span data-ttu-id="70ec0-200">ISAPI 擴充程式</span><span class="sxs-lookup"><span data-stu-id="70ec0-200">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-201">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="70ec0-201">Application Development</span></span></p></td>
<td><p><span data-ttu-id="70ec0-202">ISAPI 篩選器</span><span class="sxs-lookup"><span data-stu-id="70ec0-202">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-203">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="70ec0-203">Application Development</span></span></p></td>
<td><p><span data-ttu-id="70ec0-204">伺服器端包括</span><span class="sxs-lookup"><span data-stu-id="70ec0-204">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-205">管理工具</span><span class="sxs-lookup"><span data-stu-id="70ec0-205">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="70ec0-206">IIS 管理主控台</span><span class="sxs-lookup"><span data-stu-id="70ec0-206">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-207">管理工具</span><span class="sxs-lookup"><span data-stu-id="70ec0-207">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="70ec0-208">IIS 6 元資料庫相容性</span><span class="sxs-lookup"><span data-stu-id="70ec0-208">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-209">管理工具</span><span class="sxs-lookup"><span data-stu-id="70ec0-209">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="70ec0-210">IIS 管理指令碼及工具</span><span class="sxs-lookup"><span data-stu-id="70ec0-210">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-211">.Net 3.5 Framework 功能</span><span class="sxs-lookup"><span data-stu-id="70ec0-211">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="70ec0-212">.Net 3.5 Framework</span><span class="sxs-lookup"><span data-stu-id="70ec0-212">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-213">.Net 4.5 Framework 功能</span><span class="sxs-lookup"><span data-stu-id="70ec0-213">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="70ec0-214">.Net Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="70ec0-214">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-215">.Net 4.5 Framework 功能</span><span class="sxs-lookup"><span data-stu-id="70ec0-215">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="70ec0-216">ASP.Net 4。5</span><span class="sxs-lookup"><span data-stu-id="70ec0-216">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-217">.Net 4.5 Framework 功能</span><span class="sxs-lookup"><span data-stu-id="70ec0-217">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="70ec0-218">HTTP 啟用</span><span class="sxs-lookup"><span data-stu-id="70ec0-218">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-219">.Net 4.5 Framework 功能</span><span class="sxs-lookup"><span data-stu-id="70ec0-219">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="70ec0-220">TCP 埠共用</span><span class="sxs-lookup"><span data-stu-id="70ec0-220">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-221">背景智慧傳輸服務</span><span class="sxs-lookup"><span data-stu-id="70ec0-221">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="70ec0-222">IIS 伺服器擴充</span><span class="sxs-lookup"><span data-stu-id="70ec0-222">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-223">筆跡及手寫服務</span><span class="sxs-lookup"><span data-stu-id="70ec0-223">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="70ec0-224">筆跡及手寫服務</span><span class="sxs-lookup"><span data-stu-id="70ec0-224">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-225">媒體基礎</span><span class="sxs-lookup"><span data-stu-id="70ec0-225">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="70ec0-226">媒體基礎</span><span class="sxs-lookup"><span data-stu-id="70ec0-226">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-227">使用者介面和基礎結構</span><span class="sxs-lookup"><span data-stu-id="70ec0-227">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="70ec0-228">圖形管理工具和基礎結構</span><span class="sxs-lookup"><span data-stu-id="70ec0-228">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-229">使用者介面和基礎結構</span><span class="sxs-lookup"><span data-stu-id="70ec0-229">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="70ec0-230">桌面體驗</span><span class="sxs-lookup"><span data-stu-id="70ec0-230">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-231">使用者介面和基礎結構</span><span class="sxs-lookup"><span data-stu-id="70ec0-231">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="70ec0-232">伺服器圖形命令介面</span><span class="sxs-lookup"><span data-stu-id="70ec0-232">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-233">Windows Identity Foundation 3。5</span><span class="sxs-lookup"><span data-stu-id="70ec0-233">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="70ec0-234">Windows Identity Foundation 3。5</span><span class="sxs-lookup"><span data-stu-id="70ec0-234">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70ec0-235">Windows 進程啟用服務</span><span class="sxs-lookup"><span data-stu-id="70ec0-235">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="70ec0-236">進程模型</span><span class="sxs-lookup"><span data-stu-id="70ec0-236">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70ec0-237">Windows 進程啟用服務</span><span class="sxs-lookup"><span data-stu-id="70ec0-237">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="70ec0-238">設定 APIs</span><span class="sxs-lookup"><span data-stu-id="70ec0-238">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="70ec0-239">在 Windows Server 2012 和 Windows Server 2012 R2 中，您可以使用 Windows PowerShell 3.0 來安裝 IIS 需求。</span><span class="sxs-lookup"><span data-stu-id="70ec0-239">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="70ec0-240">使用 Windows PowerShell 3.0 中的 ServerManager 模組，輸入：</span><span class="sxs-lookup"><span data-stu-id="70ec0-240">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="70ec0-241">Windows Server 2012 的新增功能是定義可在何處找到 Windows Server 2012 來源媒體的–來源參數。</span><span class="sxs-lookup"><span data-stu-id="70ec0-241">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="70ec0-242">媒體可以定義為 DVD 磁片磁碟機 (例如，D:\Sources\Sxs) 或網路共用（媒體檔案已複製） (例如， \\ fileserver\windows2012\sources\Sxs) 。</span><span class="sxs-lookup"><span data-stu-id="70ec0-242">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="70ec0-243">另請參閱</span><span class="sxs-lookup"><span data-stu-id="70ec0-243">See Also</span></span>


[<span data-ttu-id="70ec0-244">Lync Server 2013 中前端集區與 Standard Edition server 的 IIS 需求</span><span class="sxs-lookup"><span data-stu-id="70ec0-244">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

