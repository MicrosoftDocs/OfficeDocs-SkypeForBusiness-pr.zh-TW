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
ms.openlocfilehash: a3cee7269620a9525456e40604ae3f1d1c2cf33d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-archiving-in-lync-server-2013"></a><span data-ttu-id="1d33d-102">在 Lync Server 2013 中定義封存需求</span><span class="sxs-lookup"><span data-stu-id="1d33d-102">Defining your requirements for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d33d-103">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="1d33d-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="1d33d-104">如果您的組織必須遵循合規性規範，您可以部署封存，以啟用 Lync Server 2013 立即訊息（IM）和會議（會議）的封存支援。</span><span class="sxs-lookup"><span data-stu-id="1d33d-104">If your organization must follow compliance regulations, you can deploy Archiving to enable archiving support for Lync Server 2013 instant messaging (IM) and conferencing (meetings).</span></span> <span data-ttu-id="1d33d-105">如需有關可封存之內容類型的詳細資訊，請參閱規劃檔中的[Lync Server 2013 存檔](lync-server-2013-overview-of-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="1d33d-105">For details about the type of content that can be archived, see [Overview of Archiving in Lync Server 2013](lync-server-2013-overview-of-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="1d33d-106">若要實施封存，您必須先決定如何符合貴組織的存檔需求。</span><span class="sxs-lookup"><span data-stu-id="1d33d-106">To implement Archiving, you need to first decide how to meet your organization’s requirements for Archiving.</span></span> <span data-ttu-id="1d33d-107">這需要判斷下列事項：</span><span class="sxs-lookup"><span data-stu-id="1d33d-107">This requires determining the following:</span></span>

  - <span data-ttu-id="1d33d-108">**部署存檔**的時機。</span><span class="sxs-lookup"><span data-stu-id="1d33d-108">**When to deploy Archiving**.</span></span> <span data-ttu-id="1d33d-109">您可以將封存部署為您最初的 Lync Server 2013 部署的一部分，或者您可以將它新增到現有的部署。</span><span class="sxs-lookup"><span data-stu-id="1d33d-109">You can deploy Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="1d33d-110">您可以使用拓撲建立器將封存新增到您的拓撲結構，然後發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="1d33d-110">You deploy Archiving by using Topology Builder to add it to your topology, and then publishing the topology.</span></span>

  - <span data-ttu-id="1d33d-111">**是否封存內部或外部通訊**。</span><span class="sxs-lookup"><span data-stu-id="1d33d-111">**Whether to archive internal or external communications**.</span></span> <span data-ttu-id="1d33d-112">您可以針對內部通訊（內部使用者之間的通訊）、外部通訊（至少包含一個使用者在內部網路以外的通訊），或兩者皆啟用封存。</span><span class="sxs-lookup"><span data-stu-id="1d33d-112">You can enable archiving for internal communications (communications between internal users), external communications (communications that include at least one user outside your internal network), or both.</span></span> <span data-ttu-id="1d33d-113">您可以為整個組織指定這些選項，也可以針對特定的網站和池加以指定。</span><span class="sxs-lookup"><span data-stu-id="1d33d-113">You can specify these options for your entire organization, or you can specify them for specific sites and pools.</span></span> <span data-ttu-id="1d33d-114">預設不會啟用任何選項。</span><span class="sxs-lookup"><span data-stu-id="1d33d-114">By default, neither option is enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d33d-115">如果您使用 Microsoft Exchange 整合來儲存封存的資料，Exchange 設定就會控制 Lync 通訊是否已封存。</span><span class="sxs-lookup"><span data-stu-id="1d33d-115">If you use Microsoft Exchange integration to store archived data, your Exchange settings control whether Lync communications are archived.</span></span> <span data-ttu-id="1d33d-116">如果您的部署包含多個目錄林，您必須同步處理 Lync Server 與 Exchange 之間的設定。</span><span class="sxs-lookup"><span data-stu-id="1d33d-116">If your deployment includes multiple forests, you must synchronize the settings between Lync Server and Exchange.</span></span> <span data-ttu-id="1d33d-117">[控制內部或外部通訊的封存] 只適用于 Lync 原則。</span><span class="sxs-lookup"><span data-stu-id="1d33d-117">Controlling archiving for internal or external communications is only available for Lync Policy.</span></span> <span data-ttu-id="1d33d-118">針對 Exchange 整合式封存，這兩者都會封存或未封存。</span><span class="sxs-lookup"><span data-stu-id="1d33d-118">For Exchange-integrated archiving, both of them will be archived or not archived.</span></span>

    
    </div>

  - <span data-ttu-id="1d33d-119">**為什麼要啟用**封存。</span><span class="sxs-lookup"><span data-stu-id="1d33d-119">**Why enable Archiving**.</span></span> <span data-ttu-id="1d33d-120">您可以在全域層級為整個部署啟用和停用封存，而且您可以針對特定的網站和使用者啟用和停用封存。</span><span class="sxs-lookup"><span data-stu-id="1d33d-120">You can enable and disable Archiving for your entire deployment at a global level, and you can enable and disable Archiving for specific sites and users.</span></span> <span data-ttu-id="1d33d-121">在每個階層，您可以指定是否要啟用 IM 會話（對等）、會議（會議，也就是多方會議），或是兩者。</span><span class="sxs-lookup"><span data-stu-id="1d33d-121">At each of these levels, you specify whether to enable archiving of IM sessions (peer-to-peer), conferences (meetings, which are multiparty sessions), or both.</span></span> <span data-ttu-id="1d33d-122">根據預設，封存是停用的。</span><span class="sxs-lookup"><span data-stu-id="1d33d-122">By default, Archiving is disabled.</span></span>

  - <span data-ttu-id="1d33d-123">**貴組織中的使用者的重要存檔方式**。</span><span class="sxs-lookup"><span data-stu-id="1d33d-123">**How critical Archiving is to users in your organization**.</span></span> <span data-ttu-id="1d33d-124">如果存檔在您的組織中是至關重要的，您可以指定 Lync Server 2013 在 [重要] 模式中執行，這會在歸檔失敗時封鎖 IM 和會議會話。</span><span class="sxs-lookup"><span data-stu-id="1d33d-124">If archiving is mission-critical in your organization, you can specify that Lync Server 2013 run in critical mode, which blocks IM and conferencing sessions if archiving fails.</span></span> <span data-ttu-id="1d33d-125">例如：</span><span class="sxs-lookup"><span data-stu-id="1d33d-125">For example:</span></span>
    
      - <span data-ttu-id="1d33d-126">如果封存服務暫時無法傳送訊息到資料庫佇列或將訊息插入資料庫），則 IM 和會議功能會在部署期間封鎖，直到還原封存支援為止。</span><span class="sxs-lookup"><span data-stu-id="1d33d-126">If the Archiving service is temporarily unable to send a message to the database queue or insert a message into the database), both IM and conferencing functionality are blocked in the deployment until archiving support is restored.</span></span>
    
      - <span data-ttu-id="1d33d-127">如果會議使用者上傳檔案，但無法將檔案複製到 [封存檔案] 存放區，會議功能會在部署期間封鎖，直到問題解決為止，但不會封鎖 IM 功能。</span><span class="sxs-lookup"><span data-stu-id="1d33d-127">If a conferencing user uploads a file, but the file cannot be copied to the archiving file store, conferencing functionality is blocked in the deployment until the problem is resolved, but IM functionality is not blocked.</span></span>
    
    <span data-ttu-id="1d33d-128">您可以在 [全域] 層級、[網站層級] 和 [池] 層級設定此選項。</span><span class="sxs-lookup"><span data-stu-id="1d33d-128">You can configure this option at the global level, site level, and pool level.</span></span> <span data-ttu-id="1d33d-129">根據預設，不會啟用 [關鍵模式]。</span><span class="sxs-lookup"><span data-stu-id="1d33d-129">By default, critical mode is not enabled.</span></span>

  - <span data-ttu-id="1d33d-130">**是否要使用 Microsoft Exchange 整合**。</span><span class="sxs-lookup"><span data-stu-id="1d33d-130">**Whether to use Microsoft Exchange integration**.</span></span> <span data-ttu-id="1d33d-131">此選項會整合儲存與 Exchange 2013 儲存空間的儲存空間，讓您的 Lync Server 封存的資料和 Exchange 2013 存檔的資料會儲存在 Exchange 中。</span><span class="sxs-lookup"><span data-stu-id="1d33d-131">This option integrates Archiving storage with your Exchange 2013 storage, so that your Lync Server archived data and Exchange 2013 archived data are stored together in Exchange.</span></span> <span data-ttu-id="1d33d-132">您可以使用 Microsoft Exchange 整合來儲存駐留在 Exchange 2013 的使用者的存檔資料，如果其信箱已放在就地保留中。</span><span class="sxs-lookup"><span data-stu-id="1d33d-132">You can use Microsoft Exchange integration for storage of archiving data for users who are homed on Exchange 2013, if their mailboxes have been put on In-Place Hold.</span></span> <span data-ttu-id="1d33d-133">如果您沒有 Exchange 2013 部署，或是您不想要將它整合到 exchange 2013，或者如果您有任何不是託管于 Exchange 的 Lync 使用者，您可以使用 SQL Server 從 Lync 通訊儲存已存檔的資料，以部署個別的存檔資料庫。</span><span class="sxs-lookup"><span data-stu-id="1d33d-133">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync users who are not homed on Exchange 2013, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="1d33d-134">您可以在 [全域] 層級、[網站層級] 和 [池] 層級設定 Microsoft Exchange 整合選項。</span><span class="sxs-lookup"><span data-stu-id="1d33d-134">You can configure the Microsoft Exchange integration option at the global level, site level, and pool level.</span></span> <span data-ttu-id="1d33d-135">根據預設，不會啟用 Microsoft Exchange 整合。</span><span class="sxs-lookup"><span data-stu-id="1d33d-135">By default, Microsoft Exchange integration is not enabled.</span></span>

  - <span data-ttu-id="1d33d-136">**存檔資料的管理方式**。</span><span class="sxs-lookup"><span data-stu-id="1d33d-136">**How archived data is to be managed**.</span></span> <span data-ttu-id="1d33d-137">存檔資料庫不適用於長期保留，而且 Lync Server 2013 不會提供電子探索（搜尋）方案來儲存已封存的資料，因此需要將資料移到其他儲存空間。</span><span class="sxs-lookup"><span data-stu-id="1d33d-137">The archiving database is not intended for long-term retention and Lync Server 2013 does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="1d33d-138">Lync Server 提供可供您用來匯出封存資料的 [會話匯出] 工具，這會建立已歸檔資料的可搜尋記錄。</span><span class="sxs-lookup"><span data-stu-id="1d33d-138">Lync Server does provide a session export tool that you can use to export archived data, and which creates searchable transcripts of the archived data.</span></span> <span data-ttu-id="1d33d-139">針對全域原則，以及您建立的每個網站和使用者原則，您可以啟用資料清除，並指定下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="1d33d-139">For the global policy, and for each site and user policy that you create, you can enable data purging and specify one of the following options:</span></span>
    
      - <span data-ttu-id="1d33d-140">在特定天數之後，清除匯出的存檔資料並儲存已儲存的資料。</span><span class="sxs-lookup"><span data-stu-id="1d33d-140">Purge both exported archiving data and stored archiving data after a specific number of days.</span></span> <span data-ttu-id="1d33d-141">您可以指定的天數最少為一天。</span><span class="sxs-lookup"><span data-stu-id="1d33d-141">The minimum number of days that you can specify is one day.</span></span> <span data-ttu-id="1d33d-142">您最多可以指定2562天的天數。</span><span class="sxs-lookup"><span data-stu-id="1d33d-142">The maximum number of days that you can specify is 2562 days.</span></span>
    
      - <span data-ttu-id="1d33d-143">僅清除匯出的存檔資料。</span><span class="sxs-lookup"><span data-stu-id="1d33d-143">Purge exported archiving data only.</span></span> <span data-ttu-id="1d33d-144">這個選項會清除 [會話匯出] 工具已匯出並標示為可安全刪除的所有記錄。</span><span class="sxs-lookup"><span data-stu-id="1d33d-144">This option purges all records that have been exported and marked as safe to delete by the session export tool.</span></span>
    
    <span data-ttu-id="1d33d-145">您可以在 [全域] 層級、[網站層級] 和 [池] 層級設定此選項。</span><span class="sxs-lookup"><span data-stu-id="1d33d-145">You can configure this option at the global level, site level, and pool level.</span></span> <span data-ttu-id="1d33d-146">根據預設，不會啟用 [清除]。</span><span class="sxs-lookup"><span data-stu-id="1d33d-146">By default, purging is not enabled.</span></span>

<span data-ttu-id="1d33d-147">您可以使用下列方法來控制存檔：</span><span class="sxs-lookup"><span data-stu-id="1d33d-147">You control Archiving by using the following methods:</span></span>

  - <span data-ttu-id="1d33d-148">**存檔原則**。</span><span class="sxs-lookup"><span data-stu-id="1d33d-148">**Archiving policies**.</span></span> <span data-ttu-id="1d33d-149">您可以使用一或多個存檔原則來啟用和停用內部與外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="1d33d-149">You use one or more Archiving policies to enable and disable archiving of internal and external communications.</span></span> <span data-ttu-id="1d33d-150">根據預設，不會啟用任何封存。</span><span class="sxs-lookup"><span data-stu-id="1d33d-150">By default, no archiving is enabled.</span></span> <span data-ttu-id="1d33d-151">您可以透過使用預設的全域原則，在您的部署中啟用或停用內部通訊、外部通訊或兩者的封存。</span><span class="sxs-lookup"><span data-stu-id="1d33d-151">You enable or disable Archiving for internal communications, external communications, or both in your deployment by using the default global policy.</span></span> <span data-ttu-id="1d33d-152">您無法刪除全域原則。</span><span class="sxs-lookup"><span data-stu-id="1d33d-152">You cannot delete the global policy.</span></span> <span data-ttu-id="1d33d-153">您可以指定一或多個選用的網站原則來啟用或停用針對特定網站進行內部與外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="1d33d-153">You can specify one or more optional site policies to enable or disable Archiving for internal and external communications for specific sites.</span></span> <span data-ttu-id="1d33d-154">您也可以指定一或多個使用者原則來啟用或停用特定使用者與使用者群組的存檔。</span><span class="sxs-lookup"><span data-stu-id="1d33d-154">You can also specify one or more user policies to enable or disable Archiving for specific users and user groups.</span></span> <span data-ttu-id="1d33d-155">使用者層級原則會覆寫網站原則。</span><span class="sxs-lookup"><span data-stu-id="1d33d-155">User-level policies override site policies.</span></span> <span data-ttu-id="1d33d-156">網站層級原則會覆寫全域層原則。</span><span class="sxs-lookup"><span data-stu-id="1d33d-156">Site-level policies override the global-level policies.</span></span> <span data-ttu-id="1d33d-157">使用者層級原則只會針對設定為使用原則的特定使用者執行。</span><span class="sxs-lookup"><span data-stu-id="1d33d-157">User-level policies are implemented only for the specific users who are configured to use the policy.</span></span> <span data-ttu-id="1d33d-158">只有在至少一個參與者設定為啟用封存原則時，才會將 [立即訊息] 與 [會議] 群組封存。</span><span class="sxs-lookup"><span data-stu-id="1d33d-158">Group instant messages and conferences are archived only if a policy for at least one of the participants is configured to enable archiving.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d33d-159">如果您使用 Microsoft Exchange 整合，Exchange 2013 原則會覆寫所有駐留在 Exchange 2013 伺服器上的使用者的 Lync Server 封存原則。</span><span class="sxs-lookup"><span data-stu-id="1d33d-159">If you use Microsoft Exchange integration, Exchange 2013 policies override Lync Server Archiving policies for all users homed on the Exchange 2013 servers.</span></span>

    
    </div>

  - <span data-ttu-id="1d33d-160">**存檔**設定。</span><span class="sxs-lookup"><span data-stu-id="1d33d-160">**Archiving configurations**.</span></span> <span data-ttu-id="1d33d-161">您可以使用一或多個存檔設定來指定本主題前面所述的大部分存檔選項，除了允許封存內部和外部通訊（使用 [封存原則] 進行設定）之外，如以下所述。上一個專案符號）。</span><span class="sxs-lookup"><span data-stu-id="1d33d-161">You use one or more Archiving configurations to specify most of the Archiving options that are described previously in this topic, except for enabling archiving of internal and external communications (configured using Archiving policies, as described in the previous bullet).</span></span> <span data-ttu-id="1d33d-162">封存配置包括預設的全域配置以及選用的網站和池設定。</span><span class="sxs-lookup"><span data-stu-id="1d33d-162">Archiving configurations include the default global configuration and optional site and pool configurations.</span></span> <span data-ttu-id="1d33d-163">您無法刪除全域配置。</span><span class="sxs-lookup"><span data-stu-id="1d33d-163">You cannot delete the global configuration.</span></span> <span data-ttu-id="1d33d-164">池層級的設定會覆寫網站層級的配置。</span><span class="sxs-lookup"><span data-stu-id="1d33d-164">Pool-level configurations override site-level configurations.</span></span> <span data-ttu-id="1d33d-165">網站層級配置會覆寫全域層級設定。</span><span class="sxs-lookup"><span data-stu-id="1d33d-165">Site-level configurations override the global-level configuration.</span></span>

<span data-ttu-id="1d33d-166">作為需求分析的一部分，您必須決定如何設定全域封存配置和全域歸檔原則。</span><span class="sxs-lookup"><span data-stu-id="1d33d-166">As part of your requirements analysis, you need to determine how to configure the global Archiving configuration and global Archiving policy.</span></span> <span data-ttu-id="1d33d-167">您也需要針對任何網站層級歸檔設定、池層級的歸檔設定、網站層級的歸檔原則，以及使用者層級歸檔原則，來判斷您的需求。</span><span class="sxs-lookup"><span data-stu-id="1d33d-167">You also need to determine your requirements for any site-level Archiving configurations, pool-level Archiving configurations, site-level Archiving policies, and user-level Archiving policies.</span></span>

<span data-ttu-id="1d33d-168">如果您部署的是一個前端池或標準版伺服器的封存，則應該針對您部署中的所有其他前端池和標準版伺服器啟用該歸檔。</span><span class="sxs-lookup"><span data-stu-id="1d33d-168">If you deploy Archiving for one Front End pool or Standard Edition server, you should then enable it for all other Front End pools and Standard Edition servers in your deployment.</span></span> <span data-ttu-id="1d33d-169">您必須執行此動作，因為需要封存其通訊的使用者可以受邀加入群組 IM 交談或託管于不同的池中的會議。</span><span class="sxs-lookup"><span data-stu-id="1d33d-169">You need to do this because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool.</span></span> <span data-ttu-id="1d33d-170">如果在託管或會議所在的池中未啟用 [封存]，所有的會議資料都可能無法封存。</span><span class="sxs-lookup"><span data-stu-id="1d33d-170">If archiving is not enabled on the pool where the conversation or meeting is hosted, all conference data may not be archived.</span></span> <span data-ttu-id="1d33d-171">封存功能仍適用于已啟用的使用者和所有 IM 訊息，但是會議內容和事件可能不會封存。</span><span class="sxs-lookup"><span data-stu-id="1d33d-171">Archiving will still work for archiving enabled users and all IM messages, but conferencing content and events may not be archived.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d33d-172">若要在維護貴組織的安全性標準時啟用管理工作委派，Lync Server&nbsp;2013 使用角色式存取控制（RBAC）。</span><span class="sxs-lookup"><span data-stu-id="1d33d-172">To enable delegation of administrative tasks while maintaining your organization's security standards, Lync Server 2013&nbsp;uses role-based access control (RBAC).</span></span> <span data-ttu-id="1d33d-173">使用 RBAC，系統會將使用者指派至預先定義的管理角色，以獲得系統管理許可權。</span><span class="sxs-lookup"><span data-stu-id="1d33d-173">With RBAC, administrative privilege is granted by assigning users to predefined administrative roles.</span></span> <span data-ttu-id="1d33d-174">若要設定 Lync 歸檔原則和封存設定，使用者必須指派給 CsArchivingAdministrator 角色（除非是直接在部署歸檔的伺服器上執行，而不是從另一部電腦遠端完成）。</span><span class="sxs-lookup"><span data-stu-id="1d33d-174">To configure Lync Archiving policies and Archiving configurations, the user must be assigned to the CsArchivingAdministrator role (unless the configuration is done directly on the server where Archiving is deployed, instead of remotely from another computer).</span></span> <span data-ttu-id="1d33d-175">如需 RBAC 的詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 中的角色式存取控制規劃</A>。</span><span class="sxs-lookup"><span data-stu-id="1d33d-175">For details about RBAC, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="1d33d-176">如需封存部署所需的使用者權利、許可權和角色清單，請參閱 Lync Server 2013 中的 [封存]<A href="lync-server-2013-deployment-checklist-for-archiving.md">部署核對清單</A>（在規劃檔和部署檔中都有提供）。</span><span class="sxs-lookup"><span data-stu-id="1d33d-176">For a list of the user rights, permissions, and roles required for archiving deployment, see <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</A>, which is available in both the Planning documentation and the Deployment documentation.</span></span><BR><span data-ttu-id="1d33d-177">如果您使用的是 Microsoft Exchange 整合，則 Exchange 原則的設定需要適當的系統管理員權力和許可權。</span><span class="sxs-lookup"><span data-stu-id="1d33d-177">If you use Microsoft Exchange integration, configuration of Exchange policies requires appropriate administrator rights and permissions.</span></span> <span data-ttu-id="1d33d-178">如需詳細資訊，請參閱 Exchange 2013 檔。</span><span class="sxs-lookup"><span data-stu-id="1d33d-178">For details, see the Exchange 2013 documentation.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

