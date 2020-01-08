---
title: Lync Server 2013：針對通訊錄管理取得 CsService
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Get-CsService for Address Book management
ms:assetid: 373b717d-5efa-4c36-a899-a23a5bd922b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429698(v=OCS.15)
ms:contentKeyID: 48183853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cfa9bd42bb29ca32ab27dc64d2ee9a111abab8d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a>在 Lync Server 2013 中取得通訊錄管理的 CsService

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

誰可以執行這個 Cmdlet：根據預設，下列群組的成員有權在本機執行 CsService Cmdlet： RTCUniversalUserAdmins、RTCUniversalServerAdmins。 若要傳回已指派這個 Cmdlet 的所有角色式存取控制（RBAC）角色的清單（包括您自行建立的任何自訂 RBAC 角色），請在 Windows PowerShell 提示中執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

CsService 可讓您檢索並顯示基礎結構已定義 Web 服務的目前設定。 透過定義池子的完整功能變數名稱（FQDN）和參數 Web 服務，此 Cmdlet 會傳回您伺服器所提供的 web 服務，包括通訊錄處理常式和通訊群組清單展開 Uri。

例如：

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

這個 Cmdlet 會傳回下列內容：

身分識別： Web:pool01

:Dc01：

UserServer： UserServer:pool01

PrimaryHttpPort：80

PrimaryHttpsPort：443

ExternalHttpPort：8080

ExternalHttpsPort：4443

PublishedPrimaryHttpPort：80

PublishedPrimaryHttpsPort：443

PublishedExternalHttpPort：80

PublishedExternalHttpsPort：443

ReachPrimaryPsomServerPort：8060

ReachExternalPsomServerPort：8061

AppSharingPortStart：49152

AppSharingPortCount：16383

LIServiceInternalUri :https://internalweb.contoso.net/locationinformation/liservice.svc

ABHandlerInternalUri :https://internalweb.contoso.net/abs/handler

ABHandlerExternalUri :https://csweb.contoso.com/abs/handler

DLExpansionInternalUri :https://internalweb.contoso.net/groupexpansion/service.svc

DLExpansionExternalUri :https://csweb.contoso.com/groupexpansion/service.svc

CAHandlerInternalUri :https://internalweb.contoso.net/CertProv/CertProvisioningService.svc

CAHandlerInternalAnonUri :http://internalweb.contoso.net/CertProv/CertProvisioningService.svc

CollabContentInternalUri :https://internalweb.contoso.net/CollabContent

CollabContentExternalUri :https://csweb.contoso.com/CollabContent

CAHandlerExternalUri :https://csweb.contoso.com/CertProv/CertProvisioningService.svc

DeviceUpdateDownloadInternalUri :https://internalweb.contoso.net/RequestHandler/ucdevice.upx

DeviceUpdateDownloadExternalUri :https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx

DeviceUpdateStoreInternalUri :http://internalweb.contoso.net/RequestHandler/Files

DeviceUpdateStoreExternalUri :https://csweb.contoso.com/RequestHandlerExt/Files

RgsAgentServiceInternalUri :https://internalweb.contoso.net/RgsClients/AgentService.svc

RgsAgentServiceExternalUri :https://csweb.contoso.com/RgsClients/AgentService.svc

MeetExternalUri :https://csweb.contoso.com/Meet

DialinExternalUri :https://csweb.contoso.com/Dialin

CscpInternalUri :https://internalweb.contoso.net/Cscp

ReachExternalUri :https://csweb.contoso.com/Reach

ReachInternalUri :https://internalweb.contoso.net/Reach

WebTicketExternalUri :https://csweb.contoso.com/WebTicket/WebTicketService.svc

WebTicketInternalUri :https://internalweb.contoso.net/WebTicket/WebTicketService.svc

ExternalFqdn： csweb.contoso.com

InternalFqdn： internalweb.contoso.net

DependentServiceList： {註冊機構:pool01. net.tcp. ConferencingServer:pool01。

ServiceId： 1-WebServices-1

SiteId：網站：雷蒙德

PoolFqdn： pool01.contoso.net

版本：5

Role： Web

<div>

## <a name="see-also"></a>請參閱


[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

