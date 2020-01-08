---
title: Lync Server 2013：常設聊天室伺服器的部署檢查清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e539a1aa6883863228aaab19ddaa38300ae45591
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="3f82c-102">Lync Server 2013 中的常設聊天室伺服器的部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="3f82c-102">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f82c-103">_**主題上次修改日期：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="3f82c-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="3f82c-104">若要部署 Lync Server 2013，持久的聊天伺服器需要您以正確的順序部署它，且您已完成所有必要的部署步驟。</span><span class="sxs-lookup"><span data-stu-id="3f82c-104">Deployment of Lync Server 2013, Persistent Chat Server requires that you deploy it in the correct sequence and that you complete all required deployment steps.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="3f82c-105">部署順序</span><span class="sxs-lookup"><span data-stu-id="3f82c-105">Deployment Sequence</span></span>

<span data-ttu-id="3f82c-106">您可以在部署初始拓撲（包括至少一個 Lync Server 2013、前端池或一個 Lync Server 2013，標準版伺服器）之後，部署持續式聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="3f82c-106">You can deploy Persistent Chat Server after you deploy your initial topology, including at least one Lync Server 2013, Front End pool or one Lync Server 2013, Standard Edition server.</span></span> <span data-ttu-id="3f82c-107">本主題描述如何將持久聊天伺服器新增至現有的部署。</span><span class="sxs-lookup"><span data-stu-id="3f82c-107">This topic describes how to deploy Persistent Chat Server by adding it to an existing deployment.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="3f82c-108">部署程式</span><span class="sxs-lookup"><span data-stu-id="3f82c-108">Deployment Process</span></span>

<span data-ttu-id="3f82c-109">下表列出部署持久聊天伺服器的基本步驟，並提供更多詳細資料的連結。</span><span class="sxs-lookup"><span data-stu-id="3f82c-109">The following table lists the basic steps to deploy Persistent Chat Server and provides links for more details.</span></span>

### <a name="persistent-chat-server-deployment-process"></a><span data-ttu-id="3f82c-110">持續聊天伺服器部署程式</span><span class="sxs-lookup"><span data-stu-id="3f82c-110">Persistent Chat Server Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f82c-111">工作</span><span class="sxs-lookup"><span data-stu-id="3f82c-111">Task</span></span></th>
<th><span data-ttu-id="3f82c-112">步驟</span><span class="sxs-lookup"><span data-stu-id="3f82c-112">Steps</span></span></th>
<th><span data-ttu-id="3f82c-113">必要角色和群組成員資格</span><span class="sxs-lookup"><span data-stu-id="3f82c-113">Required roles and group memberships</span></span></th>
<th><span data-ttu-id="3f82c-114">相關主題</span><span class="sxs-lookup"><span data-stu-id="3f82c-114">Related topics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f82c-115"><strong>安裝必備的硬體和軟體</strong></span><span class="sxs-lookup"><span data-stu-id="3f82c-115"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="3f82c-116">在符合系統需求的硬體上，安裝下列各項：</span><span class="sxs-lookup"><span data-stu-id="3f82c-116">On hardware that meets system requirements, install the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3f82c-117">在永久聊天伺服器前端伺服器上：</span><span class="sxs-lookup"><span data-stu-id="3f82c-117">On the Persistent Chat Server Front End Servers:</span></span></p></li>
</ul>
<ul>
<li><p><span data-ttu-id="3f82c-118">符合系統需求的作業系統</span><span class="sxs-lookup"><span data-stu-id="3f82c-118">An operating system that meets system requirements</span></span></p></li>
<li><p><span data-ttu-id="3f82c-119">運行 Lync Server 2013 之電腦的軟體先決條件</span><span class="sxs-lookup"><span data-stu-id="3f82c-119">Software prerequisites for computers running Lync Server 2013</span></span></p></li>
<li><p><span data-ttu-id="3f82c-120">伺服器上將主控持久聊天伺服器資料庫的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="3f82c-120">SQL Server on the server that will host Persistent Chat Server database</span></span></p></li>
</ul>
<p><span data-ttu-id="3f82c-121">如果需要持續聊天伺服器合規性：</span><span class="sxs-lookup"><span data-stu-id="3f82c-121">If Persistent Chat Server compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="3f82c-122">伺服器上將託管持久聊天伺服器合規性資料庫的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="3f82c-122">SQL Server on the server that will host Persistent Chat Server compliance database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3f82c-123">屬於本機管理員群組成員的任何使用者。</span><span class="sxs-lookup"><span data-stu-id="3f82c-123">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="3f82c-124">支援檔中的<a href="lync-server-2013-supported-hardware.md">Lync Server 2013 支援的硬體</a></span><span class="sxs-lookup"><span data-stu-id="3f82c-124"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="3f82c-125">支援檔中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的伺服器軟體和基礎結構支援</a></span><span class="sxs-lookup"><span data-stu-id="3f82c-125"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="3f82c-126"><a href="lync-server-2013-determining-your-system-requirements.md">判定 Lync Server 2013 的系統需求</a></span><span class="sxs-lookup"><span data-stu-id="3f82c-126"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="3f82c-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Lync Server 2013 中持續聊天伺服器的技術需求</a></span><span class="sxs-lookup"><span data-stu-id="3f82c-127"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technical requirements for Persistent Chat Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f82c-128"><strong>建立適當的內部拓朴，以支援持續聊天伺服器（以及可隨意進行的聊天合規性）</strong></span><span class="sxs-lookup"><span data-stu-id="3f82c-128"><strong>Create the appropriate internal topology to support Persistent Chat Server (and optionally, Persistent Chat compliance)</strong></span></span></p></td>
<td><p><span data-ttu-id="3f82c-129">執行拓撲建立器，以新增持久聊天伺服器池至您的拓撲：</span><span class="sxs-lookup"><span data-stu-id="3f82c-129">Run Topology Builder to add a Persistent Chat Server pool to your topology:</span></span></p>
<ul>
<li><p><span data-ttu-id="3f82c-130">新增持久聊天伺服器元件至拓撲</span><span class="sxs-lookup"><span data-stu-id="3f82c-130">Add Persistent Chat Server components to the topology</span></span></p></li>
<li><p><span data-ttu-id="3f82c-131">建立持久聊天伺服器存放區的 SQL Server 資料庫（以及災害復原的備份 SQL Server）</span><span class="sxs-lookup"><span data-stu-id="3f82c-131">Create a SQL Server database for the Persistent Chat Server store (and a backup SQL Server for disaster recovery)</span></span></p></li>
<li><p><span data-ttu-id="3f82c-132">定義新的 Lync 檔案存放區，或使用現有的 Lync 檔案存放區儲存持久聊天伺服器檔案</span><span class="sxs-lookup"><span data-stu-id="3f82c-132">Define a new Lync File Store or use an existing Lync File Store for Persistent Chat Server files</span></span></p></li>
<li><p><span data-ttu-id="3f82c-133">將可傳送要求的 Lync Server 2013 池與此持續聊天伺服器池建立關聯</span><span class="sxs-lookup"><span data-stu-id="3f82c-133">Associate the Lync Server 2013 pool that can route requests to this Persistent Chat Server pool</span></span></p></li>
</ul>
<p><span data-ttu-id="3f82c-134">如果需要持續聊天合規性：</span><span class="sxs-lookup"><span data-stu-id="3f82c-134">If Persistent Chat compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="3f82c-135">新增持久聊天合規性存放區</span><span class="sxs-lookup"><span data-stu-id="3f82c-135">Add Persistent Chat Compliance Store</span></span></p></li>
<li><p><span data-ttu-id="3f82c-136">按一下 [持續聊天伺服器池定義] 核取方塊以啟用合規性</span><span class="sxs-lookup"><span data-stu-id="3f82c-136">Click the Persistent Chat Server pool definition check box for enabling compliance</span></span></p></li>
<li><p><span data-ttu-id="3f82c-137">發行拓撲</span><span class="sxs-lookup"><span data-stu-id="3f82c-137">Publish the topology</span></span></p></li>
</ul>
<p><span data-ttu-id="3f82c-138">如果您在標準版上安裝持續式聊天伺服器，則持久性聊天伺服器池的完整功能變數名稱（FQDN）必須符合標準版伺服器，且 SQL Server 資料庫在標準版的 SQL Server Express 實例上是 collocated 的。Edition 伺服器</span><span class="sxs-lookup"><span data-stu-id="3f82c-138">If you install Persistent Chat Server on Standard Edition, the fully qualified domain name (FQDN) of the Persistent Chat Server pool must match the Standard Edition server, and the SQL Server databases are collocated on the SQL Server Express instance on the Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="3f82c-139">若要定義拓撲，該帳戶是 [本機使用者] 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="3f82c-139">To define a topology, an account that is a member of the local Users group.</span></span></p>
<p><span data-ttu-id="3f82c-140">若要發佈拓朴，該帳戶是網域系統管理員群組和 RTCUniversalServerAdmins 群組的成員，而且使用者在 Lync 檔案存放區上也應該有完整的控制許可權（讀取/寫入/修改），以取得持續聊天伺服器檔案（讓拓撲產生器可以設定所需的 Dacl）。</span><span class="sxs-lookup"><span data-stu-id="3f82c-140">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and the user should also have full control permissions (read/write/modify) on the Lync File Store for Persistent Chat Server files (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="3f82c-141">在部署檔的<a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 中新增持久聊天伺服器到您的部署</a></span><span class="sxs-lookup"><span data-stu-id="3f82c-141"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f82c-142"><strong>部署常設聊天室伺服器</strong></span><span class="sxs-lookup"><span data-stu-id="3f82c-142"><strong>Deploy Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="3f82c-143">在執行永久聊天伺服器的所有電腦上執行 Lync Server 設定。</span><span class="sxs-lookup"><span data-stu-id="3f82c-143">Run the Lync Server setup on all the computers running Persistent Chat Server.</span></span> <span data-ttu-id="3f82c-144">[永久聊天伺服器] 安裝程式已整合至 Lync Server 2013 部署嚮導，並提供下列指示：</span><span class="sxs-lookup"><span data-stu-id="3f82c-144">The Persistent Chat Server setup is integrated into the Lync Server 2013 Deployment wizard that provides the following instructions:</span></span></p>
<ul>
<li><p><span data-ttu-id="3f82c-145">部署本機管理存放區</span><span class="sxs-lookup"><span data-stu-id="3f82c-145">Deploy local management store</span></span></p></li>
<li><p><span data-ttu-id="3f82c-146">安裝永久性聊天伺服器服務</span><span class="sxs-lookup"><span data-stu-id="3f82c-146">Install Persistent Chat Server services</span></span></p></li>
<li><p><span data-ttu-id="3f82c-147">要求並指派憑證</span><span class="sxs-lookup"><span data-stu-id="3f82c-147">Request and assign certificates</span></span></p></li>
<li><p><span data-ttu-id="3f82c-148">執行並啟動服務</span><span class="sxs-lookup"><span data-stu-id="3f82c-148">Run and start the services</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3f82c-149">屬於本機管理員群組成員的任何使用者。</span><span class="sxs-lookup"><span data-stu-id="3f82c-149">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="3f82c-150">部署檔中的<a href="lync-server-2013-deploying-persistent-chat-server.md">Lync server 2013 部署持續聊天伺服器</a></span><span class="sxs-lookup"><span data-stu-id="3f82c-150"><a href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f82c-151"><strong>建立常設聊天室系統管理員</strong></span><span class="sxs-lookup"><span data-stu-id="3f82c-151"><strong>Create a Persistent Chat administrator</strong></span></span></p></td>
<td><p><span data-ttu-id="3f82c-152">將使用者新增至 CsPersistentChatAdministrator 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="3f82c-152">Add users to the CsPersistentChatAdministrator security group.</span></span></p></td>
<td><p><span data-ttu-id="3f82c-153">屬於網域管理員成員的任何使用者。</span><span class="sxs-lookup"><span data-stu-id="3f82c-153">Any user who is a member of domain administrators.</span></span></p></td>
<td><p><span data-ttu-id="3f82c-154">在部署檔的<a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Lync Server 2013 中新增持續性聊天系統管理員</a></span><span class="sxs-lookup"><span data-stu-id="3f82c-154"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Adding a Persistent Chat administrator in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f82c-155"><strong>設定常設聊天室伺服器</strong></span><span class="sxs-lookup"><span data-stu-id="3f82c-155"><strong>Configure Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="3f82c-156">設定使用者：</span><span class="sxs-lookup"><span data-stu-id="3f82c-156">Configure users:</span></span></p>
<ul>
<li><p><span data-ttu-id="3f82c-157">使用者必須由原則啟用，才能存取持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="3f82c-157">User has to be enabled by policy to access Persistent Chat Server.</span></span> <span data-ttu-id="3f82c-158">根據預設，對於所有使用者而言，原則都是關閉的，而且可以在全域/網站/池/使用者範圍中定義。</span><span class="sxs-lookup"><span data-stu-id="3f82c-158">By default, the policy is turned off for all users and can be defined at global/site/pool/user scopes.</span></span></p></li>
<li><p><span data-ttu-id="3f82c-159">設定設定</span><span class="sxs-lookup"><span data-stu-id="3f82c-159">Configure settings</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3f82c-160">使用者必須是 CsPersistentChatAdministrator 的成員。</span><span class="sxs-lookup"><span data-stu-id="3f82c-160">User must be a member of CsPersistentChatAdministrator.</span></span> <span data-ttu-id="3f82c-161">若要變更原則，使用者至少必須在 CsUserAdministrator 中。</span><span class="sxs-lookup"><span data-stu-id="3f82c-161">To change policy, user must be in CsUserAdministrator, at a minimum.</span></span></p></td>
<td><p><span data-ttu-id="3f82c-162">在部署檔中的<a href="lync-server-2013-configuring-persistent-chat-server.md">Lync server 2013 中設定持續聊天伺服器</a></span><span class="sxs-lookup"><span data-stu-id="3f82c-162"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuring Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="3f82c-163">您可以部署一或多個持久聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="3f82c-163">You can deploy one or more Persistent Chat Server pools.</span></span> <span data-ttu-id="3f82c-164">我們支援多個持續聊天伺服器池，以確保在指定區域中產生的資料必須留在該區域。</span><span class="sxs-lookup"><span data-stu-id="3f82c-164">We support multiple Persistent Chat Server pools for regulatory reasons whereby data generated in a given region is required to stay in that region.</span></span> <span data-ttu-id="3f82c-165">例如，如果您是在芝加哥部署持續式聊天伺服器池，而另一個是在蘇黎世中遵守瑞士資料的規章，使用者只要有存取權，就能連線到持久性聊天伺服器池中的聊天室。</span><span class="sxs-lookup"><span data-stu-id="3f82c-165">For example, if you deploy a Persistent Chat Server pool in Chicago, and another in Zurich to comply with regulations for data in Switzerland, users can connect to rooms in both the Persistent Chat Server pools, provided they have access.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

