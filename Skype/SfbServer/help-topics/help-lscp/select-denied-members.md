---
title: 選取遭拒絕的成員
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
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: Persistent Chat 系統管理員可以建立及管理聊天室類別。 在建立及管理聊天室類別的過程中，Persistent Chat 管理員可以將主體設定 (Active Directory 網域服務群組/容器/使用者) ，該使用者有權存取屬於特定類別之聊天室的成員/建立者。 Persistent Chat 系統管理員也可以新增 DeniedMembers 至類別，而這些專案會變成對允許清單的明確排除。 DeniedMembers 覆寫 AllowedMembers 中的內容。
ms.openlocfilehash: c5f942723937fe2da28025fba5da1fc7ee121c83
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814573"
---
# <a name="select-denied-members"></a><span data-ttu-id="97675-106">選取遭拒絕的成員</span><span class="sxs-lookup"><span data-stu-id="97675-106">Select Denied Members</span></span>

<span data-ttu-id="97675-107">Persistent Chat 系統管理員可以建立及管理聊天室類別。</span><span class="sxs-lookup"><span data-stu-id="97675-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="97675-108">在建立及管理聊天室類別的過程中，Persistent Chat 管理員可以將主體設定 (Active Directory 網域服務群組/容器/使用者) ，該使用者有權存取屬於特定類別之聊天室的成員/建立者。</span><span class="sxs-lookup"><span data-stu-id="97675-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="97675-109">Persistent Chat 系統管理員也可以新增 DeniedMembers 至類別，而這些專案會變成對允許清單的明確排除。</span><span class="sxs-lookup"><span data-stu-id="97675-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="97675-110">DeniedMembers 覆寫 AllowedMembers 中的內容。</span><span class="sxs-lookup"><span data-stu-id="97675-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="97675-111">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="97675-111">Tasks that you can perform</span></span>

<span data-ttu-id="97675-112">您可以在「 **選取拒絕的成員** 」頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="97675-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="97675-113">設定類別</span><span class="sxs-lookup"><span data-stu-id="97675-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="97675-114">新的持久聊天伺服器功能</span><span class="sxs-lookup"><span data-stu-id="97675-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="97675-115">如需您可以使用商務用 Skype Server 控制台執行的不同程式的詳細資訊，請參閱 [管理商務用 Skype server 2015](../../manage/manage.md)。</span><span class="sxs-lookup"><span data-stu-id="97675-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="97675-116">設定聊天室的類別</span><span class="sxs-lookup"><span data-stu-id="97675-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="97675-117">在 [ **成員資格**] 的 [ **拒絕的成員** ] 區段中，新增或移除與被聊天室拒絕的成員有關聯的使用者及其他 Active Directory 主體。</span><span class="sxs-lookup"><span data-stu-id="97675-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="97675-118">如需 Persistent Chat Server 功能及功能的詳細資訊，請參閱規劃檔中的 [Persistent Chat Server 綜述](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="97675-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="97675-119">如需使用持續性聊天伺服器設定的詳細資訊，請參閱設定 [Persistent Chat server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) In the Deployment 檔和 [管理 Lync Server 2013，Persistent Chat server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in Operations 檔中。</span><span class="sxs-lookup"><span data-stu-id="97675-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="97675-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="97675-120">See also</span></span>

[<span data-ttu-id="97675-121">瞭解 Persistent Chat 成員資格</span><span class="sxs-lookup"><span data-stu-id="97675-121">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
