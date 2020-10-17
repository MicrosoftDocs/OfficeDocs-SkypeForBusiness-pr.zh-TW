---
title: Lync Server 2013： Lync Server 2013 控制台疑難排解
description: Lync Server 2013：對 Lync Server 2013 控制台進行疑難排解。
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
ms.openlocfilehash: 9c3559c26b7b0a8d715563665c4b9a57e5999156
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549019"
---
# <a name="troubleshooting-lync-server-2013-control-panel"></a><span data-ttu-id="d6f5a-103">疑難排解 Lync Server 2013 控制台</span><span class="sxs-lookup"><span data-stu-id="d6f5a-103">Troubleshooting Lync Server 2013 Control Panel</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6f5a-104">_**主題上次修改日期：** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="d6f5a-104">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="d6f5a-105">本主題提供的資訊和程式可協助您疑難排解 Lync Server 2013 控制台的存取。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-105">This topic provides information and procedures that can help you troubleshoot access to Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="internet-browser-requirements"></a><span data-ttu-id="d6f5a-106">網際網路瀏覽器需求</span><span class="sxs-lookup"><span data-stu-id="d6f5a-106">Internet Browser Requirements</span></span>

<span data-ttu-id="d6f5a-107">Lync Server 控制台要求安裝 Microsoft Silverlight 瀏覽器外掛程式版本4.0.50524.0 或最新版本。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-107">Lync Server Control Panel requires that Microsoft Silverlight browser plug-in version 4.0.50524.0 or latest version is installed.</span></span> <span data-ttu-id="d6f5a-108">若未安裝 Silverlight 或已安裝舊版，請依照訊息中的指示安裝必要的版本。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-108">If Silverlight is not installed or if an earlier version is installed, follow the instructions in the message to install the required version.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6f5a-109">Lync Server 控制台的其他軟體需求，適用于可安裝 Lync Server 控制台和所有其他 Lync Server 2013 系統管理工具的作業系統。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-109">Other software requirements for Lync Server Control Panel pertain to the operating system on which Lync Server Control Panel and all other Lync Server 2013 administrative tools can be installed.</span></span> <span data-ttu-id="d6f5a-110">如需詳細資訊，請參閱支援檔中的 <A href="lync-server-2013-server-and-tools-operating-system-support.md">伺服器和工具作業系統支援（Lync Server 2013</A> ）。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-110">For details, see <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="d6f5a-111">如果您的網際網路瀏覽器因安全性考慮而封鎖安裝 Silverlight，請將開啟 Lync Server 控制台的統一資源定位器 (URL) 新增至受信任的網站清單。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-111">If your Internet browser blocks installation of Silverlight due to security considerations, add the Uniform Resource Locator (URL) that opens Lync Server Control Panel to the list of trusted sites.</span></span> <span data-ttu-id="d6f5a-112">在 Internet Explorer 安全性設定中，確定 [執行 ActiveX 控制項及外掛程式]\*\*\*\* 設為 [已啟用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-112">In Internet Explorer security settings, ensure that **Run ActiveX controls and plug-ins** is set to **Enabled**.</span></span> <span data-ttu-id="d6f5a-113">如需詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060) 。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-113">For details, see [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060).</span></span> <span data-ttu-id="d6f5a-114">此外，請確定瀏覽器設定為使用 SSL 3.0。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-114">Furthermore, ensure that the browser is configured to use SSL 3.0.</span></span>

<span data-ttu-id="d6f5a-p104">如果網際網路瀏覽器設定為使用 Proxy 伺服器，請確認瀏覽器針對自動偵測為內部站台的站台，設定為略過 Proxy 伺服器。或者，在 Proxy 伺服器組態設定中，將位址新增至瀏覽器的例外清單。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-p104">If the Internet browser is configured to use a proxy server, verify that the browser is configured to bypass the proxy server for sites that are automatically detected as internal sites. Or, add the address to the browser's exception list in the proxy server configuration settings.</span></span>

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a><span data-ttu-id="d6f5a-117">系統管理存取 URL 的 DNS 記錄及憑證需求</span><span class="sxs-lookup"><span data-stu-id="d6f5a-117">DNS Record and Certificate Requirements for the Administrative Access URL</span></span>

<span data-ttu-id="d6f5a-118">如果您設定了簡易 URL 來存取 Lync Server 控制台，請確定您也已設定靜態網域名稱系統 (DNS) 主機 (使用該管理存取 URL 所需的) 資源記錄和憑證。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-118">If you configured a simple URL to access Lync Server Control Panel, ensure that you also configured the static Domain Name System (DNS) host (A) resource record and certificate necessary to use that administrative access URL.</span></span> <span data-ttu-id="d6f5a-119">如果您隨時變更基底 URL，請確定變更會反映在適當的 DNS 記錄和憑證中，並且在每個 Director 和前端伺服器上執行 *Enable-CsComputer* 以登錄變更。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-119">If you change the base URL at any time, ensure that the change is reflected in the appropriate DNS record and certificate and that you run the *Enable-CsComputer* on each Director and Front End Server to register the change.</span></span> <span data-ttu-id="d6f5a-120">如需詳細資訊，請參閱＜規劃＞文件中的下列主題：</span><span class="sxs-lookup"><span data-stu-id="d6f5a-120">For details, see the following topics in the Planning documentation:</span></span>

  - [<span data-ttu-id="d6f5a-121">在 Lync Server 2013 中規劃簡易 URLs</span><span class="sxs-lookup"><span data-stu-id="d6f5a-121">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)

  - [<span data-ttu-id="d6f5a-122">Lync Server 2013 中簡易 URLs 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="d6f5a-122">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="d6f5a-123">Lync Server 2013 中內部伺服器的憑證需求</span><span class="sxs-lookup"><span data-stu-id="d6f5a-123">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

<span data-ttu-id="d6f5a-124">如需設定管理存取 URL 的逐步程式，請參閱部署檔中的在 [Lync Server 2013 中編輯或設定簡單 URLs](lync-server-2013-edit-or-configure-simple-urls.md) 。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-124">For step-by-step procedures to configure the administrative access URL, see [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="d6f5a-125">Internet Information Services (IIS) 需求</span><span class="sxs-lookup"><span data-stu-id="d6f5a-125">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="d6f5a-126">Lync Server 控制台是 Lync Server 2013 的其中一個元件，需要 Internet Information Services (IIS) 。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-126">Lync Server Control Panel is one of the components of Lync Server 2013 that requires Internet Information Services (IIS).</span></span> <span data-ttu-id="d6f5a-127">特別是，請確定 HTTP 重新導向和 Windows 驗證功能已啟用，而且 World Wide Web Publishing 服務 (W3SVC) 正在執行。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-127">In particular, ensure that HTTP redirection and Windows authentication features are enabled, and that the World Wide Web Publishing Service (W3SVC) is running.</span></span>

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a><span data-ttu-id="d6f5a-128">World Wide Publishing Service (Windows 服務) 相依性</span><span class="sxs-lookup"><span data-stu-id="d6f5a-128">World Wide Publishing Service (Windows Service) Dependency</span></span>

<span data-ttu-id="d6f5a-129">停止 World Wide Web 發佈服務後，就無法存取 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-129">When the World Wide Web Publishing Service is stopped, you cannot access Lync Server Control Panel.</span></span> <span data-ttu-id="d6f5a-130">您可以使用 Windows Services Microsoft Management Console (MMC) 來重新啟動服務。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-130">You can restart the service by using the Windows Services Microsoft Management Console (MMC).</span></span>

<span data-ttu-id="d6f5a-131">**啟動 World Wide Web Publishing 服務**</span><span class="sxs-lookup"><span data-stu-id="d6f5a-131">**To start the World Wide Web Publishing Service**</span></span>

1.  <span data-ttu-id="d6f5a-132">以網際網路資訊服務 (IIS) 的一部分，登入安裝 World Wide Web 發佈服務的電腦。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-132">Log on to the computer where the World Wide Web Publishing Service is installed as part of Internet Information Services (IIS).</span></span>

2.  <span data-ttu-id="d6f5a-133">依序按一下 [開始]\*\*\*\*、[系統管理工具]\*\*\*\* 和 [服務]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-133">Click **Start**, click **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="d6f5a-134">用滑鼠右鍵按一下 [World Wide Web Publishing 服務]\*\*\*\*，然後按一下 [啟動]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-134">Right-click **World Wide Web Publishing Service**, and then click **Start**.</span></span>

</div>

<div>

## <a name="application-pool-mode"></a><span data-ttu-id="d6f5a-135">應用程式集區模式</span><span class="sxs-lookup"><span data-stu-id="d6f5a-135">Application Pool Mode</span></span>

<span data-ttu-id="d6f5a-136">設定 IIS，讓 CsManagementAppPool 應用程式集區使用網路服務帳戶做為其處理序模型身分識別。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-136">Configure IIS so that the CsManagementAppPool application pool uses the Network Service account as its process model identity.</span></span>

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a><span data-ttu-id="d6f5a-137">使用者權限</span><span class="sxs-lookup"><span data-stu-id="d6f5a-137">User Rights and Permissions</span></span>

<span data-ttu-id="d6f5a-138">您必須使用屬於 CsAdministrator 群組成員的網域帳戶，或是使用已委派使用者權限的帳戶，登入 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-138">You must sign in to Lync Server Control Panel either by using a domain account that is a member of the CsAdministrator group or by using an account to which you have delegated user rights and permissions.</span></span> <span data-ttu-id="d6f5a-139">您無法使用本機電腦帳戶登入 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-139">You cannot sign in to Lync Server Control Panel by using a local machine account.</span></span> <span data-ttu-id="d6f5a-140">如需透過以角色為基礎的存取控制委派系統管理工作的詳細資訊 (RBAC) ，請參閱規劃檔中的 [規劃 Lync Server 2013 中的角色型存取控制](lync-server-2013-planning-for-role-based-access-control.md) 。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-140">For details about delegating administrative tasks through role-based access control (RBAC), see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="d6f5a-141">如果您使用簡易 URL 來存取 Lync Server 控制台，請確定網頁伺服器已新增至 RTCUniversalServerAdmins 和 RTCUniversalUserAdmins 群組。</span><span class="sxs-lookup"><span data-stu-id="d6f5a-141">If you use a simple URL to access Lync Server Control Panel, ensure that web servers are added to the RTCUniversalServerAdmins and RTCUniversalUserAdmins groups.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d6f5a-142">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d6f5a-142">See Also</span></span>


[<span data-ttu-id="d6f5a-143">Lync Server 2013 系統管理工具</span><span class="sxs-lookup"><span data-stu-id="d6f5a-143">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

