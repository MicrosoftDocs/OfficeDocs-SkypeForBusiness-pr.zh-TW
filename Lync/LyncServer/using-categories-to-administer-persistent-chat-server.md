---
title: 使用類別以管理常設聊天室伺服器
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
ms.openlocfilehash: 52e56f776969ece55f71355ed7f184dd6dd46a91
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a><span data-ttu-id="4bd5c-102">使用類別以管理常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="4bd5c-102">Using categories to administer Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bd5c-103">_**主題上次修改日期：** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="4bd5c-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="4bd5c-104">您的持續聊天伺服器部署可以主持許多併發持久聊天室。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-104">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="4bd5c-105">聊天室在伺服器上會組織成一組類別。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-105">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="4bd5c-106">每個聊天室各屬於一項類別，而且會繼承該類別中的一些設定。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-106">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="4bd5c-107">這樣的組織會建立一個有用的結構，可用於根據其商業用途來識別交談，並促進委派管理功能和簡化管理。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-107">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4bd5c-108">雖然您可以在執行持續聊天（Lync 用戶端）使用者的電腦上使用聊天室的許多管理功能，但持續聊天系統管理員（在<STRONG>cspersistentchatadministrator</STRONG>角色中）必須使用 Lync Server [控制台] 或 [Windows PowerShell Cmdlet] 來建立或管理類別。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-108">Although many of the management features of chat rooms are available in computers running Persistent Chat (Lync client) for the user, Persistent Chat Administrators (in the <STRONG>cspersistentchatadministrator</STRONG> role) must use the Lync Server Control Panel or Windows PowerShell cmdlets to create or manage categories.</span></span>



</div>

<span data-ttu-id="4bd5c-109">持續性聊天系統管理員使用 Lync Server 控制台或 Windows PowerShell Cmdlet 來建立及管理類別，以及針對組織中的使用者設計聊天室的存取權。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-109">Persistent Chat administrators use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>

<span data-ttu-id="4bd5c-110">持久的聊天室管理員（能管理一或多個聊天室），可使用 Lync 用戶端啟動會議室管理 Web 應用程式來建立及管理會議室（或客戶可以建立要呼叫的自訂解決方案和工作流程）。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-110">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the Lync client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> <span data-ttu-id="4bd5c-111">持續聊天管理員也可以使用 Lync Server [控制台] 或 [Windows PowerShell Cmdlet] 來建立及管理會議室。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-111">Persistent Chat administrators can also use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage rooms.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4bd5c-112">持續聊天室不能與持續聊天類別具有相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-112">A Persistent Chat room cannot have the same name as a Persistent Chat category.</span></span>



</div>

<span data-ttu-id="4bd5c-p103">聊天室管理員可以變更所有聊天室內容，但不能變更聊天室類別。無法限制其進行下列動作：</span><span class="sxs-lookup"><span data-stu-id="4bd5c-p103">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>

  - <span data-ttu-id="4bd5c-115">停用聊天室</span><span class="sxs-lookup"><span data-stu-id="4bd5c-115">Disabling a chat room</span></span>

  - <span data-ttu-id="4bd5c-116">變更聊天室名稱</span><span class="sxs-lookup"><span data-stu-id="4bd5c-116">Changing a chat room name</span></span>

  - <span data-ttu-id="4bd5c-117">變更聊天室說明</span><span class="sxs-lookup"><span data-stu-id="4bd5c-117">Changing a chat room description</span></span>

  - <span data-ttu-id="4bd5c-118">變更聊天室類型 (視聽形式或是一般形式)</span><span class="sxs-lookup"><span data-stu-id="4bd5c-118">Changing a chat room type (Auditorium versus Normal)</span></span>

  - <span data-ttu-id="4bd5c-119">變更聊天室隱私權 (比較開放式、封閉式及祕密)</span><span class="sxs-lookup"><span data-stu-id="4bd5c-119">Changing the privacy of a room (open versus closed versus secret)</span></span>

  - <span data-ttu-id="4bd5c-120">新增或移除成員</span><span class="sxs-lookup"><span data-stu-id="4bd5c-120">Adding or removing members</span></span>

  - <span data-ttu-id="4bd5c-121">新增或移除聊天室管理員</span><span class="sxs-lookup"><span data-stu-id="4bd5c-121">Adding or removing chat room managers</span></span>

  - <span data-ttu-id="4bd5c-122">新增或移除增益集</span><span class="sxs-lookup"><span data-stu-id="4bd5c-122">Adding or removing an add-in</span></span>

  - <span data-ttu-id="4bd5c-123">變更設定，例如邀請 (根據該類別所允許的設定)</span><span class="sxs-lookup"><span data-stu-id="4bd5c-123">Changing settings such as invitations (according to what’s permitted by the category)</span></span>

<div>

## <a name="delegated-administration"></a><span data-ttu-id="4bd5c-124">委派管理</span><span class="sxs-lookup"><span data-stu-id="4bd5c-124">Delegated Administration</span></span>

<span data-ttu-id="4bd5c-125">使用正確的類別，就能更輕鬆地建立及管理持續聊天室。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-125">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="4bd5c-126">持續性聊天管理員可以定義每個類別的**AllowedMembers**和**創意者**，也可以定義預設的聊天室設定和行為，這些動作會套用至在類別中建立的所有聊天室。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-126">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="4bd5c-127">持續聊天系統管理員使用 Lync Server [控制台] 或 [Windows PowerShell Cmdlet] 來建立及管理類別。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-127">Persistent Chat administrators create and manage categories by using Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="4bd5c-p105">允許以該類別建立聊天室的個人與群組，只有識別為該類別 Creators 的使用者、組織單位 (OU) 及使用者群組。建立類別之後，可以從類別的 **AllowedMembers** 清單中選擇使用者、OU 及使用者群組，做為管理和參與聊天室的聊天室管理員與成員。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-p105">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category. After the category is created, they can choose users, OUs, and user groups from the category’s **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

<span data-ttu-id="4bd5c-130">在類別中建立的聊天室會遵守類別所強制的原則和設定（例如誰可以在會議室的成員資格、誰可以管理聊天室、是否允許檔案上傳、是否已傳送邀請等）。</span><span class="sxs-lookup"><span data-stu-id="4bd5c-130">Chat rooms that are created in a category adhere to the policies and settings enforced by the category (such as who can be in the room’s membership, who can manage the room, whether file uploads are allowed, whether invitations are sent, and so on).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

