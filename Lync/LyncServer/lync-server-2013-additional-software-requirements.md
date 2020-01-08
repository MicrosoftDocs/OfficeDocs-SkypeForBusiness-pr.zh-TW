---
title: Lync Server 2013：其他軟體需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e21a375fecbd109e108806dc816a9fa3fce81a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a><span data-ttu-id="a4dc4-102">Lync Server 2013 的其他軟體需求</span><span class="sxs-lookup"><span data-stu-id="a4dc4-102">Additional software requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4dc4-103">_**主題上次修改日期：** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="a4dc4-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="a4dc4-104">除了伺服器平臺的硬體及作業系統需求之外，Lync Server 2013 還需要在您部署的伺服器上安裝其他軟體。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-104">In addition to the hardware and operating system requirements for server platforms, Lync Server 2013 requires the installation of additional software on the servers that you deploy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a4dc4-105">如需執行 Lync Server 之伺服器平臺需求的詳細資訊，請參閱 lync server <A href="lync-server-2013-server-hardware-platforms.md">2013 的伺服器硬體平臺</A>和 lync server 2013 中的 [伺服器<A href="lync-server-2013-server-and-tools-operating-system-support.md">與工具作業系統支援</A>]。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-105">For details about the platform requirements for servers running Lync Server, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A>.</span></span> <span data-ttu-id="a4dc4-106">如需用戶端電腦和裝置的系統需求的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013 中的用戶端和裝置規劃</A>。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-106">For details about system requirements for client computers and devices, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="a4dc4-107">如需管理工具的軟體需求的詳細資訊，請參閱<A href="lync-server-2013-administrative-tools-software-requirements.md">Lync Server 2013 中的系統管理工具軟體需求</A>。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-107">For details about software requirements for administrative tools, see <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative tools software requirements in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a><span data-ttu-id="a4dc4-108">所有內部伺服器角色所需的其他軟體</span><span class="sxs-lookup"><span data-stu-id="a4dc4-108">Additional Software Necessary for All Internal Server Roles</span></span>

<span data-ttu-id="a4dc4-109">本節列出所有內部伺服器角色所需的軟體，這些都是除 Edge 伺服器以外的所有 Lync Server 伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-109">This section lists software necessary on all internal server roles, which are all Lync Server server roles except for Edge Server.</span></span> <span data-ttu-id="a4dc4-110">Edge 伺服器與邊緣池的需求將在本主題的 [**其他適用于 Edge 伺服器的軟體**] 底下列出。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-110">The requirements for the Edge Servers and Edge pools are listed later in this topic under **Additional Software for Edge Servers**.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="a4dc4-111">Windows PowerShell 3。0</span><span class="sxs-lookup"><span data-stu-id="a4dc4-111">Windows PowerShell 3.0</span></span>

<span data-ttu-id="a4dc4-112">每個執行 Lync Server 2013 的伺服器都必須安裝正確的 Windows PowerShell 3.0 版本。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-112">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="a4dc4-113">如需詳細資訊，請參閱[安裝 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-113">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="a4dc4-114">Microsoft .NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="a4dc4-114">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="a4dc4-115">Lync Server 在所有內部伺服器角色以及任何您要執行 Lync Server 系統管理工具或 Microsoft Lync Server 2013 的電腦上，都需要 Microsoft .NET Framework 4.5，這是規劃工具。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-115">Lync Server requires Microsoft .NET Framework 4.5 on all internal server roles and on any computer where you will run the Lync Server administrative tools or Microsoft Lync Server 2013, Planning Tool.</span></span> <span data-ttu-id="a4dc4-116">針對 Lync Server 2013，您必須先在伺服器上手動安裝64位版本的 Microsoft .NET Framework 4.5，才能安裝 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-116">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="a4dc4-117">若要手動安裝，請從 Microsoft 下載中心下載 Microsoft .NET 4.5 架構[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="a4dc4-117">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a><span data-ttu-id="a4dc4-118">在執行 Windows Server 2012 的伺服器上安裝 Microsoft .NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="a4dc4-118">Installing Microsoft .NET Framework 4.5 on Servers Running Windows Server 2012</span></span>

<span data-ttu-id="a4dc4-119">當您在將執行 Lync Server 2013 和 Windows Server 2012 的伺服器上安裝 Microsoft .NET Framework 4.5 時，您必須執行一個額外的步驟。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-119">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 and Windows Server 2012, you must perform one additional step.</span></span> <span data-ttu-id="a4dc4-120">安裝 .NET Framework 4.5 之後，請使用伺服器管理員來安裝 HTTP 啟用。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-120">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="a4dc4-121">**在 Windows Server 2012 上安裝 .NET 4.5 HTTP 啟用**</span><span class="sxs-lookup"><span data-stu-id="a4dc4-121">**To Install .NET 4.5 HTTP Activation on Windows Server 2012**</span></span>

1.  <span data-ttu-id="a4dc4-122">從 [**開始**] 功能表，按一下 [**程式**]，然後按一下 [**管理工具**]，再按一下 [**伺服器管理員**]。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-122">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="a4dc4-123">在 [伺服器管理員] 的 [**功能摘要**] 底下，選擇 [**新增功能**]。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-123">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="a4dc4-124">展開 [ **.Net Framework 4.5**]。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-124">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="a4dc4-125">選取 [ **WCF 啟用**] （如果尚未選取的話）。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-125">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="a4dc4-126">然後選取 [ **HTTP 啟用**]。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-126">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="a4dc4-127">按一下 **[下一步**]，然後依照提示完成安裝。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-127">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a><span data-ttu-id="a4dc4-128">Windows 身分識別基礎</span><span class="sxs-lookup"><span data-stu-id="a4dc4-128">Windows Identity Foundation</span></span>

<span data-ttu-id="a4dc4-129">在 Lync Server 2013 中的**Windows 身分識別基礎**需要安裝 Windows 身分識別基礎，才能支援伺服器到伺服器驗證案例。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-129">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="a4dc4-130">Windows Server 2008 R2 和 Windows Server 2012 需要不同的程式來安裝 Windows 身分識別基礎。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-130">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="a4dc4-131">從下列清單選取您的伺服器作業系統：</span><span class="sxs-lookup"><span data-stu-id="a4dc4-131">Select your server operating system from the following list:</span></span>

  - <span data-ttu-id="a4dc4-132">Windows server 2008 R2 For Windows Server 2008 R2，您可以檢查是否已將它安裝在您的電腦上。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-132">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="a4dc4-133">若要這樣做，請移至 [**新增/移除程式**]、[**查看已安裝的更新**]，然後在 [ **windows** ] 底下看到 [專案**windows 身分識別基礎（KB974405）**]。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-133">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="a4dc4-134">如需安裝 Windows 身分識別基礎的詳細[https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-134">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="a4dc4-135">Windows server 2012 For Windows Server 2012，您可以使用**伺服器管理員**來安裝 Windows 身分識別基礎。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-135">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="a4dc4-136">在伺服器管理員 [**新增角色與功能] 嚮導**中，選取 [**功能**]。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-136">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="a4dc4-137">從清單中選取 [ **Windows 身分識別基礎 3.5** ]。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-137">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="a4dc4-138">按一下 **[下一步]**，然後按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-138">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a><span data-ttu-id="a4dc4-139">適用于所有前端伺服器和標準版伺服器的其他軟體</span><span class="sxs-lookup"><span data-stu-id="a4dc4-139">Additional Software for All Front End Servers and Standard Edition Servers</span></span>

<span data-ttu-id="a4dc4-140">所有前端伺服器和標準版伺服器也都必須在特定的模組中執行網際網路資訊服務（IIS）。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-140">All Front End Servers and Standard Edition servers must also run Internet Information Services (IIS) with certain modules.</span></span> <span data-ttu-id="a4dc4-141">此外，部署會議、通話駐留應用程式、公告或回應群組的所有前端伺服器和標準版伺服器，都必須執行 Windows Media 格式執行時間。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-141">Additionally, all Front End Servers and Standard Edition servers where conferencing, Call Park application, Announcement, or Response Groups are deployed must run Windows Media Format Runtime.</span></span>

<div>

## <a name="internet-information-services-iis"></a><span data-ttu-id="a4dc4-142">網際網路資訊服務（IIS）</span><span class="sxs-lookup"><span data-stu-id="a4dc4-142">Internet Information Services (IIS)</span></span>

<span data-ttu-id="a4dc4-143">前端伺服器和標準版伺服器必須執行網際網路資訊服務（IIS），並附帶下列模組：</span><span class="sxs-lookup"><span data-stu-id="a4dc4-143">Front End Servers and Standard Edition servers must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="a4dc4-144">靜態內容</span><span class="sxs-lookup"><span data-stu-id="a4dc4-144">Static Content</span></span>

  - <span data-ttu-id="a4dc4-145">預設檔</span><span class="sxs-lookup"><span data-stu-id="a4dc4-145">Default Document</span></span>

  - <span data-ttu-id="a4dc4-146">HTTP 錯誤</span><span class="sxs-lookup"><span data-stu-id="a4dc4-146">HTTP Errors</span></span>

  - <span data-ttu-id="a4dc4-147">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a4dc4-147">ASP.NET</span></span>

  - <span data-ttu-id="a4dc4-148">.NET 擴充性</span><span class="sxs-lookup"><span data-stu-id="a4dc4-148">.NET Extensibility</span></span>

  - <span data-ttu-id="a4dc4-149">網際網路伺服器 API （ISAPI）延伸</span><span class="sxs-lookup"><span data-stu-id="a4dc4-149">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="a4dc4-150">ISAPI 篩選</span><span class="sxs-lookup"><span data-stu-id="a4dc4-150">ISAPI Filters</span></span>

  - <span data-ttu-id="a4dc4-151">HTTP 記錄</span><span class="sxs-lookup"><span data-stu-id="a4dc4-151">HTTP Logging</span></span>

  - <span data-ttu-id="a4dc4-152">記錄工具</span><span class="sxs-lookup"><span data-stu-id="a4dc4-152">Logging Tools</span></span>

  - <span data-ttu-id="a4dc4-153">診斷</span><span class="sxs-lookup"><span data-stu-id="a4dc4-153">Tracing</span></span>

  - <span data-ttu-id="a4dc4-154">Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="a4dc4-154">Windows Authentication</span></span>

  - <span data-ttu-id="a4dc4-155">要求篩選</span><span class="sxs-lookup"><span data-stu-id="a4dc4-155">Request Filtering</span></span>

  - <span data-ttu-id="a4dc4-156">靜態內容壓縮</span><span class="sxs-lookup"><span data-stu-id="a4dc4-156">Static Content Compression</span></span>

  - <span data-ttu-id="a4dc4-157">動態內容壓縮</span><span class="sxs-lookup"><span data-stu-id="a4dc4-157">Dynamic Content Compression</span></span>

  - <span data-ttu-id="a4dc4-158">IIS 管理主控台</span><span class="sxs-lookup"><span data-stu-id="a4dc4-158">IIS Management Console</span></span>

  - <span data-ttu-id="a4dc4-159">IIS 管理腳本與工具</span><span class="sxs-lookup"><span data-stu-id="a4dc4-159">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="a4dc4-160">匿名驗證（預設會在安裝 IIS 時安裝）。）</span><span class="sxs-lookup"><span data-stu-id="a4dc4-160">Anonymous Authentication (this is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="a4dc4-161">用戶端憑證對應驗證</span><span class="sxs-lookup"><span data-stu-id="a4dc4-161">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a><span data-ttu-id="a4dc4-162">Windows Media 格式執行時間與 Windows 桌上出版體驗</span><span class="sxs-lookup"><span data-stu-id="a4dc4-162">Windows Media Format Runtime and Windows Desktop Experience</span></span>

<span data-ttu-id="a4dc4-163">**Windows 桌面體驗**部署會議所需的所有前端伺服器和標準版伺服器都必須安裝 Windows Media 執行時間，但 Windows Server 2012 （除了 windows 桌上出版體驗之外）還會安裝。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-163">**Windows Desktop Experience** All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed, which, except for Windows Server 2012 is installed as part of the Windows desktop experience.</span></span> <span data-ttu-id="a4dc4-164">Windows Server 2012 需要 Microsoft 媒體基礎。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-164">Windows Server 2012 requires Microsoft Media Foundation.</span></span> <span data-ttu-id="a4dc4-165">您必須具備 Windows Media 格式執行時間，才能執行通話駐留、宣告及回應群組應用程式的 Windows Media 音訊（.wma）檔案，以便在公告和音樂中播放。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-165">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>

<span data-ttu-id="a4dc4-166">我們建議您先安裝 Windows 桌面體驗，然後再安裝 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-166">We recommend that you install Windows desktop experience before you install Lync Server 2013.</span></span> <span data-ttu-id="a4dc4-167">如果 Lync Server 2013 在伺服器上找不到這個軟體，系統會提示您安裝它，然後您必須重新開機伺服器才能完成安裝。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-167">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a><span data-ttu-id="a4dc4-168">在 Windows Server 2012 上執行的前端伺服器和標準版伺服器的其他軟體</span><span class="sxs-lookup"><span data-stu-id="a4dc4-168">Additional Software for Front End Servers and Standard Edition Servers Running on Windows Server 2012</span></span>

<span data-ttu-id="a4dc4-169">前端伺服器需要 .NET 3.5 （預設不會安裝在 Windows Server 2012 上）。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-169">Front End Servers require .NET 3.5, which is not installed by default on Windows Server 2012.</span></span> <span data-ttu-id="a4dc4-170">若要安裝，請將您的 Windows Server 2012 安裝媒體放在磁碟機 D 中，並輸入以下內容：</span><span class="sxs-lookup"><span data-stu-id="a4dc4-170">To install it, put your Windows Server 2012 installation media in Drive D and type the following:</span></span>

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

<span data-ttu-id="a4dc4-171">如需在執行 Windows Server 2012 的伺服器上安裝 .NET 3.5 的詳細資訊，請參閱「Microsoft .NET Framework <https://go.microsoft.com/fwlink/p/?linkid=275032>3.5 部署考慮」。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-171">For details about installing .NET 3.5 on servers running Windows Server 2012, see "Microsoft .NET Framework 3.5 Deployment Considerations" at <https://go.microsoft.com/fwlink/p/?linkid=275032>.</span></span>

</div>

<div>

## <a name="additional-software-for-directors"></a><span data-ttu-id="a4dc4-172">其他董事版軟體</span><span class="sxs-lookup"><span data-stu-id="a4dc4-172">Additional Software for Directors</span></span>

<span data-ttu-id="a4dc4-173">控制器必須執行網際網路資訊服務（IIS），並提供下列模組：</span><span class="sxs-lookup"><span data-stu-id="a4dc4-173">Directors must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="a4dc4-174">靜態內容</span><span class="sxs-lookup"><span data-stu-id="a4dc4-174">Static Content</span></span>

  - <span data-ttu-id="a4dc4-175">預設檔</span><span class="sxs-lookup"><span data-stu-id="a4dc4-175">Default Document</span></span>

  - <span data-ttu-id="a4dc4-176">HTTP 錯誤</span><span class="sxs-lookup"><span data-stu-id="a4dc4-176">HTTP Errors</span></span>

  - <span data-ttu-id="a4dc4-177">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a4dc4-177">ASP.NET</span></span>

  - <span data-ttu-id="a4dc4-178">.NET 擴充性</span><span class="sxs-lookup"><span data-stu-id="a4dc4-178">.NET Extensibility</span></span>

  - <span data-ttu-id="a4dc4-179">網際網路伺服器 API （ISAPI）延伸</span><span class="sxs-lookup"><span data-stu-id="a4dc4-179">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="a4dc4-180">ISAPI 篩選</span><span class="sxs-lookup"><span data-stu-id="a4dc4-180">ISAPI Filters</span></span>

  - <span data-ttu-id="a4dc4-181">HTTP 記錄</span><span class="sxs-lookup"><span data-stu-id="a4dc4-181">HTTP Logging</span></span>

  - <span data-ttu-id="a4dc4-182">記錄工具</span><span class="sxs-lookup"><span data-stu-id="a4dc4-182">Logging Tools</span></span>

  - <span data-ttu-id="a4dc4-183">診斷</span><span class="sxs-lookup"><span data-stu-id="a4dc4-183">Tracing</span></span>

  - <span data-ttu-id="a4dc4-184">Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="a4dc4-184">Windows Authentication</span></span>

  - <span data-ttu-id="a4dc4-185">要求篩選</span><span class="sxs-lookup"><span data-stu-id="a4dc4-185">Request Filtering</span></span>

  - <span data-ttu-id="a4dc4-186">靜態內容壓縮</span><span class="sxs-lookup"><span data-stu-id="a4dc4-186">Static Content Compression</span></span>

  - <span data-ttu-id="a4dc4-187">IIS 管理主控台</span><span class="sxs-lookup"><span data-stu-id="a4dc4-187">IIS Management Console</span></span>

  - <span data-ttu-id="a4dc4-188">IIS 管理腳本與工具</span><span class="sxs-lookup"><span data-stu-id="a4dc4-188">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="a4dc4-189">匿名驗證（預設會在安裝 IIS 時安裝）。）</span><span class="sxs-lookup"><span data-stu-id="a4dc4-189">Anonymous Authentication (This is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="a4dc4-190">用戶端憑證對應驗證</span><span class="sxs-lookup"><span data-stu-id="a4dc4-190">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a><span data-ttu-id="a4dc4-191">持續聊天前端伺服器的其他軟體</span><span class="sxs-lookup"><span data-stu-id="a4dc4-191">Additional Software for Persistent Chat Front End Servers</span></span>

<span data-ttu-id="a4dc4-192">持續聊天前端伺服器必須執行訊息佇列（也稱為 MSMQ），這是 Windows Server 的元件。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-192">Persistent Chat Front End Servers must run Message Queuing (also known as MSMQ), which is a component of Windows Server.</span></span>

<span data-ttu-id="a4dc4-193">如需啟用 MSMQ 的詳細資訊，請[按一下這裡。](https://technet.microsoft.com/en-us/library/cc771474.aspx)</span><span class="sxs-lookup"><span data-stu-id="a4dc4-193">For information on enabling MSMQ, [click here.](https://technet.microsoft.com/en-us/library/cc771474.aspx)</span></span>

</div>

<div>

## <a name="additional-software-for-edge-servers"></a><span data-ttu-id="a4dc4-194">其他適用于 Edge 伺服器的軟體</span><span class="sxs-lookup"><span data-stu-id="a4dc4-194">Additional Software for Edge Servers</span></span>

<span data-ttu-id="a4dc4-195">Edge 伺服器需要下列軟體：</span><span class="sxs-lookup"><span data-stu-id="a4dc4-195">Edge Servers require the following software:</span></span>

  - <span data-ttu-id="a4dc4-196">每個執行 Lync Server 2013 的伺服器都必須安裝正確的 Windows PowerShell 3.0 版本。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-196">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="a4dc4-197">如需詳細資訊，請參閱[安裝 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-197">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

  - <span data-ttu-id="a4dc4-198">Lync Server 需要 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-198">Lync Server requires Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="a4dc4-199">在 Windows Server 2008 R2 上安裝的 Lync Server 2013，您必須先在伺服器上手動安裝64位版本的 Microsoft .NET Framework 4.5，然後才能安裝 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-199">For Lync Server 2013 installed on Windows Server 2008 R2, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="a4dc4-200">若要手動安裝，請從 Microsoft 下載中心下載 Microsoft .NET 4.5 架構[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="a4dc4-200">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

  - <span data-ttu-id="a4dc4-201">在 Lync Server 2013 中的**Windows 身分識別基礎**需要安裝 Windows 身分識別基礎，才能支援伺服器到伺服器驗證案例。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-201">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="a4dc4-202">Windows Server 2008 R2 和 Windows Server 2012 需要不同的程式來安裝 Windows 身分識別基礎。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-202">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="a4dc4-203">從下列清單選取您的伺服器作業系統：</span><span class="sxs-lookup"><span data-stu-id="a4dc4-203">Select your server operating system from the following list:</span></span>
    
      - <span data-ttu-id="a4dc4-204">Windows server 2008 R2 For Windows Server 2008 R2，您可以檢查是否已將它安裝在您的電腦上。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-204">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="a4dc4-205">若要這樣做，請移至 [**新增/移除程式**]、[**查看已安裝的更新**]，然後在 [ **windows** ] 底下看到 [專案**windows 身分識別基礎（KB974405）**]。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-205">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="a4dc4-206">如需安裝 Windows 身分識別基礎的詳細[https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)資料，請參閱。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-206">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>
    
      - <span data-ttu-id="a4dc4-207">Windows server 2012 For Windows Server 2012，您可以使用**伺服器管理員**來安裝 Windows 身分識別基礎。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-207">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="a4dc4-208">在伺服器管理員 [**新增角色與功能] 嚮導**中，選取 [**功能**]。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-208">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="a4dc4-209">從清單中選取 [ **Windows 身分識別基礎 3.5** ]。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-209">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="a4dc4-210">按一下 **[下一步]**，然後按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-210">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a><span data-ttu-id="a4dc4-211">不要在媒體伺服器上安裝多層次通訊端提供者</span><span class="sxs-lookup"><span data-stu-id="a4dc4-211">Do Not Install Layered Socket Providers on Media Servers</span></span>

<span data-ttu-id="a4dc4-212">請勿在任何前端伺服器或獨立的中繼伺服器上安裝任何 Microsoft 網際網路安全性與加速（ISA） Server 用戶端軟體或任何其他 Winsock 層次服務提供者（LSP）軟體。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-212">Do not install any Microsoft Internet Security and Acceleration (ISA) Server client software, or any other Winsock Layered Service Providers (LSP) software, on any Front End Servers or stand-alone Mediation Servers.</span></span> <span data-ttu-id="a4dc4-213">安裝這個軟體可能會導致媒體流量較差的效能。</span><span class="sxs-lookup"><span data-stu-id="a4dc4-213">Installing this software could cause poor media traffic performance.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a4dc4-214">請參閱</span><span class="sxs-lookup"><span data-stu-id="a4dc4-214">See Also</span></span>


[<span data-ttu-id="a4dc4-215">Lync Server 2013 中的系統管理工具軟體需求</span><span class="sxs-lookup"><span data-stu-id="a4dc4-215">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

