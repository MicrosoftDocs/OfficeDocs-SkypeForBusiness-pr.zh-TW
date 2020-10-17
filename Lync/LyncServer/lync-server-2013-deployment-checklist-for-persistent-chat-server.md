---
title: Lync Server 2013： Persistent Chat Server 的部署檢查清單
description: Lync Server 2013： Persistent Chat Server 的部署檢查清單。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28d96da5e2961634e6a81450796e5d1ae3426819
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568289"
---
# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="2c04a-103">Lync Server 2013 中 Persistent Chat Server 的部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="2c04a-103">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c04a-104">_**主題上次修改日期：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="2c04a-104">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="2c04a-105">部署 Lync Server 2013，Persistent Chat Server 需要您以正確順序進行部署，而且您已完成所有必要的部署步驟。</span><span class="sxs-lookup"><span data-stu-id="2c04a-105">Deployment of Lync Server 2013, Persistent Chat Server requires that you deploy it in the correct sequence and that you complete all required deployment steps.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="2c04a-106">部署順序</span><span class="sxs-lookup"><span data-stu-id="2c04a-106">Deployment Sequence</span></span>

<span data-ttu-id="2c04a-107">您可以在部署初始拓撲（包括至少一個 Lync Server 2013、前端集區或一部 Lync Server 2013，Standard Edition server）之後，部署 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="2c04a-107">You can deploy Persistent Chat Server after you deploy your initial topology, including at least one Lync Server 2013, Front End pool or one Lync Server 2013, Standard Edition server.</span></span> <span data-ttu-id="2c04a-108">本主題說明如何將 Persistent Chat Server 新增至現有的部署。</span><span class="sxs-lookup"><span data-stu-id="2c04a-108">This topic describes how to deploy Persistent Chat Server by adding it to an existing deployment.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="2c04a-109">部署程式</span><span class="sxs-lookup"><span data-stu-id="2c04a-109">Deployment Process</span></span>

<span data-ttu-id="2c04a-110">下表列出部署 Persistent Chat Server 的基本步驟，並提供詳細資訊的連結。</span><span class="sxs-lookup"><span data-stu-id="2c04a-110">The following table lists the basic steps to deploy Persistent Chat Server and provides links for more details.</span></span>

### <a name="persistent-chat-server-deployment-process"></a><span data-ttu-id="2c04a-111">Persistent Chat Server 部署程式</span><span class="sxs-lookup"><span data-stu-id="2c04a-111">Persistent Chat Server Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c04a-112">工作</span><span class="sxs-lookup"><span data-stu-id="2c04a-112">Task</span></span></th>
<th><span data-ttu-id="2c04a-113">步驟</span><span class="sxs-lookup"><span data-stu-id="2c04a-113">Steps</span></span></th>
<th><span data-ttu-id="2c04a-114">必要的角色和群組成員資格</span><span class="sxs-lookup"><span data-stu-id="2c04a-114">Required roles and group memberships</span></span></th>
<th><span data-ttu-id="2c04a-115">相關主題</span><span class="sxs-lookup"><span data-stu-id="2c04a-115">Related topics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c04a-116"><strong>安裝必備硬體和軟體</strong></span><span class="sxs-lookup"><span data-stu-id="2c04a-116"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="2c04a-117">在符合系統需求的硬體上，安裝下列各項：</span><span class="sxs-lookup"><span data-stu-id="2c04a-117">On hardware that meets system requirements, install the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2c04a-118">在 Persistent Chat Server 前端伺服器上：</span><span class="sxs-lookup"><span data-stu-id="2c04a-118">On the Persistent Chat Server Front End Servers:</span></span></p></li>
</ul>
<ul>
<li><p><span data-ttu-id="2c04a-119">符合系統需求的作業系統</span><span class="sxs-lookup"><span data-stu-id="2c04a-119">An operating system that meets system requirements</span></span></p></li>
<li><p><span data-ttu-id="2c04a-120">執行 Lync Server 2013 之電腦的軟體必要條件</span><span class="sxs-lookup"><span data-stu-id="2c04a-120">Software prerequisites for computers running Lync Server 2013</span></span></p></li>
<li><p><span data-ttu-id="2c04a-121">會裝載 Persistent Chat Server 資料庫之伺服器上的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="2c04a-121">SQL Server on the server that will host Persistent Chat Server database</span></span></p></li>
</ul>
<p><span data-ttu-id="2c04a-122">如果需要 Persistent Chat Server 規範：</span><span class="sxs-lookup"><span data-stu-id="2c04a-122">If Persistent Chat Server compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="2c04a-123">伺服器上將主控 Persistent Chat Server 規範資料庫的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="2c04a-123">SQL Server on the server that will host Persistent Chat Server compliance database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2c04a-124">屬於本機 Administrators 群組成員的任何使用者。</span><span class="sxs-lookup"><span data-stu-id="2c04a-124">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="2c04a-125">支援檔中的<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支援的硬體</a></span><span class="sxs-lookup"><span data-stu-id="2c04a-125"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="2c04a-126">支援檔中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的伺服器軟體和基礎結構支援</a></span><span class="sxs-lookup"><span data-stu-id="2c04a-126"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="2c04a-127"><a href="lync-server-2013-determining-your-system-requirements.md">決定 Lync Server 2013 的系統需求</a></span><span class="sxs-lookup"><span data-stu-id="2c04a-127"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="2c04a-128"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Lync Server 2013 中 Persistent Chat Server 的技術需求</a></span><span class="sxs-lookup"><span data-stu-id="2c04a-128"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technical requirements for Persistent Chat Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c04a-129"><strong>建立適當的內部拓撲以支援 Persistent Chat Server (及（選用）持續性聊天規範) </strong></span><span class="sxs-lookup"><span data-stu-id="2c04a-129"><strong>Create the appropriate internal topology to support Persistent Chat Server (and optionally, Persistent Chat compliance)</strong></span></span></p></td>
<td><p><span data-ttu-id="2c04a-130">執行拓撲產生器，將 Persistent Chat Server 集區新增至您的拓撲：</span><span class="sxs-lookup"><span data-stu-id="2c04a-130">Run Topology Builder to add a Persistent Chat Server pool to your topology:</span></span></p>
<ul>
<li><p><span data-ttu-id="2c04a-131">將 Persistent Chat Server 元件新增至拓撲</span><span class="sxs-lookup"><span data-stu-id="2c04a-131">Add Persistent Chat Server components to the topology</span></span></p></li>
<li><p><span data-ttu-id="2c04a-132">為 Persistent Chat Server store (和備份 SQL Server 建立 SQL Server 資料庫，以進行嚴重損壞修復) </span><span class="sxs-lookup"><span data-stu-id="2c04a-132">Create a SQL Server database for the Persistent Chat Server store (and a backup SQL Server for disaster recovery)</span></span></p></li>
<li><p><span data-ttu-id="2c04a-133">定義新的 Lync 檔存放區，或使用現有的 Lync 檔案存放區做為持久聊天伺服器檔案</span><span class="sxs-lookup"><span data-stu-id="2c04a-133">Define a new Lync File Store or use an existing Lync File Store for Persistent Chat Server files</span></span></p></li>
<li><p><span data-ttu-id="2c04a-134">關聯可將要求路由傳送至此 Persistent Chat Server 集區的 Lync Server 2013 集區</span><span class="sxs-lookup"><span data-stu-id="2c04a-134">Associate the Lync Server 2013 pool that can route requests to this Persistent Chat Server pool</span></span></p></li>
</ul>
<p><span data-ttu-id="2c04a-135">如果需要持久聊天規範：</span><span class="sxs-lookup"><span data-stu-id="2c04a-135">If Persistent Chat compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="2c04a-136">新增 Persistent 聊天室規範存放區</span><span class="sxs-lookup"><span data-stu-id="2c04a-136">Add Persistent Chat Compliance Store</span></span></p></li>
<li><p><span data-ttu-id="2c04a-137">按一下 [Persistent Chat Server 集區定義] 核取方塊以啟用相容性</span><span class="sxs-lookup"><span data-stu-id="2c04a-137">Click the Persistent Chat Server pool definition check box for enabling compliance</span></span></p></li>
<li><p><span data-ttu-id="2c04a-138">發行拓撲</span><span class="sxs-lookup"><span data-stu-id="2c04a-138">Publish the topology</span></span></p></li>
</ul>
<p><span data-ttu-id="2c04a-139">如果您在 Standard Edition 上安裝 Persistent Chat Server，則 Persistent Chat Server 集區的完整功能變數名稱 (FQDN) 必須符合 Standard Edition server，而且 SQL Server 資料庫會在 Standard Edition server 上的 SQL Server Express 實例上組合</span><span class="sxs-lookup"><span data-stu-id="2c04a-139">If you install Persistent Chat Server on Standard Edition, the fully qualified domain name (FQDN) of the Persistent Chat Server pool must match the Standard Edition server, and the SQL Server databases are collocated on the SQL Server Express instance on the Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="2c04a-140">若要定義拓撲，則為本機使用者群組成員的帳戶。</span><span class="sxs-lookup"><span data-stu-id="2c04a-140">To define a topology, an account that is a member of the local Users group.</span></span></p>
<p><span data-ttu-id="2c04a-141">若要發行拓撲，則為 Domain Admins 群組和 RTCUniversalServerAdmins 群組成員的帳戶，而且使用者應在 Lync 檔存放區上 (讀取/寫入/修改) 的「完全控制」許可權，以取得 Persistent Chat Server 檔案 (，讓拓撲產生器可以設定必要的 Dacl) 。</span><span class="sxs-lookup"><span data-stu-id="2c04a-141">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and the user should also have full control permissions (read/write/modify) on the Lync File Store for Persistent Chat Server files (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="2c04a-142">在部署檔中<a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">將 Persistent Chat Server 新增至 Lync server 2013</a>中的部署</span><span class="sxs-lookup"><span data-stu-id="2c04a-142"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c04a-143"><strong>部署常設聊天室伺服器</strong></span><span class="sxs-lookup"><span data-stu-id="2c04a-143"><strong>Deploy Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="2c04a-144">在所有執行 Persistent Chat Server 的電腦上執行 Lync Server 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="2c04a-144">Run the Lync Server setup on all the computers running Persistent Chat Server.</span></span> <span data-ttu-id="2c04a-145">Persistent Chat Server 安裝程式已整合至 Lync Server 2013 部署嚮導，提供下列指示：</span><span class="sxs-lookup"><span data-stu-id="2c04a-145">The Persistent Chat Server setup is integrated into the Lync Server 2013 Deployment wizard that provides the following instructions:</span></span></p>
<ul>
<li><p><span data-ttu-id="2c04a-146">部署本機管理存放區</span><span class="sxs-lookup"><span data-stu-id="2c04a-146">Deploy local management store</span></span></p></li>
<li><p><span data-ttu-id="2c04a-147">安裝 Persistent Chat Server 服務</span><span class="sxs-lookup"><span data-stu-id="2c04a-147">Install Persistent Chat Server services</span></span></p></li>
<li><p><span data-ttu-id="2c04a-148">要求並指派憑證</span><span class="sxs-lookup"><span data-stu-id="2c04a-148">Request and assign certificates</span></span></p></li>
<li><p><span data-ttu-id="2c04a-149">執行並啟動服務</span><span class="sxs-lookup"><span data-stu-id="2c04a-149">Run and start the services</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2c04a-150">屬於本機 Administrators 群組成員的任何使用者。</span><span class="sxs-lookup"><span data-stu-id="2c04a-150">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="2c04a-151">部署檔中的<a href="lync-server-2013-deploying-persistent-chat-server.md">Lync server 2013 部署 Persistent Chat Server</a></span><span class="sxs-lookup"><span data-stu-id="2c04a-151"><a href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c04a-152"><strong>建立常設聊天室系統管理員</strong></span><span class="sxs-lookup"><span data-stu-id="2c04a-152"><strong>Create a Persistent Chat administrator</strong></span></span></p></td>
<td><p><span data-ttu-id="2c04a-153">將使用者新增至 CsPersistentChatAdministrator 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="2c04a-153">Add users to the CsPersistentChatAdministrator security group.</span></span></p></td>
<td><p><span data-ttu-id="2c04a-154">任何屬於網域管理員成員的使用者。</span><span class="sxs-lookup"><span data-stu-id="2c04a-154">Any user who is a member of domain administrators.</span></span></p></td>
<td><p><span data-ttu-id="2c04a-155">在部署檔中的<a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Lync Server 2013 中新增 Persistent Chat 系統管理員</a></span><span class="sxs-lookup"><span data-stu-id="2c04a-155"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Adding a Persistent Chat administrator in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c04a-156"><strong>設定 Persistent Chat Server</strong></span><span class="sxs-lookup"><span data-stu-id="2c04a-156"><strong>Configure Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="2c04a-157">設定使用者：</span><span class="sxs-lookup"><span data-stu-id="2c04a-157">Configure users:</span></span></p>
<ul>
<li><p><span data-ttu-id="2c04a-158">使用者必須啟用該原則，才能存取 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="2c04a-158">User has to be enabled by policy to access Persistent Chat Server.</span></span> <span data-ttu-id="2c04a-159">根據預設，會為所有使用者關閉原則，並且可以在全域/網站/集區/使用者範圍上定義。</span><span class="sxs-lookup"><span data-stu-id="2c04a-159">By default, the policy is turned off for all users and can be defined at global/site/pool/user scopes.</span></span></p></li>
<li><p><span data-ttu-id="2c04a-160">進行設定</span><span class="sxs-lookup"><span data-stu-id="2c04a-160">Configure settings</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2c04a-161">使用者必須是 CsPersistentChatAdministrator 的成員。</span><span class="sxs-lookup"><span data-stu-id="2c04a-161">User must be a member of CsPersistentChatAdministrator.</span></span> <span data-ttu-id="2c04a-162">若要變更原則，使用者至少必須在 CsUserAdministrator 中。</span><span class="sxs-lookup"><span data-stu-id="2c04a-162">To change policy, user must be in CsUserAdministrator, at a minimum.</span></span></p></td>
<td><p><span data-ttu-id="2c04a-163">在部署檔中的<a href="lync-server-2013-configuring-persistent-chat-server.md">Lync server 2013 中設定 Persistent Chat Server</a></span><span class="sxs-lookup"><span data-stu-id="2c04a-163"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuring Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="2c04a-164">您可以部署一或多個 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="2c04a-164">You can deploy one or more Persistent Chat Server pools.</span></span> <span data-ttu-id="2c04a-165">由於法規原因，我們支援多個 Persistent Chat Server 集區，因此需要在特定區域中產生的資料保持在該地區內。</span><span class="sxs-lookup"><span data-stu-id="2c04a-165">We support multiple Persistent Chat Server pools for regulatory reasons whereby data generated in a given region is required to stay in that region.</span></span> <span data-ttu-id="2c04a-166">例如，如果您在芝加哥部署了 Persistent Chat Server 集區，而另一個在蘇黎世中遵循的是瑞士的資料法規，只要使用者有存取權，使用者就可以在 Persistent Chat Server 集區中連接至聊天室。</span><span class="sxs-lookup"><span data-stu-id="2c04a-166">For example, if you deploy a Persistent Chat Server pool in Chicago, and another in Zurich to comply with regulations for data in Switzerland, users can connect to rooms in both the Persistent Chat Server pools, provided they have access.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

