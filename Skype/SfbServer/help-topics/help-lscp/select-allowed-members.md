---
title: 選取允許的成員
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: 使用正確的類別，就能更輕鬆地建立及管理持續聊天室。 持續性聊天管理員可以定義每個類別的 AllowedMembers 和創意者，也可以定義預設的聊天室設定和行為，這些動作會套用至在類別中建立的所有聊天室。 持續聊天系統管理員使用 [控制台] 或 [Windows PowerShell Cmdlet] 來建立及管理類別。
ms.openlocfilehash: ad371fada6bbb7e8c9a2620eb5ec533cc60a0673
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822296"
---
# <a name="select-allowed-members"></a><span data-ttu-id="c2db9-105">選取允許的成員</span><span class="sxs-lookup"><span data-stu-id="c2db9-105">Select Allowed Members</span></span>

<span data-ttu-id="c2db9-106">使用正確的類別，就能更輕鬆地建立及管理持續聊天室。</span><span class="sxs-lookup"><span data-stu-id="c2db9-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="c2db9-107">持續性聊天管理員可以定義每個類別的**AllowedMembers**和**創意者**，也可以定義預設的聊天室設定和行為，這些動作會套用至在類別中建立的所有聊天室。</span><span class="sxs-lookup"><span data-stu-id="c2db9-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="c2db9-108">持續聊天系統管理員使用 [控制台] 或 [Windows PowerShell Cmdlet] 來建立及管理類別。</span><span class="sxs-lookup"><span data-stu-id="c2db9-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="c2db9-109">允許以該類別建立聊天室的個人與群組，只有識別為該類別 Creators 的使用者、組織單位 (OU) 及使用者群組。</span><span class="sxs-lookup"><span data-stu-id="c2db9-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="c2db9-110">在建立類別之後，他們可以從類別的**AllowedMembers**清單中選擇使用者、ou 和使用者群組，做為聊天室管理員與管理並參與聊天室的成員。</span><span class="sxs-lookup"><span data-stu-id="c2db9-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="c2db9-111">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="c2db9-111">Tasks that you can perform</span></span>

<span data-ttu-id="c2db9-112">您可以在「選取允許的成員」\*\*\*\* 頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="c2db9-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="c2db9-113">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="c2db9-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="c2db9-114">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="c2db9-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="c2db9-115">如需使用商務用 Skype Server [控制台] 所能執行的不同程式的詳細資訊，請參閱[管理商務用 Skype server 2015](../../manage/manage.md)。</span><span class="sxs-lookup"><span data-stu-id="c2db9-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="c2db9-116">設定聊天室的類別</span><span class="sxs-lookup"><span data-stu-id="c2db9-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="c2db9-117">在 [**成員資格**] 的 [**允許的成員**] 區段中，新增或移除使用者及其他 Active Directory 網域服務主體（使用者、通訊群組、組織單位等），允許將其新增為屬於該類別之聊天室的成員。</span><span class="sxs-lookup"><span data-stu-id="c2db9-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="c2db9-118">類別所允許的主體可以搜尋該類別中的聊天室 (除非該聊天室為隱藏，則只有其成員可以在目錄中搜尋它)。</span><span class="sxs-lookup"><span data-stu-id="c2db9-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="c2db9-119">如需持續聊天伺服器功能與功能的詳細資訊，請參閱規劃檔中的[持續聊天伺服器概覽](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c2db9-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="c2db9-120">如需使用持續聊天伺服器設定的詳細資料，請參閱在部署檔中設定[持久聊天伺服器](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx)，以及[管理 Lync Server 2013](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx)的操作檔中的持續聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="c2db9-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2db9-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c2db9-121">See also</span></span>

[<span data-ttu-id="c2db9-122">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="c2db9-122">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
