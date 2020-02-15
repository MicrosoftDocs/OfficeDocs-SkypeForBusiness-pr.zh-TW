---
title: 前端集區及 Standard Edition 伺服器的 IIS 需求
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
ms.openlocfilehash: bc92cc4c27f7af395a8e41bec26679a27010562d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="2494b-102">前端集區和 Standard Edition server 在 Lync Server 2013 中的 IIS 需求</span><span class="sxs-lookup"><span data-stu-id="2494b-102">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2494b-103">_**主題上次修改日期：** 2012年-06-19_</span><span class="sxs-lookup"><span data-stu-id="2494b-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="2494b-104">Standard Edition 伺服器和前端伺服器和 Director，Lync Server 2013 安裝程式會建立虛擬目錄中網際網路資訊服務 (IIS) 基於下列目的：</span><span class="sxs-lookup"><span data-stu-id="2494b-104">For Standard Edition servers and Front End Servers, and Directors, the Lync Server 2013 installer creates virtual directories in Internet Information Services (IIS) for the following purposes:</span></span>

  - <span data-ttu-id="2494b-105">若要讓使用者能夠從通訊錄服務下載檔案</span><span class="sxs-lookup"><span data-stu-id="2494b-105">To enable users to download files from the Address Book Service</span></span>

  - <span data-ttu-id="2494b-106">若要讓用戶端取得更新</span><span class="sxs-lookup"><span data-stu-id="2494b-106">To enable clients to obtain updates</span></span>

  - <span data-ttu-id="2494b-107">若要啟用會議</span><span class="sxs-lookup"><span data-stu-id="2494b-107">To enable conferencing</span></span>

  - <span data-ttu-id="2494b-108">若要讓使用者能夠下載會議內容</span><span class="sxs-lookup"><span data-stu-id="2494b-108">To enable users to download meeting content</span></span>

  - <span data-ttu-id="2494b-109">若要讓使用者能夠擴充通訊群組</span><span class="sxs-lookup"><span data-stu-id="2494b-109">To enable users to expand distribution groups</span></span>

  - <span data-ttu-id="2494b-110">若要啟用電話會議</span><span class="sxs-lookup"><span data-stu-id="2494b-110">To enable phone conferencing</span></span>

  - <span data-ttu-id="2494b-111">若要啟用回應群組功能</span><span class="sxs-lookup"><span data-stu-id="2494b-111">To enable response group features</span></span>

<span data-ttu-id="2494b-112">此外，Lync Server 2010 的累計更新： 11 月 2011年安裝程式會建立虛擬目錄在 IIS 中用於下列用途：</span><span class="sxs-lookup"><span data-stu-id="2494b-112">In addition, the cumulative update for Lync Server 2010: November 2011 installer creates virtual directories in IIS for the following purposes:</span></span>

  - <span data-ttu-id="2494b-113">在前端伺服器或 Standard Edition 伺服器，以支援行動裝置上的行動功能，例如立即訊息 (IM) 和目前狀態</span><span class="sxs-lookup"><span data-stu-id="2494b-113">On Front End Servers or Standard Edition servers to support mobility functionality, such as instant messaging (IM) and presence, on mobile devices</span></span>

  - <span data-ttu-id="2494b-114">在前端伺服器或 Standard Edition 伺服器和 Director 上，讓行動裝置能夠自動探索行動性資源</span><span class="sxs-lookup"><span data-stu-id="2494b-114">On Front End Servers or Standard Edition servers and on Directors to enable mobile devices to automatically discover mobility resources</span></span>



> [!NOTE]
> <span data-ttu-id="2494b-115">如果您正在部署行動性，建議您使用 IIS 7.5。</span><span class="sxs-lookup"><span data-stu-id="2494b-115">If you are deploying mobility, we recommend that you use IIS 7.5.</span></span> <span data-ttu-id="2494b-116">Lync Server Mobility Service 安裝程式會設定某些 ASP.NET 旗標，以改善效能。</span><span class="sxs-lookup"><span data-stu-id="2494b-116">The Lync Server Mobility Service installer sets some ASP.NET flags to improve performance.</span></span> <span data-ttu-id="2494b-117">依預設，IIS 7.5 會安裝在 Windows Server 2008 R2 上，而且 Mobility Service 安裝程式會自動變更 ASP.NET 設定。</span><span class="sxs-lookup"><span data-stu-id="2494b-117">IIS 7.5 is installed by default on Windows Server 2008 R2, and the Mobility Service installer automatically changes the ASP.NET settings.</span></span> <span data-ttu-id="2494b-118">如果您在 Windows Server 2008 上使用 IIS 7.0，則需要手動變更這些設定。</span><span class="sxs-lookup"><span data-stu-id="2494b-118">If you use IIS 7.0 on Windows Server 2008, you need to manually change these settings.</span></span>



<span data-ttu-id="2494b-119">Lync 伺服器上需要安裝下列 IIS 模組：</span><span class="sxs-lookup"><span data-stu-id="2494b-119">Lync Server requires the following IIS modules to be installed:</span></span>


> [!IMPORTANT]
> <span data-ttu-id="2494b-120">如果貴組織需要在非系統磁碟機的磁碟機上尋找 IIS 和所有 Web 服務，您可以變更設定] 對話方塊中的 Lync Server 檔案的安裝位置路徑。</span><span class="sxs-lookup"><span data-stu-id="2494b-120">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="2494b-121">如果您將安裝檔案安裝到此路徑，包括 OCSCore.msi，Lync Server 檔案的其餘部分將會部署至這個磁碟機。</span><span class="sxs-lookup"><span data-stu-id="2494b-121">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server files will be deployed to this drive as well.</span></span> <span data-ttu-id="2494b-122">如需如何重新放置部署 Windows Server 管理員安裝 IIS 時 INETPUB 的詳細資訊，請參閱<A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>。</span><span class="sxs-lookup"><span data-stu-id="2494b-122">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>


  - <span data-ttu-id="2494b-123">靜態內容</span><span class="sxs-lookup"><span data-stu-id="2494b-123">Static Content</span></span>

  - <span data-ttu-id="2494b-124">預設文件</span><span class="sxs-lookup"><span data-stu-id="2494b-124">Default Document</span></span>

  - <span data-ttu-id="2494b-125">HTTP 錯誤</span><span class="sxs-lookup"><span data-stu-id="2494b-125">HTTP Errors</span></span>

  - <span data-ttu-id="2494b-126">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2494b-126">ASP.NET</span></span>

  - <span data-ttu-id="2494b-127">.NET 擴充性</span><span class="sxs-lookup"><span data-stu-id="2494b-127">.NET Extensibility</span></span>

  - <span data-ttu-id="2494b-128">網際網路伺服器 API (ISAPI) 延伸模組</span><span class="sxs-lookup"><span data-stu-id="2494b-128">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="2494b-129">ISAPI 篩選</span><span class="sxs-lookup"><span data-stu-id="2494b-129">ISAPI Filters</span></span>

  - <span data-ttu-id="2494b-130">HTTP 記錄</span><span class="sxs-lookup"><span data-stu-id="2494b-130">HTTP Logging</span></span>

  - <span data-ttu-id="2494b-131">記錄工具</span><span class="sxs-lookup"><span data-stu-id="2494b-131">Logging Tools</span></span>

  - <span data-ttu-id="2494b-132">追蹤</span><span class="sxs-lookup"><span data-stu-id="2494b-132">Tracing</span></span>

  - <span data-ttu-id="2494b-133">Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="2494b-133">Windows Authentication</span></span>

  - <span data-ttu-id="2494b-134">要求篩選</span><span class="sxs-lookup"><span data-stu-id="2494b-134">Request Filtering</span></span>

  - <span data-ttu-id="2494b-135">靜態內容壓縮</span><span class="sxs-lookup"><span data-stu-id="2494b-135">Static Content Compression</span></span>

  - <span data-ttu-id="2494b-136">動態內容壓縮</span><span class="sxs-lookup"><span data-stu-id="2494b-136">Dynamic Content Compression</span></span>

  - <span data-ttu-id="2494b-137">IIS 管理主控台</span><span class="sxs-lookup"><span data-stu-id="2494b-137">IIS Management Console</span></span>

  - <span data-ttu-id="2494b-138">IIS 管理指令碼與工具</span><span class="sxs-lookup"><span data-stu-id="2494b-138">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="2494b-139">匿名驗證 （預設安裝安裝 IIS 時）</span><span class="sxs-lookup"><span data-stu-id="2494b-139">Anonymous Authentication (installed by default when IIS is installed)</span></span>

  - <span data-ttu-id="2494b-140">用戶端憑證對應驗證</span><span class="sxs-lookup"><span data-stu-id="2494b-140">Client Certificate Mapping Authentication</span></span>

<span data-ttu-id="2494b-141">下表列出內部存取與它們所參考的檔案系統資源的虛擬目錄的 Uri。</span><span class="sxs-lookup"><span data-stu-id="2494b-141">The following table lists the URIs for the virtual directories for internal access and the file system resources to which they refer.</span></span>

### <a name="virtual-directories-for-internal-access"></a><span data-ttu-id="2494b-142">供內部存取的虛擬目錄</span><span class="sxs-lookup"><span data-stu-id="2494b-142">Virtual Directories for Internal Access</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2494b-143">功能</span><span class="sxs-lookup"><span data-stu-id="2494b-143">Feature</span></span></th>
<th><span data-ttu-id="2494b-144">虛擬目錄 URI</span><span class="sxs-lookup"><span data-stu-id="2494b-144">Virtual directory URI</span></span></th>
<th><span data-ttu-id="2494b-145">參照到</span><span class="sxs-lookup"><span data-stu-id="2494b-145">Refers to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2494b-146">Address Book Server</span><span class="sxs-lookup"><span data-stu-id="2494b-146">Address Book Server</span></span></p></td>
<td><p><span data-ttu-id="2494b-147">https://&lt;內部 FQDN&gt;/ABS/int/Handler</span><span class="sxs-lookup"><span data-stu-id="2494b-147">https://&lt;Internal FQDN&gt;/ABS/int/Handler</span></span></p></td>
<td><p><span data-ttu-id="2494b-148">位置的 Address Book Server 下載檔案，供內部使用者。</span><span class="sxs-lookup"><span data-stu-id="2494b-148">Location of Address Book Server download files for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2494b-149">自動探索服務</span><span class="sxs-lookup"><span data-stu-id="2494b-149">Autodiscover Service</span></span></p></td>
<td><p><span data-ttu-id="2494b-150">https://&lt;內部 FQDN&gt;/Autodiscover</span><span class="sxs-lookup"><span data-stu-id="2494b-150">https://&lt;Internal FQDN&gt;/Autodiscover</span></span></p></td>
<td><p><span data-ttu-id="2494b-151">尋找內部行動裝置使用者的行動性資源 Lync Server 自動探索服務的位置。</span><span class="sxs-lookup"><span data-stu-id="2494b-151">Location of the Lync Server Autodiscover Service that locates mobility resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2494b-152">用戶端更新</span><span class="sxs-lookup"><span data-stu-id="2494b-152">Client updates</span></span></p></td>
<td><p><span data-ttu-id="2494b-153">http://&lt;內部 FQDN&gt;/AutoUpdate/Int</span><span class="sxs-lookup"><span data-stu-id="2494b-153">http://&lt;Internal FQDN&gt;/AutoUpdate/Int</span></span></p></td>
<td><p><span data-ttu-id="2494b-154">內部電腦為基礎的用戶端更新檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="2494b-154">Location of update files for internal computer-based clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2494b-155">Conf</span><span class="sxs-lookup"><span data-stu-id="2494b-155">Conf</span></span></p></td>
<td><p><span data-ttu-id="2494b-156">http://&lt;內部 FQDN&gt;/Conf/Int</span><span class="sxs-lookup"><span data-stu-id="2494b-156">http://&lt;Internal FQDN&gt;/Conf/Int</span></span></p></td>
<td><p><span data-ttu-id="2494b-157">供內部使用者的會議資源的位置。</span><span class="sxs-lookup"><span data-stu-id="2494b-157">Location of conferencing resources for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2494b-158">裝置更新</span><span class="sxs-lookup"><span data-stu-id="2494b-158">Device updates</span></span></p></td>
<td><p><span data-ttu-id="2494b-159">http://&lt;內部 FQDN&gt;/DeviceUpdateFiles_Int</span><span class="sxs-lookup"><span data-stu-id="2494b-159">http://&lt;Internal FQDN&gt;/DeviceUpdateFiles_Int</span></span></p></td>
<td><p><span data-ttu-id="2494b-160">供內部 UC 裝置的整合的通訊 (UC) 裝置更新檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="2494b-160">Location of unified communications (UC) device update files for internal UC devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2494b-161">會議</span><span class="sxs-lookup"><span data-stu-id="2494b-161">Meeting</span></span></p></td>
<td><p><span data-ttu-id="2494b-162">http://&lt;內部 FQDN&gt;/etc/place/null</span><span class="sxs-lookup"><span data-stu-id="2494b-162">http://&lt;Internal FQDN&gt;/etc/place/null</span></span></p></td>
<td><p><span data-ttu-id="2494b-163">內部使用者的會議內容位置。</span><span class="sxs-lookup"><span data-stu-id="2494b-163">Location of meeting content for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2494b-164">Mobility Service</span><span class="sxs-lookup"><span data-stu-id="2494b-164">Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="2494b-165">https://&lt;內部 FQDN&gt;/Mcx</span><span class="sxs-lookup"><span data-stu-id="2494b-165">https://&lt;Internal FQDN&gt;/Mcx</span></span></p></td>
<td><p><span data-ttu-id="2494b-166">內部行動裝置使用者的 Mobility Service 資源的位置。</span><span class="sxs-lookup"><span data-stu-id="2494b-166">Location of Mobility Service resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2494b-167">群組擴充和通訊錄 Web 查詢服務</span><span class="sxs-lookup"><span data-stu-id="2494b-167">Group Expansion and Address Book Web Query service</span></span></p></td>
<td><p><span data-ttu-id="2494b-168">http://&lt;內部 FQDN&gt;/GroupExpansion/int/service.asmx</span><span class="sxs-lookup"><span data-stu-id="2494b-168">http://&lt;Internal FQDN&gt;/GroupExpansion/int/service.asmx</span></span></p></td>
<td><p><span data-ttu-id="2494b-169">可讓內部使用者的群組擴充的 Web 服務的位置。</span><span class="sxs-lookup"><span data-stu-id="2494b-169">Location of the Web service that enables group expansion for internal users.</span></span> <span data-ttu-id="2494b-170">此外，全域通訊清單資訊提供給內部 Lync Mobile Microsoft Lync 2010 Mobile 用戶端通訊錄 Web 查詢服務位置。</span><span class="sxs-lookup"><span data-stu-id="2494b-170">Also, the location of the Address Book Web Query service that provides global address list information to internal Lync Mobile Microsoft Lync 2010 Mobile clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2494b-171">電話會議</span><span class="sxs-lookup"><span data-stu-id="2494b-171">Phone Conferencing</span></span></p></td>
<td><p><span data-ttu-id="2494b-172">http://&lt;內部 FQDN&gt;/PhoneConferencing/Int</span><span class="sxs-lookup"><span data-stu-id="2494b-172">http://&lt;Internal FQDN&gt;/PhoneConferencing/Int</span></span></p></td>
<td><p><span data-ttu-id="2494b-173">供內部使用者的電話會議資料的位置。</span><span class="sxs-lookup"><span data-stu-id="2494b-173">Location of phone conferencing data for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2494b-174">裝置更新</span><span class="sxs-lookup"><span data-stu-id="2494b-174">Device updates</span></span></p></td>
<td><p><span data-ttu-id="2494b-175">http://&lt;內部 FQDN&gt;/RequestHandler</span><span class="sxs-lookup"><span data-stu-id="2494b-175">http://&lt;Internal FQDN&gt;/RequestHandler</span></span></p></td>
<td><p><span data-ttu-id="2494b-176">裝置更新 Web 服務，可讓內部 UC 裝置上傳記錄並檢查更新的要求處理常式的位置。</span><span class="sxs-lookup"><span data-stu-id="2494b-176">Location of the Device Update Web service Request Handler that enables internal UC devices to upload logs and check for updates.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2494b-177">回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="2494b-177">Response Group application</span></span></p></td>
<td><p><span data-ttu-id="2494b-178">http://&lt;內部 FQDN&gt;/RgsConfig</span><span class="sxs-lookup"><span data-stu-id="2494b-178">http://&lt;Internal FQDN&gt;/RgsConfig</span></span></p>
<p><span data-ttu-id="2494b-179">http://&lt;內部 FQDN&gt;/RgsClients</span><span class="sxs-lookup"><span data-stu-id="2494b-179">http://&lt;Internal FQDN&gt;/RgsClients</span></span></p></td>
<td><p><span data-ttu-id="2494b-180">回應群組組態工具的位置。</span><span class="sxs-lookup"><span data-stu-id="2494b-180">Location of Response Group Configuration Tool.</span></span></p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> <span data-ttu-id="2494b-181">合併設定中的前端集區，您必須部署 IIS 才能您可以將伺服器新增至集區。</span><span class="sxs-lookup"><span data-stu-id="2494b-181">For Front End pools in a consolidated configuration, you must deploy IIS before you can add servers to the pool.</span></span>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全性" alt="security" /><span data-ttu-id="2494b-183">安全性附註：</span><span class="sxs-lookup"><span data-stu-id="2494b-183">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="2494b-184">您必須使用 IIS 系統管理嵌入式管理單元來指派 IIS web 元件伺服器所使用的憑證。</span><span class="sxs-lookup"><span data-stu-id="2494b-184">You must use the IIS administrative snap-in to assign the certificate used by the IIS web component server.</span></span></td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

