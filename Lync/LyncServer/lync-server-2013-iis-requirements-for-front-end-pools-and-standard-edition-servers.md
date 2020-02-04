---
title: 前端集區與 Standard Edition Server 的 IIS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c00ffe97b77f20107fc3351a678c71e28bbc6675
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="d9a25-102">Lync Server 2013 中的前端集區與 Standard Edition Server 的 IIS 需求</span><span class="sxs-lookup"><span data-stu-id="d9a25-102">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9a25-103">_**主題上次修改日期：** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="d9a25-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="d9a25-104">針對標準版伺服器和前端伺服器以及控制器，Lync Server 2013 安裝程式會在網際網路資訊服務（IIS）中建立虛擬目錄，以進行下列用途：</span><span class="sxs-lookup"><span data-stu-id="d9a25-104">For Standard Edition servers and Front End Servers, and Directors, the Lync Server 2013 installer creates virtual directories in Internet Information Services (IIS) for the following purposes:</span></span>

  - <span data-ttu-id="d9a25-105">若要讓使用者能夠從通訊錄服務下載檔案</span><span class="sxs-lookup"><span data-stu-id="d9a25-105">To enable users to download files from the Address Book Service</span></span>

  - <span data-ttu-id="d9a25-106">啟用用戶端以取得更新</span><span class="sxs-lookup"><span data-stu-id="d9a25-106">To enable clients to obtain updates</span></span>

  - <span data-ttu-id="d9a25-107">若要啟用會議</span><span class="sxs-lookup"><span data-stu-id="d9a25-107">To enable conferencing</span></span>

  - <span data-ttu-id="d9a25-108">讓使用者能夠下載會議內容</span><span class="sxs-lookup"><span data-stu-id="d9a25-108">To enable users to download meeting content</span></span>

  - <span data-ttu-id="d9a25-109">若要讓使用者能夠展開通訊群組</span><span class="sxs-lookup"><span data-stu-id="d9a25-109">To enable users to expand distribution groups</span></span>

  - <span data-ttu-id="d9a25-110">若要啟用電話會議</span><span class="sxs-lookup"><span data-stu-id="d9a25-110">To enable phone conferencing</span></span>

  - <span data-ttu-id="d9a25-111">啟用回應群組功能</span><span class="sxs-lookup"><span data-stu-id="d9a25-111">To enable response group features</span></span>

<span data-ttu-id="d9a25-112">此外，Lync Server 2010 的累加更新：2011年11月安裝程式會在 IIS 中建立虛擬目錄，以進行下列用途：</span><span class="sxs-lookup"><span data-stu-id="d9a25-112">In addition, the cumulative update for Lync Server 2010: November 2011 installer creates virtual directories in IIS for the following purposes:</span></span>

  - <span data-ttu-id="d9a25-113">在前端伺服器或標準版伺服器上，支援行動裝置上的行動功能（例如立即訊息（IM）與目前狀態）</span><span class="sxs-lookup"><span data-stu-id="d9a25-113">On Front End Servers or Standard Edition servers to support mobility functionality, such as instant messaging (IM) and presence, on mobile devices</span></span>

  - <span data-ttu-id="d9a25-114">在前端伺服器或標準版伺服器以及控制器上，讓行動裝置能夠自動探索行動資源</span><span class="sxs-lookup"><span data-stu-id="d9a25-114">On Front End Servers or Standard Edition servers and on Directors to enable mobile devices to automatically discover mobility resources</span></span>



> [!NOTE]
> <span data-ttu-id="d9a25-115">如果您要部署行動性，建議您使用 IIS 7.5。</span><span class="sxs-lookup"><span data-stu-id="d9a25-115">If you are deploying mobility, we recommend that you use IIS 7.5.</span></span> <span data-ttu-id="d9a25-116">Lync Server 行動服務安裝程式會設定一些 ASP.NET 標誌來改善效能。</span><span class="sxs-lookup"><span data-stu-id="d9a25-116">The Lync Server Mobility Service installer sets some ASP.NET flags to improve performance.</span></span> <span data-ttu-id="d9a25-117">預設會在 Windows Server 2008 R2 上安裝 IIS 7.5，且行動服務安裝程式會自動變更 ASP.NET 設定。</span><span class="sxs-lookup"><span data-stu-id="d9a25-117">IIS 7.5 is installed by default on Windows Server 2008 R2, and the Mobility Service installer automatically changes the ASP.NET settings.</span></span> <span data-ttu-id="d9a25-118">如果您在 Windows Server 2008 上使用 IIS 7.0，您必須手動變更這些設定。</span><span class="sxs-lookup"><span data-stu-id="d9a25-118">If you use IIS 7.0 on Windows Server 2008, you need to manually change these settings.</span></span>



<span data-ttu-id="d9a25-119">Lync Server 需要安裝下列 IIS 模組：</span><span class="sxs-lookup"><span data-stu-id="d9a25-119">Lync Server requires the following IIS modules to be installed:</span></span>


> [!IMPORTANT]
> <span data-ttu-id="d9a25-120">如果您的組織要求您在系統磁片磁碟機以外的磁片磁碟機上找到 [IIS] 和 [所有 Web 服務]，您可以在 [設定] 對話方塊中變更 Lync Server 檔案的安裝位置路徑。</span><span class="sxs-lookup"><span data-stu-id="d9a25-120">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="d9a25-121">如果您將安裝檔案安裝到此路徑，包括 OCSCore，則其餘的 Lync Server 檔案也將會部署到此磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="d9a25-121">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server files will be deployed to this drive as well.</span></span> <span data-ttu-id="d9a25-122">如需有關如何在安裝 IIS 時重新置放由 Windows Server Manager 部署的 INETPUB 的<A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>詳細資訊，請參閱。</span><span class="sxs-lookup"><span data-stu-id="d9a25-122">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>


  - <span data-ttu-id="d9a25-123">靜態內容</span><span class="sxs-lookup"><span data-stu-id="d9a25-123">Static Content</span></span>

  - <span data-ttu-id="d9a25-124">預設檔</span><span class="sxs-lookup"><span data-stu-id="d9a25-124">Default Document</span></span>

  - <span data-ttu-id="d9a25-125">HTTP 錯誤</span><span class="sxs-lookup"><span data-stu-id="d9a25-125">HTTP Errors</span></span>

  - <span data-ttu-id="d9a25-126">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d9a25-126">ASP.NET</span></span>

  - <span data-ttu-id="d9a25-127">.NET 擴充性</span><span class="sxs-lookup"><span data-stu-id="d9a25-127">.NET Extensibility</span></span>

  - <span data-ttu-id="d9a25-128">網際網路伺服器 API （ISAPI）延伸</span><span class="sxs-lookup"><span data-stu-id="d9a25-128">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="d9a25-129">ISAPI 篩選</span><span class="sxs-lookup"><span data-stu-id="d9a25-129">ISAPI Filters</span></span>

  - <span data-ttu-id="d9a25-130">HTTP 記錄</span><span class="sxs-lookup"><span data-stu-id="d9a25-130">HTTP Logging</span></span>

  - <span data-ttu-id="d9a25-131">記錄工具</span><span class="sxs-lookup"><span data-stu-id="d9a25-131">Logging Tools</span></span>

  - <span data-ttu-id="d9a25-132">診斷</span><span class="sxs-lookup"><span data-stu-id="d9a25-132">Tracing</span></span>

  - <span data-ttu-id="d9a25-133">Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="d9a25-133">Windows Authentication</span></span>

  - <span data-ttu-id="d9a25-134">要求篩選</span><span class="sxs-lookup"><span data-stu-id="d9a25-134">Request Filtering</span></span>

  - <span data-ttu-id="d9a25-135">靜態內容壓縮</span><span class="sxs-lookup"><span data-stu-id="d9a25-135">Static Content Compression</span></span>

  - <span data-ttu-id="d9a25-136">動態內容壓縮</span><span class="sxs-lookup"><span data-stu-id="d9a25-136">Dynamic Content Compression</span></span>

  - <span data-ttu-id="d9a25-137">IIS 管理主控台</span><span class="sxs-lookup"><span data-stu-id="d9a25-137">IIS Management Console</span></span>

  - <span data-ttu-id="d9a25-138">IIS 管理腳本與工具</span><span class="sxs-lookup"><span data-stu-id="d9a25-138">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="d9a25-139">匿名驗證（在安裝 IIS 時預設為已安裝）</span><span class="sxs-lookup"><span data-stu-id="d9a25-139">Anonymous Authentication (installed by default when IIS is installed)</span></span>

  - <span data-ttu-id="d9a25-140">用戶端憑證對應驗證</span><span class="sxs-lookup"><span data-stu-id="d9a25-140">Client Certificate Mapping Authentication</span></span>

<span data-ttu-id="d9a25-141">下表列出內部存取虛擬目錄的 Uri，以及它們所參照的檔案系統資源。</span><span class="sxs-lookup"><span data-stu-id="d9a25-141">The following table lists the URIs for the virtual directories for internal access and the file system resources to which they refer.</span></span>

### <a name="virtual-directories-for-internal-access"></a><span data-ttu-id="d9a25-142">內部存取的虛擬目錄</span><span class="sxs-lookup"><span data-stu-id="d9a25-142">Virtual Directories for Internal Access</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9a25-143">功能</span><span class="sxs-lookup"><span data-stu-id="d9a25-143">Feature</span></span></th>
<th><span data-ttu-id="d9a25-144">虛擬目錄 URI</span><span class="sxs-lookup"><span data-stu-id="d9a25-144">Virtual directory URI</span></span></th>
<th><span data-ttu-id="d9a25-145">參照</span><span class="sxs-lookup"><span data-stu-id="d9a25-145">Refers to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9a25-146">通訊錄服務器</span><span class="sxs-lookup"><span data-stu-id="d9a25-146">Address Book Server</span></span></p></td>
<td><p><span data-ttu-id="d9a25-147">HTTPs://&lt;內部 FQDN&gt;/ABS/int/Handler</span><span class="sxs-lookup"><span data-stu-id="d9a25-147">https://&lt;Internal FQDN&gt;/ABS/int/Handler</span></span></p></td>
<td><p><span data-ttu-id="d9a25-148">內部使用者的通訊錄服務器下載檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="d9a25-148">Location of Address Book Server download files for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9a25-149">自動探索服務</span><span class="sxs-lookup"><span data-stu-id="d9a25-149">Autodiscover Service</span></span></p></td>
<td><p><span data-ttu-id="d9a25-150">HTTPs://&lt;內部 FQDN&gt;/Autodiscover</span><span class="sxs-lookup"><span data-stu-id="d9a25-150">https://&lt;Internal FQDN&gt;/Autodiscover</span></span></p></td>
<td><p><span data-ttu-id="d9a25-151">Lync Server 自動探索服務的位置，可為內部行動裝置使用者找到行動資源。</span><span class="sxs-lookup"><span data-stu-id="d9a25-151">Location of the Lync Server Autodiscover Service that locates mobility resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9a25-152">用戶端更新</span><span class="sxs-lookup"><span data-stu-id="d9a25-152">Client updates</span></span></p></td>
<td><p><span data-ttu-id="d9a25-153">HTTP://&lt;內部 FQDN&gt;/AutoUpdate/Int</span><span class="sxs-lookup"><span data-stu-id="d9a25-153">http://&lt;Internal FQDN&gt;/AutoUpdate/Int</span></span></p></td>
<td><p><span data-ttu-id="d9a25-154">內部電腦式用戶端的更新檔案位置。</span><span class="sxs-lookup"><span data-stu-id="d9a25-154">Location of update files for internal computer-based clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9a25-155">會議</span><span class="sxs-lookup"><span data-stu-id="d9a25-155">Conf</span></span></p></td>
<td><p><span data-ttu-id="d9a25-156">HTTP://&lt;內部 FQDN&gt;/Conf/Int</span><span class="sxs-lookup"><span data-stu-id="d9a25-156">http://&lt;Internal FQDN&gt;/Conf/Int</span></span></p></td>
<td><p><span data-ttu-id="d9a25-157">內部使用者的會議資源位置。</span><span class="sxs-lookup"><span data-stu-id="d9a25-157">Location of conferencing resources for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9a25-158">裝置更新</span><span class="sxs-lookup"><span data-stu-id="d9a25-158">Device updates</span></span></p></td>
<td><p><span data-ttu-id="d9a25-159">HTTP://&lt;內部 FQDN&gt;/DeviceUpdateFiles_Int</span><span class="sxs-lookup"><span data-stu-id="d9a25-159">http://&lt;Internal FQDN&gt;/DeviceUpdateFiles_Int</span></span></p></td>
<td><p><span data-ttu-id="d9a25-160">內部 UC 裝置的整合通訊（UC）裝置更新檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="d9a25-160">Location of unified communications (UC) device update files for internal UC devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9a25-161">要求</span><span class="sxs-lookup"><span data-stu-id="d9a25-161">Meeting</span></span></p></td>
<td><p><span data-ttu-id="d9a25-162">HTTP://&lt;內部 FQDN&gt;/etc/place/null</span><span class="sxs-lookup"><span data-stu-id="d9a25-162">http://&lt;Internal FQDN&gt;/etc/place/null</span></span></p></td>
<td><p><span data-ttu-id="d9a25-163">內部使用者的會議內容位置。</span><span class="sxs-lookup"><span data-stu-id="d9a25-163">Location of meeting content for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9a25-164">行動服務</span><span class="sxs-lookup"><span data-stu-id="d9a25-164">Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="d9a25-165">HTTPs://&lt;內部 FQDN&gt;/Mcx</span><span class="sxs-lookup"><span data-stu-id="d9a25-165">https://&lt;Internal FQDN&gt;/Mcx</span></span></p></td>
<td><p><span data-ttu-id="d9a25-166">內部行動裝置使用者的行動服務資源位置。</span><span class="sxs-lookup"><span data-stu-id="d9a25-166">Location of Mobility Service resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9a25-167">群組展開和通訊錄網頁查詢服務</span><span class="sxs-lookup"><span data-stu-id="d9a25-167">Group Expansion and Address Book Web Query service</span></span></p></td>
<td><p><span data-ttu-id="d9a25-168">HTTP://&lt;內部 FQDN&gt;/GroupExpansion/int/service.asmx</span><span class="sxs-lookup"><span data-stu-id="d9a25-168">http://&lt;Internal FQDN&gt;/GroupExpansion/int/service.asmx</span></span></p></td>
<td><p><span data-ttu-id="d9a25-169">針對內部使用者啟用群組延伸的 Web 服務的位置。</span><span class="sxs-lookup"><span data-stu-id="d9a25-169">Location of the Web service that enables group expansion for internal users.</span></span> <span data-ttu-id="d9a25-170">此外，提供全域通訊清單資訊給內部 Lync Mobile Microsoft Lync 2010 行動用戶端的通訊錄 Web 查詢服務的位置。</span><span class="sxs-lookup"><span data-stu-id="d9a25-170">Also, the location of the Address Book Web Query service that provides global address list information to internal Lync Mobile Microsoft Lync 2010 Mobile clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9a25-171">電話會議</span><span class="sxs-lookup"><span data-stu-id="d9a25-171">Phone Conferencing</span></span></p></td>
<td><p><span data-ttu-id="d9a25-172">HTTP://&lt;內部 FQDN&gt;/PhoneConferencing/Int</span><span class="sxs-lookup"><span data-stu-id="d9a25-172">http://&lt;Internal FQDN&gt;/PhoneConferencing/Int</span></span></p></td>
<td><p><span data-ttu-id="d9a25-173">內部使用者的電話會議資料位置。</span><span class="sxs-lookup"><span data-stu-id="d9a25-173">Location of phone conferencing data for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9a25-174">裝置更新</span><span class="sxs-lookup"><span data-stu-id="d9a25-174">Device updates</span></span></p></td>
<td><p><span data-ttu-id="d9a25-175">HTTP://&lt;內部 FQDN&gt;/RequestHandler</span><span class="sxs-lookup"><span data-stu-id="d9a25-175">http://&lt;Internal FQDN&gt;/RequestHandler</span></span></p></td>
<td><p><span data-ttu-id="d9a25-176">裝置更新 Web 服務要求處理常式的位置，可讓內部 UC 裝置上傳記錄並檢查更新。</span><span class="sxs-lookup"><span data-stu-id="d9a25-176">Location of the Device Update Web service Request Handler that enables internal UC devices to upload logs and check for updates.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9a25-177">回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="d9a25-177">Response Group application</span></span></p></td>
<td><p><span data-ttu-id="d9a25-178">HTTP://&lt;內部 FQDN&gt;/RgsConfig</span><span class="sxs-lookup"><span data-stu-id="d9a25-178">http://&lt;Internal FQDN&gt;/RgsConfig</span></span></p>
<p><span data-ttu-id="d9a25-179">HTTP://&lt;內部 FQDN&gt;/RgsClients</span><span class="sxs-lookup"><span data-stu-id="d9a25-179">http://&lt;Internal FQDN&gt;/RgsClients</span></span></p></td>
<td><p><span data-ttu-id="d9a25-180">[回應群組設定] 工具的位置。</span><span class="sxs-lookup"><span data-stu-id="d9a25-180">Location of Response Group Configuration Tool.</span></span></p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> <span data-ttu-id="d9a25-181">針對整合式設定中的前端池，您必須先部署 IIS，才能將伺服器新增至池中。</span><span class="sxs-lookup"><span data-stu-id="d9a25-181">For Front End pools in a consolidated configuration, you must deploy IIS before you can add servers to the pool.</span></span>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全性" alt="security" /><span data-ttu-id="d9a25-183">安全性注意事項：</span><span class="sxs-lookup"><span data-stu-id="d9a25-183">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d9a25-184">您必須使用 [IIS 管理] 管理單元來指派 IIS 網頁元件伺服器所使用的憑證。</span><span class="sxs-lookup"><span data-stu-id="d9a25-184">You must use the IIS administrative snap-in to assign the certificate used by the IIS web component server.</span></span></td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

