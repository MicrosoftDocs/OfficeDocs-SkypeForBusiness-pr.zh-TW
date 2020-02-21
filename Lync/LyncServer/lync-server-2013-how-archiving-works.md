---
title: Lync Server 2013： 封存的運作方式
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
ms.openlocfilehash: 4bc6266cdf81f4462adf82c5878bcc47a6060fdf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-archiving-works-in-lync-server-2013"></a><span data-ttu-id="0f9d7-102">封存 Lync Server 2013 中的運作方式</span><span class="sxs-lookup"><span data-stu-id="0f9d7-102">How Archiving works in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f9d7-103">_**上次修改主題：** 2014年-02-04_</span><span class="sxs-lookup"><span data-stu-id="0f9d7-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="0f9d7-104">Lync Server 2013 Archiving 提供可協助您符合法務遵循需求的選項。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-104">Lync Server 2013 Archiving provides options to help you meet your compliance needs.</span></span> <span data-ttu-id="0f9d7-105">若要實作及維護以最有效率地符合您的組織需求的方式，您應該先了解：</span><span class="sxs-lookup"><span data-stu-id="0f9d7-105">To implement and maintain it in a way that most effectively meets your organization’s requirements, you should understand:</span></span>

  - <span data-ttu-id="0f9d7-106">可以封存哪些資訊。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-106">What information can be archived.</span></span>

  - <span data-ttu-id="0f9d7-107">如何在部署中啟用和停用封存。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-107">How to enable and disable Archiving in your deployment.</span></span>

  - <span data-ttu-id="0f9d7-108">您可以設定來控制如何實作封存的封存選項。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-108">The archiving options that you can configure to control how Archiving is implemented.</span></span>

<div>

## <a name="what-information-can-be-archived"></a><span data-ttu-id="0f9d7-109">可以封存哪些資訊？</span><span class="sxs-lookup"><span data-stu-id="0f9d7-109">What Information Can Be Archived?</span></span>

<span data-ttu-id="0f9d7-110">可以封存下列類型的內容：</span><span class="sxs-lookup"><span data-stu-id="0f9d7-110">The following types of content can be archived:</span></span>

  - <span data-ttu-id="0f9d7-111">對等立即訊息</span><span class="sxs-lookup"><span data-stu-id="0f9d7-111">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="0f9d7-112">會議，其為多方立即訊息</span><span class="sxs-lookup"><span data-stu-id="0f9d7-112">Conferences (meetings), which are multiparty instant messages</span></span>

  - <span data-ttu-id="0f9d7-113">會議內容，包括上傳的內容 (例如，講義) 和事件相關內容 (例如，加入、離開、上傳共用，以及可見度變更)</span><span class="sxs-lookup"><span data-stu-id="0f9d7-113">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

  - <span data-ttu-id="0f9d7-114">在會議期間共用白板與投票</span><span class="sxs-lookup"><span data-stu-id="0f9d7-114">Whiteboards and polls shared during a conference</span></span>

<span data-ttu-id="0f9d7-115">不會封存下列類型的內容：</span><span class="sxs-lookup"><span data-stu-id="0f9d7-115">The following types of content are not archived:</span></span>

  - <span data-ttu-id="0f9d7-116">對等檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="0f9d7-116">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="0f9d7-117">對等立即訊息和會議的音訊/視訊</span><span class="sxs-lookup"><span data-stu-id="0f9d7-117">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="0f9d7-118">對等立即訊息和會議的桌面與應用程式共用</span><span class="sxs-lookup"><span data-stu-id="0f9d7-118">Desktop and application sharing for peer-to-peer instant messages and conferences</span></span>

<span data-ttu-id="0f9d7-119">Lync Server 也不會封存常設聊天室的交談。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-119">Lync Server also does not archive Persistent Chat conversations.</span></span> <span data-ttu-id="0f9d7-120">若要封存常設聊天室的交談，您必須啟用並設定規範服務，也就是可以使用 Microsoft Lync Server 2013，Persistent Chat Server 部署的元件。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-120">To archive Persistent Chat conversations, you must enable and configure the compliance service, which is a component that can be deployed with Microsoft Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="0f9d7-121">如需詳細資訊，請參閱規劃文件中的[Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-121">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a><span data-ttu-id="0f9d7-122">如何開始使用封存？</span><span class="sxs-lookup"><span data-stu-id="0f9d7-122">How Do I Start Using Archiving?</span></span>

<span data-ttu-id="0f9d7-p103">當您部署伺服器時，封存會自動安裝於每部前端伺服器上，但在您設定封存之前不會加以啟用。您設定封存的方式是根據您部署封存的方式來決定：</span><span class="sxs-lookup"><span data-stu-id="0f9d7-p103">Archiving is automatically installed on each Front End Server when you deploy the server, but Archiving is not enabled until you configure it. How you configure it is determined by how you deploy Archiving:</span></span>

  - <span data-ttu-id="0f9d7-125">**封存使用 Microsoft Exchange 整合。**</span><span class="sxs-lookup"><span data-stu-id="0f9d7-125">**Archiving using Microsoft Exchange integration.**</span></span> <span data-ttu-id="0f9d7-126">如果您有位於 Exchange 2013 的使用者，且其信箱已處於就地保留，您可以選取 Exchange 儲存區與整合 Lync Server 2013 儲存體選項。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-126">If you have users who are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can select the option to integrate Lync Server 2013 storage with Exchange storage.</span></span> <span data-ttu-id="0f9d7-127">如果您選擇 [Microsoft Exchange 整合選項，您使用 Exchange 2013 原則和設定來控制這些使用者的 Lync Server 2013 資料的封存。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-127">If you choose the Microsoft Exchange integration option, you use Exchange 2013 policies and configurations to control the archiving of Lync Server 2013 data for those users.</span></span>

  - <span data-ttu-id="0f9d7-128">**使用 Lync Server 封存資料庫的封存。**</span><span class="sxs-lookup"><span data-stu-id="0f9d7-128">**Archiving using Lync Server Archiving databases.**</span></span> <span data-ttu-id="0f9d7-129">如果您有誰不位於 Exchange 2013 或誰不有所放入原有範圍暫止，其信箱的使用者，或如果您不想要用於您的部署中的任一或所有使用者的 Microsoft Exchange 整合，您可以部署 Lync Server 封存資料庫使用 SQL Server 若要儲存這些使用者的封存資料。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-129">If you have users who are not homed on Exchange 2013 or who have not had their mailboxes put on In-Place Hold, or if you don’t want to use Microsoft Exchange integration for any or all users in your deployment, you can deploy Lync Server Archiving databases using SQL Server to store Archiving data for those users.</span></span> <span data-ttu-id="0f9d7-130">在此情況下，Lync Server 2013 封存原則和設定決定是否要啟用封存，並實作方式。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-130">In this case, Lync Server 2013 Archiving policies and configurations determine whether Archiving is enabled and how it is implemented.</span></span> <span data-ttu-id="0f9d7-131">若要使用 Lync Server 2013，您必須將適當的 SQL Server 資料庫新增至您的拓撲，並發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-131">To use Lync Server 2013, you must add the appropriate SQL Server databases to your topology and publish the topology.</span></span>

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a><span data-ttu-id="0f9d7-132">使用 Microsoft Exchange 整合時進行封存設定</span><span class="sxs-lookup"><span data-stu-id="0f9d7-132">Archiving Setup When Using Microsoft Exchange Integration</span></span>

<span data-ttu-id="0f9d7-133">如果您的使用者位於 Exchange 2013 和他們的信箱已處於就地保留，您可以封存 Lync Server 2013 的使用者，選擇 [ **Microsoft Exchange 整合**] 選項 （如本節稍後所述），然後您可以控制這些使用者的封存藉由指定 Exchange 就地保留原則和設定，以及 Lync Server 設定以控制下列：</span><span class="sxs-lookup"><span data-stu-id="0f9d7-133">If your users are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can choose the **Microsoft Exchange integration** option (as described later in this section) to archive Lync Server 2013 for those users, and then you control archiving for those users by specifying Exchange In-Place Hold policies and settings, as well as Lync Server configurations to control the following:</span></span>

  - <span data-ttu-id="0f9d7-134">是否要封存 IM、會議或兩者。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-134">Whether to archive IM, conferencing, or both.</span></span>

  - <span data-ttu-id="0f9d7-135">是否要實作 Lync Server 部署的關鍵模式。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-135">Whether to implement critical mode for your Lync Server deployment.</span></span>

  - <span data-ttu-id="0f9d7-136">Microsoft Exchange 整合選項，以使用 Exchange 2013 來儲存封存資料的選取範圍。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-136">Selection of the Microsoft Exchange integration option to use Exchange 2013 for storage of archived data.</span></span>

<span data-ttu-id="0f9d7-137">本節中稍後說明這些 Lync Server 2013 封存組態選項。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-137">These Lync Server 2013 Archiving configuration options are described later in this section.</span></span> <span data-ttu-id="0f9d7-138">如需如何設定 Exchange 就地保留原則和設定來支援封存的詳細資訊，請參閱 < Exchange 2013 產品的說明文件。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-138">For information about how to configure Exchange In-Place Hold policies and settings to support archiving, see the Exchange 2013 product documentation.</span></span>

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a><span data-ttu-id="0f9d7-139">使用 Lync Server 封存資料庫儲存時進行封存設定</span><span class="sxs-lookup"><span data-stu-id="0f9d7-139">Archiving Setup When Using Lync Server Archiving Database Storage</span></span>

<span data-ttu-id="0f9d7-140">如果您想要使用 Lync Server 封存資料庫 （使用 SQL Server 資料庫） 封存的部署中的任何使用者資料，您可以設定 Lync Server 封存原則以控制是否為這些使用者啟用封存。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-140">If you want to use Lync Server Archiving databases (using SQL Server databases) to archive data for any users in your deployment, you can configure Lync Server Archiving policies to control whether Archiving is enabled for those users.</span></span> <span data-ttu-id="0f9d7-141">在每個封存原則中，您可以針對下列其中一項或兩項來啟用或停用封存：</span><span class="sxs-lookup"><span data-stu-id="0f9d7-141">In each Archiving policy, you can enable or disable Archiving for either or both of the following:</span></span>

  - <span data-ttu-id="0f9d7-142">內部通訊</span><span class="sxs-lookup"><span data-stu-id="0f9d7-142">Internal communications</span></span>

  - <span data-ttu-id="0f9d7-143">外部通訊</span><span class="sxs-lookup"><span data-stu-id="0f9d7-143">External communications</span></span>

<span data-ttu-id="0f9d7-144">根據預設，封存未啟用內部通訊或任何 Lync Server 封存原則中的外部通訊。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-144">By default, archiving is not enabled for internal communications or external communications in any Lync Server Archiving policy.</span></span> <span data-ttu-id="0f9d7-145">您啟用及停用通訊使用 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面中使用指令程式。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-145">You enable and disable communications using Lync Server 2013 Control Panel or using cmdlets in the Lync Server 2013 Management Shell.</span></span>

<span data-ttu-id="0f9d7-146">Lync Server 2013 封存原則包含下列：</span><span class="sxs-lookup"><span data-stu-id="0f9d7-146">Lync Server 2013 Archiving policies include the following:</span></span>

  - <span data-ttu-id="0f9d7-147">**全域封存原則**。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-147">**Global Archiving policy**.</span></span> <span data-ttu-id="0f9d7-148">此為預設的封存原則，可以套用至您的整個部署。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-148">This is the default Archiving policy and applies to your entire deployment.</span></span> <span data-ttu-id="0f9d7-149">它會建立部署 Lync Server 2013 時，並依預設，會停用封存的內部與外部通訊。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-149">It is created when you deploy Lync Server 2013 and, by default, disables Archiving for both internal and external communications.</span></span> <span data-ttu-id="0f9d7-150">您無法刪除此原則。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-150">You cannot delete this policy.</span></span> <span data-ttu-id="0f9d7-151">如果您選擇刪除選項，即會將全域原則重設為預設設定。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-151">If you choose the delete option, the global policy is reset to the default settings.</span></span>

  - <span data-ttu-id="0f9d7-p110">**網站封存原則**。您可以選擇性地為一或多個指定網站啟用或停用封存，作法是針對該網站建立和設定網站層級的封存原則。當您建立網站層級的封存原則時，預設不會啟用封存。您可以刪除任何您建立之網站層級的封存原則。網站層級的封存原則優先於全域原則，但僅適用於原則中指定的網站。例如，如果您在全域原則中針對內部與外部通訊啟用封存，然後建立一個網站原則以針對外部通訊停用封存，則只會針對該網站封存內部通訊。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-p110">**Site Archiving policy**. Optionally, you can enable or disable Archiving for one or more specific sites by creating and configuring a site-level Archiving policy for the site. When you create a site-level Archiving policy, by default, archiving is not enabled. You can delete any site-level Archiving policy that you create. A site-level Archiving policy overrides the global policy, but only for the site specified in the policy. For example, if you enable Archiving for internal and external communications in your global policy and create a site policy in which you disable Archiving for external communications, only internal communications would be archived for that site.</span></span>

  - <span data-ttu-id="0f9d7-p111">**使用者封存原則**。您可以選擇性地為一或多個特定使用者或使用者群組啟用或停用封存，作法是為指定的使用者和使用者群組建立、設定及套用使用者層級的封存原則。當您建立使用者層級的封存原則時，預設不會啟用封存。您可以刪除任何您建立之使用者層級的封存原則，而且可以變更要套用封存原則的使用者與使用者群組。使用者層級的封存原則優先於全域原則及所有網站原則，但僅適用於套用原則的使用者和使用者群組。例如，如果您在全域原則中針對內部與外部通訊停用封存、建立一個網站層級的原則以針對內部與外部通訊啟用封存，然後建立一個使用者層級的原則以針對外部通訊停用封存，則系統將針對所有網站使用者的外部與內部通訊封存通訊，但您套用使用者層級原則的使用者例外，只會為他們封存內部通訊。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-p111">**User Archiving policy**. Optionally, you can enable or disable Archiving for one or more specific users and group of users by creating, configuring, and applying a user-level Archiving policy for the specified users and user groups. When you create a user-level Archiving policy, by default, archiving is not enabled. You can delete any user-level Archiving policy that you create, and you can change which users and group of users the Archiving policy applies to. A user-level Archiving policy overrides the global policy and any site policies, but only for the users and user groups to whom the policy is applied. For example, if you disable Archiving for internal and external communications in your global policy, create a site-level policy in which you enable Archiving for internal and external communications, and then create a user-level policy in which you disable Archiving for external communications, the communications would be archived for both external and internal communications for all site users except that, for the users to whom you apply the user-level policy, only internal communications would be archived.</span></span>

<span data-ttu-id="0f9d7-164">如需如何設定初始封存原則，當您部署封存的詳細資訊，請參閱部署文件中的[設定和指派 Lync Server 2013 中的封存原則](lync-server-2013-configuring-and-assigning-archiving-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-164">For details about how to set up initial Archiving policies when you deploy Archiving, see [Configuring and assigning Archiving policies in Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="0f9d7-165">如需使用封存原則來啟用及停用通訊部署後的詳細資訊，請參閱作業文件中的[管理 Lync Server 2013 中的內部和外部通訊的封存](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-165">For details about using Archiving policies to enable and disable communications after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0f9d7-166">如果您實作這兩個 Lync Server 2013 封存資料庫，並啟用 Microsoft Exchange 整合，Exchange 2013 原則會覆寫 Lync Server 封存原則，但僅針對使用者位於 Exchange 2013，並有鎖其信箱置於就地保留.</span><span class="sxs-lookup"><span data-stu-id="0f9d7-166">If you implement both Lync Server 2013 Archiving databases and enable Microsoft Exchange integration, Exchange 2013 policies override Lync Server Archiving policies, but only for users who are homed on Exchange 2013 and have had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="0f9d7-167">Lync Archiving 取決於僅 Microsoft Exchange 就地保留原則。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-167">Lync Archiving depends on Microsoft Exchange In-Place Hold policy only.</span></span>



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a><span data-ttu-id="0f9d7-168">我可以使用哪些選項來設定封存？</span><span class="sxs-lookup"><span data-stu-id="0f9d7-168">What Options Do I Have for Configuring Archiving?</span></span>

<span data-ttu-id="0f9d7-169">除了使用原則及啟用與停用封存，您還有其他封存選項可用來為整個部署進行設定，而且可以選擇性地針對特定的網站與集區進行設定。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-169">In addition to using policies and to enable and disable Archiving, you have other Archiving options that can be configure for your entire deployment and, optionally, for specific sites and pools.</span></span> <span data-ttu-id="0f9d7-170">您可以使用一或多個封存組態，其中可使用 Lync Server 2013 控制台，但也有另一個選項，只適用於使用 Lync Server 2013 管理命令介面設定，以控制大部分的封存選項。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-170">You control most Archiving options by using one or more Archiving configurations, which are available in Lync Server 2013 Control Panel, but also have another option that is only available for configuration using Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a><span data-ttu-id="0f9d7-171">Lync Server 2013 控制台中的封存設定選項</span><span class="sxs-lookup"><span data-stu-id="0f9d7-171">Archiving Configuration Options Available in Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="0f9d7-172">每個封存設定都會提供下列選項：</span><span class="sxs-lookup"><span data-stu-id="0f9d7-172">Each archiving configuration provides the following options:</span></span>

<span data-ttu-id="0f9d7-p115">部署封存時會自動建立全域層級的設定，全域層級的設定可加以設定，但不能刪除。如果您選取選項來刪除全域設定，即會將設定重設為預設值。您可以建立多個網站與集區設定，與全域設定一起使用來控制封存設定。針對全域設定及每個台站與集區設定，您會有下列選項：</span><span class="sxs-lookup"><span data-stu-id="0f9d7-p115">The global-level configuration is created automatically when you deploy archiving and can be configured, but not deleted. If you select the option to delete the global configuration, the settings are reset to the default values. You can create multiple site and pool configurations that, together with the global configuration, control archiving settings. For the global configuration and each site and pool configuration, you have the following options:</span></span>

  - <span data-ttu-id="0f9d7-177">停用封存、僅針對立即訊息 (IM) 啟用封存，或者針對 IM 和會議啟用封存</span><span class="sxs-lookup"><span data-stu-id="0f9d7-177">Disable archiving, enable archiving only for instant messaging (IM), or enable archiving of both IM and conferencing.</span></span>

  - <span data-ttu-id="0f9d7-178">在 Lync 伺服器故障時設定嚴重模式以封鎖 IM 與會議工作階段。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-178">Configure critical mode to block IM and conferencing sessions in the event of a Lync Server failure.</span></span> <span data-ttu-id="0f9d7-179">失敗包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="0f9d7-179">Failures include the following:</span></span>
    
      - <span data-ttu-id="0f9d7-180">**IM**。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-180">**IM**.</span></span> <span data-ttu-id="0f9d7-181">Lync Server 儲存體服務發生問題。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-181">A problem with the Lync Server storage service.</span></span> <span data-ttu-id="0f9d7-182">在此情況下，會針對已啟用封存的使用者封鎖 IM。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-182">In this case, IM is blocked for users who are enabled for Archiving.</span></span>
    
      - <span data-ttu-id="0f9d7-p118">**會議**。失敗可能是無法使用的檔案共用，或是儲存服務發生問題。在此情況下，所有失敗時於集區中舉行的作用中會議都會切換為限制模式，並且無法啟動新會議。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-p118">**Conferencing**. A failure could be an unavailable file share or a problem with the storage service. In this case, all active conferences hosted in the pool at the time of failure are switched to restricted mode and new conferences cannot be activated.</span></span>
    
    <span data-ttu-id="0f9d7-186">IM 和會議會在更正失敗之後自動復原。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-186">Both IM and conferencing automatically recover after the failures are corrected.</span></span>

  - <span data-ttu-id="0f9d7-187">指定要用於儲存封存資料，而非設定個別的 SQL Server 資料庫來儲存封存資料的 Lync Server 2013 中的 Exchange 2013 的 Microsoft Exchange Server 2013 整合的使用。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-187">Specify the use of Microsoft Exchange Server 2013 integration to use Exchange 2013 for storage of archived data, instead of setting up separate SQL Server databases for storage of Lync Server 2013 archiving data.</span></span>

  - <span data-ttu-id="0f9d7-p119">設定封存資料的清除選項。這包含指定何時清除封存的資料，可以是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="0f9d7-p119">Configure purging options for archived data. This includes specifying when to purge archived data, which can be either of the following:</span></span>
    
      - <span data-ttu-id="0f9d7-190">在您指定的特定天數之後</span><span class="sxs-lookup"><span data-stu-id="0f9d7-190">After a specific number of days that you specify</span></span>
    
      - <span data-ttu-id="0f9d7-191">封存資料匯出之後 （其中包含資料已上傳至 Exchange，如果您啟用 Microsoft Exchange 整合）。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-191">After the archiving data has been exported (which includes data that has been uploaded to Exchange, if you enable Microsoft Exchange integration).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0f9d7-192">如果您啟用 Microsoft Exchange 整合，清除使用者位於 Exchange 2013，以及與他們放入原有範圍暫止的信箱由控制 Exchange。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-192">If you enable Microsoft Exchange integration, purging for users homed on Exchange 2013 and with their mailboxes put on In-Place Hold is controlled by Exchange.</span></span> <span data-ttu-id="0f9d7-193">唯一限定性條件適用於儲存在 Lync Server 檔案共用的會議檔案。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-193">The only qualification is for conferencing files, which are stored on the Lync Server file share.</span></span> <span data-ttu-id="0f9d7-194">這類檔案會在匯出 (上傳至 Exchange) 之後 (選取匯出封存資料之後才清除資料的選項時)，或是達到指定天數上限之後 (指定保留天數上限時) 才從檔案共用中清除。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-194">These files are purged from the file share only after the files have been exported (uploaded to Exchange), if you select the option to purge data after the archiving data has been exported, or after the specified maximum number of days, if you specify a maximum number of days for retention.</span></span>

    
    </div>

<span data-ttu-id="0f9d7-195">預設不會啟用任何封存選項。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-195">By default, no archiving options are enabled.</span></span> <span data-ttu-id="0f9d7-196">您可以管理使用 Lync Server 2013 控制台的封存組態。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-196">You can manage Archiving configurations using Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="0f9d7-197">您可以指定下列封存設定：</span><span class="sxs-lookup"><span data-stu-id="0f9d7-197">You can specify the following Archiving configurations:</span></span>

  - <span data-ttu-id="0f9d7-198">**全域封存設定**。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-198">**Global Archiving configuration**.</span></span> <span data-ttu-id="0f9d7-199">此為預設的封存設定，可套用至您的整個部署。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-199">This is the default Archiving configuration and applies to your entire deployment.</span></span> <span data-ttu-id="0f9d7-200">它會建立當您部署 Lync Server 2013，根據預設，不會啟用封存功能。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-200">It is created when you deploy Lync Server 2013 and, by default, does not enable archiving functionality.</span></span> <span data-ttu-id="0f9d7-201">您可以修改全域設定，但無法刪除它。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-201">You can modify the global configuration, but you cannot delete it.</span></span> <span data-ttu-id="0f9d7-202">如果您針對設定選擇刪除選項，即會將全域設定重設為預設設定。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-202">If you choose the delete option for the configuration, the global configuration is reset to the default settings.</span></span>

  - <span data-ttu-id="0f9d7-p123">**網站封存設定**。您可以選擇性地為一或多個指定的網站設定封存，作法是針對個別網站建立和設定網站層級的封存設定。網站層級的封存設定只有在您建立它時才會存在。您可以修改或刪除任何網站層級的封存設定。網站層級的封存設定優先於全域設定，但僅適用於網站層級設定中指定的網站。例如，如果您在全域設定中僅針對 IM 啟用封存，並建立一個網站設定以針對 IM 和會議啟用封存，則只會針對該網站封存會議，而不會為貴組織的其餘部分封存會議。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-p123">**Site Archiving configuration**. Optionally, you can configure Archiving for one or more specific sites by creating and configuring a site-level Archiving configuration for an individual site. A site-level Archiving configuration exists only if you create it. You can modify or delete any site-level Archiving configuration. A site-level Archiving configuration overrides the global configuration, but only for the site specified in the site-level configuration. For example, if you enable Archiving for only IM in your global configuration and create a site configuration in which you enable Archiving for both IM and conferencing, conferencing would only be archived for the site, not for the remainder of your organization.</span></span>

  - <span data-ttu-id="0f9d7-p124">**集區封存設定**。您可以選擇性地為一或多個指定的集區指定封存設定，作法是為個別集區建立和設定集區層級的設定。集區層級的封存設定只有在您建立它時才會存在。您可以修改和刪除任何集區層級的封存設定。集區層級的封存設定優先於全域設定，以及您可能已建立的任何網站封存設定。例如，如果您在全域設定中僅針對 IM 啟用封存，並建立一個網站層級的設定以針對該網站的 IM 和會議啟用封存，接著建立一個集區層級的設定以便僅針對 IM 啟用封存，則會針對網站的所有使用者封存 IM 與會議的通訊，但位於集區層級設定中指定之集區中的使用者例外。針對組織中所有的其他使用者，就只會針對 IM 啟用封存。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-p124">**Pool Archiving configuration**. Optionally, you can specify Archiving settings for one or more specific pools by creating and configuring a pool-level configuration for the individual pool. A pool-level Archiving configuration exists only if you create it. You can modify and delete any pool-level Archiving configuration. A pool-level Archiving configuration overrides the global configuration and any site archiving configuration you may have created. For example, if you enable Archiving for only IM in your global configuration, create a site-level configuration in which you enable Archiving for both IM and conferencing for the site, and then create a pool-level configuration in which you enable Archiving only for IM, the communications would be archived for both IM and conferencing for all users of the site except the users homed in the pool specified in the pool-level configuration. For all other users in your organization, Archiving would be enabled only for IM.</span></span>

<span data-ttu-id="0f9d7-216">如需如何設定初始封存組態，當您部署封存的詳細資訊，請參閱部署文件中的[Lync Server 2013 中的設定封存選項](lync-server-2013-configuring-archiving-options.md)。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-216">For details about how to set up initial Archiving configurations when you deploy Archiving, see [Configuring Archiving options in Lync Server 2013](lync-server-2013-configuring-archiving-options.md) in the Deployment documentation.</span></span> <span data-ttu-id="0f9d7-217">如需使用封存原則來啟用及停用通訊部署後的詳細資訊，請參閱作業文件中的[組織、 網站及集區的 Lync Server 2013 中管理封存組態選項](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-217">For details about using Archiving policies to enable and disable communications after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a><span data-ttu-id="0f9d7-218">僅能在 Windows PowerShell 中使用的封存選項</span><span class="sxs-lookup"><span data-stu-id="0f9d7-218">Archiving Options Available Only in Windows PowerShell</span></span>

<span data-ttu-id="0f9d7-219">使用 Lync Server 2013 管理命令介面，您可以使用 cmdlet 來實作 Lync Server 2013 控制台] 中所沒有的選項。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-219">Using Lync Server 2013 Management Shell, you can use cmdlets to implement options that are not available in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="0f9d7-220">這些選項包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="0f9d7-220">These options include the following:</span></span>

  - <span data-ttu-id="0f9d7-221">**封存重複的訊息**。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-221">**Archive duplicate messages**.</span></span> <span data-ttu-id="0f9d7-222">如需詳細資訊，請參閱作業文件中的 [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) 和 [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-222">For details, see [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) and [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) in the Operations documentation.</span></span>

  - <span data-ttu-id="0f9d7-223">**匯出封存的資料**。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-223">**Export archived data**.</span></span> <span data-ttu-id="0f9d7-224">如需詳細資訊，請參閱 [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)</span><span class="sxs-lookup"><span data-stu-id="0f9d7-224">For details, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)</span></span>

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a><span data-ttu-id="0f9d7-225">如何存取封存的資料？</span><span class="sxs-lookup"><span data-stu-id="0f9d7-225">How Do I Access Archived Data?</span></span>

<span data-ttu-id="0f9d7-226">存取封存的資料會根據儲存資料的地方而定：</span><span class="sxs-lookup"><span data-stu-id="0f9d7-226">Access to archived data is dependent on where the data is stored:</span></span>

  - <span data-ttu-id="0f9d7-227">**Microsoft Exchange 儲存區**。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-227">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="0f9d7-228">如果您選擇 [Exchange 整合選項，則 Lync Server deposits 誰位於 Exchange 2013 中，以及誰已有將信箱置於 「 就地保留 」 狀態的所有使用者的 Exchange 2013 儲存區中封存的內容。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-228">If you choose the Exchange integration option, Lync Server deposits the archiving content in the Exchange 2013 store for all users who are homed on Exchange 2013, and who have had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="0f9d7-229">封存的資料會儲存使用者信箱 [可復原的項目] 資料夾中，也就是一般使用者看不到，僅可搜尋的使用者與 Exchange**探索管理**角色。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-229">Archived data is stored in user mailboxes Recoverable items folder, which is generally invisible to users, and can only be searched by users with an Exchange **Discovery Management** role.</span></span> <span data-ttu-id="0f9d7-230">Exchange 可讓同盟的搜尋及探索，以及 SharePoint，如果部署。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-230">Exchange enables federated search and discovery, along with SharePoint, if it is deployed.</span></span> <span data-ttu-id="0f9d7-231">如需詳細資訊儲存、 保留和探索 Exchange 中儲存的資料，請參閱 Exchange 2013 和 SharePoint 文件。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-231">For more details about storage, retention, and discovery of data stored in Exchange, see the Exchange 2013 and SharePoint documentation.</span></span>

  - <span data-ttu-id="0f9d7-232">**Lync Server 儲存**。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-232">**Lync Server storage**.</span></span> <span data-ttu-id="0f9d7-233">如果您設定 Lync Server 2013 封存資料庫來儲存 Lync Server 資料時，不封存內容中的 Lync Server 封存資料庫 （SQL Server 資料庫） 的任何使用者的 Lync Server 存款位於 Exchange 2013 中，以及誰具有不有放入其信箱原有範圍暫止。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-233">If you set up Lync Server 2013 Archiving databases for storage of Lync Server data, Lync Server deposits archiving content in the Lync Server Archiving databases (SQL Server databases) for any users not homed on Exchange 2013, and who have not had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="0f9d7-234">此資料是無法搜尋的，但可匯出為可使用其他工具搜尋的格式。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-234">This data is not searchable, but it can be exported to formats that are searchable using other tools.</span></span> <span data-ttu-id="0f9d7-235">如需匯出資料儲存在封存資料庫的詳細資訊，請參閱作業文件中的[匯出封存的資料從 Lync Server 2013](lync-server-2013-exporting-archived-data.md) 。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-235">For details about exporting data stored in Archiving databases, see [Exporting archived data from Lync Server 2013](lync-server-2013-exporting-archived-data.md) in the Operations documentation.</span></span>

<span data-ttu-id="0f9d7-236">如需有關 Lync Server 2013 和 Exchange 2013 如何共同運作的詳細資訊，請參閱支援文件中的[Exchange Server 與 Lync Server 2013 中支援的 SharePoint 整合](lync-server-2013-exchange-and-sharepoint-integration-support.md)。</span><span class="sxs-lookup"><span data-stu-id="0f9d7-236">For more details about how Lync Server 2013 and Exchange 2013 work together, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

