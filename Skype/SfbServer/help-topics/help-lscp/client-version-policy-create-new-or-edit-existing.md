---
title: 用戶端版本原則建立新的或編輯現有的
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: 您可以指定環境中支援的用戶端版本。 當執行不同版本的兩個用戶端互動時，這兩個用戶端可用的功能會受限於彼此的功能。 若要充分運用商務用 Skype Server 2015 隨附的功能，並改善總體使用者體驗，您可以使用用戶端版本篩選來限制在您的環境中使用的用戶端版本。 使用用戶端版本篩選器還可幫助您降低支援多個用戶端版本的相關成本。
ms.openlocfilehash: d7b8dcbfe8b867de4dd48ba4c736246927e53b9a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823076"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="3e162-106">用戶端版本原則：建立新的或編輯現有原則</span><span class="sxs-lookup"><span data-stu-id="3e162-106">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="3e162-107">您可以指定環境中支援的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="3e162-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="3e162-108">當執行不同版本的兩個用戶端互動時，這兩個用戶端可用的功能會受限於彼此的功能。</span><span class="sxs-lookup"><span data-stu-id="3e162-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="3e162-109">若要充分運用商務用 Skype Server 2015 隨附的功能，並改善總體使用者體驗，您可以使用用戶端版本篩選來限制在您的環境中使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="3e162-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="3e162-110">使用用戶端版本篩選器還可幫助您降低支援多個用戶端版本的相關成本。</span><span class="sxs-lookup"><span data-stu-id="3e162-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e162-p103">篩選器會依優先順序列出。例如，如果您有一個可讓執行 1.5 版的用戶端連線的篩選器，後面接著一個封鎖執行 2.0 以前版本之用戶端的篩選器，則第一個篩選器的優先順序高於第二個，而且執行 1.5 版的用戶端可以連線。</span><span class="sxs-lookup"><span data-stu-id="3e162-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="3e162-113">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="3e162-113">Tasks you can perform</span></span>

<span data-ttu-id="3e162-114">您可以在「新增用戶端版本原則」\*\*\*\* 或「編輯用戶端版本原則」\*\*\*\* 頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="3e162-114">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="3e162-115">新增或修改用戶端版本原則的名稱或描述。</span><span class="sxs-lookup"><span data-stu-id="3e162-115">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="3e162-116">新增或修改用戶端版本原則的用戶端版本規則。</span><span class="sxs-lookup"><span data-stu-id="3e162-116">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="3e162-117">UI 參考</span><span class="sxs-lookup"><span data-stu-id="3e162-117">UI Reference</span></span>

<span data-ttu-id="3e162-118">下列清單說明頁面上的功能表、命令、欄位及內容。</span><span class="sxs-lookup"><span data-stu-id="3e162-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="3e162-119">**範圍**識別用戶端版本原則的範圍（網站、池或使用者）。</span><span class="sxs-lookup"><span data-stu-id="3e162-119">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="3e162-120">**名稱**您可以新增或修改用戶端版本原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="3e162-120">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="3e162-121">**描述**您可以在 [用戶端版本原則] 頁面上的清單中新增描述，以協助識別原則。</span><span class="sxs-lookup"><span data-stu-id="3e162-121">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="3e162-122">**新增**您可以將新的用戶端版本規則新增至原則。</span><span class="sxs-lookup"><span data-stu-id="3e162-122">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="3e162-123">**顯示詳細資料**這個選項會開啟一個對話方塊，您可以在其中變更用戶端版本規則的選項。</span><span class="sxs-lookup"><span data-stu-id="3e162-123">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="3e162-124">**移除**此選項會從原則中移除選取的用戶端版本規則。</span><span class="sxs-lookup"><span data-stu-id="3e162-124">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="3e162-125">**向上鍵和向下鍵**此選項會將選取的用戶端版本規則在 [優先順序] 中向上或向下移動。</span><span class="sxs-lookup"><span data-stu-id="3e162-125">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="3e162-126">規則會按照所列的順序進行處理。</span><span class="sxs-lookup"><span data-stu-id="3e162-126">Rules are processed in the order listed.</span></span>

<span data-ttu-id="3e162-p105">如需用戶端和用戶端版本間互通性的詳細資訊，請參閱規劃文件中的〈[Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)〉。如需使用用戶端版本原則的詳細資訊，請參閱作業文件中的〈[Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="3e162-p105">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

