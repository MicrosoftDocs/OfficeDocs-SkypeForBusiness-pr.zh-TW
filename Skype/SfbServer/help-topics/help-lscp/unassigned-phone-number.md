---
title: 未指派電話號碼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
description: 未指派號碼是對您的組織有效但未指派給使用者或電話的電話號碼。未指派號碼表指出您希望如何處理撥打至未指定號碼的通話。
ms.openlocfilehash: 88852088b4b664665750ef0e6167ba98b506a501
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193914"
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="675d4-104">未指派電話號碼</span><span class="sxs-lookup"><span data-stu-id="675d4-104">Unassigned Phone Number</span></span>

<span data-ttu-id="675d4-p102">未指派號碼是對您的組織有效但未指派給使用者或電話的電話號碼。未指派號碼表指出您希望如何處理撥打至未指定號碼的通話。</span><span class="sxs-lookup"><span data-stu-id="675d4-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

<span data-ttu-id="675d4-p103">設定未指派號碼表的方式取決於其使用方式。您可以設定包含組織所有有效分機號碼、只包含未指派的分機號碼，或包含結合這兩種類型之號碼的表格。未指派號碼表可以同時包含已指派和未指派的號碼，但是只有在來電者撥打目前未指派的號碼時才會叫用。如果您在未指派號碼表中納入所有有效的分機號碼，可以指定每次某人離開組織時要執行的動作，而不必重新設定表格。如果表格中包含未指派的分機號碼，您可以針對特定號碼設計要採取的動作。例如，如果您變更客服人員的分機號碼，則可以在表格中包含舊的客服號碼，並且將它指派給提供新號碼的宣告。</span><span class="sxs-lookup"><span data-stu-id="675d4-p103">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="675d4-113">您必須先定義一個或多個宣告或設定 Exchange UM 自動語音應答，才能設定未指派號碼表。</span><span class="sxs-lookup"><span data-stu-id="675d4-113">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="675d4-114">「未指派的號碼」\*\*\*\* 頁面會顯示為組織定義的未指派號碼範圍清單。</span><span class="sxs-lookup"><span data-stu-id="675d4-114">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="675d4-115">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="675d4-115">Tasks you can perform</span></span>

<span data-ttu-id="675d4-116">您可以在「未指派的號碼」\*\*\*\* 頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="675d4-116">You can perform the following tasks from the **Unassigned Number** page:</span></span>

- <span data-ttu-id="675d4-117">建立新的未指派號碼範圍</span><span class="sxs-lookup"><span data-stu-id="675d4-117">Create a new unassigned number range</span></span>

- <span data-ttu-id="675d4-118">變更現有的未指派號碼範圍</span><span class="sxs-lookup"><span data-stu-id="675d4-118">Change an existing unassigned number range</span></span>

- <span data-ttu-id="675d4-119">刪除未指派的號碼範圍</span><span class="sxs-lookup"><span data-stu-id="675d4-119">Delete an unassigned number range</span></span>

- <span data-ttu-id="675d4-120">變更未指派的號碼範圍順序，以決定哪個動作要先套用至符合未指派號碼的來電。</span><span class="sxs-lookup"><span data-stu-id="675d4-120">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="675d4-121">UI 參考</span><span class="sxs-lookup"><span data-stu-id="675d4-121">UI Reference</span></span>

<span data-ttu-id="675d4-122">下列清單說明頁面上的命令。</span><span class="sxs-lookup"><span data-stu-id="675d4-122">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="675d4-123">**新增**開始新的未指派的數位範圍。</span><span class="sxs-lookup"><span data-stu-id="675d4-123">**New** Starts a new unassigned number range.</span></span>

- <span data-ttu-id="675d4-124">[**編輯**]開啟選取的未指定的數位範圍進行編輯, 選取清單中所有未指定的數位範圍, 或刪除選取的未指定的數位範圍。</span><span class="sxs-lookup"><span data-stu-id="675d4-124">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>

- <span data-ttu-id="675d4-125">**上移**在清單中將選取的未指派的數位範圍往上移動, 讓商務用 Skype 伺服器更快找到並套用指定的動作, 然後再針對清單中的其他範圍套用所指定的動作。</span><span class="sxs-lookup"><span data-stu-id="675d4-125">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="675d4-126">商務用 Skype Server 會從上到下搜尋 [未指定的數位] 資料表, 並使用符合未指定數位的第一個範圍。</span><span class="sxs-lookup"><span data-stu-id="675d4-126">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="675d4-127">例如，如果您有一個範圍指定的是最後不得不採取的動作，請確定該範圍位於清單底部。</span><span class="sxs-lookup"><span data-stu-id="675d4-127">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

- <span data-ttu-id="675d4-128">**向下移動**在清單中將選取的未指派的數位範圍向下移動。</span><span class="sxs-lookup"><span data-stu-id="675d4-128">**Move down** Moves the selected unassigned number range down in the list.</span></span>

- <span data-ttu-id="675d4-129">**全部確認**儲存您對未指派的數位範圍所做的所有變更。</span><span class="sxs-lookup"><span data-stu-id="675d4-129">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="675d4-130">此命令會儲存您在「新增未指派的號碼」\*\*\*\* 頁面和「編輯未指派的號碼」\*\*\*\* 頁面上進行的所有變更。</span><span class="sxs-lookup"><span data-stu-id="675d4-130">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>

- <span data-ttu-id="675d4-131">**更新**刷新未指派的數位範圍清單。</span><span class="sxs-lookup"><span data-stu-id="675d4-131">**Refresh** Refreshes the list of unassigned number ranges.</span></span>

<span data-ttu-id="675d4-132">下列清單說明頁面上的欄位。</span><span class="sxs-lookup"><span data-stu-id="675d4-132">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="675d4-133">**名稱**識別未指定的數位範圍的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="675d4-133">**Name** The unique name that identifies the unassigned number range.</span></span>

- <span data-ttu-id="675d4-134">**狀態**顯示已儲存至資料庫並沒有的數位範圍。</span><span class="sxs-lookup"><span data-stu-id="675d4-134">**State** Shows which number ranges have been saved to the database and which have not.</span></span>

- <span data-ttu-id="675d4-135">**起始範圍**未指定的數位範圍的起始編號。</span><span class="sxs-lookup"><span data-stu-id="675d4-135">**Start range** The beginning number of the unassigned number range.</span></span>

- <span data-ttu-id="675d4-136">**結束範圍**未指定的數位範圍的結束數位。</span><span class="sxs-lookup"><span data-stu-id="675d4-136">**End range** The ending number of the unassigned number range.</span></span>

- <span data-ttu-id="675d4-137">**目的地**主持宣告應用程式的應用程式服務的服務識別碼, 會處理撥入呼叫到此未指定號碼的範圍。</span><span class="sxs-lookup"><span data-stu-id="675d4-137">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

- <span data-ttu-id="675d4-138">**宣告**將針對此未指定編號範圍播放的公告。</span><span class="sxs-lookup"><span data-stu-id="675d4-138">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>

<span data-ttu-id="675d4-139">如需公告功能和功能的詳細資訊, 請參閱規劃檔中的[商務用 Skype 2015 中的宣告應用程式規劃](../../plan-your-deployment/enterprise-voice-solution/announcement.md)。</span><span class="sxs-lookup"><span data-stu-id="675d4-139">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="675d4-140">如需使用未指派號碼範圍的詳細資訊，請參閱作業文件中的〈[Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="675d4-140">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


