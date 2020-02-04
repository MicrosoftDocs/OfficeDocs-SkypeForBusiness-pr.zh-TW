---
title: 選取拒絕的成員
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: 持續聊天系統管理員可以建立及管理聊天室類別。 在建立及管理聊天室類別的過程中，持續性聊天管理員可以設定主體（Active Directory 網域服務群組/容器/使用者），這些使用者有權存取成為特定類別之聊天室的成員/提供者。 持續聊天管理員也可以將 DeniedMembers 新增至某個類別，並將它們變成 [允許] 清單的明確排除式。 DeniedMembers 會覆寫 AllowedMembers 中的內容。
ms.openlocfilehash: c8b357abe49d794283b7165d9c5decdffaece275
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685878"
---
# <a name="select-denied-members"></a><span data-ttu-id="0e510-106">選取拒絕的成員</span><span class="sxs-lookup"><span data-stu-id="0e510-106">Select Denied Members</span></span>

<span data-ttu-id="0e510-107">持續聊天系統管理員可以建立及管理聊天室類別。</span><span class="sxs-lookup"><span data-stu-id="0e510-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="0e510-108">在建立及管理聊天室類別的過程中，持續性聊天管理員可以設定主體（Active Directory 網域服務群組/容器/使用者），這些使用者有權存取成為特定類別之聊天室的成員/提供者。</span><span class="sxs-lookup"><span data-stu-id="0e510-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="0e510-109">持續聊天管理員也可以將 DeniedMembers 新增至某個類別，並將它們變成 [允許] 清單的明確排除式。</span><span class="sxs-lookup"><span data-stu-id="0e510-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="0e510-110">DeniedMembers 會覆寫 AllowedMembers 中的內容。</span><span class="sxs-lookup"><span data-stu-id="0e510-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="0e510-111">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="0e510-111">Tasks that you can perform</span></span>

<span data-ttu-id="0e510-112">您可以在「選取拒絕的成員」\*\*\*\* 頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="0e510-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="0e510-113">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="0e510-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="0e510-114">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="0e510-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="0e510-115">如需使用商務用 Skype Server [控制台] 所能執行的不同程式的詳細資訊，請參閱[管理商務用 Skype server 2015](../../manage/manage.md)。</span><span class="sxs-lookup"><span data-stu-id="0e510-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="0e510-116">設定聊天室的類別</span><span class="sxs-lookup"><span data-stu-id="0e510-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="0e510-117">在 [**成員資格**] 的 [**拒絕的成員**] 區段中，新增或移除與從聊天室拒絕的成員相關聯的使用者及其他 Active Directory 主體。</span><span class="sxs-lookup"><span data-stu-id="0e510-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="0e510-118">如需持續聊天伺服器功能與功能的詳細資訊，請參閱規劃檔中的[持續聊天伺服器概覽](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0e510-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="0e510-119">如需使用持續聊天伺服器設定的詳細資料，請參閱在部署檔中設定[持久聊天伺服器](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx)，以及[管理 Lync Server 2013](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx)的操作檔中的持續聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="0e510-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e510-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0e510-120">See also</span></span>

[<span data-ttu-id="0e510-121">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="0e510-121">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
