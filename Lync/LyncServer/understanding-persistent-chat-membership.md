---
title: 瞭解常設聊天室成員資格
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b4eb5fbe4342c1bd6bcb3bbb842e076e5863ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a><span data-ttu-id="e378e-102">瞭解常設聊天室成員資格</span><span class="sxs-lookup"><span data-stu-id="e378e-102">Understanding Persistent Chat membership</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e378e-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="e378e-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="e378e-104">使用者存取持久聊天室是由成員資格所管理;使用者必須是聊天室的成員，才能張貼及閱讀郵件。</span><span class="sxs-lookup"><span data-stu-id="e378e-104">User access to Persistent Chat rooms is managed by membership; users must be members of a chat room to be able to post and read messages.</span></span> <span data-ttu-id="e378e-105">只有已指定隸屬于聊天室的**簡報者**，才可以使用**張貼功能來 Auditorium 會議室**。</span><span class="sxs-lookup"><span data-stu-id="e378e-105">Only **Presenters** who have a designated affiliation with chat rooms are allowed to use **Posting to Auditorium rooms**.</span></span> <span data-ttu-id="e378e-106">Auditorium 是一種聊天室（另一個是**標準**），只有簡報者可以張貼，而且所有人都可以閱讀。</span><span class="sxs-lookup"><span data-stu-id="e378e-106">An auditorium is a type of chat room (the other is **Normal**), where only Presenters can post and everyone can read.</span></span>

<span data-ttu-id="e378e-107">此外，持續聊天室也會在類別的規則下運作。</span><span class="sxs-lookup"><span data-stu-id="e378e-107">In addition, Persistent Chat rooms operate under the rules of a category.</span></span> <span data-ttu-id="e378e-108">如需類別的詳細資訊，請參閱在[Lync Server 2013 中管理類別、會議室和增益集](lync-server-2013-managing-categories-rooms-and-add-ins.md)，以及本主題後面的「類別作用中的運作方式」和「會議室類別戰略」章節。</span><span class="sxs-lookup"><span data-stu-id="e378e-108">For details about categories, see [Managing categories, rooms, and add-ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), and also the sections "How Category Scoping Works" and "Room Category Strategies" later in this topic.</span></span>

<span data-ttu-id="e378e-109">持續聊天系統管理員可以建立及管理聊天室類別。</span><span class="sxs-lookup"><span data-stu-id="e378e-109">A Persistent Chat administrator can create and manage chat room categories.</span></span> <span data-ttu-id="e378e-110">在建立及管理聊天室類別的過程中，持續性聊天管理員可以設定主體（Active Directory 網域服務群組、容器和使用者），這些使用者有權存取屬於特定類別之聊天室的成員或會議室。</span><span class="sxs-lookup"><span data-stu-id="e378e-110">As part of creating and managing chat room categories, the Persistent Chat administrator can configure principals (Active Directory Domain Services groups, containers, and users) that have access to be members or creators of chat rooms of a particular category.</span></span>

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a><span data-ttu-id="e378e-111">Active Directory 網域服務和持續聊天</span><span class="sxs-lookup"><span data-stu-id="e378e-111">Active Directory Domain Services and Persistent Chat</span></span>

<span data-ttu-id="e378e-112">持續聊天伺服器會依賴內部持久聊天使用者池的 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="e378e-112">Persistent Chat Server relies on Active Directory for the pool of internal Persistent Chat users.</span></span> <span data-ttu-id="e378e-113">安裝持續聊天（用戶端）之後，您可以將使用者和使用者群組的網域新增至聊天室類別。</span><span class="sxs-lookup"><span data-stu-id="e378e-113">After you install Persistent Chat (client), you can add domains of users and user groups to the room category.</span></span> <span data-ttu-id="e378e-114">然後，您可以將這些使用者和群組新增至聊天室類別的成員資格。</span><span class="sxs-lookup"><span data-stu-id="e378e-114">You can then add these users and groups to the membership of your room categories.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e378e-115">您必須確定要對其持續聊天室進行變更的使用者，不存在重複的名稱。</span><span class="sxs-lookup"><span data-stu-id="e378e-115">You must ensure that there are no duplicate names for users who want to make changes to their Persistent Chat room(s).</span></span> <span data-ttu-id="e378e-116">如果有重複的使用者名稱存在，請將其變更為不同的名稱，以解除封鎖使用者進行這些變更。</span><span class="sxs-lookup"><span data-stu-id="e378e-116">If duplicate user names exist, change them to different names to unblock users from making those changes.</span></span> <span data-ttu-id="e378e-117">如果使用者在 Active Directory 中有重複的名稱，並嘗試在聊天室中進行變更，則會出現錯誤訊息，提示使用者與管理員聯繫以進行解決。</span><span class="sxs-lookup"><span data-stu-id="e378e-117">If a user has duplicate names in Active Directory and tries to make changes in their room(s), an error message appears prompting the user to contact the administrator for resolution.</span></span>



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a><span data-ttu-id="e378e-118">類別作用中的運作方式</span><span class="sxs-lookup"><span data-stu-id="e378e-118">How Category Scoping Works</span></span>

<span data-ttu-id="e378e-119">類別會根據其**AllowedMembers**屬性，指定可成為該類別之持續聊天室的成員資格清單中的所有使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="e378e-119">A category specifies all the users and groups that can be members in a membership list of a Persistent Chat room in that category, based on its **AllowedMembers** property.</span></span> <span data-ttu-id="e378e-120">例如，如果您將類別的**AllowedMembers**設定為 contoso.com，您可以在*contoso*中新增任何群組或使用者作為該類別中的聊天室。</span><span class="sxs-lookup"><span data-stu-id="e378e-120">For example, if you set the category’s **AllowedMembers** to contoso.com, you can add any group or user at *Contoso* as a member to chat rooms in that category.</span></span> <span data-ttu-id="e378e-121">如果您將類別的**AllowedMembers**設定為 [*銷售*]，則只有此通訊群組清單中的群組和使用者可以新增為該類別中的聊天聊天室成員。</span><span class="sxs-lookup"><span data-stu-id="e378e-121">If you set the **AllowedMembers** on a category to *Sales*, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="e378e-122">同樣地，[**創意者**] 屬性可讓您控制誰可以在該類別中建立聊天室。</span><span class="sxs-lookup"><span data-stu-id="e378e-122">Similarly, the **Creators** property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="e378e-123">在您建立聊天室之後，您可以將來自**AllowedMembers**群組的任何人指派為系統**管理員**，以便在會議室上進行持續的管理作業（例如，成員資格變更與核准）。</span><span class="sxs-lookup"><span data-stu-id="e378e-123">After the chat room is created, anyone from the **AllowedMembers** group can be designated as a **Manager** for ongoing management operations on the rooms (for example, membership changes and approvals).</span></span>

<span data-ttu-id="e378e-124">定義類別的**AllowedMembers**和**創意者**具有下列優點：</span><span class="sxs-lookup"><span data-stu-id="e378e-124">Defining **AllowedMembers** and **Creators** for a category has the following benefits:</span></span>

  - <span data-ttu-id="e378e-125">此類別中的所有聊天室都是由在類別層級設定的限制來系結。</span><span class="sxs-lookup"><span data-stu-id="e378e-125">All chat rooms in this category are bound by the restrictions set at the category level.</span></span> <span data-ttu-id="e378e-126">您可以根據業務需求與存取原則，使用這個功能來隔離聊天室。</span><span class="sxs-lookup"><span data-stu-id="e378e-126">You can use this to segregate chat rooms based on business need and access policies.</span></span>

  - <span data-ttu-id="e378e-127">[**製作者**清單] 中的使用者可以在該類別中建立新的聊天室。</span><span class="sxs-lookup"><span data-stu-id="e378e-127">A user who is in the **Creators** list can create new chat rooms in that category.</span></span> <span data-ttu-id="e378e-128">如果您想要實現組織中受限制的人員可以建立聊天室的系統，此控制項可以用來符合該需求。</span><span class="sxs-lookup"><span data-stu-id="e378e-128">If you want to implement a system where a restricted number of personnel in the organization can create chat rooms, this control can be used to meet that requirement.</span></span>

</div>

<div>

## <a name="room-category-strategies"></a><span data-ttu-id="e378e-129">會議室類別策略</span><span class="sxs-lookup"><span data-stu-id="e378e-129">Room Category Strategies</span></span>

<span data-ttu-id="e378e-130">類別的**AllowedMembers**必須包含所有將在此類別中使用任何持續聊天室的使用者。</span><span class="sxs-lookup"><span data-stu-id="e378e-130">A category’s **AllowedMembers** must include all users who will use any Persistent Chat room in this category.</span></span> <span data-ttu-id="e378e-131">根據您保護商務資料的需求，並確保適當的存取層級，您可能會想要定義一或多個類別，以指定誰可以搜尋及參與會議室。</span><span class="sxs-lookup"><span data-stu-id="e378e-131">Depending on your requirements to protect business data and ensure the appropriate level of access, you may want to define one or more categories to specify who can search and participate in rooms.</span></span> <span data-ttu-id="e378e-132">如果您想要只允許一組特定的使用者（中央支援人員或只有全職員工）來建立會議室，您可以將類別的建立**者**限定為符合該需求。</span><span class="sxs-lookup"><span data-stu-id="e378e-132">If you want to allow only a particular set of users (a central helpdesk, or only full-time employees) to create rooms, you can scope the **Creators** of a category to satisfy that requirement.</span></span>

<span data-ttu-id="e378e-133">您也可以使用類別來建立道德的牆。</span><span class="sxs-lookup"><span data-stu-id="e378e-133">Categories can also be used to create ethical walls.</span></span> <span data-ttu-id="e378e-134">道德的背景牆可避免組織中任何利益衝突的情況。</span><span class="sxs-lookup"><span data-stu-id="e378e-134">Ethical walls prevent any conflict of interest in an organization.</span></span> <span data-ttu-id="e378e-135">例如，管理員只能在商貿類別中建立聊天室，而其他類別的聊天室只能由分析師使用。</span><span class="sxs-lookup"><span data-stu-id="e378e-135">For example, an administrator can create chat rooms in a category for traders only, whereas chat rooms in another category can be used by analysts only.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e378e-136">在 Lync Server 2013 的持續聊天伺服器中，我們不支援聯盟使用者的存取權。</span><span class="sxs-lookup"><span data-stu-id="e378e-136">In Lync Server 2013, Persistent Chat Server, we do not support access to federated users.</span></span> <span data-ttu-id="e378e-137">如果在舊版本的持久性聊天伺服器中有來自同盟使用者的聊天，他們將會被遷移。</span><span class="sxs-lookup"><span data-stu-id="e378e-137">If there are chats from federated users in previous versions of Persistent Chat Server, they will be migrated.</span></span> <span data-ttu-id="e378e-138">聯盟使用者會新增為停用的主體。</span><span class="sxs-lookup"><span data-stu-id="e378e-138">The federated users are added as disabled principals.</span></span>



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a><span data-ttu-id="e378e-139">將成員收縮到使用者群組</span><span class="sxs-lookup"><span data-stu-id="e378e-139">Narrowing the Members to User Groups</span></span>

<span data-ttu-id="e378e-140">當您將網域新增至某個類別時，您可以使用該網域中包含其群組物件的使用者群組，以便將其指定為該類別中的會議室成員。</span><span class="sxs-lookup"><span data-stu-id="e378e-140">When you add a domain to a category, the user groups whose group objects are contained in that domain are available to you so that you can specify them as members of rooms in that category.</span></span>

<span data-ttu-id="e378e-141">我們建議您使用 Active Directory 容器（例如網域和組織單位）來定義類別的**AllowedMembers**及建立**者**，以作為一般規則。</span><span class="sxs-lookup"><span data-stu-id="e378e-141">We recommend, as a general rule, that you use Active Directory containers, such as domains and organizational units, for defining a category’s **AllowedMembers** and **Creators**.</span></span> <span data-ttu-id="e378e-142">您可以將任何網域中的物件新增至**AllowedMembers**或**創意者**清單。</span><span class="sxs-lookup"><span data-stu-id="e378e-142">You can add objects from any domain to an **AllowedMembers** or **Creators** list.</span></span> <span data-ttu-id="e378e-143">只有**AllowedMembers**或**創意者**清單中的物件可以新增到該類別下的聊天室中。</span><span class="sxs-lookup"><span data-stu-id="e378e-143">Only objects within the **AllowedMembers** or **Creators** list can be added to rooms under that category.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

