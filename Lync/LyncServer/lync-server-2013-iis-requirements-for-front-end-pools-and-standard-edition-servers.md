---
title: 前端集區與 Standard Edition server 的 IIS 需求
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
ms.openlocfilehash: 33c3db01f772f43ea8507cee5c309b6705c8a69d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528140"
---
# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="69886-102">Lync Server 2013 中前端集區與 Standard Edition server 的 IIS 需求</span><span class="sxs-lookup"><span data-stu-id="69886-102">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69886-103">_**主題上次修改日期：** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="69886-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="69886-104">對於 Standard Edition server 和前端伺服器及 Director，Lync Server 2013 安裝程式會在網際網路資訊服務中建立虛擬目錄，以供下列目的 (IIS) ：</span><span class="sxs-lookup"><span data-stu-id="69886-104">For Standard Edition servers and Front End Servers, and Directors, the Lync Server 2013 installer creates virtual directories in Internet Information Services (IIS) for the following purposes:</span></span>

  - <span data-ttu-id="69886-105">讓使用者能夠從通訊錄服務下載檔案</span><span class="sxs-lookup"><span data-stu-id="69886-105">To enable users to download files from the Address Book Service</span></span>

  - <span data-ttu-id="69886-106">啟用用戶端以取得更新</span><span class="sxs-lookup"><span data-stu-id="69886-106">To enable clients to obtain updates</span></span>

  - <span data-ttu-id="69886-107">啟用會議</span><span class="sxs-lookup"><span data-stu-id="69886-107">To enable conferencing</span></span>

  - <span data-ttu-id="69886-108">讓使用者能夠下載會議內容</span><span class="sxs-lookup"><span data-stu-id="69886-108">To enable users to download meeting content</span></span>

  - <span data-ttu-id="69886-109">讓使用者能夠展開通訊群組</span><span class="sxs-lookup"><span data-stu-id="69886-109">To enable users to expand distribution groups</span></span>

  - <span data-ttu-id="69886-110">若要啟用電話會議</span><span class="sxs-lookup"><span data-stu-id="69886-110">To enable phone conferencing</span></span>

  - <span data-ttu-id="69886-111">啟用回應群組功能</span><span class="sxs-lookup"><span data-stu-id="69886-111">To enable response group features</span></span>

<span data-ttu-id="69886-112">此外，Lync Server 2010 的累計更新：11月2011安裝程式會在 IIS 中為下列目的建立虛擬目錄：</span><span class="sxs-lookup"><span data-stu-id="69886-112">In addition, the cumulative update for Lync Server 2010: November 2011 installer creates virtual directories in IIS for the following purposes:</span></span>

  - <span data-ttu-id="69886-113">在前端伺服器或 Standard Edition server 上，以支援行動裝置上的行動功能，例如立即訊息 (IM) 和目前狀態</span><span class="sxs-lookup"><span data-stu-id="69886-113">On Front End Servers or Standard Edition servers to support mobility functionality, such as instant messaging (IM) and presence, on mobile devices</span></span>

  - <span data-ttu-id="69886-114">在前端伺服器或 Standard Edition server 及 Director 上，讓行動裝置能夠自動探索行動性資源</span><span class="sxs-lookup"><span data-stu-id="69886-114">On Front End Servers or Standard Edition servers and on Directors to enable mobile devices to automatically discover mobility resources</span></span>



> [!NOTE]
> <span data-ttu-id="69886-115">若要部署行動性，建議您使用 IIS 7.5。</span><span class="sxs-lookup"><span data-stu-id="69886-115">If you are deploying mobility, we recommend that you use IIS 7.5.</span></span> <span data-ttu-id="69886-116">Lync Server 行動服務安裝程式會設定部分 ASP.NET 旗標，以提升效能。</span><span class="sxs-lookup"><span data-stu-id="69886-116">The Lync Server Mobility Service installer sets some ASP.NET flags to improve performance.</span></span> <span data-ttu-id="69886-117">依預設，IIS 7.5 會安裝在 Windows Server 2008 R2 上，而且 Mobility Service 安裝程式會自動變更 ASP.NET 設定。</span><span class="sxs-lookup"><span data-stu-id="69886-117">IIS 7.5 is installed by default on Windows Server 2008 R2, and the Mobility Service installer automatically changes the ASP.NET settings.</span></span> <span data-ttu-id="69886-118">如果您在 Windows Server 2008 上使用 IIS 7.0，則需要手動變更這些設定。</span><span class="sxs-lookup"><span data-stu-id="69886-118">If you use IIS 7.0 on Windows Server 2008, you need to manually change these settings.</span></span>



<span data-ttu-id="69886-119">Lync Server 需要安裝下列 IIS 模組：</span><span class="sxs-lookup"><span data-stu-id="69886-119">Lync Server requires the following IIS modules to be installed:</span></span>


> [!IMPORTANT]
> <span data-ttu-id="69886-120">如果您的組織需要在系統磁片磁碟機以外的磁片磁碟機上找到 [IIS] 和 [所有 Web 服務]，您可以在 [安裝程式] 對話方塊中變更 Lync Server 檔案的安裝位置路徑。</span><span class="sxs-lookup"><span data-stu-id="69886-120">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="69886-121">若將安裝檔案安裝至此路徑（包括 OCSCore.msi），則其他的 Lync Server 檔案也會同時部署至此磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="69886-121">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server files will be deployed to this drive as well.</span></span> <span data-ttu-id="69886-122">如需如何重新置放 Windows Server Manager 在安裝 IIS 時所部署之 INETPUB 的詳細資訊，請參閱 <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> 。</span><span class="sxs-lookup"><span data-stu-id="69886-122">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>


  - <span data-ttu-id="69886-123">靜態內容</span><span class="sxs-lookup"><span data-stu-id="69886-123">Static Content</span></span>

  - <span data-ttu-id="69886-124">預設文件</span><span class="sxs-lookup"><span data-stu-id="69886-124">Default Document</span></span>

  - <span data-ttu-id="69886-125">HTTP 錯誤</span><span class="sxs-lookup"><span data-stu-id="69886-125">HTTP Errors</span></span>

  - <span data-ttu-id="69886-126">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="69886-126">ASP.NET</span></span>

  - <span data-ttu-id="69886-127">.NET 擴充性</span><span class="sxs-lookup"><span data-stu-id="69886-127">.NET Extensibility</span></span>

  - <span data-ttu-id="69886-128">網際網路伺服器 API (ISAPI) 擴充</span><span class="sxs-lookup"><span data-stu-id="69886-128">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="69886-129">ISAPI 篩選</span><span class="sxs-lookup"><span data-stu-id="69886-129">ISAPI Filters</span></span>

  - <span data-ttu-id="69886-130">HTTP 記錄</span><span class="sxs-lookup"><span data-stu-id="69886-130">HTTP Logging</span></span>

  - <span data-ttu-id="69886-131">記錄工具</span><span class="sxs-lookup"><span data-stu-id="69886-131">Logging Tools</span></span>

  - <span data-ttu-id="69886-132">跟蹤</span><span class="sxs-lookup"><span data-stu-id="69886-132">Tracing</span></span>

  - <span data-ttu-id="69886-133">Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="69886-133">Windows Authentication</span></span>

  - <span data-ttu-id="69886-134">要求篩選</span><span class="sxs-lookup"><span data-stu-id="69886-134">Request Filtering</span></span>

  - <span data-ttu-id="69886-135">靜態內容壓縮</span><span class="sxs-lookup"><span data-stu-id="69886-135">Static Content Compression</span></span>

  - <span data-ttu-id="69886-136">動態內容壓縮</span><span class="sxs-lookup"><span data-stu-id="69886-136">Dynamic Content Compression</span></span>

  - <span data-ttu-id="69886-137">IIS 管理主控台</span><span class="sxs-lookup"><span data-stu-id="69886-137">IIS Management Console</span></span>

  - <span data-ttu-id="69886-138">IIS 管理指令碼與工具</span><span class="sxs-lookup"><span data-stu-id="69886-138">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="69886-139">安裝 IIS 時，預設會安裝匿名驗證 () </span><span class="sxs-lookup"><span data-stu-id="69886-139">Anonymous Authentication (installed by default when IIS is installed)</span></span>

  - <span data-ttu-id="69886-140">用戶端憑證對應驗證</span><span class="sxs-lookup"><span data-stu-id="69886-140">Client Certificate Mapping Authentication</span></span>

<span data-ttu-id="69886-141">下表列出內部存取虛擬目錄的 URIs，以及其所參照的檔案系統資源。</span><span class="sxs-lookup"><span data-stu-id="69886-141">The following table lists the URIs for the virtual directories for internal access and the file system resources to which they refer.</span></span>

### <a name="virtual-directories-for-internal-access"></a><span data-ttu-id="69886-142">內部存取的虛擬目錄</span><span class="sxs-lookup"><span data-stu-id="69886-142">Virtual Directories for Internal Access</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69886-143">功能</span><span class="sxs-lookup"><span data-stu-id="69886-143">Feature</span></span></th>
<th><span data-ttu-id="69886-144">虛擬目錄 URI</span><span class="sxs-lookup"><span data-stu-id="69886-144">Virtual directory URI</span></span></th>
<th><span data-ttu-id="69886-145">參照到</span><span class="sxs-lookup"><span data-stu-id="69886-145">Refers to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69886-146">Address Book Server</span><span class="sxs-lookup"><span data-stu-id="69886-146">Address Book Server</span></span></p></td>
<td><p><span data-ttu-id="69886-147">HTTPs:// &lt; 內部 FQDN &gt; /ABS/int/Handler</span><span class="sxs-lookup"><span data-stu-id="69886-147">https://&lt;Internal FQDN&gt;/ABS/int/Handler</span></span></p></td>
<td><p><span data-ttu-id="69886-148">內部使用者之通訊錄服務器下載檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="69886-148">Location of Address Book Server download files for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69886-149">自動探索服務</span><span class="sxs-lookup"><span data-stu-id="69886-149">Autodiscover Service</span></span></p></td>
<td><p><span data-ttu-id="69886-150">HTTPs:// &lt; 內部 FQDN &gt; /Autodiscover</span><span class="sxs-lookup"><span data-stu-id="69886-150">https://&lt;Internal FQDN&gt;/Autodiscover</span></span></p></td>
<td><p><span data-ttu-id="69886-151">Lync Server 自動探索服務的位置，可為內部行動裝置使用者找到行動資源。</span><span class="sxs-lookup"><span data-stu-id="69886-151">Location of the Lync Server Autodiscover Service that locates mobility resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69886-152">用戶端更新</span><span class="sxs-lookup"><span data-stu-id="69886-152">Client updates</span></span></p></td>
<td><p><span data-ttu-id="69886-153">HTTP:// &lt; 內部 FQDN &gt; /AutoUpdate/Int</span><span class="sxs-lookup"><span data-stu-id="69886-153">http://&lt;Internal FQDN&gt;/AutoUpdate/Int</span></span></p></td>
<td><p><span data-ttu-id="69886-154">內部電腦型用戶端的更新檔案位置。</span><span class="sxs-lookup"><span data-stu-id="69886-154">Location of update files for internal computer-based clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69886-155">會議</span><span class="sxs-lookup"><span data-stu-id="69886-155">Conf</span></span></p></td>
<td><p><span data-ttu-id="69886-156">HTTP:// &lt; 內部 FQDN &gt; /Conf/Int</span><span class="sxs-lookup"><span data-stu-id="69886-156">http://&lt;Internal FQDN&gt;/Conf/Int</span></span></p></td>
<td><p><span data-ttu-id="69886-157">內部使用者的會議資源位置。</span><span class="sxs-lookup"><span data-stu-id="69886-157">Location of conferencing resources for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69886-158">裝置更新</span><span class="sxs-lookup"><span data-stu-id="69886-158">Device updates</span></span></p></td>
<td><p><span data-ttu-id="69886-159">HTTP:// &lt; 內部 FQDN &gt; /DeviceUpdateFiles_Int</span><span class="sxs-lookup"><span data-stu-id="69886-159">http://&lt;Internal FQDN&gt;/DeviceUpdateFiles_Int</span></span></p></td>
<td><p><span data-ttu-id="69886-160">整合通訊 (UC) 裝置更新檔案的內部 UC 裝置的位置。</span><span class="sxs-lookup"><span data-stu-id="69886-160">Location of unified communications (UC) device update files for internal UC devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69886-161">會議</span><span class="sxs-lookup"><span data-stu-id="69886-161">Meeting</span></span></p></td>
<td><p><span data-ttu-id="69886-162">HTTP:// &lt; 內部 FQDN &gt; /etc/place/null</span><span class="sxs-lookup"><span data-stu-id="69886-162">http://&lt;Internal FQDN&gt;/etc/place/null</span></span></p></td>
<td><p><span data-ttu-id="69886-163">內部使用者之會議內容的位置。</span><span class="sxs-lookup"><span data-stu-id="69886-163">Location of meeting content for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69886-164">行動性服務</span><span class="sxs-lookup"><span data-stu-id="69886-164">Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="69886-165">HTTPs:// &lt; 內部 FQDN &gt; /Mcx</span><span class="sxs-lookup"><span data-stu-id="69886-165">https://&lt;Internal FQDN&gt;/Mcx</span></span></p></td>
<td><p><span data-ttu-id="69886-166">內部行動裝置使用者的行動服務資源位置。</span><span class="sxs-lookup"><span data-stu-id="69886-166">Location of Mobility Service resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69886-167">群組擴充和通訊錄 Web 查詢服務</span><span class="sxs-lookup"><span data-stu-id="69886-167">Group Expansion and Address Book Web Query service</span></span></p></td>
<td><p><span data-ttu-id="69886-168">HTTP:// &lt; 內部 FQDN &gt; /GroupExpansion/int/service.asmx</span><span class="sxs-lookup"><span data-stu-id="69886-168">http://&lt;Internal FQDN&gt;/GroupExpansion/int/service.asmx</span></span></p></td>
<td><p><span data-ttu-id="69886-169">Web 服務的位置，可對內部使用者啟用群組擴充。</span><span class="sxs-lookup"><span data-stu-id="69886-169">Location of the Web service that enables group expansion for internal users.</span></span> <span data-ttu-id="69886-170">此外，也就是通訊錄 Web 查詢服務的位置，可提供全域通訊清單資訊給內部 Lync Mobile Microsoft Lync 2010 行動用戶端。</span><span class="sxs-lookup"><span data-stu-id="69886-170">Also, the location of the Address Book Web Query service that provides global address list information to internal Lync Mobile Microsoft Lync 2010 Mobile clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69886-171">電話會議</span><span class="sxs-lookup"><span data-stu-id="69886-171">Phone Conferencing</span></span></p></td>
<td><p><span data-ttu-id="69886-172">HTTP:// &lt; 內部 FQDN &gt; /PhoneConferencing/Int</span><span class="sxs-lookup"><span data-stu-id="69886-172">http://&lt;Internal FQDN&gt;/PhoneConferencing/Int</span></span></p></td>
<td><p><span data-ttu-id="69886-173">內部使用者之電話會議資料的位置。</span><span class="sxs-lookup"><span data-stu-id="69886-173">Location of phone conferencing data for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69886-174">裝置更新</span><span class="sxs-lookup"><span data-stu-id="69886-174">Device updates</span></span></p></td>
<td><p><span data-ttu-id="69886-175">HTTP:// &lt; 內部 FQDN &gt; /RequestHandler</span><span class="sxs-lookup"><span data-stu-id="69886-175">http://&lt;Internal FQDN&gt;/RequestHandler</span></span></p></td>
<td><p><span data-ttu-id="69886-176">裝置更新 Web 服務要求處理常式的位置，可讓內部 UC 裝置上傳記錄檔並檢查更新。</span><span class="sxs-lookup"><span data-stu-id="69886-176">Location of the Device Update Web service Request Handler that enables internal UC devices to upload logs and check for updates.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69886-177">回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="69886-177">Response Group application</span></span></p></td>
<td><p><span data-ttu-id="69886-178">HTTP:// &lt; 內部 FQDN &gt; /RgsConfig</span><span class="sxs-lookup"><span data-stu-id="69886-178">http://&lt;Internal FQDN&gt;/RgsConfig</span></span></p>
<p><span data-ttu-id="69886-179">HTTP:// &lt; 內部 FQDN &gt; /RgsClients</span><span class="sxs-lookup"><span data-stu-id="69886-179">http://&lt;Internal FQDN&gt;/RgsClients</span></span></p></td>
<td><p><span data-ttu-id="69886-180">回應群組設定工具的位置。</span><span class="sxs-lookup"><span data-stu-id="69886-180">Location of Response Group Configuration Tool.</span></span></p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> <span data-ttu-id="69886-181">對於合併設定中的前端集區，您必須先部署 IIS，才能將伺服器新增至集區。</span><span class="sxs-lookup"><span data-stu-id="69886-181">For Front End pools in a consolidated configuration, you must deploy IIS before you can add servers to the pool.</span></span>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全" alt="security" /><span data-ttu-id="69886-183">安全性附注：</span><span class="sxs-lookup"><span data-stu-id="69886-183">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="69886-184">您必須使用 IIS 系統管理嵌入式管理單元來指派 IIS web 元件伺服器所使用的憑證。</span><span class="sxs-lookup"><span data-stu-id="69886-184">You must use the IIS administrative snap-in to assign the certificate used by the IIS web component server.</span></span></td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

