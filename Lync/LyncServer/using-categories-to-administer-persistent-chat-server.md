---
title: 使用類別來管理常設聊天室伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eecae8ff3c84861df7c624e8ca5b958c4fb53696
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049825"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a><span data-ttu-id="1a70c-102">使用類別來管理常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="1a70c-102">Using categories to administer Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a70c-103">_**上次修改主題：** 2013年-10-01_</span><span class="sxs-lookup"><span data-stu-id="1a70c-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="1a70c-104">Persistent Chat Server 部署可以裝載多個同時進行的常設聊天室。</span><span class="sxs-lookup"><span data-stu-id="1a70c-104">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="1a70c-105">聊天室可以在伺服器上組織成一組類別。</span><span class="sxs-lookup"><span data-stu-id="1a70c-105">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="1a70c-106">每個聊天室各屬於一個類別，並繼承該類別的某些設定。</span><span class="sxs-lookup"><span data-stu-id="1a70c-106">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="1a70c-107">這樣的組織會建立一個有用的結構，可用於根據其商業用途來識別交談，並促進委派管理功能和簡化管理。</span><span class="sxs-lookup"><span data-stu-id="1a70c-107">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1a70c-108">雖然有許多聊天室管理功能是用於執行使用者的常設聊天室 （Lync 用戶端） 的電腦，常設聊天室系統管理員 （ <STRONG>cspersistentchatadministrator</STRONG>角色） 必須使用 Lync Server 控制台或 Windows PowerShell cmdlet 來建立或管理類別。</span><span class="sxs-lookup"><span data-stu-id="1a70c-108">Although many of the management features of chat rooms are available in computers running Persistent Chat (Lync client) for the user, Persistent Chat Administrators (in the <STRONG>cspersistentchatadministrator</STRONG> role) must use the Lync Server Control Panel or Windows PowerShell cmdlets to create or manage categories.</span></span>



</div>

<span data-ttu-id="1a70c-109">常設聊天室系統管理員使用 Lync Server 控制台或 Windows PowerShell cmdlet 來建立及管理類別，以及設計聊天室的組織中使用者的存取權。</span><span class="sxs-lookup"><span data-stu-id="1a70c-109">Persistent Chat administrators use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>

<span data-ttu-id="1a70c-110">常設聊天室管理員，擁有管理一或多個聊天室的能力，可以使用 Lync 用戶端來啟動聊天室管理 Web 應用程式以建立及管理聊天室 （或客戶可以建立自訂解決方案和叫用的工作流程）。</span><span class="sxs-lookup"><span data-stu-id="1a70c-110">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the Lync client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> <span data-ttu-id="1a70c-111">常設聊天室系統管理員也可以使用 Lync Server 控制台或 Windows PowerShell cmdlet 建立及管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="1a70c-111">Persistent Chat administrators can also use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage rooms.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1a70c-112">常設聊天室會議室不能有相同的常設聊天室類別的名稱。</span><span class="sxs-lookup"><span data-stu-id="1a70c-112">A Persistent Chat room cannot have the same name as a Persistent Chat category.</span></span>



</div>

<span data-ttu-id="1a70c-p103">聊天室管理員可以變更所有的聊天室內容，但不能變更聊天室的類別。不能限制聊天室管理員執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="1a70c-p103">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>

  - <span data-ttu-id="1a70c-115">停用聊天室</span><span class="sxs-lookup"><span data-stu-id="1a70c-115">Disabling a chat room</span></span>

  - <span data-ttu-id="1a70c-116">變更聊天室名稱</span><span class="sxs-lookup"><span data-stu-id="1a70c-116">Changing a chat room name</span></span>

  - <span data-ttu-id="1a70c-117">變更聊天室說明</span><span class="sxs-lookup"><span data-stu-id="1a70c-117">Changing a chat room description</span></span>

  - <span data-ttu-id="1a70c-118">變更聊天室類型 (視聽形式或是一般形式)</span><span class="sxs-lookup"><span data-stu-id="1a70c-118">Changing a chat room type (Auditorium versus Normal)</span></span>

  - <span data-ttu-id="1a70c-119">變更聊天室的隱私權 (開放、關閉或秘密)</span><span class="sxs-lookup"><span data-stu-id="1a70c-119">Changing the privacy of a room (open versus closed versus secret)</span></span>

  - <span data-ttu-id="1a70c-120">新增或移除成員</span><span class="sxs-lookup"><span data-stu-id="1a70c-120">Adding or removing members</span></span>

  - <span data-ttu-id="1a70c-121">新增或移除聊天室管理員</span><span class="sxs-lookup"><span data-stu-id="1a70c-121">Adding or removing chat room managers</span></span>

  - <span data-ttu-id="1a70c-122">新增或移除增益集</span><span class="sxs-lookup"><span data-stu-id="1a70c-122">Adding or removing an add-in</span></span>

  - <span data-ttu-id="1a70c-123">變更邀請等設定 (根據類別允許的內容)</span><span class="sxs-lookup"><span data-stu-id="1a70c-123">Changing settings such as invitations (according to what’s permitted by the category)</span></span>

<div>

## <a name="delegated-administration"></a><span data-ttu-id="1a70c-124">委派的管理</span><span class="sxs-lookup"><span data-stu-id="1a70c-124">Delegated Administration</span></span>

<span data-ttu-id="1a70c-125">建立及管理常設聊天室就能輕鬆與類別的正確用法。</span><span class="sxs-lookup"><span data-stu-id="1a70c-125">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="1a70c-126">常設聊天室管理員可以針對每個類別定義**AllowedMembers**和**Creators** ，並將會套用至所有聊天室的類別中建立的行為與預設聊天室設定，也可以定義。</span><span class="sxs-lookup"><span data-stu-id="1a70c-126">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="1a70c-127">常設聊天室系統管理員建立並使用 Lync Server 控制台或 Windows PowerShell cmdlet 管理類別。</span><span class="sxs-lookup"><span data-stu-id="1a70c-127">Persistent Chat administrators create and manage categories by using Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="1a70c-128">使用者、 組織單位 (Ou)，並會被識別為類別的建立者的使用者群組是唯一的個人和都可建立聊天室的類別中的群組。</span><span class="sxs-lookup"><span data-stu-id="1a70c-128">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="1a70c-129">建立類別之後，他們可以使用者、 Ou、 及使用者群組從清單中選擇類別**AllowedMembers**為聊天室管理員和成員可以管理和參與會議室。</span><span class="sxs-lookup"><span data-stu-id="1a70c-129">After the category is created, they can choose users, OUs, and user groups from the category’s **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

<span data-ttu-id="1a70c-130">類別中建立的聊天室遵守原則與設定強制提供的類別 （例如，誰具有聊天室的成員資格、 可以管理聊天室、 是否允許檔案上傳，是否要傳送邀請等）。</span><span class="sxs-lookup"><span data-stu-id="1a70c-130">Chat rooms that are created in a category adhere to the policies and settings enforced by the category (such as who can be in the room’s membership, who can manage the room, whether file uploads are allowed, whether invitations are sent, and so on).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

