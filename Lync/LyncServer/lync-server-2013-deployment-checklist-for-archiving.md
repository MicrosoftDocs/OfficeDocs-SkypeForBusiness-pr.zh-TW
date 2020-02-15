---
title: Lync Server 2013： 封存的部署檢查清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 275556e6be613d2dfe23cf245e75c725286e0c02
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a><span data-ttu-id="92083-102">Lync Server 2013 中的封存的部署檢查表</span><span class="sxs-lookup"><span data-stu-id="92083-102">Deployment checklist for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92083-103">_**主題上次修改日期：** 2012年-10-18_</span><span class="sxs-lookup"><span data-stu-id="92083-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="92083-104">封存會自動安裝在每部前端伺服器在 Lync Server 2013 部署中，但您仍需要設定它，然後您可以使用它。</span><span class="sxs-lookup"><span data-stu-id="92083-104">Archiving is automatically installed on each Front End Server in your Lync Server 2013 deployment, but you still need to set it up before you can use it.</span></span> <span data-ttu-id="92083-105">請依本節摘要之設定所需的步驟部署封存。</span><span class="sxs-lookup"><span data-stu-id="92083-105">The steps required to set it up, as summarized in this section, constitute the deployment of Archiving.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="92083-106">部署順序</span><span class="sxs-lookup"><span data-stu-id="92083-106">Deployment Sequence</span></span>

<span data-ttu-id="92083-107">如何根據所選擇的存放區選項設定封存：</span><span class="sxs-lookup"><span data-stu-id="92083-107">How you set up Archiving depends on which storage option you choose:</span></span>

  - <span data-ttu-id="92083-108">如果您在部署中的所有使用者使用 Microsoft Exchange 整合，您不需要設定您的使用者的 Lync Server 2013 封存原則。</span><span class="sxs-lookup"><span data-stu-id="92083-108">If you use Microsoft Exchange integration for all users in your deployment, you don’t need to configure Lync Server 2013 Archiving policies for your users.</span></span> <span data-ttu-id="92083-109">相反地，設定 Exchange 就地保留原則以支援封存的使用者使用他們放入原有範圍暫止的信箱位於 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="92083-109">Instead, configure your Exchange In-Place Hold policies to support archiving for users homed on Exchange 2013, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="92083-110">如需設定這些原則的詳細資訊，請參閱 < Exchange 2013 產品的說明文件。</span><span class="sxs-lookup"><span data-stu-id="92083-110">For details about configuring these policies, see the Exchange 2013 product documentation.</span></span>

  - <span data-ttu-id="92083-111">如果您不在您的部署中使用的所有使用者的 Microsoft Exchange 整合，您需要新增 Lync Server 封存資料庫 （SQL Server 資料庫） 至您的拓撲，然後發行，以及設定原則和設定您的使用者，然後您才可以封存這些使用者的資料。</span><span class="sxs-lookup"><span data-stu-id="92083-111">If you do not use Microsoft Exchange integration for all users in your deployment, you need to add Lync Server Archiving databases (SQL Server databases) to your topology and then publish it, as well as configure policies and settings for your users, before you can archive data for those users.</span></span> <span data-ttu-id="92083-112">您可在部署初始拓撲的同時，或者在部署至少一個前端集區或 Standard Edition Server 之後，進行部署封存資料庫。</span><span class="sxs-lookup"><span data-stu-id="92083-112">You can deploy Archiving databases at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span> <span data-ttu-id="92083-113">本文件描述如何透過將封存資料庫新增至現有部署來進行部署。</span><span class="sxs-lookup"><span data-stu-id="92083-113">This document describes how to deploy Archiving databases by adding them to an existing deployment.</span></span>

<span data-ttu-id="92083-p104">如果您在一個前端集區或 Standard Edition Server 啟用封存，則應在部署中針對所有其他前端集區和 Standard Edition Server 一併啟用。這是因為，需要將通訊封存的使用者可受邀至由其他集區所主控的群組 IM 交談或會議。如果封存未在主控交談或會議的所在集區啟用，可能無法封存完整的工作階段。在此情況下，包含已啟用封存之使用者的 IM 仍可進行封存，但不包含會議內容檔案以及會議加入或離開事件。</span><span class="sxs-lookup"><span data-stu-id="92083-p104">If you enable archiving in one Front End pool or Standard Edition server, you should enable it for all other Front End pools and Standard Edition servers in your deployment. This is because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool. If archiving is not enabled on the pool where the conversation or meeting is hosted, the complete session may not be archived. In these cases, IMs with archiving-enabled users still can be archived, but not for conferencing content files, and conference join or leave events.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="92083-118">如果封存極為重要，您的組織基於規範考量，務必部署封存、 設定原則與其他選項，在適當的層級，以及啟用的所有適當的使用者，才能讓這些使用者在 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="92083-118">If archiving is critical in your organization for compliance reasons, be sure to deploy Archiving, configure policies and other options at the appropriate level, and enable it for all appropriate users, before you enable those users for Lync Server 2013.</span></span>



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a><span data-ttu-id="92083-119">封存部署程序</span><span class="sxs-lookup"><span data-stu-id="92083-119">Archiving Deployment Process</span></span>

<span data-ttu-id="92083-120">下表提供在現有拓撲中部署封存之所需步驟的概觀。</span><span class="sxs-lookup"><span data-stu-id="92083-120">The following table provides an overview of the steps required to deploy archiving in an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92083-121">階段</span><span class="sxs-lookup"><span data-stu-id="92083-121">Phase</span></span></th>
<th><span data-ttu-id="92083-122">步驟</span><span class="sxs-lookup"><span data-stu-id="92083-122">Steps</span></span></th>
<th><span data-ttu-id="92083-123">角色和群組成員資格</span><span class="sxs-lookup"><span data-stu-id="92083-123">Roles and group memberships</span></span></th>
<th><span data-ttu-id="92083-124">文件</span><span class="sxs-lookup"><span data-stu-id="92083-124">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92083-125"><strong>安裝必備硬體和軟體</strong></span><span class="sxs-lookup"><span data-stu-id="92083-125"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="92083-126">若要使用 Microsoft Exchange 整合 （針對部分或所有使用者的封存存放區中使用 Exchange 2013），您需要現有的 Exchange 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="92083-126">To use Microsoft Exchange integration (using Exchange 2013 for archiving storage for some or all users), you need an existing Exchange 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="92083-127">若針對部分或所有使用者使用個別封存資料庫 (使用 SQL Server 資料庫) 封存存放區，伺服器上的 SQL Server 將會儲存封存資料。</span><span class="sxs-lookup"><span data-stu-id="92083-127">To use separate Archiving databases (using SQL Server databases) for archiving storage for some or all users, SQL Server on the server that will store archiving data.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="92083-p105">封存會在 Enterprise Pool 前端伺服器與 Standard Edition Server 上執行。安裝這些伺服器除必條件外，沒有額外的硬體或軟體需求。</span><span class="sxs-lookup"><span data-stu-id="92083-p105">Archiving runs on Front End Servers of an Enterprise pool and Standard Edition servers. It has no additional hardware or software requirements beyond what is required to install those servers.</span></span>


</div></td>
<td><p><span data-ttu-id="92083-130">身為本機系統管理員群組成員的網域使用者。</span><span class="sxs-lookup"><span data-stu-id="92083-130">Domain user who is a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="92083-131">支援文件中<a href="lync-server-2013-supported-hardware.md">的 Lync Server 2013 支援硬體</a>。</span><span class="sxs-lookup"><span data-stu-id="92083-131"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="92083-132">支援文件中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync Server 2013 中的伺服器軟體和基礎結構支援</a>。</span><span class="sxs-lookup"><span data-stu-id="92083-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="92083-133">規劃文件中<a href="lync-server-2013-technical-requirements-for-archiving.md">的 technical requirements for Lync Server 2013 中的封存</a>。</span><span class="sxs-lookup"><span data-stu-id="92083-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="92083-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">設定系統與基礎結構的 Lync Server 2013 中的封存</a>中部署文件。</span><span class="sxs-lookup"><span data-stu-id="92083-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Setting up systems and infrastructure for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="92083-135">支援文件中的<a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange Server 與 SharePoint 整合支援 Lync Server 2013 中</a>。</span><span class="sxs-lookup"><span data-stu-id="92083-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange Server and SharePoint integration support in Lync Server 2013</a> in the Supportability documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92083-136"><strong>建立適當的內部拓撲以支援封存 （只有當不使用 Microsoft Exchange 整合您的部署中的所有使用者）</strong></span><span class="sxs-lookup"><span data-stu-id="92083-136"><strong>Create the appropriate internal topology to support archiving (only if not using Microsoft Exchange integration for all users in your deployment)</strong></span></span></p></td>
<td><p><span data-ttu-id="92083-137">執行拓撲產生器來將 Lync Server 2013 封存資料庫 （SQL Server 資料庫） 新增至拓撲，並再發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="92083-137">Run Topology Builder to add Lync Server 2013 Archiving databases (SQL Server databases) to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="92083-138">若要將拓撲定義以納入封存資料庫，帳戶須為本機使用者群組成員。</span><span class="sxs-lookup"><span data-stu-id="92083-138">To define a topology to incorporate Archiving databases, an account that is a member of the local users group.</span></span></p>
<p><span data-ttu-id="92083-139">若要發行拓撲，這是 domain admins 群組和 RTCUniversalServerAdmins 群組的成員，且用於 Lync Server 2013 檔案存放區 （以便拓撲產生器可以設定必要的 Dacl） 的檔案共用具有完整控制權限 （讀取/寫入/修改） 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="92083-139">To publish the topology, an account that is a member of the domain admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="92083-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">新增封存資料庫到現有的 Lync Server 2013 部署</a>中部署文件。</span><span class="sxs-lookup"><span data-stu-id="92083-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adding Archiving databases to an existing Lync Server 2013 Deployment</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92083-141"><strong>設定伺服器對伺服器驗證 （只有在使用 Microsoft Exchange 整合）</strong></span><span class="sxs-lookup"><span data-stu-id="92083-141"><strong>Configure server-to-server authentication (only if using Microsoft Exchange integration)</strong></span></span></p></td>
<td><p><span data-ttu-id="92083-142">設定伺服器，以啟用 Lync Server 2013 和 Exchange 2013 之間的驗證。</span><span class="sxs-lookup"><span data-stu-id="92083-142">Configure servers to enable authentication between Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="92083-143">建議您執行<strong>測試 CsExchangeStorageConnectivity testuser_sipUri – 資料夾暫放</strong>若要驗證 Exchange 封存儲存連線才能啟用封存。</span><span class="sxs-lookup"><span data-stu-id="92083-143">We recommend running <strong>Test-CsExchangeStorageConnectivity testuser_sipUri –Folder Dumpster</strong> to validate Exchange Archiving storage connectivity before enabling archiving.</span></span></p></td>
<td><p><span data-ttu-id="92083-144">具有適當權限可在伺服器上管理憑證的帳戶。</span><span class="sxs-lookup"><span data-stu-id="92083-144">An account with the appropriate permissions for managing certificates on the servers.</span></span></p></td>
<td><p><span data-ttu-id="92083-145">部署文件或作業文件中的<a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">管理伺服器對伺服器驗證 (OAuth) 與 Lync Server 2013 中的協力廠商應用程式</a>。</span><span class="sxs-lookup"><span data-stu-id="92083-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</a> in the Deployment documentation or the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92083-146"><strong>設定封存原則及組態</strong></span><span class="sxs-lookup"><span data-stu-id="92083-146"><strong>Configure archiving policies and configurations</strong></span></span></p></td>
<td><p><span data-ttu-id="92083-147">設定封存，包括是否要使用 Microsoft Exchange 整合、 全域原則及任何網站與使用者原則 （如果不使用 Microsoft Exchange 整合的所有資料存放區），以及特定封存選項，例如重要模式及資料匯出和清除。</span><span class="sxs-lookup"><span data-stu-id="92083-147">Configure archiving, including whether to use Microsoft Exchange integration, the global policy and any site and user policies (when not using Microsoft Exchange integration for all data storage), and specific archiving options, such as critical mode and data export and purging.</span></span></p>
<p><span data-ttu-id="92083-148">如果使用 Microsoft Exchange 整合，視需要設定 Exchange 就地保留原則。</span><span class="sxs-lookup"><span data-stu-id="92083-148">If using Microsoft Exchange integration, configure Exchange In-Place Hold policies as appropriate.</span></span></p></td>
<td><p><span data-ttu-id="92083-149">RTCUniversalServerAdmins 群組 (僅限 Windows PowerShell) 或將使用者指派為 CSArchivingAdministrator 或 CSAdministrator 角色。</span><span class="sxs-lookup"><span data-stu-id="92083-149">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the CSArchivingAdministrator or CSAdministrator role.</span></span></p></td>
<td><p><span data-ttu-id="92083-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving Lync Server 2013 中</a>部署文件中。</span><span class="sxs-lookup"><span data-stu-id="92083-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="92083-151">Exchange 產品文件 （如果使用 Microsoft Exchange 整合）。</span><span class="sxs-lookup"><span data-stu-id="92083-151">Exchange product documentation (if using Microsoft Exchange integration).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a><span data-ttu-id="92083-152">部署 Lync Server 和 Microsoft Exchange 在不同樹系</span><span class="sxs-lookup"><span data-stu-id="92083-152">Deploying Lync Server and Microsoft Exchange in Different Forests</span></span>

<span data-ttu-id="92083-153">如果未在 Lync Server 相同的樹系中部署 Microsoft Exchange Server，您必須確定下列 Exchange Active Directory 屬性已同步處理至 Lync Server 部署所在之樹系：</span><span class="sxs-lookup"><span data-stu-id="92083-153">If Microsoft Exchange Server is not deployed in the same forest as Lync Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Lync Server is deployed:</span></span>

1.  <span data-ttu-id="92083-154">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="92083-154">msExchUserHoldPolicies</span></span>

2.  <span data-ttu-id="92083-155">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="92083-155">proxyAddresses</span></span>

<span data-ttu-id="92083-p107">此為多重值屬性。在同步處理此屬性之時，您必須將數值合併，不要予以取代，以便確保現有數值不會遺失。</span><span class="sxs-lookup"><span data-stu-id="92083-p107">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

