---
title: Lync Server 2013： 定義 Persistent Chat Server 的需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e6d796f3d06a9749cdccc86f59271a739eaa7e4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="29295-102">定義 Lync Server 2013 中的 [for Persistent Chat Server 貴組織的需求</span><span class="sxs-lookup"><span data-stu-id="29295-102">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29295-103">_**上次修改主題：** 2014年-01-15_</span><span class="sxs-lookup"><span data-stu-id="29295-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="29295-104">為貴組織部署常設聊天室伺服器之前，請務必考量下列關鍵問題以最佳化您的部署：</span><span class="sxs-lookup"><span data-stu-id="29295-104">Before you deploy Persistent Chat Server for your organization, it’s essential to consider the following key questions to optimize your deployment:</span></span>

  - <span data-ttu-id="29295-105">誰應 for Persistent Chat Server 啟用 （使用者設定檔）？</span><span class="sxs-lookup"><span data-stu-id="29295-105">Who (user profile) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="29295-106">Persistent Chat Server 會啟用可以設定全域、 網站、 集區或使用者層級的原則。</span><span class="sxs-lookup"><span data-stu-id="29295-106">Persistent Chat Server is enabled by a policy that can be set at a Global, Site, Pool or User level.</span></span>

  - <span data-ttu-id="29295-107">使用者人數 （擴充） 應啟用 for Persistent Chat Server？</span><span class="sxs-lookup"><span data-stu-id="29295-107">How many users (scale) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="29295-108">Persistent Chat Server 支援 150000 佈建的使用者 （由原則啟用），並使用 Persistent Chat Server 80000 位並行使用者的最大值。</span><span class="sxs-lookup"><span data-stu-id="29295-108">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users using Persistent Chat Server.</span></span> <span data-ttu-id="29295-109">在單一的常設聊天室伺服器可支援 20000 已連線的使用者，並在單一常設聊天室伺服器集區可以有最多總共為 80000 位同時連線的使用者 4 作用中的伺服器。</span><span class="sxs-lookup"><span data-stu-id="29295-109">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>

  - <span data-ttu-id="29295-110">會從舊版的群組聊天伺服器，您移轉或第一次 deploying Persistent Chat Server？</span><span class="sxs-lookup"><span data-stu-id="29295-110">Are you migrating from a previous version of Group Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>

  - <span data-ttu-id="29295-111">是否有規範需求？</span><span class="sxs-lookup"><span data-stu-id="29295-111">Are there compliance requirements?</span></span> <span data-ttu-id="29295-112">Persistent Chat Server 支援合規性。</span><span class="sxs-lookup"><span data-stu-id="29295-112">Persistent Chat Server supports compliance.</span></span> <span data-ttu-id="29295-113">規範服務會執行組合常設聊天室伺服器前端伺服器上，而不是在不同的電腦上一個 Group Chat 伺服器部署中的需求。</span><span class="sxs-lookup"><span data-stu-id="29295-113">The compliance service runs collocated on the Persistent Chat Server Front End Server, as opposed to the requirement for a separate computer in previous Group Chat Server deployments.</span></span> <span data-ttu-id="29295-114">規範是選用的，如果選擇，就需要有規範資料庫，且必須將該資料庫設定為儲存規範資料和事件。</span><span class="sxs-lookup"><span data-stu-id="29295-114">Compliance is optional, and if chosen, requires a compliance database that must be configured to store compliance data and events.</span></span> <span data-ttu-id="29295-115">若要設定規範資料庫的資料並將轉換成另一種格式 （例如 XML 檔或 Exchange 託管封存） 介面卡。</span><span class="sxs-lookup"><span data-stu-id="29295-115">You may want to also configure an adapter to take the data from the compliance database and convert to another format (such as XML files or Exchange-hosted archives).</span></span>

  - <span data-ttu-id="29295-p104">您想要如何控制範圍、道德界限及存取？您可以定義 **[類別]** 來隔離這些界限，並選擇允許進入聊天室的人員，這些聊天室是建立於每個類別中。</span><span class="sxs-lookup"><span data-stu-id="29295-p104">How do you want to control scopes, ethical boundaries, and access? You can define **Categories** to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>

  - <span data-ttu-id="29295-p105">您想要如何控制可以建立聊天室的人員？您可以設定適用於類別的 **[建立者]**，讓這類人員可以建立聊天室。建立者可以根據類別所設定的 **[允許的成員/遭拒的成員]** 範圍，將其他成員指派為 **[聊天室管理員]**，以便持續不斷地管理聊天室 (新增或移除其他成員)。</span><span class="sxs-lookup"><span data-stu-id="29295-p105">How do you want to control who can create rooms? You can configure **Creators**, appropriate to your categories, who can create rooms. Creators can assign other members as **Chat Room Managers** for ongoing management of the rooms (adding or removing additional members), according to the scope for **AllowedMembers/DeniedMembers** configured by the category.</span></span>

  - <span data-ttu-id="29295-121">您想要如何建立聊天室？</span><span class="sxs-lookup"><span data-stu-id="29295-121">How do you want to create rooms?</span></span> <span data-ttu-id="29295-122">Persistent Chat Server 提供的 web 式功能的會議室架設與管理。</span><span class="sxs-lookup"><span data-stu-id="29295-122">Persistent Chat Server provides a web-based feature for room creation and management.</span></span> <span data-ttu-id="29295-123">這可以從 Lync 2013 用戶端啟動。</span><span class="sxs-lookup"><span data-stu-id="29295-123">This can be launched from the Lync 2013 client.</span></span> <span data-ttu-id="29295-124">您可以選擇定義的自訂解決方案 （藉由使用常設聊天室伺服器軟體開發套件 (SDK)） 實作您的業務需求與工作流程，並會以引導使用者到您的自訂解決方案的常設聊天室伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="29295-124">You can choose to define a custom solution (by using the Persistent Chat Server Software Development Kit (SDK)) that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>

  - <span data-ttu-id="29295-125">您想要佈建哪些種類的增益集？</span><span class="sxs-lookup"><span data-stu-id="29295-125">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="29295-126">**增益集**來加強室內體驗運用 Lync 2013 用戶端提供與會議室相關的內容中的 [擴充性] 窗格。</span><span class="sxs-lookup"><span data-stu-id="29295-126">**Add-ins** enhance the in-room experience by leveraging the extensibility pane in the Lync 2013 client to provide context that is relevant to the room.</span></span> <span data-ttu-id="29295-127">您可以選擇哪些一般增益集最有用 (例如，貴公司的網站、內部共同作業元件等)。</span><span class="sxs-lookup"><span data-stu-id="29295-127">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="29295-128">聊天室管理員可以選擇其中一個登錄的增益集，並視需要將它關聯至他們的聊天室。</span><span class="sxs-lookup"><span data-stu-id="29295-128">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span>

  - <span data-ttu-id="29295-129">您有哪些種類的高可用性與災害復原需求？</span><span class="sxs-lookup"><span data-stu-id="29295-129">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="29295-130">Persistent Chat Server 支援 SQL Server 鏡像和 SQL Server 叢集的高可用性和支援最多 8 部伺服器 （4 個作用中且 4 待命） 中的延伸集區與 SQL Server 記錄傳送進行災害復原。</span><span class="sxs-lookup"><span data-stu-id="29295-130">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability and supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping for disaster recovery.</span></span>

  - <span data-ttu-id="29295-131">是否有法規需求？</span><span class="sxs-lookup"><span data-stu-id="29295-131">Are there regulatory requirements?</span></span> <span data-ttu-id="29295-132">如果貴公司是在其中的資料必須保持國家/地區內的國家/地區中，您可能需要將多個 Persistent Chat Server 集區，每個本機部署至特定的地理位置。</span><span class="sxs-lookup"><span data-stu-id="29295-132">If your company is in a country/region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="29295-133">會議室、 類別或增益集未跨越集區-它屬於只有一個 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="29295-133">A room, category, or add-in does not span pools—it belongs to only one Persistent Chat Server pool.</span></span> <span data-ttu-id="29295-134">您可以管理類別、 增益集和每個 Persistent Chat Server 集區的聊天室的設定。</span><span class="sxs-lookup"><span data-stu-id="29295-134">You can manage the set of categories, add-ins and rooms for each Persistent Chat Server pool.</span></span> <span data-ttu-id="29295-135">使用者可以設定為具有存取權使用 AllowedMembers 範圍的類別或聊天室的成員資格範圍，根據您如何設計您類別的一個或多個集區中的會議室。</span><span class="sxs-lookup"><span data-stu-id="29295-135">Users can be configured to have access to rooms in one or more pools using the category AllowedMembers scope or Room’s membership scope, depending on how you design your categories.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="29295-136">具有多個 Persistent Chat Server 集區並不會提供更大的範圍 （您可以跨所有 Persistent Chat Server 集區仍有只有 80000 位同時連線的使用者）。</span><span class="sxs-lookup"><span data-stu-id="29295-136">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrently connected users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="29295-137">支援多個 Persistent Chat Server 集區的主要原因是要支援法規考量。</span><span class="sxs-lookup"><span data-stu-id="29295-137">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

