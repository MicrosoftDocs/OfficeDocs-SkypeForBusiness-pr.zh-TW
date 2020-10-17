---
title: Lync Server 2013：回應群組的部署程式
description: Lync Server 2013：回應群組的部署程式。
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
ms.openlocfilehash: 4b50fb7903a2fcc301bbf435013b8f8df4e775a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551029"
---
# <a name="deployment-process-for-response-group-in-lync-server-2013"></a><span data-ttu-id="1253d-103">Lync Server 2013 中回應群組的部署程式</span><span class="sxs-lookup"><span data-stu-id="1253d-103">Deployment process for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1253d-104">_**主題上次修改日期：** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="1253d-104">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="1253d-105">本節概述部署回應群組應用程式所需的階段和步驟。</span><span class="sxs-lookup"><span data-stu-id="1253d-105">This section provides an overview of the phases and steps involved in deploying the Response Group application.</span></span>

### <a name="response-group-deployment-process"></a><span data-ttu-id="1253d-106">回應群組部署程式</span><span class="sxs-lookup"><span data-stu-id="1253d-106">Response Group Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1253d-107">階段</span><span class="sxs-lookup"><span data-stu-id="1253d-107">Phase</span></span></th>
<th><span data-ttu-id="1253d-108">步驟</span><span class="sxs-lookup"><span data-stu-id="1253d-108">Steps</span></span></th>
<th><span data-ttu-id="1253d-109">權限</span><span class="sxs-lookup"><span data-stu-id="1253d-109">Permissions</span></span></th>
<th><span data-ttu-id="1253d-110">部署文件</span><span class="sxs-lookup"><span data-stu-id="1253d-110">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1253d-111">安裝回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="1253d-111">Install the Response Group application</span></span></p></td>
<td><p><span data-ttu-id="1253d-112">當您部署企業語音時，預設會安裝及啟用回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="1253d-112">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="1253d-113">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1253d-113">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="1253d-114"><a href="lync-server-2013-deploying-enterprise-voice.md">在 Lync Server 2013 中部署企業語音</a></span><span class="sxs-lookup"><span data-stu-id="1253d-114"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1253d-115">安裝回應群組的元件</span><span class="sxs-lookup"><span data-stu-id="1253d-115">Install components for Response Group</span></span></p></td>
<td><p><span data-ttu-id="1253d-116">Lync Server Cmdlet、Lync Server 控制台、回應群組設定工具、代理程式的登入和登出主控台，以及回應群組用戶端 Web 服務會安裝為 Web 服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="1253d-116">Lync Server cmdlets, the Lync Server Control Panel, Response Group Configuration Tool, agents' sign-in and sign-out console, and Response Group Client Web service are installed as part of Web Services.</span></span> <span data-ttu-id="1253d-117">當您部署 Enterprise Edition 集區或 Standard Edition server 時，即會安裝 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="1253d-117">Web Services is installed when you deploy an Enterprise Edition pool or a Standard Edition server.</span></span></p></td>
<td><p><span data-ttu-id="1253d-118">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1253d-118">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="1253d-119"><a href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1253d-119"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1253d-120">啟用使用者的 Lync 2013 和 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="1253d-120">Enable users for Lync 2013 and for Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="1253d-121">啟用將會成為 Lync Server 和 Enterprise Voice 之代理人的使用者。</span><span class="sxs-lookup"><span data-stu-id="1253d-121">Enable users who will be agents for Lync Server and Enterprise Voice.</span></span> <span data-ttu-id="1253d-122">您必須先啟用使用者，才能將其新增至代理人群組。</span><span class="sxs-lookup"><span data-stu-id="1253d-122">Users must be enabled before you can add them to agent groups.</span></span> <span data-ttu-id="1253d-123">一般來說，在 Enterprise Edition 或 Standard Edition Server 部署期間會為 Lync Server 啟用使用者。</span><span class="sxs-lookup"><span data-stu-id="1253d-123">Typically, users are enabled for Lync Server during the Enterprise Edition or Standard Edition server deployment.</span></span> <span data-ttu-id="1253d-124">在企業語音部署期間，使用者已啟用 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="1253d-124">Users are enabled for Enterprise Voice during the Enterprise Voice deployment.</span></span></p></td>
<td><p><span data-ttu-id="1253d-125">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1253d-125">RTCUniversalUserAdmins</span></span></p>
<p><span data-ttu-id="1253d-126">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="1253d-126">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="1253d-127">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="1253d-127">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1253d-128"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">停用或重新啟用 Lync Server 2013 的使用者帳戶</a></span><span class="sxs-lookup"><span data-stu-id="1253d-128"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="1253d-129"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">在 Lync Server 2013 中啟用使用者的 Enterprise Voice</a></span><span class="sxs-lookup"><span data-stu-id="1253d-129"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1253d-130">建立和設定回應群組，包括代理群組、佇列和工作流程</span><span class="sxs-lookup"><span data-stu-id="1253d-130">Create and configure response groups, which consist of agent groups, queues, and workflows</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="1253d-131">使用 Lync Server 控制台或 Lync Server 管理命令介面執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="1253d-131">Use the Lync Server Control Panel or Lync Server Management Shell to do the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="1253d-132">建立和設定代理人群組。</span><span class="sxs-lookup"><span data-stu-id="1253d-132">Create and configure agent groups.</span></span></p></li>
<li><p><span data-ttu-id="1253d-133">建立和設定佇列。</span><span class="sxs-lookup"><span data-stu-id="1253d-133">Create and configure queues.</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="1253d-134">（選用）使用 Lync Server 管理命令介面來建立預先定義的回應群組上班時間與假日。</span><span class="sxs-lookup"><span data-stu-id="1253d-134">Optionally, use Lync Server Management Shell to create predefined response group business hours and holidays.</span></span></p></li>
<li><p><span data-ttu-id="1253d-135">使用回應群組設定工具或 Lync Server 管理命令介面來建立工作流程 (群組搜尋或互動語音回應 (IVR) 通話流程) （包括自訂回應群組的上班時間和公休日）。</span><span class="sxs-lookup"><span data-stu-id="1253d-135">Use the Response Group Configuration Tool or Lync Server Management Shell to create workflows (hunt groups or interactive voice response (IVR) call flows), including custom response group business hours and holidays.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="1253d-136">您可以透過 Lync Server 控制台存取回應群組設定工具。</span><span class="sxs-lookup"><span data-stu-id="1253d-136">You can access the Response Group Configuration Tool through Lync Server Control Panel.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="1253d-137">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1253d-137">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="1253d-138">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="1253d-138">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="1253d-139">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="1253d-139">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="1253d-140">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="1253d-140">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="1253d-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="1253d-141">CsAdministrator</span></span></p>
<p><span data-ttu-id="1253d-142">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="1253d-142">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="1253d-143"><a href="lync-server-2013-create-response-group-agent-groups.md">建立回應群組代理群組 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1253d-143"><a href="lync-server-2013-create-response-group-agent-groups.md">Create Response Group agent groups Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="1253d-144"><a href="lync-server-2013-create-response-group-queues.md">在 Lync Server 2013 中建立回應群組佇列</a></span><span class="sxs-lookup"><span data-stu-id="1253d-144"><a href="lync-server-2013-create-response-group-queues.md">Create Response Group queues in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="1253d-145"><a href="lync-server-2013-optional-define-response-group-business-hours.md"> (選用) 在 Lync Server 2013 中定義回應群組上班時間</a></span><span class="sxs-lookup"><span data-stu-id="1253d-145"><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="1253d-146"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md"> (選用) 在 Lync Server 2013 中定義回應群組假日集</a></span><span class="sxs-lookup"><span data-stu-id="1253d-146"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="1253d-147"><a href="lync-server-2013-create-or-modify-a-workflow.md">在 Lync Server 2013 中建立或修改工作流程</a></span><span class="sxs-lookup"><span data-stu-id="1253d-147"><a href="lync-server-2013-create-or-modify-a-workflow.md">Create or modify a workflow in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1253d-148"> (選用) 自訂應用層級設定</span><span class="sxs-lookup"><span data-stu-id="1253d-148">(Optional) Customize application-level settings</span></span></p></td>
<td><p><span data-ttu-id="1253d-149">使用 Lync Server 管理命令介面，來自訂預設的等候音樂設定、預設的等候音樂音訊檔、代理程式回電寬限期，以及呼叫內容設定。</span><span class="sxs-lookup"><span data-stu-id="1253d-149">Use Lync Server Management Shell to customize the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span></p></td>
<td><p><span data-ttu-id="1253d-150">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1253d-150">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="1253d-151">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="1253d-151">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="1253d-152">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="1253d-152">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="1253d-153">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="1253d-153">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="1253d-154">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="1253d-154">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1253d-155"><a href="lync-server-2013-managing-application-level-response-group-settings.md">在 Lync Server 2013 中管理應用層級回應群組設定</a></span><span class="sxs-lookup"><span data-stu-id="1253d-155"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Managing application-level Response Group settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1253d-156"> (選用) 委派管理回應群組</span><span class="sxs-lookup"><span data-stu-id="1253d-156">(Optional) Delegate management of response groups</span></span></p></td>
<td><p><span data-ttu-id="1253d-157">將 CsResponseGroupManager 角色指派給使用者，以委派回應群組的設定。</span><span class="sxs-lookup"><span data-stu-id="1253d-157">Assign users the CsResponseGroupManager role to delegate configuration of response groups.</span></span> <span data-ttu-id="1253d-158">然後，回應群組管理員可以設定指派給他們的回應群組。</span><span class="sxs-lookup"><span data-stu-id="1253d-158">Response Group Managers can then configure the response groups assigned to them.</span></span></p></td>
<td><p><span data-ttu-id="1253d-159">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="1253d-159">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="1253d-160">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="1253d-160">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="1253d-161">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="1253d-161">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="1253d-162">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="1253d-162">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="1253d-163">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="1253d-163">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1253d-164"><a href="lync-server-2013-planning-for-role-based-access-control.md">在 Lync Server 2013 中規劃以角色為基礎的存取控制</a></span><span class="sxs-lookup"><span data-stu-id="1253d-164"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1253d-165">驗證您的回應群組部署</span><span class="sxs-lookup"><span data-stu-id="1253d-165">Verify your Response Group deployment</span></span></p></td>
<td><p><span data-ttu-id="1253d-166">測試接聽群組搜尋和互動語音回應工作流程的來電，以確保您的設定如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="1253d-166">Test answering calls to your hunt group and interactive voice response workflows to ensure that your configuration works as expected.</span></span></p></td>
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

