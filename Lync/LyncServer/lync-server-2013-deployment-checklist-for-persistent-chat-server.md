---
title: 'Lync Server 2013: Persistent Chat Server 的部署檢查清單'
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
ms.openlocfilehash: 6234ca4a8a0e7f6edc2069b7bb42f0bae545713b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="7df99-102">Persistent Chat Server in Lync Server 2013 的部署檢查表</span><span class="sxs-lookup"><span data-stu-id="7df99-102">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7df99-103">_**主題上次修改日期：** 2012 年 10-16_</span><span class="sxs-lookup"><span data-stu-id="7df99-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="7df99-104">部署 Lync Server 2013，Persistent Chat Server 需要您將它部署以正確的順序，以及您完成所有必要的部署步驟。</span><span class="sxs-lookup"><span data-stu-id="7df99-104">Deployment of Lync Server 2013, Persistent Chat Server requires that you deploy it in the correct sequence and that you complete all required deployment steps.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="7df99-105">部署順序</span><span class="sxs-lookup"><span data-stu-id="7df99-105">Deployment Sequence</span></span>

<span data-ttu-id="7df99-106">在部署初始拓撲，包括至少一個 Lync Server 2013 中，前端集區或一 Lync Server 2013 Standard Edition server 之後，您可以部署 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="7df99-106">You can deploy Persistent Chat Server after you deploy your initial topology, including at least one Lync Server 2013, Front End pool or one Lync Server 2013, Standard Edition server.</span></span> <span data-ttu-id="7df99-107">本主題說明如何部署常設聊天室伺服器新增至現有的部署。</span><span class="sxs-lookup"><span data-stu-id="7df99-107">This topic describes how to deploy Persistent Chat Server by adding it to an existing deployment.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="7df99-108">部署程序</span><span class="sxs-lookup"><span data-stu-id="7df99-108">Deployment Process</span></span>

<span data-ttu-id="7df99-109">下表列出部署常設聊天室伺服器的基本步驟，並提供連結如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="7df99-109">The following table lists the basic steps to deploy Persistent Chat Server and provides links for more details.</span></span>

### <a name="persistent-chat-server-deployment-process"></a><span data-ttu-id="7df99-110">常設聊天室伺服器部署程序</span><span class="sxs-lookup"><span data-stu-id="7df99-110">Persistent Chat Server Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7df99-111">工作</span><span class="sxs-lookup"><span data-stu-id="7df99-111">Task</span></span></th>
<th><span data-ttu-id="7df99-112">步驟</span><span class="sxs-lookup"><span data-stu-id="7df99-112">Steps</span></span></th>
<th><span data-ttu-id="7df99-113">必要的角色和群組成員資格</span><span class="sxs-lookup"><span data-stu-id="7df99-113">Required roles and group memberships</span></span></th>
<th><span data-ttu-id="7df99-114">相關主題</span><span class="sxs-lookup"><span data-stu-id="7df99-114">Related topics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7df99-115"><strong>安裝必備硬體和軟體</strong></span><span class="sxs-lookup"><span data-stu-id="7df99-115"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="7df99-116">在符合系統需求的硬體上，安裝下列各項：</span><span class="sxs-lookup"><span data-stu-id="7df99-116">On hardware that meets system requirements, install the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7df99-117">在 [常設聊天室伺服器前端伺服器：</span><span class="sxs-lookup"><span data-stu-id="7df99-117">On the Persistent Chat Server Front End Servers:</span></span></p></li>
</ul>
<ul>
<li><p><span data-ttu-id="7df99-118">符合系統需求的作業系統</span><span class="sxs-lookup"><span data-stu-id="7df99-118">An operating system that meets system requirements</span></span></p></li>
<li><p><span data-ttu-id="7df99-119">執行 Lync Server 2013 的電腦的軟體先決條件</span><span class="sxs-lookup"><span data-stu-id="7df99-119">Software prerequisites for computers running Lync Server 2013</span></span></p></li>
<li><p><span data-ttu-id="7df99-120">在將主控 Persistent Chat Server 資料庫的伺服器上的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="7df99-120">SQL Server on the server that will host Persistent Chat Server database</span></span></p></li>
</ul>
<p><span data-ttu-id="7df99-121">如果需要常設聊天室伺服器規範：</span><span class="sxs-lookup"><span data-stu-id="7df99-121">If Persistent Chat Server compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="7df99-122">將裝載常設聊天室伺服器規範資料庫的伺服器上的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="7df99-122">SQL Server on the server that will host Persistent Chat Server compliance database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7df99-123">使用屬於本機 Administrators 群組的任何使用者。</span><span class="sxs-lookup"><span data-stu-id="7df99-123">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="7df99-124">支援文件中<a href="lync-server-2013-supported-hardware.md">的 Lync Server 2013 支援硬體</a></span><span class="sxs-lookup"><span data-stu-id="7df99-124"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="7df99-125">支援文件中的 [ <a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync Server 2013 中的伺服器軟體和基礎結構支援</a></span><span class="sxs-lookup"><span data-stu-id="7df99-125"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="7df99-126"><a href="lync-server-2013-determining-your-system-requirements.md">決定您的 Lync Server 2013 的系統需求</a></span><span class="sxs-lookup"><span data-stu-id="7df99-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="7df99-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Persistent Chat Server in Lync Server 2013 的技術需求</a></span><span class="sxs-lookup"><span data-stu-id="7df99-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technical requirements for Persistent Chat Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7df99-128"><strong>建立適當的內部拓撲以支援 Persistent Chat Server （並選擇性地常設聊天室規範）</strong></span><span class="sxs-lookup"><span data-stu-id="7df99-128"><strong>Create the appropriate internal topology to support Persistent Chat Server (and optionally, Persistent Chat compliance)</strong></span></span></p></td>
<td><p><span data-ttu-id="7df99-129">執行拓撲產生器來將 Persistent Chat Server 集區新增至您的拓撲：</span><span class="sxs-lookup"><span data-stu-id="7df99-129">Run Topology Builder to add a Persistent Chat Server pool to your topology:</span></span></p>
<ul>
<li><p><span data-ttu-id="7df99-130">Persistent Chat Server 元件新增至拓撲</span><span class="sxs-lookup"><span data-stu-id="7df99-130">Add Persistent Chat Server components to the topology</span></span></p></li>
<li><p><span data-ttu-id="7df99-131">建立 SQL Server 資料庫 Persistent Chat Server 儲存區 （及嚴重損壞修復備份 SQL Server）</span><span class="sxs-lookup"><span data-stu-id="7df99-131">Create a SQL Server database for the Persistent Chat Server store (and a backup SQL Server for disaster recovery)</span></span></p></li>
<li><p><span data-ttu-id="7df99-132">定義新的 Lync 檔案存放區，或使用現有的 Lync 檔案存放區 Persistent Chat Server 檔案</span><span class="sxs-lookup"><span data-stu-id="7df99-132">Define a new Lync File Store or use an existing Lync File Store for Persistent Chat Server files</span></span></p></li>
<li><p><span data-ttu-id="7df99-133">建立可以將要求路由傳送到此 Persistent Chat Server 集區的 Lync Server 2013 集區的關聯</span><span class="sxs-lookup"><span data-stu-id="7df99-133">Associate the Lync Server 2013 pool that can route requests to this Persistent Chat Server pool</span></span></p></li>
</ul>
<p><span data-ttu-id="7df99-134">如果需要常設聊天室規範：</span><span class="sxs-lookup"><span data-stu-id="7df99-134">If Persistent Chat compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="7df99-135">新增常設聊天室規範存放區</span><span class="sxs-lookup"><span data-stu-id="7df99-135">Add Persistent Chat Compliance Store</span></span></p></li>
<li><p><span data-ttu-id="7df99-136">按一下 [常設聊天室伺服器集區定義核取方塊，來啟用規範</span><span class="sxs-lookup"><span data-stu-id="7df99-136">Click the Persistent Chat Server pool definition check box for enabling compliance</span></span></p></li>
<li><p><span data-ttu-id="7df99-137">發行拓撲</span><span class="sxs-lookup"><span data-stu-id="7df99-137">Publish the topology</span></span></p></li>
</ul>
<p><span data-ttu-id="7df99-138">如果您在 Standard Edition 上安裝 Persistent Chat Server，Persistent Chat Server 集區的完整的網域名稱 (FQDN) 必須符合 Standard Edition server，並在標準的 SQL Server Express 執行個體上組合的 SQL Server 資料庫Edition 伺服器</span><span class="sxs-lookup"><span data-stu-id="7df99-138">If you install Persistent Chat Server on Standard Edition, the fully qualified domain name (FQDN) of the Persistent Chat Server pool must match the Standard Edition server, and the SQL Server databases are collocated on the SQL Server Express instance on the Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="7df99-139">若要定義拓樸，屬於本機 Users 群組帳戶。</span><span class="sxs-lookup"><span data-stu-id="7df99-139">To define a topology, an account that is a member of the local Users group.</span></span></p>
<p><span data-ttu-id="7df99-140">若要發行拓樸，屬於 Domain Admins 群組和 RTCUniversalServerAdmins 群組，以及使用者帳戶應該也具備完全控制權限 （讀取/寫入/修改） Persistent Chat Server 檔案 Lync 檔案存放區 （以便拓撲產生器可以設定必要的 Dacl）。</span><span class="sxs-lookup"><span data-stu-id="7df99-140">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and the user should also have full control permissions (read/write/modify) on the Lync File Store for Persistent Chat Server files (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="7df99-141"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">新增常設聊天室伺服器的 Lync Server 2013 部署</a>中部署文件</span><span class="sxs-lookup"><span data-stu-id="7df99-141"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7df99-142"><strong>部署常設聊天室伺服器</strong></span><span class="sxs-lookup"><span data-stu-id="7df99-142"><strong>Deploy Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="7df99-143">在執行 Persistent Chat Server 的所有電腦上執行 Lync Server 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="7df99-143">Run the Lync Server setup on all the computers running Persistent Chat Server.</span></span> <span data-ttu-id="7df99-144">Persistent Chat Server 安裝程式已整合至 Lync Server 2013 部署精靈，可提供下列指示：</span><span class="sxs-lookup"><span data-stu-id="7df99-144">The Persistent Chat Server setup is integrated into the Lync Server 2013 Deployment wizard that provides the following instructions:</span></span></p>
<ul>
<li><p><span data-ttu-id="7df99-145">部署本機管理存放區</span><span class="sxs-lookup"><span data-stu-id="7df99-145">Deploy local management store</span></span></p></li>
<li><p><span data-ttu-id="7df99-146">安裝 Persistent Chat Server 服務</span><span class="sxs-lookup"><span data-stu-id="7df99-146">Install Persistent Chat Server services</span></span></p></li>
<li><p><span data-ttu-id="7df99-147">要求並指派憑證</span><span class="sxs-lookup"><span data-stu-id="7df99-147">Request and assign certificates</span></span></p></li>
<li><p><span data-ttu-id="7df99-148">執行及啟動服務</span><span class="sxs-lookup"><span data-stu-id="7df99-148">Run and start the services</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7df99-149">使用屬於本機 Administrators 群組的任何使用者。</span><span class="sxs-lookup"><span data-stu-id="7df99-149">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="7df99-150">部署文件中的<a href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7df99-150"><a href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7df99-151"><strong>建立常設聊天室管理員</strong></span><span class="sxs-lookup"><span data-stu-id="7df99-151"><strong>Create a Persistent Chat administrator</strong></span></span></p></td>
<td><p><span data-ttu-id="7df99-152">將使用者新增至 CsPersistentChatAdministrator 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="7df99-152">Add users to the CsPersistentChatAdministrator security group.</span></span></p></td>
<td><p><span data-ttu-id="7df99-153">屬於網域 administrators 成員的任何使用者。</span><span class="sxs-lookup"><span data-stu-id="7df99-153">Any user who is a member of domain administrators.</span></span></p></td>
<td><p><span data-ttu-id="7df99-154">部署文件中的 [<a href="lync-server-2013-adding-a-persistent-chat-administrator.md">新增 Lync Server 2013 常設聊天室管理員</a></span><span class="sxs-lookup"><span data-stu-id="7df99-154"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Adding a Persistent Chat administrator in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7df99-155"><strong>設定常設聊天室伺服器</strong></span><span class="sxs-lookup"><span data-stu-id="7df99-155"><strong>Configure Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="7df99-156">設定使用者：</span><span class="sxs-lookup"><span data-stu-id="7df99-156">Configure users:</span></span></p>
<ul>
<li><p><span data-ttu-id="7df99-157">使用者已啟用原則，才能存取 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="7df99-157">User has to be enabled by policy to access Persistent Chat Server.</span></span> <span data-ttu-id="7df99-158">依預設，此原則已關閉的所有使用者，並可以定義於全域/網站/集區/使用者範圍。</span><span class="sxs-lookup"><span data-stu-id="7df99-158">By default, the policy is turned off for all users and can be defined at global/site/pool/user scopes.</span></span></p></li>
<li><p><span data-ttu-id="7df99-159">進行設定</span><span class="sxs-lookup"><span data-stu-id="7df99-159">Configure settings</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7df99-160">使用者必須是 CsPersistentChatAdministrator 的成員。</span><span class="sxs-lookup"><span data-stu-id="7df99-160">User must be a member of CsPersistentChatAdministrator.</span></span> <span data-ttu-id="7df99-161">若要變更原則，使用者必須在 CsUserAdministrator，在最低限度下。</span><span class="sxs-lookup"><span data-stu-id="7df99-161">To change policy, user must be in CsUserAdministrator, at a minimum.</span></span></p></td>
<td><p><span data-ttu-id="7df99-162">部署文件中的<a href="lync-server-2013-configuring-persistent-chat-server.md">Configuring Persistent Chat Server in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7df99-162"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuring Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="7df99-163">您可以部署一個或多個 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="7df99-163">You can deploy one or more Persistent Chat Server pools.</span></span> <span data-ttu-id="7df99-164">我們基於法規的原因： 在特定區域所產生的資料，才能留在該區域支援多個 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="7df99-164">We support multiple Persistent Chat Server pools for regulatory reasons whereby data generated in a given region is required to stay in that region.</span></span> <span data-ttu-id="7df99-165">例如，如果您部署中芝加哥，Persistent Chat Server 集區，另一個 Zurich 遵守法規瑞士中的資料中，使用者可以連線至兩個 Persistent Chat Server 集區中的會議室提供他們具有其存取。</span><span class="sxs-lookup"><span data-stu-id="7df99-165">For example, if you deploy a Persistent Chat Server pool in Chicago, and another in Zurich to comply with regulations for data in Switzerland, users can connect to rooms in both the Persistent Chat Server pools, provided they have access.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

