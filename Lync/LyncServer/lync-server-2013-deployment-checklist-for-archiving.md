---
title: Lync Server 2013：封存的部署檢查單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51c556dd288ff3539bbf2f4de816eab3a544b847
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a><span data-ttu-id="a009b-102">Lync Server 2013 中封存的部署檢查單</span><span class="sxs-lookup"><span data-stu-id="a009b-102">Deployment checklist for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a009b-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="a009b-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="a009b-104">存檔會自動安裝在 Lync Server 2013 部署中的每個前端伺服器上，但您仍需先設定，然後才能使用。</span><span class="sxs-lookup"><span data-stu-id="a009b-104">Archiving is automatically installed on each Front End Server in your Lync Server 2013 deployment, but you still need to set it up before you can use it.</span></span> <span data-ttu-id="a009b-105">進行設定所需的步驟，如本節所總結，將歸檔部署組成。</span><span class="sxs-lookup"><span data-stu-id="a009b-105">The steps required to set it up, as summarized in this section, constitute the deployment of Archiving.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="a009b-106">部署順序</span><span class="sxs-lookup"><span data-stu-id="a009b-106">Deployment Sequence</span></span>

<span data-ttu-id="a009b-107">設定存檔的方式取決於您選擇的儲存空間選項：</span><span class="sxs-lookup"><span data-stu-id="a009b-107">How you set up Archiving depends on which storage option you choose:</span></span>

  - <span data-ttu-id="a009b-108">如果您針對部署中的所有使用者使用 Microsoft Exchange 整合，就不需要為使用者設定 Lync Server 2013 的歸檔原則。</span><span class="sxs-lookup"><span data-stu-id="a009b-108">If you use Microsoft Exchange integration for all users in your deployment, you don’t need to configure Lync Server 2013 Archiving policies for your users.</span></span> <span data-ttu-id="a009b-109">相反地，請設定您的 Exchange 就地保留原則，以支援駐留在 Exchange 2013 的使用者的封存，並將其信箱放在適當的位置。</span><span class="sxs-lookup"><span data-stu-id="a009b-109">Instead, configure your Exchange In-Place Hold policies to support archiving for users homed on Exchange 2013, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="a009b-110">如需有關設定這些原則的詳細資訊，請參閱 Exchange 2013 產品檔。</span><span class="sxs-lookup"><span data-stu-id="a009b-110">For details about configuring these policies, see the Exchange 2013 product documentation.</span></span>

  - <span data-ttu-id="a009b-111">如果您不是針對您部署中的所有使用者使用 Microsoft Exchange 整合，您必須先在拓撲中新增 Lync Server 封存資料庫（SQL Server 資料庫），然後發佈它，以及為使用者設定原則和設定，才能存檔這些使用者的資料。</span><span class="sxs-lookup"><span data-stu-id="a009b-111">If you do not use Microsoft Exchange integration for all users in your deployment, you need to add Lync Server Archiving databases (SQL Server databases) to your topology and then publish it, as well as configure policies and settings for your users, before you can archive data for those users.</span></span> <span data-ttu-id="a009b-112">您可以在部署初始拓撲或部署至少一個前端池或標準版伺服器之後，部署存檔資料庫。</span><span class="sxs-lookup"><span data-stu-id="a009b-112">You can deploy Archiving databases at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span> <span data-ttu-id="a009b-113">本檔說明如何將存檔資料庫新增至現有的部署。</span><span class="sxs-lookup"><span data-stu-id="a009b-113">This document describes how to deploy Archiving databases by adding them to an existing deployment.</span></span>

<span data-ttu-id="a009b-114">如果您在一個前端池或標準版伺服器中啟用封存，您應該針對部署中的所有其他前端池和標準版伺服器啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="a009b-114">If you enable archiving in one Front End pool or Standard Edition server, you should enable it for all other Front End pools and Standard Edition servers in your deployment.</span></span> <span data-ttu-id="a009b-115">這是因為需要封存其通訊的使用者可以受邀加入群組 IM 交談或託管于不同的池中的會議。</span><span class="sxs-lookup"><span data-stu-id="a009b-115">This is because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool.</span></span> <span data-ttu-id="a009b-116">如果在託管或會議所在的池中未啟用 [封存]，則可能不會封存整個會話。</span><span class="sxs-lookup"><span data-stu-id="a009b-116">If archiving is not enabled on the pool where the conversation or meeting is hosted, the complete session may not be archived.</span></span> <span data-ttu-id="a009b-117">在這些情況下，擁有封存的使用者的 Im 仍可歸檔，但不適用於會議內容檔案，以及會議加入或離開活動。</span><span class="sxs-lookup"><span data-stu-id="a009b-117">In these cases, IMs with archiving-enabled users still can be archived, but not for conferencing content files, and conference join or leave events.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a009b-118">如果您組織中的存檔是符合合規性的理由，請務必在適當的層級部署封存、設定原則及其他選項，並針對所有適當的使用者啟用封存，然後再針對 Lync Server 2013 啟用這些使用者。</span><span class="sxs-lookup"><span data-stu-id="a009b-118">If archiving is critical in your organization for compliance reasons, be sure to deploy Archiving, configure policies and other options at the appropriate level, and enable it for all appropriate users, before you enable those users for Lync Server 2013.</span></span>



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a><span data-ttu-id="a009b-119">存檔部署程式</span><span class="sxs-lookup"><span data-stu-id="a009b-119">Archiving Deployment Process</span></span>

<span data-ttu-id="a009b-120">下表概要說明在現有拓撲中部署存檔所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="a009b-120">The following table provides an overview of the steps required to deploy archiving in an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a009b-121">分</span><span class="sxs-lookup"><span data-stu-id="a009b-121">Phase</span></span></th>
<th><span data-ttu-id="a009b-122">步驟</span><span class="sxs-lookup"><span data-stu-id="a009b-122">Steps</span></span></th>
<th><span data-ttu-id="a009b-123">角色和群組成員資格</span><span class="sxs-lookup"><span data-stu-id="a009b-123">Roles and group memberships</span></span></th>
<th><span data-ttu-id="a009b-124">文件</span><span class="sxs-lookup"><span data-stu-id="a009b-124">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a009b-125"><strong>安裝必備的硬體和軟體</strong></span><span class="sxs-lookup"><span data-stu-id="a009b-125"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="a009b-126">若要使用 Microsoft Exchange 整合（使用 Exchange 2013 來封存部分或所有使用者的儲存空間），您需要現有的 Exchange 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="a009b-126">To use Microsoft Exchange integration (using Exchange 2013 for archiving storage for some or all users), you need an existing Exchange 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="a009b-127">若要使用個別的存檔資料庫（使用 SQL Server 資料庫）來儲存部分或所有使用者的儲存空間，請在伺服器上將儲存封存資料的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="a009b-127">To use separate Archiving databases (using SQL Server databases) for archiving storage for some or all users, SQL Server on the server that will store archiving data.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="a009b-128">封存是在企業版池和標準版伺服器的前端伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="a009b-128">Archiving runs on Front End Servers of an Enterprise pool and Standard Edition servers.</span></span> <span data-ttu-id="a009b-129">除了安裝這些伺服器所需的其他硬體或軟體需求之外，它還沒有其他硬體或軟體需求。</span><span class="sxs-lookup"><span data-stu-id="a009b-129">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span>


</div></td>
<td><p><span data-ttu-id="a009b-130">屬於本機管理員群組成員的網域使用者。</span><span class="sxs-lookup"><span data-stu-id="a009b-130">Domain user who is a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="a009b-131"><a href="lync-server-2013-supported-hardware.md">支援檔中 Lync Server 2013 支援的硬體</a>。</span><span class="sxs-lookup"><span data-stu-id="a009b-131"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="a009b-132">支援檔中的<a href="lync-server-2013-server-software-and-infrastructure-support.md">Lync server 2013 中的伺服器軟體和基礎結構支援</a>。</span><span class="sxs-lookup"><span data-stu-id="a009b-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="a009b-133">規劃檔中的<a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013 中的存檔技術需求</a>。</span><span class="sxs-lookup"><span data-stu-id="a009b-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="a009b-134">在部署檔中<a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">設定在 Lync Server 2013 中封存的系統和基礎結構</a>。</span><span class="sxs-lookup"><span data-stu-id="a009b-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Setting up systems and infrastructure for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="a009b-135">支援檔中的<a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Lync server 2013 Exchange Server 和 SharePoint 整合支援</a>。</span><span class="sxs-lookup"><span data-stu-id="a009b-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange Server and SharePoint integration support in Lync Server 2013</a> in the Supportability documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a009b-136"><strong>建立適當的內部拓朴，以支援封存（僅適用于您部署中的所有使用者都不使用 Microsoft Exchange 整合）</strong></span><span class="sxs-lookup"><span data-stu-id="a009b-136"><strong>Create the appropriate internal topology to support archiving (only if not using Microsoft Exchange integration for all users in your deployment)</strong></span></span></p></td>
<td><p><span data-ttu-id="a009b-137">執行拓撲建立器，將 Lync Server 2013 封存資料庫（SQL Server 資料庫）新增到拓撲結構，然後發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="a009b-137">Run Topology Builder to add Lync Server 2013 Archiving databases (SQL Server databases) to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="a009b-138">若要定義拓撲以納入封存資料庫，該帳戶是 [本機使用者] 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="a009b-138">To define a topology to incorporate Archiving databases, an account that is a member of the local users group.</span></span></p>
<p><span data-ttu-id="a009b-139">若要發佈拓朴，該帳戶是網域系統管理員群組和 RTCUniversalServerAdmins 群組的成員，且在檔案共用上擁有 [完全控制] 許可權（讀取/寫入/修改），以用於 Lync Server 2013 檔案存放區（讓拓撲建立員可以設定所需的 Dacl）。</span><span class="sxs-lookup"><span data-stu-id="a009b-139">To publish the topology, an account that is a member of the domain admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="a009b-140">在部署檔中<a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">將存檔資料庫新增至現有的 Lync Server 2013 部署</a>。</span><span class="sxs-lookup"><span data-stu-id="a009b-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adding Archiving databases to an existing Lync Server 2013 Deployment</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a009b-141"><strong>設定伺服器對伺服器驗證（僅在使用 Microsoft Exchange 整合時）</strong></span><span class="sxs-lookup"><span data-stu-id="a009b-141"><strong>Configure server-to-server authentication (only if using Microsoft Exchange integration)</strong></span></span></p></td>
<td><p><span data-ttu-id="a009b-142">設定伺服器以啟用 Lync Server 2013 與 Exchange 2013 之間的驗證。</span><span class="sxs-lookup"><span data-stu-id="a009b-142">Configure servers to enable authentication between Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="a009b-143">我們建議您執行<strong>測試 CsExchangeStorageConnectivity testuser_sipUri –資料夾 Dumpster</strong> ，以驗證 Exchange 封存儲存連接，才能啟用封存。</span><span class="sxs-lookup"><span data-stu-id="a009b-143">We recommend running <strong>Test-CsExchangeStorageConnectivity testuser_sipUri –Folder Dumpster</strong> to validate Exchange Archiving storage connectivity before enabling archiving.</span></span></p></td>
<td><p><span data-ttu-id="a009b-144">具有適當許可權的帳戶，可在伺服器上管理證書。</span><span class="sxs-lookup"><span data-stu-id="a009b-144">An account with the appropriate permissions for managing certificates on the servers.</span></span></p></td>
<td><p><span data-ttu-id="a009b-145">在部署檔或操作檔中<a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">管理 Lync server 2013 中的伺服器到伺服器驗證（OAuth）與合作夥伴應用程式</a>。</span><span class="sxs-lookup"><span data-stu-id="a009b-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</a> in the Deployment documentation or the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a009b-146"><strong>設定封存原則和配置</strong></span><span class="sxs-lookup"><span data-stu-id="a009b-146"><strong>Configure archiving policies and configurations</strong></span></span></p></td>
<td><p><span data-ttu-id="a009b-147">設定封存，包括是否使用 Microsoft Exchange 整合、全域原則及任何網站和使用者原則（不使用 Microsoft Exchange 整合進行所有資料儲存），以及特定的歸檔選項（例如，重要模式與資料）匯出和清除。</span><span class="sxs-lookup"><span data-stu-id="a009b-147">Configure archiving, including whether to use Microsoft Exchange integration, the global policy and any site and user policies (when not using Microsoft Exchange integration for all data storage), and specific archiving options, such as critical mode and data export and purging.</span></span></p>
<p><span data-ttu-id="a009b-148">如果您使用的是 Microsoft Exchange 整合，請視需要設定 Exchange 就地保留原則。</span><span class="sxs-lookup"><span data-stu-id="a009b-148">If using Microsoft Exchange integration, configure Exchange In-Place Hold policies as appropriate.</span></span></p></td>
<td><p><span data-ttu-id="a009b-149">RTCUniversalServerAdmins 群組（僅限 Windows PowerShell）或將使用者指派給 CSArchivingAdministrator 或 CSAdministrator 角色。</span><span class="sxs-lookup"><span data-stu-id="a009b-149">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the CSArchivingAdministrator or CSAdministrator role.</span></span></p></td>
<td><p><span data-ttu-id="a009b-150">在部署檔中設定<a href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013 中的封存支援</a>。</span><span class="sxs-lookup"><span data-stu-id="a009b-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="a009b-151">Exchange 產品檔（如果您使用的是 Microsoft Exchange 整合）。</span><span class="sxs-lookup"><span data-stu-id="a009b-151">Exchange product documentation (if using Microsoft Exchange integration).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a><span data-ttu-id="a009b-152">在不同的林中部署 Lync Server 和 Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="a009b-152">Deploying Lync Server and Microsoft Exchange in Different Forests</span></span>

<span data-ttu-id="a009b-153">如果 Microsoft Exchange Server 未部署在 Lync Server 所在的林中，您必須確認下列 Exchange Active Directory 屬性已同步處理到部署 Lync Server 的林：</span><span class="sxs-lookup"><span data-stu-id="a009b-153">If Microsoft Exchange Server is not deployed in the same forest as Lync Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Lync Server is deployed:</span></span>

1.  <span data-ttu-id="a009b-154">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="a009b-154">msExchUserHoldPolicies</span></span>

2.  <span data-ttu-id="a009b-155">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="a009b-155">proxyAddresses</span></span>

<span data-ttu-id="a009b-156">這是多重值屬性。</span><span class="sxs-lookup"><span data-stu-id="a009b-156">This is a multi-value attribute.</span></span> <span data-ttu-id="a009b-157">同步處理此屬性時，您必須合併值，而不要將其取代，以確保現有值不會遺失。</span><span class="sxs-lookup"><span data-stu-id="a009b-157">When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

