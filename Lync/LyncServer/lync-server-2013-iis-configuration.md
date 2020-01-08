---
title: Lync Server 2013：IIS 組態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de2205ad049beb05f30dd58795257b62eca68d46
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="f5ec6-102">Lync Server 2013 中的 IIS 組態</span><span class="sxs-lookup"><span data-stu-id="f5ec6-102">IIS configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5ec6-103">_**主題上次修改日期：** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="f5ec6-103">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="f5ec6-104">若要成功完成此程式，您應該以本機管理員和網域使用者的身分登入伺服器。</span><span class="sxs-lookup"><span data-stu-id="f5ec6-104">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="f5ec6-105">在將 Lync Server 2013、標準版或第一個前端伺服器的前端伺服器設定並安裝到池中之前，您必須安裝並設定網際網路資訊服務（IIS）的伺服器角色和 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="f5ec6-105">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="f5ec6-106">如果您的組織要求您在系統磁片磁碟機以外的磁片磁碟機上找到 IIS 和所有 Web 服務，您可以在初次安裝 Lync Server 2013 時，在 [設定] 對話方塊中變更 Lync Server 2013 檔案的安裝位置路徑[管理工具]。</span><span class="sxs-lookup"><span data-stu-id="f5ec6-106">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="f5ec6-107">安裝 IIS 之前，請先安裝 [管理工具]。</span><span class="sxs-lookup"><span data-stu-id="f5ec6-107">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="f5ec6-108">如果您將安裝檔案安裝到此路徑（包括 OCSCore），其餘的 Lync Server 2013 檔案也會部署到這個磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="f5ec6-108">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="f5ec6-109">如需 dtails，請參閱<A href="lync-server-2013-install-lync-server-administrative-tools.md">安裝 Lync Server 2013 系統管理工具</A>。</span><span class="sxs-lookup"><span data-stu-id="f5ec6-109">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="f5ec6-110">如需有關如何在安裝 IIS 時重新置放由 Windows Server Manager 部署的 INETPUB 的<A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="f5ec6-110">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="f5ec6-111">下表指出必要的 IIS 7.5 角色服務。</span><span class="sxs-lookup"><span data-stu-id="f5ec6-111">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="f5ec6-112">IIS 7.5 角色服務</span><span class="sxs-lookup"><span data-stu-id="f5ec6-112">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5ec6-113">角色標題</span><span class="sxs-lookup"><span data-stu-id="f5ec6-113">Role Heading</span></span></th>
<th><span data-ttu-id="f5ec6-114">角色服務</span><span class="sxs-lookup"><span data-stu-id="f5ec6-114">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-115">已安裝常見的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="f5ec6-115">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-116">靜態內容</span><span class="sxs-lookup"><span data-stu-id="f5ec6-116">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-117">已安裝常見的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="f5ec6-117">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-118">預設檔</span><span class="sxs-lookup"><span data-stu-id="f5ec6-118">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-119">已安裝常見的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="f5ec6-119">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-120">HTTP 錯誤</span><span class="sxs-lookup"><span data-stu-id="f5ec6-120">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-121">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="f5ec6-121">Application development</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-122">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f5ec6-122">ASP.NET</span></span></p>
<p><span data-ttu-id="f5ec6-123">Windows Server 2012 也需要 ASP. NET 4。5</span><span class="sxs-lookup"><span data-stu-id="f5ec6-123">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-124">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="f5ec6-124">Application development</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-125">.NET 擴充性</span><span class="sxs-lookup"><span data-stu-id="f5ec6-125">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-126">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="f5ec6-126">Application development</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-127">網際網路伺服器 API （ISAPI）延伸</span><span class="sxs-lookup"><span data-stu-id="f5ec6-127">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-128">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="f5ec6-128">Application development</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-129">ISAPI 篩選</span><span class="sxs-lookup"><span data-stu-id="f5ec6-129">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-130">健康與診斷</span><span class="sxs-lookup"><span data-stu-id="f5ec6-130">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-131">HTTP 記錄</span><span class="sxs-lookup"><span data-stu-id="f5ec6-131">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-132">健康與診斷</span><span class="sxs-lookup"><span data-stu-id="f5ec6-132">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-133">記錄工具</span><span class="sxs-lookup"><span data-stu-id="f5ec6-133">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-134">健康與診斷</span><span class="sxs-lookup"><span data-stu-id="f5ec6-134">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-135">診斷</span><span class="sxs-lookup"><span data-stu-id="f5ec6-135">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-136">安全性</span><span class="sxs-lookup"><span data-stu-id="f5ec6-136">Security</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-137">匿名驗證（預設為已安裝和啟用）</span><span class="sxs-lookup"><span data-stu-id="f5ec6-137">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-138">安全性</span><span class="sxs-lookup"><span data-stu-id="f5ec6-138">Security</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-139">Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="f5ec6-139">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-140">安全性</span><span class="sxs-lookup"><span data-stu-id="f5ec6-140">Security</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-141">用戶端憑證對應驗證</span><span class="sxs-lookup"><span data-stu-id="f5ec6-141">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-142">安全性</span><span class="sxs-lookup"><span data-stu-id="f5ec6-142">Security</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-143">要求篩選</span><span class="sxs-lookup"><span data-stu-id="f5ec6-143">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-144">提高</span><span class="sxs-lookup"><span data-stu-id="f5ec6-144">Performance</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-145">靜態內容壓縮</span><span class="sxs-lookup"><span data-stu-id="f5ec6-145">Static content compression</span></span></p>
<p><span data-ttu-id="f5ec6-146">動態內容壓縮</span><span class="sxs-lookup"><span data-stu-id="f5ec6-146">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-147">管理工具</span><span class="sxs-lookup"><span data-stu-id="f5ec6-147">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-148">IIS 管理主控台</span><span class="sxs-lookup"><span data-stu-id="f5ec6-148">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-149">管理工具</span><span class="sxs-lookup"><span data-stu-id="f5ec6-149">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-150">IIS 管理腳本與工具</span><span class="sxs-lookup"><span data-stu-id="f5ec6-150">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f5ec6-151">在 Windows Server 2008 R2 SP1 x64 作業系統上，您可以使用 Windows PowerShell 2.0。</span><span class="sxs-lookup"><span data-stu-id="f5ec6-151">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="f5ec6-152">您必須先匯入 ServerManager 模組，然後再安裝 IIS 7.5 角色和角色服務。</span><span class="sxs-lookup"><span data-stu-id="f5ec6-152">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```
    Import-Module ServerManager
   ```

   ```
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="f5ec6-153">預設會安裝匿名驗證與 IIS 伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="f5ec6-153">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="f5ec6-154">您可以在安裝 IIS 之後管理匿名驗證。</span><span class="sxs-lookup"><span data-stu-id="f5ec6-154">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="f5ec6-155">如需詳細資訊，請參閱「啟用匿名驗證（IIS 7 <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>）」。</span><span class="sxs-lookup"><span data-stu-id="f5ec6-155">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="f5ec6-156">下表顯示 Windows Server 2012 和 Windows Server 2012 R2 所需的 IIS 8.0 和 IIS 8.5 角色服務。</span><span class="sxs-lookup"><span data-stu-id="f5ec6-156">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="f5ec6-157">針對 Windows Server 2012 和 Windows Server 2012 R2，Add-windowsfeature Cmdlet 已由 Install Cmdlet 取代。</span><span class="sxs-lookup"><span data-stu-id="f5ec6-157">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="f5ec6-158">如需詳細資訊，請參閱<A href="http://go.microsoft.com/fwlink/p/?linkid=392274">安裝程式</A>。</span><span class="sxs-lookup"><span data-stu-id="f5ec6-158">For details, see <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="f5ec6-159">IIS 8.0 和 IIS 8.5 角色服務</span><span class="sxs-lookup"><span data-stu-id="f5ec6-159">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5ec6-160">角色標題</span><span class="sxs-lookup"><span data-stu-id="f5ec6-160">Role Heading</span></span></th>
<th><span data-ttu-id="f5ec6-161">角色服務</span><span class="sxs-lookup"><span data-stu-id="f5ec6-161">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-162">Web 服務器（IIS）</span><span class="sxs-lookup"><span data-stu-id="f5ec6-162">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-163">網頁伺服器</span><span class="sxs-lookup"><span data-stu-id="f5ec6-163">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-164">常見的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="f5ec6-164">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-165">預設檔</span><span class="sxs-lookup"><span data-stu-id="f5ec6-165">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-166">常見的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="f5ec6-166">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-167">瀏覽目錄</span><span class="sxs-lookup"><span data-stu-id="f5ec6-167">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-168">常見的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="f5ec6-168">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-169">HTTP 錯誤</span><span class="sxs-lookup"><span data-stu-id="f5ec6-169">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-170">常見的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="f5ec6-170">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-171">靜態內容</span><span class="sxs-lookup"><span data-stu-id="f5ec6-171">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-172">常見的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="f5ec6-172">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-173">HTTP 重新導向</span><span class="sxs-lookup"><span data-stu-id="f5ec6-173">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-174">健康與診斷</span><span class="sxs-lookup"><span data-stu-id="f5ec6-174">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-175">HTTP 記錄</span><span class="sxs-lookup"><span data-stu-id="f5ec6-175">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-176">健康與診斷</span><span class="sxs-lookup"><span data-stu-id="f5ec6-176">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-177">記錄工具</span><span class="sxs-lookup"><span data-stu-id="f5ec6-177">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-178">健康與診斷</span><span class="sxs-lookup"><span data-stu-id="f5ec6-178">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-179">要求監視器</span><span class="sxs-lookup"><span data-stu-id="f5ec6-179">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-180">健康與診斷</span><span class="sxs-lookup"><span data-stu-id="f5ec6-180">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-181">診斷</span><span class="sxs-lookup"><span data-stu-id="f5ec6-181">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-182">安全性</span><span class="sxs-lookup"><span data-stu-id="f5ec6-182">Security</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-183">要求篩選</span><span class="sxs-lookup"><span data-stu-id="f5ec6-183">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-184">安全性</span><span class="sxs-lookup"><span data-stu-id="f5ec6-184">Security</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-185">基本驗證</span><span class="sxs-lookup"><span data-stu-id="f5ec6-185">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-186">安全性</span><span class="sxs-lookup"><span data-stu-id="f5ec6-186">Security</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-187">用戶端憑證對應驗證</span><span class="sxs-lookup"><span data-stu-id="f5ec6-187">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-188">安全性</span><span class="sxs-lookup"><span data-stu-id="f5ec6-188">Security</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-189">Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="f5ec6-189">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-190">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="f5ec6-190">Application Development</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-191">.Net 擴充性3。5</span><span class="sxs-lookup"><span data-stu-id="f5ec6-191">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-192">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="f5ec6-192">Application Development</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-193">.Net 擴充性4。5</span><span class="sxs-lookup"><span data-stu-id="f5ec6-193">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-194">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="f5ec6-194">Application Development</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-195">ASP.Net 3。5</span><span class="sxs-lookup"><span data-stu-id="f5ec6-195">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-196">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="f5ec6-196">Application Development</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-197">ASP.Net 4。5</span><span class="sxs-lookup"><span data-stu-id="f5ec6-197">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-198">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="f5ec6-198">Application Development</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-199">ISAPI 延伸</span><span class="sxs-lookup"><span data-stu-id="f5ec6-199">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-200">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="f5ec6-200">Application Development</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-201">ISAPI 篩選</span><span class="sxs-lookup"><span data-stu-id="f5ec6-201">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-202">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="f5ec6-202">Application Development</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-203">伺服器端包含</span><span class="sxs-lookup"><span data-stu-id="f5ec6-203">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-204">管理工具</span><span class="sxs-lookup"><span data-stu-id="f5ec6-204">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-205">IIS 管理主控台</span><span class="sxs-lookup"><span data-stu-id="f5ec6-205">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-206">管理工具</span><span class="sxs-lookup"><span data-stu-id="f5ec6-206">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-207">IIS 6 元資料庫相容性</span><span class="sxs-lookup"><span data-stu-id="f5ec6-207">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-208">管理工具</span><span class="sxs-lookup"><span data-stu-id="f5ec6-208">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-209">IIS 管理腳本與工具</span><span class="sxs-lookup"><span data-stu-id="f5ec6-209">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-210">.Net 3.5 Framework 功能</span><span class="sxs-lookup"><span data-stu-id="f5ec6-210">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-211">.Net 3.5 Framework</span><span class="sxs-lookup"><span data-stu-id="f5ec6-211">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-212">.Net 4.5 Framework 功能</span><span class="sxs-lookup"><span data-stu-id="f5ec6-212">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-213">.Net Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="f5ec6-213">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-214">.Net 4.5 Framework 功能</span><span class="sxs-lookup"><span data-stu-id="f5ec6-214">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-215">ASP.Net 4。5</span><span class="sxs-lookup"><span data-stu-id="f5ec6-215">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-216">.Net 4.5 Framework 功能</span><span class="sxs-lookup"><span data-stu-id="f5ec6-216">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-217">HTTP 啟用</span><span class="sxs-lookup"><span data-stu-id="f5ec6-217">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-218">.Net 4.5 Framework 功能</span><span class="sxs-lookup"><span data-stu-id="f5ec6-218">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-219">TCP 埠共用</span><span class="sxs-lookup"><span data-stu-id="f5ec6-219">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-220">背景智慧傳送服務</span><span class="sxs-lookup"><span data-stu-id="f5ec6-220">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-221">IIS 伺服器延伸</span><span class="sxs-lookup"><span data-stu-id="f5ec6-221">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-222">筆跡與手寫服務</span><span class="sxs-lookup"><span data-stu-id="f5ec6-222">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-223">筆跡與手寫服務</span><span class="sxs-lookup"><span data-stu-id="f5ec6-223">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-224">媒體基礎</span><span class="sxs-lookup"><span data-stu-id="f5ec6-224">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-225">媒體基礎</span><span class="sxs-lookup"><span data-stu-id="f5ec6-225">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-226">使用者介面與基礎結構</span><span class="sxs-lookup"><span data-stu-id="f5ec6-226">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-227">圖形管理工具與基礎結構</span><span class="sxs-lookup"><span data-stu-id="f5ec6-227">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-228">使用者介面與基礎結構</span><span class="sxs-lookup"><span data-stu-id="f5ec6-228">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-229">桌面體驗</span><span class="sxs-lookup"><span data-stu-id="f5ec6-229">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-230">使用者介面與基礎結構</span><span class="sxs-lookup"><span data-stu-id="f5ec6-230">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-231">伺服器圖形命令介面</span><span class="sxs-lookup"><span data-stu-id="f5ec6-231">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-232">Windows 身分識別 Foundation 3。5</span><span class="sxs-lookup"><span data-stu-id="f5ec6-232">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-233">Windows 身分識別 Foundation 3。5</span><span class="sxs-lookup"><span data-stu-id="f5ec6-233">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5ec6-234">Windows Process Activation Service</span><span class="sxs-lookup"><span data-stu-id="f5ec6-234">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-235">處理模型</span><span class="sxs-lookup"><span data-stu-id="f5ec6-235">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5ec6-236">Windows Process Activation Service</span><span class="sxs-lookup"><span data-stu-id="f5ec6-236">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="f5ec6-237">配置 Api</span><span class="sxs-lookup"><span data-stu-id="f5ec6-237">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f5ec6-238">在 Windows Server 2012 和 Windows Server 2012 R2 中，您可以使用 Windows PowerShell 3.0 來安裝 IIS 需求。</span><span class="sxs-lookup"><span data-stu-id="f5ec6-238">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="f5ec6-239">使用 Windows PowerShell 3.0 中的 ServerManager 模組，請輸入：</span><span class="sxs-lookup"><span data-stu-id="f5ec6-239">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```
    Import-Module ServerManager
   ```

   ```
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="f5ec6-240">Windows Server 2012 的新功能是 [來源] 參數，可定義可找到 Windows Server 2012 來源媒體的位置。</span><span class="sxs-lookup"><span data-stu-id="f5ec6-240">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="f5ec6-241">媒體可以定義為 DVD 光碟機（例如，D:\Sources\Sxs），或複製媒體檔案的網路共用（例如， \\fileserver\windows2012\sources\Sxs）。</span><span class="sxs-lookup"><span data-stu-id="f5ec6-241">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f5ec6-242">請參閱</span><span class="sxs-lookup"><span data-stu-id="f5ec6-242">See Also</span></span>


[<span data-ttu-id="f5ec6-243">Lync Server 2013 中的前端集區與 Standard Edition Server 的 IIS 需求</span><span class="sxs-lookup"><span data-stu-id="f5ec6-243">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

