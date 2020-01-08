---
title: Lync Server 2013：回應群組的部署程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2151532b31f3c1660be98d11ac9d9c337ffecb64
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a>Lync Server 2013 中的回應群組部署程式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-27_

本節概要說明部署回應群組應用程式時所涉及的階段和步驟。

### <a name="response-group-deployment-process"></a>回應群組部署程式

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>分</th>
<th>步驟</th>
<th>許可權</th>
<th>部署檔</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>安裝回應群組應用程式</p></td>
<td><p>當您部署企業語音時，系統會預設安裝並啟用回應群組應用程式。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">在 Lync Server 2013 中部署企業版語音</a></p></td>
</tr>
<tr class="even">
<td><p>安裝回應群組元件</p></td>
<td><p>Lync Server Cmdlet、Lync Server [控制台]、[回應群組設定] 工具、[代理程式登入與登出主控台]，以及回應群組用戶端 Web 服務已安裝為 Web 服務的一部分。 當您部署企業版文件庫或標準版伺服器時，就會安裝 Web 服務。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>允許使用者使用 Lync 2013 和企業語音</p></td>
<td><p>啟用將是 Lync Server 和企業語音的使用者。 您必須先啟用使用者，才能將其新增至代理群組。 通常，在企業版或標準版伺服器部署期間，會啟用 Lync Server 的使用者。 在企業語音部署期間，系統會為使用者啟用企業語音。</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">停用或重新啟用 Lync Server 2013 的使用者帳戶</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">在 Lync Server 2013 中啟用企業語音的使用者</a></p></td>
</tr>
<tr class="even">
<td><p>建立及設定回應群組，包括代理群組、佇列和工作流程</p></td>
<td><ol>
<li><p>使用 Lync Server [控制台] 或 [Lync Server 管理命令介面] 執行下列動作：</p>
<ol>
<li><p>建立及設定代理群組。</p></li>
<li><p>建立及設定佇列。</p></li>
</ol></li>
<li><p>或者，您也可以使用 Lync Server 管理命令介面來建立預先定義的回應群組商務時數和假日。</p></li>
<li><p>使用 [回應群組設定] 工具或 [Lync Server 管理命令介面] 來建立工作流程（查尋群組或互動式語音回應（IVR）通話流程），包括自訂回應群組的商務時數和假日。</p>
<div>

> [!NOTE]  
> 您可以透過 [Lync Server 控制台] 存取 [回應群組設定] 工具。


</div></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsResponseGroupManager</p></td>
<td><p><a href="lync-server-2013-create-response-group-agent-groups.md">在 Lync Server 2013 中建立回應群組代理群組</a></p>
<p><a href="lync-server-2013-create-response-group-queues.md">在 Lync Server 2013 中建立回應群組佇列</a></p>
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">可選在 Lync Server 2013 中定義回應群組的上班時間</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">可選在 Lync Server 2013 中定義回應群組假日集</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">在 Lync Server 2013 中建立或修改工作流程</a></p></td>
</tr>
<tr class="odd">
<td><p>可選自訂應用程式層級設定</p></td>
<td><p>您可以使用 Lync Server 管理命令介面來自訂預設的音樂保留式設定、預設的音樂保留音訊檔案、代理 ringback 寬限期，以及通話內容配置。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">管理 Lync Server 2013 中的應用層級回應群組設定</a></p></td>
</tr>
<tr class="even">
<td><p>可選委派對回應群組的管理</p></td>
<td><p>指派使用者的 CsResponseGroupManager 角色來委派回應群組的設定。 回應群組管理員可以設定指派給他們的回應群組。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-planning-for-role-based-access-control.md">在 Lync Server 2013 中規劃角色型存取控制</a></p></td>
</tr>
<tr class="odd">
<td><p>驗證您的回應群組部署</p></td>
<td><p>測試對您的查尋群組和互動式語音回應工作流程的通話回應，以確保您的設定如預期的那樣正常運作。</p></td>
<td><p>-</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

