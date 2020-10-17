---
title: Lync Server 2013：設定大型會議的支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up support for large meetings
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48184763
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e7d7796a879398d5f73ebfc67cc6cc6a68b5b1c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497580"
---
# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="48b65-102">在 Lync Server 2013 中設定大型會議的支援</span><span class="sxs-lookup"><span data-stu-id="48b65-102">Setting up support for large meetings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48b65-103">_**主題上次修改日期：** 2014-05-12_</span><span class="sxs-lookup"><span data-stu-id="48b65-103">_**Topic Last Modified:** 2014-05-12_</span></span>

<span data-ttu-id="48b65-104">支援最多1000使用者的大型會議，需要建立適當的拓撲、會議硬體和軟體必要條件，並適當地設定環境。</span><span class="sxs-lookup"><span data-stu-id="48b65-104">Supporting large meetings of up to 1000 users requires creating an appropriate topology, meeting hardware and software prerequisites, and configuring the environment appropriately.</span></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="48b65-105">拓撲需求</span><span class="sxs-lookup"><span data-stu-id="48b65-105">Topology Requirements</span></span>

<span data-ttu-id="48b65-106">單一大型會議需要至少一部前端伺服器和一部後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="48b65-106">A single large meeting requires at least one Front End Server and one Back End Server.</span></span> <span data-ttu-id="48b65-107">不過，為了提供高可用性，我們建議使用兩部前端伺服器集區和鏡像後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="48b65-107">However, to provide high availability, we recommend a two Front End Server pool with mirrored Back End Servers.</span></span>

<span data-ttu-id="48b65-108">主控大型會議的使用者必須擁有位於此集區中的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="48b65-108">The user who hosts the large meetings must have their user account homed in this pool.</span></span> <span data-ttu-id="48b65-109">不過，我們不建議您在此集區中主控其他使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="48b65-109">However, we do not recommend that you host other user accounts in this pool.</span></span> <span data-ttu-id="48b65-110">而只是用於大型會議。</span><span class="sxs-lookup"><span data-stu-id="48b65-110">Instead, use it only for the large meetings.</span></span> <span data-ttu-id="48b65-111">最佳作法是在此集區中建立特殊的使用者帳戶，僅供主控大型會議使用。</span><span class="sxs-lookup"><span data-stu-id="48b65-111">The best practice is to create a special user account in this pool to be used only to host large meetings.</span></span> <span data-ttu-id="48b65-112">因為大型會議設定已經針對效能進行優化，所以以一般使用者的身分使用它時，可能會發生問題，例如，當涉及 PSTN 端點時，無法將 P2P 會話提升為會議。</span><span class="sxs-lookup"><span data-stu-id="48b65-112">Since the large meeting setting is optimized for performance, using it as a normal user could have problems such as the inability to promote a P2P session to a meeting when a PSTN endpoint is involved.</span></span>

<span data-ttu-id="48b65-113">若要管理恰好兩部前端伺服器的集區，需要一些特殊的考慮。</span><span class="sxs-lookup"><span data-stu-id="48b65-113">Managing a pool with exactly two Front End Servers requires some special considerations.</span></span> <span data-ttu-id="48b65-114">如需詳細資訊，請參閱 [Lync Server 2013 中的前端伺服器、立即訊息及顯示狀態的拓撲和元件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="48b65-114">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

<span data-ttu-id="48b65-115">此外，如果您想要選擇性地為大型會議所用的集區提供嚴重損壞修復備份和容錯移轉，您可以將它與不同資料中心的專用集區配對。</span><span class="sxs-lookup"><span data-stu-id="48b65-115">Additionally, if you want to optionally provide disaster recovery backup and failover for the pool used for large meetings, you can pair it with a similarly set up dedicated pool in a different data center.</span></span> <span data-ttu-id="48b65-116">如需詳細資訊，請參閱 [在 Lync Server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="48b65-116">For details, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<span data-ttu-id="48b65-117">![大型會議集區設定](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "大型會議集區設定")</span><span class="sxs-lookup"><span data-stu-id="48b65-117">![Large Meetings pool configuration](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Large Meetings pool configuration")</span></span>

<span data-ttu-id="48b65-118">拓撲的其他注意事項包括：</span><span class="sxs-lookup"><span data-stu-id="48b65-118">Additional notes about the topology include:</span></span>

  - <span data-ttu-id="48b65-119">需要有檔案共用，才能儲存會議內容，以及在部署及啟用封存伺服器時儲存封存檔。</span><span class="sxs-lookup"><span data-stu-id="48b65-119">A file share is required for storing meeting content and, if Archiving Server is deployed and enabled, for storing the archiving files.</span></span> <span data-ttu-id="48b65-120">檔案共用可以專用於集區，也可以是部署集區之網站上其他集區所使用的相同檔案共用。</span><span class="sxs-lookup"><span data-stu-id="48b65-120">The file share can be dedicated to the pool or can be the same file share used by another pool at the site in which the pool is deployed.</span></span> <span data-ttu-id="48b65-121">如需設定檔案共用的詳細資訊，請參閱 [Configure file storage For Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md)。</span><span class="sxs-lookup"><span data-stu-id="48b65-121">For details about configuring the file share, see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>

  - <span data-ttu-id="48b65-122">若要在大型會議中啟用 PowerPoint 簡報功能，必須使用 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="48b65-122">A Office Web Apps Server is required for enabling the PowerPoint presentation functionality in large meetings.</span></span> <span data-ttu-id="48b65-123">Office Web Apps Server 可以專用於大型會議集區，也可以是部署專用集區之網站上其他集區所使用的 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="48b65-123">The Office Web Apps Server can be dedicated to the large meeting pool or, it can be the same Office Web Apps Server used by other pools at the site in which the dedicated pool is deployed.</span></span>

  - <span data-ttu-id="48b65-124">前端伺服器的負載平衡需要對 HTTP 流量 (例如「會議內容下載) 」的硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="48b65-124">Load balancing of the Front End Servers requires hardware load balancing for the HTTP traffic (such as meeting content download).</span></span> <span data-ttu-id="48b65-125">建議使用 DNS 負載平衡進行 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="48b65-125">DNS load balancing is recommended for SIP traffic.</span></span> <span data-ttu-id="48b65-126">如需詳細資訊，請參閱 [Lync Server 2013 的負載平衡需求](lync-server-2013-load-balancing-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="48b65-126">For details see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="48b65-127">如果您想要對專用大型會議集區使用監控伺服器，我們建議您使用在 Lync Server 部署中所有前端伺服器集區中共用的監控伺服器及其資料庫。</span><span class="sxs-lookup"><span data-stu-id="48b65-127">If you want to use Monitoring Server for the dedicated large-meeting pool, we recommend using the Monitoring Server and its database that are shared across all of the Front End Server pools in your Lync Server deployment.</span></span>

</div>

<div>

## <a name="hardware-and-software-requirements"></a><span data-ttu-id="48b65-128">軟硬體需求</span><span class="sxs-lookup"><span data-stu-id="48b65-128">Hardware and Software Requirements</span></span>

<span data-ttu-id="48b65-129">專用大型會議集區中之伺服器的硬體需求與其他 Lync Server 2013 伺服器的硬體需求相同。</span><span class="sxs-lookup"><span data-stu-id="48b65-129">The hardware requirements for servers in a dedicated large-meeting pool are the same as for your other Lync Server 2013 servers.</span></span> <span data-ttu-id="48b65-130">如需硬體需求的詳細資訊，請參閱「[Lync server 2013 的伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)」。</span><span class="sxs-lookup"><span data-stu-id="48b65-130">For details about hardware requirements, see "[Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="48b65-131">專用大型會議集區中的伺服器必須符合所有的 Lync Server 2013 軟體需求。</span><span class="sxs-lookup"><span data-stu-id="48b65-131">Servers in a dedicated large-meeting pool must meet all Lync Server 2013 software requirements.</span></span> <span data-ttu-id="48b65-132">如需軟體需求的詳細資訊，請參閱下列檔：</span><span class="sxs-lookup"><span data-stu-id="48b65-132">For details about software requirements, please see the following documentation:</span></span>

  - [<span data-ttu-id="48b65-133">Lync Server 2013 中的伺服器和工具作業系統支援</span><span class="sxs-lookup"><span data-stu-id="48b65-133">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="48b65-134">Lync Server 2013 中的資料庫軟體支援</span><span class="sxs-lookup"><span data-stu-id="48b65-134">Database software support in Lync Server 2013</span></span>](lync-server-2013-database-software-support.md)

  - [<span data-ttu-id="48b65-135">Lync Server 2013 的其他軟體需求</span><span class="sxs-lookup"><span data-stu-id="48b65-135">Additional software requirements for Lync Server 2013</span></span>](lync-server-2013-additional-software-requirements.md)

<span data-ttu-id="48b65-136">此外，Lync Server 2013 和所有 Lync Server 2013 用戶端都必須具有最新的更新。</span><span class="sxs-lookup"><span data-stu-id="48b65-136">Additionally, both Lync Server 2013 and all Lync Server 2013 clients must have the latest updates.</span></span>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="48b65-137">設定需求</span><span class="sxs-lookup"><span data-stu-id="48b65-137">Configuration Requirements</span></span>

<span data-ttu-id="48b65-138">建議您專門為大型會議建立新的會議原則，然後將會議原則指派給位於專屬大型會議集區的使用者。</span><span class="sxs-lookup"><span data-stu-id="48b65-138">We recommend creating a new conferencing policy specifically for large meetings, and then assigning the conferencing policy to the users who are homed on the dedicated large-meeting pool.</span></span> <span data-ttu-id="48b65-139">使用下列設定來設定會議原則：</span><span class="sxs-lookup"><span data-stu-id="48b65-139">Configure the conferencing policy using the following settings:</span></span>

  - <span data-ttu-id="48b65-140">將 **MaxMeetingSize** 選項設定為 **1000**。</span><span class="sxs-lookup"><span data-stu-id="48b65-140">Set the **MaxMeetingSize** option to **1000**.</span></span> <span data-ttu-id="48b65-141"> (預設值為 **250**。 ) </span><span class="sxs-lookup"><span data-stu-id="48b65-141">(The default is **250**.)</span></span>

  - <span data-ttu-id="48b65-142">將 **AllowLargeMeetings** 選項設定為 **True**。</span><span class="sxs-lookup"><span data-stu-id="48b65-142">Set the **AllowLargeMeetings** option to **True**.</span></span>

  - <span data-ttu-id="48b65-143">將 **EnableAppDesktopSharing** 選項設定為 [ **無**]。</span><span class="sxs-lookup"><span data-stu-id="48b65-143">Set the **EnableAppDesktopSharing** option to **None**.</span></span>

  - <span data-ttu-id="48b65-144">將 **AllowUserToScheduleMeetingsWithAppSharing** 選項設定為 **False**。</span><span class="sxs-lookup"><span data-stu-id="48b65-144">Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.</span></span>

  - <span data-ttu-id="48b65-145">將 **AllowSharedNotes** 選項設定為 **False**。</span><span class="sxs-lookup"><span data-stu-id="48b65-145">Set the **AllowSharedNotes** option to **False**.</span></span>

  - <span data-ttu-id="48b65-146">將 **AllowAnnotations** 選項設定為 **False**。</span><span class="sxs-lookup"><span data-stu-id="48b65-146">Set the **AllowAnnotations** option to **False**.</span></span>

  - <span data-ttu-id="48b65-147">將 **DisablePowerPointAnnotations** 選項設定為 **True**。</span><span class="sxs-lookup"><span data-stu-id="48b65-147">Set the **DisablePowerPointAnnotations** option to **True**.</span></span>

  - <span data-ttu-id="48b65-148">將 **AllowMultiview** 選項設定為 **False**。</span><span class="sxs-lookup"><span data-stu-id="48b65-148">Set the **AllowMultiview** option to **False**.</span></span>

  - <span data-ttu-id="48b65-149">將 **EnableMultiviewJoin** 選項設定為 **False**。</span><span class="sxs-lookup"><span data-stu-id="48b65-149">Set the **EnableMultiviewJoin** option to **False**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="48b65-150">在 Lync Server 2013 中對1000使用者大型會議的支援，需要將會議排程器的會議原則中的 [ <STRONG>AllowLargeMeetings</STRONG> ] 設定設為 true。</span><span class="sxs-lookup"><span data-stu-id="48b65-150">The support for 1000 user large meetings in Lync Server 2013 requires the <STRONG>AllowLargeMeetings</STRONG> setting in the conferencing policy for the meeting scheduler to be set to true.</span></span> <span data-ttu-id="48b65-151">當此設定設為 true 時，當使用者加入這類會議時，Lync 體驗會針對額外的大型會議進行優化。</span><span class="sxs-lookup"><span data-stu-id="48b65-151">When this setting is set to true, the Lync experience will be optimized for extra large meetings when users joins such meeting.</span></span> <span data-ttu-id="48b65-152">特別是在大型會議中，Lync 不會顯示完整會議參與者清單的初始或更新，也就是用戶端和 Lync Server 2013 的性能瓶頸。</span><span class="sxs-lookup"><span data-stu-id="48b65-152">Specifically, in a large meeting, Lync will not show the initial or update of the full meeting participant list, which is a performance bottleneck for both the client and Lync Server 2013.</span></span> <span data-ttu-id="48b65-153">相反地，Lync 只會顯示使用者的相關資訊和會議的簡報者清單。</span><span class="sxs-lookup"><span data-stu-id="48b65-153">Instead, Lync will only show information about the user and the list of presenters of the meeting.</span></span> <span data-ttu-id="48b65-154">Lync 仍會正確顯示大型會議中可用的參與者總數。</span><span class="sxs-lookup"><span data-stu-id="48b65-154">Lync will still properly shows total number of participants available in the large meetings.</span></span>



</div>

<span data-ttu-id="48b65-155">除了 [ **最大會議大小** ] 設定之外，您還需要在這裡指定的所有其他會議原則設定，才能停用大型會議中不需要的會議功能。</span><span class="sxs-lookup"><span data-stu-id="48b65-155">Except for the **Maximum meeting size** setting, all the other conferencing policy settings specified here are required in order to disable conferencing capabilities that are not necessary in large meetings.</span></span>

<span data-ttu-id="48b65-156">此外，您必須設定專門的大型會議集區，使位於集區中的每個 Lync Server 2013 使用者都擁有適當的許可權。</span><span class="sxs-lookup"><span data-stu-id="48b65-156">Additionally, you need to configure the dedicated large-meeting pool so that each Lync Server 2013 user that is homed on the pool and responsible for managing the meeting schedule has the appropriate permissions.</span></span> <span data-ttu-id="48b65-157">若要這麼做，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="48b65-157">To do this, do the following:</span></span>

  - <span data-ttu-id="48b65-158">將 [ **指定為簡報者** ] 選項設定為 [ **無**]。</span><span class="sxs-lookup"><span data-stu-id="48b65-158">Set the **Designate as presenter** option to **None**.</span></span> <span data-ttu-id="48b65-159">通常，一或多個大型會議參與者的使用者都是簡報者，所以不應該以簡報者的身分，將參與者自動承認為大型會議。</span><span class="sxs-lookup"><span data-stu-id="48b65-159">Typically, one or just a few users of all the participants of a large meeting are presenters, so participants should not be automatically admitted to large meetings as presenters.</span></span> <span data-ttu-id="48b65-160">相反地，簡報者應明確指派會議排程時間，或是在大型會議期間明確升級。</span><span class="sxs-lookup"><span data-stu-id="48b65-160">Instead, the presenters should be explicitly designated at meeting scheduling time, or be explicitly promoted during the large meeting.</span></span>

  - <span data-ttu-id="48b65-161">請確定未選取 [ **依預設指派指派會議類型** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="48b65-161">Make sure that the **Assigned conference type by default** check box is not selected.</span></span> <span data-ttu-id="48b65-162">此設定可控制 Lync 2013 的線上會議增益集是否一定要使用召集人指派的會議來排程會議，這表示已排程的會議具有相同的加入 URL 和音訊資訊。</span><span class="sxs-lookup"><span data-stu-id="48b65-162">This setting controls whether the Online Meeting Add-in for Lync 2013 always schedules conferences using the organizer’s assigned conference, which means that scheduled meetings have the same join URL and audio information.</span></span> <span data-ttu-id="48b65-163">在小型群組共同作業案例中，有這種指派的會議類型可順利運作，因為每個人都有自己的指派會議，而常數加入 URL 和音訊資訊可協助協助加入更快速的會議。</span><span class="sxs-lookup"><span data-stu-id="48b65-163">In small group collaboration scenarios, having such assigned conference type works well because everyone has their own individual assigned conference, and the constant join URL and audio information helps to facilitate faster meeting joining.</span></span> <span data-ttu-id="48b65-164">不過，在大型會議案例中，大型會議支援人員會使用一組使用者認證來安排大型會議，然後為會議申請者提供加入 URLs 和音訊資訊。</span><span class="sxs-lookup"><span data-stu-id="48b65-164">However, in the large-meeting scenario, the large meeting support staff schedules the large meetings using a single set of user credentials, and then provides join URLs and audio information to the meeting requesters.</span></span> <span data-ttu-id="48b65-165">在此情況下，使用不同的 URL 來加入每個會議可更好地運作。</span><span class="sxs-lookup"><span data-stu-id="48b65-165">In this case, using a different URL to join each meeting works better.</span></span>

  - <span data-ttu-id="48b65-166">除非有必要，否則請確定未選取 [ **預設會承認匿名使用者** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="48b65-166">Ensure that the **Admit anonymous users by default** check box is not selected, unless it is required.</span></span> <span data-ttu-id="48b65-167">在未使用指派的會議時，此設定會影響 Lync 2013 之線上會議增益集排程的預設會議存取類型。</span><span class="sxs-lookup"><span data-stu-id="48b65-167">This setting affects the default meeting access type scheduled by the Online Meeting Add-in for Lync 2013 when not using an assigned conference.</span></span> <span data-ttu-id="48b65-168">此設定的適當選項取決於組織的需求。</span><span class="sxs-lookup"><span data-stu-id="48b65-168">The appropriate option for this setting depends on your organization’s needs.</span></span> <span data-ttu-id="48b65-169">如果貴組織大多數的大型會議為內部會議，請勿選取此選項。</span><span class="sxs-lookup"><span data-stu-id="48b65-169">If most large meetings for your organization are internal meetings, do not select this option.</span></span> <span data-ttu-id="48b65-170">如果大多數大型會議都要求外部使用者可以加入，請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="48b65-170">If most large meetings require that external users be able to join, select this option.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

