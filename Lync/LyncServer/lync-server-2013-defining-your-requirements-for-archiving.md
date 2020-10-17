---
title: Lync Server 2013：定義封存需求
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
ms.openlocfilehash: 4a5f789f390e1cf104a0dc1b3a10a4116ba38c03
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521660"
---
# <a name="defining-your-requirements-for-archiving-in-lync-server-2013"></a><span data-ttu-id="3d056-102">在 Lync Server 2013 中定義封存需求</span><span class="sxs-lookup"><span data-stu-id="3d056-102">Defining your requirements for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d056-103">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="3d056-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="3d056-104">如果您的組織必須遵循相容性法規，您可以部署封存，以啟用 Lync Server 2013 立即訊息 (IM) 和會議 (會議) 的封存支援。</span><span class="sxs-lookup"><span data-stu-id="3d056-104">If your organization must follow compliance regulations, you can deploy Archiving to enable archiving support for Lync Server 2013 instant messaging (IM) and conferencing (meetings).</span></span> <span data-ttu-id="3d056-105">如需可封存之內容類型的詳細資訊，請參閱規劃檔中的封存 [簡介 In Lync Server 2013](lync-server-2013-overview-of-archiving.md) 。</span><span class="sxs-lookup"><span data-stu-id="3d056-105">For details about the type of content that can be archived, see [Overview of Archiving in Lync Server 2013](lync-server-2013-overview-of-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="3d056-106">若要執行封存，您必須先決定如何符合組織的封存需求。</span><span class="sxs-lookup"><span data-stu-id="3d056-106">To implement Archiving, you need to first decide how to meet your organization’s requirements for Archiving.</span></span> <span data-ttu-id="3d056-107">這需要判斷下列專案：</span><span class="sxs-lookup"><span data-stu-id="3d056-107">This requires determining the following:</span></span>

  - <span data-ttu-id="3d056-108">**何時部署**封存。</span><span class="sxs-lookup"><span data-stu-id="3d056-108">**When to deploy Archiving**.</span></span> <span data-ttu-id="3d056-109">您可以將封存部署為初始 Lync Server 2013 部署的一部分，也可以將其新增至現有的部署。</span><span class="sxs-lookup"><span data-stu-id="3d056-109">You can deploy Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="3d056-110">您可以使用拓撲產生器來部署封存，將其新增至您的拓撲，然後發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="3d056-110">You deploy Archiving by using Topology Builder to add it to your topology, and then publishing the topology.</span></span>

  - <span data-ttu-id="3d056-111">**是否封存內部或外部通訊**。</span><span class="sxs-lookup"><span data-stu-id="3d056-111">**Whether to archive internal or external communications**.</span></span> <span data-ttu-id="3d056-112">您可以對內部使用者之間的通訊 (通訊啟用內部通訊的封存) 、外部通訊 (在內部網路以外至少包含一位使用者的通訊) ，或是兩者。</span><span class="sxs-lookup"><span data-stu-id="3d056-112">You can enable archiving for internal communications (communications between internal users), external communications (communications that include at least one user outside your internal network), or both.</span></span> <span data-ttu-id="3d056-113">您可以為整個組織指定這些選項，也可以為特定網站和集區指定這些選項。</span><span class="sxs-lookup"><span data-stu-id="3d056-113">You can specify these options for your entire organization, or you can specify them for specific sites and pools.</span></span> <span data-ttu-id="3d056-114">根據預設，這兩個選項都不會啟用。</span><span class="sxs-lookup"><span data-stu-id="3d056-114">By default, neither option is enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3d056-115">如果您使用 Microsoft Exchange 整合來儲存封存的資料，您的 Exchange 設定會控制是否要封存 Lync 通訊。</span><span class="sxs-lookup"><span data-stu-id="3d056-115">If you use Microsoft Exchange integration to store archived data, your Exchange settings control whether Lync communications are archived.</span></span> <span data-ttu-id="3d056-116">如果您的部署包含多個樹系，您必須同步處理 Lync Server 與 Exchange 之間的設定。</span><span class="sxs-lookup"><span data-stu-id="3d056-116">If your deployment includes multiple forests, you must synchronize the settings between Lync Server and Exchange.</span></span> <span data-ttu-id="3d056-117">控制內部或外部通訊的封存只適用于 Lync 原則。</span><span class="sxs-lookup"><span data-stu-id="3d056-117">Controlling archiving for internal or external communications is only available for Lync Policy.</span></span> <span data-ttu-id="3d056-118">針對 Exchange 整合型封存，這兩項都將會封存或未封存。</span><span class="sxs-lookup"><span data-stu-id="3d056-118">For Exchange-integrated archiving, both of them will be archived or not archived.</span></span>

    
    </div>

  - <span data-ttu-id="3d056-119">**為何啟用**封存。</span><span class="sxs-lookup"><span data-stu-id="3d056-119">**Why enable Archiving**.</span></span> <span data-ttu-id="3d056-120">您可以為全域層級的整個部署啟用和停用封存，也可以啟用和停用特定網站和使用者的封存。</span><span class="sxs-lookup"><span data-stu-id="3d056-120">You can enable and disable Archiving for your entire deployment at a global level, and you can enable and disable Archiving for specific sites and users.</span></span> <span data-ttu-id="3d056-121">在每個層級中，您會指定是否要啟用 IM 會話的封存 (對等) 、會議 (會議，也就是) 的多方會話，也是兩者。</span><span class="sxs-lookup"><span data-stu-id="3d056-121">At each of these levels, you specify whether to enable archiving of IM sessions (peer-to-peer), conferences (meetings, which are multiparty sessions), or both.</span></span> <span data-ttu-id="3d056-122">預設會停用封存。</span><span class="sxs-lookup"><span data-stu-id="3d056-122">By default, Archiving is disabled.</span></span>

  - <span data-ttu-id="3d056-123">**組織中使用者的重要**封存。</span><span class="sxs-lookup"><span data-stu-id="3d056-123">**How critical Archiving is to users in your organization**.</span></span> <span data-ttu-id="3d056-124">如果您的組織中的封存非常重要，您可以指定 Lync Server 2013 在重要模式中執行，這會在封存失敗時封鎖 IM 和會議會話。</span><span class="sxs-lookup"><span data-stu-id="3d056-124">If archiving is mission-critical in your organization, you can specify that Lync Server 2013 run in critical mode, which blocks IM and conferencing sessions if archiving fails.</span></span> <span data-ttu-id="3d056-125">例如：</span><span class="sxs-lookup"><span data-stu-id="3d056-125">For example:</span></span>
    
      - <span data-ttu-id="3d056-126">如果封存服務暫時無法將訊息傳送給資料庫佇列或將訊息插入資料庫，則在恢復封存支援之前，部署項目會同時封鎖 IM 與會議功能。</span><span class="sxs-lookup"><span data-stu-id="3d056-126">If the Archiving service is temporarily unable to send a message to the database queue or insert a message into the database), both IM and conferencing functionality are blocked in the deployment until archiving support is restored.</span></span>
    
      - <span data-ttu-id="3d056-127">當會議使用者上載檔案，但該檔案卻無法複製到封存檔案存放區時，部署項目會在問題解決之前封鎖會議功能，但不會封鎖 IM 功能。</span><span class="sxs-lookup"><span data-stu-id="3d056-127">If a conferencing user uploads a file, but the file cannot be copied to the archiving file store, conferencing functionality is blocked in the deployment until the problem is resolved, but IM functionality is not blocked.</span></span>
    
    <span data-ttu-id="3d056-128">您可以在全域層級、網站層級及集區層級設定此選項。</span><span class="sxs-lookup"><span data-stu-id="3d056-128">You can configure this option at the global level, site level, and pool level.</span></span> <span data-ttu-id="3d056-129">根據預設，不會啟用重要模式。</span><span class="sxs-lookup"><span data-stu-id="3d056-129">By default, critical mode is not enabled.</span></span>

  - <span data-ttu-id="3d056-130">**是否使用 Microsoft Exchange 整合**。</span><span class="sxs-lookup"><span data-stu-id="3d056-130">**Whether to use Microsoft Exchange integration**.</span></span> <span data-ttu-id="3d056-131">此選項會將封存儲存與 Exchange 2013 儲存整合，讓您的 Lync Server 封存資料和 Exchange 2013 封存資料會一起儲存在 Exchange 中。</span><span class="sxs-lookup"><span data-stu-id="3d056-131">This option integrates Archiving storage with your Exchange 2013 storage, so that your Lync Server archived data and Exchange 2013 archived data are stored together in Exchange.</span></span> <span data-ttu-id="3d056-132">您可以使用 Microsoft Exchange 整合，儲存位於 Exchange 2013 （如果使用者的信箱已放在 In-Place 暫止）的封存資料。</span><span class="sxs-lookup"><span data-stu-id="3d056-132">You can use Microsoft Exchange integration for storage of archiving data for users who are homed on Exchange 2013, if their mailboxes have been put on In-Place Hold.</span></span> <span data-ttu-id="3d056-133">如果您沒有 Exchange 2013 部署，或者您不想要將其與其整合，或者如果您有任何 Lync 使用者未裝載于 Exchange 2013，您可以使用 SQL Server 將封存的資料儲存在 Lync 通訊中，以部署個別的封存資料庫。</span><span class="sxs-lookup"><span data-stu-id="3d056-133">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync users who are not homed on Exchange 2013, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="3d056-134">您可以在全域層級、網站層級及集區層級設定 Microsoft Exchange 整合選項。</span><span class="sxs-lookup"><span data-stu-id="3d056-134">You can configure the Microsoft Exchange integration option at the global level, site level, and pool level.</span></span> <span data-ttu-id="3d056-135">依預設，不會啟用 Microsoft Exchange 整合功能。</span><span class="sxs-lookup"><span data-stu-id="3d056-135">By default, Microsoft Exchange integration is not enabled.</span></span>

  - <span data-ttu-id="3d056-136">封存**資料的管理方式**。</span><span class="sxs-lookup"><span data-stu-id="3d056-136">**How archived data is to be managed**.</span></span> <span data-ttu-id="3d056-137">封存資料庫不適用於長期保留，而 Lync Server 2013 不會提供電子探索 (搜尋) 的封存資料的解決方案，因此必須將資料移至其他儲存區。</span><span class="sxs-lookup"><span data-stu-id="3d056-137">The archiving database is not intended for long-term retention and Lync Server 2013 does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="3d056-138">Lync Server 提供一種會話匯出工具，可供您用來匯出封存的資料，並可建立已封存資料的可搜尋記錄。</span><span class="sxs-lookup"><span data-stu-id="3d056-138">Lync Server does provide a session export tool that you can use to export archived data, and which creates searchable transcripts of the archived data.</span></span> <span data-ttu-id="3d056-139">針對全域原則，以及您建立的每個網站和使用者原則，您可以啟用資料清除，並指定下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="3d056-139">For the global policy, and for each site and user policy that you create, you can enable data purging and specify one of the following options:</span></span>
    
      - <span data-ttu-id="3d056-140">在經過指定的天數之後，同時清除匯出的封存資料與儲存的封存資料。</span><span class="sxs-lookup"><span data-stu-id="3d056-140">Purge both exported archiving data and stored archiving data after a specific number of days.</span></span> <span data-ttu-id="3d056-141">您可以指定的天數下限為 1 天。</span><span class="sxs-lookup"><span data-stu-id="3d056-141">The minimum number of days that you can specify is one day.</span></span> <span data-ttu-id="3d056-142">您可以指定的天數上限為 2562 天。</span><span class="sxs-lookup"><span data-stu-id="3d056-142">The maximum number of days that you can specify is 2562 days.</span></span>
    
      - <span data-ttu-id="3d056-p112">只清除匯出的封存資料。此選項會清除所有已經匯出，以及被工作階段匯出工具標示為可安心刪除的記錄。</span><span class="sxs-lookup"><span data-stu-id="3d056-p112">Purge exported archiving data only. This option purges all records that have been exported and marked as safe to delete by the session export tool.</span></span>
    
    <span data-ttu-id="3d056-145">您可以在全域層級、網站層級及集區層級設定此選項。</span><span class="sxs-lookup"><span data-stu-id="3d056-145">You can configure this option at the global level, site level, and pool level.</span></span> <span data-ttu-id="3d056-146">預設不會啟用清除功能。</span><span class="sxs-lookup"><span data-stu-id="3d056-146">By default, purging is not enabled.</span></span>

<span data-ttu-id="3d056-147">您可以使用下列方法來控制封存：</span><span class="sxs-lookup"><span data-stu-id="3d056-147">You control Archiving by using the following methods:</span></span>

  - <span data-ttu-id="3d056-148">封存**原則**。</span><span class="sxs-lookup"><span data-stu-id="3d056-148">**Archiving policies**.</span></span> <span data-ttu-id="3d056-149">您可以使用一或多個封存原則來啟用和停用內部及外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="3d056-149">You use one or more Archiving policies to enable and disable archiving of internal and external communications.</span></span> <span data-ttu-id="3d056-150">根據預設，不會啟用任何封存。</span><span class="sxs-lookup"><span data-stu-id="3d056-150">By default, no archiving is enabled.</span></span> <span data-ttu-id="3d056-151">您可以使用預設全域原則，在部署中啟用或停用內部通訊、外部通訊或兩者的封存。</span><span class="sxs-lookup"><span data-stu-id="3d056-151">You enable or disable Archiving for internal communications, external communications, or both in your deployment by using the default global policy.</span></span> <span data-ttu-id="3d056-152">您無法刪除全域原則。</span><span class="sxs-lookup"><span data-stu-id="3d056-152">You cannot delete the global policy.</span></span> <span data-ttu-id="3d056-153">您可以指定一或多個選用的網站原則，針對特定網站啟用或停用內部及外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="3d056-153">You can specify one or more optional site policies to enable or disable Archiving for internal and external communications for specific sites.</span></span> <span data-ttu-id="3d056-154">您也可以指定一或多個使用者原則，以啟用或停用特定使用者和使用者群組的封存。</span><span class="sxs-lookup"><span data-stu-id="3d056-154">You can also specify one or more user policies to enable or disable Archiving for specific users and user groups.</span></span> <span data-ttu-id="3d056-155">使用者層級原則會覆寫網站原則。</span><span class="sxs-lookup"><span data-stu-id="3d056-155">User-level policies override site policies.</span></span> <span data-ttu-id="3d056-156">網站層級原則會覆寫全域層級原則。</span><span class="sxs-lookup"><span data-stu-id="3d056-156">Site-level policies override the global-level policies.</span></span> <span data-ttu-id="3d056-157">只有設定為使用原則的特定使用者才能執行使用者層級原則。</span><span class="sxs-lookup"><span data-stu-id="3d056-157">User-level policies are implemented only for the specific users who are configured to use the policy.</span></span> <span data-ttu-id="3d056-158">只有在至少有一位參與者的原則設定為啟用封存時，才會封存「立即訊息和會議」。</span><span class="sxs-lookup"><span data-stu-id="3d056-158">Group instant messages and conferences are archived only if a policy for at least one of the participants is configured to enable archiving.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3d056-159">如果您使用 Microsoft Exchange 整合，Exchange 2013 原則會覆寫位於 Exchange 2013 伺服器上之所有使用者的 Lync Server 封存原則。</span><span class="sxs-lookup"><span data-stu-id="3d056-159">If you use Microsoft Exchange integration, Exchange 2013 policies override Lync Server Archiving policies for all users homed on the Exchange 2013 servers.</span></span>

    
    </div>

  - <span data-ttu-id="3d056-160">封存**設定。**</span><span class="sxs-lookup"><span data-stu-id="3d056-160">**Archiving configurations**.</span></span> <span data-ttu-id="3d056-161">您可以使用一或多個封存設定來指定本主題先前所述的大部分封存選項，但不允許使用封存原則來設定內部和外部通訊 (，如先前專案符號) 所述。</span><span class="sxs-lookup"><span data-stu-id="3d056-161">You use one or more Archiving configurations to specify most of the Archiving options that are described previously in this topic, except for enabling archiving of internal and external communications (configured using Archiving policies, as described in the previous bullet).</span></span> <span data-ttu-id="3d056-162">封存設定包括預設全域設定和選用的網站及集區設定。</span><span class="sxs-lookup"><span data-stu-id="3d056-162">Archiving configurations include the default global configuration and optional site and pool configurations.</span></span> <span data-ttu-id="3d056-163">您無法刪除全域設定。</span><span class="sxs-lookup"><span data-stu-id="3d056-163">You cannot delete the global configuration.</span></span> <span data-ttu-id="3d056-164">集區層級設定會覆寫網站層級設定。</span><span class="sxs-lookup"><span data-stu-id="3d056-164">Pool-level configurations override site-level configurations.</span></span> <span data-ttu-id="3d056-165">網站層級設定會覆寫全域層級設定。</span><span class="sxs-lookup"><span data-stu-id="3d056-165">Site-level configurations override the global-level configuration.</span></span>

<span data-ttu-id="3d056-166">在您的需求分析過程中，您必須決定如何設定全域封存設定和全域封存原則。</span><span class="sxs-lookup"><span data-stu-id="3d056-166">As part of your requirements analysis, you need to determine how to configure the global Archiving configuration and global Archiving policy.</span></span> <span data-ttu-id="3d056-167">您也需要判斷任何網站層級封存設定、集區層級的封存設定、網站層級的封存原則，以及使用者層級的封存原則的需求。</span><span class="sxs-lookup"><span data-stu-id="3d056-167">You also need to determine your requirements for any site-level Archiving configurations, pool-level Archiving configurations, site-level Archiving policies, and user-level Archiving policies.</span></span>

<span data-ttu-id="3d056-168">如果您部署一個前端集區或 Standard Edition server 的封存，則應該針對部署中的所有其他前端集區和 Standard Edition server 啟用該封存。</span><span class="sxs-lookup"><span data-stu-id="3d056-168">If you deploy Archiving for one Front End pool or Standard Edition server, you should then enable it for all other Front End pools and Standard Edition servers in your deployment.</span></span> <span data-ttu-id="3d056-169">您必須這麼做，因為需要封存其通訊的使用者可以應邀參加位於不同集區的群組 IM 交談或會議。</span><span class="sxs-lookup"><span data-stu-id="3d056-169">You need to do this because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool.</span></span> <span data-ttu-id="3d056-170">如果在主控交談或會議的集區上未啟用封存，所有會議資料可能都不會封存。</span><span class="sxs-lookup"><span data-stu-id="3d056-170">If archiving is not enabled on the pool where the conversation or meeting is hosted, all conference data may not be archived.</span></span> <span data-ttu-id="3d056-171">封存仍可用於啟用使用者和所有 IM 訊息的封存，但會議內容和事件可能不會封存。</span><span class="sxs-lookup"><span data-stu-id="3d056-171">Archiving will still work for archiving enabled users and all IM messages, but conferencing content and events may not be archived.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3d056-172">若要在維護組織的安全性標準時，啟用管理工作委派，Lync Server 2013 &nbsp; 使用角色型存取控制 (RBAC) 。</span><span class="sxs-lookup"><span data-stu-id="3d056-172">To enable delegation of administrative tasks while maintaining your organization's security standards, Lync Server 2013&nbsp;uses role-based access control (RBAC).</span></span> <span data-ttu-id="3d056-173">透過 RBAC，系統管理許可權是透過指派使用者至預先定義的系統管理角色授與。</span><span class="sxs-lookup"><span data-stu-id="3d056-173">With RBAC, administrative privilege is granted by assigning users to predefined administrative roles.</span></span> <span data-ttu-id="3d056-174">若要設定 Lync 封存原則和封存設定，必須將使用者指派給 CsArchivingAdministrator role (，除非在部署封存的伺服器上直接執行設定，而不是從其他電腦) 進行遠端處理。</span><span class="sxs-lookup"><span data-stu-id="3d056-174">To configure Lync Archiving policies and Archiving configurations, the user must be assigned to the CsArchivingAdministrator role (unless the configuration is done directly on the server where Archiving is deployed, instead of remotely from another computer).</span></span> <span data-ttu-id="3d056-175">如需 RBAC 的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-planning-for-role-based-access-control.md">規劃 Lync Server 2013 中的角色型存取控制</A> 。</span><span class="sxs-lookup"><span data-stu-id="3d056-175">For details about RBAC, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="3d056-176">如需封存部署所需之使用者權利、許可權及角色的清單，請參閱 <A href="lync-server-2013-deployment-checklist-for-archiving.md">部署檢查清單中</A>的封存（適用于規劃檔和部署檔中）的 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="3d056-176">For a list of the user rights, permissions, and roles required for archiving deployment, see <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</A>, which is available in both the Planning documentation and the Deployment documentation.</span></span><BR><span data-ttu-id="3d056-177">如果您使用 Microsoft Exchange 整合，設定 Exchange 原則需要適當的系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="3d056-177">If you use Microsoft Exchange integration, configuration of Exchange policies requires appropriate administrator rights and permissions.</span></span> <span data-ttu-id="3d056-178">如需詳細資訊，請參閱 Exchange 2013 檔。</span><span class="sxs-lookup"><span data-stu-id="3d056-178">For details, see the Exchange 2013 documentation.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

