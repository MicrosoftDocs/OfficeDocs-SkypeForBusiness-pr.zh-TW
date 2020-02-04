---
title: Lync Server 2013：存檔的運作方式
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
ms.openlocfilehash: ca026dcfb9b994353de139b6e10ecd419c9dd165
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-archiving-works-in-lync-server-2013"></a><span data-ttu-id="5025b-102">存檔在 Lync Server 2013 中的運作方式</span><span class="sxs-lookup"><span data-stu-id="5025b-102">How Archiving works in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5025b-103">_**主題上次修改日期：** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="5025b-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="5025b-104">Lync Server 2013 封存提供可協助您符合合規性需求的選項。</span><span class="sxs-lookup"><span data-stu-id="5025b-104">Lync Server 2013 Archiving provides options to help you meet your compliance needs.</span></span> <span data-ttu-id="5025b-105">若要以最有效地符合貴組織需求的方式來實施及維護，您應該瞭解：</span><span class="sxs-lookup"><span data-stu-id="5025b-105">To implement and maintain it in a way that most effectively meets your organization’s requirements, you should understand:</span></span>

  - <span data-ttu-id="5025b-106">您可以封存哪些資訊。</span><span class="sxs-lookup"><span data-stu-id="5025b-106">What information can be archived.</span></span>

  - <span data-ttu-id="5025b-107">如何在您的部署中啟用和停用封存。</span><span class="sxs-lookup"><span data-stu-id="5025b-107">How to enable and disable Archiving in your deployment.</span></span>

  - <span data-ttu-id="5025b-108">您可以設定的封存選項，以控制實施封存的方式。</span><span class="sxs-lookup"><span data-stu-id="5025b-108">The archiving options that you can configure to control how Archiving is implemented.</span></span>

<div>

## <a name="what-information-can-be-archived"></a><span data-ttu-id="5025b-109">哪些資訊可以封存？</span><span class="sxs-lookup"><span data-stu-id="5025b-109">What Information Can Be Archived?</span></span>

<span data-ttu-id="5025b-110">您可以封存下列內容類型：</span><span class="sxs-lookup"><span data-stu-id="5025b-110">The following types of content can be archived:</span></span>

  - <span data-ttu-id="5025b-111">對等立即訊息</span><span class="sxs-lookup"><span data-stu-id="5025b-111">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="5025b-112">會議（會議），這是多方立即訊息</span><span class="sxs-lookup"><span data-stu-id="5025b-112">Conferences (meetings), which are multiparty instant messages</span></span>

  - <span data-ttu-id="5025b-113">會議內容，包括上傳的內容（例如講義）及事件相關內容（例如加入、離開、上傳共用，以及在可見度中變更）</span><span class="sxs-lookup"><span data-stu-id="5025b-113">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

  - <span data-ttu-id="5025b-114">在會議期間共用白板和投票</span><span class="sxs-lookup"><span data-stu-id="5025b-114">Whiteboards and polls shared during a conference</span></span>

<span data-ttu-id="5025b-115">下列內容類型沒有封存：</span><span class="sxs-lookup"><span data-stu-id="5025b-115">The following types of content are not archived:</span></span>

  - <span data-ttu-id="5025b-116">對等檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="5025b-116">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="5025b-117">對等立即訊息與會議的音訊/視頻</span><span class="sxs-lookup"><span data-stu-id="5025b-117">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="5025b-118">對等立即訊息和會議的桌面與應用程式共用</span><span class="sxs-lookup"><span data-stu-id="5025b-118">Desktop and application sharing for peer-to-peer instant messages and conferences</span></span>

<span data-ttu-id="5025b-119">Lync Server 也不封存持久的聊天交談。</span><span class="sxs-lookup"><span data-stu-id="5025b-119">Lync Server also does not archive Persistent Chat conversations.</span></span> <span data-ttu-id="5025b-120">若要封存持續聊天交談，您必須啟用並設定合規性服務，這是可使用 Microsoft Lync Server 2013、持久聊天伺服器部署的元件。</span><span class="sxs-lookup"><span data-stu-id="5025b-120">To archive Persistent Chat conversations, you must enable and configure the compliance service, which is a component that can be deployed with Microsoft Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="5025b-121">如需詳細資訊，請參閱規劃檔中的[Lync server 2013 中的持續聊天伺服器規劃](lync-server-2013-planning-for-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="5025b-121">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a><span data-ttu-id="5025b-122">我要如何開始使用存檔？</span><span class="sxs-lookup"><span data-stu-id="5025b-122">How Do I Start Using Archiving?</span></span>

<span data-ttu-id="5025b-123">當您部署伺服器時，會在每個前端伺服器上自動安裝封存，但除非您設定存檔，否則不會啟用封存。</span><span class="sxs-lookup"><span data-stu-id="5025b-123">Archiving is automatically installed on each Front End Server when you deploy the server, but Archiving is not enabled until you configure it.</span></span> <span data-ttu-id="5025b-124">您設定的方式取決於您部署存檔的方式：</span><span class="sxs-lookup"><span data-stu-id="5025b-124">How you configure it is determined by how you deploy Archiving:</span></span>

  - <span data-ttu-id="5025b-125">**使用 Microsoft Exchange 整合進行封存。**</span><span class="sxs-lookup"><span data-stu-id="5025b-125">**Archiving using Microsoft Exchange integration.**</span></span> <span data-ttu-id="5025b-126">如果您擁有託管于 Exchange 2013 的使用者，且其信箱已放在就地保留中，您可以選取將 Lync Server 2013 儲存空間與 Exchange 儲存體整合的選項。</span><span class="sxs-lookup"><span data-stu-id="5025b-126">If you have users who are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can select the option to integrate Lync Server 2013 storage with Exchange storage.</span></span> <span data-ttu-id="5025b-127">如果您選擇 [Microsoft Exchange 整合] 選項，您可以使用 Exchange 2013 原則和設定來控制這些使用者的 Lync Server 2013 資料的存檔。</span><span class="sxs-lookup"><span data-stu-id="5025b-127">If you choose the Microsoft Exchange integration option, you use Exchange 2013 policies and configurations to control the archiving of Lync Server 2013 data for those users.</span></span>

  - <span data-ttu-id="5025b-128">**使用 Lync Server 封存資料庫進行封存。**</span><span class="sxs-lookup"><span data-stu-id="5025b-128">**Archiving using Lync Server Archiving databases.**</span></span> <span data-ttu-id="5025b-129">如果您有非託管于 Exchange 2013 的使用者，或未將其信箱放在就地保留中的使用者，或者您不想針對部署中的任何或所有使用者使用 Microsoft Exchange 整合，就可以使用 SQL Server 部署 Lync Server 封存資料庫 儲存這些使用者的存檔資料。</span><span class="sxs-lookup"><span data-stu-id="5025b-129">If you have users who are not homed on Exchange 2013 or who have not had their mailboxes put on In-Place Hold, or if you don’t want to use Microsoft Exchange integration for any or all users in your deployment, you can deploy Lync Server Archiving databases using SQL Server to store Archiving data for those users.</span></span> <span data-ttu-id="5025b-130">在這種情況下，Lync Server 2013 封存原則和設定會判斷是否已啟用並執行封存。</span><span class="sxs-lookup"><span data-stu-id="5025b-130">In this case, Lync Server 2013 Archiving policies and configurations determine whether Archiving is enabled and how it is implemented.</span></span> <span data-ttu-id="5025b-131">若要使用 Lync Server 2013，您必須在拓撲中新增適當的 SQL Server 資料庫，然後發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="5025b-131">To use Lync Server 2013, you must add the appropriate SQL Server databases to your topology and publish the topology.</span></span>

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a><span data-ttu-id="5025b-132">使用 Microsoft Exchange 整合時的存檔設定</span><span class="sxs-lookup"><span data-stu-id="5025b-132">Archiving Setup When Using Microsoft Exchange Integration</span></span>

<span data-ttu-id="5025b-133">如果您的使用者是駐留在 Exchange 2013 上，且其信箱已放在就地保留中，您可以選擇 [ **Microsoft Exchange 整合**] 選項（如本節稍後所述），以封存這些使用者的 Lync server 2013，然後使用 [Exchange 就地保留原則] 和 [設定]，以及 [Lync 伺服器設定] 控制這些使用者的歸檔，以控制下列各項：</span><span class="sxs-lookup"><span data-stu-id="5025b-133">If your users are homed on Exchange 2013 and their mailboxes have been put on In-Place Hold, you can choose the **Microsoft Exchange integration** option (as described later in this section) to archive Lync Server 2013 for those users, and then you control archiving for those users by specifying Exchange In-Place Hold policies and settings, as well as Lync Server configurations to control the following:</span></span>

  - <span data-ttu-id="5025b-134">是否要封存 IM、會議或兩者。</span><span class="sxs-lookup"><span data-stu-id="5025b-134">Whether to archive IM, conferencing, or both.</span></span>

  - <span data-ttu-id="5025b-135">是否要為 Lync Server 部署實現重要模式。</span><span class="sxs-lookup"><span data-stu-id="5025b-135">Whether to implement critical mode for your Lync Server deployment.</span></span>

  - <span data-ttu-id="5025b-136">選取 [Microsoft Exchange 整合] 選項，即可使用 Exchange 2013 儲存已歸檔的資料。</span><span class="sxs-lookup"><span data-stu-id="5025b-136">Selection of the Microsoft Exchange integration option to use Exchange 2013 for storage of archived data.</span></span>

<span data-ttu-id="5025b-137">此區段稍後會說明這些 Lync Server 2013 封存配置選項。</span><span class="sxs-lookup"><span data-stu-id="5025b-137">These Lync Server 2013 Archiving configuration options are described later in this section.</span></span> <span data-ttu-id="5025b-138">如需如何設定 Exchange 就地保留原則和設定以支援封存的相關資訊，請參閱 Exchange 2013 產品檔。</span><span class="sxs-lookup"><span data-stu-id="5025b-138">For information about how to configure Exchange In-Place Hold policies and settings to support archiving, see the Exchange 2013 product documentation.</span></span>

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a><span data-ttu-id="5025b-139">使用 Lync Server 封存資料庫儲存空間時的存檔設定</span><span class="sxs-lookup"><span data-stu-id="5025b-139">Archiving Setup When Using Lync Server Archiving Database Storage</span></span>

<span data-ttu-id="5025b-140">如果您想要使用 Lync Server 封存資料庫（使用 SQL Server 資料庫）來為您部署中的任何使用者封存資料，您可以設定 Lync Server 封存原則來控制是否已針對這些使用者啟用封存功能。</span><span class="sxs-lookup"><span data-stu-id="5025b-140">If you want to use Lync Server Archiving databases (using SQL Server databases) to archive data for any users in your deployment, you can configure Lync Server Archiving policies to control whether Archiving is enabled for those users.</span></span> <span data-ttu-id="5025b-141">在每個存檔原則中，您可以啟用或停用下列其中一項或兩項作業：</span><span class="sxs-lookup"><span data-stu-id="5025b-141">In each Archiving policy, you can enable or disable Archiving for either or both of the following:</span></span>

  - <span data-ttu-id="5025b-142">內部通訊</span><span class="sxs-lookup"><span data-stu-id="5025b-142">Internal communications</span></span>

  - <span data-ttu-id="5025b-143">外部通訊</span><span class="sxs-lookup"><span data-stu-id="5025b-143">External communications</span></span>

<span data-ttu-id="5025b-144">根據預設，在任何 Lync Server 存檔原則中，都不會針對內部通訊或外部通訊啟用封存。</span><span class="sxs-lookup"><span data-stu-id="5025b-144">By default, archiving is not enabled for internal communications or external communications in any Lync Server Archiving policy.</span></span> <span data-ttu-id="5025b-145">您可以使用 Lync Server 2013 [控制台] 或在 Lync Server 2013 管理命令介面中使用 Cmdlet 來啟用和停用通訊。</span><span class="sxs-lookup"><span data-stu-id="5025b-145">You enable and disable communications using Lync Server 2013 Control Panel or using cmdlets in the Lync Server 2013 Management Shell.</span></span>

<span data-ttu-id="5025b-146">Lync Server 2013 的歸檔原則包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="5025b-146">Lync Server 2013 Archiving policies include the following:</span></span>

  - <span data-ttu-id="5025b-147">**全域存檔原則**。</span><span class="sxs-lookup"><span data-stu-id="5025b-147">**Global Archiving policy**.</span></span> <span data-ttu-id="5025b-148">這是預設的存檔原則，且適用于整個部署。</span><span class="sxs-lookup"><span data-stu-id="5025b-148">This is the default Archiving policy and applies to your entire deployment.</span></span> <span data-ttu-id="5025b-149">它是在您部署 Lync Server 2013 時建立的，而且預設會停用內部與外部通訊的存檔。</span><span class="sxs-lookup"><span data-stu-id="5025b-149">It is created when you deploy Lync Server 2013 and, by default, disables Archiving for both internal and external communications.</span></span> <span data-ttu-id="5025b-150">您無法刪除此原則。</span><span class="sxs-lookup"><span data-stu-id="5025b-150">You cannot delete this policy.</span></span> <span data-ttu-id="5025b-151">如果您選擇 [刪除] 選項，全域原則將重設為預設設定。</span><span class="sxs-lookup"><span data-stu-id="5025b-151">If you choose the delete option, the global policy is reset to the default settings.</span></span>

  - <span data-ttu-id="5025b-152">**網站歸檔原則**。</span><span class="sxs-lookup"><span data-stu-id="5025b-152">**Site Archiving policy**.</span></span> <span data-ttu-id="5025b-153">或者，您可以建立及設定網站的網站層級歸檔原則，以啟用或停用一或多個特定網站的封存。</span><span class="sxs-lookup"><span data-stu-id="5025b-153">Optionally, you can enable or disable Archiving for one or more specific sites by creating and configuring a site-level Archiving policy for the site.</span></span> <span data-ttu-id="5025b-154">當您建立網站層級歸檔原則時，預設不會啟用封存。</span><span class="sxs-lookup"><span data-stu-id="5025b-154">When you create a site-level Archiving policy, by default, archiving is not enabled.</span></span> <span data-ttu-id="5025b-155">您可以刪除任何您建立的網站層級歸檔原則。</span><span class="sxs-lookup"><span data-stu-id="5025b-155">You can delete any site-level Archiving policy that you create.</span></span> <span data-ttu-id="5025b-156">網站層級的歸檔原則會覆寫全域原則，但只適用于原則中指定的網站。</span><span class="sxs-lookup"><span data-stu-id="5025b-156">A site-level Archiving policy overrides the global policy, but only for the site specified in the policy.</span></span> <span data-ttu-id="5025b-157">例如，如果您在全域原則中啟用內部和外部通訊的封存，並建立您在其中停用外部通訊封存的網站原則，則只有內部通訊會針對該網站進行歸檔。</span><span class="sxs-lookup"><span data-stu-id="5025b-157">For example, if you enable Archiving for internal and external communications in your global policy and create a site policy in which you disable Archiving for external communications, only internal communications would be archived for that site.</span></span>

  - <span data-ttu-id="5025b-158">**使用者歸檔原則**。</span><span class="sxs-lookup"><span data-stu-id="5025b-158">**User Archiving policy**.</span></span> <span data-ttu-id="5025b-159">或者，您也可以為特定的使用者和使用者群組建立、設定及套用使用者層級歸檔原則，以啟用或停用一或多個特定使用者和使用者群組的封存。</span><span class="sxs-lookup"><span data-stu-id="5025b-159">Optionally, you can enable or disable Archiving for one or more specific users and group of users by creating, configuring, and applying a user-level Archiving policy for the specified users and user groups.</span></span> <span data-ttu-id="5025b-160">當您建立使用者層級歸檔原則時，系統預設不會啟用封存。</span><span class="sxs-lookup"><span data-stu-id="5025b-160">When you create a user-level Archiving policy, by default, archiving is not enabled.</span></span> <span data-ttu-id="5025b-161">您可以刪除您建立的任何使用者層級歸檔原則，而且您可以變更封存原則適用的使用者和使用者組。</span><span class="sxs-lookup"><span data-stu-id="5025b-161">You can delete any user-level Archiving policy that you create, and you can change which users and group of users the Archiving policy applies to.</span></span> <span data-ttu-id="5025b-162">使用者層級的歸檔原則會覆寫全域原則和任何網站原則，但只適用于已套用原則的使用者和使用者群組。</span><span class="sxs-lookup"><span data-stu-id="5025b-162">A user-level Archiving policy overrides the global policy and any site policies, but only for the users and user groups to whom the policy is applied.</span></span> <span data-ttu-id="5025b-163">例如，如果您在全域原則中停用內部和外部通訊的封存，請建立網站層級原則，您可以在其中啟用內部和外部通訊的封存，然後建立您停用的使用者層級原則。針對外部通訊進行封存，除了針對您套用使用者層級原則的使用者之外，您還會針對所有網站使用者的外部與內部通訊歸檔通訊，只會封存內部通訊。</span><span class="sxs-lookup"><span data-stu-id="5025b-163">For example, if you disable Archiving for internal and external communications in your global policy, create a site-level policy in which you enable Archiving for internal and external communications, and then create a user-level policy in which you disable Archiving for external communications, the communications would be archived for both external and internal communications for all site users except that, for the users to whom you apply the user-level policy, only internal communications would be archived.</span></span>

<span data-ttu-id="5025b-164">如需有關如何在部署存檔時設定初始封存原則的詳細資訊，請參閱在部署檔中設定[和指派 Lync Server 2013 中的存檔原則](lync-server-2013-configuring-and-assigning-archiving-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5025b-164">For details about how to set up initial Archiving policies when you deploy Archiving, see [Configuring and assigning Archiving policies in Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="5025b-165">如需使用封存原則在部署後啟用和停用通訊的詳細資料，請參閱在作業檔中[管理 Lync Server 2013 內的內部和外部通訊](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)。</span><span class="sxs-lookup"><span data-stu-id="5025b-165">For details about using Archiving policies to enable and disable communications after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5025b-166">如果您同時執行兩個 Lync Server 2013 封存資料庫並啟用 Microsoft Exchange 整合，Exchange 2013 原則會覆寫 Lync Server 封存原則，但只適用于駐留在 Exchange 2013 且已將其信箱放在就地保留中的使用者.</span><span class="sxs-lookup"><span data-stu-id="5025b-166">If you implement both Lync Server 2013 Archiving databases and enable Microsoft Exchange integration, Exchange 2013 policies override Lync Server Archiving policies, but only for users who are homed on Exchange 2013 and have had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="5025b-167">Lync 存檔只依賴 Microsoft Exchange 就地保留原則。</span><span class="sxs-lookup"><span data-stu-id="5025b-167">Lync Archiving depends on Microsoft Exchange In-Place Hold policy only.</span></span>



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a><span data-ttu-id="5025b-168">我有哪些選項可設定存檔？</span><span class="sxs-lookup"><span data-stu-id="5025b-168">What Options Do I Have for Configuring Archiving?</span></span>

<span data-ttu-id="5025b-169">除了使用原則以及啟用及停用封存之外，您還可以針對整個部署以及特定網站和池（您也可以）設定其他的存檔選項。</span><span class="sxs-lookup"><span data-stu-id="5025b-169">In addition to using policies and to enable and disable Archiving, you have other Archiving options that can be configure for your entire deployment and, optionally, for specific sites and pools.</span></span> <span data-ttu-id="5025b-170">您可以使用一或多個存檔設定（可在 Lync Server 2013 的 [控制台] 中找到）來控制大部分的存檔選項，但也有另一個選項，只適用于使用 Lync Server 2013 管理命令介面的配置。</span><span class="sxs-lookup"><span data-stu-id="5025b-170">You control most Archiving options by using one or more Archiving configurations, which are available in Lync Server 2013 Control Panel, but also have another option that is only available for configuration using Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a><span data-ttu-id="5025b-171">在 Lync Server 2013 的 [控制台] 中提供的 [封存配置選項]</span><span class="sxs-lookup"><span data-stu-id="5025b-171">Archiving Configuration Options Available in Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="5025b-172">每個封存配置都提供下列選項：</span><span class="sxs-lookup"><span data-stu-id="5025b-172">Each archiving configuration provides the following options:</span></span>

<span data-ttu-id="5025b-173">全域層級設定是在您部署封存時自動建立，而且可以設定，但不能刪除。</span><span class="sxs-lookup"><span data-stu-id="5025b-173">The global-level configuration is created automatically when you deploy archiving and can be configured, but not deleted.</span></span> <span data-ttu-id="5025b-174">如果您選取刪除全域設定的選項，設定就會重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="5025b-174">If you select the option to delete the global configuration, the settings are reset to the default values.</span></span> <span data-ttu-id="5025b-175">您可以建立多個網站和池設定，搭配全域配置來控制存檔設定。</span><span class="sxs-lookup"><span data-stu-id="5025b-175">You can create multiple site and pool configurations that, together with the global configuration, control archiving settings.</span></span> <span data-ttu-id="5025b-176">針對全域設定以及每個網站和池配置，您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="5025b-176">For the global configuration and each site and pool configuration, you have the following options:</span></span>

  - <span data-ttu-id="5025b-177">停用 [封存]、[只針對立即訊息（IM）啟用封存]，或啟用 IM 與會議的存檔。</span><span class="sxs-lookup"><span data-stu-id="5025b-177">Disable archiving, enable archiving only for instant messaging (IM), or enable archiving of both IM and conferencing.</span></span>

  - <span data-ttu-id="5025b-178">設定在 Lync 伺服器失敗時封鎖 IM 和會議會話的 [關鍵模式]。</span><span class="sxs-lookup"><span data-stu-id="5025b-178">Configure critical mode to block IM and conferencing sessions in the event of a Lync Server failure.</span></span> <span data-ttu-id="5025b-179">失敗包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="5025b-179">Failures include the following:</span></span>
    
      - <span data-ttu-id="5025b-180">**即時消息**。</span><span class="sxs-lookup"><span data-stu-id="5025b-180">**IM**.</span></span> <span data-ttu-id="5025b-181">Lync Server storage service 發生問題。</span><span class="sxs-lookup"><span data-stu-id="5025b-181">A problem with the Lync Server storage service.</span></span> <span data-ttu-id="5025b-182">在此情況下，具有封存能力的使用者皆無法使用 IM。</span><span class="sxs-lookup"><span data-stu-id="5025b-182">In this case, IM is blocked for users who are enabled for Archiving.</span></span>
    
      - <span data-ttu-id="5025b-183">**會議**。</span><span class="sxs-lookup"><span data-stu-id="5025b-183">**Conferencing**.</span></span> <span data-ttu-id="5025b-184">失敗原因可能是無法使用檔案共用，或存放服務發生問題。</span><span class="sxs-lookup"><span data-stu-id="5025b-184">A failure could be an unavailable file share or a problem with the storage service.</span></span> <span data-ttu-id="5025b-185">在此情況下，所有於失敗時間在集區中進行的會議，都會切換為限制模式，而且無法啟動新的會議。</span><span class="sxs-lookup"><span data-stu-id="5025b-185">In this case, all active conferences hosted in the pool at the time of failure are switched to restricted mode and new conferences cannot be activated.</span></span>
    
    <span data-ttu-id="5025b-186">IM 和會議會在更正失敗之後自動復原。</span><span class="sxs-lookup"><span data-stu-id="5025b-186">Both IM and conferencing automatically recover after the failures are corrected.</span></span>

  - <span data-ttu-id="5025b-187">指定使用 Microsoft Exchange Server 2013 整合，以使用 Exchange 2013 儲存已歸檔的資料，而不是設定個別的 SQL Server 資料庫來儲存 Lync Server 2013 封存資料。</span><span class="sxs-lookup"><span data-stu-id="5025b-187">Specify the use of Microsoft Exchange Server 2013 integration to use Exchange 2013 for storage of archived data, instead of setting up separate SQL Server databases for storage of Lync Server 2013 archiving data.</span></span>

  - <span data-ttu-id="5025b-188">針對存檔資料設定清除選項。</span><span class="sxs-lookup"><span data-stu-id="5025b-188">Configure purging options for archived data.</span></span> <span data-ttu-id="5025b-189">這包括指定何時清除封存的資料，這可能是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="5025b-189">This includes specifying when to purge archived data, which can be either of the following:</span></span>
    
      - <span data-ttu-id="5025b-190">在您指定的天數之後</span><span class="sxs-lookup"><span data-stu-id="5025b-190">After a specific number of days that you specify</span></span>
    
      - <span data-ttu-id="5025b-191">匯出資料之後（包括已上傳至 Exchange 的資料），如果您啟用 Microsoft Exchange 整合，就會出現這種情況。</span><span class="sxs-lookup"><span data-stu-id="5025b-191">After the archiving data has been exported (which includes data that has been uploaded to Exchange, if you enable Microsoft Exchange integration).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5025b-192">如果您啟用 Microsoft Exchange 整合，請清除駐留在 Exchange 2013 的使用者，並將其信箱放在就地保留中，由 Exchange 控制。</span><span class="sxs-lookup"><span data-stu-id="5025b-192">If you enable Microsoft Exchange integration, purging for users homed on Exchange 2013 and with their mailboxes put on In-Place Hold is controlled by Exchange.</span></span> <span data-ttu-id="5025b-193">唯一的認證是儲存在 Lync Server 檔案共用的會議檔案。</span><span class="sxs-lookup"><span data-stu-id="5025b-193">The only qualification is for conferencing files, which are stored on the Lync Server file share.</span></span> <span data-ttu-id="5025b-194">這類檔案會在匯出 (上傳至 Exchange) 之後 (選取匯出封存資料之後才清除資料的選項時)，或是達到指定天數上限之後 (指定保留天數上限時) 才從檔案共用中清除。</span><span class="sxs-lookup"><span data-stu-id="5025b-194">These files are purged from the file share only after the files have been exported (uploaded to Exchange), if you select the option to purge data after the archiving data has been exported, or after the specified maximum number of days, if you specify a maximum number of days for retention.</span></span>

    
    </div>

<span data-ttu-id="5025b-195">根據預設，不會啟用任何存檔選項。</span><span class="sxs-lookup"><span data-stu-id="5025b-195">By default, no archiving options are enabled.</span></span> <span data-ttu-id="5025b-196">您可以使用 Lync Server 2013 [控制台] 管理封存配置。</span><span class="sxs-lookup"><span data-stu-id="5025b-196">You can manage Archiving configurations using Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="5025b-197">您可以指定下列存檔設定：</span><span class="sxs-lookup"><span data-stu-id="5025b-197">You can specify the following Archiving configurations:</span></span>

  - <span data-ttu-id="5025b-198">**全域存檔**設定。</span><span class="sxs-lookup"><span data-stu-id="5025b-198">**Global Archiving configuration**.</span></span> <span data-ttu-id="5025b-199">這是預設的存檔設定，且適用于整個部署。</span><span class="sxs-lookup"><span data-stu-id="5025b-199">This is the default Archiving configuration and applies to your entire deployment.</span></span> <span data-ttu-id="5025b-200">它是在您部署 Lync Server 2013 時建立，而且預設不會啟用 [封存] 功能。</span><span class="sxs-lookup"><span data-stu-id="5025b-200">It is created when you deploy Lync Server 2013 and, by default, does not enable archiving functionality.</span></span> <span data-ttu-id="5025b-201">您可以修改全域設定，但無法將其刪除。</span><span class="sxs-lookup"><span data-stu-id="5025b-201">You can modify the global configuration, but you cannot delete it.</span></span> <span data-ttu-id="5025b-202">如果您選擇設定的 [刪除] 選項，全域設定就會重設為預設設定。</span><span class="sxs-lookup"><span data-stu-id="5025b-202">If you choose the delete option for the configuration, the global configuration is reset to the default settings.</span></span>

  - <span data-ttu-id="5025b-203">**網站封存配置**。</span><span class="sxs-lookup"><span data-stu-id="5025b-203">**Site Archiving configuration**.</span></span> <span data-ttu-id="5025b-204">或者，您也可以透過建立及設定個別網站的網站層級封存設定，來設定一或多個特定網站的存檔。</span><span class="sxs-lookup"><span data-stu-id="5025b-204">Optionally, you can configure Archiving for one or more specific sites by creating and configuring a site-level Archiving configuration for an individual site.</span></span> <span data-ttu-id="5025b-205">網站層級的歸檔設定只有在您建立時才存在。</span><span class="sxs-lookup"><span data-stu-id="5025b-205">A site-level Archiving configuration exists only if you create it.</span></span> <span data-ttu-id="5025b-206">您可以修改或刪除任何網站層級的存檔設定。</span><span class="sxs-lookup"><span data-stu-id="5025b-206">You can modify or delete any site-level Archiving configuration.</span></span> <span data-ttu-id="5025b-207">網站層級的存檔設定會覆寫全域設定，但僅適用于網站層級設定中指定的網站。</span><span class="sxs-lookup"><span data-stu-id="5025b-207">A site-level Archiving configuration overrides the global configuration, but only for the site specified in the site-level configuration.</span></span> <span data-ttu-id="5025b-208">例如，如果您只針對全域設定中的 IM 啟用 [封存]，並建立可讓 IM 與會議同時啟用存檔的網站設定，會議將只會封存給該網站，而不是貴組織的其餘部分。</span><span class="sxs-lookup"><span data-stu-id="5025b-208">For example, if you enable Archiving for only IM in your global configuration and create a site configuration in which you enable Archiving for both IM and conferencing, conferencing would only be archived for the site, not for the remainder of your organization.</span></span>

  - <span data-ttu-id="5025b-209">**池存檔**設定。</span><span class="sxs-lookup"><span data-stu-id="5025b-209">**Pool Archiving configuration**.</span></span> <span data-ttu-id="5025b-210">或者，您也可以為個別的 [池] 建立和設定池層級設定，以指定一或多個特定資源池的存檔設定。</span><span class="sxs-lookup"><span data-stu-id="5025b-210">Optionally, you can specify Archiving settings for one or more specific pools by creating and configuring a pool-level configuration for the individual pool.</span></span> <span data-ttu-id="5025b-211">池層級的歸檔設定只有在您建立時才存在。</span><span class="sxs-lookup"><span data-stu-id="5025b-211">A pool-level Archiving configuration exists only if you create it.</span></span> <span data-ttu-id="5025b-212">您可以修改並刪除任何池層級的存檔設定。</span><span class="sxs-lookup"><span data-stu-id="5025b-212">You can modify and delete any pool-level Archiving configuration.</span></span> <span data-ttu-id="5025b-213">池層級的存檔設定會覆寫全域設定和您可能已建立的任何網站封存設定。</span><span class="sxs-lookup"><span data-stu-id="5025b-213">A pool-level Archiving configuration overrides the global configuration and any site archiving configuration you may have created.</span></span> <span data-ttu-id="5025b-214">例如，如果您只針對全域設定中的 IM 啟用 [封存]，請建立網站層級設定，讓您為網站的 IM 和會議啟用封存，然後建立一層級設定，讓您只在其中啟用存檔IM，對於網站的所有使用者，除了駐留在池層級設定中指定的池中的使用者之外，還會針對該網站的所有使用者封存 IM 和會議的通訊。</span><span class="sxs-lookup"><span data-stu-id="5025b-214">For example, if you enable Archiving for only IM in your global configuration, create a site-level configuration in which you enable Archiving for both IM and conferencing for the site, and then create a pool-level configuration in which you enable Archiving only for IM, the communications would be archived for both IM and conferencing for all users of the site except the users homed in the pool specified in the pool-level configuration.</span></span> <span data-ttu-id="5025b-215">針對貴組織中的所有其他使用者，只會針對 IM 啟用封存功能。</span><span class="sxs-lookup"><span data-stu-id="5025b-215">For all other users in your organization, Archiving would be enabled only for IM.</span></span>

<span data-ttu-id="5025b-216">如需如何在部署存檔時設定初始封存配置的詳細資料，請參閱在部署檔中的[Lync Server 2013](lync-server-2013-configuring-archiving-options.md)中的 [設定封存選項]。</span><span class="sxs-lookup"><span data-stu-id="5025b-216">For details about how to set up initial Archiving configurations when you deploy Archiving, see [Configuring Archiving options in Lync Server 2013](lync-server-2013-configuring-archiving-options.md) in the Deployment documentation.</span></span> <span data-ttu-id="5025b-217">如需在部署後使用封存原則啟用和停用通訊的詳細資料，請參閱在作業檔中[針對貴組織、網站和池管理 Lync Server 2013 中的 [存檔](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)設定] 選項。</span><span class="sxs-lookup"><span data-stu-id="5025b-217">For details about using Archiving policies to enable and disable communications after deployment, see [Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) in the Operations documentation.</span></span>

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a><span data-ttu-id="5025b-218">只能在 Windows PowerShell 中使用封存選項</span><span class="sxs-lookup"><span data-stu-id="5025b-218">Archiving Options Available Only in Windows PowerShell</span></span>

<span data-ttu-id="5025b-219">使用 Lync Server 2013 管理命令介面，您可以使用 Cmdlet 來實現 Lync Server 2013 [控制台] 中不提供的選項。</span><span class="sxs-lookup"><span data-stu-id="5025b-219">Using Lync Server 2013 Management Shell, you can use cmdlets to implement options that are not available in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="5025b-220">這些選項包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="5025b-220">These options include the following:</span></span>

  - <span data-ttu-id="5025b-221">封存**重複的郵件**。</span><span class="sxs-lookup"><span data-stu-id="5025b-221">**Archive duplicate messages**.</span></span> <span data-ttu-id="5025b-222">如需詳細資訊，請參閱作業檔中的[新 CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration)和[CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) 。</span><span class="sxs-lookup"><span data-stu-id="5025b-222">For details, see [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) and [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) in the Operations documentation.</span></span>

  - <span data-ttu-id="5025b-223">**匯出**封存的資料。</span><span class="sxs-lookup"><span data-stu-id="5025b-223">**Export archived data**.</span></span> <span data-ttu-id="5025b-224">如需詳細資訊，請參閱[Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)</span><span class="sxs-lookup"><span data-stu-id="5025b-224">For details, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)</span></span>

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a><span data-ttu-id="5025b-225">如何存取已歸檔的資料？</span><span class="sxs-lookup"><span data-stu-id="5025b-225">How Do I Access Archived Data?</span></span>

<span data-ttu-id="5025b-226">歸檔資料的存取權視資料的儲存位置而定：</span><span class="sxs-lookup"><span data-stu-id="5025b-226">Access to archived data is dependent on where the data is stored:</span></span>

  - <span data-ttu-id="5025b-227">**Microsoft Exchange 儲存空間**。</span><span class="sxs-lookup"><span data-stu-id="5025b-227">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="5025b-228">如果您選擇 [Exchange 整合] 選項，Lync Server 會在 Exchange 2013 存放區中針對所有託管于 Exchange 2013 的使用者，以及將其信箱放在就地保留中的使用者，將其存檔。</span><span class="sxs-lookup"><span data-stu-id="5025b-228">If you choose the Exchange integration option, Lync Server deposits the archiving content in the Exchange 2013 store for all users who are homed on Exchange 2013, and who have had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="5025b-229">已歸檔的資料會儲存在使用者信箱可復原的專案資料夾中，對於使用者通常是不可見的，而且只有擁有 Exchange**探索管理**角色的使用者才能進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="5025b-229">Archived data is stored in user mailboxes Recoverable items folder, which is generally invisible to users, and can only be searched by users with an Exchange **Discovery Management** role.</span></span> <span data-ttu-id="5025b-230">Exchange 可在已部署的情況下，與 SharePoint 一起啟用同盟搜尋與探索。</span><span class="sxs-lookup"><span data-stu-id="5025b-230">Exchange enables federated search and discovery, along with SharePoint, if it is deployed.</span></span> <span data-ttu-id="5025b-231">如需有關儲存在 Exchange 中之資料的儲存、保留和探索的詳細資訊，請參閱 Exchange 2013 和 SharePoint 檔。</span><span class="sxs-lookup"><span data-stu-id="5025b-231">For more details about storage, retention, and discovery of data stored in Exchange, see the Exchange 2013 and SharePoint documentation.</span></span>

  - <span data-ttu-id="5025b-232">**Lync Server 儲存空間**。</span><span class="sxs-lookup"><span data-stu-id="5025b-232">**Lync Server storage**.</span></span> <span data-ttu-id="5025b-233">如果您設定 Lync Server 2013 封存資料庫以儲存 Lync Server 資料，Lync Server 會將存檔內容放在 Lync Server 封存資料庫（SQL Server 資料庫）中，以供未駐留在 Exchange 2013 的任何使用者使用，而且未將其信箱放在就地保留。</span><span class="sxs-lookup"><span data-stu-id="5025b-233">If you set up Lync Server 2013 Archiving databases for storage of Lync Server data, Lync Server deposits archiving content in the Lync Server Archiving databases (SQL Server databases) for any users not homed on Exchange 2013, and who have not had their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="5025b-234">此資料是無法搜尋的，但可將其匯出為可使用其他工具搜尋的格式。</span><span class="sxs-lookup"><span data-stu-id="5025b-234">This data is not searchable, but it can be exported to formats that are searchable using other tools.</span></span> <span data-ttu-id="5025b-235">如需有關匯出儲存在歸檔資料庫中之資料的詳細資訊，請參閱在作業檔中[匯出 Lync Server 2013 的存檔資料](lync-server-2013-exporting-archived-data.md)。</span><span class="sxs-lookup"><span data-stu-id="5025b-235">For details about exporting data stored in Archiving databases, see [Exporting archived data from Lync Server 2013](lync-server-2013-exporting-archived-data.md) in the Operations documentation.</span></span>

<span data-ttu-id="5025b-236">如需有關 Lync Server 2013 與 Exchange 2013 共同運作方式的詳細資訊，請參閱可支援性檔中的[Lync server 2013 中的 Exchange Server 和 SharePoint 整合支援](lync-server-2013-exchange-and-sharepoint-integration-support.md)。</span><span class="sxs-lookup"><span data-stu-id="5025b-236">For more details about how Lync Server 2013 and Exchange 2013 work together, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

