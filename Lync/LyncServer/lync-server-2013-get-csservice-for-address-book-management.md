---
title: Lync Server 2013：針對通訊錄管理取得 CsService
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Get-CsService for Address Book management
ms:assetid: 373b717d-5efa-4c36-a899-a23a5bd922b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429698(v=OCS.15)
ms:contentKeyID: 48183853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 656c1aa545a1f10e49c5ff60b51c20386854d146
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="8e581-102">在 Lync Server 2013 中取得通訊錄管理的 CsService</span><span class="sxs-lookup"><span data-stu-id="8e581-102">Get-CsService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e581-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8e581-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8e581-104">誰可以執行這個 Cmdlet：根據預設，下列群組的成員有權在本機執行 CsService Cmdlet： RTCUniversalUserAdmins、RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="8e581-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span> <span data-ttu-id="8e581-105">若要傳回已指派這個 Cmdlet 的所有角色式存取控制（RBAC）角色的清單（包括您自行建立的任何自訂 RBAC 角色），請在 Windows PowerShell 提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="8e581-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="8e581-106">CsService 可讓您檢索並顯示基礎結構已定義 Web 服務的目前設定。</span><span class="sxs-lookup"><span data-stu-id="8e581-106">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="8e581-107">透過定義池子的完整功能變數名稱（FQDN）和參數 Web 服務，此 Cmdlet 會傳回您伺服器所提供的 web 服務，包括通訊錄處理常式和通訊群組清單展開 Uri。</span><span class="sxs-lookup"><span data-stu-id="8e581-107">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="8e581-108">例如：</span><span class="sxs-lookup"><span data-stu-id="8e581-108">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="8e581-109">這個 Cmdlet 會傳回下列內容：</span><span class="sxs-lookup"><span data-stu-id="8e581-109">This cmdlet returns the following:</span></span>

<span data-ttu-id="8e581-110">身分識別： Web:pool01</span><span class="sxs-lookup"><span data-stu-id="8e581-110">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="8e581-111">:Dc01：</span><span class="sxs-lookup"><span data-stu-id="8e581-111">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="8e581-112">UserServer： UserServer:pool01</span><span class="sxs-lookup"><span data-stu-id="8e581-112">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="8e581-113">PrimaryHttpPort：80</span><span class="sxs-lookup"><span data-stu-id="8e581-113">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="8e581-114">PrimaryHttpsPort：443</span><span class="sxs-lookup"><span data-stu-id="8e581-114">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="8e581-115">ExternalHttpPort：8080</span><span class="sxs-lookup"><span data-stu-id="8e581-115">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="8e581-116">ExternalHttpsPort：4443</span><span class="sxs-lookup"><span data-stu-id="8e581-116">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="8e581-117">PublishedPrimaryHttpPort：80</span><span class="sxs-lookup"><span data-stu-id="8e581-117">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="8e581-118">PublishedPrimaryHttpsPort：443</span><span class="sxs-lookup"><span data-stu-id="8e581-118">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="8e581-119">PublishedExternalHttpPort：80</span><span class="sxs-lookup"><span data-stu-id="8e581-119">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="8e581-120">PublishedExternalHttpsPort：443</span><span class="sxs-lookup"><span data-stu-id="8e581-120">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="8e581-121">ReachPrimaryPsomServerPort：8060</span><span class="sxs-lookup"><span data-stu-id="8e581-121">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="8e581-122">ReachExternalPsomServerPort：8061</span><span class="sxs-lookup"><span data-stu-id="8e581-122">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="8e581-123">AppSharingPortStart：49152</span><span class="sxs-lookup"><span data-stu-id="8e581-123">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="8e581-124">AppSharingPortCount：16383</span><span class="sxs-lookup"><span data-stu-id="8e581-124">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="8e581-125">LIServiceInternalUri :https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="8e581-125">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="8e581-126">ABHandlerInternalUri :https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="8e581-126">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="8e581-127">ABHandlerExternalUri :https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="8e581-127">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="8e581-128">DLExpansionInternalUri :https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="8e581-128">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="8e581-129">DLExpansionExternalUri :https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="8e581-129">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="8e581-130">CAHandlerInternalUri :https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="8e581-130">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="8e581-131">CAHandlerInternalAnonUri :http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="8e581-131">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="8e581-132">CollabContentInternalUri :https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="8e581-132">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="8e581-133">CollabContentExternalUri :https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="8e581-133">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="8e581-134">CAHandlerExternalUri :https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="8e581-134">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="8e581-135">DeviceUpdateDownloadInternalUri :https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="8e581-135">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="8e581-136">DeviceUpdateDownloadExternalUri :https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="8e581-136">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="8e581-137">DeviceUpdateStoreInternalUri :http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="8e581-137">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="8e581-138">DeviceUpdateStoreExternalUri :https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="8e581-138">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="8e581-139">RgsAgentServiceInternalUri :https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="8e581-139">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="8e581-140">RgsAgentServiceExternalUri :https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="8e581-140">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="8e581-141">MeetExternalUri :https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="8e581-141">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="8e581-142">DialinExternalUri :https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="8e581-142">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="8e581-143">CscpInternalUri :https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="8e581-143">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="8e581-144">ReachExternalUri :https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="8e581-144">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="8e581-145">ReachInternalUri :https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="8e581-145">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="8e581-146">WebTicketExternalUri :https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="8e581-146">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="8e581-147">WebTicketInternalUri :https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="8e581-147">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="8e581-148">ExternalFqdn： csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e581-148">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="8e581-149">InternalFqdn： internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8e581-149">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="8e581-150">DependentServiceList： {註冊機構:pool01. net.tcp. ConferencingServer:pool01。</span><span class="sxs-lookup"><span data-stu-id="8e581-150">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="8e581-151">ServiceId： 1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="8e581-151">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="8e581-152">SiteId：網站：雷蒙德</span><span class="sxs-lookup"><span data-stu-id="8e581-152">SiteId : Site:Redmond</span></span>

<span data-ttu-id="8e581-153">PoolFqdn： pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8e581-153">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="8e581-154">版本：5</span><span class="sxs-lookup"><span data-stu-id="8e581-154">Version : 5</span></span>

<span data-ttu-id="8e581-155">Role： Web</span><span class="sxs-lookup"><span data-stu-id="8e581-155">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8e581-156">請參閱</span><span class="sxs-lookup"><span data-stu-id="8e581-156">See Also</span></span>


[<span data-ttu-id="8e581-157">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="8e581-157">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

