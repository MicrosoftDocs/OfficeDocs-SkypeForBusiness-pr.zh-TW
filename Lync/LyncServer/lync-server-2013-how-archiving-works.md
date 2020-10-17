---
title: Lync Server 2013：封存的運作方式
description: Lync Server 2013：封存的運作方式。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Archiving works
ms:assetid: 536a52a9-cfb7-4392-9620-ffc5b319b31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204900(v=OCS.15)
ms:contentKeyID: 48184174
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57a5ef19c0781b4faa279a6aad46ac34b83ae0f9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543379"
---
# <a name="how-archiving-works-in-lync-server-2013"></a><span data-ttu-id="338ce-103">Lync Server 2013 中的封存運作方式</span><span class="sxs-lookup"><span data-stu-id="338ce-103">How Archiving works in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="338ce-104">_**主題上次修改日期：** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="338ce-104">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="338ce-105">Lync Server 2013 封存提供的選項可協助您符合您的合規性需求。</span><span class="sxs-lookup"><span data-stu-id="338ce-105">Lync Server 2013 Archiving provides options to help you meet your compliance needs.</span></span> <span data-ttu-id="338ce-106">若要以最有效地符合組織需求的方式來實施及維護它，您應該瞭解：</span><span class="sxs-lookup"><span data-stu-id="338ce-106">To implement and maintain it in a way that most effectively meets your organization’s requirements, you should understand:</span></span>

  - <span data-ttu-id="338ce-107">可以封存哪些資訊。</span><span class="sxs-lookup"><span data-stu-id="338ce-107">What information can be archived.</span></span>

  - <span data-ttu-id="338ce-108">如何在部署中啟用和停用封存。</span><span class="sxs-lookup"><span data-stu-id="338ce-108">How to enable and disable Archiving in your deployment.</span></span>

  - <span data-ttu-id="338ce-109">您可以設定來控制如何實作封存的封存選項。</span><span class="sxs-lookup"><span data-stu-id="338ce-109">The archiving options that you can configure to control how Archiving is implemented.</span></span>

<div>

## <a name="what-information-can-be-archived"></a><span data-ttu-id="338ce-110">可以封存哪些資訊？</span><span class="sxs-lookup"><span data-stu-id="338ce-110">What Information Can Be Archived?</span></span>

<span data-ttu-id="338ce-111">可以封存下列類型的內容：</span><span class="sxs-lookup"><span data-stu-id="338ce-111">The following types of content can be archived:</span></span>

  - <span data-ttu-id="338ce-112">對等立即訊息</span><span class="sxs-lookup"><span data-stu-id="338ce-112">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="338ce-113">會議，其為多方立即訊息</span><span class="sxs-lookup"><span data-stu-id="338ce-113">Conferences (meetings), which are multiparty instant messages</span></span>

  - <span data-ttu-id="338ce-114">會議內容，包括上傳的內容 (例如，講義) 和事件相關內容 (例如，加入、離開、上傳共用，以及可見度變更)</span><span class="sxs-lookup"><span data-stu-id="338ce-114">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

  - <span data-ttu-id="338ce-115">在會議期間共用白板與投票</span><span class="sxs-lookup"><span data-stu-id="338ce-115">Whiteboards and polls shared during a conference</span></span>

<span data-ttu-id="338ce-116">不會封存下列類型的內容：</span><span class="sxs-lookup"><span data-stu-id="338ce-116">The following types of content are not archived:</span></span>

  - <span data-ttu-id="338ce-117">對等檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="338ce-117">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="338ce-118">對等立即訊息和會議的音訊/視訊</span><span class="sxs-lookup"><span data-stu-id="338ce-118">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="338ce-119">對等立即訊息和會議的桌面與應用程式共用</span><span class="sxs-lookup"><span data-stu-id="338ce-119">Desktop and application sharing for peer-to-peer instant messages and conferences</span></span>

<span data-ttu-id="338ce-120">Lync Server 也不會封存持久聊天交談。</span><span class="sxs-lookup"><span data-stu-id="338ce-120">Lync Server also does not archive Persistent Chat conversations.</span></span> <span data-ttu-id="338ce-121">若要封存持久聊天對話，您必須啟用和設定規范服務，該服務是可與 Microsoft Lync Server 2013，Persistent Chat Server 一起部署的元件。</span><span class="sxs-lookup"><span data-stu-id="338ce-121">To archive Persistent Chat conversations, you must enable and configure the compliance service, which is a component that can be deployed with Microsoft Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="338ce-122">如需詳細資訊，請參閱規劃檔中的在 [Lync server 2013 中規劃 Persistent Chat Server](lync-server-2013-planning-for-persistent-chat-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="338ce-122">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a><span data-ttu-id="338ce-123">如何開始使用封存？</span><span class="sxs-lookup"><span data-stu-id="338ce-123">How Do I Start Using Archiving?</span></span>

<span data-ttu-id="338ce-p103">當您部署伺服器時，封存會自動安裝於每部前端伺服器上，但在您設定封存之前不會加以啟用。您設定封存的方式是根據您部署封存的方式來決定：</span><span class="sxs-lookup"><span data-stu-id="338ce-p103">Archiving is automatically installed on each Front End Server when you deploy the server, but Archiving is not enabled until you configure it. How you configure it is determined by how you deploy Archiving:</span></span>

  - <span data-ttu-id="338ce-126">**使用 Microsoft Exchange 整合進行封存。**</span><span class="sxs-lookup"><span data-stu-id="338ce-126">**Archiving using Microsoft Exchange integration.**</span></span> <span data-ttu-id="338ce-127">如果您擁有位於 Exchange 2013 的使用者，且已將其信箱置於 In-Place 保留狀態，您可以選取此選項，以整合 Lync Server 2013 儲存體與 Exchange storage。</span><span class="sxs-lookup"><span data-stu-id="338ce-127">If you have users who are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can select the option to integrate Lync Server 2013 storage with Exchange storage.</span></span> <span data-ttu-id="338ce-128">如果您選擇 [Microsoft Exchange 整合] 選項，您可以使用 Exchange 2013 原則和設定來控制這些使用者之 Lync Server 2013 資料的封存。</span><span class="sxs-lookup"><span data-stu-id="338ce-128">If you choose the Microsoft Exchange integration option, you use Exchange 2013 policies and configurations to control the archiving of Lync Server 2013 data for those users.</span></span>

  - <span data-ttu-id="338ce-129">**使用 Lync Server 封存資料庫進行封存。**</span><span class="sxs-lookup"><span data-stu-id="338ce-129">**Archiving using Lync Server Archiving databases.**</span></span> <span data-ttu-id="338ce-130">如果您有未位於 Exchange 2013 的使用者，或其信箱未放在 In-Place 保留中的使用者，或是您不想要在部署中使用任何或所有使用者的 Microsoft Exchange 整合，您可以使用 SQL Server 部署 Lync Server 封存資料庫，以儲存使用者的封存資料。</span><span class="sxs-lookup"><span data-stu-id="338ce-130">If you have users who are not homed on Exchange 2013 or who have not had their mailboxes put on In-Place Hold, or if you don’t want to use Microsoft Exchange integration for any or all users in your deployment, you can deploy Lync Server Archiving databases using SQL Server to store Archiving data for those users.</span></span> <span data-ttu-id="338ce-131">在此情況下，Lync Server 2013 封存原則和設定會決定封存是否已啟用以及如何執行。</span><span class="sxs-lookup"><span data-stu-id="338ce-131">In this case, Lync Server 2013 Archiving policies and configurations determine whether Archiving is enabled and how it is implemented.</span></span> <span data-ttu-id="338ce-132">若要使用 Lync Server 2013，您必須將適當的 SQL Server 資料庫新增至您的拓撲，併發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="338ce-132">To use Lync Server 2013, you must add the appropriate SQL Server databases to your topology and publish the topology.</span></span>

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a><span data-ttu-id="338ce-133">使用 Microsoft Exchange 整合時的封存設定</span><span class="sxs-lookup"><span data-stu-id="338ce-133">Archiving Setup When Using Microsoft Exchange Integration</span></span>

<span data-ttu-id="338ce-134">如果您的使用者位於 Exchange 2013，而且其信箱已放在 In-Place 暫止狀態，您可以選擇 [ **Microsoft Exchange 整合** ] 選項 (本節稍後所述) 封存使用者的 Lync server 2013，然後指定 Exchange In-Place 保留原則和設定，以及 Lync server 設定來控制下列各項：</span><span class="sxs-lookup"><span data-stu-id="338ce-134">If your users are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can choose the **Microsoft Exchange integration** option (as described later in this section) to archive Lync Server 2013 for those users, and then you control archiving for those users by specifying Exchange In-Place Hold policies and settings, as well as Lync Server configurations to control the following:</span></span>

  - <span data-ttu-id="338ce-135">是否要封存 IM、會議或兩者。</span><span class="sxs-lookup"><span data-stu-id="338ce-135">Whether to archive IM, conferencing, or both.</span></span>

  - <span data-ttu-id="338ce-136">是否要為您的 Lync Server 部署實施重要模式。</span><span class="sxs-lookup"><span data-stu-id="338ce-136">Whether to implement critical mode for your Lync Server deployment.</span></span>

  - <span data-ttu-id="338ce-137">Microsoft Exchange 整合選項的選取範圍，使用 Exchange 2013 儲存封存的資料。</span><span class="sxs-lookup"><span data-stu-id="338ce-137">Selection of the Microsoft Exchange integration option to use Exchange 2013 for storage of archived data.</span></span>

<span data-ttu-id="338ce-138">本節稍後會說明這些 Lync Server 2013 封存設定選項。</span><span class="sxs-lookup"><span data-stu-id="338ce-138">These Lync Server 2013 Archiving configuration options are described later in this section.</span></span> <span data-ttu-id="338ce-139">如需如何設定 Exchange In-Place 保留原則及設定以支援封存的詳細資訊，請參閱 Exchange 2013 產品檔。</span><span class="sxs-lookup"><span data-stu-id="338ce-139">For information about how to configure Exchange In-Place Hold policies and settings to support archiving, see the Exchange 2013 product documentation.</span></span>

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a><span data-ttu-id="338ce-140">使用 Lync Server 封存資料庫儲存時進行封存設定</span><span class="sxs-lookup"><span data-stu-id="338ce-140">Archiving Setup When Using Lync Server Archiving Database Storage</span></span>

<span data-ttu-id="338ce-141">若要使用 Lync Server 封存資料庫 (使用 SQL Server 資料庫) 若要封存部署中任何使用者的資料，您可以設定 Lync Server 封存原則，以控制是否為這些使用者啟用封存功能。</span><span class="sxs-lookup"><span data-stu-id="338ce-141">If you want to use Lync Server Archiving databases (using SQL Server databases) to archive data for any users in your deployment, you can configure Lync Server Archiving policies to control whether Archiving is enabled for those users.</span></span> <span data-ttu-id="338ce-142">在每個封存原則中，您可以針對下列其中一項或兩項來啟用或停用封存：</span><span class="sxs-lookup"><span data-stu-id="338ce-142">In each Archiving policy, you can enable or disable Archiving for either or both of the following:</span></span>

  - <span data-ttu-id="338ce-143">內部通訊</span><span class="sxs-lookup"><span data-stu-id="338ce-143">Internal communications</span></span>

  - <span data-ttu-id="338ce-144">外部通訊</span><span class="sxs-lookup"><span data-stu-id="338ce-144">External communications</span></span>

<span data-ttu-id="338ce-145">根據預設，不會在任何 Lync Server 封存原則中啟用內部通訊或外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="338ce-145">By default, archiving is not enabled for internal communications or external communications in any Lync Server Archiving policy.</span></span> <span data-ttu-id="338ce-146">您可以使用 Lync Server 2013 控制台或在 Lync Server 2013 管理命令介面中使用 Cmdlet 來啟用及停用通訊。</span><span class="sxs-lookup"><span data-stu-id="338ce-146">You enable and disable communications using Lync Server 2013 Control Panel or using cmdlets in the Lync Server 2013 Management Shell.</span></span>

<span data-ttu-id="338ce-147">Lync Server 2013 封存原則包括下列專案：</span><span class="sxs-lookup"><span data-stu-id="338ce-147">Lync Server 2013 Archiving policies include the following:</span></span>

  - <span data-ttu-id="338ce-148">**全域封存原則**。</span><span class="sxs-lookup"><span data-stu-id="338ce-148">**Global Archiving policy**.</span></span> <span data-ttu-id="338ce-149">此為預設的封存原則，可以套用至您的整個部署。</span><span class="sxs-lookup"><span data-stu-id="338ce-149">This is the default Archiving policy and applies to your entire deployment.</span></span> <span data-ttu-id="338ce-150">它會在您部署 Lync Server 2013 時建立，而且預設會同時停用內部和外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="338ce-150">It is created when you deploy Lync Server 2013 and, by default, disables Archiving for both internal and external communications.</span></span> <span data-ttu-id="338ce-151">您無法刪除此原則。</span><span class="sxs-lookup"><span data-stu-id="338ce-151">You cannot delete this policy.</span></span> <span data-ttu-id="338ce-152">如果您選擇刪除選項，即會將全域原則重設為預設設定。</span><span class="sxs-lookup"><span data-stu-id="338ce-152">If you choose the delete option, the global policy is reset to the default settings.</span></span>

  - <span data-ttu-id="338ce-p110">**網站封存原則**。您可以選擇性地為一或多個指定網站啟用或停用封存，作法是針對該網站建立和設定網站層級的封存原則。當您建立網站層級的封存原則時，預設不會啟用封存。您可以刪除任何您建立之網站層級的封存原則。網站層級的封存原則優先於全域原則，但僅適用於原則中指定的網站。例如，如果您在全域原則中針對內部與外部通訊啟用封存，然後建立一個網站原則以針對外部通訊停用封存，則只會針對該網站封存內部通訊。</span><span class="sxs-lookup"><span data-stu-id="338ce-p110">**Site Archiving policy**. Optionally, you can enable or disable Archiving for one or more specific sites by creating and configuring a site-level Archiving policy for the site. When you create a site-level Archiving policy, by default, archiving is not enabled. You can delete any site-level Archiving policy that you create. A site-level Archiving policy overrides the global policy, but only for the site specified in the policy. For example, if you enable Archiving for internal and external communications in your global policy and create a site policy in which you disable Archiving for external communications, only internal communications would be archived for that site.</span></span>

  - <span data-ttu-id="338ce-p111">**使用者封存原則**。您可以選擇性地為一或多個特定使用者或使用者群組啟用或停用封存，作法是為指定的使用者和使用者群組建立、設定及套用使用者層級的封存原則。當您建立使用者層級的封存原則時，預設不會啟用封存。您可以刪除任何您建立之使用者層級的封存原則，而且可以變更要套用封存原則的使用者與使用者群組。使用者層級的封存原則優先於全域原則及所有網站原則，但僅適用於套用原則的使用者和使用者群組。例如，如果您在全域原則中針對內部與外部通訊停用封存、建立一個網站層級的原則以針對內部與外部通訊啟用封存，然後建立一個使用者層級的原則以針對外部通訊停用封存，則系統將針對所有網站使用者的外部與內部通訊封存通訊，但您套用使用者層級原則的使用者例外，只會為他們封存內部通訊。</span><span class="sxs-lookup"><span data-stu-id="338ce-p111">**User Archiving policy**. Optionally, you can enable or disable Archiving for one or more specific users and group of users by creating, configuring, and applying a user-level Archiving policy for the specified users and user groups. When you create a user-level Archiving policy, by default, archiving is not enabled. You can delete any user-level Archiving policy that you create, and you can change which users and group of users the Archiving policy applies to. A user-level Archiving policy overrides the global policy and any site policies, but only for the users and user groups to whom the policy is applied. For example, if you disable Archiving for internal and external communications in your global policy, create a site-level policy in which you enable Archiving for internal and external communications, and then create a user-level policy in which you disable Archiving for external communications, the communications would be archived for both external and internal communications for all site users except that, for the users to whom you apply the user-level policy, only internal communications would be archived.</span></span>

<span data-ttu-id="338ce-165">如需如何在部署封存時設定初始封存原則的詳細資訊，請參閱部署檔中的設定 [和指派 Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md) 中的封存原則。</span><span class="sxs-lookup"><span data-stu-id="338ce-165">For details about how to set up initial Archiving policies when you deploy Archiving, see [Configuring and assigning Archiving policies in Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="338ce-166">如需使用封存原則來啟用及停用部署後的通訊的詳細資訊，請參閱 Operations 檔中的 [管理 Lync Server 2013 中的內部及外部通訊](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) 的封存。</span><span class="sxs-lookup"><span data-stu-id="338ce-166">For details about using Archiving policies to enable and disable communications after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="338ce-167">如果您同時執行這兩種 Lync Server 2013 封存資料庫並啟用 Microsoft Exchange 整合，Exchange 2013 原則會覆寫 Lync Server 封存原則，但僅限於位於 Exchange 2013 的使用者，且其信箱置於 In-Place 保留狀態。</span><span class="sxs-lookup"><span data-stu-id="338ce-167">If you implement both Lync Server 2013 Archiving databases and enable Microsoft Exchange integration, Exchange 2013 policies override Lync Server Archiving policies, but only for users who are homed on Exchange 2013 and have had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="338ce-168">Lync 封存取決於 Microsoft Exchange In-Place 暫止原則。</span><span class="sxs-lookup"><span data-stu-id="338ce-168">Lync Archiving depends on Microsoft Exchange In-Place Hold policy only.</span></span>



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a><span data-ttu-id="338ce-169">我可以使用哪些選項來設定封存？</span><span class="sxs-lookup"><span data-stu-id="338ce-169">What Options Do I Have for Configuring Archiving?</span></span>

<span data-ttu-id="338ce-170">除了使用原則及啟用與停用封存，您還有其他封存選項可用來為整個部署進行設定，而且可以選擇性地針對特定的網站與集區進行設定。</span><span class="sxs-lookup"><span data-stu-id="338ce-170">In addition to using policies and to enable and disable Archiving, you have other Archiving options that can be configure for your entire deployment and, optionally, for specific sites and pools.</span></span> <span data-ttu-id="338ce-171">您可以使用一或多個封存設定來控制大部分封存選項，這些選項可在 Lync Server 2013 控制台中使用，但也有另一個僅可用於設定的選項，使用 Lync Server 2013 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="338ce-171">You control most Archiving options by using one or more Archiving configurations, which are available in Lync Server 2013 Control Panel, but also have another option that is only available for configuration using Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a><span data-ttu-id="338ce-172">Lync Server 2013 控制台中的封存設定選項</span><span class="sxs-lookup"><span data-stu-id="338ce-172">Archiving Configuration Options Available in Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="338ce-173">每個封存設定都會提供下列選項：</span><span class="sxs-lookup"><span data-stu-id="338ce-173">Each archiving configuration provides the following options:</span></span>

<span data-ttu-id="338ce-p115">部署封存時會自動建立全域層級的設定，全域層級的設定可加以設定，但不能刪除。如果您選取選項來刪除全域設定，即會將設定重設為預設值。您可以建立多個網站與集區設定，與全域設定一起使用來控制封存設定。針對全域設定及每個台站與集區設定，您會有下列選項：</span><span class="sxs-lookup"><span data-stu-id="338ce-p115">The global-level configuration is created automatically when you deploy archiving and can be configured, but not deleted. If you select the option to delete the global configuration, the settings are reset to the default values. You can create multiple site and pool configurations that, together with the global configuration, control archiving settings. For the global configuration and each site and pool configuration, you have the following options:</span></span>

  - <span data-ttu-id="338ce-178">停用封存、僅針對立即訊息 (IM) 啟用封存，或者針對 IM 和會議啟用封存</span><span class="sxs-lookup"><span data-stu-id="338ce-178">Disable archiving, enable archiving only for instant messaging (IM), or enable archiving of both IM and conferencing.</span></span>

  - <span data-ttu-id="338ce-179">設定重要模式，以在 Lync 伺服器失敗的事件中封鎖 IM 和會議會話。</span><span class="sxs-lookup"><span data-stu-id="338ce-179">Configure critical mode to block IM and conferencing sessions in the event of a Lync Server failure.</span></span> <span data-ttu-id="338ce-180">失敗包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="338ce-180">Failures include the following:</span></span>
    
      - <span data-ttu-id="338ce-181">**IM**。</span><span class="sxs-lookup"><span data-stu-id="338ce-181">**IM**.</span></span> <span data-ttu-id="338ce-182">Lync Server storage service 發生問題。</span><span class="sxs-lookup"><span data-stu-id="338ce-182">A problem with the Lync Server storage service.</span></span> <span data-ttu-id="338ce-183">在此情況下，會針對已啟用封存的使用者封鎖 IM。</span><span class="sxs-lookup"><span data-stu-id="338ce-183">In this case, IM is blocked for users who are enabled for Archiving.</span></span>
    
      - <span data-ttu-id="338ce-p118">**會議**。失敗可能是無法使用的檔案共用，或是儲存服務發生問題。在此情況下，所有失敗時於集區中舉行的作用中會議都會切換為限制模式，並且無法啟動新會議。</span><span class="sxs-lookup"><span data-stu-id="338ce-p118">**Conferencing**. A failure could be an unavailable file share or a problem with the storage service. In this case, all active conferences hosted in the pool at the time of failure are switched to restricted mode and new conferences cannot be activated.</span></span>
    
    <span data-ttu-id="338ce-187">IM 和會議會在更正失敗之後自動復原。</span><span class="sxs-lookup"><span data-stu-id="338ce-187">Both IM and conferencing automatically recover after the failures are corrected.</span></span>

  - <span data-ttu-id="338ce-188">指定使用 Microsoft Exchange Server 2013 整合，以使用 Exchange 2013 儲存封存資料，而不是設定個別的 SQL Server 資料庫來儲存 Lync Server 2013 封存資料。</span><span class="sxs-lookup"><span data-stu-id="338ce-188">Specify the use of Microsoft Exchange Server 2013 integration to use Exchange 2013 for storage of archived data, instead of setting up separate SQL Server databases for storage of Lync Server 2013 archiving data.</span></span>

  - <span data-ttu-id="338ce-p119">設定封存資料的清除選項。這包含指定何時清除封存的資料，可以是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="338ce-p119">Configure purging options for archived data. This includes specifying when to purge archived data, which can be either of the following:</span></span>
    
      - <span data-ttu-id="338ce-191">在您指定的特定天數之後</span><span class="sxs-lookup"><span data-stu-id="338ce-191">After a specific number of days that you specify</span></span>
    
      - <span data-ttu-id="338ce-192">在匯出封存資料之後 (包括已上傳至 Exchange 的資料（如果您啟用 Microsoft Exchange 整合) ）。</span><span class="sxs-lookup"><span data-stu-id="338ce-192">After the archiving data has been exported (which includes data that has been uploaded to Exchange, if you enable Microsoft Exchange integration).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="338ce-193">如果您啟用 Microsoft Exchange 整合，請清除駐留在 Exchange 2013 的使用者，並將其信箱置於 In-Place 保留狀態，由 Exchange 所控制。</span><span class="sxs-lookup"><span data-stu-id="338ce-193">If you enable Microsoft Exchange integration, purging for users homed on Exchange 2013 and with their mailboxes put on In-Place Hold is controlled by Exchange.</span></span> <span data-ttu-id="338ce-194">只有在 Lync Server 檔案共用上儲存的會議檔案的唯一資格。</span><span class="sxs-lookup"><span data-stu-id="338ce-194">The only qualification is for conferencing files, which are stored on the Lync Server file share.</span></span> <span data-ttu-id="338ce-195">這類檔案會在匯出 (上傳至 Exchange) 之後 (選取匯出封存資料之後才清除資料的選項時)，或是達到指定天數上限之後 (指定保留天數上限時) 才從檔案共用中清除。</span><span class="sxs-lookup"><span data-stu-id="338ce-195">These files are purged from the file share only after the files have been exported (uploaded to Exchange), if you select the option to purge data after the archiving data has been exported, or after the specified maximum number of days, if you specify a maximum number of days for retention.</span></span>

    
    </div>

<span data-ttu-id="338ce-196">預設不會啟用任何封存選項。</span><span class="sxs-lookup"><span data-stu-id="338ce-196">By default, no archiving options are enabled.</span></span> <span data-ttu-id="338ce-197">您可以使用 Lync Server 2013 控制台管理封存設定。</span><span class="sxs-lookup"><span data-stu-id="338ce-197">You can manage Archiving configurations using Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="338ce-198">您可以指定下列封存設定：</span><span class="sxs-lookup"><span data-stu-id="338ce-198">You can specify the following Archiving configurations:</span></span>

  - <span data-ttu-id="338ce-199">**全域封存設定**。</span><span class="sxs-lookup"><span data-stu-id="338ce-199">**Global Archiving configuration**.</span></span> <span data-ttu-id="338ce-200">此為預設的封存設定，可套用至您的整個部署。</span><span class="sxs-lookup"><span data-stu-id="338ce-200">This is the default Archiving configuration and applies to your entire deployment.</span></span> <span data-ttu-id="338ce-201">它會在您部署 Lync Server 2013 時建立，而且根據預設，不會啟用封存功能。</span><span class="sxs-lookup"><span data-stu-id="338ce-201">It is created when you deploy Lync Server 2013 and, by default, does not enable archiving functionality.</span></span> <span data-ttu-id="338ce-202">您可以修改全域設定，但無法刪除它。</span><span class="sxs-lookup"><span data-stu-id="338ce-202">You can modify the global configuration, but you cannot delete it.</span></span> <span data-ttu-id="338ce-203">如果您針對設定選擇刪除選項，即會將全域設定重設為預設設定。</span><span class="sxs-lookup"><span data-stu-id="338ce-203">If you choose the delete option for the configuration, the global configuration is reset to the default settings.</span></span>

  - <span data-ttu-id="338ce-p123">**網站封存設定**。您可以選擇性地為一或多個指定的網站設定封存，作法是針對個別網站建立和設定網站層級的封存設定。網站層級的封存設定只有在您建立它時才會存在。您可以修改或刪除任何網站層級的封存設定。網站層級的封存設定優先於全域設定，但僅適用於網站層級設定中指定的網站。例如，如果您在全域設定中僅針對 IM 啟用封存，並建立一個網站設定以針對 IM 和會議啟用封存，則只會針對該網站封存會議，而不會為貴組織的其餘部分封存會議。</span><span class="sxs-lookup"><span data-stu-id="338ce-p123">**Site Archiving configuration**. Optionally, you can configure Archiving for one or more specific sites by creating and configuring a site-level Archiving configuration for an individual site. A site-level Archiving configuration exists only if you create it. You can modify or delete any site-level Archiving configuration. A site-level Archiving configuration overrides the global configuration, but only for the site specified in the site-level configuration. For example, if you enable Archiving for only IM in your global configuration and create a site configuration in which you enable Archiving for both IM and conferencing, conferencing would only be archived for the site, not for the remainder of your organization.</span></span>

  - <span data-ttu-id="338ce-p124">**集區封存設定**。您可以選擇性地為一或多個指定的集區指定封存設定，作法是為個別集區建立和設定集區層級的設定。集區層級的封存設定只有在您建立它時才會存在。您可以修改和刪除任何集區層級的封存設定。集區層級的封存設定優先於全域設定，以及您可能已建立的任何網站封存設定。例如，如果您在全域設定中僅針對 IM 啟用封存，並建立一個網站層級的設定以針對該網站的 IM 和會議啟用封存，接著建立一個集區層級的設定以便僅針對 IM 啟用封存，則會針對網站的所有使用者封存 IM 與會議的通訊，但位於集區層級設定中指定之集區中的使用者例外。針對組織中所有的其他使用者，就只會針對 IM 啟用封存。</span><span class="sxs-lookup"><span data-stu-id="338ce-p124">**Pool Archiving configuration**. Optionally, you can specify Archiving settings for one or more specific pools by creating and configuring a pool-level configuration for the individual pool. A pool-level Archiving configuration exists only if you create it. You can modify and delete any pool-level Archiving configuration. A pool-level Archiving configuration overrides the global configuration and any site archiving configuration you may have created. For example, if you enable Archiving for only IM in your global configuration, create a site-level configuration in which you enable Archiving for both IM and conferencing for the site, and then create a pool-level configuration in which you enable Archiving only for IM, the communications would be archived for both IM and conferencing for all users of the site except the users homed in the pool specified in the pool-level configuration. For all other users in your organization, Archiving would be enabled only for IM.</span></span>

<span data-ttu-id="338ce-217">如需如何在部署封存時設定初始封存設定的詳細資訊，請參閱部署檔中的在 [Lync Server 2013](lync-server-2013-configuring-archiving-options.md) 中設定封存選項。</span><span class="sxs-lookup"><span data-stu-id="338ce-217">For details about how to set up initial Archiving configurations when you deploy Archiving, see [Configuring Archiving options in Lync Server 2013](lync-server-2013-configuring-archiving-options.md) in the Deployment documentation.</span></span> <span data-ttu-id="338ce-218">如需使用封存原則來啟用及停用部署後進行通訊的詳細資訊，請參閱 Operations 檔中的 [管理伺服器、網站及集區的 Lync Server 2013 中的封存配置選項](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) 。</span><span class="sxs-lookup"><span data-stu-id="338ce-218">For details about using Archiving policies to enable and disable communications after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a><span data-ttu-id="338ce-219">僅能在 Windows PowerShell 中使用的封存選項</span><span class="sxs-lookup"><span data-stu-id="338ce-219">Archiving Options Available Only in Windows PowerShell</span></span>

<span data-ttu-id="338ce-220">使用 Lync Server 2013 管理命令介面，您可以使用 Cmdlet 來執行 Lync Server 2013 控制台中不可用的選項。</span><span class="sxs-lookup"><span data-stu-id="338ce-220">Using Lync Server 2013 Management Shell, you can use cmdlets to implement options that are not available in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="338ce-221">這些選項包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="338ce-221">These options include the following:</span></span>

  - <span data-ttu-id="338ce-222">**封存重複的訊息**。</span><span class="sxs-lookup"><span data-stu-id="338ce-222">**Archive duplicate messages**.</span></span> <span data-ttu-id="338ce-223">如需詳細資訊，請參閱作業文件中的 [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) 和 [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="338ce-223">For details, see [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) and [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) in the Operations documentation.</span></span>

  - <span data-ttu-id="338ce-224">**匯出封存的資料**。</span><span class="sxs-lookup"><span data-stu-id="338ce-224">**Export archived data**.</span></span> <span data-ttu-id="338ce-225">如需詳細資訊，請參閱 [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)</span><span class="sxs-lookup"><span data-stu-id="338ce-225">For details, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)</span></span>

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a><span data-ttu-id="338ce-226">如何存取封存的資料？</span><span class="sxs-lookup"><span data-stu-id="338ce-226">How Do I Access Archived Data?</span></span>

<span data-ttu-id="338ce-227">存取封存的資料會根據儲存資料的地方而定：</span><span class="sxs-lookup"><span data-stu-id="338ce-227">Access to archived data is dependent on where the data is stored:</span></span>

  - <span data-ttu-id="338ce-228">**Microsoft Exchange storage**。</span><span class="sxs-lookup"><span data-stu-id="338ce-228">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="338ce-229">如果您選擇 Exchange 整合選項，Lync Server 會在 Exchange 2013 存放區中，針對所有位於 Exchange 2013 的使用者，以及其信箱置於 In-Place 保留狀態的使用者，在 Exchange 存放區中儲蓄內容。</span><span class="sxs-lookup"><span data-stu-id="338ce-229">If you choose the Exchange integration option, Lync Server deposits the archiving content in the Exchange 2013 store for all users who are homed on Exchange 2013, and who have had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="338ce-230">封存的資料儲存在使用者信箱的 [可復原的專案] 資料夾中，該資料夾通常對使用者來說是無法看到的，而且只有具備 Exchange **探索管理** 角色的使用者可以搜尋。</span><span class="sxs-lookup"><span data-stu-id="338ce-230">Archived data is stored in user mailboxes Recoverable items folder, which is generally invisible to users, and can only be searched by users with an Exchange **Discovery Management** role.</span></span> <span data-ttu-id="338ce-231">Exchange 可在部署時，啟用同盟搜尋與探索，以及 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="338ce-231">Exchange enables federated search and discovery, along with SharePoint, if it is deployed.</span></span> <span data-ttu-id="338ce-232">如需儲存在 Exchange 中之資料儲存、保留及探索的詳細資訊，請參閱 Exchange 2013 及 SharePoint 檔。</span><span class="sxs-lookup"><span data-stu-id="338ce-232">For more details about storage, retention, and discovery of data stored in Exchange, see the Exchange 2013 and SharePoint documentation.</span></span>

  - <span data-ttu-id="338ce-233">**Lync Server 儲存**。</span><span class="sxs-lookup"><span data-stu-id="338ce-233">**Lync Server storage**.</span></span> <span data-ttu-id="338ce-234">如果您設定 Lync Server 2013 封存資料庫來儲存 Lync Server 資料，Lync Server 會將封存內容放在 Lync Server 封存資料庫中 (SQL Server 資料庫) ，以供任何不是位於 Exchange 2013 的使用者使用，也不會將其信箱置於 In-Place 保留狀態。</span><span class="sxs-lookup"><span data-stu-id="338ce-234">If you set up Lync Server 2013 Archiving databases for storage of Lync Server data, Lync Server deposits archiving content in the Lync Server Archiving databases (SQL Server databases) for any users not homed on Exchange 2013, and who have not had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="338ce-235">此資料是無法搜尋的，但可匯出為可使用其他工具搜尋的格式。</span><span class="sxs-lookup"><span data-stu-id="338ce-235">This data is not searchable, but it can be exported to formats that are searchable using other tools.</span></span> <span data-ttu-id="338ce-236">如需匯出儲存在封存資料庫中之資料的詳細資訊，請參閱操作檔中的 [從 Lync Server 2013 匯出封存的資料](lync-server-2013-exporting-archived-data.md) 。</span><span class="sxs-lookup"><span data-stu-id="338ce-236">For details about exporting data stored in Archiving databases, see [Exporting archived data from Lync Server 2013](lync-server-2013-exporting-archived-data.md) in the Operations documentation.</span></span>

<span data-ttu-id="338ce-237">如需有關 Lync Server 2013 和 Exchange 2013 如何共同運作的詳細資訊，請參閱支援檔 [中的 Exchange Server 和 SharePoint integration support In Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) 。</span><span class="sxs-lookup"><span data-stu-id="338ce-237">For more details about how Lync Server 2013 and Exchange 2013 work together, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

