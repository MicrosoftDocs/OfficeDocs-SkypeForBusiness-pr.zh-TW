---
title: 前端集區與 Standard Edition server 的 IIS 需求
description: 前端集區和 Standard Edition server 的 IIS 需求。
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
ms.openlocfilehash: f56452c7e47352333ac3ac5a51d649b0828a0ff9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573339"
---
# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="0dc22-103">Lync Server 2013 中前端集區與 Standard Edition server 的 IIS 需求</span><span class="sxs-lookup"><span data-stu-id="0dc22-103">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0dc22-104">_**主題上次修改日期：** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="0dc22-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="0dc22-105">對於 Standard Edition server 和前端伺服器及 Director，Lync Server 2013 安裝程式會在網際網路資訊服務中建立虛擬目錄，以供下列目的 (IIS) ：</span><span class="sxs-lookup"><span data-stu-id="0dc22-105">For Standard Edition servers and Front End Servers, and Directors, the Lync Server 2013 installer creates virtual directories in Internet Information Services (IIS) for the following purposes:</span></span>

  - <span data-ttu-id="0dc22-106">讓使用者能夠從通訊錄服務下載檔案</span><span class="sxs-lookup"><span data-stu-id="0dc22-106">To enable users to download files from the Address Book Service</span></span>

  - <span data-ttu-id="0dc22-107">啟用用戶端以取得更新</span><span class="sxs-lookup"><span data-stu-id="0dc22-107">To enable clients to obtain updates</span></span>

  - <span data-ttu-id="0dc22-108">啟用會議</span><span class="sxs-lookup"><span data-stu-id="0dc22-108">To enable conferencing</span></span>

  - <span data-ttu-id="0dc22-109">讓使用者能夠下載會議內容</span><span class="sxs-lookup"><span data-stu-id="0dc22-109">To enable users to download meeting content</span></span>

  - <span data-ttu-id="0dc22-110">讓使用者能夠展開通訊群組</span><span class="sxs-lookup"><span data-stu-id="0dc22-110">To enable users to expand distribution groups</span></span>

  - <span data-ttu-id="0dc22-111">若要啟用電話會議</span><span class="sxs-lookup"><span data-stu-id="0dc22-111">To enable phone conferencing</span></span>

  - <span data-ttu-id="0dc22-112">啟用回應群組功能</span><span class="sxs-lookup"><span data-stu-id="0dc22-112">To enable response group features</span></span>

<span data-ttu-id="0dc22-113">此外，Lync Server 2010 的累計更新：11月2011安裝程式會在 IIS 中為下列目的建立虛擬目錄：</span><span class="sxs-lookup"><span data-stu-id="0dc22-113">In addition, the cumulative update for Lync Server 2010: November 2011 installer creates virtual directories in IIS for the following purposes:</span></span>

  - <span data-ttu-id="0dc22-114">在前端伺服器或 Standard Edition server 上，以支援行動裝置上的行動功能，例如立即訊息 (IM) 和目前狀態</span><span class="sxs-lookup"><span data-stu-id="0dc22-114">On Front End Servers or Standard Edition servers to support mobility functionality, such as instant messaging (IM) and presence, on mobile devices</span></span>

  - <span data-ttu-id="0dc22-115">在前端伺服器或 Standard Edition server 及 Director 上，讓行動裝置能夠自動探索行動性資源</span><span class="sxs-lookup"><span data-stu-id="0dc22-115">On Front End Servers or Standard Edition servers and on Directors to enable mobile devices to automatically discover mobility resources</span></span>



> [!NOTE]
> <span data-ttu-id="0dc22-116">若要部署行動性，建議您使用 IIS 7.5。</span><span class="sxs-lookup"><span data-stu-id="0dc22-116">If you are deploying mobility, we recommend that you use IIS 7.5.</span></span> <span data-ttu-id="0dc22-117">Lync Server 行動服務安裝程式會設定部分 ASP.NET 旗標，以提升效能。</span><span class="sxs-lookup"><span data-stu-id="0dc22-117">The Lync Server Mobility Service installer sets some ASP.NET flags to improve performance.</span></span> <span data-ttu-id="0dc22-118">依預設，IIS 7.5 會安裝在 Windows Server 2008 R2 上，而且 Mobility Service 安裝程式會自動變更 ASP.NET 設定。</span><span class="sxs-lookup"><span data-stu-id="0dc22-118">IIS 7.5 is installed by default on Windows Server 2008 R2, and the Mobility Service installer automatically changes the ASP.NET settings.</span></span> <span data-ttu-id="0dc22-119">如果您在 Windows Server 2008 上使用 IIS 7.0，則需要手動變更這些設定。</span><span class="sxs-lookup"><span data-stu-id="0dc22-119">If you use IIS 7.0 on Windows Server 2008, you need to manually change these settings.</span></span>



<span data-ttu-id="0dc22-120">Lync Server 需要安裝下列 IIS 模組：</span><span class="sxs-lookup"><span data-stu-id="0dc22-120">Lync Server requires the following IIS modules to be installed:</span></span>


> [!IMPORTANT]
> <span data-ttu-id="0dc22-121">如果您的組織需要在系統磁片磁碟機以外的磁片磁碟機上找到 [IIS] 和 [所有 Web 服務]，您可以在 [安裝程式] 對話方塊中變更 Lync Server 檔案的安裝位置路徑。</span><span class="sxs-lookup"><span data-stu-id="0dc22-121">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="0dc22-122">若將安裝檔案安裝至此路徑（包括 OCSCore.msi），則其他的 Lync Server 檔案也會同時部署至此磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="0dc22-122">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server files will be deployed to this drive as well.</span></span> <span data-ttu-id="0dc22-123">如需如何重新置放 Windows Server Manager 在安裝 IIS 時所部署之 INETPUB 的詳細資訊，請參閱 <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> 。</span><span class="sxs-lookup"><span data-stu-id="0dc22-123">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>


  - <span data-ttu-id="0dc22-124">靜態內容</span><span class="sxs-lookup"><span data-stu-id="0dc22-124">Static Content</span></span>

  - <span data-ttu-id="0dc22-125">預設文件</span><span class="sxs-lookup"><span data-stu-id="0dc22-125">Default Document</span></span>

  - <span data-ttu-id="0dc22-126">HTTP 錯誤</span><span class="sxs-lookup"><span data-stu-id="0dc22-126">HTTP Errors</span></span>

  - <span data-ttu-id="0dc22-127">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0dc22-127">ASP.NET</span></span>

  - <span data-ttu-id="0dc22-128">.NET 擴充性</span><span class="sxs-lookup"><span data-stu-id="0dc22-128">.NET Extensibility</span></span>

  - <span data-ttu-id="0dc22-129">網際網路伺服器 API (ISAPI) 擴充</span><span class="sxs-lookup"><span data-stu-id="0dc22-129">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="0dc22-130">ISAPI 篩選</span><span class="sxs-lookup"><span data-stu-id="0dc22-130">ISAPI Filters</span></span>

  - <span data-ttu-id="0dc22-131">HTTP 記錄</span><span class="sxs-lookup"><span data-stu-id="0dc22-131">HTTP Logging</span></span>

  - <span data-ttu-id="0dc22-132">記錄工具</span><span class="sxs-lookup"><span data-stu-id="0dc22-132">Logging Tools</span></span>

  - <span data-ttu-id="0dc22-133">跟蹤</span><span class="sxs-lookup"><span data-stu-id="0dc22-133">Tracing</span></span>

  - <span data-ttu-id="0dc22-134">Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="0dc22-134">Windows Authentication</span></span>

  - <span data-ttu-id="0dc22-135">要求篩選</span><span class="sxs-lookup"><span data-stu-id="0dc22-135">Request Filtering</span></span>

  - <span data-ttu-id="0dc22-136">靜態內容壓縮</span><span class="sxs-lookup"><span data-stu-id="0dc22-136">Static Content Compression</span></span>

  - <span data-ttu-id="0dc22-137">動態內容壓縮</span><span class="sxs-lookup"><span data-stu-id="0dc22-137">Dynamic Content Compression</span></span>

  - <span data-ttu-id="0dc22-138">IIS 管理主控台</span><span class="sxs-lookup"><span data-stu-id="0dc22-138">IIS Management Console</span></span>

  - <span data-ttu-id="0dc22-139">IIS 管理指令碼與工具</span><span class="sxs-lookup"><span data-stu-id="0dc22-139">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="0dc22-140">安裝 IIS 時，預設會安裝匿名驗證 () </span><span class="sxs-lookup"><span data-stu-id="0dc22-140">Anonymous Authentication (installed by default when IIS is installed)</span></span>

  - <span data-ttu-id="0dc22-141">用戶端憑證對應驗證</span><span class="sxs-lookup"><span data-stu-id="0dc22-141">Client Certificate Mapping Authentication</span></span>

<span data-ttu-id="0dc22-142">下表列出內部存取虛擬目錄的 URIs，以及其所參照的檔案系統資源。</span><span class="sxs-lookup"><span data-stu-id="0dc22-142">The following table lists the URIs for the virtual directories for internal access and the file system resources to which they refer.</span></span>

### <a name="virtual-directories-for-internal-access"></a><span data-ttu-id="0dc22-143">內部存取的虛擬目錄</span><span class="sxs-lookup"><span data-stu-id="0dc22-143">Virtual Directories for Internal Access</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0dc22-144">功能</span><span class="sxs-lookup"><span data-stu-id="0dc22-144">Feature</span></span></th>
<th><span data-ttu-id="0dc22-145">虛擬目錄 URI</span><span class="sxs-lookup"><span data-stu-id="0dc22-145">Virtual directory URI</span></span></th>
<th><span data-ttu-id="0dc22-146">參照到</span><span class="sxs-lookup"><span data-stu-id="0dc22-146">Refers to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0dc22-147">Address Book Server</span><span class="sxs-lookup"><span data-stu-id="0dc22-147">Address Book Server</span></span></p></td>
<td><p><span data-ttu-id="0dc22-148">HTTPs:// &lt; 內部 FQDN &gt; /ABS/int/Handler</span><span class="sxs-lookup"><span data-stu-id="0dc22-148">https://&lt;Internal FQDN&gt;/ABS/int/Handler</span></span></p></td>
<td><p><span data-ttu-id="0dc22-149">內部使用者之通訊錄服務器下載檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="0dc22-149">Location of Address Book Server download files for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0dc22-150">自動探索服務</span><span class="sxs-lookup"><span data-stu-id="0dc22-150">Autodiscover Service</span></span></p></td>
<td><p><span data-ttu-id="0dc22-151">HTTPs:// &lt; 內部 FQDN &gt; /Autodiscover</span><span class="sxs-lookup"><span data-stu-id="0dc22-151">https://&lt;Internal FQDN&gt;/Autodiscover</span></span></p></td>
<td><p><span data-ttu-id="0dc22-152">Lync Server 自動探索服務的位置，可為內部行動裝置使用者找到行動資源。</span><span class="sxs-lookup"><span data-stu-id="0dc22-152">Location of the Lync Server Autodiscover Service that locates mobility resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0dc22-153">用戶端更新</span><span class="sxs-lookup"><span data-stu-id="0dc22-153">Client updates</span></span></p></td>
<td><p><span data-ttu-id="0dc22-154">HTTP:// &lt; 內部 FQDN &gt; /AutoUpdate/Int</span><span class="sxs-lookup"><span data-stu-id="0dc22-154">http://&lt;Internal FQDN&gt;/AutoUpdate/Int</span></span></p></td>
<td><p><span data-ttu-id="0dc22-155">內部電腦型用戶端的更新檔案位置。</span><span class="sxs-lookup"><span data-stu-id="0dc22-155">Location of update files for internal computer-based clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0dc22-156">會議</span><span class="sxs-lookup"><span data-stu-id="0dc22-156">Conf</span></span></p></td>
<td><p><span data-ttu-id="0dc22-157">HTTP:// &lt; 內部 FQDN &gt; /Conf/Int</span><span class="sxs-lookup"><span data-stu-id="0dc22-157">http://&lt;Internal FQDN&gt;/Conf/Int</span></span></p></td>
<td><p><span data-ttu-id="0dc22-158">內部使用者的會議資源位置。</span><span class="sxs-lookup"><span data-stu-id="0dc22-158">Location of conferencing resources for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0dc22-159">裝置更新</span><span class="sxs-lookup"><span data-stu-id="0dc22-159">Device updates</span></span></p></td>
<td><p><span data-ttu-id="0dc22-160">HTTP:// &lt; 內部 FQDN &gt; /DeviceUpdateFiles_Int</span><span class="sxs-lookup"><span data-stu-id="0dc22-160">http://&lt;Internal FQDN&gt;/DeviceUpdateFiles_Int</span></span></p></td>
<td><p><span data-ttu-id="0dc22-161">整合通訊 (UC) 裝置更新檔案的內部 UC 裝置的位置。</span><span class="sxs-lookup"><span data-stu-id="0dc22-161">Location of unified communications (UC) device update files for internal UC devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0dc22-162">會議</span><span class="sxs-lookup"><span data-stu-id="0dc22-162">Meeting</span></span></p></td>
<td><p><span data-ttu-id="0dc22-163">HTTP:// &lt; 內部 FQDN &gt; /etc/place/null</span><span class="sxs-lookup"><span data-stu-id="0dc22-163">http://&lt;Internal FQDN&gt;/etc/place/null</span></span></p></td>
<td><p><span data-ttu-id="0dc22-164">內部使用者之會議內容的位置。</span><span class="sxs-lookup"><span data-stu-id="0dc22-164">Location of meeting content for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0dc22-165">行動性服務</span><span class="sxs-lookup"><span data-stu-id="0dc22-165">Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="0dc22-166">HTTPs:// &lt; 內部 FQDN &gt; /Mcx</span><span class="sxs-lookup"><span data-stu-id="0dc22-166">https://&lt;Internal FQDN&gt;/Mcx</span></span></p></td>
<td><p><span data-ttu-id="0dc22-167">內部行動裝置使用者的行動服務資源位置。</span><span class="sxs-lookup"><span data-stu-id="0dc22-167">Location of Mobility Service resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0dc22-168">群組擴充和通訊錄 Web 查詢服務</span><span class="sxs-lookup"><span data-stu-id="0dc22-168">Group Expansion and Address Book Web Query service</span></span></p></td>
<td><p><span data-ttu-id="0dc22-169">HTTP:// &lt; 內部 FQDN &gt; /GroupExpansion/int/service.asmx</span><span class="sxs-lookup"><span data-stu-id="0dc22-169">http://&lt;Internal FQDN&gt;/GroupExpansion/int/service.asmx</span></span></p></td>
<td><p><span data-ttu-id="0dc22-170">Web 服務的位置，可對內部使用者啟用群組擴充。</span><span class="sxs-lookup"><span data-stu-id="0dc22-170">Location of the Web service that enables group expansion for internal users.</span></span> <span data-ttu-id="0dc22-171">此外，也就是通訊錄 Web 查詢服務的位置，可提供全域通訊清單資訊給內部 Lync Mobile Microsoft Lync 2010 行動用戶端。</span><span class="sxs-lookup"><span data-stu-id="0dc22-171">Also, the location of the Address Book Web Query service that provides global address list information to internal Lync Mobile Microsoft Lync 2010 Mobile clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0dc22-172">電話會議</span><span class="sxs-lookup"><span data-stu-id="0dc22-172">Phone Conferencing</span></span></p></td>
<td><p><span data-ttu-id="0dc22-173">HTTP:// &lt; 內部 FQDN &gt; /PhoneConferencing/Int</span><span class="sxs-lookup"><span data-stu-id="0dc22-173">http://&lt;Internal FQDN&gt;/PhoneConferencing/Int</span></span></p></td>
<td><p><span data-ttu-id="0dc22-174">內部使用者之電話會議資料的位置。</span><span class="sxs-lookup"><span data-stu-id="0dc22-174">Location of phone conferencing data for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0dc22-175">裝置更新</span><span class="sxs-lookup"><span data-stu-id="0dc22-175">Device updates</span></span></p></td>
<td><p><span data-ttu-id="0dc22-176">HTTP:// &lt; 內部 FQDN &gt; /RequestHandler</span><span class="sxs-lookup"><span data-stu-id="0dc22-176">http://&lt;Internal FQDN&gt;/RequestHandler</span></span></p></td>
<td><p><span data-ttu-id="0dc22-177">裝置更新 Web 服務要求處理常式的位置，可讓內部 UC 裝置上傳記錄檔並檢查更新。</span><span class="sxs-lookup"><span data-stu-id="0dc22-177">Location of the Device Update Web service Request Handler that enables internal UC devices to upload logs and check for updates.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0dc22-178">回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="0dc22-178">Response Group application</span></span></p></td>
<td><p><span data-ttu-id="0dc22-179">HTTP:// &lt; 內部 FQDN &gt; /RgsConfig</span><span class="sxs-lookup"><span data-stu-id="0dc22-179">http://&lt;Internal FQDN&gt;/RgsConfig</span></span></p>
<p><span data-ttu-id="0dc22-180">HTTP:// &lt; 內部 FQDN &gt; /RgsClients</span><span class="sxs-lookup"><span data-stu-id="0dc22-180">http://&lt;Internal FQDN&gt;/RgsClients</span></span></p></td>
<td><p><span data-ttu-id="0dc22-181">回應群組設定工具的位置。</span><span class="sxs-lookup"><span data-stu-id="0dc22-181">Location of Response Group Configuration Tool.</span></span></p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> <span data-ttu-id="0dc22-182">對於合併設定中的前端集區，您必須先部署 IIS，才能將伺服器新增至集區。</span><span class="sxs-lookup"><span data-stu-id="0dc22-182">For Front End pools in a consolidated configuration, you must deploy IIS before you can add servers to the pool.</span></span>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全" alt="security" /><span data-ttu-id="0dc22-184">安全性附注：</span><span class="sxs-lookup"><span data-stu-id="0dc22-184">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0dc22-185">您必須使用 IIS 系統管理嵌入式管理單元來指派 IIS web 元件伺服器所使用的憑證。</span><span class="sxs-lookup"><span data-stu-id="0dc22-185">You must use the IIS administrative snap-in to assign the certificate used by the IIS web component server.</span></span></td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

