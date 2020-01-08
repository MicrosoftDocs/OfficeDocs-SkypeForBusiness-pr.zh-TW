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

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a><span data-ttu-id="f1bf4-102">Lync Server 2013 中的回應群組部署程式</span><span class="sxs-lookup"><span data-stu-id="f1bf4-102">Deployment process for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1bf4-103">_**主題上次修改日期：** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="f1bf4-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="f1bf4-104">本節概要說明部署回應群組應用程式時所涉及的階段和步驟。</span><span class="sxs-lookup"><span data-stu-id="f1bf4-104">This section provides an overview of the phases and steps involved in deploying the Response Group application.</span></span>

### <a name="response-group-deployment-process"></a><span data-ttu-id="f1bf4-105">回應群組部署程式</span><span class="sxs-lookup"><span data-stu-id="f1bf4-105">Response Group Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1bf4-106">分</span><span class="sxs-lookup"><span data-stu-id="f1bf4-106">Phase</span></span></th>
<th><span data-ttu-id="f1bf4-107">步驟</span><span class="sxs-lookup"><span data-stu-id="f1bf4-107">Steps</span></span></th>
<th><span data-ttu-id="f1bf4-108">許可權</span><span class="sxs-lookup"><span data-stu-id="f1bf4-108">Permissions</span></span></th>
<th><span data-ttu-id="f1bf4-109">部署檔</span><span class="sxs-lookup"><span data-stu-id="f1bf4-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1bf4-110">安裝回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="f1bf4-110">Install the Response Group application</span></span></p></td>
<td><p><span data-ttu-id="f1bf4-111">當您部署企業語音時，系統會預設安裝並啟用回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="f1bf4-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="f1bf4-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f1bf4-112">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="f1bf4-113"><a href="lync-server-2013-deploying-enterprise-voice.md">在 Lync Server 2013 中部署企業版語音</a></span><span class="sxs-lookup"><span data-stu-id="f1bf4-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1bf4-114">安裝回應群組元件</span><span class="sxs-lookup"><span data-stu-id="f1bf4-114">Install components for Response Group</span></span></p></td>
<td><p><span data-ttu-id="f1bf4-115">Lync Server Cmdlet、Lync Server [控制台]、[回應群組設定] 工具、[代理程式登入與登出主控台]，以及回應群組用戶端 Web 服務已安裝為 Web 服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="f1bf4-115">Lync Server cmdlets, the Lync Server Control Panel, Response Group Configuration Tool, agents' sign-in and sign-out console, and Response Group Client Web service are installed as part of Web Services.</span></span> <span data-ttu-id="f1bf4-116">當您部署企業版文件庫或標準版伺服器時，就會安裝 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="f1bf4-116">Web Services is installed when you deploy an Enterprise Edition pool or a Standard Edition server.</span></span></p></td>
<td><p><span data-ttu-id="f1bf4-117">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f1bf4-117">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="f1bf4-118"><a href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f1bf4-118"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1bf4-119">允許使用者使用 Lync 2013 和企業語音</span><span class="sxs-lookup"><span data-stu-id="f1bf4-119">Enable users for Lync 2013 and for Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="f1bf4-120">啟用將是 Lync Server 和企業語音的使用者。</span><span class="sxs-lookup"><span data-stu-id="f1bf4-120">Enable users who will be agents for Lync Server and Enterprise Voice.</span></span> <span data-ttu-id="f1bf4-121">您必須先啟用使用者，才能將其新增至代理群組。</span><span class="sxs-lookup"><span data-stu-id="f1bf4-121">Users must be enabled before you can add them to agent groups.</span></span> <span data-ttu-id="f1bf4-122">通常，在企業版或標準版伺服器部署期間，會啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="f1bf4-122">Typically, users are enabled for Lync Server during the Enterprise Edition or Standard Edition server deployment.</span></span> <span data-ttu-id="f1bf4-123">在企業語音部署期間，系統會為使用者啟用企業語音。</span><span class="sxs-lookup"><span data-stu-id="f1bf4-123">Users are enabled for Enterprise Voice during the Enterprise Voice deployment.</span></span></p></td>
<td><p><span data-ttu-id="f1bf4-124">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="f1bf4-124">RTCUniversalUserAdmins</span></span></p>
<p><span data-ttu-id="f1bf4-125">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="f1bf4-125">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="f1bf4-126">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f1bf4-126">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="f1bf4-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">停用或重新啟用 Lync Server 2013 的使用者帳戶</a></span><span class="sxs-lookup"><span data-stu-id="f1bf4-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="f1bf4-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">在 Lync Server 2013 中啟用企業語音的使用者</a></span><span class="sxs-lookup"><span data-stu-id="f1bf4-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1bf4-129">建立及設定回應群組，包括代理群組、佇列和工作流程</span><span class="sxs-lookup"><span data-stu-id="f1bf4-129">Create and configure response groups, which consist of agent groups, queues, and workflows</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f1bf4-130">使用 Lync Server [控制台] 或 [Lync Server 管理命令介面] 執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f1bf4-130">Use the Lync Server Control Panel or Lync Server Management Shell to do the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="f1bf4-131">建立及設定代理群組。</span><span class="sxs-lookup"><span data-stu-id="f1bf4-131">Create and configure agent groups.</span></span></p></li>
<li><p><span data-ttu-id="f1bf4-132">建立及設定佇列。</span><span class="sxs-lookup"><span data-stu-id="f1bf4-132">Create and configure queues.</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="f1bf4-133">或者，您也可以使用 Lync Server 管理命令介面來建立預先定義的回應群組商務時數和假日。</span><span class="sxs-lookup"><span data-stu-id="f1bf4-133">Optionally, use Lync Server Management Shell to create predefined response group business hours and holidays.</span></span></p></li>
<li><p><span data-ttu-id="f1bf4-134">使用 [回應群組設定] 工具或 [Lync Server 管理命令介面] 來建立工作流程（查尋群組或互動式語音回應（IVR）通話流程），包括自訂回應群組的商務時數和假日。</span><span class="sxs-lookup"><span data-stu-id="f1bf4-134">Use the Response Group Configuration Tool or Lync Server Management Shell to create workflows (hunt groups or interactive voice response (IVR) call flows), including custom response group business hours and holidays.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f1bf4-135">您可以透過 [Lync Server 控制台] 存取 [回應群組設定] 工具。</span><span class="sxs-lookup"><span data-stu-id="f1bf4-135">You can access the Response Group Configuration Tool through Lync Server Control Panel.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="f1bf4-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f1bf4-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="f1bf4-137">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="f1bf4-137">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="f1bf4-138">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="f1bf4-138">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="f1bf4-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f1bf4-139">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="f1bf4-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f1bf4-140">CsAdministrator</span></span></p>
<p><span data-ttu-id="f1bf4-141">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="f1bf4-141">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="f1bf4-142"><a href="lync-server-2013-create-response-group-agent-groups.md">在 Lync Server 2013 中建立回應群組代理群組</a></span><span class="sxs-lookup"><span data-stu-id="f1bf4-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Create Response Group agent groups Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="f1bf4-143"><a href="lync-server-2013-create-response-group-queues.md">在 Lync Server 2013 中建立回應群組佇列</a></span><span class="sxs-lookup"><span data-stu-id="f1bf4-143"><a href="lync-server-2013-create-response-group-queues.md">Create Response Group queues in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="f1bf4-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">可選在 Lync Server 2013 中定義回應群組的上班時間</a></span><span class="sxs-lookup"><span data-stu-id="f1bf4-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="f1bf4-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">可選在 Lync Server 2013 中定義回應群組假日集</a></span><span class="sxs-lookup"><span data-stu-id="f1bf4-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="f1bf4-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">在 Lync Server 2013 中建立或修改工作流程</a></span><span class="sxs-lookup"><span data-stu-id="f1bf4-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Create or modify a workflow in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1bf4-147">可選自訂應用程式層級設定</span><span class="sxs-lookup"><span data-stu-id="f1bf4-147">(Optional) Customize application-level settings</span></span></p></td>
<td><p><span data-ttu-id="f1bf4-148">您可以使用 Lync Server 管理命令介面來自訂預設的音樂保留式設定、預設的音樂保留音訊檔案、代理 ringback 寬限期，以及通話內容配置。</span><span class="sxs-lookup"><span data-stu-id="f1bf4-148">Use Lync Server Management Shell to customize the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span></p></td>
<td><p><span data-ttu-id="f1bf4-149">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f1bf4-149">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="f1bf4-150">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="f1bf4-150">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="f1bf4-151">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="f1bf4-151">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="f1bf4-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f1bf4-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="f1bf4-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f1bf4-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="f1bf4-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">管理 Lync Server 2013 中的應用層級回應群組設定</a></span><span class="sxs-lookup"><span data-stu-id="f1bf4-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Managing application-level Response Group settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1bf4-155">可選委派對回應群組的管理</span><span class="sxs-lookup"><span data-stu-id="f1bf4-155">(Optional) Delegate management of response groups</span></span></p></td>
<td><p><span data-ttu-id="f1bf4-156">指派使用者的 CsResponseGroupManager 角色來委派回應群組的設定。</span><span class="sxs-lookup"><span data-stu-id="f1bf4-156">Assign users the CsResponseGroupManager role to delegate configuration of response groups.</span></span> <span data-ttu-id="f1bf4-157">回應群組管理員可以設定指派給他們的回應群組。</span><span class="sxs-lookup"><span data-stu-id="f1bf4-157">Response Group Managers can then configure the response groups assigned to them.</span></span></p></td>
<td><p><span data-ttu-id="f1bf4-158">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f1bf4-158">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="f1bf4-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="f1bf4-159">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="f1bf4-160">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="f1bf4-160">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="f1bf4-161">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f1bf4-161">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="f1bf4-162">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f1bf4-162">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="f1bf4-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">在 Lync Server 2013 中規劃角色型存取控制</a></span><span class="sxs-lookup"><span data-stu-id="f1bf4-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1bf4-164">驗證您的回應群組部署</span><span class="sxs-lookup"><span data-stu-id="f1bf4-164">Verify your Response Group deployment</span></span></p></td>
<td><p><span data-ttu-id="f1bf4-165">測試對您的查尋群組和互動式語音回應工作流程的通話回應，以確保您的設定如預期的那樣正常運作。</span><span class="sxs-lookup"><span data-stu-id="f1bf4-165">Test answering calls to your hunt group and interactive voice response workflows to ensure that your configuration works as expected.</span></span></p></td>
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

