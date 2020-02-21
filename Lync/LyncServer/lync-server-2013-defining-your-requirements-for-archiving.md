---
title: Lync Server 2013： 定義封存需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Archiving
ms:assetid: ce0fc0f6-7704-4b80-bf19-a1fa9818fc7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205276(v=OCS.15)
ms:contentKeyID: 48185462
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21f7d374d3c4263f2341386d2c4471f50e4b719d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-archiving-in-lync-server-2013"></a><span data-ttu-id="94454-102">Lync Server 2013 中定義封存需求</span><span class="sxs-lookup"><span data-stu-id="94454-102">Defining your requirements for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94454-103">_**主題上次修改日期：** 2012年-10-09_</span><span class="sxs-lookup"><span data-stu-id="94454-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="94454-104">如果您的組織必須遵循法規合規性，您可以部署封存，若要啟用封存支援適用於 Lync Server 2013 立即訊息 (IM) 和會議 （會議）。</span><span class="sxs-lookup"><span data-stu-id="94454-104">If your organization must follow compliance regulations, you can deploy Archiving to enable archiving support for Lync Server 2013 instant messaging (IM) and conferencing (meetings).</span></span> <span data-ttu-id="94454-105">如需可以封存的內容類型的詳細資訊，請參閱[概觀的封存 Lync Server 2013 中](lync-server-2013-overview-of-archiving.md)規劃文件。</span><span class="sxs-lookup"><span data-stu-id="94454-105">For details about the type of content that can be archived, see [Overview of Archiving in Lync Server 2013](lync-server-2013-overview-of-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="94454-106">若要實作封存，您需要先決定要如何符合您的組織需求的封存。</span><span class="sxs-lookup"><span data-stu-id="94454-106">To implement Archiving, you need to first decide how to meet your organization’s requirements for Archiving.</span></span> <span data-ttu-id="94454-107">這需要決定下列：</span><span class="sxs-lookup"><span data-stu-id="94454-107">This requires determining the following:</span></span>

  - <span data-ttu-id="94454-108">**部署封存的時機**。</span><span class="sxs-lookup"><span data-stu-id="94454-108">**When to deploy Archiving**.</span></span> <span data-ttu-id="94454-109">您可以將封存部署為初始 Lync Server 2013 部署的一部分，或您可以將它新增至現有的部署。</span><span class="sxs-lookup"><span data-stu-id="94454-109">You can deploy Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="94454-110">您將部署封存使用拓撲產生器將它新增至您的拓撲，然後再發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="94454-110">You deploy Archiving by using Topology Builder to add it to your topology, and then publishing the topology.</span></span>

  - <span data-ttu-id="94454-111">**是否要封存內部或外部通訊**。</span><span class="sxs-lookup"><span data-stu-id="94454-111">**Whether to archive internal or external communications**.</span></span> <span data-ttu-id="94454-112">您可以啟用外部通訊 （包含您的內部網路外的至少一位使用者的通訊），或兩者的封存內部通訊 （內部部署使用者之間的通訊）。</span><span class="sxs-lookup"><span data-stu-id="94454-112">You can enable archiving for internal communications (communications between internal users), external communications (communications that include at least one user outside your internal network), or both.</span></span> <span data-ttu-id="94454-113">您可以指定這些選項的整個組織，或您可以將它們指定特定的網站與集區。</span><span class="sxs-lookup"><span data-stu-id="94454-113">You can specify these options for your entire organization, or you can specify them for specific sites and pools.</span></span> <span data-ttu-id="94454-114">根據預設，會啟用這兩個選項。</span><span class="sxs-lookup"><span data-stu-id="94454-114">By default, neither option is enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="94454-115">如果您使用 Microsoft Exchange 整合來儲存封存的資料，您的 Exchange 設定會控制是否要封存的 Lync 通訊。</span><span class="sxs-lookup"><span data-stu-id="94454-115">If you use Microsoft Exchange integration to store archived data, your Exchange settings control whether Lync communications are archived.</span></span> <span data-ttu-id="94454-116">如果您的部署包含多個樹系，您必須同步處理 Lync Server 和 Exchange 之間的設定。</span><span class="sxs-lookup"><span data-stu-id="94454-116">If your deployment includes multiple forests, you must synchronize the settings between Lync Server and Exchange.</span></span> <span data-ttu-id="94454-117">控制的內部或外部通訊封存 」 僅適用於 Lync 原則。</span><span class="sxs-lookup"><span data-stu-id="94454-117">Controlling archiving for internal or external communications is only available for Lync Policy.</span></span> <span data-ttu-id="94454-118">Exchange 整合封存，兩者都將封存或不會封存。</span><span class="sxs-lookup"><span data-stu-id="94454-118">For Exchange-integrated archiving, both of them will be archived or not archived.</span></span>

    
    </div>

  - <span data-ttu-id="94454-119">**為什麼要啟用封存**。</span><span class="sxs-lookup"><span data-stu-id="94454-119">**Why enable Archiving**.</span></span> <span data-ttu-id="94454-120">您可以啟用及停用整個部署在全域層級的封存，您可以啟用及停用特定的網站和使用者的封存。</span><span class="sxs-lookup"><span data-stu-id="94454-120">You can enable and disable Archiving for your entire deployment at a global level, and you can enable and disable Archiving for specific sites and users.</span></span> <span data-ttu-id="94454-121">您指定是否要啟用封存 IM 工作階段 （對等端對端），在每個這些層級，會議 （會議，也就是多方工作階段），或兩者。</span><span class="sxs-lookup"><span data-stu-id="94454-121">At each of these levels, you specify whether to enable archiving of IM sessions (peer-to-peer), conferences (meetings, which are multiparty sessions), or both.</span></span> <span data-ttu-id="94454-122">根據預設，會停用封存。</span><span class="sxs-lookup"><span data-stu-id="94454-122">By default, Archiving is disabled.</span></span>

  - <span data-ttu-id="94454-123">**如何重要封存為您組織中的使用者**。</span><span class="sxs-lookup"><span data-stu-id="94454-123">**How critical Archiving is to users in your organization**.</span></span> <span data-ttu-id="94454-124">如果封存是重要的組織中，您可以指定在封存失敗時封鎖 IM 與會議工作階段的關鍵模式下執行 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="94454-124">If archiving is mission-critical in your organization, you can specify that Lync Server 2013 run in critical mode, which blocks IM and conferencing sessions if archiving fails.</span></span> <span data-ttu-id="94454-125">例如：</span><span class="sxs-lookup"><span data-stu-id="94454-125">For example:</span></span>
    
      - <span data-ttu-id="94454-126">如果封存服務暫時無法將訊息傳送給資料庫佇列或將訊息插入資料庫，則在恢復封存支援之前，部署項目會同時封鎖 IM 與會議功能。</span><span class="sxs-lookup"><span data-stu-id="94454-126">If the Archiving service is temporarily unable to send a message to the database queue or insert a message into the database), both IM and conferencing functionality are blocked in the deployment until archiving support is restored.</span></span>
    
      - <span data-ttu-id="94454-127">當會議使用者上載檔案，但該檔案卻無法複製到封存檔案存放區時，部署項目會在問題解決之前封鎖會議功能，但不會封鎖 IM 功能。</span><span class="sxs-lookup"><span data-stu-id="94454-127">If a conferencing user uploads a file, but the file cannot be copied to the archiving file store, conferencing functionality is blocked in the deployment until the problem is resolved, but IM functionality is not blocked.</span></span>
    
    <span data-ttu-id="94454-128">您可以在全域層級、 網站層級和集區層級設定此選項。</span><span class="sxs-lookup"><span data-stu-id="94454-128">You can configure this option at the global level, site level, and pool level.</span></span> <span data-ttu-id="94454-129">根據預設，不會啟用關鍵模式。</span><span class="sxs-lookup"><span data-stu-id="94454-129">By default, critical mode is not enabled.</span></span>

  - <span data-ttu-id="94454-130">**是否要使用 Microsoft Exchange 整合**。</span><span class="sxs-lookup"><span data-stu-id="94454-130">**Whether to use Microsoft Exchange integration**.</span></span> <span data-ttu-id="94454-131">此選項，讓您的 Lync Server 封存資料和 Exchange 2013 封存的資料都會一起儲存在 Exchange 與您的 Exchange 2013 儲存體，封存存放區整合。</span><span class="sxs-lookup"><span data-stu-id="94454-131">This option integrates Archiving storage with your Exchange 2013 storage, so that your Lync Server archived data and Exchange 2013 archived data are stored together in Exchange.</span></span> <span data-ttu-id="94454-132">您可以使用 Microsoft Exchange 整合來儲存封存資料的使用者位於 Exchange 2013 中，如果他們的信箱已處於就地保留。</span><span class="sxs-lookup"><span data-stu-id="94454-132">You can use Microsoft Exchange integration for storage of archiving data for users who are homed on Exchange 2013, if their mailboxes have been put on In-Place Hold.</span></span> <span data-ttu-id="94454-133">如果您沒有 Exchange 2013 部署中，如果您不想整合，或如果您有任何 Lync 使用者不位於 Exchange 2013，您可以使用 SQL Server 來儲存封存的資料從 Lync 通訊部署個別封存資料庫。</span><span class="sxs-lookup"><span data-stu-id="94454-133">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync users who are not homed on Exchange 2013, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="94454-134">您可以在全域層級、 網站層級和集區層級設定 Microsoft Exchange 整合選項。</span><span class="sxs-lookup"><span data-stu-id="94454-134">You can configure the Microsoft Exchange integration option at the global level, site level, and pool level.</span></span> <span data-ttu-id="94454-135">根據預設，不會啟用 Microsoft Exchange 整合。</span><span class="sxs-lookup"><span data-stu-id="94454-135">By default, Microsoft Exchange integration is not enabled.</span></span>

  - <span data-ttu-id="94454-136">**如何封存資料是以進行管理**。</span><span class="sxs-lookup"><span data-stu-id="94454-136">**How archived data is to be managed**.</span></span> <span data-ttu-id="94454-137">封存資料庫不是長期保留和 Lync Server 2013 不提供 e-探索 （搜尋） 解決方案封存的資料，因此資料移至其他儲存區。</span><span class="sxs-lookup"><span data-stu-id="94454-137">The archiving database is not intended for long-term retention and Lync Server 2013 does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="94454-138">Lync Server 並提供您可以使用匯出封存的資料，以及而產生的封存資料的可搜尋記錄的工作階段匯出工具。</span><span class="sxs-lookup"><span data-stu-id="94454-138">Lync Server does provide a session export tool that you can use to export archived data, and which creates searchable transcripts of the archived data.</span></span> <span data-ttu-id="94454-139">全域原則，以及您建立每個網站與使用者原則，您可以啟用資料清除，並指定下列選項之一：</span><span class="sxs-lookup"><span data-stu-id="94454-139">For the global policy, and for each site and user policy that you create, you can enable data purging and specify one of the following options:</span></span>
    
      - <span data-ttu-id="94454-140">在經過指定的天數之後，同時清除匯出的封存資料與儲存的封存資料。</span><span class="sxs-lookup"><span data-stu-id="94454-140">Purge both exported archiving data and stored archiving data after a specific number of days.</span></span> <span data-ttu-id="94454-141">您可以指定的天數下限為 1 天。</span><span class="sxs-lookup"><span data-stu-id="94454-141">The minimum number of days that you can specify is one day.</span></span> <span data-ttu-id="94454-142">您可以指定的天數上限為 2562 天。</span><span class="sxs-lookup"><span data-stu-id="94454-142">The maximum number of days that you can specify is 2562 days.</span></span>
    
      - <span data-ttu-id="94454-p112">只清除匯出的封存資料。此選項會清除所有已經匯出，以及被工作階段匯出工具標示為可安心刪除的記錄。</span><span class="sxs-lookup"><span data-stu-id="94454-p112">Purge exported archiving data only. This option purges all records that have been exported and marked as safe to delete by the session export tool.</span></span>
    
    <span data-ttu-id="94454-145">您可以在全域層級、 網站層級和集區層級設定此選項。</span><span class="sxs-lookup"><span data-stu-id="94454-145">You can configure this option at the global level, site level, and pool level.</span></span> <span data-ttu-id="94454-146">預設不會啟用清除功能。</span><span class="sxs-lookup"><span data-stu-id="94454-146">By default, purging is not enabled.</span></span>

<span data-ttu-id="94454-147">您可以使用下列方法，以控制封存：</span><span class="sxs-lookup"><span data-stu-id="94454-147">You control Archiving by using the following methods:</span></span>

  - <span data-ttu-id="94454-148">**封存原則**。</span><span class="sxs-lookup"><span data-stu-id="94454-148">**Archiving policies**.</span></span> <span data-ttu-id="94454-149">您可以使用一或多個封存原則來啟用及停用內部和外部通訊封存。</span><span class="sxs-lookup"><span data-stu-id="94454-149">You use one or more Archiving policies to enable and disable archiving of internal and external communications.</span></span> <span data-ttu-id="94454-150">根據預設，會啟用任何封存。</span><span class="sxs-lookup"><span data-stu-id="94454-150">By default, no archiving is enabled.</span></span> <span data-ttu-id="94454-151">您可以啟用或停用封存內部通訊、 外部通訊或兩者部署中使用預設的全域原則。</span><span class="sxs-lookup"><span data-stu-id="94454-151">You enable or disable Archiving for internal communications, external communications, or both in your deployment by using the default global policy.</span></span> <span data-ttu-id="94454-152">您無法刪除全域原則。</span><span class="sxs-lookup"><span data-stu-id="94454-152">You cannot delete the global policy.</span></span> <span data-ttu-id="94454-153">您可以指定一或多個選用的網站原則，以啟用或停用的特定網站的內部和外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="94454-153">You can specify one or more optional site policies to enable or disable Archiving for internal and external communications for specific sites.</span></span> <span data-ttu-id="94454-154">您也可以指定一或多個使用者原則，以啟用或停用封存為特定使用者和使用者群組。</span><span class="sxs-lookup"><span data-stu-id="94454-154">You can also specify one or more user policies to enable or disable Archiving for specific users and user groups.</span></span> <span data-ttu-id="94454-155">使用者層級原則會覆寫網站原則。</span><span class="sxs-lookup"><span data-stu-id="94454-155">User-level policies override site policies.</span></span> <span data-ttu-id="94454-156">網站層級的原則會覆寫全域層級原則。</span><span class="sxs-lookup"><span data-stu-id="94454-156">Site-level policies override the global-level policies.</span></span> <span data-ttu-id="94454-157">僅針對特定使用者設定為使用原則實作使用者層級原則。</span><span class="sxs-lookup"><span data-stu-id="94454-157">User-level policies are implemented only for the specific users who are configured to use the policy.</span></span> <span data-ttu-id="94454-158">群組立即訊息與會議已封存只有在至少一個參與者原則設定啟用封存。</span><span class="sxs-lookup"><span data-stu-id="94454-158">Group instant messages and conferences are archived only if a policy for at least one of the participants is configured to enable archiving.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="94454-159">如果您使用 Microsoft Exchange 整合，Exchange 2013 原則會覆寫所有使用者都位於 Exchange 2013 伺服器上的 Lync Server 封存原則。</span><span class="sxs-lookup"><span data-stu-id="94454-159">If you use Microsoft Exchange integration, Exchange 2013 policies override Lync Server Archiving policies for all users homed on the Exchange 2013 servers.</span></span>

    
    </div>

  - <span data-ttu-id="94454-160">**封存組態**。</span><span class="sxs-lookup"><span data-stu-id="94454-160">**Archiving configurations**.</span></span> <span data-ttu-id="94454-161">使用下列一個或多個封存組態，以指定大部分的封存選項，將前文所述在本主題中，除了啟用內部與外部通訊封存 (如所述使用封存原則的設定上一個項目符號）。</span><span class="sxs-lookup"><span data-stu-id="94454-161">You use one or more Archiving configurations to specify most of the Archiving options that are described previously in this topic, except for enabling archiving of internal and external communications (configured using Archiving policies, as described in the previous bullet).</span></span> <span data-ttu-id="94454-162">封存組態包含選用的網站與集區設定與預設的全域設定。</span><span class="sxs-lookup"><span data-stu-id="94454-162">Archiving configurations include the default global configuration and optional site and pool configurations.</span></span> <span data-ttu-id="94454-163">您無法刪除全域設定。</span><span class="sxs-lookup"><span data-stu-id="94454-163">You cannot delete the global configuration.</span></span> <span data-ttu-id="94454-164">集區層級設定會覆寫網站層級設定。</span><span class="sxs-lookup"><span data-stu-id="94454-164">Pool-level configurations override site-level configurations.</span></span> <span data-ttu-id="94454-165">網站層級設定會覆寫全域層級設定。</span><span class="sxs-lookup"><span data-stu-id="94454-165">Site-level configurations override the global-level configuration.</span></span>

<span data-ttu-id="94454-166">需求分析的一部份，您必須決定如何設定全域封存設定資料庫和全域封存原則。</span><span class="sxs-lookup"><span data-stu-id="94454-166">As part of your requirements analysis, you need to determine how to configure the global Archiving configuration and global Archiving policy.</span></span> <span data-ttu-id="94454-167">您也需要判斷您的任何網站層級的封存組態、 集區層級的封存組態、 網站層級的封存原則和使用者層級的封存原則的需求。</span><span class="sxs-lookup"><span data-stu-id="94454-167">You also need to determine your requirements for any site-level Archiving configurations, pool-level Archiving configurations, site-level Archiving policies, and user-level Archiving policies.</span></span>

<span data-ttu-id="94454-168">如果您的一個前端集區或 Standard Edition server 部署封存，您應該然後加以啟用的所有其他前端集區和 Standard Edition server 部署中。</span><span class="sxs-lookup"><span data-stu-id="94454-168">If you deploy Archiving for one Front End pool or Standard Edition server, you should then enable it for all other Front End pools and Standard Edition servers in your deployment.</span></span> <span data-ttu-id="94454-169">您需要這麼做，因為其通訊所要封存的使用者可以邀請加入群組 IM 交談或會議裝載於另一個集區上。</span><span class="sxs-lookup"><span data-stu-id="94454-169">You need to do this because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool.</span></span> <span data-ttu-id="94454-170">如果主控交談或會議的集區上未啟用封存，可能不會封存所有會議資料。</span><span class="sxs-lookup"><span data-stu-id="94454-170">If archiving is not enabled on the pool where the conversation or meeting is hosted, all conference data may not be archived.</span></span> <span data-ttu-id="94454-171">封存來封存已啟用的使用者和所有 IM 訊息，仍然可以使用，但會議內容和事件可能不會封存。</span><span class="sxs-lookup"><span data-stu-id="94454-171">Archiving will still work for archiving enabled users and all IM messages, but conferencing content and events may not be archived.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94454-172">若要啟用同時維持貴組織的安全性標準，Lync Server 2013 系統管理工作的委派&nbsp;使用角色型存取控制 (RBAC)。</span><span class="sxs-lookup"><span data-stu-id="94454-172">To enable delegation of administrative tasks while maintaining your organization's security standards, Lync Server 2013&nbsp;uses role-based access control (RBAC).</span></span> <span data-ttu-id="94454-173">使用 RBAC，管理特殊權限會授與預先定義的系統管理角色指派的使用者。</span><span class="sxs-lookup"><span data-stu-id="94454-173">With RBAC, administrative privilege is granted by assigning users to predefined administrative roles.</span></span> <span data-ttu-id="94454-174">若要設定 Lync 封存原則和封存組態，使用者必須指派給 CsArchivingAdministrator 角色 (除非組態是直接在其中要部署封存，而不是從遠端伺服器上從另一部電腦)。</span><span class="sxs-lookup"><span data-stu-id="94454-174">To configure Lync Archiving policies and Archiving configurations, the user must be assigned to the CsArchivingAdministrator role (unless the configuration is done directly on the server where Archiving is deployed, instead of remotely from another computer).</span></span> <span data-ttu-id="94454-175">如需有關 RBAC 的詳細資訊，請參閱規劃文件中的<A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Lync Server 2013 中角色型存取控制</A>。</span><span class="sxs-lookup"><span data-stu-id="94454-175">For details about RBAC, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="94454-176">使用者權限、 權限，和封存部署所需的角色清單，請參閱<A href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 中的封存的部署檢查清單</A>，這是在規劃文件和部署文件中使用。</span><span class="sxs-lookup"><span data-stu-id="94454-176">For a list of the user rights, permissions, and roles required for archiving deployment, see <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</A>, which is available in both the Planning documentation and the Deployment documentation.</span></span><BR><span data-ttu-id="94454-177">如果您使用 Microsoft Exchange 整合，設定 Exchange 原則，會需要適當的系統管理員權限和權限。</span><span class="sxs-lookup"><span data-stu-id="94454-177">If you use Microsoft Exchange integration, configuration of Exchange policies requires appropriate administrator rights and permissions.</span></span> <span data-ttu-id="94454-178">如需詳細資訊，請參閱 < Exchange 2013 文件。</span><span class="sxs-lookup"><span data-stu-id="94454-178">For details, see the Exchange 2013 documentation.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

