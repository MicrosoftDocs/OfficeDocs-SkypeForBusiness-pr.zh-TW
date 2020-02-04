---
title: 用戶端版本原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以指定環境中支援的用戶端版本。 當執行不同版本的兩個用戶端互動時，這兩個用戶端可用的功能會受限於彼此的功能。
ms.openlocfilehash: 62ec8d2e242ccb0202a700a2a0427c4ed898a29d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705268"
---
# <a name="client-version-policy"></a><span data-ttu-id="ada21-104">用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="ada21-104">Client Version Policy</span></span>

<span data-ttu-id="ada21-105">您可以指定環境中支援的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="ada21-105">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="ada21-106">當執行不同版本的兩個用戶端互動時，這兩個用戶端可用的功能會受限於彼此的功能。</span><span class="sxs-lookup"><span data-stu-id="ada21-106">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="ada21-107">若要充分運用商務用 Skype Server 中包含的功能，並改善總體使用者體驗，您可以使用用戶端版本篩選來限制在您的環境中使用的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="ada21-107">To make the greatest use of features included in Skype for Business Server and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="ada21-108">使用用戶端版本篩選器還可幫助您降低支援多個用戶端版本的相關成本。</span><span class="sxs-lookup"><span data-stu-id="ada21-108">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="ada21-109">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="ada21-109">Tasks you can perform</span></span>

<span data-ttu-id="ada21-110">您可以在「用戶端版本原則」\*\*\*\* 頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="ada21-110">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="ada21-111">編輯預設（**全域**）用戶端版本原則。</span><span class="sxs-lookup"><span data-stu-id="ada21-111">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="ada21-112">為特定網站或集區建立用戶端版本原則。</span><span class="sxs-lookup"><span data-stu-id="ada21-112">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="ada21-113">建立可以指派給個別使用者的用戶端版本原則。</span><span class="sxs-lookup"><span data-stu-id="ada21-113">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="ada21-114">由於匿名使用者不會與使用者、網站或服務產生關聯，因此匿名使用者只會受全域層級的原則影響。</span><span class="sxs-lookup"><span data-stu-id="ada21-114">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="ada21-115">UI 參考</span><span class="sxs-lookup"><span data-stu-id="ada21-115">UI Reference</span></span>

<span data-ttu-id="ada21-116">下列清單說明頁面上的功能表、命令、欄位及內容。</span><span class="sxs-lookup"><span data-stu-id="ada21-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="ada21-117">**新增**您可以建立下列其中一或多個用戶端版本原則：</span><span class="sxs-lookup"><span data-stu-id="ada21-117">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="ada21-118">網站原則</span><span class="sxs-lookup"><span data-stu-id="ada21-118">Site policy</span></span>

  - <span data-ttu-id="ada21-119">集區原則</span><span class="sxs-lookup"><span data-stu-id="ada21-119">Pool policy</span></span>

  - <span data-ttu-id="ada21-120">使用者原則</span><span class="sxs-lookup"><span data-stu-id="ada21-120">User policy</span></span>

- <span data-ttu-id="ada21-121">[**編輯**]您可以變更任何用戶端版本原則的選項。</span><span class="sxs-lookup"><span data-stu-id="ada21-121">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="ada21-122">使用此選項，您可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ada21-122">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="ada21-123">**顯示詳細資料**這個選項會開啟一個對話方塊，您可以在其中變更用戶端版本原則的選項。</span><span class="sxs-lookup"><span data-stu-id="ada21-123">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="ada21-124">**選取全部**此選項會選取清單中的所有用戶端版本原則。</span><span class="sxs-lookup"><span data-stu-id="ada21-124">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="ada21-125">**刪除**此選項會刪除所有選取的用戶端版本原則。</span><span class="sxs-lookup"><span data-stu-id="ada21-125">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="ada21-126">**更新**您可以重新整理用戶端版本原則清單，以驗證所有用戶端版本原則的選項狀態。</span><span class="sxs-lookup"><span data-stu-id="ada21-126">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="ada21-127">如需用戶端與用戶端版本之間的互通性詳細資料，請參閱規劃檔中的[用戶端互用性](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ada21-127">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="ada21-128">如需使用用戶端版本原則的詳細資訊，請參閱作業文件中的〈[Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="ada21-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

