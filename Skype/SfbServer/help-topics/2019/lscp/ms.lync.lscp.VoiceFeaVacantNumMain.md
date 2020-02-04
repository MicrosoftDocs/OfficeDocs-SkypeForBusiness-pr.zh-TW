---
title: 未指派電話號碼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: 未指派號碼是對您的組織有效但未指派給使用者或電話的電話號碼。未指派號碼表指出您希望如何處理撥打至未指定號碼的通話。
ms.openlocfilehash: 910b83f18350bc2a26da281f2e0660e8aa8913b9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41690388"
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="2440d-104">未指派電話號碼</span><span class="sxs-lookup"><span data-stu-id="2440d-104">Unassigned Phone Number</span></span>

> [!NOTE]
> <span data-ttu-id="2440d-105">當您將商務用 Skype 2019 與 Exchange 2013 或 Exchange 2016 整合時，Exchange UM 仍可在商務用 Skype Server 2019 中使用。</span><span class="sxs-lookup"><span data-stu-id="2440d-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="2440d-106">由於 Exchange 2019 中的支援變更，因此需要取消 Exchange UM 整合，以取代雲端語音信箱和雲端自動語音應答功能。</span><span class="sxs-lookup"><span data-stu-id="2440d-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="2440d-p103">未指派號碼是對您的組織有效但未指派給使用者或電話的電話號碼。未指派號碼表指出您希望如何處理撥打至未指定號碼的通話。</span><span class="sxs-lookup"><span data-stu-id="2440d-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

<span data-ttu-id="2440d-p104">設定未指派號碼表的方式取決於其使用方式。您可以設定包含組織所有有效分機號碼、只包含未指派的分機號碼，或包含結合這兩種類型之號碼的表格。未指派號碼表可以同時包含已指派和未指派的號碼，但是只有在來電者撥打目前未指派的號碼時才會叫用。如果您在未指派號碼表中納入所有有效的分機號碼，可以指定每次某人離開組織時要執行的動作，而不必重新設定表格。如果表格中包含未指派的分機號碼，您可以針對特定號碼設計要採取的動作。例如，如果您變更客服人員的分機號碼，則可以在表格中包含舊的客服號碼，並且將它指派給提供新號碼的宣告。</span><span class="sxs-lookup"><span data-stu-id="2440d-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2440d-115">您必須先定義一個或多個宣告或設定 Exchange UM 自動語音應答，才能設定未指派號碼表。</span><span class="sxs-lookup"><span data-stu-id="2440d-115">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="2440d-116">「未指派的號碼」\*\*\*\* 頁面會顯示為組織定義的未指派號碼範圍清單。</span><span class="sxs-lookup"><span data-stu-id="2440d-116">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="2440d-117">您可以執行的工作</span><span class="sxs-lookup"><span data-stu-id="2440d-117">Tasks you can perform</span></span>

<span data-ttu-id="2440d-118">您可以在「未指派的號碼」\*\*\*\* 頁面上執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="2440d-118">You can perform the following tasks from the **Unassigned Number** page:</span></span>

- <span data-ttu-id="2440d-119">建立新的未指派號碼範圍</span><span class="sxs-lookup"><span data-stu-id="2440d-119">Create a new unassigned number range</span></span>

- <span data-ttu-id="2440d-120">變更現有的未指派號碼範圍</span><span class="sxs-lookup"><span data-stu-id="2440d-120">Change an existing unassigned number range</span></span>

- <span data-ttu-id="2440d-121">刪除未指派的號碼範圍</span><span class="sxs-lookup"><span data-stu-id="2440d-121">Delete an unassigned number range</span></span>

- <span data-ttu-id="2440d-122">變更未指派的號碼範圍順序，以決定哪個動作要先套用至符合未指派號碼的來電。</span><span class="sxs-lookup"><span data-stu-id="2440d-122">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="2440d-123">UI 參考</span><span class="sxs-lookup"><span data-stu-id="2440d-123">UI Reference</span></span>

<span data-ttu-id="2440d-124">下列清單說明頁面上的命令。</span><span class="sxs-lookup"><span data-stu-id="2440d-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="2440d-125">**新增**開始新的未指派的數位範圍。</span><span class="sxs-lookup"><span data-stu-id="2440d-125">**New** Starts a new unassigned number range.</span></span>

- <span data-ttu-id="2440d-126">[**編輯**]開啟選取的未指定的數位範圍進行編輯，選取清單中所有未指定的數位範圍，或刪除選取的未指定的數位範圍。</span><span class="sxs-lookup"><span data-stu-id="2440d-126">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>

- <span data-ttu-id="2440d-127">**上移**在清單中將選取的未指派的數位範圍往上移動，讓商務用 Skype 伺服器更快找到並套用指定的動作，然後再針對清單中的其他範圍套用所指定的動作。</span><span class="sxs-lookup"><span data-stu-id="2440d-127">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2440d-128">商務用 Skype Server 會從上到下搜尋 [未指定的數位] 資料表，並使用符合未指定數位的第一個範圍。</span><span class="sxs-lookup"><span data-stu-id="2440d-128">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="2440d-129">例如，如果您有一個範圍指定的是最後不得不採取的動作，請確定該範圍位於清單底部。</span><span class="sxs-lookup"><span data-stu-id="2440d-129">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

- <span data-ttu-id="2440d-130">**向下移動**在清單中將選取的未指派的數位範圍向下移動。</span><span class="sxs-lookup"><span data-stu-id="2440d-130">**Move down** Moves the selected unassigned number range down in the list.</span></span>

- <span data-ttu-id="2440d-131">**全部確認**儲存您對未指派的數位範圍所做的所有變更。</span><span class="sxs-lookup"><span data-stu-id="2440d-131">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2440d-132">此命令會儲存您在「新增未指派的號碼」\*\*\*\* 頁面和「編輯未指派的號碼」\*\*\*\* 頁面上進行的所有變更。</span><span class="sxs-lookup"><span data-stu-id="2440d-132">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>

- <span data-ttu-id="2440d-133">**更新**刷新未指派的數位範圍清單。</span><span class="sxs-lookup"><span data-stu-id="2440d-133">**Refresh** Refreshes the list of unassigned number ranges.</span></span>

<span data-ttu-id="2440d-134">下列清單說明頁面上的欄位。</span><span class="sxs-lookup"><span data-stu-id="2440d-134">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="2440d-135">**名稱**識別未指定的數位範圍的唯一名稱。</span><span class="sxs-lookup"><span data-stu-id="2440d-135">**Name** The unique name that identifies the unassigned number range.</span></span>

- <span data-ttu-id="2440d-136">**狀態**顯示已儲存至資料庫並沒有的數位範圍。</span><span class="sxs-lookup"><span data-stu-id="2440d-136">**State** Shows which number ranges have been saved to the database and which have not.</span></span>

- <span data-ttu-id="2440d-137">**起始範圍**未指定的數位範圍的起始編號。</span><span class="sxs-lookup"><span data-stu-id="2440d-137">**Start range** The beginning number of the unassigned number range.</span></span>

- <span data-ttu-id="2440d-138">**結束範圍**未指定的數位範圍的結束數位。</span><span class="sxs-lookup"><span data-stu-id="2440d-138">**End range** The ending number of the unassigned number range.</span></span>

- <span data-ttu-id="2440d-139">**目的地**主持宣告應用程式的應用程式服務的服務識別碼，會處理撥入呼叫到此未指定號碼的範圍。</span><span class="sxs-lookup"><span data-stu-id="2440d-139">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

- <span data-ttu-id="2440d-140">**宣告**將針對此未指定編號範圍播放的公告。</span><span class="sxs-lookup"><span data-stu-id="2440d-140">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>

<span data-ttu-id="2440d-141">如需公告功能和功能的詳細資訊，請參閱規劃檔中的[商務用 Skype 中的宣告應用程式規劃](../../../plan-your-deployment/enterprise-voice-solution/announcement.md)。</span><span class="sxs-lookup"><span data-stu-id="2440d-141">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="2440d-142">如需使用未指派號碼範圍的詳細資訊，請參閱作業文件中的〈[Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="2440d-142">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


