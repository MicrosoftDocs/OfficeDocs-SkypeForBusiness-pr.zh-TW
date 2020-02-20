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
ms.openlocfilehash: c39520a54ae664a1eddf241cbf1d8d27fe858510
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="get-csservice-for-address-book-management-in-lync-server-2013"></a>適用於通訊錄管理 Lync Server 2013 中的 get-CsService

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

誰可以執行這個 Cmdlet：根據預設，下列群組成員已獲得授權，可在本機執行 Get-CsService Cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。若要傳回指派給該 Cmdlet 的所有角色型存取控制 (RBAC) 角色清單 (包括您自己建立的任何自訂 RBAC 角色)，請在 Windows PowerShell 提示中輸入下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsService"}

Get-csservice 有價值來擷取並顯示您的基礎結構定義 Web 服務的目前設定。 在定義集區的完整網域名稱 (FQDN) 和參數 WebServer 後，此 Cmdlet 會傳回伺服器提供的 Web 服務，包括通訊錄處理常式和通訊群組清單延伸 URI。

例如：

    Get-CsService -PoolFqdn "fe01.contoso.net" -WebServer

此 Cmdlet 會傳回下列項目：

身分識別： Pool01.contoso.net

FileStore: Dc01.contoso.net

UserServer: UserServer:pool01.contoso.net

PrimaryHttpPort: 80

PrimaryHttpsPort: 443

ExternalHttpPort: 8080

ExternalHttpsPort: 4443

PublishedPrimaryHttpPort: 80

PublishedPrimaryHttpsPort: 443

PublishedExternalHttpPort: 80

PublishedExternalHttpsPort: 443

ReachPrimaryPsomServerPort: 8060

ReachExternalPsomServerPort: 8061

AppSharingPortStart: 49152

AppSharingPortCount: 16383

LIServiceInternalUri:https://internalweb.contoso.net/locationinformation/liservice.svc

ABHandlerInternalUri:https://internalweb.contoso.net/abs/handler

ABHandlerExternalUri:https://csweb.contoso.com/abs/handler

DLExpansionInternalUri:https://internalweb.contoso.net/groupexpansion/service.svc

DLExpansionExternalUri:https://csweb.contoso.com/groupexpansion/service.svc

CAHandlerInternalUri:https://internalweb.contoso.net/CertProv/CertProvisioningService.svc

CAHandlerInternalAnonUri:http://internalweb.contoso.net/CertProv/CertProvisioningService.svc

CollabContentInternalUri:https://internalweb.contoso.net/CollabContent

CollabContentExternalUri:https://csweb.contoso.com/CollabContent

CAHandlerExternalUri:https://csweb.contoso.com/CertProv/CertProvisioningService.svc

DeviceUpdateDownloadInternalUri:https://internalweb.contoso.net/RequestHandler/ucdevice.upx

DeviceUpdateDownloadExternalUri:https://csweb.contoso.com/RequestHandlerExt/ucdevice.upx

DeviceUpdateStoreInternalUri:http://internalweb.contoso.net/RequestHandler/Files

DeviceUpdateStoreExternalUri:https://csweb.contoso.com/RequestHandlerExt/Files

RgsAgentServiceInternalUri:https://internalweb.contoso.net/RgsClients/AgentService.svc

RgsAgentServiceExternalUri:https://csweb.contoso.com/RgsClients/AgentService.svc

MeetExternalUri:https://csweb.contoso.com/Meet

DialinExternalUri:https://csweb.contoso.com/Dialin

CscpInternalUri:https://internalweb.contoso.net/Cscp

ReachExternalUri:https://csweb.contoso.com/Reach

ReachInternalUri:https://internalweb.contoso.net/Reach

WebTicketExternalUri:https://csweb.contoso.com/WebTicket/WebTicketService.svc

WebTicketInternalUri:https://internalweb.contoso.net/WebTicket/WebTicketService.svc

ExternalFqdn: csweb.contoso.com

InternalFqdn: internalweb.contoso.net

DependentServiceList: {Registrar: pool01.contoso.net，conferencingserver: Pool01.contoso.net}

ServiceId: 1-WebServices-1

SiteId: Site: Redmond

PoolFqdn: pool01.contoso.net

版： 5

Role: WebServer

<div>

## <a name="see-also"></a>另請參閱


[Get-csservice](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

