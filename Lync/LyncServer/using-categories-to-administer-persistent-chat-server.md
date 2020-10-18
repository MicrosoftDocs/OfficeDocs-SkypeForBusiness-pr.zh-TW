---
title: 使用類別管理 Persistent Chat Server
description: 使用類別來管理 Persistent Chat Server。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 181ecba944a042e3598b2964ad233590cf63349e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579539"
---
# <a name="using-categories-to-administer-persistent-chat-server"></a><span data-ttu-id="d740f-103">使用類別管理 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="d740f-103">Using categories to administer Persistent Chat Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d740f-104">_**主題上次修改日期：** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="d740f-104">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="d740f-105">您的持久聊天伺服器部署可以主控許多併發的持久聊天室。</span><span class="sxs-lookup"><span data-stu-id="d740f-105">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="d740f-106">聊天室可以在伺服器上組織成一組類別。</span><span class="sxs-lookup"><span data-stu-id="d740f-106">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="d740f-107">每個聊天室各屬於一個類別，並繼承該類別的某些設定。</span><span class="sxs-lookup"><span data-stu-id="d740f-107">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="d740f-108">這樣的組織會建立一個有用的結構，可用於根據其商業用途來識別交談，並促進委派管理功能和簡化管理。</span><span class="sxs-lookup"><span data-stu-id="d740f-108">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d740f-109">雖然聊天室的許多管理功能均可在執行 Persistent Chat (Lync 用戶端) 的電腦上使用，但在 <STRONG>cspersistentchatadministrator</STRONG> role 中) 的持續性聊天系統管理員 (，必須使用 Lync Server 控制台或 Windows PowerShell Cmdlet 來建立或管理類別。</span><span class="sxs-lookup"><span data-stu-id="d740f-109">Although many of the management features of chat rooms are available in computers running Persistent Chat (Lync client) for the user, Persistent Chat Administrators (in the <STRONG>cspersistentchatadministrator</STRONG> role) must use the Lync Server Control Panel or Windows PowerShell cmdlets to create or manage categories.</span></span>



</div>

<span data-ttu-id="d740f-110">Persistent Chat administrator 使用 Lync Server 控制台或 Windows PowerShell Cmdlet 來建立及管理類別，以及為組織中的使用者設計聊天室的存取。</span><span class="sxs-lookup"><span data-stu-id="d740f-110">Persistent Chat administrators use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>

<span data-ttu-id="d740f-111">Persistent 聊天室管理員（能夠管理一或多個聊天室）可以使用 Lync 用戶端來啟動聊天室管理 Web 應用程式，以建立及管理會議室 (或客戶可以建立自訂的解決方案和工作流程以) 進行呼叫。</span><span class="sxs-lookup"><span data-stu-id="d740f-111">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the Lync client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> <span data-ttu-id="d740f-112">Persistent Chat 系統管理員也可以使用 Lync Server 控制台或 Windows PowerShell Cmdlet 來建立及管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="d740f-112">Persistent Chat administrators can also use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage rooms.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d740f-113">Persistent 聊天室的名稱不能與 Persistent 聊天類別相同。</span><span class="sxs-lookup"><span data-stu-id="d740f-113">A Persistent Chat room cannot have the same name as a Persistent Chat category.</span></span>



</div>

<span data-ttu-id="d740f-p103">聊天室管理員可以變更所有的聊天室內容，但不能變更聊天室的類別。不能限制聊天室管理員執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d740f-p103">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>

  - <span data-ttu-id="d740f-116">停用聊天室</span><span class="sxs-lookup"><span data-stu-id="d740f-116">Disabling a chat room</span></span>

  - <span data-ttu-id="d740f-117">變更聊天室名稱</span><span class="sxs-lookup"><span data-stu-id="d740f-117">Changing a chat room name</span></span>

  - <span data-ttu-id="d740f-118">變更聊天室說明</span><span class="sxs-lookup"><span data-stu-id="d740f-118">Changing a chat room description</span></span>

  - <span data-ttu-id="d740f-119">變更聊天室類型 (視聽形式或是一般形式)</span><span class="sxs-lookup"><span data-stu-id="d740f-119">Changing a chat room type (Auditorium versus Normal)</span></span>

  - <span data-ttu-id="d740f-120">變更聊天室的隱私權 (開放、關閉或秘密)</span><span class="sxs-lookup"><span data-stu-id="d740f-120">Changing the privacy of a room (open versus closed versus secret)</span></span>

  - <span data-ttu-id="d740f-121">新增或移除成員</span><span class="sxs-lookup"><span data-stu-id="d740f-121">Adding or removing members</span></span>

  - <span data-ttu-id="d740f-122">新增或移除聊天室管理員</span><span class="sxs-lookup"><span data-stu-id="d740f-122">Adding or removing chat room managers</span></span>

  - <span data-ttu-id="d740f-123">新增或移除增益集</span><span class="sxs-lookup"><span data-stu-id="d740f-123">Adding or removing an add-in</span></span>

  - <span data-ttu-id="d740f-124">變更邀請等設定 (根據類別允許的內容)</span><span class="sxs-lookup"><span data-stu-id="d740f-124">Changing settings such as invitations (according to what’s permitted by the category)</span></span>

<div>

## <a name="delegated-administration"></a><span data-ttu-id="d740f-125">委派管理</span><span class="sxs-lookup"><span data-stu-id="d740f-125">Delegated Administration</span></span>

<span data-ttu-id="d740f-126">正確使用類別時，建立及管理 Persistent 聊天室的工作會更容易。</span><span class="sxs-lookup"><span data-stu-id="d740f-126">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="d740f-127">Persistent Chat 管理員可以定義每個類別的 **AllowedMembers** 和建立 **者** ，也可以定義將套用到所有在類別中建立之聊天室的預設聊天室設定和行為。</span><span class="sxs-lookup"><span data-stu-id="d740f-127">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="d740f-128">Persistent Chat 系統管理員可以使用 Lync Server 控制台或 Windows PowerShell Cmdlet 來建立及管理類別。</span><span class="sxs-lookup"><span data-stu-id="d740f-128">Persistent Chat administrators create and manage categories by using Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="d740f-129">使用者、組織單位 (Ou) ，以及識別為類別建立者的使用者群組，都是唯一可以在類別中建立聊天室的個人和群組。</span><span class="sxs-lookup"><span data-stu-id="d740f-129">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="d740f-130">在建立類別之後，他們可以從類別的 **AllowedMembers** 清單選擇使用者、ou 和使用者群組做為聊天室管理員和成員，以管理及參與會議室。</span><span class="sxs-lookup"><span data-stu-id="d740f-130">After the category is created, they can choose users, OUs, and user groups from the category’s **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

<span data-ttu-id="d740f-131">在類別中建立的聊天室遵循類別 (所強制執行的原則和設定，例如誰可以在會議室的成員資格、誰可以管理該會議室、是否允許檔案上傳、是否已傳送邀請，等等) 。</span><span class="sxs-lookup"><span data-stu-id="d740f-131">Chat rooms that are created in a category adhere to the policies and settings enforced by the category (such as who can be in the room’s membership, who can manage the room, whether file uploads are allowed, whether invitations are sent, and so on).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

