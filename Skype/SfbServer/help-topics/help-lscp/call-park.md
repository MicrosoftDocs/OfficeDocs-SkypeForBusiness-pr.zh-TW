---
title: 通話駐留
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
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: 當來電停用時，會將通話轉移至暫留的臨時號碼，直到有人將通話轉移或下班時為止。您必須使用保留用於寄存通話的分機號碼範圍來設定表格。 這些分機號碼必須是虛擬分機 (亦即，未指派使用者或電話的分機) 。 每個執行通話駐留應用程式的集區，都可以有一個或多個範圍的分機。 在您的部署中，這些範圍必須是全域唯一的。
ms.openlocfilehash: 7723b3bb3145725834059c73c0acc273fc67ca61
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800303"
---
# <a name="call-park"></a><span data-ttu-id="79413-106">通話駐留</span><span class="sxs-lookup"><span data-stu-id="79413-106">Call Park</span></span>

<span data-ttu-id="79413-107">當來電停用時，會將通話轉移至暫留的臨時號碼，直到有人將通話轉移或下班時為止。您必須使用保留用於寄存通話的分機號碼範圍來設定表格。</span><span class="sxs-lookup"><span data-stu-id="79413-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="79413-108">這些分機號碼必須是虛擬分機 (亦即，未指派使用者或電話的分機) 。</span><span class="sxs-lookup"><span data-stu-id="79413-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="79413-109">每個執行通話駐留應用程式的集區，都可以有一個或多個範圍的分機。</span><span class="sxs-lookup"><span data-stu-id="79413-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="79413-110">在您的部署中，這些範圍必須是全域唯一的。</span><span class="sxs-lookup"><span data-stu-id="79413-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="79413-111">「 **通話駐留** 」頁面會顯示針對您組織所定義之所有通話駐留號碼範圍的清單。</span><span class="sxs-lookup"><span data-stu-id="79413-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="79413-112">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="79413-112">Tasks you can perform</span></span>

<span data-ttu-id="79413-113">您可以從「 **通話駐留** 」頁面執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="79413-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="79413-114">建立新的號碼範圍</span><span class="sxs-lookup"><span data-stu-id="79413-114">Create a new number range</span></span>

- <span data-ttu-id="79413-115">變更現有號碼範圍</span><span class="sxs-lookup"><span data-stu-id="79413-115">Change an existing number range</span></span>

- <span data-ttu-id="79413-116">刪除號碼範圍</span><span class="sxs-lookup"><span data-stu-id="79413-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="79413-117">UI 參考</span><span class="sxs-lookup"><span data-stu-id="79413-117">UI Reference</span></span>

<span data-ttu-id="79413-118">下列清單說明頁面上的命令。</span><span class="sxs-lookup"><span data-stu-id="79413-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="79413-119">**新** 啟動新的通話駐留號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="79413-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="79413-120">**編輯** 開啟選取的號碼範圍進行編輯、選取清單中的所有號碼範圍，或刪除選取的號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="79413-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="79413-121">**Refresh** 重新整理號碼範圍清單。</span><span class="sxs-lookup"><span data-stu-id="79413-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="79413-122">下列清單說明頁面上的欄位。</span><span class="sxs-lookup"><span data-stu-id="79413-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="79413-123">**名稱** 識別號碼範圍的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="79413-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="79413-124">**起始範圍** 範圍的開始號碼。</span><span class="sxs-lookup"><span data-stu-id="79413-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="79413-125">**結束範圍** 範圍的結束號碼。</span><span class="sxs-lookup"><span data-stu-id="79413-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="79413-126">**目的地** 主機號碼範圍內主控通話駐留應用程式之應用程式服務的完整功能變數名稱 (FQDN) 或服務識別碼。</span><span class="sxs-lookup"><span data-stu-id="79413-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="79413-127">如需通話駐留功能及功能的詳細資訊，請參閱 [在商務用 Skype 2015 中規劃通話駐留](../../plan-your-deployment/enterprise-voice-solution/call-park.md)。</span><span class="sxs-lookup"><span data-stu-id="79413-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="79413-128">如需使用通話駐留號碼範圍的詳細資訊，請參閱 [設定寄存通話的電話號碼分機號碼](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="79413-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


