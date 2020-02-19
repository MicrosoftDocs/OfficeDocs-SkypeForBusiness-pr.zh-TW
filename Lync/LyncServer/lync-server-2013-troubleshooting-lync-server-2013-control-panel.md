---
title: 'Lync Server 2013: Troubleshooting Lync Server 2013 控制台'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07e670dc0871490e513023d3276ad80126be173b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a><span data-ttu-id="bbc4a-102">疑難排解 Lync Server 2013 控制台</span><span class="sxs-lookup"><span data-stu-id="bbc4a-102">Troubleshooting Lync Server 2013 Control Panel</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbc4a-103">_**主題上次修改日期：** 2016年-07-28_</span><span class="sxs-lookup"><span data-stu-id="bbc4a-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="bbc4a-104">本主題提供的資訊和程序，可協助您疑難排解存取 Lync Server 2013 控制台。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-104">This topic provides information and procedures that can help you troubleshoot access to Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="internet-browser-requirements"></a><span data-ttu-id="bbc4a-105">網際網路瀏覽器需求</span><span class="sxs-lookup"><span data-stu-id="bbc4a-105">Internet Browser Requirements</span></span>

<span data-ttu-id="bbc4a-106">Lync Server 控制台需要已安裝 Microsoft Silverlight 瀏覽器外掛程式版本 4.0.50524.0 或最新版本。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-106">Lync Server Control Panel requires that Microsoft Silverlight browser plug-in version 4.0.50524.0 or latest version is installed.</span></span> <span data-ttu-id="bbc4a-107">如果未安裝 Silverlight 或安裝更早的版本，請依照下列訊息即可安裝必要的版本中的指示。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-107">If Silverlight is not installed or if an earlier version is installed, follow the instructions in the message to install the required version.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bbc4a-108">Lync Server 控制台的其他軟體需求適用於 Lync Server Control Panel 及所有其他 Lync Server 2013 系統管理工具可以安裝所在的作業系統。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-108">Other software requirements for Lync Server Control Panel pertain to the operating system on which Lync Server Control Panel and all other Lync Server 2013 administrative tools can be installed.</span></span> <span data-ttu-id="bbc4a-109">如需詳細資訊，請參閱支援文件中的<A href="lync-server-2013-server-and-tools-operating-system-support.md">Lync Server 2013 中的伺服器和工具作業系統支援</A>。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-109">For details, see <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="bbc4a-110">如果您網際網路瀏覽器封鎖安裝 Silverlight 因安全性考量而新增統一資源定位器 (URL)，會開啟 Lync Server Control Panel 的信任網站清單。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-110">If your Internet browser blocks installation of Silverlight due to security considerations, add the Uniform Resource Locator (URL) that opens Lync Server Control Panel to the list of trusted sites.</span></span> <span data-ttu-id="bbc4a-111">在 Internet Explorer 安全性設定中，確定 [執行 ActiveX 控制項及外掛程式]\*\*\*\* 設為 [已啟用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-111">In Internet Explorer security settings, ensure that **Run ActiveX controls and plug-ins** is set to **Enabled**.</span></span> <span data-ttu-id="bbc4a-112">如需詳細資訊，請參閱[https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060)。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-112">For details, see [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060).</span></span> <span data-ttu-id="bbc4a-113">此外，請確定瀏覽器設定為使用 SSL 3.0。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-113">Furthermore, ensure that the browser is configured to use SSL 3.0.</span></span>

<span data-ttu-id="bbc4a-p104">如果網際網路瀏覽器設定為使用 Proxy 伺服器，請確認瀏覽器針對自動偵測為內部站台的站台，設定為略過 Proxy 伺服器。或者，在 Proxy 伺服器組態設定中，將位址新增至瀏覽器的例外清單。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-p104">If the Internet browser is configured to use a proxy server, verify that the browser is configured to bypass the proxy server for sites that are automatically detected as internal sites. Or, add the address to the browser's exception list in the proxy server configuration settings.</span></span>

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a><span data-ttu-id="bbc4a-116">系統管理存取 URL 的 DNS 記錄及憑證需求</span><span class="sxs-lookup"><span data-stu-id="bbc4a-116">DNS Record and Certificate Requirements for the Administrative Access URL</span></span>

<span data-ttu-id="bbc4a-117">如果您設定簡單 URL 來存取 Lync Server Control Panel，請確定您也設定靜態的網域名稱系統 (DNS) 主機 (A) 資源記錄和憑證必須使用該系統管理存取 URL。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-117">If you configured a simple URL to access Lync Server Control Panel, ensure that you also configured the static Domain Name System (DNS) host (A) resource record and certificate necessary to use that administrative access URL.</span></span> <span data-ttu-id="bbc4a-118">如果您在任何時間變更的基底 URL，請確定此變更會反映在適當的 DNS 記錄和憑證，而且您執行*Enable-cscomputer* ，以登錄變更每個 Director 與前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-118">If you change the base URL at any time, ensure that the change is reflected in the appropriate DNS record and certificate and that you run the *Enable-CsComputer* on each Director and Front End Server to register the change.</span></span> <span data-ttu-id="bbc4a-119">如需詳細資訊，請參閱＜規劃＞文件中的下列主題：</span><span class="sxs-lookup"><span data-stu-id="bbc4a-119">For details, see the following topics in the Planning documentation:</span></span>

  - [<span data-ttu-id="bbc4a-120">規劃 Lync Server 2013 中的簡單 Url</span><span class="sxs-lookup"><span data-stu-id="bbc4a-120">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)

  - [<span data-ttu-id="bbc4a-121">Lync Server 2013 中的簡單 Url 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="bbc4a-121">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="bbc4a-122">適用於 Lync Server 2013 中的內部伺服器的憑證需求</span><span class="sxs-lookup"><span data-stu-id="bbc4a-122">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

<span data-ttu-id="bbc4a-123">若要設定系統管理存取 URL 的逐步程序，請參閱部署文件中的[編輯或設定在 Lync Server 2013 中的簡單 Url](lync-server-2013-edit-or-configure-simple-urls.md) 。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-123">For step-by-step procedures to configure the administrative access URL, see [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="bbc4a-124">Internet Information Services (IIS) 需求</span><span class="sxs-lookup"><span data-stu-id="bbc4a-124">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="bbc4a-125">Lync Server Control Panel 是一個需要網際網路資訊服務 (IIS) 的 Lync Server 2013 的元件。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-125">Lync Server Control Panel is one of the components of Lync Server 2013 that requires Internet Information Services (IIS).</span></span> <span data-ttu-id="bbc4a-126">特別是，請確定 HTTP 重新導向和 Windows 驗證功能已啟用，而且 World Wide Web Publishing 服務 (W3SVC) 正在執行。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-126">In particular, ensure that HTTP redirection and Windows authentication features are enabled, and that the World Wide Web Publishing Service (W3SVC) is running.</span></span>

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a><span data-ttu-id="bbc4a-127">World Wide Publishing Service (Windows 服務) 相依性</span><span class="sxs-lookup"><span data-stu-id="bbc4a-127">World Wide Publishing Service (Windows Service) Dependency</span></span>

<span data-ttu-id="bbc4a-128">World Wide Web Publishing 服務停止時，您不能存取 Lync Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-128">When the World Wide Web Publishing Service is stopped, you cannot access Lync Server Control Panel.</span></span> <span data-ttu-id="bbc4a-129">您可以使用 Windows Services Microsoft Management Console (MMC) 來重新啟動服務。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-129">You can restart the service by using the Windows Services Microsoft Management Console (MMC).</span></span>

<span data-ttu-id="bbc4a-130">**啟動 World Wide Web Publishing 服務**</span><span class="sxs-lookup"><span data-stu-id="bbc4a-130">**To start the World Wide Web Publishing Service**</span></span>

1.  <span data-ttu-id="bbc4a-131">World Wide Web Publishing 服務一部分的網際網路資訊服務 (IIS) 的安裝所在的電腦登入。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-131">Log on to the computer where the World Wide Web Publishing Service is installed as part of Internet Information Services (IIS).</span></span>

2.  <span data-ttu-id="bbc4a-132">依序按一下 [開始]\*\*\*\*、[系統管理工具]\*\*\*\* 和 [服務]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-132">Click **Start**, click **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="bbc4a-133">用滑鼠右鍵按一下 [World Wide Web Publishing 服務]\*\*\*\*，然後按一下 [啟動]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-133">Right-click **World Wide Web Publishing Service**, and then click **Start**.</span></span>

</div>

<div>

## <a name="application-pool-mode"></a><span data-ttu-id="bbc4a-134">應用程式集區模式</span><span class="sxs-lookup"><span data-stu-id="bbc4a-134">Application Pool Mode</span></span>

<span data-ttu-id="bbc4a-135">設定 IIS，讓 CsManagementAppPool 應用程式集區使用網路服務帳戶做為其處理序模型身分識別。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-135">Configure IIS so that the CsManagementAppPool application pool uses the Network Service account as its process model identity.</span></span>

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a><span data-ttu-id="bbc4a-136">使用者權限</span><span class="sxs-lookup"><span data-stu-id="bbc4a-136">User Rights and Permissions</span></span>

<span data-ttu-id="bbc4a-137">您必須登入 Lync Server Control Panel 使用網域帳戶屬於 CsAdministrator 群組的成員，或使用您已委派使用者權利和權限的帳戶。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-137">You must sign in to Lync Server Control Panel either by using a domain account that is a member of the CsAdministrator group or by using an account to which you have delegated user rights and permissions.</span></span> <span data-ttu-id="bbc4a-138">您無法使用本機電腦帳戶來登入 Lync Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-138">You cannot sign in to Lync Server Control Panel by using a local machine account.</span></span> <span data-ttu-id="bbc4a-139">如需有關委派系統管理工作，透過角色型存取控制 (RBAC) 的詳細資訊，請參閱規劃文件中的[Planning for Lync Server 2013 中角色型存取控制](lync-server-2013-planning-for-role-based-access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-139">For details about delegating administrative tasks through role-based access control (RBAC), see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="bbc4a-140">如果您使用簡單 URL 來存取 Lync Server Control Panel，確保伺服器已新增至 RTCUniversalServerAdmins 及 RTCUniversalUserAdmins 群組的網頁。</span><span class="sxs-lookup"><span data-stu-id="bbc4a-140">If you use a simple URL to access Lync Server Control Panel, ensure that web servers are added to the RTCUniversalServerAdmins and RTCUniversalUserAdmins groups.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bbc4a-141">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bbc4a-141">See Also</span></span>


[<span data-ttu-id="bbc4a-142">Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="bbc4a-142">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

