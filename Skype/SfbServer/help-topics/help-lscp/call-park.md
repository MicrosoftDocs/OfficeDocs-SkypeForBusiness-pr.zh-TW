---
title: 通話駐留
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: 當通話停用時, 會將來電轉接到暫時的號碼中, 讓通話一直留在有人將它取出或超時。您必須使用您為寄存通話保留的延伸編號範圍來設定表格。 這些分機必須是虛擬分機 (也就是，沒有為分機指派任何使用者或電話)。 每個執行通話駐留應用程式的池都可以有一或多個延伸範圍。 在您的部署中，這些範圍必須是全域唯一的。
ms.openlocfilehash: 2b29591ac0173310caf2513db5d27b53142e9ae5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193179"
---
# <a name="call-park"></a><span data-ttu-id="6a1a0-106">通話駐留</span><span class="sxs-lookup"><span data-stu-id="6a1a0-106">Call Park</span></span>

<span data-ttu-id="6a1a0-107">當通話停用時, 會將來電轉接到暫時的號碼中, 讓通話一直留在有人將它取出或超時。您必須使用您為寄存通話保留的延伸編號範圍來設定表格。</span><span class="sxs-lookup"><span data-stu-id="6a1a0-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="6a1a0-108">這些分機必須是虛擬分機 (也就是，沒有為分機指派任何使用者或電話)。</span><span class="sxs-lookup"><span data-stu-id="6a1a0-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="6a1a0-109">每個執行通話駐留應用程式的池都可以有一或多個延伸範圍。</span><span class="sxs-lookup"><span data-stu-id="6a1a0-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="6a1a0-110">在您的部署中，這些範圍必須是全域唯一的。</span><span class="sxs-lookup"><span data-stu-id="6a1a0-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="6a1a0-111">[**通話駐留**] 頁面會顯示針對您的組織定義的所有電話寄存編號範圍清單。</span><span class="sxs-lookup"><span data-stu-id="6a1a0-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="6a1a0-112">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="6a1a0-112">Tasks you can perform</span></span>

<span data-ttu-id="6a1a0-113">您可以從「通話駐留」\*\*\*\* 頁面執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="6a1a0-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="6a1a0-114">建立新號碼範圍</span><span class="sxs-lookup"><span data-stu-id="6a1a0-114">Create a new number range</span></span>

- <span data-ttu-id="6a1a0-115">變更現有號碼範圍</span><span class="sxs-lookup"><span data-stu-id="6a1a0-115">Change an existing number range</span></span>

- <span data-ttu-id="6a1a0-116">刪除號碼範圍</span><span class="sxs-lookup"><span data-stu-id="6a1a0-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="6a1a0-117">UI 參考</span><span class="sxs-lookup"><span data-stu-id="6a1a0-117">UI Reference</span></span>

<span data-ttu-id="6a1a0-118">下列清單說明頁面上的命令。</span><span class="sxs-lookup"><span data-stu-id="6a1a0-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="6a1a0-119">**新增**開始新的通話公園編號範圍。</span><span class="sxs-lookup"><span data-stu-id="6a1a0-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="6a1a0-120">[**編輯**]開啟選取的數位範圍進行編輯、選取清單中的所有數位範圍, 或刪除選取的數位範圍。</span><span class="sxs-lookup"><span data-stu-id="6a1a0-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="6a1a0-121">**更新**刷新數位範圍清單。</span><span class="sxs-lookup"><span data-stu-id="6a1a0-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="6a1a0-122">下列清單說明頁面上的欄位。</span><span class="sxs-lookup"><span data-stu-id="6a1a0-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="6a1a0-123">**名稱**識別數位範圍的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="6a1a0-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="6a1a0-124">**起始範圍**範圍的起始編號。</span><span class="sxs-lookup"><span data-stu-id="6a1a0-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="6a1a0-125">**結束範圍**範圍的結束數位。</span><span class="sxs-lookup"><span data-stu-id="6a1a0-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="6a1a0-126">**目的地**寄存電話號碼範圍之通話駐留應用程式之應用程式服務的完整功能變數名稱 (FQDN) 或服務識別碼。</span><span class="sxs-lookup"><span data-stu-id="6a1a0-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="6a1a0-127">如需通話寄存功能與功能的詳細資料, 請參閱[在商務用 Skype 2015 中規劃通話寄存](../../plan-your-deployment/enterprise-voice-solution/call-park.md)。</span><span class="sxs-lookup"><span data-stu-id="6a1a0-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="6a1a0-128">如需使用通話駐留編號範圍的詳細資料, 請參閱[設定停用通話的電話號碼延伸](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6a1a0-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


