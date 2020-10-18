---
title: 瞭解 Persistent Chat 成員資格
description: 瞭解 Persistent Chat 成員資格。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63e0d26ea56552d8906ab9a5cf216a7026868017
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579599"
---
# <a name="understanding-persistent-chat-membership"></a><span data-ttu-id="9fd63-103">瞭解 Persistent Chat 成員資格</span><span class="sxs-lookup"><span data-stu-id="9fd63-103">Understanding Persistent Chat membership</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fd63-104">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="9fd63-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="9fd63-105">使用者存取持久聊天室是由成員資格管理;使用者必須是聊天室的成員，才能張貼和閱讀郵件。</span><span class="sxs-lookup"><span data-stu-id="9fd63-105">User access to Persistent Chat rooms is managed by membership; users must be members of a chat room to be able to post and read messages.</span></span> <span data-ttu-id="9fd63-106">只有具有聊天室關聯的 **簡報者** ，才可以使用 **張貼功能來視聽中心會議室**。</span><span class="sxs-lookup"><span data-stu-id="9fd63-106">Only **Presenters** who have a designated affiliation with chat rooms are allowed to use **Posting to Auditorium rooms**.</span></span> <span data-ttu-id="9fd63-107">視聽中心是一種類型的聊天室 (另一種是 **普通**) ，其中只有簡報者可以張貼，而且所有人都可以讀取。</span><span class="sxs-lookup"><span data-stu-id="9fd63-107">An auditorium is a type of chat room (the other is **Normal**), where only Presenters can post and everyone can read.</span></span>

<span data-ttu-id="9fd63-108">此外，Persistent 聊天室會在類別的規則下運作。</span><span class="sxs-lookup"><span data-stu-id="9fd63-108">In addition, Persistent Chat rooms operate under the rules of a category.</span></span> <span data-ttu-id="9fd63-109">如需類別的詳細資訊，請參閱 [管理 Lync Server 2013 中的類別、聊天室及增益集](lync-server-2013-managing-categories-rooms-and-add-ins.md)，以及本主題稍後的「類別範圍的運作方式」和「會議室類別策略」一節。</span><span class="sxs-lookup"><span data-stu-id="9fd63-109">For details about categories, see [Managing categories, rooms, and add-ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), and also the sections "How Category Scoping Works" and "Room Category Strategies" later in this topic.</span></span>

<span data-ttu-id="9fd63-110">Persistent Chat 系統管理員可以建立及管理聊天室類別。</span><span class="sxs-lookup"><span data-stu-id="9fd63-110">A Persistent Chat administrator can create and manage chat room categories.</span></span> <span data-ttu-id="9fd63-111">在建立及管理聊天室類別的過程中，Persistent Chat 管理員可以將主體設定 (Active Directory 網域服務群組、容器和使用者) ，該使用者有權存取屬於特定類別之聊天室的成員或建立者。</span><span class="sxs-lookup"><span data-stu-id="9fd63-111">As part of creating and managing chat room categories, the Persistent Chat administrator can configure principals (Active Directory Domain Services groups, containers, and users) that have access to be members or creators of chat rooms of a particular category.</span></span>

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a><span data-ttu-id="9fd63-112">Active Directory 網域服務和持續聊天</span><span class="sxs-lookup"><span data-stu-id="9fd63-112">Active Directory Domain Services and Persistent Chat</span></span>

<span data-ttu-id="9fd63-113">Persistent Chat Server 依賴內部 Persistent Chat 使用者之集區的 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="9fd63-113">Persistent Chat Server relies on Active Directory for the pool of internal Persistent Chat users.</span></span> <span data-ttu-id="9fd63-114">在您安裝 Persistent Chat (用戶端) 之後，您可以將使用者和使用者群組的網域新增至聊天室類別。</span><span class="sxs-lookup"><span data-stu-id="9fd63-114">After you install Persistent Chat (client), you can add domains of users and user groups to the room category.</span></span> <span data-ttu-id="9fd63-115">然後，您可以將這些使用者和群組新增至您的聊天室類別的成員資格。</span><span class="sxs-lookup"><span data-stu-id="9fd63-115">You can then add these users and groups to the membership of your room categories.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9fd63-116">您必須確定要對其持久聊天室 () 的使用者進行變更時，是否沒有重複的名稱。</span><span class="sxs-lookup"><span data-stu-id="9fd63-116">You must ensure that there are no duplicate names for users who want to make changes to their Persistent Chat room(s).</span></span> <span data-ttu-id="9fd63-117">如果存在重複的使用者名稱，請將其變更為不同的名稱，以解除封鎖使用者進行這些變更。</span><span class="sxs-lookup"><span data-stu-id="9fd63-117">If duplicate user names exist, change them to different names to unblock users from making those changes.</span></span> <span data-ttu-id="9fd63-118">如果使用者在 Active Directory 中有重名的名稱，並嘗試在其聊天室中進行變更 (s) 時，會出現錯誤訊息，提示使用者與系統管理員聯繫以進行解析。</span><span class="sxs-lookup"><span data-stu-id="9fd63-118">If a user has duplicate names in Active Directory and tries to make changes in their room(s), an error message appears prompting the user to contact the administrator for resolution.</span></span>



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a><span data-ttu-id="9fd63-119">類別範圍的運作方式</span><span class="sxs-lookup"><span data-stu-id="9fd63-119">How Category Scoping Works</span></span>

<span data-ttu-id="9fd63-120">類別會根據其 **AllowedMembers** 屬性，指定其成員資格清單中的成員在該類別中的成員資格清單中的所有使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="9fd63-120">A category specifies all the users and groups that can be members in a membership list of a Persistent Chat room in that category, based on its **AllowedMembers** property.</span></span> <span data-ttu-id="9fd63-121">例如，如果您將類別的 **AllowedMembers** 設定為 contoso.com，您可以將 *contoso* 中的任何群組或使用者新增至該類別中的聊天室的成員。</span><span class="sxs-lookup"><span data-stu-id="9fd63-121">For example, if you set the category’s **AllowedMembers** to contoso.com, you can add any group or user at *Contoso* as a member to chat rooms in that category.</span></span> <span data-ttu-id="9fd63-122">如果您將類別上的 **AllowedMembers** 設定為 *Sales*，則只有此通訊群組清單中的群組和使用者可以新增為該類別中聊天室的成員。</span><span class="sxs-lookup"><span data-stu-id="9fd63-122">If you set the **AllowedMembers** on a category to *Sales*, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="9fd63-123">同樣地，建立 **者** 屬性可讓您控制哪些人員可以在該類別建立聊天室。</span><span class="sxs-lookup"><span data-stu-id="9fd63-123">Similarly, the **Creators** property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="9fd63-124">在建立聊天室之後，可以將 **AllowedMembers** 群組中的任何人指派為該會議室上的日常管理作業的 **管理員** (例如，成員資格變更和核准) 。</span><span class="sxs-lookup"><span data-stu-id="9fd63-124">After the chat room is created, anyone from the **AllowedMembers** group can be designated as a **Manager** for ongoing management operations on the rooms (for example, membership changes and approvals).</span></span>

<span data-ttu-id="9fd63-125">定義類別的 **AllowedMembers** 和建立 **者** 具有下列優點：</span><span class="sxs-lookup"><span data-stu-id="9fd63-125">Defining **AllowedMembers** and **Creators** for a category has the following benefits:</span></span>

  - <span data-ttu-id="9fd63-126">此類別中的所有聊天室都受限於在類別層級設定的限制。</span><span class="sxs-lookup"><span data-stu-id="9fd63-126">All chat rooms in this category are bound by the restrictions set at the category level.</span></span> <span data-ttu-id="9fd63-127">您可以使用此功能，根據業務需求和存取原則隔離聊天室。</span><span class="sxs-lookup"><span data-stu-id="9fd63-127">You can use this to segregate chat rooms based on business need and access policies.</span></span>

  - <span data-ttu-id="9fd63-128">建立 **者** 清單中的使用者可以在該類別中建立新聊天室。</span><span class="sxs-lookup"><span data-stu-id="9fd63-128">A user who is in the **Creators** list can create new chat rooms in that category.</span></span> <span data-ttu-id="9fd63-129">如果您想要執行的系統中組織中的人員人數有限，可以建立聊天室，此控制項可用於符合該需求。</span><span class="sxs-lookup"><span data-stu-id="9fd63-129">If you want to implement a system where a restricted number of personnel in the organization can create chat rooms, this control can be used to meet that requirement.</span></span>

</div>

<div>

## <a name="room-category-strategies"></a><span data-ttu-id="9fd63-130">會議室類別策略</span><span class="sxs-lookup"><span data-stu-id="9fd63-130">Room Category Strategies</span></span>

<span data-ttu-id="9fd63-131">類別的 **AllowedMembers** 必須包括將在此類別中使用任何持續聊天室的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="9fd63-131">A category’s **AllowedMembers** must include all users who will use any Persistent Chat room in this category.</span></span> <span data-ttu-id="9fd63-132">根據您保護商務資料的需求，並確定適當的存取層級，您可能想要定義一或多個類別，以指定誰可以搜尋及參與聊天室。</span><span class="sxs-lookup"><span data-stu-id="9fd63-132">Depending on your requirements to protect business data and ensure the appropriate level of access, you may want to define one or more categories to specify who can search and participate in rooms.</span></span> <span data-ttu-id="9fd63-133">如果您只想要允許中央技術支援人員 (一組特定的使用者，或是只) 建立會議室的全職員工，您可以限定類別建立 **者** 以滿足此需求。</span><span class="sxs-lookup"><span data-stu-id="9fd63-133">If you want to allow only a particular set of users (a central helpdesk, or only full-time employees) to create rooms, you can scope the **Creators** of a category to satisfy that requirement.</span></span>

<span data-ttu-id="9fd63-134">類別也可以用來建立道德的背景牆。</span><span class="sxs-lookup"><span data-stu-id="9fd63-134">Categories can also be used to create ethical walls.</span></span> <span data-ttu-id="9fd63-135">道德的牆可防止組織利益衝突。</span><span class="sxs-lookup"><span data-stu-id="9fd63-135">Ethical walls prevent any conflict of interest in an organization.</span></span> <span data-ttu-id="9fd63-136">例如，系統管理員可以只為商貿建立一個類別的聊天室，而另一個類別的聊天室只可供分析員使用。</span><span class="sxs-lookup"><span data-stu-id="9fd63-136">For example, an administrator can create chat rooms in a category for traders only, whereas chat rooms in another category can be used by analysts only.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9fd63-137">在 Lync Server 2013 中，Persistent Chat Server，我們不支援同盟使用者的存取。</span><span class="sxs-lookup"><span data-stu-id="9fd63-137">In Lync Server 2013, Persistent Chat Server, we do not support access to federated users.</span></span> <span data-ttu-id="9fd63-138">如果舊版 Persistent Chat Server 中的同盟使用者已有聊天版本，將會進行遷移。</span><span class="sxs-lookup"><span data-stu-id="9fd63-138">If there are chats from federated users in previous versions of Persistent Chat Server, they will be migrated.</span></span> <span data-ttu-id="9fd63-139">同盟使用者已新增為已停用的主體。</span><span class="sxs-lookup"><span data-stu-id="9fd63-139">The federated users are added as disabled principals.</span></span>



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a><span data-ttu-id="9fd63-140">將成員縮小為使用者群組</span><span class="sxs-lookup"><span data-stu-id="9fd63-140">Narrowing the Members to User Groups</span></span>

<span data-ttu-id="9fd63-141">當您將網域新增至類別時，您可以使用其 group 物件包含在該網域中的使用者群組，讓您將其指定為該類別中聊天室的成員。</span><span class="sxs-lookup"><span data-stu-id="9fd63-141">When you add a domain to a category, the user groups whose group objects are contained in that domain are available to you so that you can specify them as members of rooms in that category.</span></span>

<span data-ttu-id="9fd63-142">我們建議您使用 Active Directory 容器（如網域和組織單位）來定義類別的 **AllowedMembers** 和建立 **者**，以成為一般規則。</span><span class="sxs-lookup"><span data-stu-id="9fd63-142">We recommend, as a general rule, that you use Active Directory containers, such as domains and organizational units, for defining a category’s **AllowedMembers** and **Creators**.</span></span> <span data-ttu-id="9fd63-143">您可以將任何網域中的物件新增至 **AllowedMembers** 或建立 **者** 清單。</span><span class="sxs-lookup"><span data-stu-id="9fd63-143">You can add objects from any domain to an **AllowedMembers** or **Creators** list.</span></span> <span data-ttu-id="9fd63-144">只有 **AllowedMembers** 或建立 **者** 清單中的物件可以新增至該類別底下的聊天室。</span><span class="sxs-lookup"><span data-stu-id="9fd63-144">Only objects within the **AllowedMembers** or **Creators** list can be added to rooms under that category.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

