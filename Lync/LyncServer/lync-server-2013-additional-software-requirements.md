---
title: Lync Server 2013：其他軟體需求
description: Lync Server 2013：其他軟體需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbc36f23a2246c9d653e47954064182c756f0dff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553039"
---
# <a name="additional-software-requirements-for-lync-server-2013"></a><span data-ttu-id="f1761-103">Lync Server 2013 的其他軟體需求</span><span class="sxs-lookup"><span data-stu-id="f1761-103">Additional software requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1761-104">_**主題上次修改日期：** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="f1761-104">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="f1761-105">除了伺服器平臺的硬體和作業系統需求之外，Lync Server 2013 還需要在您部署的伺服器上安裝其他軟體。</span><span class="sxs-lookup"><span data-stu-id="f1761-105">In addition to the hardware and operating system requirements for server platforms, Lync Server 2013 requires the installation of additional software on the servers that you deploy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f1761-106">如需執行 Lync Server 之伺服器平臺需求的詳細資訊，請參閱 lync server <A href="lync-server-2013-server-hardware-platforms.md">2013 的伺服器硬體平臺</A> 和 <A href="lync-server-2013-server-and-tools-operating-system-support.md">伺服器及工具作業系統支援（lync server 2013</A>）。</span><span class="sxs-lookup"><span data-stu-id="f1761-106">For details about the platform requirements for servers running Lync Server, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A>.</span></span> <span data-ttu-id="f1761-107">如需用戶端電腦和裝置之系統需求的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-planning-for-clients-and-devices.md">規劃 Lync Server 2013 中的用戶端和裝置</A> 。</span><span class="sxs-lookup"><span data-stu-id="f1761-107">For details about system requirements for client computers and devices, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="f1761-108">如需系統管理工具軟體需求的詳細資訊，請參閱 <A href="lync-server-2013-administrative-tools-software-requirements.md">Lync Server 2013 中的系統管理工具軟體需求</A>。</span><span class="sxs-lookup"><span data-stu-id="f1761-108">For details about software requirements for administrative tools, see <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative tools software requirements in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a><span data-ttu-id="f1761-109">所有內部伺服器角色所需的其他軟體</span><span class="sxs-lookup"><span data-stu-id="f1761-109">Additional Software Necessary for All Internal Server Roles</span></span>

<span data-ttu-id="f1761-110">本節列出所有內部伺服器角色所需的軟體，也就是除 Edge Server 之外所有的 Lync Server server 角色。</span><span class="sxs-lookup"><span data-stu-id="f1761-110">This section lists software necessary on all internal server roles, which are all Lync Server server roles except for Edge Server.</span></span> <span data-ttu-id="f1761-111">Edge server 和 Edge 集區的其他軟體會列在本主題稍後的 **其他適用于 Edge server 的軟體**。</span><span class="sxs-lookup"><span data-stu-id="f1761-111">The requirements for the Edge Servers and Edge pools are listed later in this topic under **Additional Software for Edge Servers**.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="f1761-112">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="f1761-112">Windows PowerShell 3.0</span></span>

<span data-ttu-id="f1761-113">每一部執行 Lync Server 2013 的伺服器必須已安裝正確的 Windows PowerShell 3.0 版本。</span><span class="sxs-lookup"><span data-stu-id="f1761-113">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="f1761-114">如需詳細資訊，請參閱 [安裝適用于 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。</span><span class="sxs-lookup"><span data-stu-id="f1761-114">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="f1761-115">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="f1761-115">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="f1761-116">Lync Server 需要 Microsoft .NET Framework 4.5 在所有內部伺服器角色上，以及您要執行 Lync Server 系統管理工具或 Microsoft Lync Server 2013 的任何電腦上，規劃工具。</span><span class="sxs-lookup"><span data-stu-id="f1761-116">Lync Server requires Microsoft .NET Framework 4.5 on all internal server roles and on any computer where you will run the Lync Server administrative tools or Microsoft Lync Server 2013, Planning Tool.</span></span> <span data-ttu-id="f1761-117">針對 Lync Server 2013，您必須在安裝 Lync Server 2013 之前，先在伺服器上手動安裝64位版本的 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="f1761-117">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="f1761-118">若要手動安裝，請從 Microsoft 下載中心下載 Microsoft .NET 4.5 Framework，網址是 [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="f1761-118">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a><span data-ttu-id="f1761-119">在執行 Windows Server 2012 的伺服器上安裝 Microsoft .NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="f1761-119">Installing Microsoft .NET Framework 4.5 on Servers Running Windows Server 2012</span></span>

<span data-ttu-id="f1761-120">當您在將執行 Lync Server 2013 和 Windows Server 2012 的伺服器上安裝 Microsoft .NET Framework 4.5 時，您必須執行一個額外的步驟。</span><span class="sxs-lookup"><span data-stu-id="f1761-120">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 and Windows Server 2012, you must perform one additional step.</span></span> <span data-ttu-id="f1761-121">安裝 .NET Framework 4.5 後，請使用伺服器管理員安裝 HTTP 啟用。</span><span class="sxs-lookup"><span data-stu-id="f1761-121">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="f1761-122">**在 Windows Server 2012 上安裝 .NET 4.5 HTTP 啟用**</span><span class="sxs-lookup"><span data-stu-id="f1761-122">**To Install .NET 4.5 HTTP Activation on Windows Server 2012**</span></span>

1.  <span data-ttu-id="f1761-123">在 [ **開始** ] 功能表上，按一下 [ **程式**]，然後按一下 [系統 **管理工具**]，再按一下 [ **伺服器管理員**]。</span><span class="sxs-lookup"><span data-stu-id="f1761-123">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="f1761-124">在 [伺服器管理員] 的 [ **功能摘要**] 下，選擇 [ **新增功能**]。</span><span class="sxs-lookup"><span data-stu-id="f1761-124">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="f1761-125">展開 **.Net Framework 4.5**。</span><span class="sxs-lookup"><span data-stu-id="f1761-125">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="f1761-126">選取 [ **WCF 啟用** ] （如果尚未選取）。</span><span class="sxs-lookup"><span data-stu-id="f1761-126">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="f1761-127">然後選取 [ **HTTP 啟用**]。</span><span class="sxs-lookup"><span data-stu-id="f1761-127">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="f1761-128">按 **[下一步** ]，然後依照提示完成安裝。</span><span class="sxs-lookup"><span data-stu-id="f1761-128">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a><span data-ttu-id="f1761-129">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="f1761-129">Windows Identity Foundation</span></span>

<span data-ttu-id="f1761-130">Lync Server 2013 中的**Windows Identity foundation**需要安裝 Windows identity foundation，才能支援伺服器的伺服器驗證案例。</span><span class="sxs-lookup"><span data-stu-id="f1761-130">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="f1761-131">Windows Server 2008 R2 和 Windows Server 2012 需要不同的程式來安裝 Windows 識別基礎。</span><span class="sxs-lookup"><span data-stu-id="f1761-131">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="f1761-132">從下列清單中選取您的伺服器作業系統：</span><span class="sxs-lookup"><span data-stu-id="f1761-132">Select your server operating system from the following list:</span></span>

  - <span data-ttu-id="f1761-133">Windows server 2008 R2 For Windows Server 2008 R2，您可以查看是否已安裝在電腦上。</span><span class="sxs-lookup"><span data-stu-id="f1761-133">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="f1761-134">若要這麼做，請移至 [ **新增/移除程式**]、[ **查看已安裝的更新**]，然後在 [ **windows** ] 下的 [專案 \*\*windows Identity Foundation (KB974405) \*\*中查看。</span><span class="sxs-lookup"><span data-stu-id="f1761-134">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="f1761-135">如需安裝 Windows Identity Foundation 的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) 。</span><span class="sxs-lookup"><span data-stu-id="f1761-135">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="f1761-136">Windows server 2012 For Windows Server 2012，您可以使用 **伺服器管理員** 安裝 Windows Identity Foundation。</span><span class="sxs-lookup"><span data-stu-id="f1761-136">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="f1761-137">在 [伺服器管理員 **新增角色與功能] 嚮導**中，選取 [ **功能**]。</span><span class="sxs-lookup"><span data-stu-id="f1761-137">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="f1761-138">從清單中選取 [ **Windows Identity Foundation 3.5** ]。</span><span class="sxs-lookup"><span data-stu-id="f1761-138">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="f1761-139">按 **[下一步]**，然後按一下 [ **安裝**]。</span><span class="sxs-lookup"><span data-stu-id="f1761-139">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a><span data-ttu-id="f1761-140">所有前端伺服器和 Standard Edition Server 的其他軟體</span><span class="sxs-lookup"><span data-stu-id="f1761-140">Additional Software for All Front End Servers and Standard Edition Servers</span></span>

<span data-ttu-id="f1761-141">所有前端伺服器和 Standard Edition server 也必須執行 Internet Information Services (IIS) 與某些模組。</span><span class="sxs-lookup"><span data-stu-id="f1761-141">All Front End Servers and Standard Edition servers must also run Internet Information Services (IIS) with certain modules.</span></span> <span data-ttu-id="f1761-142">此外，部署會議、通話駐留應用程式、宣告或回應群組的所有前端伺服器和 Standard Edition 伺服器，都必須執行 Windows Media Format Runtime。</span><span class="sxs-lookup"><span data-stu-id="f1761-142">Additionally, all Front End Servers and Standard Edition servers where conferencing, Call Park application, Announcement, or Response Groups are deployed must run Windows Media Format Runtime.</span></span>

<div>

## <a name="internet-information-services-iis"></a><span data-ttu-id="f1761-143">Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="f1761-143">Internet Information Services (IIS)</span></span>

<span data-ttu-id="f1761-144">前端伺服器和 Standard Edition 伺服器必須使用下列模組執行 Internet Information Services (IIS) ：</span><span class="sxs-lookup"><span data-stu-id="f1761-144">Front End Servers and Standard Edition servers must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="f1761-145">靜態內容</span><span class="sxs-lookup"><span data-stu-id="f1761-145">Static Content</span></span>

  - <span data-ttu-id="f1761-146">預設文件</span><span class="sxs-lookup"><span data-stu-id="f1761-146">Default Document</span></span>

  - <span data-ttu-id="f1761-147">HTTP 錯誤</span><span class="sxs-lookup"><span data-stu-id="f1761-147">HTTP Errors</span></span>

  - <span data-ttu-id="f1761-148">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f1761-148">ASP.NET</span></span>

  - <span data-ttu-id="f1761-149">.NET 擴充性</span><span class="sxs-lookup"><span data-stu-id="f1761-149">.NET Extensibility</span></span>

  - <span data-ttu-id="f1761-150">網際網路伺服器 API (ISAPI) 擴充</span><span class="sxs-lookup"><span data-stu-id="f1761-150">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="f1761-151">ISAPI 篩選</span><span class="sxs-lookup"><span data-stu-id="f1761-151">ISAPI Filters</span></span>

  - <span data-ttu-id="f1761-152">HTTP 記錄</span><span class="sxs-lookup"><span data-stu-id="f1761-152">HTTP Logging</span></span>

  - <span data-ttu-id="f1761-153">記錄工具</span><span class="sxs-lookup"><span data-stu-id="f1761-153">Logging Tools</span></span>

  - <span data-ttu-id="f1761-154">跟蹤</span><span class="sxs-lookup"><span data-stu-id="f1761-154">Tracing</span></span>

  - <span data-ttu-id="f1761-155">Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="f1761-155">Windows Authentication</span></span>

  - <span data-ttu-id="f1761-156">要求篩選</span><span class="sxs-lookup"><span data-stu-id="f1761-156">Request Filtering</span></span>

  - <span data-ttu-id="f1761-157">靜態內容壓縮</span><span class="sxs-lookup"><span data-stu-id="f1761-157">Static Content Compression</span></span>

  - <span data-ttu-id="f1761-158">動態內容壓縮</span><span class="sxs-lookup"><span data-stu-id="f1761-158">Dynamic Content Compression</span></span>

  - <span data-ttu-id="f1761-159">IIS 管理主控台</span><span class="sxs-lookup"><span data-stu-id="f1761-159">IIS Management Console</span></span>

  - <span data-ttu-id="f1761-160">IIS 管理指令碼與工具</span><span class="sxs-lookup"><span data-stu-id="f1761-160">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="f1761-161">匿名驗證 (在安裝 IIS 時預設會安裝此功能。 ) </span><span class="sxs-lookup"><span data-stu-id="f1761-161">Anonymous Authentication (this is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="f1761-162">用戶端憑證對應驗證</span><span class="sxs-lookup"><span data-stu-id="f1761-162">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a><span data-ttu-id="f1761-163">Windows Media Format Runtime 和 Windows 桌面體驗</span><span class="sxs-lookup"><span data-stu-id="f1761-163">Windows Media Format Runtime and Windows Desktop Experience</span></span>

<span data-ttu-id="f1761-164">**Windows 桌面體驗** 所有要部署會議的前端伺服器和 Standard Edition 伺服器都必須已安裝 Windows Media Format Runtime，但 Windows Server 2012 除外，也會安裝 windows 桌面體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="f1761-164">**Windows Desktop Experience** All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed, which, except for Windows Server 2012 is installed as part of the Windows desktop experience.</span></span> <span data-ttu-id="f1761-165">Windows Server 2012 需要 Microsoft Media Foundation。</span><span class="sxs-lookup"><span data-stu-id="f1761-165">Windows Server 2012 requires Microsoft Media Foundation.</span></span> <span data-ttu-id="f1761-166">Windows Media Format Runtime 是執行 Windows Media Audio () 檔案，可讓通話駐留、宣告及回應群組應用程式對宣告和音樂播放。</span><span class="sxs-lookup"><span data-stu-id="f1761-166">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>

<span data-ttu-id="f1761-167">建議您先安裝 Windows 桌面體驗，再安裝 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="f1761-167">We recommend that you install Windows desktop experience before you install Lync Server 2013.</span></span> <span data-ttu-id="f1761-168">如果 Lync Server 2013 在伺服器上找不到此軟體，它會提示您安裝它，然後您必須重新開機伺服器以完成安裝。</span><span class="sxs-lookup"><span data-stu-id="f1761-168">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a><span data-ttu-id="f1761-169">在 Windows Server 2012 上執行的前端伺服器和 Standard Edition 伺服器的其他軟體</span><span class="sxs-lookup"><span data-stu-id="f1761-169">Additional Software for Front End Servers and Standard Edition Servers Running on Windows Server 2012</span></span>

<span data-ttu-id="f1761-170">前端伺服器需要 .NET 3.5，這不會在 Windows Server 2012 上預設安裝。</span><span class="sxs-lookup"><span data-stu-id="f1761-170">Front End Servers require .NET 3.5, which is not installed by default on Windows Server 2012.</span></span> <span data-ttu-id="f1761-171">若要安裝，請將 Windows Server 2012 安裝媒體置於磁碟機 D 中，並輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="f1761-171">To install it, put your Windows Server 2012 installation media in Drive D and type the following:</span></span>

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

<span data-ttu-id="f1761-172">如需在執行 Windows Server 2012 的伺服器上安裝 .NET 3.5 的詳細資訊，請參閱 at 中的「Microsoft .NET Framework 3.5 部署考慮」 <https://go.microsoft.com/fwlink/p/?linkid=275032> 。</span><span class="sxs-lookup"><span data-stu-id="f1761-172">For details about installing .NET 3.5 on servers running Windows Server 2012, see "Microsoft .NET Framework 3.5 Deployment Considerations" at <https://go.microsoft.com/fwlink/p/?linkid=275032>.</span></span>

</div>

<div>

## <a name="additional-software-for-directors"></a><span data-ttu-id="f1761-173">Director 的其他軟體</span><span class="sxs-lookup"><span data-stu-id="f1761-173">Additional Software for Directors</span></span>

<span data-ttu-id="f1761-174">Director 必須使用下列模組執行 Internet Information Services (IIS) ：</span><span class="sxs-lookup"><span data-stu-id="f1761-174">Directors must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="f1761-175">靜態內容</span><span class="sxs-lookup"><span data-stu-id="f1761-175">Static Content</span></span>

  - <span data-ttu-id="f1761-176">預設文件</span><span class="sxs-lookup"><span data-stu-id="f1761-176">Default Document</span></span>

  - <span data-ttu-id="f1761-177">HTTP 錯誤</span><span class="sxs-lookup"><span data-stu-id="f1761-177">HTTP Errors</span></span>

  - <span data-ttu-id="f1761-178">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f1761-178">ASP.NET</span></span>

  - <span data-ttu-id="f1761-179">.NET 擴充性</span><span class="sxs-lookup"><span data-stu-id="f1761-179">.NET Extensibility</span></span>

  - <span data-ttu-id="f1761-180">網際網路伺服器 API (ISAPI) 擴充</span><span class="sxs-lookup"><span data-stu-id="f1761-180">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="f1761-181">ISAPI 篩選</span><span class="sxs-lookup"><span data-stu-id="f1761-181">ISAPI Filters</span></span>

  - <span data-ttu-id="f1761-182">HTTP 記錄</span><span class="sxs-lookup"><span data-stu-id="f1761-182">HTTP Logging</span></span>

  - <span data-ttu-id="f1761-183">記錄工具</span><span class="sxs-lookup"><span data-stu-id="f1761-183">Logging Tools</span></span>

  - <span data-ttu-id="f1761-184">跟蹤</span><span class="sxs-lookup"><span data-stu-id="f1761-184">Tracing</span></span>

  - <span data-ttu-id="f1761-185">Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="f1761-185">Windows Authentication</span></span>

  - <span data-ttu-id="f1761-186">要求篩選</span><span class="sxs-lookup"><span data-stu-id="f1761-186">Request Filtering</span></span>

  - <span data-ttu-id="f1761-187">靜態內容壓縮</span><span class="sxs-lookup"><span data-stu-id="f1761-187">Static Content Compression</span></span>

  - <span data-ttu-id="f1761-188">IIS 管理主控台</span><span class="sxs-lookup"><span data-stu-id="f1761-188">IIS Management Console</span></span>

  - <span data-ttu-id="f1761-189">IIS 管理指令碼與工具</span><span class="sxs-lookup"><span data-stu-id="f1761-189">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="f1761-190">匿名驗證 (在安裝 IIS 時預設會安裝此功能。 ) </span><span class="sxs-lookup"><span data-stu-id="f1761-190">Anonymous Authentication (This is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="f1761-191">用戶端憑證對應驗證</span><span class="sxs-lookup"><span data-stu-id="f1761-191">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a><span data-ttu-id="f1761-192">適用于持久聊天前端伺服器的其他軟體</span><span class="sxs-lookup"><span data-stu-id="f1761-192">Additional Software for Persistent Chat Front End Servers</span></span>

<span data-ttu-id="f1761-193">Persistent Chat 前端伺服器必須執行郵件佇列 (也稱為 MSMQ) ，也就是 Windows Server 的元件。</span><span class="sxs-lookup"><span data-stu-id="f1761-193">Persistent Chat Front End Servers must run Message Queuing (also known as MSMQ), which is a component of Windows Server.</span></span>

<span data-ttu-id="f1761-194">如需啟用 MSMQ 的資訊，請 [按一下這裡。](https://technet.microsoft.com/library/cc771474.aspx)</span><span class="sxs-lookup"><span data-stu-id="f1761-194">For information on enabling MSMQ, [click here.](https://technet.microsoft.com/library/cc771474.aspx)</span></span>

</div>

<div>

## <a name="additional-software-for-edge-servers"></a><span data-ttu-id="f1761-195">其他 Edge Server 軟體</span><span class="sxs-lookup"><span data-stu-id="f1761-195">Additional Software for Edge Servers</span></span>

<span data-ttu-id="f1761-196">Edge Server 需要下列軟體：</span><span class="sxs-lookup"><span data-stu-id="f1761-196">Edge Servers require the following software:</span></span>

  - <span data-ttu-id="f1761-197">每一部執行 Lync Server 2013 的伺服器必須已安裝正確的 Windows PowerShell 3.0 版本。</span><span class="sxs-lookup"><span data-stu-id="f1761-197">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="f1761-198">如需詳細資訊，請參閱 [安裝適用于 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。</span><span class="sxs-lookup"><span data-stu-id="f1761-198">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

  - <span data-ttu-id="f1761-199">Lync Server 需要 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="f1761-199">Lync Server requires Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="f1761-200">針對安裝在 Windows Server 2008 R2 上的 Lync Server 2013，您必須在安裝 Lync Server 2013 之前，先在伺服器上手動安裝64位版本的 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="f1761-200">For Lync Server 2013 installed on Windows Server 2008 R2, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="f1761-201">若要手動安裝，請從 Microsoft 下載中心下載 Microsoft .NET 4.5 Framework，網址是 [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="f1761-201">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

  - <span data-ttu-id="f1761-202">Lync Server 2013 中的**Windows Identity foundation**需要安裝 Windows identity foundation，才能支援伺服器的伺服器驗證案例。</span><span class="sxs-lookup"><span data-stu-id="f1761-202">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="f1761-203">Windows Server 2008 R2 和 Windows Server 2012 需要不同的程式來安裝 Windows 識別基礎。</span><span class="sxs-lookup"><span data-stu-id="f1761-203">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="f1761-204">從下列清單中選取您的伺服器作業系統：</span><span class="sxs-lookup"><span data-stu-id="f1761-204">Select your server operating system from the following list:</span></span>
    
      - <span data-ttu-id="f1761-205">Windows server 2008 R2 For Windows Server 2008 R2，您可以查看是否已安裝在電腦上。</span><span class="sxs-lookup"><span data-stu-id="f1761-205">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="f1761-206">若要這麼做，請移至 [ **新增/移除程式**]、[ **查看已安裝的更新**]，然後在 [ **windows** ] 下的 [專案 \*\*windows Identity Foundation (KB974405) \*\*中查看。</span><span class="sxs-lookup"><span data-stu-id="f1761-206">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="f1761-207">如需安裝 Windows Identity Foundation 的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) 。</span><span class="sxs-lookup"><span data-stu-id="f1761-207">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>
    
      - <span data-ttu-id="f1761-208">Windows server 2012 For Windows Server 2012，您可以使用 **伺服器管理員** 安裝 Windows Identity Foundation。</span><span class="sxs-lookup"><span data-stu-id="f1761-208">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="f1761-209">在 [伺服器管理員 **新增角色與功能] 嚮導**中，選取 [ **功能**]。</span><span class="sxs-lookup"><span data-stu-id="f1761-209">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="f1761-210">從清單中選取 [ **Windows Identity Foundation 3.5** ]。</span><span class="sxs-lookup"><span data-stu-id="f1761-210">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="f1761-211">按 **[下一步]**，然後按一下 [ **安裝**]。</span><span class="sxs-lookup"><span data-stu-id="f1761-211">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a><span data-ttu-id="f1761-212">不要在媒體伺服器上安裝分層通訊端提供者</span><span class="sxs-lookup"><span data-stu-id="f1761-212">Do Not Install Layered Socket Providers on Media Servers</span></span>

<span data-ttu-id="f1761-213">請勿在任何前端伺服器或獨立轉送伺服器上安裝任何 Microsoft Internet 安全性和加速 (ISA) Server 用戶端軟體或任何其他 Winsock 分層服務提供者 (LSP) 軟體。</span><span class="sxs-lookup"><span data-stu-id="f1761-213">Do not install any Microsoft Internet Security and Acceleration (ISA) Server client software, or any other Winsock Layered Service Providers (LSP) software, on any Front End Servers or stand-alone Mediation Servers.</span></span> <span data-ttu-id="f1761-214">安裝此軟體可能會導致媒體流量效能降低。</span><span class="sxs-lookup"><span data-stu-id="f1761-214">Installing this software could cause poor media traffic performance.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f1761-215">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f1761-215">See Also</span></span>


[<span data-ttu-id="f1761-216">Lync Server 2013 中的系統管理工具軟體需求</span><span class="sxs-lookup"><span data-stu-id="f1761-216">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

