---
title: 'Lync Server 2013: Get-CsService 適用於通訊錄管理'
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
ms.openlocfilehash: 8a9e8be425a86eef0d548493e1466888d3d8728c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="0ac8f-102">適用於通訊錄管理 Lync Server 2013 中的 get-CsService</span><span class="sxs-lookup"><span data-stu-id="0ac8f-102">Get-CsService for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ac8f-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="0ac8f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0ac8f-p101">誰可以執行這個 Cmdlet：根據預設，下列群組成員已獲得授權，可在本機執行 Get-CsService Cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。若要傳回指派給該 Cmdlet 的所有角色型存取控制 (RBAC) 角色清單 (包括您自己建立的任何自訂 RBAC 角色)，請在 Windows PowerShell 提示中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="0ac8f-p101">Who can run this cmdlet: By default, members of the following groups are authorized to run the Get-CsService cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

<span data-ttu-id="0ac8f-106">Get-csservice 有價值來擷取並顯示您的基礎結構定義 Web 服務的目前設定。</span><span class="sxs-lookup"><span data-stu-id="0ac8f-106">Get-CsService is valuable to retrieve and display the current configuration of your infrastructure’s defined Web Services.</span></span> <span data-ttu-id="0ac8f-107">在定義集區的完整網域名稱 (FQDN) 和參數 WebServer 後，此 Cmdlet 會傳回伺服器提供的 Web 服務，包括通訊錄處理常式和通訊群組清單延伸 URI。</span><span class="sxs-lookup"><span data-stu-id="0ac8f-107">By defining the pool’s fully qualified domain name (FQDN) and the parameter WebServer, the cmdlet returns the web-based services offered by your server, including the Address Book handler and distribution list expansion URIs.</span></span>

<span data-ttu-id="0ac8f-108">例如：</span><span class="sxs-lookup"><span data-stu-id="0ac8f-108">For example:</span></span>

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

<span data-ttu-id="0ac8f-109">此 Cmdlet 會傳回下列項目：</span><span class="sxs-lookup"><span data-stu-id="0ac8f-109">This cmdlet returns the following:</span></span>

<span data-ttu-id="0ac8f-110">身分識別： Pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0ac8f-110">Identity : WebServer:pool01.contoso.net</span></span>

<span data-ttu-id="0ac8f-111">FileStore: Dc01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0ac8f-111">FileStore : FileStore:dc01.contoso.net</span></span>

<span data-ttu-id="0ac8f-112">UserServer: UserServer:pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0ac8f-112">UserServer : UserServer:pool01.contoso.net</span></span>

<span data-ttu-id="0ac8f-113">PrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="0ac8f-113">PrimaryHttpPort : 80</span></span>

<span data-ttu-id="0ac8f-114">PrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="0ac8f-114">PrimaryHttpsPort : 443</span></span>

<span data-ttu-id="0ac8f-115">ExternalHttpPort: 8080</span><span class="sxs-lookup"><span data-stu-id="0ac8f-115">ExternalHttpPort : 8080</span></span>

<span data-ttu-id="0ac8f-116">ExternalHttpsPort: 4443</span><span class="sxs-lookup"><span data-stu-id="0ac8f-116">ExternalHttpsPort : 4443</span></span>

<span data-ttu-id="0ac8f-117">PublishedPrimaryHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="0ac8f-117">PublishedPrimaryHttpPort : 80</span></span>

<span data-ttu-id="0ac8f-118">PublishedPrimaryHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="0ac8f-118">PublishedPrimaryHttpsPort : 443</span></span>

<span data-ttu-id="0ac8f-119">PublishedExternalHttpPort: 80</span><span class="sxs-lookup"><span data-stu-id="0ac8f-119">PublishedExternalHttpPort : 80</span></span>

<span data-ttu-id="0ac8f-120">PublishedExternalHttpsPort: 443</span><span class="sxs-lookup"><span data-stu-id="0ac8f-120">PublishedExternalHttpsPort : 443</span></span>

<span data-ttu-id="0ac8f-121">ReachPrimaryPsomServerPort: 8060</span><span class="sxs-lookup"><span data-stu-id="0ac8f-121">ReachPrimaryPsomServerPort : 8060</span></span>

<span data-ttu-id="0ac8f-122">ReachExternalPsomServerPort: 8061</span><span class="sxs-lookup"><span data-stu-id="0ac8f-122">ReachExternalPsomServerPort : 8061</span></span>

<span data-ttu-id="0ac8f-123">AppSharingPortStart: 49152</span><span class="sxs-lookup"><span data-stu-id="0ac8f-123">AppSharingPortStart : 49152</span></span>

<span data-ttu-id="0ac8f-124">AppSharingPortCount: 16383</span><span class="sxs-lookup"><span data-stu-id="0ac8f-124">AppSharingPortCount : 16383</span></span>

<span data-ttu-id="0ac8f-125">LIServiceInternalUri:https://internalweb.contoso.net/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="0ac8f-125">LIServiceInternalUri : https://internalweb.contoso.net/locationinformation/liservice.svc</span></span>

<span data-ttu-id="0ac8f-126">ABHandlerInternalUri:https://internalweb.contoso.net/abs/handler</span><span class="sxs-lookup"><span data-stu-id="0ac8f-126">ABHandlerInternalUri : https://internalweb.contoso.net/abs/handler</span></span>

<span data-ttu-id="0ac8f-127">ABHandlerExternalUri:https://csweb.contoso.com/abs/handler</span><span class="sxs-lookup"><span data-stu-id="0ac8f-127">ABHandlerExternalUri : https://csweb.contoso.com/abs/handler</span></span>

<span data-ttu-id="0ac8f-128">DLExpansionInternalUri:https://internalweb.contoso.net/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="0ac8f-128">DLExpansionInternalUri : https://internalweb.contoso.net/groupexpansion/service.svc</span></span>

<span data-ttu-id="0ac8f-129">DLExpansionExternalUri:https://csweb.contoso.com/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="0ac8f-129">DLExpansionExternalUri : https://csweb.contoso.com/groupexpansion/service.svc</span></span>

<span data-ttu-id="0ac8f-130">CAHandlerInternalUri:https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="0ac8f-130">CAHandlerInternalUri : https://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="0ac8f-131">CAHandlerInternalAnonUri:http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="0ac8f-131">CAHandlerInternalAnonUri : http://internalweb.contoso.net/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="0ac8f-132">CollabContentInternalUri:https://internalweb.contoso.net/CollabContent</span><span class="sxs-lookup"><span data-stu-id="0ac8f-132">CollabContentInternalUri : https://internalweb.contoso.net/CollabContent</span></span>

<span data-ttu-id="0ac8f-133">CollabContentExternalUri:https://csweb.contoso.com/CollabContent</span><span class="sxs-lookup"><span data-stu-id="0ac8f-133">CollabContentExternalUri : https://csweb.contoso.com/CollabContent</span></span>

<span data-ttu-id="0ac8f-134">CAHandlerExternalUri:https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="0ac8f-134">CAHandlerExternalUri : https://csweb.contoso.com/CertProv/CertProvisioningService.svc</span></span>

<span data-ttu-id="0ac8f-135">DeviceUpdateDownloadInternalUri:https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="0ac8f-135">DeviceUpdateDownloadInternalUri : https://internalweb.contoso.net/RequestHandler/ucdevice.upx</span></span>

<span data-ttu-id="0ac8f-136">DeviceUpdateDownloadExternalUri:https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span><span class="sxs-lookup"><span data-stu-id="0ac8f-136">DeviceUpdateDownloadExternalUri : https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx</span></span>

<span data-ttu-id="0ac8f-137">DeviceUpdateStoreInternalUri:http://internalweb.contoso.net/RequestHandler/Files</span><span class="sxs-lookup"><span data-stu-id="0ac8f-137">DeviceUpdateStoreInternalUri : http://internalweb.contoso.net/RequestHandler/Files</span></span>

<span data-ttu-id="0ac8f-138">DeviceUpdateStoreExternalUri:https://csweb.contoso.com/RequestHandlerExt/Files</span><span class="sxs-lookup"><span data-stu-id="0ac8f-138">DeviceUpdateStoreExternalUri : https://csweb.contoso.com/RequestHandlerExt/Files</span></span>

<span data-ttu-id="0ac8f-139">RgsAgentServiceInternalUri:https://internalweb.contoso.net/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="0ac8f-139">RgsAgentServiceInternalUri : https://internalweb.contoso.net/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="0ac8f-140">RgsAgentServiceExternalUri:https://csweb.contoso.com/RgsClients/AgentService.svc</span><span class="sxs-lookup"><span data-stu-id="0ac8f-140">RgsAgentServiceExternalUri : https://csweb.contoso.com/RgsClients/AgentService.svc</span></span>

<span data-ttu-id="0ac8f-141">MeetExternalUri:https://csweb.contoso.com/Meet</span><span class="sxs-lookup"><span data-stu-id="0ac8f-141">MeetExternalUri : https://csweb.contoso.com/Meet</span></span>

<span data-ttu-id="0ac8f-142">DialinExternalUri:https://csweb.contoso.com/Dialin</span><span class="sxs-lookup"><span data-stu-id="0ac8f-142">DialinExternalUri : https://csweb.contoso.com/Dialin</span></span>

<span data-ttu-id="0ac8f-143">CscpInternalUri:https://internalweb.contoso.net/Cscp</span><span class="sxs-lookup"><span data-stu-id="0ac8f-143">CscpInternalUri : https://internalweb.contoso.net/Cscp</span></span>

<span data-ttu-id="0ac8f-144">ReachExternalUri:https://csweb.contoso.com/Reach</span><span class="sxs-lookup"><span data-stu-id="0ac8f-144">ReachExternalUri : https://csweb.contoso.com/Reach</span></span>

<span data-ttu-id="0ac8f-145">ReachInternalUri:https://internalweb.contoso.net/Reach</span><span class="sxs-lookup"><span data-stu-id="0ac8f-145">ReachInternalUri : https://internalweb.contoso.net/Reach</span></span>

<span data-ttu-id="0ac8f-146">WebTicketExternalUri:https://csweb.contoso.com/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="0ac8f-146">WebTicketExternalUri : https://csweb.contoso.com/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="0ac8f-147">WebTicketInternalUri:https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="0ac8f-147">WebTicketInternalUri : https://internalweb.contoso.net/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="0ac8f-148">ExternalFqdn: csweb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0ac8f-148">ExternalFqdn : csweb.contoso.com</span></span>

<span data-ttu-id="0ac8f-149">InternalFqdn: internalweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0ac8f-149">InternalFqdn : internalweb.contoso.net</span></span>

<span data-ttu-id="0ac8f-150">DependentServiceList: {Registrar: pool01.contoso.net，conferencingserver: Pool01.contoso.net}</span><span class="sxs-lookup"><span data-stu-id="0ac8f-150">DependentServiceList : {Registrar:pool01.contoso.net, ConferencingServer:pool01.contoso.net}</span></span>

<span data-ttu-id="0ac8f-151">ServiceId: 1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="0ac8f-151">ServiceId : 1-WebServices-1</span></span>

<span data-ttu-id="0ac8f-152">SiteId: Site: Redmond</span><span class="sxs-lookup"><span data-stu-id="0ac8f-152">SiteId : Site:Redmond</span></span>

<span data-ttu-id="0ac8f-153">PoolFqdn: pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="0ac8f-153">PoolFqdn : pool01.contoso.net</span></span>

<span data-ttu-id="0ac8f-154">版： 5</span><span class="sxs-lookup"><span data-stu-id="0ac8f-154">Version : 5</span></span>

<span data-ttu-id="0ac8f-155">Role: WebServer</span><span class="sxs-lookup"><span data-stu-id="0ac8f-155">Role : WebServer</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="0ac8f-156">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0ac8f-156">See Also</span></span>


[<span data-ttu-id="0ac8f-157">Get-csservice</span><span class="sxs-lookup"><span data-stu-id="0ac8f-157">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

