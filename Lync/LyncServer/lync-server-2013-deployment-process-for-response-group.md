---
title: Lync Server 2013： 部署程序的回應群組
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
ms.openlocfilehash: 7c592b0ee0ba2794391c539bdc52e9344bc43b27
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a><span data-ttu-id="e16e0-102">Lync Server 2013 中的回應群組部署程序</span><span class="sxs-lookup"><span data-stu-id="e16e0-102">Deployment process for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e16e0-103">_**主題上次修改日期：** 2012 年 09 月 27 日_</span><span class="sxs-lookup"><span data-stu-id="e16e0-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="e16e0-104">本章節提供階段和部署的回應群組應用程式的相關步驟的概觀。</span><span class="sxs-lookup"><span data-stu-id="e16e0-104">This section provides an overview of the phases and steps involved in deploying the Response Group application.</span></span>

### <a name="response-group-deployment-process"></a><span data-ttu-id="e16e0-105">回應群組部署程序</span><span class="sxs-lookup"><span data-stu-id="e16e0-105">Response Group Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e16e0-106">階段</span><span class="sxs-lookup"><span data-stu-id="e16e0-106">Phase</span></span></th>
<th><span data-ttu-id="e16e0-107">步驟</span><span class="sxs-lookup"><span data-stu-id="e16e0-107">Steps</span></span></th>
<th><span data-ttu-id="e16e0-108">權限</span><span class="sxs-lookup"><span data-stu-id="e16e0-108">Permissions</span></span></th>
<th><span data-ttu-id="e16e0-109">部署文件</span><span class="sxs-lookup"><span data-stu-id="e16e0-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e16e0-110">安裝回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="e16e0-110">Install the Response Group application</span></span></p></td>
<td><p><span data-ttu-id="e16e0-111">回應群組應用程式已安裝並啟用根據預設，當您部署企業語音。</span><span class="sxs-lookup"><span data-stu-id="e16e0-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="e16e0-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e16e0-112">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="e16e0-113"><a href="lync-server-2013-deploying-enterprise-voice.md">部署 Lync Server 2013 中的 Enterprise Voice</a></span><span class="sxs-lookup"><span data-stu-id="e16e0-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e16e0-114">回應群組安裝的元件</span><span class="sxs-lookup"><span data-stu-id="e16e0-114">Install components for Response Group</span></span></p></td>
<td><p><span data-ttu-id="e16e0-115">Lync Server cmdlet、 Lync Server 控制台中，回應群組組態工具、 代理的登入與登出主控台及回應群組用戶端 Web 服務安裝 Web 服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="e16e0-115">Lync Server cmdlets, the Lync Server Control Panel, Response Group Configuration Tool, agents' sign-in and sign-out console, and Response Group Client Web service are installed as part of Web Services.</span></span> <span data-ttu-id="e16e0-116">當您部署的 Enterprise Edition 集區或 Standard Edition server 已安裝 web 服務。</span><span class="sxs-lookup"><span data-stu-id="e16e0-116">Web Services is installed when you deploy an Enterprise Edition pool or a Standard Edition server.</span></span></p></td>
<td><p><span data-ttu-id="e16e0-117">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e16e0-117">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="e16e0-118"><a href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e16e0-118"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e16e0-119">啟用使用者的 Lync 2013 及 Enterprise voice</span><span class="sxs-lookup"><span data-stu-id="e16e0-119">Enable users for Lync 2013 and for Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="e16e0-120">讓使用者擔任 Lync 伺服器和 Enterprise Voice 的代理程式。</span><span class="sxs-lookup"><span data-stu-id="e16e0-120">Enable users who will be agents for Lync Server and Enterprise Voice.</span></span> <span data-ttu-id="e16e0-121">您可以將其新增至代理程式群組之前，必須啟用使用者。</span><span class="sxs-lookup"><span data-stu-id="e16e0-121">Users must be enabled before you can add them to agent groups.</span></span> <span data-ttu-id="e16e0-122">一般而言，使用者已啟用 Lync Server Enterprise Edition 或 Standard Edition server 部署期間。</span><span class="sxs-lookup"><span data-stu-id="e16e0-122">Typically, users are enabled for Lync Server during the Enterprise Edition or Standard Edition server deployment.</span></span> <span data-ttu-id="e16e0-123">使用者在 Enterprise Voice 部署期間啟用 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="e16e0-123">Users are enabled for Enterprise Voice during the Enterprise Voice deployment.</span></span></p></td>
<td><p><span data-ttu-id="e16e0-124">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="e16e0-124">RTCUniversalUserAdmins</span></span></p>
<p><span data-ttu-id="e16e0-125">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="e16e0-125">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="e16e0-126">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e16e0-126">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e16e0-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">停用或重新啟用 Lync Server 2013 的使用者帳戶</a></span><span class="sxs-lookup"><span data-stu-id="e16e0-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="e16e0-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">啟用使用者的 Lync Server 2013 中的 Enterprise Voice</a></span><span class="sxs-lookup"><span data-stu-id="e16e0-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e16e0-129">建立和設定回應群組，其中包含代理人群組、 佇列及工作流程</span><span class="sxs-lookup"><span data-stu-id="e16e0-129">Create and configure response groups, which consist of agent groups, queues, and workflows</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="e16e0-130">使用 Lync Server Control Panel 或 Lync Server 管理命令介面來執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e16e0-130">Use the Lync Server Control Panel or Lync Server Management Shell to do the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="e16e0-131">建立和設定代理人群組。</span><span class="sxs-lookup"><span data-stu-id="e16e0-131">Create and configure agent groups.</span></span></p></li>
<li><p><span data-ttu-id="e16e0-132">建立和設定佇列。</span><span class="sxs-lookup"><span data-stu-id="e16e0-132">Create and configure queues.</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="e16e0-133">（選用） 使用 Lync Server 管理命令介面來建立預先定義的回應群組營業時間與假日。</span><span class="sxs-lookup"><span data-stu-id="e16e0-133">Optionally, use Lync Server Management Shell to create predefined response group business hours and holidays.</span></span></p></li>
<li><p><span data-ttu-id="e16e0-134">使用的回應群組組態工具或 Lync Server 管理命令介面來建立工作流程 （群組搜尋或互動語音回應 (IVR) 通話流程），包括自訂回應群組營業時間與假日。</span><span class="sxs-lookup"><span data-stu-id="e16e0-134">Use the Response Group Configuration Tool or Lync Server Management Shell to create workflows (hunt groups or interactive voice response (IVR) call flows), including custom response group business hours and holidays.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e16e0-135">您可以透過 Lync Server Control Panel 存取回應群組組態工具。</span><span class="sxs-lookup"><span data-stu-id="e16e0-135">You can access the Response Group Configuration Tool through Lync Server Control Panel.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="e16e0-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e16e0-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e16e0-137">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="e16e0-137">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="e16e0-138">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="e16e0-138">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="e16e0-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e16e0-139">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="e16e0-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e16e0-140">CsAdministrator</span></span></p>
<p><span data-ttu-id="e16e0-141">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="e16e0-141">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="e16e0-142"><a href="lync-server-2013-create-response-group-agent-groups.md">建立回應群組代理群組 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e16e0-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Create Response Group agent groups Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="e16e0-143"><a href="lync-server-2013-create-response-group-queues.md">Lync Server 2013 中建立回應群組佇列</a></span><span class="sxs-lookup"><span data-stu-id="e16e0-143"><a href="lync-server-2013-create-response-group-queues.md">Create Response Group queues in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="e16e0-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">（選用）Lync Server 2013 中的定義回應群組營業時間</a></span><span class="sxs-lookup"><span data-stu-id="e16e0-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="e16e0-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">（選用）Lync Server 2013 中的定義回應群組假日集</a></span><span class="sxs-lookup"><span data-stu-id="e16e0-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="e16e0-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">建立或修改 Lync Server 2013 中的工作流程</a></span><span class="sxs-lookup"><span data-stu-id="e16e0-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Create or modify a workflow in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e16e0-147">（選用）自訂應用程式層級設定</span><span class="sxs-lookup"><span data-stu-id="e16e0-147">(Optional) Customize application-level settings</span></span></p></td>
<td><p><span data-ttu-id="e16e0-148">使用 Lync Server 管理命令介面自訂預設的等候音樂上保留設定、 預設的等候音樂上保留音訊檔案、 代理人回電寬限期以及來電內容設定。</span><span class="sxs-lookup"><span data-stu-id="e16e0-148">Use Lync Server Management Shell to customize the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span></p></td>
<td><p><span data-ttu-id="e16e0-149">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e16e0-149">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e16e0-150">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="e16e0-150">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="e16e0-151">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="e16e0-151">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="e16e0-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e16e0-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="e16e0-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e16e0-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e16e0-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">管理 Lync Server 2013 中的應用程式層級回應群組設定</a></span><span class="sxs-lookup"><span data-stu-id="e16e0-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Managing application-level Response Group settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e16e0-155">（選用）委派管理回應群組</span><span class="sxs-lookup"><span data-stu-id="e16e0-155">(Optional) Delegate management of response groups</span></span></p></td>
<td><p><span data-ttu-id="e16e0-156">將使用者指派 CsResponseGroupManager 角色委派的回應群組組態。</span><span class="sxs-lookup"><span data-stu-id="e16e0-156">Assign users the CsResponseGroupManager role to delegate configuration of response groups.</span></span> <span data-ttu-id="e16e0-157">回應群組管理員則可以設定指派給他們的回應群組。</span><span class="sxs-lookup"><span data-stu-id="e16e0-157">Response Group Managers can then configure the response groups assigned to them.</span></span></p></td>
<td><p><span data-ttu-id="e16e0-158">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e16e0-158">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e16e0-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="e16e0-159">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="e16e0-160">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="e16e0-160">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="e16e0-161">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e16e0-161">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="e16e0-162">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e16e0-162">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e16e0-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">規劃 Lync Server 2013 中角色型存取控制</a></span><span class="sxs-lookup"><span data-stu-id="e16e0-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e16e0-164">確認回應群組部署</span><span class="sxs-lookup"><span data-stu-id="e16e0-164">Verify your Response Group deployment</span></span></p></td>
<td><p><span data-ttu-id="e16e0-165">測試群組搜尋或互動語音回應系統工作流程自動答錄服務呼叫以確保您的設定，如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="e16e0-165">Test answering calls to your hunt group and interactive voice response workflows to ensure that your configuration works as expected.</span></span></p></td>
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

