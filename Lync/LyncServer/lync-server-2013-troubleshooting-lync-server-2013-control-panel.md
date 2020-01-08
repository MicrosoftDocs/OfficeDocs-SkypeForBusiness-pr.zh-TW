---
title: Lync Server 2013：疑難排解 Lync Server 2013 [控制台]
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 943f2ab5f0fe808d1bf5e10cf8b451ac1df2575b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a><span data-ttu-id="79dde-102">Lync Server 2013 [控制台] 的疑難排解</span><span class="sxs-lookup"><span data-stu-id="79dde-102">Troubleshooting Lync Server 2013 Control Panel</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79dde-103">_**主題上次修改日期：** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="79dde-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="79dde-104">本主題提供的資訊和程式可協助您疑難排解 Lync Server 2013 [控制台] 的存取權。</span><span class="sxs-lookup"><span data-stu-id="79dde-104">This topic provides information and procedures that can help you troubleshoot access to Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="internet-browser-requirements"></a><span data-ttu-id="79dde-105">網際網路瀏覽器的需求</span><span class="sxs-lookup"><span data-stu-id="79dde-105">Internet Browser Requirements</span></span>

<span data-ttu-id="79dde-106">Lync Server 控制台需要安裝 Microsoft Silverlight 瀏覽器外掛程式版本4.0.50524.0 或最新版本。</span><span class="sxs-lookup"><span data-stu-id="79dde-106">Lync Server Control Panel requires that Microsoft Silverlight browser plug-in version 4.0.50524.0 or latest version is installed.</span></span> <span data-ttu-id="79dde-107">如果未安裝 Silverlight，或安裝的是舊版版本，請依照訊息中的指示安裝所需的版本。</span><span class="sxs-lookup"><span data-stu-id="79dde-107">If Silverlight is not installed or if an earlier version is installed, follow the instructions in the message to install the required version.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="79dde-108">Lync Server [控制台] 的其他軟體需求適用于 Lync Server [控制台] 以及所有其他 Lync Server 2013 系統管理工具可安裝的作業系統。</span><span class="sxs-lookup"><span data-stu-id="79dde-108">Other software requirements for Lync Server Control Panel pertain to the operating system on which Lync Server Control Panel and all other Lync Server 2013 administrative tools can be installed.</span></span> <span data-ttu-id="79dde-109">如需詳細資訊，請參閱支援檔中的<A href="lync-server-2013-server-and-tools-operating-system-support.md">Lync server 2013 中的伺服器和工具作業系統支援</A>。</span><span class="sxs-lookup"><span data-stu-id="79dde-109">For details, see <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="79dde-110">如果您的網際網路瀏覽器由於安全考慮而封鎖 Silverlight 的安裝，請將開啟 Lync Server [控制台] 的統一資源定位器（URL）新增到信任的網站清單中。</span><span class="sxs-lookup"><span data-stu-id="79dde-110">If your Internet browser blocks installation of Silverlight due to security considerations, add the Uniform Resource Locator (URL) that opens Lync Server Control Panel to the list of trusted sites.</span></span> <span data-ttu-id="79dde-111">在 Internet Explorer 安全性設定中，請確定 **[執行 ActiveX 控制項與外掛程式]** 已設定為 [**啟用**]。</span><span class="sxs-lookup"><span data-stu-id="79dde-111">In Internet Explorer security settings, ensure that **Run ActiveX controls and plug-ins** is set to **Enabled**.</span></span> <span data-ttu-id="79dde-112">如需詳細資訊[http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060)，請參閱。</span><span class="sxs-lookup"><span data-stu-id="79dde-112">For details, see [http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060).</span></span> <span data-ttu-id="79dde-113">此外，請確定瀏覽器已設定為使用 SSL 3.0。</span><span class="sxs-lookup"><span data-stu-id="79dde-113">Furthermore, ensure that the browser is configured to use SSL 3.0.</span></span>

<span data-ttu-id="79dde-114">如果 Internet 瀏覽器已設定為使用 proxy 伺服器，請確認瀏覽器已設定為對自動偵測為內部網站的網站略過 proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="79dde-114">If the Internet browser is configured to use a proxy server, verify that the browser is configured to bypass the proxy server for sites that are automatically detected as internal sites.</span></span> <span data-ttu-id="79dde-115">或者，在 proxy 伺服器設定中，將位址新增到瀏覽器的例外清單中。</span><span class="sxs-lookup"><span data-stu-id="79dde-115">Or, add the address to the browser's exception list in the proxy server configuration settings.</span></span>

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a><span data-ttu-id="79dde-116">管理存取 URL 的 DNS 記錄與證書需求</span><span class="sxs-lookup"><span data-stu-id="79dde-116">DNS Record and Certificate Requirements for the Administrative Access URL</span></span>

<span data-ttu-id="79dde-117">如果您已將簡單的 URL 設定為 access Lync Server 控制台，請確定您也已設定靜態網域名稱系統（DNS）主機（A）資源記錄及證書，以使用該管理存取 URL。</span><span class="sxs-lookup"><span data-stu-id="79dde-117">If you configured a simple URL to access Lync Server Control Panel, ensure that you also configured the static Domain Name System (DNS) host (A) resource record and certificate necessary to use that administrative access URL.</span></span> <span data-ttu-id="79dde-118">如果您隨時變更基底 URL，請確定變更會反映在適當的 DNS 記錄和憑證中，並且您在每個控制器和前端伺服器上執行*Enable CsComputer*來登錄變更。</span><span class="sxs-lookup"><span data-stu-id="79dde-118">If you change the base URL at any time, ensure that the change is reflected in the appropriate DNS record and certificate and that you run the *Enable-CsComputer* on each Director and Front End Server to register the change.</span></span> <span data-ttu-id="79dde-119">如需詳細資訊，請參閱規劃檔中的下列主題：</span><span class="sxs-lookup"><span data-stu-id="79dde-119">For details, see the following topics in the Planning documentation:</span></span>

  - [<span data-ttu-id="79dde-120">在 Lync Server 2013 中規劃簡單 URL</span><span class="sxs-lookup"><span data-stu-id="79dde-120">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)

  - [<span data-ttu-id="79dde-121">Lync Server 2013 中簡單 URL 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="79dde-121">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="79dde-122">Lync Server 2013 中內部伺服器的憑證需求</span><span class="sxs-lookup"><span data-stu-id="79dde-122">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

<span data-ttu-id="79dde-123">如需設定管理存取 URL 的逐步程式，請參閱在部署檔中[編輯或設定 Lync Server 2013 中的簡單 url](lync-server-2013-edit-or-configure-simple-urls.md) 。</span><span class="sxs-lookup"><span data-stu-id="79dde-123">For step-by-step procedures to configure the administrative access URL, see [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="79dde-124">網際網路資訊服務（IIS）需求</span><span class="sxs-lookup"><span data-stu-id="79dde-124">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="79dde-125">Lync Server [控制台] 是需要 Internet Information Services （IIS）的 Lync Server 2013 元件之一。</span><span class="sxs-lookup"><span data-stu-id="79dde-125">Lync Server Control Panel is one of the components of Lync Server 2013 that requires Internet Information Services (IIS).</span></span> <span data-ttu-id="79dde-126">特別是，請確定已啟用 HTTP 重新導向及 Windows 驗證功能，且萬維網發佈服務（W3SVC）正在執行。</span><span class="sxs-lookup"><span data-stu-id="79dde-126">In particular, ensure that HTTP redirection and Windows authentication features are enabled, and that the World Wide Web Publishing Service (W3SVC) is running.</span></span>

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a><span data-ttu-id="79dde-127">全球廣發佈服務（Windows 服務）相依性</span><span class="sxs-lookup"><span data-stu-id="79dde-127">World Wide Publishing Service (Windows Service) Dependency</span></span>

<span data-ttu-id="79dde-128">當萬維網發佈服務停止時，您無法存取 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="79dde-128">When the World Wide Web Publishing Service is stopped, you cannot access Lync Server Control Panel.</span></span> <span data-ttu-id="79dde-129">您可以使用 Windows Services Microsoft 管理主控台（MMC）重新開機服務。</span><span class="sxs-lookup"><span data-stu-id="79dde-129">You can restart the service by using the Windows Services Microsoft Management Console (MMC).</span></span>

<span data-ttu-id="79dde-130">**啟動 World Wide Web 發佈服務**</span><span class="sxs-lookup"><span data-stu-id="79dde-130">**To start the World Wide Web Publishing Service**</span></span>

1.  <span data-ttu-id="79dde-131">登入安裝萬維網發佈服務的電腦，這是網際網路資訊服務（IIS）的一部分。</span><span class="sxs-lookup"><span data-stu-id="79dde-131">Log on to the computer where the World Wide Web Publishing Service is installed as part of Internet Information Services (IIS).</span></span>

2.  <span data-ttu-id="79dde-132">按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [**服務**]。</span><span class="sxs-lookup"><span data-stu-id="79dde-132">Click **Start**, click **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="79dde-133">以滑鼠右鍵按一下 [**萬維網發佈服務**]，然後按一下 [**開始**]。</span><span class="sxs-lookup"><span data-stu-id="79dde-133">Right-click **World Wide Web Publishing Service**, and then click **Start**.</span></span>

</div>

<div>

## <a name="application-pool-mode"></a><span data-ttu-id="79dde-134">應用程式池模式</span><span class="sxs-lookup"><span data-stu-id="79dde-134">Application Pool Mode</span></span>

<span data-ttu-id="79dde-135">設定 IIS，讓 CsManagementAppPool 應用程式池使用 Network Service 帳戶做為其處理模型身分識別。</span><span class="sxs-lookup"><span data-stu-id="79dde-135">Configure IIS so that the CsManagementAppPool application pool uses the Network Service account as its process model identity.</span></span>

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a><span data-ttu-id="79dde-136">使用者權利與許可權</span><span class="sxs-lookup"><span data-stu-id="79dde-136">User Rights and Permissions</span></span>

<span data-ttu-id="79dde-137">您必須使用是 CsAdministrator 群組成員的網域帳戶，或使用您已委派使用者權利和許可權的帳戶登入 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="79dde-137">You must sign in to Lync Server Control Panel either by using a domain account that is a member of the CsAdministrator group or by using an account to which you have delegated user rights and permissions.</span></span> <span data-ttu-id="79dde-138">您無法使用本機電腦帳戶登入 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="79dde-138">You cannot sign in to Lync Server Control Panel by using a local machine account.</span></span> <span data-ttu-id="79dde-139">如需透過角色式存取控制（RBAC）委派管理工作的詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的角色式存取控制規劃](lync-server-2013-planning-for-role-based-access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="79dde-139">For details about delegating administrative tasks through role-based access control (RBAC), see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="79dde-140">如果您使用簡單的 URL 來存取 Lync Server 控制台，請確定網頁伺服器已新增至 RTCUniversalServerAdmins 和 RTCUniversalUserAdmins 群組。</span><span class="sxs-lookup"><span data-stu-id="79dde-140">If you use a simple URL to access Lync Server Control Panel, ensure that web servers are added to the RTCUniversalServerAdmins and RTCUniversalUserAdmins groups.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="79dde-141">請參閱</span><span class="sxs-lookup"><span data-stu-id="79dde-141">See Also</span></span>


[<span data-ttu-id="79dde-142">Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="79dde-142">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

