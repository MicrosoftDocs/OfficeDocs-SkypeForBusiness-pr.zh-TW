---
title: 選取允許的成員
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 正確使用類別時，建立及管理 Persistent 聊天室的工作會更容易。 Persistent Chat 管理員可以定義每個類別的 AllowedMembers 和建立者，也可以定義將套用到所有在類別中建立之聊天室的預設聊天室設定和行為。 Persistent Chat 系統管理員可以使用控制台或 Windows PowerShell Cmdlet 來建立及管理類別。
ms.openlocfilehash: 8c45a16f88bf20ab973927e17807b3241f20e942
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829133"
---
# <a name="select-allowed-members"></a><span data-ttu-id="7bbb0-105">選取允許的成員</span><span class="sxs-lookup"><span data-stu-id="7bbb0-105">Select Allowed Members</span></span>

<span data-ttu-id="7bbb0-106">正確使用類別時，建立及管理 Persistent 聊天室的工作會更容易。</span><span class="sxs-lookup"><span data-stu-id="7bbb0-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="7bbb0-107">Persistent Chat 管理員可以定義每個類別的 **AllowedMembers** 和建立 **者** ，也可以定義將套用到所有在類別中建立之聊天室的預設聊天室設定和行為。</span><span class="sxs-lookup"><span data-stu-id="7bbb0-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="7bbb0-108">Persistent Chat 系統管理員可以使用控制台或 Windows PowerShell Cmdlet 來建立及管理類別。</span><span class="sxs-lookup"><span data-stu-id="7bbb0-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="7bbb0-109">使用者、組織單位 (Ou) ，以及識別為類別建立者的使用者群組，都是唯一可以在類別中建立聊天室的個人和群組。</span><span class="sxs-lookup"><span data-stu-id="7bbb0-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="7bbb0-110">在建立類別之後，他們可以從類別的 **AllowedMembers** 清單選擇使用者、ou 和使用者群組做為聊天室管理員和成員，以管理及參與會議室。</span><span class="sxs-lookup"><span data-stu-id="7bbb0-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="7bbb0-111">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="7bbb0-111">Tasks that you can perform</span></span>

<span data-ttu-id="7bbb0-112">您可以在「 **選取允許的成員** 」頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="7bbb0-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="7bbb0-113">設定類別</span><span class="sxs-lookup"><span data-stu-id="7bbb0-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="7bbb0-114">新的持久聊天伺服器功能</span><span class="sxs-lookup"><span data-stu-id="7bbb0-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="7bbb0-115">如需您可以使用商務用 Skype Server 控制台執行的不同程式的詳細資訊，請參閱 [管理商務用 Skype server 2015](../../manage/manage.md)。</span><span class="sxs-lookup"><span data-stu-id="7bbb0-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="7bbb0-116">設定聊天室的類別</span><span class="sxs-lookup"><span data-stu-id="7bbb0-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="7bbb0-117">在 [ **成員資格**] 的 [ **允許的成員** ] 區段中，新增或移除使用者及其他 Active Directory 網域服務主體 (使用者、通訊群組、組織單位等) ，允許將其新增為屬於類別之聊天室的成員。</span><span class="sxs-lookup"><span data-stu-id="7bbb0-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="7bbb0-118">類別所允許的主體可以搜尋該類別中的聊天室 (除非該聊天室為隱藏，則只有其成員可以在目錄中搜尋它)。</span><span class="sxs-lookup"><span data-stu-id="7bbb0-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="7bbb0-119">如需 Persistent Chat Server 功能及功能的詳細資訊，請參閱規劃檔中的 [Persistent Chat Server 綜述](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="7bbb0-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="7bbb0-120">如需使用持續性聊天伺服器設定的詳細資訊，請參閱設定 [Persistent Chat server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) In the Deployment 檔和 [管理 Lync Server 2013，Persistent Chat server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in Operations 檔中。</span><span class="sxs-lookup"><span data-stu-id="7bbb0-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="7bbb0-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7bbb0-121">See also</span></span>

[<span data-ttu-id="7bbb0-122">瞭解 Persistent Chat 成員資格</span><span class="sxs-lookup"><span data-stu-id="7bbb0-122">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
