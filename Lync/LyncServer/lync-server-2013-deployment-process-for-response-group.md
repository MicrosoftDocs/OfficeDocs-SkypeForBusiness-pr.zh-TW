---
title: Lync Server 2013：回應群組的部署程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54335e8f70753a77f937819f896135ec1fe67b93
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526890"
---
# <a name="deployment-process-for-response-group-in-lync-server-2013"></a>Lync Server 2013 中回應群組的部署程式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-27_

本節概述部署回應群組應用程式所需的階段和步驟。

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
<th>階段</th>
<th>步驟</th>
<th>權限</th>
<th>部署文件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>安裝回應群組應用程式</p></td>
<td><p>當您部署企業語音時，預設會安裝及啟用回應群組應用程式。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">在 Lync Server 2013 中部署企業語音</a></p></td>
</tr>
<tr class="even">
<td><p>安裝回應群組的元件</p></td>
<td><p>Lync Server Cmdlet、Lync Server 控制台、回應群組設定工具、代理程式的登入和登出主控台，以及回應群組用戶端 Web 服務會安裝為 Web 服務的一部分。 當您部署 Enterprise Edition 集區或 Standard Edition server 時，即會安裝 Web 服務。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>啟用使用者的 Lync 2013 和 Enterprise Voice</p></td>
<td><p>啟用將會成為 Lync Server 和 Enterprise Voice 之代理人的使用者。 您必須先啟用使用者，才能將其新增至代理人群組。 一般來說，在 Enterprise Edition 或 Standard Edition Server 部署期間會為 Lync Server 啟用使用者。 在企業語音部署期間，使用者已啟用 Enterprise Voice。</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">停用或重新啟用 Lync Server 2013 的使用者帳戶</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">在 Lync Server 2013 中啟用使用者的 Enterprise Voice</a></p></td>
</tr>
<tr class="even">
<td><p>建立和設定回應群組，包括代理群組、佇列和工作流程</p></td>
<td><ol>
<li><p>使用 Lync Server 控制台或 Lync Server 管理命令介面執行下列作業：</p>
<ol>
<li><p>建立和設定代理人群組。</p></li>
<li><p>建立和設定佇列。</p></li>
</ol></li>
<li><p>（選用）使用 Lync Server 管理命令介面來建立預先定義的回應群組上班時間與假日。</p></li>
<li><p>使用回應群組設定工具或 Lync Server 管理命令介面來建立工作流程 (群組搜尋或互動語音回應 (IVR) 通話流程) （包括自訂回應群組的上班時間和公休日）。</p>
<div>

> [!NOTE]  
> 您可以透過 Lync Server 控制台存取回應群組設定工具。


</div></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsResponseGroupManager</p></td>
<td><p><a href="lync-server-2013-create-response-group-agent-groups.md">建立回應群組代理群組 Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-response-group-queues.md">在 Lync Server 2013 中建立回應群組佇列</a></p>
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md"> (選用) 在 Lync Server 2013 中定義回應群組上班時間</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md"> (選用) 在 Lync Server 2013 中定義回應群組假日集</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">在 Lync Server 2013 中建立或修改工作流程</a></p></td>
</tr>
<tr class="odd">
<td><p> (選用) 自訂應用層級設定</p></td>
<td><p>使用 Lync Server 管理命令介面，來自訂預設的等候音樂設定、預設的等候音樂音訊檔、代理程式回電寬限期，以及呼叫內容設定。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">在 Lync Server 2013 中管理應用層級回應群組設定</a></p></td>
</tr>
<tr class="even">
<td><p> (選用) 委派管理回應群組</p></td>
<td><p>將 CsResponseGroupManager 角色指派給使用者，以委派回應群組的設定。 然後，回應群組管理員可以設定指派給他們的回應群組。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-planning-for-role-based-access-control.md">在 Lync Server 2013 中規劃以角色為基礎的存取控制</a></p></td>
</tr>
<tr class="odd">
<td><p>驗證您的回應群組部署</p></td>
<td><p>測試接聽群組搜尋和互動語音回應工作流程的來電，以確保您的設定如預期般運作。</p></td>
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

