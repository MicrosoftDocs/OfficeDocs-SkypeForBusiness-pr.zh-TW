---
title: 選取建立者
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
- ms.lync.lscp.SelectCreators
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8d9ed6f-22ba-470e-b0b4-0da3cea5e961
description: 正確使用類別時，建立及管理 Persistent 聊天室的工作會更容易。 Persistent Chat 管理員可以定義每個類別的 AllowedMembers 和建立者，也可以定義將套用到所有在類別中建立之聊天室的預設聊天室設定和行為。 Persistent Chat administrator 使用商務用 Skype Server 控制台或 Windows PowerShell Cmdlet 來建立及管理類別。
ms.openlocfilehash: 9fc8bf615de02a4c9eefcd204c832c5c8691eb7e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821953"
---
# <a name="select-creators"></a><span data-ttu-id="5b483-105">選取建立者</span><span class="sxs-lookup"><span data-stu-id="5b483-105">Select Creators</span></span>

<span data-ttu-id="5b483-106">正確使用類別時，建立及管理 Persistent 聊天室的工作會更容易。</span><span class="sxs-lookup"><span data-stu-id="5b483-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="5b483-107">Persistent Chat 管理員可以定義每個類別的 **AllowedMembers** 和建立 **者** ，也可以定義將套用到所有在類別中建立之聊天室的預設聊天室設定和行為。</span><span class="sxs-lookup"><span data-stu-id="5b483-107">A Persistent Chat administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="5b483-108">Persistent Chat administrator 使用商務用 Skype Server 控制台或 Windows PowerShell Cmdlet 來建立及管理類別。</span><span class="sxs-lookup"><span data-stu-id="5b483-108">Persistent Chat administrators create and manage categories by using Skype for Business Server Control Panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="5b483-109">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="5b483-109">Tasks that you can perform</span></span>

<span data-ttu-id="5b483-110">您可以在「 **選取建立者** 」頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="5b483-110">You can perform the following tasks on the **Select Creators** page:</span></span>

- [<span data-ttu-id="5b483-111">設定類別</span><span class="sxs-lookup"><span data-stu-id="5b483-111">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="5b483-112">新的持久聊天伺服器功能</span><span class="sxs-lookup"><span data-stu-id="5b483-112">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="5b483-113">如需您可以使用商務用 Skype Server 控制台執行的不同程式的詳細資訊，請參閱 [管理商務用 Skype server 2015](../../manage/manage.md)。</span><span class="sxs-lookup"><span data-stu-id="5b483-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="5b483-114">設定聊天室的類別</span><span class="sxs-lookup"><span data-stu-id="5b483-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="5b483-115">在 [ **成員資格**] 的 [建立 **者** ] 區段中，新增或移除與類別建立者相關聯的使用者及其他 Active Directory 主體。</span><span class="sxs-lookup"><span data-stu-id="5b483-115">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="5b483-116">建立者是有權建立聊天室及指派聊天室管理員和成員的使用者。</span><span class="sxs-lookup"><span data-stu-id="5b483-116">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>



<span data-ttu-id="5b483-117">如需 Persistent Chat Server 功能及功能的詳細資訊，請參閱規劃檔中的 [Persistent Chat Server 綜述](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="5b483-117">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="5b483-118">如需使用持續性聊天伺服器設定的詳細資訊，請參閱設定 [Persistent Chat server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) In the Deployment 檔和 [管理 Lync Server 2013，Persistent Chat server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in Operations 檔中。</span><span class="sxs-lookup"><span data-stu-id="5b483-118">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b483-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5b483-119">See also</span></span>

[<span data-ttu-id="5b483-120">瞭解 Persistent Chat 成員資格</span><span class="sxs-lookup"><span data-stu-id="5b483-120">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)

[<span data-ttu-id="5b483-121">使用類別管理 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="5b483-121">Using Categories to Administer Persistent Chat Server</span></span>](https://technet.microsoft.com/library/dfcb3ad1-da90-467e-b08c-f4e68673b7b5.aspx)

[<span data-ttu-id="5b483-122">將聊天室從某個類別移到另一個類別</span><span class="sxs-lookup"><span data-stu-id="5b483-122">Moving a Chat Room from One Category to Another</span></span>](https://technet.microsoft.com/library/7e93b8f6-5a18-4476-a432-3918e01bcfa6.aspx)

[<span data-ttu-id="5b483-123">建立或編輯新聊天室</span><span class="sxs-lookup"><span data-stu-id="5b483-123">Creating or Editing a New Room</span></span>](https://technet.microsoft.com/library/aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4.aspx)
