---
title: Lync Server 2013：用於通訊錄管理的 Get-CsService
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
ms.openlocfilehash: 43c2c6ada55c1bc7db6c8593ee14028b986a2b78
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512620"
---
# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="3100a-102">Lync Server 2013 中用於通訊錄管理的 Get-CsService</span><span class="sxs-lookup"><span data-stu-id="3100a-102">Get-CsService for Address Book management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3100a-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3100a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3100a-p101">誰可以執行這個 Cmdlet：根據預設，下列群組成員已獲得授權，可在本機執行 Get-CsService Cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。若要傳回指派給該 Cmdlet 的所有角色型存取控制 (RBAC) 角色清單 (包括您自己建立的任何自訂 RBAC 角色)，請在 Windows PowerShell 提示中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="3100a-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="3100a-106">Get-CsService 非常有用，可找回及顯示基礎結構定義的 Web 服務目前的設定。</span><span class="sxs-lookup"><span data-stu-id="3100a-106">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="3100a-107">在定義集區的完整網域名稱 (FQDN) 和參數 WebServer 後，此 Cmdlet 會傳回伺服器提供的 Web 服務，包括通訊錄處理常式和通訊群組清單延伸 URI。</span><span class="sxs-lookup"><span data-stu-id="3100a-107">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="3100a-108">例如：</span><span class="sxs-lookup"><span data-stu-id="3100a-108">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="3100a-109">此 Cmdlet 會傳回下列項目：</span><span class="sxs-lookup"><span data-stu-id="3100a-109">This cmdlet returns the following:</span></span>

<span data-ttu-id="3100a-110">Identity： WebServer:pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="3100a-110">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="3100a-111">FileStore： FileStore:dc01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="3100a-111">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="3100a-112">UserServer： UserServer:pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="3100a-112">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="3100a-113">PrimaryHttpPort：80</span><span class="sxs-lookup"><span data-stu-id="3100a-113">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="3100a-114">PrimaryHttpsPort：443</span><span class="sxs-lookup"><span data-stu-id="3100a-114">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="3100a-115">ExternalHttpPort：8080</span><span class="sxs-lookup"><span data-stu-id="3100a-115">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="3100a-116">ExternalHttpsPort：4443</span><span class="sxs-lookup"><span data-stu-id="3100a-116">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="3100a-117">PublishedPrimaryHttpPort：80</span><span class="sxs-lookup"><span data-stu-id="3100a-117">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="3100a-118">PublishedPrimaryHttpsPort：443</span><span class="sxs-lookup"><span data-stu-id="3100a-118">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="3100a-119">PublishedExternalHttpPort：80</span><span class="sxs-lookup"><span data-stu-id="3100a-119">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="3100a-120">PublishedExternalHttpsPort：443</span><span class="sxs-lookup"><span data-stu-id="3100a-120">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="3100a-121">ReachPrimaryPsomServerPort：8060</span><span class="sxs-lookup"><span data-stu-id="3100a-121">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="3100a-122">ReachExternalPsomServerPort：8061</span><span class="sxs-lookup"><span data-stu-id="3100a-122">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="3100a-123">AppSharingPortStart：49152</span><span class="sxs-lookup"><span data-stu-id="3100a-123">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="3100a-124">AppSharingPortCount：16383</span><span class="sxs-lookup"><span data-stu-id="3100a-124">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="3100a-125">LIServiceInternalUri： https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="3100a-125">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="3100a-126">ABHandlerInternalUri： https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="3100a-126">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="3100a-127">ABHandlerExternalUri： https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="3100a-127">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="3100a-128">DLExpansionInternalUri： https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="3100a-128">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="3100a-129">DLExpansionExternalUri： https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="3100a-129">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="3100a-130">CAHandlerInternalUri： https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="3100a-130">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="3100a-131">CAHandlerInternalAnonUri： http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="3100a-131">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="3100a-132">CollabContentInternalUri： https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="3100a-132">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="3100a-133">CollabContentExternalUri： https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="3100a-133">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="3100a-134">CAHandlerExternalUri： https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="3100a-134">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="3100a-135">DeviceUpdateDownloadInternalUri： https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="3100a-135">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="3100a-136">DeviceUpdateDownloadExternalUri： https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="3100a-136">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="3100a-137">DeviceUpdateStoreInternalUri： http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="3100a-137">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="3100a-138">DeviceUpdateStoreExternalUri： https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="3100a-138">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="3100a-139">RgsAgentServiceInternalUri： https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="3100a-139">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="3100a-140">RgsAgentServiceExternalUri： https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="3100a-140">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="3100a-141">MeetExternalUri： https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="3100a-141">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="3100a-142">DialinExternalUri： https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="3100a-142">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="3100a-143">CscpInternalUri： https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="3100a-143">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="3100a-144">ReachExternalUri： https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="3100a-144">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="3100a-145">ReachInternalUri： https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="3100a-145">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="3100a-146">WebTicketExternalUri： https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="3100a-146">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="3100a-147">WebTicketInternalUri： https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="3100a-147">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="3100a-148">ExternalFqdn： csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3100a-148">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="3100a-149">InternalFqdn： internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="3100a-149">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="3100a-150">DependentServiceList： {註冊機構: pool01.contoso.net，ConferencingServer:pool01.contoso.net}</span><span class="sxs-lookup"><span data-stu-id="3100a-150">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="3100a-151">ServiceId：1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="3100a-151">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="3100a-152">SiteId： Site:Redmond</span><span class="sxs-lookup"><span data-stu-id="3100a-152">SiteId : Site:Redmond</span></span>

<span data-ttu-id="3100a-153">PoolFqdn： pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="3100a-153">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="3100a-154">版本：5</span><span class="sxs-lookup"><span data-stu-id="3100a-154">Version : 5</span></span>

<span data-ttu-id="3100a-155">Role： WebServer</span><span class="sxs-lookup"><span data-stu-id="3100a-155">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="3100a-156">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3100a-156">See Also</span></span>


[<span data-ttu-id="3100a-157">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="3100a-157">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

