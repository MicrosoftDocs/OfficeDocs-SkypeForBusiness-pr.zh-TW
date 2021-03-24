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
ms.openlocfilehash: 5a31716c2fae15c6216ed050b543673479415a76
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107959"
---
# <a name="select-denied-members"></a><span data-ttu-id="b49b9-106">選取遭拒絕的成員</span><span class="sxs-lookup"><span data-stu-id="b49b9-106">Select Denied Members</span></span>

<span data-ttu-id="b49b9-107">Persistent Chat 系統管理員可以建立及管理聊天室類別。</span><span class="sxs-lookup"><span data-stu-id="b49b9-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="b49b9-108">在建立及管理聊天室類別的過程中，Persistent Chat 管理員可以將主體設定 (Active Directory 網域服務群組/容器/使用者) ，該使用者有權存取屬於特定類別之聊天室的成員/建立者。</span><span class="sxs-lookup"><span data-stu-id="b49b9-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="b49b9-109">Persistent Chat 系統管理員也可以新增 DeniedMembers 至類別，而這些專案會變成對允許清單的明確排除。</span><span class="sxs-lookup"><span data-stu-id="b49b9-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="b49b9-110">DeniedMembers 覆寫 AllowedMembers 中的內容。</span><span class="sxs-lookup"><span data-stu-id="b49b9-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="b49b9-111">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="b49b9-111">Tasks that you can perform</span></span>

<span data-ttu-id="b49b9-112">您可以在「 **選取拒絕的成員** 」頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="b49b9-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="b49b9-113">設定類別</span><span class="sxs-lookup"><span data-stu-id="b49b9-113">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="b49b9-114">新的持久聊天伺服器功能</span><span class="sxs-lookup"><span data-stu-id="b49b9-114">New Persistent Chat Server Features</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

<span data-ttu-id="b49b9-115">如需您可以使用商務用 Skype Server 控制台執行的不同程式的詳細資訊，請參閱 [管理商務用 Skype server 2015](../../manage/manage.md)。</span><span class="sxs-lookup"><span data-stu-id="b49b9-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="b49b9-116">設定聊天室的類別</span><span class="sxs-lookup"><span data-stu-id="b49b9-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="b49b9-117">在 [ **成員資格**] 的 [ **拒絕的成員** ] 區段中，新增或移除與被聊天室拒絕的成員有關聯的使用者及其他 Active Directory 主體。</span><span class="sxs-lookup"><span data-stu-id="b49b9-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="b49b9-118">如需 Persistent Chat Server 功能及功能的詳細資訊，請參閱規劃檔中的 [Persistent Chat Server 綜述](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) 。</span><span class="sxs-lookup"><span data-stu-id="b49b9-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="b49b9-119">如需使用持續性聊天伺服器設定的詳細資訊，請參閱設定 [Persistent Chat server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) In the Deployment 檔和 [管理 Lync Server 2013，Persistent Chat server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in Operations 檔中。</span><span class="sxs-lookup"><span data-stu-id="b49b9-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="b49b9-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b49b9-120">See also</span></span>

[<span data-ttu-id="b49b9-121">瞭解 Persistent Chat 成員資格</span><span class="sxs-lookup"><span data-stu-id="b49b9-121">Understanding Persistent Chat Membership</span></span>](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)