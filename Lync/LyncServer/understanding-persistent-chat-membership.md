---
title: 了解常設聊天室成員資格
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
ms.openlocfilehash: 3cc357eff6cdc68c5285eeb915f5534b6f38b871
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a><span data-ttu-id="bfaa8-102">了解常設聊天室成員資格</span><span class="sxs-lookup"><span data-stu-id="bfaa8-102">Understanding Persistent Chat membership</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfaa8-103">_**上次修改主題：** 2013年-02-22_</span><span class="sxs-lookup"><span data-stu-id="bfaa8-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="bfaa8-104">使用者的存取權的常設聊天室管理成員資格;使用者必須能夠傳送及讀取郵件聊天室的成員。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-104">User access to Persistent Chat rooms is managed by membership; users must be members of a chat room to be able to post and read messages.</span></span> <span data-ttu-id="bfaa8-105">只有**簡報者**具有聊天室與指定的 affiliation 允許使用**張貼至視聽中心聊天室**。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-105">Only **Presenters** who have a designated affiliation with chat rooms are allowed to use **Posting to Auditorium rooms**.</span></span> <span data-ttu-id="bfaa8-106">視聽中心是一種聊天室 （另一個是**標準模式**），其中只有簡報者可以張貼及每個人都可以讀取。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-106">An auditorium is a type of chat room (the other is **Normal**), where only Presenters can post and everyone can read.</span></span>

<span data-ttu-id="bfaa8-107">此外，常設聊天室操作類別的規則] 下。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-107">In addition, Persistent Chat rooms operate under the rules of a category.</span></span> <span data-ttu-id="bfaa8-108">如需類別的詳細資訊，請參閱[管理類別、 聊天室及 Lync Server 2013 中增益集](lync-server-2013-managing-categories-rooms-and-add-ins.md)，以及在本主題稍後的區段 」 類別範圍設定的運作方式 」 和 「 聊天室類別策略 」。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-108">For details about categories, see [Managing categories, rooms, and add-ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), and also the sections "How Category Scoping Works" and "Room Category Strategies" later in this topic.</span></span>

<span data-ttu-id="bfaa8-109">常設聊天室管理員可以建立及管理聊天室類別。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-109">A Persistent Chat administrator can create and manage chat room categories.</span></span> <span data-ttu-id="bfaa8-110">建立及管理聊天室類別的一部分，常設聊天室系統管理員可以設定已設為 [成員] 或 [建立者的特定類別的聊天室存取的主體 （Active Directory 網域服務群組、 容器，以及使用者）。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-110">As part of creating and managing chat room categories, the Persistent Chat administrator can configure principals (Active Directory Domain Services groups, containers, and users) that have access to be members or creators of chat rooms of a particular category.</span></span>

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a><span data-ttu-id="bfaa8-111">Active Directory 網域服務和常設聊天室</span><span class="sxs-lookup"><span data-stu-id="bfaa8-111">Active Directory Domain Services and Persistent Chat</span></span>

<span data-ttu-id="bfaa8-112">Persistent Chat Server 會依賴的常設聊天室的內部使用者的集區的 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-112">Persistent Chat Server relies on Active Directory for the pool of internal Persistent Chat users.</span></span> <span data-ttu-id="bfaa8-113">安裝常設聊天室 （用戶端） 之後，您可以將使用者和使用者群組的網域新增至聊天室類別。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-113">After you install Persistent Chat (client), you can add domains of users and user groups to the room category.</span></span> <span data-ttu-id="bfaa8-114">然後可以將這些使用者和群組新增至聊天室類別的成員資格。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-114">You can then add these users and groups to the membership of your room categories.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bfaa8-115">您必須確定有想要對其常設 Chat room(s) 進行變更的使用者沒有重複的名稱。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-115">You must ensure that there are no duplicate names for users who want to make changes to their Persistent Chat room(s).</span></span> <span data-ttu-id="bfaa8-116">如果存在重複的使用者名稱，請將它們變更為不同的名稱，以解除封鎖來自進行這些變更的使用者。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-116">If duplicate user names exist, change them to different names to unblock users from making those changes.</span></span> <span data-ttu-id="bfaa8-117">如果使用者在 Active Directory 中有重複的名稱，並嘗試在其 room(s) 中進行變更，會出現錯誤訊息，提示使用者連絡系統管理員以解決方法。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-117">If a user has duplicate names in Active Directory and tries to make changes in their room(s), an error message appears prompting the user to contact the administrator for resolution.</span></span>



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a><span data-ttu-id="bfaa8-118">類別範圍的運作方式</span><span class="sxs-lookup"><span data-stu-id="bfaa8-118">How Category Scoping Works</span></span>

<span data-ttu-id="bfaa8-119">類別指定的所有使用者和群組可在該類別中，根據其**AllowedMembers**屬性常設聊天室聊天室成員資格清單中的成員。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-119">A category specifies all the users and groups that can be members in a membership list of a Persistent Chat room in that category, based on its **AllowedMembers** property.</span></span> <span data-ttu-id="bfaa8-120">例如，如果您將類別的**AllowedMembers**為 contoso.com，您可以新增任何群組或使用者在*contoso 公司*的成員身分至該類別中聊天室。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-120">For example, if you set the category’s **AllowedMembers** to contoso.com, you can add any group or user at *Contoso* as a member to chat rooms in that category.</span></span> <span data-ttu-id="bfaa8-121">如果您設定類別以*銷售* **AllowedMembers** ，只有群組及此通訊群組清單中的使用者可以新增為成員至該類別中聊天室。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-121">If you set the **AllowedMembers** on a category to *Sales*, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="bfaa8-122">同樣地， **Creators**屬性可讓您控制可以建立該類別中聊天室。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-122">Similarly, the **Creators** property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="bfaa8-123">聊天室建立之後，從**AllowedMembers**群組的任何人都可以指定做為**管理員**的聊天室 （例如，成員資格變更及核准） 上的進行中的管理作業。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-123">After the chat room is created, anyone from the **AllowedMembers** group can be designated as a **Manager** for ongoing management operations on the rooms (for example, membership changes and approvals).</span></span>

<span data-ttu-id="bfaa8-124">類別定義**AllowedMembers**和**Creators**有下列優點：</span><span class="sxs-lookup"><span data-stu-id="bfaa8-124">Defining **AllowedMembers** and **Creators** for a category has the following benefits:</span></span>

  - <span data-ttu-id="bfaa8-125">此類別中的所有聊天室都 eng 類別層級設定的限制。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-125">All chat rooms in this category are bound by the restrictions set at the category level.</span></span> <span data-ttu-id="bfaa8-126">您可以使用這個單獨分開的聊天室根據業務需要和存取原則。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-126">You can use this to segregate chat rooms based on business need and access policies.</span></span>

  - <span data-ttu-id="bfaa8-127">在 [**建立者**] 清單中的使用者可以建立新聊天室該類別中。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-127">A user who is in the **Creators** list can create new chat rooms in that category.</span></span> <span data-ttu-id="bfaa8-128">如果您想要實作有限的數目的組織中的人員可以在其中建立聊天室的系統，此控制項可以用來符合此需求。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-128">If you want to implement a system where a restricted number of personnel in the organization can create chat rooms, this control can be used to meet that requirement.</span></span>

</div>

<div>

## <a name="room-category-strategies"></a><span data-ttu-id="bfaa8-129">聊天室類別策略</span><span class="sxs-lookup"><span data-stu-id="bfaa8-129">Room Category Strategies</span></span>

<span data-ttu-id="bfaa8-130">類別**AllowedMembers**必須包含將使用此類別中的任何常設聊天室會議室的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-130">A category’s **AllowedMembers** must include all users who will use any Persistent Chat room in this category.</span></span> <span data-ttu-id="bfaa8-131">根據您的需求來保護商務資料，並確保適當的存取層級，您可能想要定義一個或多個類別，來指定誰可以搜尋並參與聊天室。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-131">Depending on your requirements to protect business data and ensure the appropriate level of access, you may want to define one or more categories to specify who can search and participate in rooms.</span></span> <span data-ttu-id="bfaa8-132">如果您想要允許只有一組特定使用者 （中央技術服務人員或只開放全職員工） 來建立會議室，您可以範圍以滿足此需求類別**建立者**。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-132">If you want to allow only a particular set of users (a central helpdesk, or only full-time employees) to create rooms, you can scope the **Creators** of a category to satisfy that requirement.</span></span>

<span data-ttu-id="bfaa8-133">類別也可以用來建立道德管束。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-133">Categories can also be used to create ethical walls.</span></span> <span data-ttu-id="bfaa8-134">道德管束防止在組織中任何衝突的利息。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-134">Ethical walls prevent any conflict of interest in an organization.</span></span> <span data-ttu-id="bfaa8-135">例如，系統管理員可以建立聊天室類別中的 traders 只而另一個類別中聊天室可以用來分析師僅。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-135">For example, an administrator can create chat rooms in a category for traders only, whereas chat rooms in another category can be used by analysts only.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bfaa8-136">在 Lync Server 2013，Persistent Chat Server，我們不支援同盟使用者存取。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-136">In Lync Server 2013, Persistent Chat Server, we do not support access to federated users.</span></span> <span data-ttu-id="bfaa8-137">如果有從舊版 Persistent Chat Server 中的同盟使用者的聊天室，他們將會移轉。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-137">If there are chats from federated users in previous versions of Persistent Chat Server, they will be migrated.</span></span> <span data-ttu-id="bfaa8-138">同盟的使用者新增為已停用的主體。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-138">The federated users are added as disabled principals.</span></span>



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a><span data-ttu-id="bfaa8-139">範圍縮小至使用者群組的成員</span><span class="sxs-lookup"><span data-stu-id="bfaa8-139">Narrowing the Members to User Groups</span></span>

<span data-ttu-id="bfaa8-140">當您新增網域至類別時，其群組物件都包含在該網域的使用者群組可用於您，讓您可以將它們指定為該類別中聊天室的成員。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-140">When you add a domain to a category, the user groups whose group objects are contained in that domain are available to you so that you can specify them as members of rooms in that category.</span></span>

<span data-ttu-id="bfaa8-141">我們建議，作為一般規則，您使用 Active Directory 容器、 網域及組織單位，例如定義類別**AllowedMembers**和**Creators**。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-141">We recommend, as a general rule, that you use Active Directory containers, such as domains and organizational units, for defining a category’s **AllowedMembers** and **Creators**.</span></span> <span data-ttu-id="bfaa8-142">您可以將物件從任何網域新增至**AllowedMembers**或**建立者**的清單。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-142">You can add objects from any domain to an **AllowedMembers** or **Creators** list.</span></span> <span data-ttu-id="bfaa8-143">只有**AllowedMembers**或**建立者**清單中的物件可以新增至該類別底下的聊天室。</span><span class="sxs-lookup"><span data-stu-id="bfaa8-143">Only objects within the **AllowedMembers** or **Creators** list can be added to rooms under that category.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

