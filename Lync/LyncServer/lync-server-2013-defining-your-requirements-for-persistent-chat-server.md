---
title: Lync Server 2013：定義常設聊天室伺服器需求
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
ms.openlocfilehash: a0e7482ab85b72168e990eaa97b2f79cb3665532
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="583ef-102">在 Lync Server 2013 中定義組織的常設聊天室伺服器需求</span><span class="sxs-lookup"><span data-stu-id="583ef-102">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="583ef-103">_**主題上次修改日期：** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="583ef-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="583ef-104">在您為貴組織部署持續聊天伺服器之前，請務必考慮下列重要問題，以優化您的部署：</span><span class="sxs-lookup"><span data-stu-id="583ef-104">Before you deploy Persistent Chat Server for your organization, it’s essential to consider the following key questions to optimize your deployment:</span></span>

  - <span data-ttu-id="583ef-105">應該為永久聊天伺服器啟用誰（使用者設定檔）？</span><span class="sxs-lookup"><span data-stu-id="583ef-105">Who (user profile) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="583ef-106">永久聊天伺服器是由可在全域、網站、池或使用者層級設定的原則所啟用。</span><span class="sxs-lookup"><span data-stu-id="583ef-106">Persistent Chat Server is enabled by a policy that can be set at a Global, Site, Pool or User level.</span></span>

  - <span data-ttu-id="583ef-107">應該為持續聊天伺服器啟用多少使用者（小數位數）？</span><span class="sxs-lookup"><span data-stu-id="583ef-107">How many users (scale) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="583ef-108">Persistent 聊天伺服器支援150000預配的使用者（由原則啟用），以及最多可使用持續聊天伺服器80000的併發使用者數上限。</span><span class="sxs-lookup"><span data-stu-id="583ef-108">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users using Persistent Chat Server.</span></span> <span data-ttu-id="583ef-109">單一持久聊天伺服器可支援20000連線的使用者，且單一持續式聊天伺服器池最多可以有4個作用中的伺服器，共80000個同時連接的使用者。</span><span class="sxs-lookup"><span data-stu-id="583ef-109">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>

  - <span data-ttu-id="583ef-110">您是從舊版的群組聊天伺服器進行遷移，還是第一次部署持久聊天伺服器？</span><span class="sxs-lookup"><span data-stu-id="583ef-110">Are you migrating from a previous version of Group Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>

  - <span data-ttu-id="583ef-111">是否有合規性需求？</span><span class="sxs-lookup"><span data-stu-id="583ef-111">Are there compliance requirements?</span></span> <span data-ttu-id="583ef-112">持續聊天伺服器支援合規性。</span><span class="sxs-lookup"><span data-stu-id="583ef-112">Persistent Chat Server supports compliance.</span></span> <span data-ttu-id="583ef-113">合規性服務會在持續聊天伺服器前端伺服器上執行 collocated，而不需要在前一個群組聊天伺服器部署中單獨的電腦。</span><span class="sxs-lookup"><span data-stu-id="583ef-113">The compliance service runs collocated on the Persistent Chat Server Front End Server, as opposed to the requirement for a separate computer in previous Group Chat Server deployments.</span></span> <span data-ttu-id="583ef-114">合規性是選擇性的，如果已選取，則需要一個必須設定為儲存合規性資料和事件的合規性資料庫。</span><span class="sxs-lookup"><span data-stu-id="583ef-114">Compliance is optional, and if chosen, requires a compliance database that must be configured to store compliance data and events.</span></span> <span data-ttu-id="583ef-115">您也可以將配接器設定成從合規性資料庫中取得資料，並轉換成另一種格式（例如 XML 檔案或 Exchange 託管的存檔）。</span><span class="sxs-lookup"><span data-stu-id="583ef-115">You may want to also configure an adapter to take the data from the compliance database and convert to another format (such as XML files or Exchange-hosted archives).</span></span>

  - <span data-ttu-id="583ef-116">您要如何控制範圍、道德界限及存取權？</span><span class="sxs-lookup"><span data-stu-id="583ef-116">How do you want to control scopes, ethical boundaries, and access?</span></span> <span data-ttu-id="583ef-117">您可以定義**類別**來隔離這些界限，並選擇每個類別中所能建立的人員在會議室中。</span><span class="sxs-lookup"><span data-stu-id="583ef-117">You can define **Categories** to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>

  - <span data-ttu-id="583ef-118">您想要如何控制誰可以建立聊天室？</span><span class="sxs-lookup"><span data-stu-id="583ef-118">How do you want to control who can create rooms?</span></span> <span data-ttu-id="583ef-119">您可以將 [**製作者**] 設定為適合您的類別，誰可以建立會議室。</span><span class="sxs-lookup"><span data-stu-id="583ef-119">You can configure **Creators**, appropriate to your categories, who can create rooms.</span></span> <span data-ttu-id="583ef-120">根據類別所設定的**AllowedMembers/DeniedMembers**範圍，創意者可以將其他成員指派為聊天室**管理員**，以便持續管理會議室（新增或移除其他成員）。</span><span class="sxs-lookup"><span data-stu-id="583ef-120">Creators can assign other members as **Chat Room Managers** for ongoing management of the rooms (adding or removing additional members), according to the scope for **AllowedMembers/DeniedMembers** configured by the category.</span></span>

  - <span data-ttu-id="583ef-121">您想要如何建立聊天室？</span><span class="sxs-lookup"><span data-stu-id="583ef-121">How do you want to create rooms?</span></span> <span data-ttu-id="583ef-122">持續聊天伺服器提供在會議室建立與管理的網路功能。</span><span class="sxs-lookup"><span data-stu-id="583ef-122">Persistent Chat Server provides a web-based feature for room creation and management.</span></span> <span data-ttu-id="583ef-123">這可以從 Lync 2013 用戶端啟動。</span><span class="sxs-lookup"><span data-stu-id="583ef-123">This can be launched from the Lync 2013 client.</span></span> <span data-ttu-id="583ef-124">您可以選擇定義自訂解決方案（使用持續式聊天伺服器軟體發展工具組（SDK））來執行您的業務需求與工作流程，並設定持久聊天伺服器以將使用者引導至您的自訂方案。</span><span class="sxs-lookup"><span data-stu-id="583ef-124">You can choose to define a custom solution (by using the Persistent Chat Server Software Development Kit (SDK)) that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>

  - <span data-ttu-id="583ef-125">您想要提供哪種增益集？</span><span class="sxs-lookup"><span data-stu-id="583ef-125">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="583ef-126">**增益集**利用 Lync 2013 用戶端中的 [擴充性] 窗格來提供與聊天室相關的內容，以增強會議室體驗。</span><span class="sxs-lookup"><span data-stu-id="583ef-126">**Add-ins** enhance the in-room experience by leveraging the extensibility pane in the Lync 2013 client to provide context that is relevant to the room.</span></span> <span data-ttu-id="583ef-127">您可以選擇一般的增益集最實用（例如，您的公司網站、內部共同作業檔等等）。</span><span class="sxs-lookup"><span data-stu-id="583ef-127">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="583ef-128">聊天室管理員可以選擇其中一個已註冊的增益集，並視需要將其與聊天室產生關聯。</span><span class="sxs-lookup"><span data-stu-id="583ef-128">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span>

  - <span data-ttu-id="583ef-129">您擁有哪種類型的高可用性和災害復原需求？</span><span class="sxs-lookup"><span data-stu-id="583ef-129">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="583ef-130">持續性聊天伺服器支援 SQL Server 鏡像與 SQL Server 群集，以提供高可用性，且最多支援8台伺服器（4個作用及4個備用），以及適用于災害復原的 SQL Server 記錄傳送。</span><span class="sxs-lookup"><span data-stu-id="583ef-130">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability and supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping for disaster recovery.</span></span>

  - <span data-ttu-id="583ef-131">是否有法規要求？</span><span class="sxs-lookup"><span data-stu-id="583ef-131">Are there regulatory requirements?</span></span> <span data-ttu-id="583ef-132">如果您的公司所在的國家/地區中需要將資料保留在全國，您可能需要將多個持續聊天伺服器池部署到特定地理位置。</span><span class="sxs-lookup"><span data-stu-id="583ef-132">If your company is in a country/region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="583ef-133">[會議室]、[類別] 或 [增益集] 不會跨越多個池，只屬於一個持續聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="583ef-133">A room, category, or add-in does not span pools—it belongs to only one Persistent Chat Server pool.</span></span> <span data-ttu-id="583ef-134">您可以管理每個持續聊天伺服器池的類別、增益集和會議室。</span><span class="sxs-lookup"><span data-stu-id="583ef-134">You can manage the set of categories, add-ins and rooms for each Persistent Chat Server pool.</span></span> <span data-ttu-id="583ef-135">您可以將使用者設定為在一或多個池中使用類別 AllowedMembers 範圍或聊天室的成員資格，來存取會議室，視您設計類別的方式而定。</span><span class="sxs-lookup"><span data-stu-id="583ef-135">Users can be configured to have access to rooms in one or more pools using the category AllowedMembers scope or Room’s membership scope, depending on how you design your categories.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="583ef-136">擁有多個持續聊天伺服器池並不能提供更多規模（您仍可以在所有持久聊天伺服器池中同時連接80000並行連線的使用者）。</span><span class="sxs-lookup"><span data-stu-id="583ef-136">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrently connected users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="583ef-137">支援多個持續聊天伺服器池的主要原因是要支援法規問題。</span><span class="sxs-lookup"><span data-stu-id="583ef-137">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

